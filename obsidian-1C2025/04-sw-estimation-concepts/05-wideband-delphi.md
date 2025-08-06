---
tags:
- flashcards/swe/teoria/1P
- flashcards/swe/teoria/U4
---

# Wideband Delphi

- Es el [[03-juicio-experto|juicio experto]] **en grupos**.
- Da lugar a la participación de todos los involucrados.
	- Existe la visión de más de un experto en la mesa: Puede que no sean todos desarrolladores (e.g., testers).
- Provee varias ventajas por sobre la estimación individual:
	- Fácil de implementar y [[10-obl-timebox-development#Estimaciones de calendarios realistas creadas por el equipo _timebox_|da sentido de propiedad sobre la estimación]].
	- **Permite construir un desglose completo de tareas para las actividades esenciales**.
	- El consenso fomentado permite eliminar el sesgo en las estimaciones, producidas por distintas figuras de "autoridad": Expertos, estimadores inexpertos o individuos influenciales (propósitos escondidos).
	- Usualmente las personas están más comprometidas en aquellas estimaciones en las que son partícipes.
	- Ningún participante posee la verdadera respuesta y la creación de varias estimaciones da lugar a la aceptación de esta incertidumbre.
	- Filtra valores extremos y elimina parte de la "política" de la estimación.
	- Los participantes reconocen el "valor de iterar" sobre cualquier actividad compleja.
- Se puede utilizar en etapas tempranas del proyecto.
- Se recomienda utilizarlo en proyectos poco conocidos en donde no se cuenta con historia.
	- e.g., en caso de que solamente un único experto lo estime como si él lo fuese a programar, existe un equipo detrás que hará el trabajo y en realidad el experto !== equipo. Los tiempos son otros y por este motivo se ve la perspectiva de todos los integrantes, en vez de un único experto.
	- La problemática es similar para casos en donde en vez de no contar con una historia, no se conoce al equipo, no se conoce las tecnologías, no se conoce el proyecto, no se conoce la aplicación, etc.
- e.g., le preguntamos al experto: "¿Cuánto se tarda en hacer esto?", nos contesta: "No lo puedo decir yo, debemos juntarnos con el equipo". Al juntarnos con el equipo el experto en Java nos dice "1 semana", el experto en JS nos dice "3 semanas", pero el experto en texting nos dice "2 semanas". Cada uno va aportando la complejidad que ve en su área de expertise y permite estimar mejor.

> [!NOTE]
>
> El autor de la lectura recomendada cuenta que empleó este método para alcanzar el nivel 2 del [[09-cmmi-modelos-de-calidad-de-proceso|CMMI]].

---

¿En qué consiste el método de estimación _Wideband Delphi_?
?
- Es el juicio experto **en grupos**.
- Da lugar a la participación de todos los involucrados.
	- Existe la visión de más de un experto en la mesa: Puede que no sean todos desarrolladores (e.g., testers).
- Provee varias ventajas por sobre la estimación individual:
	- Fácil de implementar y da sentido de propiedad sobre la estimación.
	- Permite construir un desglose completo de tareas para las actividades esenciales.
	- El consenso fomentado permite eliminar el sesgo en las estimaciones, producidas por distintas figuras de "autoridad": Expertos, estimadores inexpertos o individuos influenciales (propósitos escondidos).
	- Usualmente las personas están más comprometidas en aquellas estimaciones en las que son partícipes.
	- Ningún participante posee la verdadera respuesta y la creación de varias estimaciones da lugar a la aceptación de esta incertidumbre.
	- Filtra valores extremos y elimina parte de la "política" de la estimación.
	- Los participantes reconocen el "valor de iterar" sobre cualquier actividad compleja.
- Se puede utilizar en etapas tempranas del proyecto.
- Se recomienda utilizarlo en proyectos poco conocidos en donde no se cuenta con historia.
	- e.g., en caso de que solamente un único experto lo estime como si él lo fuese a programar, existe un equipo detrás que hará el trabajo y en realidad el experto !== equipo. Los tiempos son otros y por este motivo se ve la perspectiva de todos los integrantes, en vez de un único experto.
	- La problemática es similar para casos en donde en vez de no contar con una historia, no se conoce al equipo, no se conoce las tecnologías, no se conoce el proyecto, no se conoce la aplicación, etc.

---

---

(Esta parte no se trató en clases pero es de la lectura recomendada)

## Wideband Delphi Process Flow

![](05.1-wideband-delphi-process-flow.png)

### Planning

- Se delimita el problema, dividiendo en partes manejables si es grande.
- El responsable prepara una documentación suficientemente detallada para permitir estimaciones informadas.
- Selección de participantes:
	- Moderador: Planea y coordina, conoce el problema, puede estimar pero actúa como facilitador imparcial.
	- Gerente del proyecto y 2 a 4 estimadores expertos en el dominio.
- Propósito: Que todos los participantes comprendan claramente el problema y estén preparados para estimar.

### Kickoff Meeting

- Duración: Hasta 1 hora.
- Acciones:
	- El moderador explica el método y entrega la especificación, supuestos y restricciones.
	- Se revisan los objetivos de la estimación y se acuerdan las unidades a utilizar (horas, semanas, líneas de código, etc.).
	- Se evalúa si todos están listos (criterios de entrada):
		- Miembros adecuados seleccionados.
		- Kickoff realizado.
		- Acuerdo sobre objetivos y unidades.
		- Gerente de proyecto disponible.
		- Estimadores informados adecuadamente.
	- Si alguien no está preparado, se le instruye o sustituye.

### Individual Preparation

- Cada participante:
	- Desarrolla de manera independiente su lista de tareas necesarias para cumplir el objetivo.
	- Desglosa actividades hasta tareas que no excedan ~20 horas-persona.
	- Estima el esfuerzo de cada tarea y suma para una estimación total inicial (en las unidades acordadas).
	- Registra supuestos y tareas de soporte (calidad, configuración, gestión, re-trabajo, reuniones, vacaciones, etc.).
- Guías:
	- Asumir que una persona realiza todas las tareas, de forma secuencial y sin interrupciones.
	- Listar tiempos de espera previstos para luego traducir esfuerzo a calendario si es necesario.
- Nota: No debe influir la expectativa del gerente u otros interesados; las estimaciones pueden estar fuera de los límites aceptables y requerir negociación posterior.

### Estimation Meeting

- Inicio:
	- El moderador recopila las estimaciones individuales y las muestra anónimamente en una gráfica (para evitar presión o deferencia a figuras de autoridad).
- Discusión inicial:
	- Cada participante lee su lista de tareas, los supuestos y plantea dudas, sin revelar su estimación.
	- Se combinan las listas para formar una lista de tareas más completa.
	- Se discuten supuestos y problemas de estimación, trabajando hacia un conjunto común de tareas y supuestos.
- Ajuste iterativo:
	- Todos ajustan (en silencio) sus estimaciones y listas, corrigiendo tareas y valores con lo aprendido.
	- El moderador recopila y grafica la nueva ronda de estimaciones.
	- Se repite el ciclo (discusión, ajuste, recopilación), normalmente hasta cumplir una o más de estas condiciones:
		- Se completan 4 rondas.
		- Las estimaciones convergen a un rango aceptable (definido previamente).
		- Se termina el tiempo asignado (usualmente 2 horas).
		- Los participantes no quieren modificar más sus estimaciones.
- Moderación:
	- El moderador controla el tiempo, fomenta la participación de todos y mantiene el anonimato al menos en las primeras rondas. En rondas finales, se puede optar por discusión abierta si el grupo lo acuerda, para cerrar diferencias grandes.
	- Se sugiere limitar discusiones a 15–20 minutos por tema.

### Assembling Tasks

- Consolidación:
	- El moderador o gerente fusiona todas las listas y estimaciones en una sola lista maestra, incluyendo tareas, supuestos, actividades de calidad/proceso, tareas generales y tiempos de espera.
	- Se eliminan duplicados y se resuelven diferencias razonablemente, manteniendo el rango de estimaciones para cada tarea.
	- Si hay diferencias grandes en tareas similares, se revisan las definiciones para aclarar posibles malentendidos.
	- Si la estimación de un participante es muy diferente, se analiza y, si corresponde, se ajusta o descarta.

### Review Results

- Reunión de cierre: (30–60 minutos)
	- Se presentan al equipo la lista final de tareas, las estimaciones individuales y acumuladas, los supuestos y otra información relevante.
	- El equipo verifica la completitud y sensatez de la consolidación.
	- Se pueden añadir tareas olvidadas o corregir estimaciones fusionadas de forma inadecuada.
	- El objetivo es lograr un rango de estimaciones que permita planificar con un nivel aceptable de confianza.

### Completing the Estimation

- Criterios de salida:
	- La lista de tareas ha sido armada.
	- Existe una lista de supuestos.
	- Hay consenso sobre cómo se sintetizó la estimación y el rango es aceptable.
- Tratamiento de resultados:
	- Se puede promediar las estimaciones, pero se recomienda conservar el rango (mejor caso, peor caso, caso promedio) para reflejar la incertidumbre inherente.
	- Opcionalmente, se pueden usar técnicas matemáticas como intervalos de predicción o simulaciones Monte Carlo para analizar la distribución de resultados.
- Seguimiento:
	- Comparar los resultados reales del proyecto con las estimaciones para mejorar la precisión futura.

---