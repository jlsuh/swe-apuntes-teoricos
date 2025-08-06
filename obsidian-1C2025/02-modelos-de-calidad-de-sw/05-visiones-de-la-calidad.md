---
tags:
- flashcards/swe/teoria/1P
- flashcards/swe/teoria/U2
---

La calidad puede ser percibida desde 5 perspectivas.

# Visión trascendental

La calidad es algo que se puede reconocer pero no se puede definir.

> [!TIP]
>
> - Estomacal / primera impresión.
> - Es más para el equipo de Marketing que para un equipo de desarrollo.
> - Ranking de subjetividad: 1°

> [!TIP]
>
> Guía las decisiones del diseño ("ergonomía" del producto, no la etapa), _look and feel_, distribución de funcionalidades, qué UI utilizar, el _packaging_, el _pricing_, etc., que dan la sensación de que un SW es de calidad.
>
> Si bien suena como que fuese algo que siempre se encuentra presente en todo el ciclo de vida de un SW, tiene más que ver con "lo que se percibe al usar el producto", "el marketing que tiene", etc.

---

¿En qué consiste la visión trascendental?
?
La calidad es algo que se puede reconocer pero no se puede definir:
- Estomacal / primera impresión.
- Es más para el equipo de Marketing que para un equipo de desarrollo.
- Ranking de subjetividad: 1°
<!--SR:!2025-05-06,2,253-->

---

# Visión del usuario

La calidad es adecuación al propósito.

> [!TIP]
>
> - "Fit for use".
> - "Depende para qué lo use".
> - Ranking de subjetividad: 3°

> [!TIP]
>
> En clases se mencionó que esta visión es menos subjetiva que la [[#Visión basada en el valor|visión basada en el valor]], ya que depende de un usuario en sí.

---

¿En qué consiste la visión del usuario?
?
La calidad es adecuación al propósito:
- "Fit for use".
- "Depende para qué lo use".
- Ranking de subjetividad: 3°
<!--SR:!2025-05-05,1,213-->

---

# Visión de la manufactura

La calidad es conformidad con **la especificación**.

> [!TIP]
>
> - Visión fabril: "esto será difícil de mantener".
> - Especificidad a la especificación:
> 	- Realizar mediciones y compararlo contra la especificación
> 	- e.g., al cerrar la puerta debe hacer 2dBA.
> - Busca minimizar el costo: desplazar hacia abajo las [[03-costo-de-la-no-calidad#Costos ocultos de la "No-Calidad"|curvas de costo]].
> - Busca poco retrabajo y poca equivocación.
> - Ranking de subjetividad: 5°

---

¿En qué consiste la visión de la manufactura?
?
La calidad es conformidad con la **especificación**:
- Visión fabril: "esto será difícil de mantener".
- Especificidad a la especificación:
	- Realizar mediciones y compararlo contra la especificación.
	- e.g., al cerrar la puerta debe hacer 2dBA.
- Busca minimizar el costo: desplazar hacia abajo las [[03-costo-de-la-no-calidad#Costos ocultos de la "No-Calidad"|curvas de costo]].
- Busca poco retrabajo y poca equivocación.
- Ranking de subjetividad: 5°
<!--SR:!2025-05-05,1,213-->

---

# Visión del producto

La calidad está vinculada a las características inherentes del producto.

> [!TIP]
>
> - "Gana el que mejor especificación tenga".
> - e.g., especificaciones del celular.
> - Ranking de subjetividad: 4°

---

¿En qué consiste la visión del producto?
?
La calidad está vinculada a las características inherentes del producto.
- "Gana el que mejor especificación tenga".
- e.g., especificaciones del celular.
- Ranking de subjetividad: 4° (A diferencia del 3°, es menos subjetiva que la misma ya que depende del producto en sí, mientras que el 3° es dependiendo de cada usuario).
<!--SR:!2025-05-06,2,230-->

---

# Visión basada en el valor

La calidad depende de la cantidad de dinero que el usuario está dispuesto a pagar por el producto.

> [!TIP]
>
> - "¿Cuánto estoy dispuesto a pagar por el producto?"
> - Relación precio-calidad.
> - Según la materia economía: es la definición de **valor de uso**.
> - Ranking de subjetividad: 2°

---

¿En qué consiste la visión basada en el valor?
?
La calidad depende de la cantidad de dinero que el usuario está dispuesto a pagar por el producto.
- "¿Cuánto estoy dispuesto a pagar por el producto?"
- Relación precio-calidad.
- Según la materia economía: es la definición de **valor de uso**.
- Ranking de subjetividad: 2°
<!--SR:!2025-05-06,2,230-->

---

# Un buen desarrollo de SW debe tener en cuenta todas estas visiones

> [!IMPORTANT]
>
> En base a qué etapa nos encontremos en el ciclo de vida del SW, conviene más una visión de calidad u otra.

- Visión trascendental: Ver [[#Visión trascendental|TIP de visión trascendental]].
- Visión del usuario: **análisis**.
- Visión de la manufactura: **construcción**.
- Visión del producto: **diseño**.
- Visión basada en el valor: **deploy**.

> [!TIP]
>
> La etapa de mantenimiento contiene las mismas etapas del ciclo de vida del SW, solo que son de menor duración. e.g., en vez de durar meses, duran días.

---

V o F. En base a qué etapa nos encontremos en el ciclo de vida del SW, conviene más una visión de calidad u otra.::V
<!--SR:!2025-05-06,2,253-->

La visión de calidad trascendental incumbe más al equipo de ==1;;marketing== que al ==1;;equipo de desarrollo==.
<!--SR:!2025-05-06,2,250-->

La visión de calidad del usuario conviene en la etapa de ==1;;análisis==.
<!--SR:!2025-05-06,2,233-->

La visión de calidad de la manufactura conviene en la etapa de ==1;;construcción==.
<!--SR:!2025-05-06,2,250-->

La visión de calidad del producto conviene en la etapa de ==1;;diseño==.
<!--SR:!2025-05-05,1,230-->

La visión de calidad basada en el valor conviene en la etapa de ==1;;deploy==.
<!--SR:!2025-05-06,2,230-->

(Control U2) Nombre las visiones de calidad que conoce.
?
- Visión trascendental.
- Visión del usuario.
- Visión de la manufactura.
- Visión del producto.
- Visión basada en el valor.
<!--SR:!2025-05-05,1,233-->

(Control U2) ¿En qué puntos del ciclo de vida utilizaría cada visión de calidad?
?
- Visión trascendental:
	- Durante el diseño del _look and feel_ ("ergonómico") del producto, la distribución de funcionalidades, la definición de la UI a emplear, el _packaging_, _pricing_, etc., que dan la sensación de que un SW es de calidad.
	- Si bien suena como que fuese algo que siempre se encuentra presente en todo el ciclo de vida de un SW, tiene más que ver con "lo que se percibe al usar el producto", "el marketing que tiene", etc.
- Visión del usuario: **análisis**.
- Visión de la manufactura: **construcción**.
- Visión del producto: **diseño**.
- Visión basada en el valor: **deploy**.
<!--SR:!2025-05-05,1,233-->

---
