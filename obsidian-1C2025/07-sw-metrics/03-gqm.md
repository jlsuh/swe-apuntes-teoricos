---
tags:
- flashcards/swe/teoria/2P
---

# ¿Cómo implementar un programa de métricas?

> [!NOTE]
>
> - Estas preguntas las hacen los _heads_, gerentes, "capo de tecnología de la organización".
> - Estas personas plantean el deseo de: tener una especie de tablero para entender cómo la organización está funcionando y qué tan lejos están de los objetivos, que nos indique N indicadores, mensualmente.
> - Responde a la pregunta: ¿Cómo hacemos para implementar estos indicadores?

Pasos a seguir:

1. Identificar los objetivos (GQM).
2. Hallar las preguntas que me ayuden a alcanzar el objetivo (GQM).
	- e.g., ¿cuántas LoC fallan?, ¿cuántos puntos de función estamos entregando?
3. Definir las métricas (GQM).
	- e.g., para productividad: # LoC por dev-mes, para calidad: # incidentes por mes, # pruebas fallidas por LoC mes, para funcionalidad: # puntos de función entregadas por LoC.
4. Recolectar datos históricos.
	- Para saber si mejoramos o empeoramos.
5. Definir el proceso de recolección de datos para las métricas.
	- e.g., ¿de dónde extraerlos? ¿en qué momento?
6. Recolectar, validar y analizar los datos.
	- Control de calidad sobre los datos para que no haya nada que meta ruido en los indicadores (_outliers_).
7. Utilizar las métricas en la toma de decisiones.
	- Es el paso más importante, ya que si incurrimos un montón de esfuerzo en los 6 pasos anteriores pero al final no lo aprovechamos, todo es en vano.
	- Si no tenemos impacto en las decisiones que tomamos => Cuestionar si métricas son las adecuadas.

> [!NOTE]
>
> - CMMI nivel 4: tenemos las métricas y las usamos para tomar ciertas decisiones (gobernanza del proceso mediante métricas).
> - CMMI nivel 5: además del nivel 4, e.g., si estamos usando Scrum, le agregamos 2 fases de Testing adicionales ya que algún indicador lo sugiere. Se modifica el proceso.

---

 ¿Cómo se implementa un programa de métricas? #exam-question
 ?
 1. Identificar los objetivos (GQM).
2. Hallar las preguntas que me ayuden a alcanzar el objetivo (GQM).
	- e.g., ¿cuántas LoC fallan?, ¿cuántos puntos de función estamos entregando?
3. Definir las métricas (GQM).
	- e.g., para productividad: # LoC por dev-mes, para calidad: # incidentes por mes, # pruebas fallidas por LoC mes, para funcionalidad: # puntos de función entregadas por LoC.
4. Recolectar datos históricos.
	- Para saber si mejoramos o empeoramos.
5. Definir el proceso de recolección de datos para las métricas.
	- e.g., ¿de dónde extraerlos? ¿en qué momento?
6. Recolectar, validar y analizar los datos.
	- Control de calidad sobre los datos para que no haya nada que meta ruido en los indicadores (_outliers_).
7. Utilizar las métricas en la toma de decisiones.
	- Es el paso más importante, ya que si incurrimos un montón de esfuerzo en los 6 pasos anteriores pero al final no lo aprovechamos, todo es en vano.
	- Si no tenemos impacto en las decisiones que tomamos => Cuestionar si métricas son las adecuadas.
<!--SR:!2025-06-25,1,230-->

V o F. Los 7 pasos para la implementación de un programa de métricas incluye al GQM.::V, la incluye en los 3 primeros.
<!--SR:!2025-06-25,1,230-->

A diferencia del CMMI nivel 4 en donde solamente empleamos las métricas obtenidas para tomar decisiones (gobernanza del proceso mediante métricas), el CMMI nivel 5 permite ==1;;modificar== y ==1;;mejorar== el proceso en base a las métricas obtenidas.
<!--SR:!2025-06-25,1,230-->

---

# GQM - Goal Question Metric - Basado en 3 niveles

1. Conceptual (**G**oal):
	- Metas (goals): aquello que la organización intenta alcanzar (SMART).
	- SMART: acrónimo mnemotécnico para establecer criterios para la formulación efectiva de metas y el desarrollo de objetivos.
		- **S**pecific.
		- **M**easurable.
		- **A**chievable.
		- **R**elevant.
		- **T**ime-Bound.
2. Operacional (**Q**uestion):
	- Preguntas (questions): son aquellas preguntas cuyas respuestas permiten definir el cumplimiento de las metas.
3. Cuantitativo (**M**etrics):
	- Métricas (metrics): las mediciones necesarias para ayudar a responder a las preguntas y confirmar si las mejoras del proceso cumplieron su objetivo.

---

¿En qué consiste el GQM? #exam-question
?
1. Conceptual (**G**oal):
	- Metas (goals): aquello que la organización intenta alcanzar (SMART).
	- SMART: acrónimo mnemotécnico para establecer criterios para la formulación efectiva de metas y el desarrollo de objetivos.
		- **S**pecific.
		- **M**easurable.
		- **A**chievable.
		- **R**elevant.
		- **T**ime-Bound.
2. Operacional (**Q**uestion):
	- Preguntas (questions): son aquellas preguntas cuyas respuestas permiten definir el cumplimiento de las metas.
3. Cuantitativo (**M**etrics):
	- Métricas (metrics): las mediciones necesarias para ayudar a responder a las preguntas y confirmar si las mejoras del proceso cumplieron su objetivo.
- Observación: contiene hasta el punto 3 de los 7 puntos.
<!--SR:!2025-06-25,1,230-->

---

## Ejemplo

![[03.1-gqm-example.png]]

> [!NOTE]
>
> - Definida como estructura jerárquica, no excluyente.
> - "# de fallas reportadas": dato duro.
> - "Nivel de satisfacción del usuario": dato más blando, hacerlo mediante alguna encuesta al usuario.
