---
tags:
- flashcards/swe/teoria/2P
---

# Overview

- Registrar la información del Estado de la Gestión de CM.
- Reportar el Estado de la Configuración.

> [!NOTE]
>
> SWEBOK:
>
> - Actividad que consiste en registrar y reportar información necesaria para gestionar una configuración en forma efectiva de ICs, baselines y relaciones entre las ICs.
> - Debe ser realizado siguiendo los esquemas lógicos definidos en la actividad [[#SC Identification|SC Identification]] para recolectar información de los ICs, baselines y las relaciones entre las ICs.

> [!NOTE]
>
> - ¿En qué estado se encuentra lo auditado?
> - ¿Qué informe brindamos a la alta gerencia / el que haya solicitado el reporte?

---

Nombrar las actividades del SC Status Accounting.
?
- Registrar la información del Estado de la Gestión de CM.
- Reportar el Estado de la Configuración.
<!--SR:!2025-06-22,1,230-->

---

# Status Accounting de la Configuración

> Analizando la historia de los cambios.

- Tiene la función de registrar y reportar la información necesaria para administrar la configuración de manera efectiva. Para ello debe:
	- Listar los ICs aprobados.
	- Mostrar el estado de los cambios que fueron aprobados.
	- Reportar la trazabilidad de todos los cambios efectuados al baseline.
- Una implementación exitosa de esta actividad debe poder contestar:
	- ¿Qué cambios se realizaron al sistema?
	- ¿Cuándo se realizaron dichos cambios?
	- ¿Quién lo cambió?
- También responder acerca del proceso de cambios:
	- ¿Quién aprobó el cambio?
	- Quién solicitó el cambio?

> [!NOTE]
>
> No solamente entender el blame, sino que también la parte de la mejora:
>
> - En qué fallamos como equipo y qué tenemos que cambiar para no volver a fallar.
> - e.g., si heredamos un sistema nuevo, ¿qué componentes nos gustaría saber de dicho sistema tal que nos vislumbre una idea de la vida que tendremos a partir de la herencia de dicho sistema? No interesaría saber:
> 	- Cada cuánto es que reportan un ticket por un bug.
> 	- Qué tipos de cambios están viniendo:
> 		- ¿Son todos por bugs?
> 		- ¿Son funcionalidades nuevas?
> 		- ¿Cada cuánto agregan funcionalidades nuevas?
> 		- Estos nos dan una idea de la vida que tendremos en el proyecto.
> 	- Componentes que más fallan: Para así ponerle más empeño al refactoring sobre los mismos.
> 	- Cuántos usuarios posee el sistema.
> - En general, es información que nos permite entender "cómo cambiar nuestra vida".

---

(Control U5) ¿Qué es el Status Accounting de SCM?
?
Tiene la función de registrar y reportar la información necesaria para administrar la configuración de manera efectiva. Para ello debe:
- Listar los ICs aprobados.
- Mostrar el estado de los cambios que fueron aprobados.
- Reportar la trazabilidad de todos los cambios efectuados al baseline.
<!--SR:!2025-06-22,1,230-->

¿Qué preguntas debe poder contestar una implementación exitosa del Status Accounting de la Configuración?
?
- ¿Qué cambios se realizaron al sistema?
- ¿Cuándo se realizaron dichos cambios?
- ¿Quién lo cambió?
- También responder acerca del proceso de cambios:
	- ¿Quién aprobó el cambio?
	- Quién solicitó el cambio?
<!--SR:!2025-06-22,1,230-->

V o F. En general, el Status Accounting de SCM nos permite obtener información que nos permite entender "cómo cambiar nuestra vida".
?
V, nos permite saber:
- Cada cuánto es que reportan un ticket por un bug.
- Qué tipos de cambios están peticionando: si son todos por bugs, funcionalidades nuevas, cada cuánto agregan funcionalidades nuevas, cuáles son los componentes que más fallan, cuántos usuarios posee el sistema, etc.
- Nos permite darnos una idea de la vida que tendremos en el proyecto.
<!--SR:!2025-06-22,1,230-->

---
