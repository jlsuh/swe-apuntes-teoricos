---
tags:
- flashcards/swe/teoria/2P
---

# Overview

- Herramientas para soportar los diferentes aspectos y niveles de la gestión de configuración.

> [!NOTE]
>
> SWEBOK:
>
> - Asisten en varios niveles al SCM y depende de quién sea el que emplea la herramienta.
> - En general, las herramientas son:
> 	- Configuration Management System (CMS): Provee la tecnología y lógica que facilitan las actividades del SCM.
> 	- Control de versiones: Almacena el código fuente, archivos de configuración y artefactos relacionados.
> 	- Automatización de builds (pipeline): Establecido para lograr la entrega continua.
> 	- Repositorio: Almacena binarios que son creados durante el proceso de construcción para extraer los últimos artefactos de construcción y re-desplegarlos a demanda (empleado en el proceso de verificación de releases).
> 	- Configuration Management Database (CMDB): 
> 	- Herramientas de control de cambios (o almacenamientos persistentes similares).
> 	- Herramientas de release/despliegue.

---

Nombrar las actividades del SCM Management Tools.
?
- Herramientas para soportar los diferentes aspectos y niveles de la gestión de configuración.
<!--SR:!2025-06-25,1,230-->

---

# SCM Tools

> Una vista Landscape.

## SCM Tooling

- Las herramientas dan soporte a la gestión de configuración en diferentes niveles. Cada organización define qué herramientas utiliza en esta gestión.
- Dentro de las herramientas, podemos mencionar:
	- Herramientas que gestionan las versiones de los código fuente, archivos de configuración y artefactos relacionados.
	- Herramientas que ayudan en la automatización del Build y establecen mecanismos (Vía Pipelines) para permitir el delivery continuo.
	- Repositorios que almacenan las historias de los builds.
	- Herramientas que gestionan los cambios funcionales y el control de cambios.
	- Herramientas que dan soporte al despliegue de aplicaciones.
	- Herramientas colaborativas para comunicar.

![[10.1-scm-tooling.png]]

---

Las herramientas dan soporte a la ==1;;gestión de configuración== en diferentes niveles de la organización y las mismas definen qué ==1;;herramientas emplear== en dicha gestión.
<!--SR:!2025-06-25,1,230-->

Nombrar algunos tipos de herramientas.
?
- Gestión de versiones de los código fuente, archivos de configuración y artefactos relacionados.
- Automatización del Build y establecen mecanismos (Pipelines) para permitir el delivery continuo.
- Repositorios que almacenan las historias de los builds.
- Gestión de los cambios funcionales y el control de cambios.
- Soporte al despliegue de aplicaciones.
- Colaborativas para comunicar.
<!--SR:!2025-06-25,1,230-->

---

## Tooling de automatización de entornos

![[10.2-tooling-automatizacion-de-entornos.png]]

- Metal / Físico (Bare Metal): (1)
	- HW:
		- Dependiente: Drivers de placas, video, controladores, etc.
	- Aislamiento:
		- Todos los servicios comparten el SO y kernel pudiendo afectar a otros.
	- Cambios:
		- No hay snapshots, al romperse hay que reinstalar.
	- Performance:
		- No hay overhead de performance.
	- Aprovisionamiento:
		- Requiere scripts con herramientas para gestión de paquetes, dependencias, acceso al servidor físico.
- Máquina Virtual (VM): (2)
	- HW:
		- Cuasi independiente: HW virtualizado, solo respeta arquitectura (x86, ARM, etc.).
	- Aislamiento:
		- Todos los servicios comparten el SO y el kernel pudiendo afectar a otros.
	- Cambios:
		- Más fáciles que metal, existen snapshots, y por ende se puede versionar una VM.
	- Performance:
		- Hay una gran pérdida de performance ya que cada máquina tiene varios SOs.
	- Aprovisionamiento:
		- Al tener las imágenes de base y snapshots de una máquina virtual, el aprovisionamiento es más rápido y simple.
		- Un developer podría tener su entorno similar a producción.
- Contenedores (Containerization): (3)
	- HW:
		- Independiente del HW: Solo respeta arquitectura. Memoria/CPU flexible.
	- Aislamiento:
		- Filosofía de 1 container por servicio, aislando los servicios entre sí.
	- Cambios:
		- Tienen archivos de configuración, son versionables, hay repositorios de containers.
	- Performance:
		- Mucho más livianos que VM, pierde muy poca performance que metal.
	- Aprovisionamiento:
		- Utiliza capas de aprovisionamiento, soporta snapshots, el bootup es en segundos o minutos.
		- Fácil de mover cambios desde y hacia producción.

> [!NOTE]
>
> 1. Costos elevados.
> 2. In-House o tercerizado.
> 3. Costos reducidos (estamos aquí).

---

Contar las diferencias de las Tooling de automatización de entornos respecto del HW.
?
- Metal / Físico: Dependiente: Drivers de placas, video, controladores, etc.
- VM: Cuasi independiente: HW virtualizado, solo respeta arquitectura (x86, ARM, etc.).
- Contenedores: Independiente del HW: Solo respeta arquitectura. Memoria/CPU flexible.
<!--SR:!2025-06-25,1,230-->

Contar las diferencias de las Tooling de automatización de entornos respecto del Aislamiento.
?
- Metal / Físico: Todos los servicios comparten el SO y kernel pudiendo afectar a otros.
- VM: Todos los servicios comparten el SO y el kernel pudiendo afectar a otros.
- Contenedores: Filosofía de 1 container por servicio, aislando los servicios entre sí.
<!--SR:!2025-06-25,1,230-->

Contar las diferencias de las Tooling de automatización de entornos respecto de los Cambios.
?
- Metal / Físico: No hay snapshots, al romperse hay que reinstalar.
- VM: Más fáciles que metal, existen snapshots, y por ende se puede versionar una VM.
- Contenedores: Tienen archivos de configuración, son versionables, hay repositorios de containers.
<!--SR:!2025-06-25,1,230-->

Contar las diferencias de las Tooling de automatización de entornos respecto de la Performance.
?
- Metal / Físico: No hay overhead de performance.
- VM: Hay una gran pérdida de performance ya que cada máquina tiene varios SOs.
- Contenedores: Mucho más livianos que VM, pierde muy poca performance que metal.
<!--SR:!2025-06-25,1,230-->

Contar las diferencias de las Tooling de automatización de entornos respecto del Aprovisionamiento.
?
- Metal / Físico: Requiere scripts con herramientas para gestión de paquetes, dependencias, acceso al servidor físico.
- VM:
	- Al tener las imágenes de base y snapshots de una máquina virtual, el aprovisionamiento es más rápido y simple.
	- Un developer podría tener su entorno similar a producción.
- Contenedores:
	- Utiliza capas de aprovisionamiento, soporta snapshots, el bootup es en segundos o minutos.
	- Fácil de mover cambios desde y hacia producción.
<!--SR:!2025-06-25,1,230-->

---

## DevOps

> La fusión entre desarrollo y operaciones.

### Problema a resolver

![[10.3-devops-meme.png]]

- En organizaciones de las llamadas tradicionales:
	- El que desarrolla no escribe los requerimientos.
	- El que desarrolla no hace testing funcional.
	- El que desarrolla no pasa a producción.
	- El que desarrolla no está de guardia.
- Durante décadas los operadores de IT y sistemas vivieron en plena queja con desarrolladores que no consideraban:
	1. Que los entornos pueden tener diferencias.
	2. Que la puesta en producción no es gratuita.
	3. Cuestiones como la escalabilidad, performance, disponibilidad, tolerancia a fallos, entre otros.
	4. Hacer SW no es "fire & forget" y esperaban que operaciones maneje automáticamente cualquier problema, sin conocimiento del dominio.

**GENERANDO FALTA DE COMUNICACIÓN Y COLABORACIÓN**.

---

¿Qué busca resolver DevOps?::Busca resolver la falta de comunicación (romper la "pared entre desarrollo y operaciones") y colaboración entre desarrollo y operaciones.
<!--SR:!2025-06-25,1,230-->

---

![[10.4-devops-wall-of-confusion.png]]

Cuando el cliente (usuario o PO) requiere de un nuevo cambio al producto SW:

- El equipo de desarrollo comienza "Deployando" una versión de SW "por encima de la pared" a Operaciones.
- Operaciones toma los artefactos de Deploy y comienza a prepararse para su implementación.
- Operaciones piratea manualmente los scripts de implementación proporcionados por los desarrolladores o crea sus propios scripts.

> [!TIP]
>
> - "¿Nuevas funcionalidades? => Embrace Change".
> - "¿Nuevos riesgos? => Mantener la estabilidad".

### Definición

- Es un conjunto de prácticas destinadas a reducir el tiempo entre el cambio en un sistema y su pasaje a producción, garantizando la calidad y minimizando el esfuerzo.
- Es también un cambio cultural, ya que en un modelo de DevOps, los equipos de desarrollo y operaciones ya no están "aislados". A veces, los dos equipos se fusionan en uno solo, donde los ingenieros trabajan en todo el ciclo de vida de la aplicación, desde el desarrollo y las pruebas hasta la implementación y las operaciones, y desarrollan una variedad de habilidades no limitadas a una única función.
- **NO es una metodología**, es más bien un conjunto de prácticas, herramientas y una filosofía cultural que automatizan e integran los procesos entre los equipos de desarrollo de SW y IT.
- El término se acuñó en una [conferencia de infraestructura en Bélgica](https://legacy.devopsdays.org/events/2009-ghent/) que quería atraer a desarrolladores.

> [!NOTE]
>
> - Nace de la "necesidad de comunicación".
> - Romper la "pared entre desarrollo y operaciones".
> - Code as a service (CaaS).
> - DevOps = Cambio cultural.

---

DevOps es un ==1;;conjunto de prácticas== destinadas a ==1;;reducir el tiempo== entre el ==1;;cambio en un sistema== y su ==1;;pasaje a producción==.
<!--SR:!2025-06-25,1,230-->

DevOps garantiza la ==1;;calidad== y ==1;;minimización del esfuerzo==.
<!--SR:!2025-06-25,1,230-->

DevOps es un ==1;;cambio cultural==
<!--SR:!2025-06-25,1,230-->

V o F. En un modelo de DevOps los equipos de desarrollo y operaciones siguen "aislados".::F
<!--SR:!2025-06-25,1,230-->

V o F. A veces, los 2 equipos se fusionan en uno solo, donde los ingenieros trabajan en todo el ciclo de vida de la aplicación, desde el desarrollo y las pruebas hasta la implementación y las operaciones, y desarrollan una variedad de habilidades no limitadas a una única función.::V
<!--SR:!2025-06-25,1,230-->

V o F. DevOps es una metodología.::F, **NO es una metodología**, es más bien un conjunto de prácticas, herramientas y una filosofía cultural que automatizan e integran los procesos entre los equipos de desarrollo de SW y IT.
<!--SR:!2025-06-25,1,230-->

---

### CALMS

CALMS es la filosofía de trabajo detrás de DevOps, dónde:

- **C**ultura: Ser dueños del cambio para mejorar la colaboración y comunicación.
- **A**utomatización: Eliminar el trabajo manual y repetitivo lleva a procesos repetibles y sistemas confiables, reduciendo el error humano.
- **L**ean: Remover la burocracia para tener ciclos más cortos y menos desperdicio.
- **M**étricas: Medir todo, usar datos para refinar los ciclos.
- **S**haring: Compartir experiencias de éxito y fallas para que otros puedan aprender.

---

¿Qué es CALMS?
?
Es la filosofía de trabajo detrás de DevOps.
<!--SR:!2025-06-25,1,230-->

Explicar las iniciales de CALMS.
?
- **C**ultura: Ser dueños del cambio para mejorar la colaboración y comunicación.
- **A**utomatización: Eliminar el trabajo manual y repetitivo lleva a procesos repetibles y sistemas confiables, reduciendo el error humano.
- **L**ean: Remover la burocracia para tener ciclos más cortos y menos desperdicio.
- **M**étricas: Medir todo, usar datos para refinar los ciclos.
- **S**haring: Compartir experiencias de éxito y fallas para que otros puedan aprender.
<!--SR:!2025-06-25,1,230-->

---

### Ciclo de vida

![[10.5-devops-ciclo-de-vida.png]]

![[10.6-agile-dev-ci-cd.gif]]

### Prácticas de DevOps en cada etapa

- Planificación del Cambio:
	- Conversación y colaboración.
- Coding & Building:
	- Automated Build Pipelines.
	- Infrastructure as Code.
- Testing:
	- Automated Testing.
	- Chaos Testing / Fault Injection.
- Release & Deployment:
	- Continuous Integration.
	- Continuous Delivery.
- Operation & Monitoring:
	- Virtualization & Containers.
	- Monitoring & Alerting tools.

---

Nombrar las etapas del ciclo de vida de DevOps.
?
- -> Planificar el Cambio: Conversación y colaboración.
- Coding & Building: Pipelines automatizados & IaaC.
- Testing: Tests automatizados & Chaos Testing / Fault Injection.
- Release & Deployment: Integración continua & Entrega continua.
- Operación: Virtualization & Containers,
- Monitoreo: Alerting tools.
- Feedback continuo.
- Descubrir. ->
- Todo esto teniendo en cuenta la colaboración y comunicación.
<!--SR:!2025-06-25,1,230-->

---
