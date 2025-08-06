---
tags:
- flashcards/swe/teoria/2P
---

# Continuous Integration

> [!IMPORTANT]
>
> Este artículo es muy extenso, un consejo de los profes es que lo utilicemos solo para los conceptos de integración continua y sus prácticas asociadas (y nada más que eso).

## Introducción

![[13.1-ci.png]]

- Integración continua: 
	- Práctica del desarrollo de SW.
	- Cada miembro del equipo integra sus cambios a la base de código junto a los cambios de sus pares, al menos una vez al día.
	- Cada integración es verificada mediante un _automated build_ (inclusive las pruebas) con la finalidad de poder detectar errores de integración lo más rápido posible.
- Beneficios usuales:
	- Reduce el riesgo de retrasos en la entrega.
	- Disminución de esfuerzos en cuestiones de integración del código.
	- Fomenta prácticas de una base de código saludable para la mejora rápida mediante la integración de nuevas funcionalidades.

## Problemática común de proyectos de SW

- "La integración de los trabajos de múltiples desarrolladores es un proceso largo e impredecible".
- Escenario:
	- Un dev se encuentra trabajando por varios días sobre una funcionalidad, trayéndose rutinariamente los cambios de _main_.
	- Al momento de querer incorporar sus cambios, aparece un cambio grande en _main_.
	- Esto hace que el desarrollador tenga que cambiar de contexto y discernir cómo integrar sus cambios en los conflictos de merge: lo que resultó bien para su colega no le resultó tan bien para éste.
	- Termina sucediendo que el desarrollador debe ponerse a depurar código ajeno.
	- Las revisiones de PRs pueden tomar tiempo, obligándole a que cambie de contexto con su siguiente funcionalidad tomada.
	- Las pruebas de integración solamente se ejecutan posterior a la integración del código a _main_.
- Consecuencias:
	- El equipo aprende que la modificación del código núcleo causa estos problemas y desalienta a los devs que lo hagan.
	- Esto previene la refactorización y permite que se acumule el _cruft_.
	- Se preguntan cómo es que el código terminó en dicho estado deplorable y usualmente la respuesta reside en que el proceso de integración posee tanta fricción que desalienta a los devs que remuevan dicho _cruft_.
- Solución propuesta:
	- Integración Continua: La esencia yace en la simple práctica de que todos los devs del equipo integren frecuentemente, al menos en forma diaria, contra un repositorio de código fuente.

## Construyendo una funcionalidad con integración continua

![[13.2-ci-example-1.png]]

![[13.3-ci-example-2.png]]

![[13.4-ci-example-3.png]]

![[13.5-ci-example-4.png]]

![[13.6-ci-example-5.png]]

![[13.7-ci-example-6.png]]

![[13.8-ci-example-7.png]]

## Prácticas de la Integración Continua

### Poner todo en una línea principal bajo control de versiones

- Un sistema de control de versiones permite:
	- Encontrar el estado actual del producto SW.
	- Obtener todos los cambios realizados al mismo.
	- Poder volver a un cierto punto del desarrollo.
	- Permite adoptar el _Diff Debugging_:
		- Técnica de depuración utilizada para identificar el cambio específico en el código que introdujo un bug de regresión (un error que aparece en una funcionalidad que antes funcionaba correctamente).
		- Consta en comparar versiones antiguas del SW, donde el bug no existía, con versiones actuales donde el bug sí está presente, para localizar el "commit culpable" mediante un proceso de búsqueda binaria (half-interval o binary search) entre ambas versiones.
		- Requiere que el código esté bajo control de versiones y que se puedan reconstruir fácilmente versiones anteriores del SW (reproducible builds).
- Deberíamos poder, con un entorno mínimamente configurado (una máquina con no más que el SO _vanilla_ instalado):
	- Fácilmente construir y ejecutar el producto luego de haber clonado el repositorio.
	- Recuperar el código fuente, pruebas, esquema de DB, datos de prueba, archivos de configuración (IDEs, scripts, etc.), bibliotecas de terceros (dependencias) y cualquier otra herramienta requerida para construir el producto SW.
- El repositorio no debe almacenar estos elementos, sino que retornarlos:
	- e.g., no tenemos que almacenar el compilador en el repositorio, sino que poder determinar el compilador correcto.
- El sistema de control de versiones debe contener todo lo que permita la construcción del producto, pero no la construcción del producto en sí.
	- e.g., un _smell_ común es almacenar el build de productos. Usualmente implica un problema más profundo: la imposibilidad de recrear builds.
- Debe ser simple encontrar el código de una funcionalidad:
	- e.g., nombres expresivos, esquemas de URLs claros, tanto dentro del repositorio como a nivel organización.
	- e.g., no perder tiempo en tratar de entender cuál rama emplear dentro del sistema de control de versiones: la integración continua se basa en tener una rama principal clara, la cual cumple el papel de "estado actual del producto" y siguiente versión que será deployado a producción.
- Emplear en lo posible archivos de texto para definir el producto y su ambiente:
	- Si bien es posible almacenar y rastrear un archivo que no contiene texto, usualmente no permiten con facilidad ver los cambios que sufrió entre versiones.

### Automatizar el Build

- Cualquier instrucción para la construcción del SW debe ser almacenado en el repositorio, implicando que debemos emplear representaciones textuales.
	- Permite que podamos inspeccionar cómo funciona y qué cambios ha sufrido.
	- Los equipos que practican la integración continua evitan herramientas que requieran interactuar con UIs para construir el SW o configurar un ambiente.
- Si bien es posible emplear lenguajes de programación (e.g., shell scripts) para un simple programa, a medida que se complejiza el sistema es mejor emplear una herramienta diseñada para la automatización de Builds. Estas herramientas suelen:
	- Proveer funciones _built-in_ para tareas usuales.
	- Proveer una lógica particular de organizar el build:
		- Dependency Network:
			- Organiza la lógica en una lista de tareas las cuáles se estructuran como un grafo de dependencias.
			- Para ejecutar una tarea, primero se debe ejecutar todas sus dependencias como "tareas pre-requisito".
	- Permite ahorrar tiempo de compilación al no haber modificado ningún código fuente.
		- e.g., comparar el tiempo de modificación de los archivos: Si alguno de estos fueron modificados posterior al _output_ => La tarea de compilación debe ejecutarse de nuevo.
- Error común: Excluir algo del build automático.

### Hacer que el Build sea _Self-Testing_

- Un programa puede ejecutar, pero esto no significa que haga lo que debe hacer.
	- Es el problema central si queremos integrar con la frecuencia que demanda la integración continua.
	- Si los bugs llegan a producción: surge la tarea abrumadora de corregir los errores sobre una base de código en constante cambio (tests manuales son muy lentos para condecir con la frecuencia de cambio).
- No permitir que los bugs lleguen a producción:
	- Principal técnica: tener un suite de test que se ejecute antes de cada integración para descartar la mayor cantidad de bugs posibles.
		- Conocido como _Self Testing Code_:
			- ![[13.12-self-testing-code.png]]
			- Práctica de escribir tests automatizados en conjunto con el SW funcional.
			- Ante su empleo correcto: Permite invocar un único comando que ejecuta todos los tests y nos permite exponer a la luz cualquier bug en nuestro código.
			- Afecta al flujo del dev: nuestra tarea no termina cuando la feature funciona correctamente, sino que también cuando tenemos los tests automatizados para demostrarlos.
- _Self Testing Code_ es un pre-requisito de la integración continua y se encuentran conjuntamente atadas una a la otra.
	- Integración continua & testing: prácticas núcleos al _Extreme Programming_, estos tipos de tests son escritos mediante TDD.
	- TDD no es esencial para la integración continua: los tests pueden ser escritos posterior al código productivo, siempre y cuando sean realizadas previo a la integración. No obstante, se considera al TDD la mejor forma de escribir _Self Testing Code_.
- Barrera común a la implementación de la integración continua: inaptitud en testing.
- "Los tests no prueban la ausencia de bugs": se prefiere tests imperfectos que se ejecuten seguido por sobre tests perfectos que nunca son escritos.

### Todos integran commits diariamente a la rama principal

- La integración consta principalmente de comunicación, permite comunicar a otros devs los cambios realizados.
- La integración a la rama principal permite darnos cuenta si existe un conflicto entre varios devs.
	- Rápida resolución => Rápida detección.
	- Mayor frecuencia de integración => Menores lugares a investigar por los errores y mayor velocidad de resolución de conflictos.
- Tipos de conflictos:
	- "Merge conflicts": conflictos textuales, son los más fácil de resolver.
	- "Semantic Conflicts": pueden ser integrados a nivel textual, pero causan que el programa se comporte distinto.
		- ![[13.11-semantic-conflicts.png]]
		- e.g., renombrar una función, extraer un efecto dentro de la función pero otro dev no está al tanto de esto (lo extraigo porque no lo quiero allí, pero mi colega no lo sabe en su rama y si lo necesita), etc.
		- Este tipo de conflicto es resoluble mediante _Self Testing Code_ & integrar con mayor frecuencia.
- Fomenta a que los devs modularicen sus trabajos en pequeñas porciones, con poco _delta_ horario y permite llevar contabilidad del progreso.

### Toda integración a la rama principal debería ejecutar un Build

- Si bien la integración diaria del equipo a la rama principal permite mantenerla saludable, en la práctica existen puntos débiles:
	- Falta de disciplina en los devs.
	- Subestimar la frecuencia de actualización y build previo a la integración.
	- Diferencias de entornos de desarrollo entre devs.
- Los servicios de integración continua permiten realizar un build ante cada integración en forma automática.
	- Si el build falla ante cada integración, sabemos que la última integración contiene la falla, reduciendo los lugares a revisar para realizar la corrección.
- Es importante notar que el servicio de CI solamente es empleado sobre la rama principal:
	- Si bien es útil emplearlo y monitorear en múltiples ramas:
		- No es lo mismo que "integración continua": la integración continua consta de "todos integran sus cambios a la rama principal todos los días".
		- Esto es considerado una semi integración.
		- Motivación principal: tener todos los commits coexistiendo en una única rama.
- Si bien es posible adoptar la integración continua sin un servicio de CI, no tiene sentido hacerlo en forma manual cuando la automatización se encuentra ampliamente disponible.
- Confusión usual: Emplear un _daemon_ para la integración continua es simplemente una herramienta, no es la práctica en sí.

### Arreglar Builds rotos inmediatamente

- La integración continua solamente es posible si la rama principal se encuentra saludable.
- Kent Beck: "No existe tarea más prioritaria que arreglar un build fallido".
	- Implica una priorización consciente de un _build fix_ como una tarea urgente y prioritaria.
- Usualmente la forma mejor forma de arreglar un build fallido es revertir el commit erróneo de la rama principal, llevando el sistema al último build consistente.
	- Si se conoce el problema en forma inmediata => [[09-release-management#Roll Forward Plan|Fix con un nuevo commit]].
	- En su defecto => [[09-release-management#Rollback Plan|Revertir la rama principal]] para que el equipo siga trabajando, mientras se intenta entender el problema en forma aislada.
- Es posible tener un _Pending Head_ (_Gated Commit_):
	- El commit se realiza a otra rama hasta que sea exitosa y posteriormente se lo pasa a la rama principal.
	- Si bien permite remover todo riesgo de romper la rama principal, un equipo efectivo raramente debería tener la rama principal rota y las pocas veces que sucede permite dar la visibilidad necesaria para que los integrantes sepan cómo prevenir y evitarlo.

### Mantener veloces los Builds

- La motivación principal de la integración continua es proveer un feedback veloz.
	- La integración continua demanda commits con alta frecuencia => El tiempo de build se acumula cada vez más.
	- Tardanzas usuales: usualmente yace sobre las pruebas, particularmente las que involucran servicios externos tales como DBs.
- Un paso crucial para comenzar es establecer un Deployment Pipeline:
	- Motivación principal: Existen múltiples builds realizados en secuencia.
	- El commit a la rama principal es lo que dispara el primer build (Commit Build).
	- Commit Build:
		- Es el build requerido cuando alguien integra commits a la rama principal.
		- Es el que debe realizarse en forma veloz: como resultado toma varios atajos que reducirá la capacidad de detectar bugs.
	- Debe existir un balance entre la detección de bugs y velocidad: un buen commit build es suficientemente estable para que otras personas trabajen sobre el mismo.
	- Existen pruebas que ralentizan el proceso, las cuáles podemos ejecutarlas en máquinas adicionales, ya que insumen más tiempo.
	- Un ejemplo de esto es el Two Stage Deployment Pipeline:
		- 1° Stage:
			- Compila y ejecuta los tests que son tests unitarios más localizados con servicios lentos, reemplazados por _Test Doubles_ (Reemplazo de objetos productivos con fines de pruebas).
			- Empleado como el _commit build_ y empleado como el principal ciclo CI.
			- Mantenerlo por debajo de los 10 minutos.
		- 2° Stage:
			- Ejecutan un suite de pruebas que le pegan a la DB real e involucra un mayor comportamiento end-to-end (integración). Conlleva varias horas en completarse.
			- Si falla:
				- No posee el mismo "parar todo", pero el equipo apunta arreglar los bugs lo más rápido posible, manteniendo en ejecución el _commit build_.
				- Es una señal que el _commit build_ puede contener un test adicional (aunque existen casos en donde solamente el build secundario).
			- Debido a que son más lentas, no se ejecutan luego de cada commit: ejecutan tan frecuente como puedan, en base al último build correcto.
	- Es posible emplear múltiples máquinas y el paralelismo.
	- Otros ejemplos de proceso de build:
		- Interacción con dependencias: valida por las nuevas versiones y las integra al build.
		- _Contract Tests_: permite detectar si los _Test Double_ deben cambiar su interfaz debido al repentino cambio de la interfaz del verdadero servicio.
		- ![[13.10-contract-tests.png]]

### Esconder el Work-in-Progress

- La integración continua implica integrar en cuanto exista un pequeño avance y el build se encuentre saludable.
	- Sugiere la integración previo a la formación completa de una funcionalidad visible para el usuario y listo para su release. Debemos saber cómo lidiar con código latente.
	- Código latente:
		- Código que es parte de una funcionalidad no completa y presente en el código productivo.
		- El equipo debe garantizar que todo código en la rama principal es de calidad productiva, junto con los tests que validan dicho código.
		- Nunca es ejecutado en producción, pero esto no quita de realizar tests.
- Formas de lidiar con el código latente:
	- Prevenir que el código latente sea ejecutado en producción mediante _Keystone Interfaces_.
		- ![[13.9-keystone-interface.png]]
		- Garantizar que la UI provea un camino hacia la nueva feature es lo último que añadimos a la base de código.
		- Las pruebas pueden seguir validando el código en todos los niveles, salvo dicha UI final.
	- Emplear _Feature Flags_ cuando no sea posible emplear _Keystone Interfaces_.
		- ![[13.14-feature-flags.png]]
		- Consta de validaciones que se hacen al momento de ejecutar código latente.
		- Configurados como parte del ambiente.
			- e.g., .env.ambiente.
			- De esta forma pueden activarse para pruebas, pero deshabilitadas en producción.
		- Aparte de permitir la integración continua, facilitan el _A/B Testing_ y los _[[09-release-management#Canary Deployment|Canary Releases]]_.
		- Posterior al release completo de la funcionalidad, es removido para que no dejar _cruft_ en la base de código.
	- Emplear _Dark Launching_ para probar cosas en producción previo a hacerlos visible ante el usuario: permite atacar el impacto sobre cuestiones de performance.
		- Consta de hablar al nuevo comportamiento o comportamiento modificado en el backend, e invocarlo desde funcionalidades existentes de usuario, sin que los usuario sepan que el mismo es invocado.
		- Es con la finalidad de contemplar la carga adicional e impactos de performance sobre el sistema previo al anuncio de la nueva funcionalidad.
		- ![[13.13-dark-launching.png]]
	- Emplear _Branch by Abstraction_:
		- Útil para casos en donde se requiere de grandes cambios infraestructurales en la base de código:
			- e.g., se desea reemplazar una dependencia (módulo, biblioteca o framework) por otra.
		- Permite cambios graduales => Hacer releases del sistema mientras los cambios siguen en proceso.
		- Genera una interfaz interna de las dependencias siendo reemplazadas. Esta interfaz permite enrutar entre la vieja y nueva lógica, reemplazando gradualmente los flujos de ejecución gradualmente.
- La introducción de una nueva feature debe siempre [[09-release-management#Rollback Plan|asegurarse de que sea _rollbackeable_ en caso de que surja algún problema]].
	- _Parallel Change_:
		- Permite segregar los cambios en varios pasos fácil de revertir y mantenerlos pequeños.
		- e.g., renombrar un campo de una DB: luego de crear el nuevo campo con el nuevo nombre:
			1. Hacer la escritura sobre el viejo y nuevo campo a la vez.
			2. Copiar el dato del campo viejo al nuevo campo.
			3. Remover el campo viejo.

### Probar en un ambiente copia de producción

- Si ejecutamos las pruebas en un entorno distinto a producción, pueden haber diferencias en los resultados que suceden en las pruebas, pero no sucede en producción.
- Queremos entonces que el ambiente de pruebas sea una mímica exacta de producción, con las mismas versiones, SO, dependencias, la misma dirección IP y puertos, sobre el mismo HW, etc.
- La dockerización del SW permite construir el mismo contenedor para el entorno de producción que para el entorno de pruebas. Incluso el entorno del dev.
	- Es mejor incurrir en esta clase esfuerzo y costo, en comparación a tener que _cazar un duende que salió de la cueva_ debido a impedancias entre entornos.
- Algunos SW pretenden ser ejecutados en múltiples entornos, tales como distintos SOs y versiones de plataformas.
	- [[#Mantener veloces los Builds|El pipeline]] debería ser capaz organizar las pruebas para todos estos entornos en forma paralela.
	- Observación: Si el SW pretende ser ejecutado en máquinas con malas conexiones => Garantizar que el entorno de pruebas imite una mala conexión.

### Todos pueden ver qué está ocurriendo (Visibilidad)

- Debido a que la integración continua se trata de comunicación, queremos que todos puedan fácilmente ver el estado del sistema y los cambios que ha sufrido.
- Una de las más importantes a comunicar es el estado del Build de la rama principal:
	- Los servicios de CI poseen paneles que indican el estado de cualquier build en curso.
	- Estos son capaces de emitir notificaciones tanto cuando el build falla o pasa (la sensación de "bien hecho" también es importante).
	- e.g., el estado de CI como un _Badge_ en el README del repositorio.

### Automatizar despliegues

- Mediante la automatización, es posible desplegar varias veces a producción en un día.
- La automatización del despliegue permite:
	- [[09-release-management#Rollback Plan|El rollback automatizado]].
	- Reducir la tensión de despliegues, fomentando a las personas en desplegar con mayor frecuencia => Presentar nuevas funcionalidades a usuarios más rápidamente.
	- El [[09-release-management#Blue / Green Deployment|Blue Green Deployment]] permite con mayor velocidad:
		- Hacer productivo nuevas versiones.
		- Hacer rollback, redirigiendo el tráfico entre las versiones ya desplegadas.
	- Permite una mayor facilidad en la configuración de [[09-release-management#Canary Deployment|Canary Releases]]:
		- Desplegar una nueva versión del producto a un subconjunto de usuarios, con la finalidad de eliminar problemas previo al release para toda la población.
- Cualquier SW sujeto a un dispositivo (e.g., aplicaciones _mobile_) requiere la presente facilidad para probar nuevas versiones de la aplicación, previo al release definitivo en las centrales de aplicaciones (e.g., App Store).
- Importante: La información de la versión de la aplicación debe estar visible al momento de desplegar SW automáticamente (e.g., mediante una pantalla "About" que tenga un build ID que permita la identificación en el sistema de control de versiones, logs, algún EP que retorne la información de la versión, etc.).

## Estilos de integración

Existen 3 estilos de pensar la integración.

### Pre-Release Integration

- Es el más antiguo de todos (Martin lo describe como el que usaban en su anécdota del "_huge, depressing, windowless warehouse full of people working in cubicles_").
- Ve a la integración como una fase más de un proyecto de SW.
	- Es una noción naturalmente parte del ciclo de vida en cascada.
- En estos proyectos:
	- El trabajo es segregado en unidades:
		- Pueden ser realizadas por individuos o equipos pequeños.
	- Cada unidad es una porción del SW:
		- Posee mínima interacción con otras unidades.
	- Son construidas y probadas en forma separada:
		- De aquí proviene el empleo original del término "pruebas unitarias".
	- Una vez que las unidades se encuentran listas => Integradas al producto final:
		- La integración ocurre una sola vez.
		- La integración es seguida de pruebas de integración y un release.
- Existen 2 fases muy visibles:
	1. Todos trabajan en forma paralela.
	2. Existe un único tramo de esfuerzo dedicada a la integración.
- La frecuencia de integración se encuentra sujeta a la frecuencia del release.
	- Usualmente versiones _major_ del SW.
	- Usualmente dimensionadas en meses o años.
- Estos equipos emplean un proceso distinto para los arreglos de bugs urgentes, por lo que pueden ser puestas en producción en forma separada al calendario ordinario de integración.

![[13.15-pre-release-integration.png]]

### Feature Branches

- Es el más popular hoy en día.
- Las funcionalidades son asignadas a individuos o pequeños equipos (Similar a las unidades en el anterior approach).
- En vez de esperar a que todas las unidades estén listas, la integración a la rama principal ocurre ni bien la funcionalidad se encuentra terminada.
- Algunos equipos prefieren hacer el release ante cada integración de una feature, otros prefieren acumular algunas features antes de hacer un release.
- Si bien se espera que cada dev se traiga los cambios de la rama principal frecuentemente, en realidad esta estrategia ese una semi integración:
	- Varios devs pueden traerse los cambios regularmente de la rama principal, pero un dev no ve los cambios de los otros devs hasta que alguno de los devs complete su funcionalidad e integre a la rama principal.
	- Cada dev debe realizar una tarea de integración luego de traerse los cambios de la rama principal.
- "Semi integración":
	- Cada dev combina los cambios en la rama principal con su propia rama local.
	- La integración completa no puede ocurrir hasta que un dev integre sus cambios, implicando otra ronda de semi integraciones.
	- Incluso aunque los devs se traigan los mismo cambios de la rama principal, solamente hemos integrado contra dichos cambios, pero no con los cambios de las ramas locales de cada uno.

![[13.16-feature-branch.png]]

### Continuous Integration

- Cada día se integran nuestros cambios a la rama principal y nos traemos los cambios de los demás a nuestro trabajo local.
- Esto hace que ocurran varios esfuerzos de integración, pero estos esfuerzos son mucho más pequeños.
- Ciertamente es más fácil combinar el trabajo de unas pocas horas, en comparación a un trabajo de varios días.
- Posee la ventaja de establecer una alta frecuencia de integración como punto de referencia, estableciendo hábitos y prácticas que la hace sostenible.

![[13.17-continuous-integration.png]]

### Conclusiones

- Respecto a los 3 estilos de integración, la mayoría de la discusión realmente evoca en la frecuencia de integración.
- Pre-Release Integration:
	- Existe una gran diferencia entre releases mensuales y anuales.
- Feature Branching:
	- Usualmente rinde frutos a una mayor frecuencia de integración, ya que la integración ocurre cuando cada feature es individualmente integrado a la rama principal, en contraposición a esperar un rejunte de funcionalidades.
	- Si el equipo se encuentra adoptando la presente estrategia y todas sus funcionalidades duran menos de 1 día de trabajo => Efectivamente se encuentran aplicando la estrategia de integración continua.
- Pre-Release Integration & Feature Branching:
	- Pueden operar a diferentes frecuencias y es posible cambiar la frecuencia de integración sin cambiar el estilo de integración.
- Integración continua:
	- Es diferente a "Feature Branching con alta frecuencia de integración", en el sentido de que:
		- Desde la propia **definición** es definida como "un estilo con alta frecuencia de integración".
	- Tiene un punto adicional en apuntar a la alta frecuencia de integración como un objetivo en sí y no estar atado a la compleción de una funcionalidad o frecuencia de release.

## Beneficios

Los siguientes son beneficios de **haber incrementado la frecuencia, sin cambiar el estilo de integración**.

### Reducción de riesgos en atrasos de entregas

- Es difícil estimar cuánto tiempo llevará una integración compleja:
	- Puede conllevar mucho tiempo, como también puede ser trivial.
	- Existe la sensación de impredecibilidad.
	- "Integration Hell".
- Toda decisión para aumentar la frecuencia de integración permite reducir este riesgo:
	- Menor # de integración pendiente => Menor # de tiempo impredecible hasta completar el release.
	- Feature Branching:
		- Patea el esfuerzo de integración a las ramas de funcionalidades.
		- Debido a que un dev no tiene idea de lo que está trabajando otro dev, no existe forma de prever cuánto esfuerzo conllevará para la integración contra la rama principal.
		- Si bien puede existir riesgo de que las funcionalidades prioritarias experimenten atrasos por integraciones, es posible prevenir esto no permitiendo la integración de funcionalidades de baja prioridad.
- Cambios pequeños => Toma poco tiempo para resolver integraciones.
- Da una mayor visibilidad del estado actual del producto:
	- No existe ningún esfuerzo de integración a ser realizado previo al release, cualquier esfuerzo de integración ya forma parte del producto.

### Menor tiempo incurrido en integraciones

- Respecto a la relación entre el tiempo que insume las integraciones con el tamaño de la integración:
	  Solamente se puede afirmar que no es lineal.
		- Si existe el doble de código a integrar => Es más probable que se tarde 4 veces más.
		- Es como la relación de necesitar 3 segmentos para conectar 3 nodos, pero 6 segmentos para conectar 4 nodos.
		- La integración es pura y exclusivamente cuestión de conexiones.
- Feature Branching:
	- El tiempo perdido en integraciones lo siente el individuo.
- En la integración continua:
	- La integración es en general un no-evento:
		- Nos traemos los cambios de la rama principal, ejecutamos el build e integramos.
		- Si existe conflicto => Todavía tenemos en mente la afinidad de la poca cantidad de código que hemos escrito.
		- El flujo de trabajo es regular: estamos curtidos y somos incentivados a automatizarlo lo más posible.
	- Existe una mayor colaboración entre miembros del equipo, permitiendo atacar los conflictos de integración antes de que se compliquen más.
	- La alta frecuencia de integración convierte al sistema de control de versiones en un canal de comunicación, capaz de transmitir información que de otro modo quedaría sin decirse.
- Error común: un equipo aprende de la experiencia de una integración traumática, por lo que decide hacer integraciones con todavía menos frecuencia, agravando el problema en el futuro.

### Menos bugs

- Si bien la integración continua no elimina los bugs, permite que sea más fácil encontrarlos y removerlos.
	- Es un síntoma de introducir el _Self-Testing Code_ y no tanto por la alta frecuencia de integración.
	- Instruye un régimen regular de pruebas.
	- Posee otro efecto exponencial en reducir los problemas causados por defectos.
- Bugs acumulativos => Mayor dificultad de removerlos.
	- Comienzan a haber interacciones entre los bugs.
	- Factor psicológico: Al haber varios bugs, los devs tienen menos energía para encontrarlos y removerlos.
- Fenómeno: "La cadencia de introducción de un nuevo cambio implica la introducción de bugs => Personas concluyen que para tener una alta fiabilidad del SW, significa reducir la tasa de releases".
	- Esto fue demostrado que es falso por [DORA Research Program](https://www.martinfowler.com/bliki/StateOfDevOpsReport.html):
		- Equipos élite despliegan a producción con mayor velocidad, con mayor frecuencia y poseen una tasa de incidencias menor al implementar los cambios.
		- Los equipos poseen un nivel de rendimiento alto cuando:
			- Poseen <= 3 ramas activas en el repositorio de la aplicación.
			- Integran las ramas a la rama principal al menos 1 vez al día.
			- No poseen "congelamiento del código" o fases de integración.

### Permite el _refactoring_ para mantener la productividad

- A medida que pasa el tiempo la base de código sufre deterioros:
	- Buenas decisiones del pasado no son lo más óptimo luego de 6 meses de trabajo.
	- La introducción de cambios en la lógica existente hizo que el equipo aprenda que conlleva a integraciones complejas que insumen mucho tiempo y poseen un alto riesgo.
	- Nadie tiene ganas de re-estructurar el código existente, incluso aunque es complicado seguir construyendo sobre el mismo, ralentizando la entrega de nuevas funcionalidades.
- La refactorización es una técnica esencial en atenuar y revertir el proceso de deterioro:
	- Un equipo que refactoriza regularmente posee la técnica disciplinada de mejorar la estructura del código existente mediante pequeñas transformaciones que preservan el comportamiento del código, haciendo que sea más fácil y rápido de introducir nuevas funcionalidades.
	- Estas transformaciones reducen en gran manera las chances de introducir bugs y pueden ser realizadas velozmente, especialmente cuando hay un buen _Self-Testing Code_.
- Esto puede ser arruinado por las integraciones:
	- Un esfuerzo de 2 semanas de refactorizaciones puede ser afectado en gran medida debido a las integraciones de varias partes que estuvieron trabajando sobre la estructura anterior.
	- Esto hace que refactorizar se considere una prohibición.
- La integración continua permite resolver este dilema entre las partes, haciendo que integren frecuentemente y sincronicen sus trabajos.
	- Si algo conflictúa con lo que estamos haciendo, lo sabemos inmediatamente, dándose la oportunidad de hablarles para poder concluir en la mejor forma de proceder.
- **Equipos que insumen mucho esfuerzo en mantener una base de código saludable entregan funcionalidades con mayor velocidad y menor costo**.
	- Tiempo que se incurre en escribir pruebas y refactorizar => Retorno de lo invertido en velocidad de entrega.
	- La integración continua:
		- Es una parte núcleo en permitir que esto suceda en un equipo.
		- En conjunto _con Self-Testing Code_, es la piedra angular de la refactorización.
		- Es un componente clave de esta clase de ecosistema de diseño evolutivo.

### El release a producción es una decisión del negocio

- Situación: Le estamos mostrando una nueva funcionalidad implementada a un stakeholder y nos pregunta "muy bueno todo, esto mejorará el negocio. ¿Cuánto tiempo se estima hasta que esté productiva?"
	- Si la funcionalidad se mostró en una rama no integrada => Quizás semanas o meses, especialmente si la automatización a producción es pobre.
	- Si la funcionalidad se mostró aplicando la integración continua => Debido a que nos permite mantener un [Release-Ready Mainline](https://www.martinfowler.com/articles/branching-patterns.html#release-ready-mainline), la decisión de lanzar la última versión del producto a producción es pura exclusivamente una decisión de negocio.
		- En caso de que los stakeholders lo deseen, es cuestión de minutos en ejecutar una pipeline automatizada para que suceda.
		- Permite a los clientes del SW en tener un mayor control de cuándo las funcionalidades deben ser lanzadas y alienta a que colaboren más estrechamente con el equipo de desarrollo.
- La integración continua y un Release-Ready Mainline remueve una de las barreras más grandes al despliegue con alta frecuencia: clientes y desarrollo.
	- El despliegue con alta frecuencia es valioso ya que permite a nuestros usuarios de obtener nuevas funcionalidades más rápidamente, tal que nos puedan dar un feedback más rápido y se tornan en general más colaborativos en el ciclo de desarrollo.
	- Esta es una de las barreras más grandes para todo desarrollo de SW exitoso.

## ¿Cuándo NO adoptar integración continua?

> Todo posee un costo y las decisiones arquitecturales / procesos usualmente decantan en _trade-offs_.

- La integración continua es uno de los pocos casos en donde existen pocas desventajas en su empleo para un equipo comprometido y con aptitud.
	- "Equipo comprometido":
		- e.g., un buen contraejemplo a esto es un proyecto _open-source_:
			- Existe 1 o 2 mantenedores y varios contribuidores.
			- Los mantenedores le dedican unas pocas horas a la semana en el proyecto.
			- No conocen a los contribuidores muy bien.
			- No poseen una buena visibilidad cuando los contribuidores contribuyen o de transmitir los estándares que deberían seguir los mismos.
			- Este es un caso orientado más a Feature Branching y PRs.
			- En este contexto la integración continua no es posible, aunque los esfuerzos de incrementar la frecuencia de integración puede resultar valiosa.
		- La integración continua es más apropiada para un equipo trabajando full-time en un producto, como el caso usual de un SW comercial, aunque existen varios grises entre un modelo open-source clásico y full-time.
		- Se requiere emplear juicio propio respecto a la política de integración a emplear que encaje al compromiso del equipo.
	- "Equipo con aptitud":
		- Hace alusión a las habilidades del equipo en seguir las prácticas necesarias.
		- Si el equipo intenta aplicar integración continua sin:
			- Un suite de pruebas robusta: no poseen mecanismos de monitorear bugs.
			- Sin automatización: la integración tomará demasiado tiempo, interfiriendo en los flujos de desarrollo.
			- La disciplina de asegurarse en integrar a la rama principal sin tener en verde el build: la rama principal terminará rota todo el tiempo, interrumpiendo el trabajo de varios.
- No se requieren de devs estrellas para implementar la práctica (de hecho, aquellos devs que se consideran "estrellas" son personas que justamente no poseen la disciplina necesaria).
- El problema usualmente yace en encontrar un buen instructor y formar estos hábitos que cristalicen la disciplina.
- Una vez que el equipo se acostumbra al flujo, usualmente es cómodo, fácil y veloz.

---

Nombrar y explicar las 2 situaciones generales en donde NO se debe adoptar la integración continua.
?
- La integración continua es uno de los pocos casos en donde existen pocas desventajas en su empleo para un equipo comprometido y con aptitud.
	- "Equipo comprometido":
		- e.g., un buen contraejemplo a esto es un proyecto _open-source_:
			- Existe 1 o 2 mantenedores y varios contribuidores.
			- Los mantenedores le dedican unas pocas horas a la semana en el proyecto.
			- No conocen a los contribuidores muy bien.
			- No poseen una buena visibilidad cuando los contribuidores contribuyen o de transmitir los estándares que deberían seguir los mismos.
			- Este es un caso orientado más a Feature Branching y PRs.
			- En este contexto la integración continua no es posible, aunque los esfuerzos de incrementar la frecuencia de integración puede resultar valiosa.
		- La integración continua es más apropiada para un equipo trabajando full-time en un producto, como el caso usual de un SW comercial, aunque existen varios grises entre un modelo open-source clásico y full-time.
		- Se requiere emplear juicio propio respecto a la política de integración a emplear que encaje al compromiso del equipo.
	- "Equipo con aptitud":
		- Hace alusión a las habilidades del equipo en seguir las prácticas necesarias.
		- Si el equipo intenta aplicar integración continua sin:
			- Un suite de pruebas robusta: no poseen mecanismos de monitorear bugs.
			- Sin automatización: la integración tomará demasiado tiempo, interfiriendo en los flujos de desarrollo.
			- La disciplina de asegurarse en integrar a la rama principal sin tener en verde el build: la rama principal terminará rota todo el tiempo, interrumpiendo el trabajo de varios.
- No se requieren de devs estrellas para implementar la práctica (de hecho, aquellos devs que se consideran "estrellas" son personas que justamente no poseen la disciplina necesaria).
- El problema usualmente yace en encontrar un buen instructor y formar estos hábitos que cristalicen la disciplina.
- Una vez que el equipo se acostumbra al flujo, usualmente es cómodo, fácil y veloz.
<!--SR:!2025-06-25,1,230-->

---

## Diferencias entre Integración Continua con Trunk-Based Development

- A medida que los servicios CI se volvieron populares, varias personas las emplearon para ejecutar builds regulares en Feature Branches.
	- Como se vio anteriormente, esto no es integración continua.
	- Ha llevado a varias personas en decir (y pensar) que estaban haciendo integración continua cuando en realidad estuvieron haciendo algo completamente distinto, causando confusión.
- Varios atacaron la difusión semántica adoptando un nuevo término: Trunk-Based Development.
	- En general se lo considera un sinónimo de la integración continua y no sufre la confusión de "ejecutar Jenkins sobre nuestras feature branches".
- Martin afirma:
	- Que existen personas tratando de clarificar las diferencias entre ambas, pero dice que no siente que las diferencias expuestas son consistentes ni tampoco convincentes.
	- No emplea el término "Trunk-Based Development", en parte porque no siente que el hecho de adoptar un nuevo nombre es una buena forma de atacar a la difusión semántica, pero especialmente porque renombrar una técnica elimina descaradamente el trabajo de aquellos, especialmente Kent Beck, quién se ha dedicado al desarrollo de la integración continua desde el comienzo.
	- Reconoce que a pesar de que evita emplear dicho término, existen varias fuentes respecto a la integración continua escritas bajo la bandera de "Trunk-Based Development". En particular: https://trunkbaseddevelopment.com/.

## Adopción de integración continua al mismo tiempo que Feature Branching

- En general la integración continua y Feature Branching son approaches mutuamente exclusivos:
	- Varios que adoptan ambos approaches ejecutan servicios CI en sus Feature Branches, lo cuál no es integración continua según visto anteriormente.
- Existe una situación en donde es posible adoptar ambos:
	- Las funcionalidades son tan pequeñas que pueden ser completadas en menos de 1 día.
	- Nuevamente, es un caso muy especial y la mayoría de las personas llamaría esto "integración continua".
- También es perfectamente válido realizar el trabajo de uno en una rama aparte, luego integrarlo contra la rama principal. Es posible hacer esto por si pensamos que accidentalmente podríamos llegar a integrar cambios rotos directamente a la rama principal.
	- La cuestión principal es si estamos integrando en forma continua, no como gestionamos el espacio de trabajo personal.

## Diferencias entre Continuous Integration & Continuous Delivery

- En las etapas tempranas de adopción de la integración continua, el camino a producción consistía a veces en una simple integración contra la rama principal, mientras que en otros era más complejo que eso.
- Esto conllevó a una noción de que existía una actividad más allá de la integración continua que se lidiaba con dicho "camino a producción": _Continuous Delivery_.
	- Objetivo principal:
		- El producto siempre debe encontrarse en un estado en donde podamos lanzar el último build.
		- En esencia, asegurar que el release a producción es una decisión del negocio.

## ¿Dónde encaja el despliegue continuo en todo esto?

- Integración continua:
	- Garantiza que todos integren su código al menos 1 vez al día contra la rama principal.
- Entrega continua:
	- Posterior a la integración continua, conlleva los pasos requeridos para garantizar que el producto sea _liberable_ a producción en cualquier momento deseado.
- Despliegue continuo:
	- Significa que el producto es automáticamente lanzado a producción, al momento en que pase todas las pruebas automatizadas en el pipeline de despliegue.
	- Cada commit integrado a la rama principal como parte de la integración continua, será **automáticamente desplegada a producción**, siempre y cuando todas las validaciones en el pipeline de despliegue hayan pasado.
		- Entrega Continua: Simplemente se asegura de que esto sea posible (y por ende es un pre-requisito del despliegue continuo).

> [!NOTE]
>
> Las preguntas asociadas a sub-apartado fueron integradas con [[09-release-management#Diferencias entre integración continua (CI), entrega continua (CD) y despliegue continuo (CD)|las diferencias entre las 3 prácticas]].
