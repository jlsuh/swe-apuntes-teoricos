---
tags:
- flashcards/swe/teoria/2P
---

# Overview

- SW Building.
- SW Releasing.

> [!NOTE]
>
> SWEBOK:
>
> - Release: Distribuir SW y artefactos relacionados fuera de las actividades de desarrollo, incluyendo releases internos y distribución a clientes.
> - Cuando existen distintas versiones de un SW item disponibles para su entrega, tales como versiones de distintas plataformas o versiones con distintos alcances, la re-creación y empaquetado de versiones específicas con los materiales correctos son necesarios con mucha frecuencia.
> - La biblioteca SW es un elemento clave en cumplir las tareas de release y entrega.

---

Nombrar las actividades del Release Management & Delivery.
?
- SW Building.
- SW Releasing.
<!--SR:!2025-06-25,1,230-->

---

# Release Management & Delivery

> Building & Releasing SW.

- Consiste en asegurar la construcción exitosa del paquete de SW, basada en los ICs requeridos para la funcionalidad a entregar, para luego liberarlo en forma controlada a otros entornos ya sea de pruebas, producción, usuario final, etc.
- Se divide en 2 partes:
	- **[[#SW Building|SW Building]]**.
	- **[[#SW Release Management|SW Release Management]]**.
- Comprende también la administración, identificación y distribución de un producto SW.

![[09.1-sw-building-and-sw-release-management.png]]

---

¿En qué consiste el Release Management?
?
- Consiste en asegurar la construcción exitosa del paquete de SW, basada en los ICs requeridos para la funcionalidad a entregar, para luego liberarlo en forma controlada a otros entornos ya sea de pruebas, producción, usuario final, etc.
- Comprende también la administración, identificación y distribución de un producto SW.
<!--SR:!2025-06-25,1,230-->

El Release Management se divide en ==1;;SW Building== y ==1;;SW Release Management==.
<!--SR:!2025-06-25,1,230-->

---

# SW Building

> "Construir el SW".

Es la construcción del paquete de SW que será distribuido, utilizando:
- Las versiones correctas de los ICs.
- Las herramientas apropiadas para construirlo.

> [!NOTE]
>
> e.g., transformar SW en .apk.

---

¿En qué consiste el SW Building?
?
Es la construcción del paquete de SW que será distribuido, utilizando:
- Las versiones correctas de los ICs.
- Las herramientas apropiadas para construirlo.
<!--SR:!2025-06-25,1,230-->

---

## Conceptos Clave de SW Building

### Build & Tipos de Build

#exam-question 

Un Build es el proceso de convertir archivos de código fuente en artefactos de SW independientes que se pueden ejecutar en un entorno.

---

¿Qué es un Build?
?
Es el proceso de convertir archivos de código fuente en artefactos de SW independientes que se pueden ejecutar en un entorno.
<!--SR:!2025-06-25,1,230-->

(Control U5) ¿Qué tipos de Build conoce? Describa brevemente.
?
- Local builds: El developer lo realiza localmente en su entorno de desarrollo, corre Pruebas Unitarias (UT).
- Integration builds:
	- Su objetivo es generar el entorno completo para pruebas de integración.
		- Mover a ambientes de integración (sale de nuestra máquina).
- Nightly builds:
	- Su objetivo es ejecutar la construcción en forma diaria y generar reportes con información sobre estabilidad, tiempo de build, etc.
		- Construir todos los días una versión, sin importar features se encuentran incompletas.
		- Establecer métricas de lo construido durante el día.
- Release builds:
	- Se disparan cuando:
		- Un administrador decide crear una nueva versión a ser liberada.
			- Release Candidate (RC): Candidato a producción.
		- Por el mismo sistema de integración si se utiliza el modo de deployment continuo.
<!--SR:!2025-06-25,1,230-->

---

#### Local builds

El developer lo realiza localmente en su entorno de desarrollo, corre Pruebas Unitarias (UT).

#### Integration builds

Su objetivo es generar el entorno completo para pruebas de integración.

> [!NOTE]
>
> Pensada para mover a ambientes de integración (sale de nuestra máquina).

#### Nightly builds

Su objetivo es ejecutar la construcción en forma diaria y generar reportes con información sobre estabilidad, tiempo de build, etc.

> [!NOTE]
>
> - Construir todos los días una versión.
> - Establecer métricas de lo construido durante el día.
> - No interesa si features se encuentran incompletas.

#### Release builds

Se disparan cuando:

- Un administrador decide crear una nueva versión a ser liberada.
- Por el mismo sistema de integración si se utiliza el modo de deployment continuo.

> [!NOTE]
>
> Release Candidate (RC): Candidato a producción.

### Integración Continua

#### Prácticas

- [[13-obl-continuous-integration-martin-fowler#Todos integran commits diariamente a la rama principal.|Disponer de un repositorio de código único]].
- [[13-obl-continuous-integration-martin-fowler#Automatizar el Build|Automatizar el proceso de build mediante scripts o herramientas]].
- [[13-obl-continuous-integration-martin-fowler#Hacer que el Build sea _Self-Testing_|Hacer el build testeable automáticamente]].
- [[13-obl-continuous-integration-martin-fowler#Toda integración a la rama principal debería ejecutar un Build.|Todo commit debe construirse por una herramienta de integración - no por el dev]] (1).
- [[13-obl-continuous-integration-martin-fowler#Mantener veloces los Builds|El build debe ser rápido]].
- [[13-obl-continuous-integration-martin-fowler#Probar en un ambiente copia de producción|Se prueba en un clon de producción]] (2).
- [[13-obl-continuous-integration-martin-fowler#Poner todo en una línea principal bajo control de versiones|Cualquiera debe obtener fácilmente la última versión del ejecutable]].
- [[13-obl-continuous-integration-martin-fowler#Todos pueden ver qué está ocurriendo (Visibilidad)|Todos deben poder ver qué pasa con el proceso de integración (transparencia)]].
- [[13-obl-continuous-integration-martin-fowler#Automatizar despliegues|Automatizar el proceso de despliegue (deployment)]].

No lo nombra la PPT pero aparecen en el [[13-obl-continuous-integration-martin-fowler|artículo de Fowler]]:

- [[13-obl-continuous-integration-martin-fowler#Esconder el Work-in-Progress|Esconder el Work-in-Progress]].
- [[13-obl-continuous-integration-martin-fowler#Arreglar Builds rotos inmediatamente|Arreglar Builds rotos inmediatamente]].

> [!NOTE]
>
> Estas son prácticas que deben suceder para que se dé la Integración Continua.

> [!NOTE]
>
> 1. Todos trabajan con la misma herramienta.
> 2. "Clon de producción":
> 	- Menos potente que producción.
> 	- Integración con 3eros:
> 		- No todos poseen y ofrecen los mismos ambientes.
> 		- Consideraciones de utilizar Mocks.

---

(Control U5) Nombre 5 prácticas de CI (integración continua).
?
- Disponer de un repositorio de código único.
- Automatizar el proceso de build mediante scripts o herramientas.
- Hacer el build testeable automáticamente.
- Todo commit debe construirse por una herramienta de integración - no por el dev (1).
- El build debe ser rápido.
- Se prueba en un clon de producción (2).
- Cualquiera debe obtener fácilmente la última versión del ejecutable.
- Todos deben poder ver qué pasa con el proceso de integración (transparencia).
- Automatizar el proceso de despliegue (deployment).
- Esconder el Work-in-Progress (solo en artículo de Fowler).
- Arreglar Builds rotos inmediatamente (solo en artículo de Fowler).
<!--SR:!2025-06-25,1,230-->

---

#### Responsabilidades del equipo

- Hacer check-in de código frecuentemente.
- No subir código roto.
- No subir código no testeado.
- No subir código cuando el build no pasa.
- No irse a casa hasta que el build central compile.

---

Nombrar las responsabilidades del equipo para que la CI sea posible.
?
- Hacer check-in de código frecuentemente.
- No subir código roto.
- No subir código no testeado.
- No subir código cuando el build no pasa.
- No irse a casa hasta que el build central compile.
<!--SR:!2025-06-25,1,230-->

---

#### Ventajas / Beneficios de la Integración Continua

Entre las ventajas de integración continua que más se suelen mencionar, se incluyen:

- Detección temprana y mejorada de errores, y métricas que le permiten abordar los errores a tiempo, a veces tras solo unos minutos de la incorporación.
- Progreso continuo para mejorar el feedback.
- Mejor colaboración en equipo: Todos los miembros del equipo pueden:
	- [[13-obl-continuous-integration-martin-fowler#Permite el _refactoring_ para mantener la productividad|Cambiar el código]].
	- [[13-obl-continuous-integration-martin-fowler#Menor tiempo incurrido en integraciones|Integrar el sistema]].
	- [[13-obl-continuous-integration-martin-fowler#Menor tiempo incurrido en integraciones|Determinar rápidamente los conflictos con otras partes del SW]].
- [[13-obl-continuous-integration-martin-fowler#Reducción de riesgos en atrasos de entregas|Integración mejorada del sistema, lo que reduce las sorpresas al final del ciclo de vida de desarrollo del SW]].
- [[13-obl-continuous-integration-martin-fowler#Menos bugs|Menor número de errores durante las pruebas del sistema]].
- Sistemas actualizados constantemente en los que realizar las pruebas.
- **Fin del "en mi máquina funciona"**.

No lo nombra la PPT pero aparece en el [[13-obl-continuous-integration-martin-fowler|artículo de Fowler]].

- [[13-obl-continuous-integration-martin-fowler#El release a producción es una decisión del negocio|El release a producción es una decisión del negocio]].

> [!NOTE]
>
> - Permite mantener un bajo nivel de incertidumbre.
> - Bajos costos.

---

Nombrar las ventajas de la integración continua.
?
- Detección temprana y mejorada de errores, y métricas que le permiten abordar los errores a tiempo, a veces tras solo unos minutos de la incorporación.
- Progreso continuo para mejorar el feedback.
- Mejor colaboración en equipo: Todos los miembros del equipo pueden:
	- Cambiar el código.
	- Integrar el sistema.
	- Determinar rápidamente los conflictos con otras partes del SW.
- Integración mejorada del sistema, lo que reduce las sorpresas al final del ciclo de vida de desarrollo del SW.
- Menor número de errores durante las pruebas del sistema.
- Sistemas actualizados constantemente en los que realizar las pruebas.
- **Fin del "en mi máquina funciona"**.
- El release a producción es una decisión del negocio (solo en artículo de Fowler).
<!--SR:!2025-06-25,1,230-->

---

# SW Release Management

> "Distribuir el producto SW".

- Gestiona la identificación (Identification), ensamblado (packing) y la entrega (Delivery / Deployment) de los elementos de un producto SW (por ejemplo, un ejecutable, documentación, notas de lanzamiento o datos de configuración).
- Define también el proceso de planificación, calendarización y gestión del SW construido a lo largo de las etapas de desarrollo, testing, despliegue y soporte productivo.

> [!NOTE]
>
> - Reglas por fuera del desarrollo, e.g., Freeze bancario a fin de año (usualmente decisiones de altos mandos).
> - El SW Release Management cobra más relevancia a medida que avanza el tiempo:
> 	- e.g., orquestación de Docker/Kubernetes: publicarlos en distintos lugares en la nube.

---

¿En qué consiste el SW Release Management?
?
- Gestiona la identificación (Identification), ensamblado (packing) y la entrega (Delivery / Deployment) de los elementos de un producto SW (por ejemplo, un ejecutable, documentación, notas de lanzamiento o datos de configuración).
- Define también el proceso de planificación, calendarización y gestión del SW construido a lo largo de las etapas de desarrollo, testing, despliegue y soporte productivo.
<!--SR:!2025-06-25,1,230-->

---

## Conceptos Clave de SW Release Management

### Versión

Es una instancia de un sistema que es funcionalmente distinta en algún aspecto de otras instancias.

> [!NOTE]
>
> e.g., [[#Semantic Versioning|Semantic Versioning]].

---

¿Qué es una versión?
?
Es una instancia de un sistema que es funcionalmente distinta en algún aspecto de otras instancias.
<!--SR:!2025-06-25,1,230-->

---

### Variante

Una instancia de un sistema que es funcionalmente igual a otras instancias, pero difiere a niveles no funcionales (Ejemplo: Mismo producto para Version Linux / Version Windows).

> [!NOTE]
>
> - "Generar .apk para Android".
> - "TestFlight para iOS (.ipa)".

---

(Control U5) ¿Qué es una variante?
?
Una instancia de un sistema que es funcionalmente igual a otras instancias, pero difiere a niveles no funcionales (Ejemplo: Mismo producto para Version Linux / Version Windows).
<!--SR:!2025-06-25,1,230-->

---

### Release

El término "Release" utilizado en este contexto, hace referencia a la distribución del SW fuera del entorno de desarrollo. En algunas herramientas, se utiliza el concepto de un "tag" como equivalente de release.

> [!NOTE]
>
> e.g., [Release Candidate (RC) de TypeScript 5.8](https://devblogs.microsoft.com/typescript/announcing-typescript-5-8-rc/).

---

¿Qué es un release?
?
El término "Release" utilizado en este contexto, hace referencia a la distribución del SW fuera del entorno de desarrollo. En algunas herramientas, se utiliza el concepto de un "tag" como equivalente de release.
<!--SR:!2025-06-25,1,230-->

---

## Semantic Versioning

Es una propuesta de un set de reglas y requerimientos que dictaminan como los números de versión son asignados e incrementados.

Resumen de la propuesta:
- Dado un número de versión **MAJOR.MINOR.PATCH**, se incrementa:
	- **MAJOR**:
		- Cuando se realizan cambios incompatibles en la API o SW.
	- **MINOR**:
		- Cuando se agrega funcionalidad de una manera compatible con versiones previas.
	- **PATCH**:
		- Cuando se arreglan bugs de forma compatible con versiones anteriores.
- Se pueden agregar etiquetas adicionales para pre-releases o metadatos de build como extensiones al formato **MAJOR.MINOR.PATCH**.

> Ver https://semver.org/ para más detalles de la propuesta.

---

¿Qué es el Semantic Versioning?
?
Es una propuesta de un set de reglas y requerimientos que dictaminan como los números de versión son asignados e incrementados.
<!--SR:!2025-06-25,1,230-->

¿En qué consiste el Semantic Versioning?
?
Dado un número de versión **MAJOR.MINOR.PATCH**, se incrementa:
- **MAJOR**:
	- Cuando se realizan cambios incompatibles en la API o SW.
- **MINOR**:
	- Cuando se agrega funcionalidad de una manera compatible con versiones previas.
- **PATCH**:
	- Cuando se arreglan bugs de forma compatible con versiones anteriores.
- Se pueden agregar etiquetas adicionales para pre-releases o metadatos de build como extensiones al formato **MAJOR.MINOR.PATCH**.
<!--SR:!2025-06-25,1,230-->

---

## Consideraciones para el Release Management

- Una vez generada la versión o release debemos buscar el mecanismo más efectivo para hacer deploy controlado a los distintos usuarios.
	- A estos mecanismos se los denomina Deployment Strategies.
- Aspectos a evaluar para realizar un release:
	- Qué usuarios deberán recibir los cambios (geográfico, premium, por segmento).
	- En qué forma se deberá hacer el despliegue.
	- Entornos por los que deberá pasar (testing, staging, producción, otros).
	- Procesos de Roll Forward.
	- Procesos de Rollback.
	- Validación de despliegue correcto / incorrecto.
	- Riesgos del despliegue y cómo se minimizan.
	- Aprobación por el negocio y/o área de QA.
	- Quienes realizarán el deployment de la versión definida.

> [!NOTE]
>
> - "La publicación en App Store tarda 2 meses en que nos llegue a todos".
> - "El deploy solo aplica para EEUU".

---

V o F. Una vez generada la versión o release debemos buscar el mecanismo más efectivo para hacer deploy controlado a los distintos usuarios.::V, y son conocidos como Deployment Strategies.
<!--SR:!2025-06-25,1,230-->

Nombrar los aspectos a evaluar para realizar un release.
?
- Qué usuarios deberán recibir los cambios (geográfico, premium, por segmento).
- En qué forma se deberá hacer el despliegue.
- Entornos por los que deberá pasar (testing, staging, producción, otros).
- Procesos de Roll Forward.
- Procesos de Rollback.
- Validación de despliegue correcto / incorrecto.
- Riesgos del despliegue y cómo se minimizan.
- Aprobación por el negocio y/o área de QA.
- Quienes realizarán el deployment de la versión definida.
<!--SR:!2025-06-25,1,230-->

---

### Rollback Plan

- Deshacer cambios realizados a un sistema en caso de una falla inesperada.
- Plan: Revertir el SW a su estado o versión anterior funcional.
- Ventajas:
	- Es más conservativo y transmite mayor seguridad a stakeholders.
- Desventajas:
	- Disruptivos y consume tiempo: pruebas para garantizar que el problema se solventó.

---

¿En qué consiste un Rollback Plan? Explicar también su plan, ventaja y desventaja.
?
- Consiste en deshacer cambios realizados a un sistema en caso de una falla inesperada.
- Plan: Revertir el SW a su estado o versión anterior funcional.
- Ventajas:
	- Es más conservativo y transmite mayor seguridad a stakeholders.
- Desventajas:
	- Disruptivos y consume tiempo: pruebas para garantizar que el problema se solventó.
<!--SR:!2025-06-25,1,230-->

---

### Roll Forward Plan

- Solventar el problema avanzando en el proceso de desarrollo de SW.
- Plan: No revertir a una versión anterior, sino que realizar arreglos en la versión actual del sistema y seguir hacia adelante.
- Ventajas:
	- Más proactivos: solventar el error más rápido, ahorrando tiempo y recursos.
	- Promoción de cultura de mejora continua e innovación.
- Desventajas:
	- Requiere un mayor nivel de experiencia para su implementación eficaz.
	- Puede introducir nuevos errores.

---

¿En qué consiste un Roll Forward Plan? Explicar también su plan, ventaja y desventaja.
- Consiste en solventar el problema avanzando en el proceso de desarrollo de SW.
- Plan: No revertir a una versión anterior, sino que realizar arreglos en la versión actual del sistema y seguir hacia adelante.
- Ventajas:
	- Más proactivos: solventar el error más rápido, ahorrando tiempo y recursos.
	- Promoción de cultura de mejora continua e innovación.
- Desventajas:
	- Requiere un mayor nivel de experiencia para su implementación eficaz.
	- Puede introducir nuevos errores.

---

### Consideraciones de los procesos de Rollback & Roll Forward

- Establecer puntos de control:
	- En conjunto a los planes de Rollback & Roll Forward, establecer un punto que, a partir del mismo en adelante, se considere que no existe más la posibilidad de un Rollback.
	- [Punto de no retorno](https://www.youtube.com/watch?v=cYH-eun23vo):
	![[09.8-point-of-no-return.png]]
- Emplear _Feature Flags_: Permite la coordinación, previo al lanzamiento definitivo de la feature.
	- e.g., Github permite las "Feature Previews".
- Ejemplos de imposibilidades:
	- "Modificación de una DB".
	- "No existe más dicho componente como tal".
	- "Sujeto a una ley o decreto firmado por presidente de la nación".

> [!IMPORTANT]
>
> Rollback & Roll Forward no son estrategias de despliegue: son parte del plan de despliegue de la estrategia de despliegue seleccionada.

---

V o F. Un Feature Flag permite la coordinación, previo al lanzamiento definitivo de la feature.::V, un ejemplo posible son las "Feature Previews" en Github.
<!--SR:!2025-06-25,1,230-->

Una consideración de los procesos de Rollback & Roll Forward es ==1;;establecer puntos de control==.
<!--SR:!2025-06-25,1,230-->

¿En qué consiste el "punto de no retorno"?
?
- Es un instante de tiempo en donde a partir del mismo en adelante se debe considerar que no existe más la posibilidad de un Rollback.
- ![[09.8-point-of-no-return.png]]
- e.g., "modificación de una DB", "no existe más dicho componente como tal", "sujeto a una ley o decreto firmado por el presidente de la nación", etc.
<!--SR:!2025-06-25,1,230-->

V o F. Rollback & Roll Forward son estrategias de despliegue.::F, NO son estrategias de despliegues, en su lugar, son parte del plan de despliegue de la estrategia de despliegue seleccionada.
<!--SR:!2025-06-25,1,230-->

---

## Integración Continua

- La integración continua (CI) es una práctica de desarrollo de SW mediante la cual los desarrolladores combinan los cambios en el código en un repositorio central de forma periódica, tras lo cual se ejecutan versiones y pruebas automáticas.
- La integración continua:
	- Se refiere en su mayoría a la fase de creación o integración del proceso de publicación de SW.
	- Conlleva un componente de:
		- Automatización:
			- e.g., CI o servicio de versiones.
		- Cultural:
			- e.g., aprender a integrar con frecuencia.
- Es una práctica requerida para poder realizar entregas continuas (Continuous Delivery).

## Continuous Delivery

![[09.2-continuous-delivery.png]]

- La Entrega Continua es un conjunto de prácticas que permiten asegurar que el SW puede desplegado en producción rápidamente y en cualquier momento, aplicando el concepto de Pipelines.
- Los artefactos resultantes del proceso de construcción incluyen código ejecutable y bibliotecas, que luego se puede combinar en una "instalación paquete" e implementado en un entorno para verificación o uso de producción.
- Esto lo logra haciendo que cada cambio llegue a un entorno de staging o semi productivo, donde se corren pruebas exhaustivas del sistema. Luego se puede pasar a producción en forma manual cuando alguien aprueba el cambio con solo apretar un botón.

> [!NOTE]
>
> Cimientos del Continuous Delivery: Pipelines.

---

¿Qué es la entrega continua?
?
La Entrega Continua es un conjunto de prácticas que permiten asegurar que el SW puede desplegado en producción rápidamente y en cualquier momento, aplicando el concepto de Pipelines.
<!--SR:!2025-06-25,1,230-->

Los artefactos resultantes del proceso de construcción incluyen ==1;;código ejecutable== y ==1;;bibliotecas==.
<!--SR:!2025-06-25,1,230-->

Los artefactos resultantes del proceso de construcción se pueden combinar en ==1;;una "instalación paquete"== e implementado en un ==1;;entorno para verificación== o ==1;;uso de producción==.
<!--SR:!2025-06-25,1,230-->

La entrega continua se logra haciendo que cada cambio llegue a un entorno de ==1;;staging== o ==1;;semi productivo==, donde se corren ==1;;pruebas exhaustivas del sistema==.
<!--SR:!2025-06-25,1,230-->

La entrega continua puede hacer el pasaje a producción en forma ==1;;manual== cuando alguien ==1;;aprueba el cambio== con solo apretar un botón.
<!--SR:!2025-06-25,1,230-->

Los cimientos del Continuous Delivery son los ==1;;Pipelines==.
<!--SR:!2025-06-25,1,230-->

---

### Pipelines en Continuous Delivery

- Para poder cumplir con el objetivo, los procesos de Continuous Delivery establecen un pipeline de acciones para poder construir e instalar el producto SW.
- Usualmente estos Pipelines suelen contener las siguientes etapas:
	- Testing & QA del SW Construido:
		- Ejecuta las pruebas automáticas.
	- Change Management, Governance, and Approvals:
		- Contiene las actividades de aprobación de los cambios a desplegar.
	- Deployment Strategies:
		- Define la estrategia con la que el SW será desplegado en el ambiente.
	- Verification:
		- Define las actividades para verificar que el SW fue correctamente desplegado.
	- Rollback:
		- Define las acciones para volver al estado anterior, en el caso de que falle la verificación.

---

Para poder cumplir con el objetivo, los procesos de Continuous Delivery establecen un ==1;;pipeline de acciones== para poder ==1;;construir== e ==1;;instalar== el producto SW.
<!--SR:!2025-06-25,1,230-->

Nombrar las etapas que usualmente suelen contener los pipelines.
?
- Testing & QA del SW Construido:
	- Ejecuta las pruebas automáticas.
- Change Management, Governance, and Approvals:
	- Contiene las actividades de aprobación de los cambios a desplegar.
- Deployment Strategies:
	- Define la estrategia con la que el SW será desplegado en el ambiente.
- Verification:
	- Define las actividades para verificar que el SW fue correctamente desplegado.
- Rollback:
	- Define las acciones para volver al estado anterior, en el caso de que falle la verificación.
<!--SR:!2025-06-25,1,230-->

---

## CD (Continuous Delivery) Vs. CD (Continuous Deployment)

![[09.3-cd-vs-cd.png]]

El **Continuous Deployment** es el paso siguiente al **Continuous Delivery**, en donde el despliegue a producción (en el Continuous Deployment) se realiza en forma automática por un proceso y no por personas.

> [!NOTE]
>
> - Para entender esta diferencia referirse a las [[13-obl-continuous-integration-martin-fowler#¿Dónde encaja el despliegue continuo en todo esto?|definiciones dadas por Martin Fowler]].
> - Continuous Delivery:
> 	- Aprobado por humano: validado.
> 	- SCCB:
> 		- Aprueban o no el delivery.
> 		- Inciden varios stakeholders y son capaces de frenar el deploy.
> - Continuous Deployment:
> 	- Automático: debe tener la capacidad de Rollback y Roll Forward.

---

¿Cuál es la diferencia fundamental entre entrega continua y despliegue continuo?
?
El **Continuous Deployment** es el paso siguiente al **Continuous Delivery**, en donde el despliegue a producción (en el Continuous Deployment) se realiza en forma automática por un proceso y no por personas.
<!--SR:!2025-06-25,1,230-->

El Continuous Delivery es a la ==1;;"aprobación y validación por un humano"==, como Continuous Deployment es a la ==1;;"automatización"==.
<!--SR:!2025-06-25,1,230-->

La aprobación en la entrega continua está dada por ==1;;el SCCB==.
<!--SR:!2025-06-25,1,230-->

---

## Diferencias entre integración continua (CI), entrega continua (CD) y despliegue continuo (CD)

![[09.7-ci-cd.png]]

---

Realizar un diagrama de dependencias entre los 3 conceptos.
?
Integración continua => Entrega continua => Despliegue continuo.
<!--SR:!2025-06-25,1,230-->

---

### Integración Continua (CI)

- Es un proceso de desarrollo de SW en el que los desarrolladores integran el código nuevo que han escrito con una mayor frecuencia a lo largo del ciclo de desarrollo, y lo añaden a la base de código al menos una vez al día.
- Se realizan pruebas automáticas en cada iteración de la compilación para identificar los problemas de integración con más rapidez, cuando son más fáciles de solucionar, para así evitar problemas en la construcción final para la publicación.

---

¿Qué es la integración continua?
?
Es una práctica de desarrollo de SW que garantiza que todos los devs integren su código a una rama principal de un repositorio central (código base):
- Al menos una vez al día
- Con una mayor frecuencia a lo largo del ciclo de desarrollo.
<!--SR:!2025-06-25,1,230-->

Se realizan ==1;;pruebas automáticas== ante cada ==1;;integración==, con la finalidad de ==1;;identificar los problemas de integración== más rápidamente, en instancias cuando todavía son más fáciles de solucionar, para así evitar problemas en la ==1;;construcción final (publicación)==.
<!--SR:!2025-06-25,1,230-->

La integración continua se refiere en su mayoría a la fase de ==1;;creación o integración== del proceso de ==1;;publicación de SW==.
<!--SR:!2025-06-25,1,230-->

La integración continua conlleva un componente de ==1;;automatización (e.g., CI o servicio de versiones)== y ==1;;cultural (e.g., aprender a integrar con frecuencia)==.
<!--SR:!2025-06-25,1,230-->

La integración continua es una práctica requerida para poder realizar ==1;;entregas continuas (Continuous Delivery)==.
<!--SR:!2025-06-25,1,230-->

---

### Entrega Continua (CD)

- Retoma el proceso donde finaliza la integración continua y automatiza la entrega de aplicaciones a los entornos de infraestructura seleccionados (1).
- La CD se centra en entregar cualquier cambio validado de la base de código (actualizaciones, correcciones de errores e incluso nuevas características) a los usuarios de la forma más rápida y segura posible.
- Garantiza la automatización del envío de los cambios del código a los diferentes entornos, como desarrollo, pruebas y producción.

> [!IMPORTANT]
>
> 1. Con "automatiza la entrega de aplicaciones a los entornos de infraestructura seleccionados", quiere decir que prepara el SW y lo deja listo para ser desplegado a producción, rápidamente y en cualquier momento, empleando el concepto de Pipelines. Observación: **La automatización de la _publicación al entorno productivo_ es responsabilidad del despliegue continuo**.

---

La entrega continua retoma el proceso donde finaliza la ==1;;integración continua== y ==1;;automatiza== la ==1;;entrega de aplicaciones== a los ==1;;entornos de infraestructura== seleccionados.
<!--SR:!2025-06-25,1,230-->

La entrega continua, posterior a la integración continua, conlleva los pasos requeridos para garantizar que ==1;;el producto sea _liberable_ a producción== en cualquier momento deseado.
<!--SR:!2025-06-25,1,230-->

La entrega continua simplemente se asegura que ==1;;el producto sea _liberable_ a producción== al momento en que ==1;;el negocio== así lo decida.
<!--SR:!2025-06-25,1,230-->

La entrega continua es una precondición del ==1;;despliegue continuo==.
<!--SR:!2025-06-25,1,230-->

La integración continua es una ==1;;condición necesaria y no suficiente== de la entrega continua. ==1;;"necesaria", ya es precondición de la entrega continua y "no suficiente", ya que la entrega continua se logra recién con otros puntos adicionales (Pipelines)==.
<!--SR:!2025-06-25,1,230-->

V o F. La entrega continua, con "automatiza la entrega de aplicaciones a los entornos de infraestructura seleccionados", quiere decir que prepara el SW y lo deja listo para ser desplegado a producción, rápidamente y en cualquier momento, empleando el concepto de Pipelines.::V, la automatización de la _publicación al entorno productivo_ es responsabilidad del **despliegue continuo**.
<!--SR:!2025-06-25,1,230-->

La entrega continua se centra en entregar cualquier ==1;;cambio validado== de la ==1;;base de código (actualizaciones, correcciones de errores e incluso nuevas características)== a los usuarios de la forma más rápida y segura posible.
<!--SR:!2025-06-25,1,230-->

Garantiza la ==1;;automatización== del envío de los ==1;;cambios del código== a los diferentes entornos, como desarrollo, pruebas y producción.
<!--SR:!2025-06-25,1,230-->

---

### Despliegue Continuo (CD)

Los cambios de código que se realizan en las aplicaciones se publican automáticamente en el entorno de producción. Esta automatización se basa en una serie de pruebas predefinidas. Una vez que las nuevas actualizaciones pasan esas pruebas, el sistema envía las actualizaciones directamente a los usuarios del SW.

---

¿En qué consiste el despliegue continuo?
?
Consiste en que los cambios de código que se realizan en las aplicaciones se publican automáticamente en el entorno de producción.
<!--SR:!2025-06-25,1,230-->

La automatización del despliegue continuo se basa en una serie de ==1;;pruebas predefinidas== sobre las ==1;;actualizaciones== las cuáles, al pasar dichas pruebas, el sistema envía las actualizaciones directamente a los usuarios del SW.
<!--SR:!2025-06-25,1,230-->

En el despliegue continuo, el release a producción es al momento en que ==1;;pasan todas las pruebas automatizadas== en el pipeline de despliegue.
<!--SR:!2025-06-25,1,230-->

Cada commit integrado a la rama principal como parte de la integración continua, será automáticamente ==1;;desplegada a producción==, siempre y cuando todas las validaciones en ==1;;el pipeline de despliegue== hayan pasado.
<!--SR:!2025-06-25,1,230-->

---

## Deployment Strategies

- Un deployment strategy es un mecanismo de cambiar o actualizar una aplicación de SW.
- El objetivo es realizar el cambio sin generar un downtime, de forma tal que los usuarios finales no noten el cambio de la aplicación.

---

(Control U5) ¿Qué tipos de Release conoce?
?
- Basic Deployment: Todos los nodos de la aplicación son actualizados en el mismo momento con la nueva versión.
- Blue Green Deployment:
	- Disponemos de dos ambientes lo más similar posible, uno "green" y el otro "blue".
	- El despliegue se realiza sobre uno de los ambientes, mientras el otro contiene la versión anterior.
	- Un balanceador selecciona a qué grupo de servers utilizar como productivo.
- Rolling Deployment: Los nodos de un ambiente son actualizados 1 a 1 (o en lotes) con la nueva versión del SW.
- Canary Deployment:
	- Conceptualmente consiste en desplegar el cambio en un set controlado de nodos, e ir chequeando el comportamiento.
	- Es actualmente una de las formas más comunes de hacer deploy.
<!--SR:!2025-06-25,1,230-->

---

### Basic Deployment

![[09.4-basic-deployment.png]]

- Concepto:
	- Todos los nodos de la aplicación son actualizados en el mismo momento con la nueva versión.
- Ventajas:
	- Muy simple de utilizar, no hay mecanismos específicos que debamos realizar para este deploy.
- Desventajas:
	- Riesgo alto de downtime.

> [!NOTE]
>
> "Saco uno, pongo otro".

---

¿En qué consiste el Basic Deployment?::Todos los nodos de la aplicación son actualizados en el mismo momento con la nueva versión.
<!--SR:!2025-06-25,1,230-->

¿Cuáles son las ventajas y desventajas del Basic Deployment?
?
- Ventajas: Muy simple de utilizar, no hay mecanismos específicos que debamos realizar para este deploy.
- Desventajas: Riesgo alto de downtime.
<!--SR:!2025-06-25,1,230-->

V o F. Una frase representativa del Basic Deployment es "saco uno, pongo otro".::V
<!--SR:!2025-06-25,1,230-->

---

### Blue / Green Deployment

![[09.5-blue-green-deployment.png]]

- Concepto:
	- Disponemos de dos ambientes lo más similar posible, uno "green" y el otro "blue".
	- El despliegue se realiza sobre uno de los ambientes, mientras el otro contiene la versión anterior.
	- Un balanceador selecciona a qué grupo de servers utilizar como productivo.
- Ventajas:
	- Simple de implementar.
- Desventajas:
	- En organizaciones grandes, se torna una solución costosa.

> [!NOTE]
>
> - La salida a producción ya no es más "todo en conjunto": progresivo.
> - Incide la "dockerización".
> - El _Load Balancer_ delega "lo nuevo a lo nuevo" y "lo viejo a lo viejo".
> - e.g., "probamos cómo funciona dirigido a un cierto público".
> - Es considerado más "por paquete" a diferencia del [[#Rolling Deployment|Rolling Deployment]].

---

¿En qué consiste el Blue Green Deployment?
?
- Disponemos de dos ambientes lo más similar posible, uno "green" y el otro "blue".
- El despliegue se realiza sobre uno de los ambientes, mientras el otro contiene la versión anterior.
- Un balanceador selecciona a qué grupo de servers utilizar como productivo.
<!--SR:!2025-06-25,1,230-->

¿Cuáles son las ventajas y desventajas del Blue Green Deployment?
?
- Ventajas: Simple de implementar.
- Desventajas: En organizaciones grandes, se torna una solución costosa.
<!--SR:!2025-06-25,1,230-->

V o F. La salida a producción en Blue Green Deployment es todo en conjunto.::F, es progresivo.
<!--SR:!2025-06-25,1,230-->

V o F. El Load Balancer delega "lo viejo a lo nuevo" y "lo nuevo a lo viejo".::F, delega "lo nuevo a lo nuevo" y "lo viejo a lo viejo".
<!--SR:!2025-06-25,1,230-->

V o F. A diferencia del Rolling Deployment, el Blue Green Deployment es considerado más "por paquete".::V
<!--SR:!2025-06-25,1,230-->

V o F. El Blue Green Deployment permite probar cómo funciona la nueva funcionalidad, dirigido a un público en específico.::V
<!--SR:!2025-06-25,1,230-->

---

### Rolling Deployment

![[09.6-rolling-deployment.png]]

- Concepto:
	- Los nodos de un ambiente son actualizados 1 a 1 (o en lotes) con la nueva versión del SW.
- Ventajas:
	- Rollout gradual con un incremento de tráfico controlado.
	- Simple de hacer rollback.
- Desventajas:
	- App / BD necesitan mantener consistencia para trabajar con versiones distintas (+1 y -1 en cada pod).

> [!NOTE]
>
> - Actualización "por nodo".
> - Permite:
> 	- Probar el nodo en un entorno productivo: puede que no lo haya probado antes.
> 	- Ir midiendo cada Roll-Out y ver su comportamiento.
> 	- Confinar el Roll-Out a un cierto público: por población, por localidad, etc.

---

¿En qué consiste el Rolling Deployment?::Los nodos de un ambiente son actualizados 1 a 1 (o en lotes) con la nueva versión del SW.
<!--SR:!2025-06-25,1,230-->

¿Cuáles son las ventajas y desventajas del Rolling Deployment?
?
- Ventajas:
	- Rollout gradual con un incremento de tráfico controlado.
	- Simple de hacer rollback.
- Desventajas:
	- App / BD necesitan mantener consistencia para trabajar con versiones distintas (+1 y -1 en cada pod).
<!--SR:!2025-06-25,1,230-->

V o F. La actualización en el Rolling Deployment son "por paquetes".::F, son actualizaciones "por nodo".
<!--SR:!2025-06-25,1,230-->

V o F. El Rolling Deployment permite probar el nodo en un entorno productivo, incluso aunque no lo hayamos probado antes en otro ambiente.::V
<!--SR:!2025-06-25,1,230-->

V o F. El Rolling Deployment es complejo en medir cada Roll-Out y ver su comportamiento.::F, permite ir midiendo cada Roll-Out y ver su comportamiento.
<!--SR:!2025-06-25,1,230-->

V o F. El Rolling Deployment permite confinar el Roll-Out a un cierto público: por población, por localidad, etc.::V
<!--SR:!2025-06-25,1,230-->

---

### Canary Deployment

![[09.9-canary-deployment.png]]

- Concepto:
	- Conceptualmente consiste en desplegar el cambio en un set controlado de nodos, e ir chequeando el comportamiento.
	- Es actualmente una de las formas más comunes de hacer deploy.
- Ventajas:
	- El despliegue es en pequeñas fases (por ejemplo 2% de los nodos, 10%, 50%, 75%, 100%).
	- En el caso de fallas, se quitan los nodos que fueron incorporándose.
	- Solo existe 1 ambiente de producción.
- Desventajas:
	- Es complejo de testear producción.
	- Herramientas de monitoreo complejas para entender que está desplegado.

Criterios de partición:

- Por nodos regionales: continente, zona geográfica.
- Por clientes "Top 10", por otra categorización, etc.

> [!NOTE]
>
> - Es posible compararlo contra [[#Rolling Deployment|Rolling Deployment]]: posee una menor granularidad que el mismo.
> - Ante un error: Redirección de peticiones a la versión funcional anterior.

---

¿En qué consiste el Canary Deployment?
?
- Conceptualmente consiste en desplegar el cambio en un set controlado de nodos, e ir chequeando el comportamiento.
- Es actualmente una de las formas más comunes de hacer deploy.
<!--SR:!2025-06-25,1,230-->

Nombrar algunos criterios posibles de partición aplicables en el Canary Deployment.
?
- Por nodos regionales: continente, zona geográfica.
- Por clientes "Top 10", por otra categorización, etc.
<!--SR:!2025-06-25,1,230-->

¿Cuáles son las ventajas y desventajas del Canary Deployment?
?
- Ventajas:
	- El despliegue es en pequeñas fases (por ejemplo 2% de los nodos, 10%, 50%, 75%, 100%).
	- En el caso de fallas, se quitan los nodos que fueron incorporándose.
	- Solo existe 1 ambiente de producción.
- Desventajas:
	- Es complejo de testear producción.
	- Herramientas de monitoreo complejas para entender que está desplegado.
<!--SR:!2025-06-25,1,230-->

V o F. El Canary Deployment posee varios entornos de producción.::F, solamente existe 1 ambiente de producción.
<!--SR:!2025-06-25,1,230-->

V o F. Una diferencia que posee Canary Deployment respecto al Blue Green Deployment es que el primero posee un único entorno productivo, mientras que el último su estrategia consiste en varios ambientes productivos.::V
<!--SR:!2025-06-25,1,230-->

V o F. El Canary Deployment posee una menor granularidad que el Rolling Deployment.::F, el Rolling Deployment posee una menor granularidad que el Canary Deployment.
<!--SR:!2025-06-25,1,230-->

V o F. Ante un error, el Canary Deployment permite redireccionar peticiones a la versión funcional anterior.::V, se quitan los nodos que fueron incorporándose.
<!--SR:!2025-06-25,1,230-->

---

# Release Management Metrics

> Métricas asociadas a los flujos de building y de releasing del SW.

> [!NOTE]
>
> - Cada organización posee sus métricas.
> - Tiene que aportarle valor a la organización.

---

V o F. Cada organización posee sus métricas y tiene que aportarle valor a la organización.::V
<!--SR:!2025-06-25,1,230-->

---

## Deployment Frequency

(DF)

- Cada cuanto tiempo una organización despliega SW a Producción satisfactoriamente.
- Medida: # de Deployments por día.
- Objetivo: Indica cada cuanto tiempo agregamos valor a los clientes.

> [!NOTE]
>
> Podríamos tener mucha integración continua, pero poca salida a producción.

---

Explicar la métrica Deployment Frequency, contar qué medida emplea y su objetivo.
?
- Mide cada cuánto tiempo una organización despliega SW a Producción satisfactoriamente.
- Medida: # de Deployments por día.
- Objetivo: Indica cada cuanto tiempo agregamos valor a los clientes.
<!--SR:!2025-06-25,1,230-->

---

## Lead Time for Changes

(LTfC)

- El tiempo que le lleva a un Commit llegar a Producción.
- Medida: Lead Time en días.
- Objetivo: Potencialmente puede indicar la productividad del proceso de desarrollo.

---

Explicar la métrica Lead Time for Changes, contar qué medida emplea y su objetivo.
- Mide el tiempo que le lleva a un Commit llegar a Producción.
- Medida: Lead Time en días.
- Objetivo: Potencialmente puede indicar la productividad del proceso de desarrollo.

---

## Change Failure Rate

(CFR)

- El porcentaje de despliegues que llevaron a una degradación del servicio.
- Medida: Número de Incidentes / Número de despliegues.
- Objetivo: Incrementar la satisfacción de los clientes al reducir el número de downtimes.

> [!NOTE]
>
> Otra medida posible:
> - Tasa de Rollbacks: Si bien es válida, quizás no es muy útil.

---

Explicar la métrica Change Failure Rate, contar qué medida emplea y su objetivo.
- El porcentaje de despliegues que llevaron a una degradación del servicio.
- Medida: Número de Incidentes / Número de despliegues.
- Objetivo: Incrementar la satisfacción de los clientes al reducir el número de downtimes.

---

## Mean Time To Recovery (MTTR)

(MTTR)

- El tiempo que le demora a la organización recuperarse luego de un incidente.
- Medida: Tiempo medido en horas.
- Objetivo: Incrementar la satisfacción de los clientes al reducir el número de downtimes.

> [!IMPORTANT]
>
> Conceptualmente:
> - El MTTR es una métrica que indica **el tiempo promedio que tarda un sistema, servicio o equipo en volver a estar operativo después de un incidente o fallo**, por lo que cualquiera de las métricas nombradas o electas deben tener dicha característica.

> [!NOTE]
>
> No las pude confirmar con los profes, pero se me ocurren:
> - Rollback: Tiempo incurrido de versión a versión hasta su recuperación.
> - Roll Forward: Tiempo incurrido del merge del fix hasta su recuperación.
> - Runtime Errors: cuánto tiempo se tarda en reponer el servicio (este es un caso en donde no falla el build, sino que el error latente se manifiesta en tiempo de ejecución).

---

Explicar la métrica Mean Time To Recovery, contar qué medida emplea y su objetivo.
- El tiempo que le demora a la organización recuperarse luego de un incidente.
- Medida: Tiempo medido en horas.
- Objetivo: Incrementar la satisfacción de los clientes al reducir el número de downtimes.

El MTTR es una métrica que indica el ==1;;tiempo promedio== que tarda un sistema, servicio o equipo en ==1;;volver a estar operativo== después de un ==1;;incidente o fallo==, por lo que cualquiera de las métricas nombradas o electas deben tener dicha característica.
<!--SR:!2025-06-25,1,230-->

---
