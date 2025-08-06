---
tags:
- flashcards/swe/teoria/2P
---

# Clasificación de métricas

![[04.1-clasificacion-metricas.png]]

> [!TIP]
>
> La misma métrica puede ser enfocada desde distintos objetos.

---

V o F. Una misma métrica puede ser enfocada desde distintos objetos.::V
<!--SR:!2025-06-25,1,230-->

---

## Métricas Orientadas al Producto (SW)

Cualquier artefacto o entregable que resulta del proceso de desarrollo de SW.

- Cantidad de líneas de código (LOC).
- Funcionalidad (Puntos por Función / Use Case Points).
- Complejidad Ciclomática (Mc Cabe).
- Cohesión.
- Acoplamiento.
- Calidad de Producto (ISO 25000).
- Cantidad de fallas de un producto.
- Confiabilidad (MTBF, MTTR): #exam-question 
	- MTBF: Mean Time Between Failures.
	- MTTR: Mean Time To Recovery.
- Deuda técnica total del producto.

---

¿Qué es una métrica orientada al producto (SW)?
?
Métrica asociada a cualquier artefacto o entregable que resulta del proceso de desarrollo de SW.
<!--SR:!2025-06-25,1,230-->

¿Cuáles son las métricas orientadas al producto (SW)?
?
- Cantidad de líneas de código (LOC).
- Funcionalidad (Puntos por Función / Use Case Points).
- Complejidad Ciclomática (Mc Cabe).
- Cohesión.
- Acoplamiento.
- Calidad de Producto (ISO 25000).
- Cantidad de fallas de un producto.
- Confiabilidad (MTBF, MTTR): #exam-question
	- MTBF: Mean Time Between Failures.
	- MTTR: Mean Time To Recovery.
- Deuda técnica total del producto.
<!--SR:!2025-06-25,1,230-->

---

## Métricas Orientadas al Proceso

Colección de actividades relacionadas con el desarrollo y mantenimiento de SW.

- Duración promedio de proyectos.
- Cantidad de proyectos segregados por tipo, tamaño, etc.
- Esfuerzo promedio segregado por tipo, duración.
- Defectos introducidos en una fase del ciclo de vida.
- Defectos detectados en una fase del ciclo de vida.
- % de tiempo/esfuerzo/costo dedicado a una fase del ciclo de vida.
- % promedio de desvío en proyectos (En costo o duración).
- Earned Value Analysis:
	- Schedule Variance = EV - PV
	- Schedule Performance Index (SPI) = EV / PV (Valor esperado: >= 1)
	- Cost Variance = EV - AC
	- Cost Performance Index (CPI) = EV / AC (Valor esperado: >= 1)
- Métricas de Kanban: lead time, cycle time & touch time.
- Deuda técnica agregada o resuelta al aplicar algún SWE Approach, e.g., Scrum, Kanban, etc.
- Velocity en Scrum.

---

¿Qué es una métrica orientada al proceso?
?
Métrica asociada a la colección de actividades relacionadas con el desarrollo y mantenimiento de SW.
<!--SR:!2025-06-25,1,230-->

¿Cuáles son las métricas orientadas al proceso?
?
- Duración promedio de proyectos.
- Cantidad de proyectos segregados por tipo, tamaño, etc.
- Esfuerzo promedio segregado por tipo, duración.
- Defectos introducidos en una fase del ciclo de vida.
- Defectos detectados en una fase del ciclo de vida.
- % de tiempo/esfuerzo/costo dedicado a una fase del ciclo de vida.
- % promedio de desvío en proyectos (En costo o duración).
- Earned Value Analysis:
	- Schedule Variance = EV - PV
	- Schedule Performance Index (SPI) = EV / PV (Valor esperado: >= 1)
	- Cost Variance = EV - AC
	- Cost Performance Index (CPI) = EV / AC (Valor esperado: >= 1)
- Métricas de Kanban: lead time, cycle time & touch time.
- Deuda técnica agregada o resuelta al aplicar algún SWE Approach, e.g., Scrum, Kanban, etc.
- Velocity en Scrum.
<!--SR:!2025-06-25,1,230-->

---

### Earned Value Analysis

- Forma estandarizada de medir el progreso de un proyecto en cualquier momento de su ciclo de vida.
- El progreso puede estar en términos del calendario, si está atrasado o adelantado para la cantidad de trabajo siendo realizado.
- Permite también determinar los costos de un proyecto: sobrecosto o por debajo.

---

¿En qué consiste el Earned Value Analysis?
?
- Es una forma estandarizada de medir el progreso de un proyecto en cualquier momento de su ciclo de vida.
<!--SR:!2025-06-25,1,230-->

¿Qué permite determinar el Earned Value Analysis?
?
- Permite determinar en términos del calendario: atrasado o adelantado respecto a la # de trabajo realizado o siendo realizado.
- Permite determinar los costos de un proyecto: sobrecosto o por debajo.
<!--SR:!2025-06-25,1,230-->

---

#### Ejemplo

![[04.2-ev-analysis-ex.png]]

- Suponiendo que el proyecto toma 5 días y supuesto en costar $400 cada día.
- Suponiendo que obtenemos un reporte al final del día 3 y nos informan que solamente el 40% del trabajo fue completado y terminó costando $1000 (el 40% de los 5 días son 2 días).

![[04.3-ev-analysis-ex.png]]

- Esto implica que esperábamos que en el día que nos hicieron el reporte (día 3) esperábamos tener completo el 60% del trabajo con un costo de $1200, no obstante, solamente el 40% del trabajo fue completado costando $1000.

Métricas:

- ACWP: Actual Cost of Work Performed = "**Actual Cost**"
- BCWP: Budgeted Cost of Work Performed = "**Earned Value**"
- BCWS: Budgeted Cost of Work Scheduled = "**Planned Value**"
- Cost Performance Index = CPI = BCWP / ACWP = EV / AC
	- CPI > 1: project underbudget 😊
	- CPI < 1: project overbudget 😢
- Cost Variance = CV = BCWP - ACWP = EV - AC
	- CV > 0: project underbudget 😊
	- CV < 0: project overbudget 😢
- Schedule Performance Index = SPI = BCWP / BCWS = EV / PV
	- SPI > 1: project ahead of schedule 😊
	- SPI < 1: project behind schedule 😢
- Schedule Variance = SV = BCWP - BCWS = EV - PV
	- SV > 0: project ahead of schedule 😊
	- SV < 0: project behind schedule 😢

En nuestro ejemplo:

- ACWP: Actual Cost of Work Performed = $1000 = AC
	- El 40% del trabajo completado terminó costando $1000.
- BCWP: Budgeted Cost of Work Performed = $800 = EV
	- Se estimó que el 40% de trabajo completado cueste $800.
- BCWS: Budgeted Cost of Work Scheduled = $1200 = PV
	- En el día del reporte (al final del día 3), se estimó un 60% del trabajo completado con un costo de $1200.
- CPI = $800 / $1000 = 0.8 < 1 => project overbudget 😢
- CV = $800 - $1000 = -$200 < 0 => project overbudget 😢
- SPI = $800 / $1200 = 0.67 < 1 => project behind schedule 😢
- SV = $800 - $1200 = -$400 < 0 => project behind schedule 😢

> [!NOTE]
>
> - Cost Performance Index & Cost Variance: son 2 formas de saber si el proyecto fue costeado por encima o por debajo.
> - Schedule Performance Index & Schedule Variance:
> 	- Son 2 formas de saber si el proyecto está adelantado o atrasado en calendario.
> 	- Otra forma de razonar es viendo el timeline del ejemplo: si el reporte fue realizado al final del 3° día, pero solamente los primeros 2 días de trabajo estimado fueron completados => El proyecto se encuentra atrasado.
> 		- Esto puede no ser tan intuitivo sobre Gantts enormes, para ello empleamos SPI & SV.

---

¿Cuáles son las 2 formas de calcular el calendario del proyecto?
?
1. Schedule Performance Index = SPI = BCWP / BCWS = EV / PV
2. Schedule Variance = SV = BCWP - BCWS = EV - PV
<!--SR:!2025-06-25,1,230-->

¿Cuáles son las 2 formas de calcular el costo del proyecto?
?
1. Cost Performance Index = CPI = BCWP / ACWP = EV / AC
2. Cost Variance = CV = BCWP - ACWP = EV - AC
<!--SR:!2025-06-25,1,230-->

---

## Métricas Orientadas a los Recursos (Seres Humanos)

Cualquier entidad requerida para realizar un proceso o actividad.

- Cantidad de fallas detectadas por tester.
- Cantidad de LOC producidas por un desarrollador.
- Esfuerzo dedicado a codificar por un desarrollador.
- Edad promedio del equipo.
- Costo promedio de cada rol.
- Años de experiencia promedio de cada rol o del equipo.
- Deuda técnica generada o resuelta por un dev o por un equipo.
- Velocity de un dev o de un equipo.

---

¿Qué es una métrica orientada a los recursos (seres humanos)?
?
Métrica asociada a cualquier entidad requerida para realizar un proceso o actividad.
<!--SR:!2025-06-25,1,230-->

¿Cuáles son las métricas orientadas a los recursos (seres humanos)?
?
- Cantidad de fallas detectadas por tester.
- Cantidad de LOC producidas por un desarrollador.
- Esfuerzo dedicado a codificar por un desarrollador.
- Edad promedio del equipo.
- Costo promedio de cada rol.
- Años de experiencia promedio de cada rol o del equipo.
- Deuda técnica generada o resuelta por un dev o por un equipo.
- Velocity de un dev o de un equipo.
<!--SR:!2025-06-25,1,230-->

---
