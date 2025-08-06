---
tags:
- flashcards/swe/teoria/2P
---

# Conceptos clave del SCM

## Item de Configuración (IC)

- Es cualquier elemento:
	- Involucrado en el desarrollo del producto.
	- Que está bajo el control del SCM.
- Para cada item se conoce información específica para poder identificarlo, como por ejemplo:
	- Nombre.
	- Versión.
	- Fecha de creación.
	- Autor.
	- Entre otros atributos.

![[02.1-config-item.png]]

> [!NOTE]
>
> - ¿Por qué nos importan los ICs? Porque son la unidad de trabajo mínima / atómica (indivisible) que administra el SCM.
> - SCM trabaja todo con ICs: Conjunto de ICs, ICs separados, ICs que generen otros ICs que tengan dependencias, relaciones o antecedan a otros.
> - En caso de que sea SW: Debe incluir todos los elementos del [[#¿Qué es el SW?|gráfico de "¿Qué es el SW?"]]
> - Algunos elementos estarán más cerca a la definición de lo que es un IC, mientras que otros pueden no ser un IC.
> - Ejemplos de "información específica para poder identificar a un IC":
> 	- La información que ofrece un commit con GIT es un ejemplo representativo de la información importante de cada uno de los ICs.
> 	- Algo no tan trivial que no ofrece GIT:
> 		- Definición de una convención de nombramiento de los items.
> 		- e.g., https://www.conventionalcommits.org/en/v1.0.0/

---

(Control U5) ¿Qué es un IC?
?
- Es cualquier elemento involucrado en el desarrollo del producto y que está bajo el control del SCM.
- Es considerada la unidad de trabajo mínima / atómica (indivisible) que administra el SCM.
<!--SR:!2025-06-22,1,230-->

¿Qué información nos interesa de cada IC para poder identificarlo?
Para cada item se conoce información específica para poder identificarlo, como por ejemplo:
- Nombre.
- Versión.
- Fecha de creación.
- Autor.
- Entre otros atributos.

¿Por qué nos importan los ICs?::Porque son la unidad de trabajo mínima / atómica (indivisible) que administra el SCM.
<!--SR:!2025-06-22,1,230-->

V o F. SCM puede trabajar con otros elementos que no sean IC.::F. Solamente trabaja con ICs.
<!--SR:!2025-06-22,1,230-->

V o F. Un IC puede incluir elementos que no sean código.::V
<!--SR:!2025-06-22,1,230-->

V o F. Git es un buen ejemplo de "información específica para poder identificar a un IC".::V.
<!--SR:!2025-06-22,1,230-->

V o F. En caso de que sea un SW, debe incluir todos los elementos del [[#¿Qué es el SW?|gráfico de "¿Qué es el SW?"]].::V.
<!--SR:!2025-06-22,1,230-->

---

## Configuración (De SW)

- Es el conjunto de ICs que gestionaremos para la construcción del producto SW (1).
- La Configuración de SW puede o no contener código, dependerá de la etapa en la construcción del producto SW.
- e.g., al iniciar un proyecto, la Configuración puede estar compuesta únicamente por una Especificación de Requerimientos SW.

![[02.2-sw-config.png]]

> [!NOTE]
>
> 1) Cada uno de los ICs del conjunto se encuentran en una "versión importante".
> 	- "Versión importante": Cada vez que generamos una configuración, armamos "algo" que nos importa identificar.
> 	- Cada vez que generemos un IC con una versión, debemos decidir a qué configuración sumarlo.

---

¿Qué es una configuración (de SW)?::Es el conjunto de ICs que gestionaremos para la construcción de nuestro producto SW.
<!--SR:!2025-06-22,1,230-->

V o F. Cada vez que generemos un IC con una versión, debemos decidir a qué configuración sumarlo.::V, ya que en una configuración cada uno de los ICs del conjunto se encuentran en una "versión importante" que nos importa identificar.
<!--SR:!2025-06-22,1,230-->

V o F. La Configuración de SW puede o no contener código, dependerá del momento en la construcción del producto SW.::V, e.g., al iniciar un proyecto, la Configuración puede estar compuesta únicamente por una Especificación de Requerimientos SW.
<!--SR:!2025-06-22,1,230-->

---

## Línea Base (Baseline)

- Representa un estado de la configuración de un conjunto de items en el ciclo de desarrollo, que puede tomarse como punto de referencia para una siguiente etapa del ciclo (1).
- Se establece porque se verifica que esta configuración del item o conjunto de items satisface(n) algunos requerimientos funcionales o técnicos (2).
- Esta línea base puede no contener código y puede no coincidir con un release de SW (3).

> IEEE (IEEE Std. No. 610.12-1990) define a la línea base como "una descripción y revisión acordada de los atributos del producto, que luego sirven como base para un mayor desarrollo y definición del cambio, y este cambio solo se puede realizar a través de procedimientos formales de control de cambios".

![[02.3-baseline.png]]

> [!NOTE]
>
> 1) ‎ 
> - A un conjunto de ICs (configuración) queremos tomarle una "foto" en un instante en particular y denominarla de alguna forma que sea identificable. Ejemplos:
> 	- Versión de enero.
> 	- 1° versión entregable.
> 	- Es el MVP del producto.
> 	- Hicimos el descubrimiento de los requerimientos de un producto y generamos un documento con los mismos.
> 	- Entre otros.
> - No existe una cantidad ni tampoco tiempo definido para hacer un _baseline_: Son momentos importantes durante el desarrollo del proyecto, definido según el _SE Approach_ empleado, que representan acuerdos que hace el equipo sobre la cuál se va a seguir construyendo hacia adelante.
> - Las _baselines_ siguen a nuestro proceso.
> - Siempre existe un _baseline_ para producción.
> 2) ‎ 
> - e.g., si estamos empleando Scrum y solamente tuvimos la planning hasta el momento, esto quiere decir que solamente tenemos armado el Sprint Backlog. Entonces: ¿Tiene sentido generar un baseline?
> 	- Para ello consideramos la pregunta: ¿Es el Sprint Backlog un IC? Teniendo en cuenta que las líneas bases son acuerdos sobre el cuál se va a seguir construyendo hacia adelante, si pensamos en el _Sprint Backlog_:
> 		- Hemos acordado el conjunto de funcionalidades que estaremos desarrollando en el Sprint y lo consensuamos entre todos los presentes: Sobre dicho acuerdo construimos el _Increment_.
> 		- Posteriormente, puede que realicemos todas las historias comprometidas y las tasks asociadas generadas.
> 			- e.g., puede que hayamos comprometido 10 puntos, de los cuáles 8 pudimos cumplir la promesa, pero 7 de los 8 son las historias originales comprometidas, mientras que el 1 restante es un bug que apareció en algún momento y tuvimos que resolverlo.
> 		- Entonces, desde este punto de vista, queremos tener un _baseline_ al finalizar la planning.
> 		- Entonces, el primer _baseline_ del sprint estará compuesto de las historias comprometidas, las tareas definidas por el equipo, las fechas comprometidas, las estimaciones y sus supuestos asociados.
> 		- Exclusivamente son cosas que no son código: solo documentación.
> 		- Es posible tener un PoC, pero en general no tenemos nada de código en estas instancias.
> 		- Las historias de usuario son parte del _baseline_, aunque ya nos lleguen a nuestras manos para ser analizadas, previo a la planning.
> 3) ‎ 
> - Tenemos tendencia de solo estimar la parte de Código. En estimaciones vimos que hay que tener en cuenta todo a la hora de estimar => Para SCM también hay que tener en cuenta todo a la hora de estimar.
> - Existen ICs que quedarán con el proyecto y pertenecen al proyecto.
> - Existen ICs que quedarán con el aplicativo que el proyecto genere/modifique y no con el proyecto.

---

(Control U5) ¿Qué es una línea base?
?
Representa un estado de la configuración de un conjunto de items en el ciclo de desarrollo, que puede tomarse como punto de referencia para una siguiente etapa del ciclo.
<!--SR:!2025-06-22,1,230-->

V o F. Una línea base puede considerársela como una "foto" de un conjunto de ICs (configuración de SW) en un instante en particular y denominarla de alguna forma tal que sea identificable.
?
V. Algunos ejemplos son:
- Versión de enero.
- 1° versión entregable.
- Es el MVP del producto.
- Hicimos el descubrimiento de los requerimientos de un producto y generamos un documento con los mismos.
- Entre otros.
<!--SR:!2025-06-22,1,230-->

V o F. No existe una cantidad ni tampoco tiempo definido para hacer un _baseline_.
?
V. Son momentos importantes durante el desarrollo del proyecto, definido según el _SE Approach_ empleado, que representan acuerdos que hace el equipo sobre la cuál se va a seguir construyendo hacia adelante.
<!--SR:!2025-06-22,1,230-->

V o F. Nuestros procesos deben seguir a las _baselines_.::F, las _baselines_ siguen a nuestro proceso.
<!--SR:!2025-06-22,1,230-->

V o F. Puede no existir un _baseline_ para producción.::F. Siempre existe un base para producción.
<!--SR:!2025-06-22,1,230-->

¿Por qué se establecen las baselines?
?
Se establece porque se verifica que esta configuración del item o conjunto de items satisface(n) algunos requerimientos funcionales o técnicos.
<!--SR:!2025-06-22,1,230-->

Si o no, justifique. Si estamos empleando Scrum y solamente tuvimos la planning hasta el momento, esto quiere decir que solamente tenemos armado el Sprint Backlog. Entonces: ¿Tiene sentido generar un baseline?
?
- Para ello consideramos la pregunta: ¿Es el Sprint Backlog un IC? Teniendo en cuenta que las líneas bases son acuerdos sobre el cuál se va a seguir construyendo hacia adelante, si pensamos en el _Sprint Backlog_:
	- Hemos acordado el conjunto de funcionalidades que estaremos desarrollando en el Sprint y lo consensuamos entre todos los presentes: Sobre dicho acuerdo construimos el _Increment_.
	- Posteriormente, puede que realicemos todas las historias comprometidas y las tasks asociadas generadas.
		- e.g., puede que hayamos comprometido 10 puntos, de los cuáles 8 pudimos cumplir la promesa, pero 7 de los 8 son las historias originales comprometidas, mientras que el 1 restante es un bug que apareció en algún momento y tuvimos que resolverlo.
	- Entonces, desde este punto de vista, queremos tener un _baseline_ al finalizar la planning.
	- Entonces, el primer _baseline_ del sprint estará compuesto de las historias comprometidas, las tareas definidas por el equipo, las fechas comprometidas, las estimaciones y sus supuestos asociados.
	- Exclusivamente son cosas que no son código: solo documentación.
	- Es posible tener un PoC, pero en general no tenemos nada de código en estas instancias.
	- Las historias de usuario son parte del _baseline_, aunque ya nos lleguen a nuestras manos para ser analizadas, previo a la planning.
<!--SR:!2025-06-22,1,230-->

V o F. Una línea base puede no contener código.::V
<!--SR:!2025-06-22,1,230-->

V o F. Una línea base puede no coincidir con un release de SW.::V
<!--SR:!2025-06-22,1,230-->

V o F. Tenemos tendencia solo estimar el Código del producto SW.::V
<!--SR:!2025-06-22,1,230-->

V o F. Para SCM también hay que tener en cuenta todo a la hora de estimar.V. En estimaciones vimos que hay que tener en cuenta todo a la hora de estimar y SCM no es una excepción a esto.

V o F. Todos los ICs quedan con el proyecto y pertenecen al proyecto, independientemente de si el ciclo de vida del producto SW se extiende más allá que la del proyecto.::F, existen ICs que quedarán con el proyecto y pertenecen al proyecto, mientras que existen otros ICs que quedarán con el producto SW (aplicativo) que el proyecto genere/modifique y no con el proyecto.
<!--SR:!2025-06-22,1,230-->

---

## ICs de Proceso

- Son los items generados por el proceso de desarrollo. Ejemplos:
	- Plan de CM.
		- El "plan" per sé es el IC de proceso. Tenga o no cambios, es nuestro plan.
		- En caso de cambiar, como todo IC, se tendrá que tener una nueva versión.
	- Propuestas de cambio.
	- Plan de desarrollo:
		- A grande escala: Puede abarcar tanto la cuestión de cuánto tiempo conservar la documentación luego del fin del ciclo de vida del proyecto / aplicación.
		- A pequeña escala: Sprint planning.
	- Plan de calidad.
	- Lista de control de entrega:
		- Es el listado de cómo uno planifica entregar las funcionalidades a lo largo de los distintos sprints.
	- Planes de proyecto.
	- Estimaciones:
		- Uno de los puntos importantes era "conservar histórico" y "conservar supuestos" en repositorios.
	- User Stories: (En caso de emplear Scrum)
		- Aquellas que todavía sean parte del Product Backlog y pueden sufrir modificaciones.
		- El producto todavía no las tiene incorporadas.
	- Repositorios en herramientas colaborativas y de documentación.
	- Interrelación y orquestación entre distintas herramientas (como las relaciones entre GitHub, Jira & Notion).
- Algunos de estos items sólo son gestionados durante una parte de la vida del producto SW.
	- e.g., el plan de proyecto solo es gestionado durante el proyecto y luego se deja de gestionar o se elimina.
- Otros items de proceso pueden seguir siendo gestionado durante toda la vida del producto SW.
	- e.g., el plan de CM.

> [!NOTE]
>
> Son los ICs que se quedan más con el proyecto o el proceso que seguimos para la construcción.

---

¿Qué es un IC de Proceso?
?
- Son los items generados por el proceso de desarrollo. Ejemplos:
	- Plan de CM.
		- El "plan" per sé es el IC de proceso. Tenga o no cambios, es nuestro plan.
		- En caso de cambiar, como todo IC, se tendrá que tener una nueva versión.
	- Propuestas de cambio.
	- Plan de desarrollo:
		- A grande escala: Puede abarcar tanto la cuestión de cuánto tiempo conservar la documentación luego del fin del ciclo de vida del proyecto / aplicación.
		- A pequeña escala: Sprint planning.
	- Plan de calidad.
	- Lista de control de entrega:
		- Es el listado de cómo uno planifica entregar las funcionalidades a lo largo de los distintos sprints.
	- Planes de proyecto.
	- Estimaciones:
		- Uno de los puntos importantes era "conservar histórico" y "conservar supuestos" en repositorios.
	- User Stories: (En caso de emplear Scrum)
		- Aquellas que todavía sean parte del Product Backlog y pueden sufrir modificaciones.
		- El producto todavía no las tiene incorporadas.
	- Repositorios en herramientas colaborativas y de documentación.
	- Interrelación y orquestación entre distintas herramientas (como las relaciones entre GitHub, Jira & Notion).
- Algunos de estos items sólo son gestionados durante una parte de la vida del producto SW.
	- e.g., el plan de proyecto solo es gestionado durante el proyecto y luego se deja de gestionar o se elimina.
- Otros items de proceso pueden seguir siendo gestionado durante toda la vida del producto SW.
	- e.g., el plan de CM.
<!--SR:!2025-06-22,1,230-->

V o F. Algunos ICs de proceso sólo son gestionados durante una parte de la vida del producto SW.::V, un ejemplo es el plan de proyecto: solo es gestionado durante el proyecto y luego se deja de gestionar o se elimina.
<!--SR:!2025-06-22,1,230-->

V o F. Algunos ICs de proceso pueden seguir siendo gestionados durante toda la vida del producto SW.::V, un ejemplo es el plan de CM.
<!--SR:!2025-06-22,1,230-->

---

## ICs de Producto

- Son los items propios del producto SW y que son gestionados durante todo el ciclo de vida del mismo. Son transversales a todos los ciclos de mantenimiento del producto.
- Ejemplos:
	- Requerimientos.
	- Plan de Integración.
	- Manual de Usuario.
	- Arquitectura del SW.
	- Estándares de codificación.
	- Casos de prueba.
	- Código fuente.
	- Documento de despliegue.
	- User Stories:
		- Aquellas que ya no formen parte del Product Backlog, sino que describen el producto.
		- El producto ya las tiene incorporadas.
	- Naming conventions.
	- Repositorios de código.

> [!NOTE]
>
> - Son los ICs que poseen sus tiempos de vida sublevadas al ciclo de vida del producto SW.
> - Los ICs de proceso e ICs de producto pueden tener distintos tiempos de vida.
> 	- En la mayoría de los casos demarcados por cuestiones "legales": Cuánto tiempo hay que conservar la documentación:
> 		- De un proyecto luego de su finalización.
> 		- De una aplicación luego del fin de su ciclo de vida.

---

¿Qué es un IC de producto?
?
- Son los items propios del producto SW y que son gestionados durante todo el ciclo de vida del mismo. Son transversales a todos los ciclos de mantenimiento del producto.
- Ejemplos:
	- Requerimientos.
	- Plan de Integración.
	- Manual de Usuario.
	- Arquitectura del SW.
	- Estándares de codificación.
	- Casos de prueba.
	- Código fuente.
	- Documento de despliegue.
	- User Stories:
		- Aquellas que ya no formen parte del Product Backlog, sino que describen el producto.
		- El producto ya las tiene incorporadas.
	- Naming conventions.
	- Repositorios de código.
<!--SR:!2025-06-22,1,230-->

V o F. Un IC de producto es aquella que posee su ciclo de vida desligada al ciclo de vida del producto SW.::F, poseen sus tiempos de vida ligadas al ciclo de vida del producto SW.
<!--SR:!2025-06-24,3,250-->

V o F. Los ICs de proceso e ICs de producto pueden tener distintos tiempos de vida.
?
V, En la mayoría de los casos demarcados por cuestiones "legales": Cuánto tiempo hay que conservar la documentación:
- De un proyecto luego de su finalización.
- De una aplicación luego del fin de su ciclo de vida.
<!--SR:!2025-06-22,1,230-->

---

## Trazabilidad

Es la capacidad de rastrear un IC a lo largo de todo el proceso.

![[02.4-trazabilidad.png]]

---

(Control U5) ¿Qué es la trazabilidad y para qué sirve?
?
- Es la capacidad de rastrear un IC a lo largo de todo el proceso.
- La trazabilidad sirve para rastrear a todos los ICs:
	- Generados en cada etapa del proceso: por un mismo requerimiento.
	- Del mismo tipo: generados en la misma etapa.
<!--SR:!2025-06-22,1,230-->

---

### Trazabilidad Horizontal

- Representa la capacidad de rastrear todos los ICs generados en cada etapa del proceso por un mismo requerimiento.
- En el gráfico:
	- Poseen un tono más claro.
	- Representadas por aristas punteadas.
		- También representan las relaciones entre los _[[#Item de Configuración (IC)|ICs]]_.
- Existen 4 tipos de _silos_ distintos:
	- Requerimientos.
	- Diseño.
	- Código.
	- Pruebas.

> [!NOTE]
>
> Respecto a un requerimiento, responde a las preguntas:
> - ¿Con qué item lo diseñé?
> - ¿Con qué item lo construí?
> - ¿Con qué item lo probé?
> - ¿Cómo y por qué se originó el problema en producción?
> - ¿Hay que corregir algo de nuestro proceso?
> 	- e.g., para el componente SW, si no estaba contemplada la falla en los casos de prueba, corregimos los casos. En caso de no haber fallado entonces sigo investigando.
> 	- e.g., se establecieron definiciones erróneas respecto a un requerimiento.

> [!NOTE]
>
> En general: Detectar la pieza que falla, entender por qué falla y arreglar el problema de una vez por todas.

---

¿Qué es la trazabilidad horizontal?
?
- Representa la capacidad de tracear todos los ICs generados en cada etapa del proceso por un mismo requerimiento.
- En el gráfico:
	- Poseen un tono más claro.
	- Representadas por aristas punteadas.
		- También representan las relaciones entre los _[[#Item de Configuración (IC)|ICs]]_.
- Existen 4 tipos de _silos_ distintos:
	- Requerimientos.
	- Diseño.
	- Código.
	- Pruebas.
<!--SR:!2025-06-22,1,230-->

---

### Trazabilidad Vertical

- Representa la capacidad de rastrear todos los ICs del mismo tipo, generados en la misma etapa.
- En el gráfico:
	- Los nodos dentro de un mismo _silo_ representan la trazabilidad vertical y poseen un tono más oscuro.
	- Representadas por aristas sólidas.
- Existen 3 grafos en total:
	- Requerimientos -> Diseño.
	- Diseño -> Código.
	- Código -> Pruebas.

> [!NOTE]
>
> Ejemplo:
> - Nos sirve para situaciones en donde tenemos un Sprint Backlog y el mismo se compone de historias de usuario:
> 	- Si cambiamos alguna de estas historias => Impactará sobre el Sprint Backlog.
> 	- Surge la necesidad de tener una trazabilidad vertical: Historias que dependen de otras historias del mismo _silo_, que modifican / se encuentran íntimamente relacionadas ("acopladas") con otras historias.

---

¿Qué es la trazabilidad vertical?
?
- Representa la capacidad de tracear todos los ICs del mismo tipo, generados en la misma etapa.
- En el gráfico:
	- Los nodos dentro de un mismo _silo_ representan la trazabilidad vertical y poseen un tono más oscuro.
	- Representadas por aristas sólidas.
- Existen 3 grafos en total:
	- Requerimientos -> Diseño.
	- Diseño -> Código.
	- Código -> Pruebas.
- Ejemplo: Nos sirve para situaciones en donde tenemos un Sprint Backlog y el mismo se compone de historias de usuario:
	- Si cambiamos alguna de estas historias => Impactará sobre el Sprint Backlog.
	- Surge la necesidad de tener una trazabilidad vertical: Historias que dependen de otras historias del mismo _silo_, que modifican / se encuentran íntimamente relacionadas ("acopladas") con otras historias.
<!--SR:!2025-06-22,1,230-->

---

### Work Product

![[02.7-work-product.png]]

Un producto de trabajo es:

- Una descripción de los elementos de contenido (_content elements_) que se utilizan para definir cualquier cosa que sea usada, producida o modificada por una tarea.
- Un concepto abstracto que generaliza a los tipos concretos de producto de trabajo:
	- _Artifact_.
	- _Outcome_.
	- _Deliverable_.
- Una abstracción para las descripciones de los elementos de contenido (_content elements_) que se utilizan para definir cualquier cosa que sea usada, producida o modificada por una tarea.
	- e.g., distintos roles emplean Productos de Trabajo para realizar tareas y producir Productos de Trabajo a lo largo de la ejecución de las mismas.
- Son responsabilidad de un único rol, lo que facilita identificar y comprender las responsabilidades, y promueve la idea de que cada pieza de información producida en el método requiere las habilidades adecuadas.
	- Si bien un rol podría "ser dueño" de un tipo específico de Producto de Trabajo, otros roles pueden de igual manera emplearlo: quizá incluso actualizarlo si es que se le otorga el permiso para hacerlo.
- "Producto de Trabajo" es el término utilizado para describir lo que en otros procesos denominan "Artefacto", "unidad de trabajo", entre otros (**Esto es lo que sucede en la cátedra de Ingeniería de SW**).

#### Artifact

Un Artefacto es:

- Un Producto de Trabajo que proporciona una descripción y definición para productos de trabajo tangibles y no triviales.
- Productos de Trabajo tangibles y bien definidos que son consumidos, producidos o modificados por Tareas.
	- Pueden estar compuestos de otros Artefactos, e.g., un Artefacto de modelo puede estar compuesto de elementos de modelo, los cuales también son Artefactos.
- Pueden servir como base para definir Activos Reutilizables.
- Los Roles emplean los Artefactos para realizar Tareas y producir Artefactos en el transcurso de la ejecución de dichas Tareas.
- Son responsabilidad de un único rol, lo que facilita identificar y comprender las responsabilidades, y promueve la idea de que cada pieza de información producida en el método requiere las habilidades adecuadas.
	- Si bien un rol podría "ser dueño" de un tipo específico de Artefacto, otros roles pueden de igual manera emplearlo: quizá incluso actualizarlo si es que se le otorga el permiso para hacerlo.
- **Generalmente no son documentos**:
	- Muchos métodos ponen un énfasis excesivo en los documentos, y en particular en la documentación en papel.
	- El enfoque más eficiente y pragmático para gestionar los artefactos del proyecto es mantenerlos dentro de la herramienta adecuada que se utiliza para crearlos y gestionarlos.
	- Cuando sea necesario, se pueden generar documentos (instantáneas) a partir de estas herramientas.
- Ejemplos de Artefactos:
	- Una especificación de casos de uso almacenada en un Word.
	- Un modelo de diseño almacenado en un draw.io.
	- Un plan de proyecto almacenado en Microsoft Project.
	- Un defecto almacenado en un sistema de trazabilidad de "bugs".
	- Una DB de requisitos del proyecto en un documento Confluence.
- Existen artefactos que deben o es más adecuado que sean documentos de texto plano, como en el caso de entradas externas al proyecto o en donde es simplemente el mejor medio para presentar información descriptiva.
- Siempre que sea posible, los equipos deben considerar el uso de herramientas colaborativas de grupos de trabajo (**Work Group tools**) para capturar la documentación textual de forma electrónica, simplificando así la gestión continua de contenidos y versiones.
	- Esto es especialmente importante cuando se deben mantener registros históricos para cumplir con requisitos como auditorías.
- En cualquier esfuerzo de desarrollo no trivial, especialmente cuando se involucran equipos de desarrollo grandes, **es muy probable que los Productos de Trabajo estén sujetos a control de versiones y gestión de la configuración**.
	- No obstante, otras veces esto solo se logra versionando el Producto de Trabajo contenedor, cuando no es posible hacerlo para los Productos de Trabajo elementales que contiene.
		- e.g., se puede controlar la versión de un modelo de diseño completo o paquete de diseño, pero no de las clases individuales que lo componen.

#### Outcome (Resultado)

Un Resultado:

- Describe Productos de Trabajo intangibles que se manifiestan como resultado o estado.
	- e.g., un servidor instalado o una red optimizada.
- Dado que la ocurrencia de un Resultado a menudo se documenta de manera informal (e.g., actas o minutas), los Resultados también pueden ser utilizados para describir Productos de Trabajo que no están definidos formalmente.
- Diferencia clave entre Resultados y Artefactos:
	- Los Resultados no son candidatos para ser aprovechados como activos reutilizables.
	- Los Resultados no pueden tener plantillas o ejemplos asociados.
	- Los Resultados no pueden ser reutilizados como activos en otros proyectos.

#### Deliverable (Entregable)

Un Entregable:

- Es un Producto de Trabajo que proporciona una descripción y definición para empaquetar otros Productos de Trabajo, y puede ser entregado a una parte (_party_) interna o externa.
- Agrupa otros Productos de Trabajo.
- Empleado para predefinir el contenido típico o recomendado en forma de Productos de Trabajo que se empaquetarían para la entrega.
	- El contenido en sí y el empaquetado del entregable pueden ser modificados para cada proyecto en base a estas recomendaciones.
	- Los entregables se emplean para representar un resultado de un proceso que posee valor material o de otra índole, para un cliente, consumidor u otro stakeholder.

## Branching

![[02.5-branching.png]]

- **Branching**:
	- Acción de crear líneas de desarrollo separadas de una línea de trabajo (**branches**).
	- Son mecanismos empleados por los equipos para que puedan desarrollar nuevas funcionalidades utilizando un entorno de trabajo separado del resto.
	- Estas líneas utilizan las líneas base de un repositorio existente como punto de partida.
		- De esta forma, las funcionalidades y bug fixes son desarrolladas por separado, facilitando el trabajo de estos temas en paralelo.
- Permite a los miembros del equipo trabajar en múltiples versiones de un producto, utilizando el mismo conjunto de ICs.

> [!NOTE]
>
> - Surge de la necesidad de tener > de 1 dev en el equipo.
> - Estrategias:
> 	- Por feature.
> 	- Por dev.
> 	- Por equipo.
> 	- Cada Plan de SCM puede decidir cómo aplicarlo y estaría bien para cada organización.
> - Definir la apertura de branches y controlar las _feature branches_:
> 	- e.g., es excesivo tener > 10 branches para un dev, 2 o 3 suenan razonables.

---

¿Qué es el Branching?
?
- Acción de crear líneas de desarrollo separadas de una línea de trabajo (**branches**).
- Son mecanismos empleados por los equipos para que puedan desarrollar nuevas funcionalidades utilizando un entorno de trabajo separado del resto.
- Estas líneas utilizan las líneas base de un repositorio existente como punto de partida.
	- De esta forma, las funcionalidades y bug fixes son desarrolladas por separado, facilitando el trabajo de estos temas en paralelo.
<!--SR:!2025-06-22,1,230-->

El Branching permite a los ==1;;miembros del equipo== trabajar en múltiples versiones de ==1;;un producto==, utilizando el mismo ==1;;conjunto de ICs==.
<!--SR:!2025-06-22,1,230-->

El branching permite definir la ==1;;apertura de branches== y controlar las ==1;;feature branches==.
<!--SR:!2025-06-22,1,230-->

---

## Ambiente (Environment)

![[02.6-environment.png]]

- Un entorno de implementación es una colección de servidores, clústeres y servicios configurados que colaboran para proporcionar un entorno para alojar módulos de SW.
- Cada entorno se construye con un propósito, pudiendo tener características funcionalmente similares pero no necesariamente ser iguales a nivel infraestructura.
	- e.g., los entornos de pre-producción y producción: no necesariamente son iguales a nivel infraestructura pero deberían ser equivalentes a nivel SW.
	- El propósito del ambiente es decidido por la organización o el equipo de trabajo: cada organización o equipo decide para qué será utilizado el ambiente y en qué etapa del proceso de desarrollo.
- Ambientes comunes en el desarrollo suelen ser desarrollo, testing, _staging_, producción.

> [!NOTE]
>
> - Desarrollo: Construcción y pruebas de devs.
> - Testing: Devs todavía realizan modificaciones, testers prueban a funcionalidad cerrada (no las pruebas del dev).
> - Homologación: Prueban testers del lado del cliente.
> - Staging (Pre-producción):
> 	- Más estable, se hacen pruebas y se observa si hay alguna corrección para hacer, luego se pasa a staging nuevamente.
> 	- Pruebas de volumen.
> - Producción.
> - Capacitación: Posterior a la puesta en producción, al siguiente día de despliega una instancia para tener un ambiente controlado con fines de capacitar gente.
> - Esto puede complicarse dependiendo de la organización en que estemos inmersos:
> 	- e.g., para una organización gubernamental, existe un gran volumen de usuarios y con bases de datos de alta volumetría, requiriendo así consideraciones especiales en el manejo, como por ejemplo horarios en los cuáles se puede emplear dicho entorno, entre otros.

> [!NOTE]
>
> - Mayor # de ambientes => Mayor administración y gastos en infraestructura / recursos (físicos y personas).
> - Ser [[01-definiciones#Cosas que comparten las definiciones|cost-effective]]:
> 	- Entender las necesidades para nuestro proceso / proyecto / producto.
> 	- No hace falta tener todos los ambientes para todos los equipos:
> 		- Quizás alcanza con unos cuántos para una cierta etapa.
> 		- Sumar otros más en otra etapa.
> 	- Depende de la etapa del desarrollo de SW actual.

---

¿Qué es un Ambiente (Environment)?
?
- Un entorno de implementación es una colección de servidores, clústeres y servicios configurados que colaboran para proporcionar un entorno para alojar módulos de SW.
- Cada entorno se construye con un propósito, pudiendo tener características funcionalmente similares pero no necesariamente ser iguales a nivel infraestructura.
	- e.g., los entornos de pre-producción y producción: no necesariamente son iguales a nivel infraestructura pero deberían ser equivalentes a nivel SW.
	- El propósito del ambiente es decidido por la organización o el equipo de trabajo: cada organización o equipo decide para qué será utilizado el ambiente y en qué etapa del proceso de desarrollo.
<!--SR:!2025-06-22,1,230-->

Nombrar los ambientes más comunes.::Desarrollo, Testing, Homologación, Staging (pre-producción), Producción, Capacitación, entre otros.
<!--SR:!2025-06-22,1,230-->

A mayor cantidad de ==1;;ambientes== => Mayor ==1;;administración== y ==1;;gastos en infraestructura / recursos (físicos y personas)==.
<!--SR:!2025-06-25,4,270-->

Hay que recordar ser ==1;;cost-effective== al momento de definir los ambientes de la organización o equipo de trabajo.
<!--SR:!2025-06-22,1,230-->

---
