---
tags:
- flashcards/swe/teoria/2P
---

# Overview

- Solicitar, evaluar y aprobar cambios al SW.
- Implementar cambios al SW.
- (Entender) Desviaciones y excepciones del proceso.

> [!NOTE]
>
> SWEBOK:
>
> - Abarca los cambios sobre los ICs durante el ciclo de vida del SW.
> - Abarca el proceso de determinar:
> 	- Qué cambios hacer.
> 	- La autoridad que aprueba ciertos cambios.
> 	- El soporte para implementar dichos cambios.
> 	- Los desvíos formales y exenciones de los requerimientos del proyecto.

> [!NOTE]
>
> - ¿Quién puede solicitar, aprobar, implementar los cambios?
> - En Scrum:
> 	- El rol candidato para solicitar cambios es el PO.
> 	- El rol candidato para aprobar cambios es cada uno de los stakeholder (SCCB).
> - Cualquier componente que tengamos dentro del proyecto y que sufrirá cambios a lo largo de su ciclo de vida, debe pasar por este control.
> 	- Uno de los mismos son **los cambios a los propios baselines**.

---

Nombrar las actividades del control de cambios de la configuración.
?
- Solicitar, evaluar y aprobar cambios al SW.
- Implementar cambios al SW.
- (Entender) Desviaciones y excepciones del proceso.
<!--SR:!2025-06-22,1,230-->

El rol candidato para solicitar cambios en Scrum es ==1;;el PO==.
<!--SR:!2025-06-22,1,230-->

El rol candidato para aprobar cambios es ==1;;cada uno de los stakeholder (SCCB)==.
<!--SR:!2025-06-22,1,230-->

V o F. Los cambios a las baselines per sé nunca puede sufrir cambios una vez definido, por lo que no hace falta pasar por este control.::F, cualquier componente que tengamos dentro del proyecto y que sufrirá cambios a lo largo de su ciclo de vida, debe pasar por este control. Uno de los mismos son **los cambios a las propias baselines**.
<!--SR:!2025-06-22,1,230-->

---

# Control de cambios de la configuración

> Establecer reglas para incorporar cambios al SW.

- Asegura que los ICs mantienen su integridad ante los cambios a través de:
	- La **identificación** del propósito del cambio.
		- e.g., "incorporar CVU, además de CBU".
	- La **evaluación del impacto** y aprobación del cambio.
		- ¿Cambio pequeño / grande / afecta a 3°?
	- La **planificación** de la incorporación del cambio.
		- e.g., entre julio y agosto, ya que septiembre habrá nueva reglamentación del BCRA.
	- El **control** de la implementación del cambio y su verificación.
		- Entender cómo fue la ejecución del cambio.
- El Control de Cambios de la Configuración consiste en establecer un procedimiento de control de cambios y controlar el cambio y la liberación de ICs a lo largo del ciclo de vida.

> [!NOTE]
>
> - Los primeros 3 implican **entender** sobre los cambios a realizar en la configuración.
> - La última implica **control**.

---

(Control U5) ¿En qué consiste el Control de Cambios de las configuraciones?
?
- Establecer un procedimiento de control de cambios.
- Controlar el cambio y la liberación de ICs a lo largo del ciclo de vida.
<!--SR:!2025-06-22,1,230-->

¿Cómo hace el Control de cambios de la configuración para asegurar la manutención de la integridad ante los cambios?
?
Esto lo hace mediante:
- La **identificación** del propósito del cambio.
- La **análisis y evaluación del impacto o riesgo**.
- La **planificación** de la incorporación del cambio.
- La **aprobación** del cambio.
- La **incorporación** del cambio.
- El **control** de la implementación del cambio.
- La **verificación** de la implementación del cambio.
<!--SR:!2025-06-22,1,230-->

---

## SW Configuration Control Board

![[06.1-sccb.png]]

- Es quién tiene la autoridad de aceptar o rechazar un cambio en la configuración de SW.
	- No lo menciona en la PPT, pero también "peticionar".
- En proyectos pequeños puede residir en el Líder del proyecto y, a medida que se incrementa la complejidad, puede ir incorporando nuevos integrantes.
- Puede haber diversos niveles de autorización de acuerdo a diferentes criterios.
	- Por ejemplo: Un nivel puede ser compuesto solo por Stakeholders para autorizar o no un cambio de alcance, mientras que en otro nivel el PO acepta o no un cambio en el Sprint Backlog.
	- Dependiendo del tamaño del SW, tamaño del cambio y tamaño de la organización, existen distintas jerarquías de aprobación.

---

¿Qué es el SW Configuration Control Board (SCCB)?
?
Es quién tiene la autoridad de aceptar o rechazar (o peticionar) un cambio en la configuración de SW.
<!--SR:!2025-06-22,1,230-->

El SCCB, en proyectos pequeños, puede residir en el ==1;;Líder del proyecto== y, a medida que se incrementa la complejidad, puede ir ==1;;incorporando nuevos integrantes==.
<!--SR:!2025-06-22,1,230-->

V o F. En el SCCB solamente existe un único nivel de autorización.::F, pueden haber diversos niveles de autorización de acuerdo a diferentes criterios, e.g., un nivel puede ser compuesto solo por Stakeholders para autorizar o no un cambio de alcance, mientras que en otro nivel el PO acepta o no un cambio en el Sprint Backlog.
<!--SR:!2025-06-22,1,230-->

Existen distintas jerarquías de aprobación en función del ==1;;tamaño del SW==, ==1;;tamaño del cambio== y ==1;;tamaño de la organización==.
<!--SR:!2025-06-22,1,230-->

---

### Importancia de la diversidad de roles en el SCCB

Existen varios roles participantes y cada uno ve distintas cosas:

- Desarrollo: Vela por la arquitectura, la seguridad del código y su mantenibilidad, fiabilidad, manutención de un alto nivel de estándares. Puede que pidamos una modificación que no es viable.
- Testing: Garantiza que todos los tests habidos y por haber hayan pasado, determina si la calidad es suficiente para pasarlo a producción, si posee toda la documentación regulatoria exigido por el cliente y el proceso para pasaje a producción.
- PO / Usuario de negocio: Puede que el producto SW cumpla con todas sus funcionalidades, pero puede que pidan parar la salida a producción del mismo debido a:
	- e.g., en el día de la madre ningún negocio quisiera perderse ninguna venta debido a un defecto sobre un PostNet / flujo de pagos. Los cambios lo hacemos luego del día de la madre.
- Stakeholders extraordinarios.
- e.g., contextos bancarios:
	- Son parte del SCCB los FINCON (control financiero): pueden desaprobar los cambios debido a procesos de auditorías.
	- "Freeze" bancario: es cuando se presentan todos los balances contables, denegando cualquier modificación durante dicho período.
- e.g., aplicaciones gubernamentales:
	- Puede que exista una regla en que no se pueden realizar despliegues a producción durante los últimos 10 días del mes y los primeros 10 días del próximo mes. Esto es debido a que la liquidación de los planes sociales ocurren durante este periodo.
	- No obstante, por algún motivo se hace caso omiso a esta regla y resulta que rompemos producción y encontramos de paso nuevos bugs.
	- En este caso, el Control Board ha fallado en no frenar el cambio. Una aplicación del gobierno es usualmente considerado como crítico.

---

La importancia de la diversidad de roles en el SCCB yace en que cada rol ve ==1;;distintos aspectos==.
<!--SR:!2025-06-22,1,230-->

Algunos ejemplos de por qué el SCCB podría desaprobar la implementación del cambio son:
?
- En el día de la madre ningún negocio quisiera perderse ninguna venta debido a un defecto sobre un PostNet / flujo de pagos. Los cambios lo hacemos luego del día de la madre.
- Contextos bancarios:
	- Son parte del SCCB los FINCON (control financiero): pueden desaprobar los cambios debido a procesos de auditorías.
	- "Freeze" bancario: es cuando se presentan todos los balances contables, denegando cualquier modificación durante dicho período.
- Aplicaciones gubernamentales:
	- Puede que exista una regla en que no se pueden realizar despliegues a producción durante los últimos 10 días del mes y los primeros 10 días del próximo mes. Esto es debido a que la liquidación de los planes sociales ocurren durante este periodo.
	- No obstante, por algún motivo se hace caso omiso a esta regla y resulta que rompemos producción y encontramos de paso nuevos bugs.
	- En este caso, el Control Board ha fallado en no frenar el cambio. Una aplicación del gobierno es usualmente considerado como crítico.
<!--SR:!2025-06-22,1,230-->

---

## Change Management Process

Es el flujo y las herramientas definidas para identificar, analizar y aprobar cambios a una configuración. Difiere en cada Organización, pero en general se puede dividir en las siguientes etapas:

---

¿En qué consiste el proceso de gestión de cambios?
?
Es el flujo y las herramientas definidas para identificar, analizar y aprobar cambios a una configuración.
<!--SR:!2025-06-22,1,230-->

V o F. El proceso de gestión de cambios difiere en cada Organización.::V
<!--SR:!2025-06-22,1,230-->

¿Cuáles son las etapas en general en las que se puede subdividir el proceso de gestión de cambios? Explicar cada una.
?
1. Identificar el cambio: Incluye formalizar el pedido de cambio.
2. Evaluar el impacto:
	- Analizar el cambio y determinar el impacto que tendrá en el SW, el equipo que trabaja en él y quienes lo usarán.
	- Evaluar los aspectos técnicos del cambio, sus posibles efectos secundarios y el impacto general en otras partes del sistema.
3. Decidir hacer o no el cambio: Entendiendo el impacto en el negocio, o en el calendario o en el equipo.
4. Planificar la implementación del cambio: Incorporarlo dentro de las tareas a realizar.
<!--SR:!2025-06-22,1,230-->

Un cambio puede ser solicitado tanto por ==1;;un usuario== como por ==1;;un desarrollador==.
<!--SR:!2025-06-22,1,230-->

En general, solo se aceptan solicitudes de cambios de ==1;;personas autorizadas a pedirlo==.
<!--SR:!2025-06-22,1,230-->

El cambio es ==1;;evaluado== y ==1;;comparado== contra los ==1;;objetivos del proyecto==.
<!--SR:!2025-06-22,1,230-->

El impacto del cambio se evalúa tanto en ==1;;el producto== como en ==1;;la calendarización del proyecto==.
<!--SR:!2025-06-22,1,230-->

En caso de ==1;;rechazar== la solicitud de un cambio, se puede dejar como parte de una ==1;;"Segunda Fase" del proyecto== o incorporarlo en una ==1;;segunda iteración de desarrollo==.
<!--SR:!2025-06-22,1,230-->

En caso de ==1;;aceptar== la solicitud de un cambio, se ==1;;re-planifican las tareas== a realizar y se le asigna ==1;;recursos== para resolverlo.
<!--SR:!2025-06-22,1,230-->

V o F. El cambio implementado no tiene por qué ser revisado en auditorías.::F
<!--SR:!2025-06-22,1,230-->

La complejidad de la administración del cambio varía de acuerdo al proyecto: en ==1;;proyectos pequeños==, el pedido de cambio puede ser ==1;;informal== y ==1;;desarrollarse rápidamente==, mientras que en ==1;;proyectos más complejos== puede haber ==1;;comités de varias personas== que ==1;;evalúen el cambio==.
<!--SR:!2025-06-22,1,230-->

---

### 1. Identificar el cambio

Incluye formalizar el pedido de cambio.

### 2. Evaluar el impacto

- Analizar el cambio y determinar el impacto que tendrá en el SW, el equipo que trabaja en él y quienes lo usarán.
- Evaluar los aspectos técnicos del cambio, sus posibles efectos secundarios y el impacto general en otras partes del sistema.

### 3. Decidir hacer o no el cambio

Entendiendo el impacto en el negocio, o en el calendario o en el equipo.

### 4. Planificar la implementación del cambio

Incorporarlo dentro de las tareas a realizar.

### Ejemplo: Proceso Control de Cambios

- **Se solicita el cambio**:
	- Puede ser solicitado tanto por un usuario como por un desarrollador.
	- En general, solo se aceptan cambios de personas autorizadas a pedirlo.
- **El cambio es evaluado y comparado contra los objetivos del proyecto**:
	- Un grupo de asesores evalúa el cambio y lo aprueba o rechaza.
	- Se suele evaluar el impacto del cambio tanto en el producto como en la calendarización del proyecto.
- Si **rechazado**: se puede dejar como parte de una "Segunda Fase" del proyecto o incorporarlo en una segunda iteración de desarrollo.
- Si **aceptado**: se re-planifican las tareas a realizar y se le asigna recursos para resolverlo.
- El cambio implementado deberá ser revisado en auditorías.
	- La complejidad de la administración del cambio varía de acuerdo al proyecto:
		- En proyectos pequeños: el pedido de cambio puede ser informal y desarrollarse rápidamente.
		- En proyectos más complejos: puede haber comités de varias personas que evalúen el cambio.

## Mediciones relacionadas a Change Requests

---

Nombre y explique las mediciones relacionadas a Change Requests.
?
- Successful Changes: Cuenta la cantidad de cambios que han sido aprobados y desplegados en producción sin generar incidentes.
- Emergency Changes: Cuenta la cantidad de cambios que han sido aprobados por canales de urgencia o emergencia.
- Changes in Backlog: Mide la cantidad de cambios pendientes de ser analizados. Es un indicio de la eficiencia del proceso de aprobación de cambios y se puede utilizar para evaluar la velocidad del equipo.
<!--SR:!2025-06-22,1,230-->

---

### Successful Changes

Cuenta la cantidad de cambios que han sido aprobados y desplegados en producción sin generar incidentes.

### Emergency Changes

Cuenta la cantidad de cambios que han sido aprobados por canales de urgencia o emergencia.

### Changes in Backlog

Mide la cantidad de cambios pendientes de ser analizados. Es un indicio de la eficiencia del proceso de aprobación de cambios y se puede utilizar para evaluar la velocidad del equipo.

> [!NOTE]
>
> Pueden haber 2 flujos distintos:
>
> - Flujo normal:
> 	- Se hace el cambio.
> 	- Pasa por toda la revisión del SCCB.
> 	- Se implementa en caso de estar aprobado.
> - Flujo de emergencia:
> 	- Se hace el cambio de lo que se tenga que corregir (existe un _maker_ y un _checker_).
> 	- Posteriormente se pasa por todo el proceso de aprobación y se revisa que esté correctamente implementado: que no haya generado más problemas de lo que resolvía.
> 	- Disparar la solución definitiva.
