---
tags:
- flashcards/swe/teoria/2P
---

# Overview

- Contexto Organizacional de SCM.
	- ¿En qué contexto estamos?
- Plan de SCM.
	- ¿Cuál es el plan? ¿Cómo lo ordenamos?
- Vigilancia del Proceso SCM.
	- ¿Quién lo controla? ¿Quién asegura que se cumpla el plan?

> [!NOTE]
>
> SWEBOK:
>
> Desde la perspectiva del SWE: Facilita las actividades de desarrollo e implementación de cambios.

> [!NOTE]
>
> Una implementación exitosa del SCM:
> - Requiere una planificación y gestión cuidadosa.
> - Implican un fuerte entendimiento sobre el contexto organizacional, con sus restricciones particulares.
> - Todo con la finalidad de diseñar e implementar el proceso del SCM.

---

Nombrar las actividades de la administración del proceso de SCM.
?
- Contexto Organizacional de SCM.
- Plan de SCM.
- Vigilancia del Proceso SCM.
<!--SR:!2025-06-22,1,230-->

¿Qué implica una implementación exitosa del SCM?
- Requiere una planificación y gestión cuidadosa.
- Implican un fuerte entendimiento sobre el contexto organizacional, con sus restricciones particulares.
- Todo con la finalidad de diseñar e implementar el proceso del SCM.

---

# Administración del proceso de gestión de configuración del SW

> Definiendo el marco de trabajo de los developers.

La Administración del Proceso de Gestión de Configuración del SW:

- Define herramientas, reportes y procesos que serán utilizados, en la organización o el proyecto, para la gestión de configuración.
- Se encarga de definir:
	- Cómo serán incorporados los ICs.
	- Cuándo se realizarán las líneas base.
	- Cómo será la estrategia de desarrollo en paralelo.
	- Cómo serán las nomenclaturas de las versiones.
	- Entre otras definiciones.
- Generalmente se realiza mediante la definición de un plan de CM.

---

¿En qué consiste la administración del proceso de SCM?
?
La Administración del Proceso de Gestión de Configuración del SW define herramientas, reportes y procesos que serán utilizados, en la organización o el proyecto, para la gestión de configuración.
<!--SR:!2025-06-22,1,230-->

¿Qué define la administración del proceso de SCM?
?
Se encarga de definir:
- Cómo serán incorporados los ICs.
- Cuándo se realizarán las líneas base.
- Cómo será la estrategia de desarrollo en paralelo.
- Cómo serán las nomenclaturas de las versiones.
- Entre otras definiciones.
<!--SR:!2025-06-22,1,230-->

¿Cómo se realiza la administración del proceso de SCM?
?
Generalmente se realiza mediante la definición de un plan de CM.
<!--SR:!2025-06-22,1,230-->

---

# Planning for SW Configuration Management: Plan de gestión de configuración (CM Plan)

Un plan de SCM define principalmente: (incluye)

- Lista items de configuración (IC) y en qué momento ingresan al sistema de CM.
	- En qué etapas aparecen y desaparece los ICs.
- Define estándares de nombres, jerarquías de directorios, estándares de versionamiento.
- Define las estrategias de Branching.
- Define los procedimientos para crear "builds" y "releases".
- Define reglas de uso de la herramienta de CM y el rol del administrador de la configuración.
- Define el contenido de los reportes de auditoría y los momentos en que estas se ejecutan.

Puede ser definido por:

- Proyecto.
- A nivel organizacional y luego realizar una adaptación al proyecto.

> [!NOTE]
>
> Un plan de SCM es un item de configuración más.

---

¿Qué elementos define principalmente un plan de SCM?
?
Un plan de SCM define principalmente: (incluye)
- Lista items de configuración (IC) y en qué momento ingresan al sistema de CM.
	- En qué etapas aparecen y desaparece los ICs.
- Estándares de nombres, jerarquías de directorios, estándares de versionamiento.
- Las estrategias de Branching.
- Los procedimientos para crear "builds" y "releases".
- Reglas de uso de la herramienta de CM y el rol del administrador de la configuración.
- El contenido de los reportes de auditoría y los momentos en que estas se ejecutan.
<!--SR:!2025-06-22,1,230-->

V o F. El plan de SCM puede ser definido por proyecto, o bien a nivel organizacional y luego realizar una adaptación al proyecto.::V
<!--SR:!2025-06-22,1,230-->

V o F. Un plan de SCM es un item de configuración más.::V
<!--SR:!2025-06-22,1,230-->

---

# Concepto Clave: Branching Strategies

- Es la estrategia que adoptan los equipos de desarrollo de SW al escribir, mergear e implementar código cuando usan un sistema de control de versiones (Git / SVN / TFS).
- Es en esencia un conjunto de reglas que los desarrolladores pueden seguir para estipular cómo interactúan con una base de código compartida.
- Una estrategia de branching tiene como objetivos:
	- Mejorar la productividad al garantizar una coordinación adecuada entre los desarrolladores.
	- Facilitar el desarrollo paralelo.
	- Ayudar a organizar una serie de lanzamientos planificados y estructurados.
	- Trazar un camino claro al realizar cambios en el SW hasta producción.
	- Mantener un código libre de errores donde los desarrolladores puedan corregir problemas rápidamente y hacer que estos cambios vuelvan a la producción sin interrumpir el flujo de trabajo de desarrollo.

---

Una Branching Strategy es ==1;;la estrategia== que adoptan los equipos de desarrollo de SW al ==1;;escribir==, ==1;;mergear== e ==1;;implementar== código cuando usan un ==1;;sistema de control de versiones (Git / SVN / TFS)==.
<!--SR:!2025-06-22,1,230-->

Una Branching Strategy es en esencia un ==1;;conjunto de reglas== que los desarrolladores pueden seguir para estipular cómo interactúan con una ==1;;base de código compartida==.
<!--SR:!2025-06-22,1,230-->

¿Cuáles son los objetivos de una estrategia de branching?
?
- Mejorar la productividad al garantizar una coordinación adecuada entre los desarrolladores.
- Facilitar el desarrollo paralelo.
- Ayudar a organizar una serie de lanzamientos planificados y estructurados.
- Trazar un camino claro al realizar cambios en el SW hasta producción.
- Mantener un código libre de errores donde los desarrolladores puedan corregir problemas rápidamente y hacer que estos cambios vuelvan a la producción sin interrumpir el flujo de trabajo de desarrollo.
<!--SR:!2025-06-22,1,230-->

---

## Gitflow

![[04.1-gitflow.png]]

- Consiste en 2 ramas principales que existen a lo largo de todo el ciclo de vida del desarrollo.
- Tiene una serie de branches de soporte.

---

¿En qué consiste la Branching Strategy Gitflow?
?
Consiste en 2 ramas principales que existen a lo largo de todo el ciclo de vida del desarrollo, a su vez tiene una serie de branches de soporte.
<!--SR:!2025-06-22,1,230-->

Nombrar los 5 tipos de branches de Gitflow.
?
- Principales:
	- Develop:
		- Punto de integración de feature branches previo a un release oficial.
	- Main / Master:
		- Histórico oficial de las historias de releases.
		- Solamente reside el código finalizado y productivo.
		- Solamente incide cuando subimos código a producción
- Soporte:
	- Feature:
		- Desarrollo de nueva funcionalidad.
		- Garantizar que los nuevos desarrollos no perturben el código base principal.
	- Release:
		- Buffers para preparar el código a ser integrado en el entorno productivo.
		- Realización de retoques finales: Bug fixes / documentación.
	- Hotfix:
		- Permite saltearse el proceso de desarrollo ordinario para poder rápidamente realizar modificaciones correctivas de los bugs en producción.
<!--SR:!2025-06-22,1,230-->

---

### Ramas principales

- Develop:
	- Punto de integración de feature branches previo a un release oficial.
- Main / Master:
	- Histórico oficial de las historias de releases.
	- Solamente reside el código finalizado y productivo.
	- Solamente incide cuando subimos código a producción

### Ramas soporte

- Feature:
	- Desarrollo de nueva funcionalidad.
	- Garantizar que los nuevos desarrollos no perturben el código base principal.
- Release:
	- Buffers para preparar el código a ser integrado en el entorno productivo.
	- Realización de retoques finales: Bug fixes / documentación.
- Hotfix:
	- Permite saltearse el proceso de desarrollo ordinario para poder rápidamente realizar modificaciones correctivas de los bugs en producción.

## Github Flow

![[04.2-github-flow.png]]

- Creado por GitHub, busca ser una alternativa simplificada del desarrollo.
- Existe una rama Master de donde parten las ramas de desarrollo.
- Cada nueva feature se trabaja en una rama separada que es integrada nuevamente en master cuando el trabajo finaliza.

> [!NOTE]
>
> Es una versión simplificada de [[#Gitflow|Gitflow]].

---

¿En qué consiste la Branching Strategy Github Flow?
- Creado por GitHub, busca ser una alternativa simplificada del desarrollo.
- Existe una rama Master de donde parten las ramas de desarrollo.
- Cada nueva feature se trabaja en una rama separada que es integrada nuevamente en master cuando el trabajo finaliza.

V o F. Github Flow es una versión simplificada de Gitflow.::V
<!--SR:!2025-06-22,1,230-->

---

## Trunk Based Flow

![[04.3-trunk-based-flow-1.png]]

![[04.3-trunk-based-flow-2.png]]

- Los desarrolladores colaboran en el código en una sola rama llamada "troncal".
- Resiste cualquier presión para crear otras ramas de desarrollo de larga duración mediante el empleo de técnicas documentadas.
- Por lo tanto, evitan fusionar el infierno, no rompen la construcción y viven felices para siempre.

> [!NOTE]
>
> - Se centra sobre la rama principal como la fuente de fixes y releases.
> - La rama principal siempre se asume como estable, sin conflictos y listo para ser desplegada (release).
> - Los mergeos de las features son contra la rama principal.
> - Permite un proceso de release más rápido y consistente.

---

¿En qué consiste la Branching Strategy Trunk Based Flow?
?
- Los desarrolladores colaboran en el código en una sola rama llamada "troncal".
- Resiste cualquier presión para crear otras ramas de desarrollo de larga duración mediante el empleo de técnicas documentadas.
- Por lo tanto, evitan fusionar el infierno, no rompen la construcción y viven felices para siempre.
<!--SR:!2025-06-22,1,230-->

V o F. Trunk Based Flow se centra sobre la rama principal como la fuente de fixes y releases.::V
<!--SR:!2025-06-22,1,230-->

V o F. En Trunk Based Flow la rama principal siempre se asume como estable, sin conflictos y listo para ser desplegada (release).::V
<!--SR:!2025-06-22,1,230-->

V o F. En Trunk Based Flow los mergeos de las features son contra la rama principal.::V
<!--SR:!2025-06-22,1,230-->

V o F. Trunk Based Flow permite un proceso de release más rápido y consistente.::V
<!--SR:!2025-06-22,1,230-->

---

# Ejemplo: Proceso de SCM definido

![[04.4-ejemplo-proceso-de-scm.png]]

> [!NOTE]
>
> - Requerimientos: Jira.
> - Definición de los roles que pueden aprobar los cambios propuestos.
> - Github como elemento de control, NPM como gestor de dependencias/paquetes.
> - Equipo eventualmente codifica.
> - Emplea las reglas de Gitflow.
> - Luego de subir el código al repositorio, actualizar los estados de las tarjetas trabajadas para el pasaje a producción.

> [!NOTE]
>
> Este es un ejemplo "set mínimo": Pueden haber más herramientas en juego en un proceso SCM.
