---
tags:
- flashcards/swe/teoria/2P
---

# El Proceso de SW Testing

## Informalmente hablando del proceso de Testing

Es posible imaginarlo desde 2 aristas:
- Probar es ejecutar un componente con el objetivo de producir fallas.
- Una prueba es exitosa si encuentra fallas.

> [!NOTE]
>
> Al siguiente nos adentramos a la formalidad de un proceso de SW Testing.

## El proceso de Testing

El proceso de Testing se compone de 2 partes:

![[02.1-el-proceso-de-testing.png]]

- Arriba: Se refiere al **diseño de la prueba**.
	1. Requerimiento: lo que hay que hacer.
	2. Condiciones de prueba: Caso general a realizar.
		- e.g., si se trata de un Login: "que el usuario complete usuario & password y pueda loggearse".
	3. Casos de prueba: Concreto.
		1. e.g., "usuario saraza y password 123".
	4. Resultado esperado.
		- Si el password está bien => Loggearse.
		- Si el password está mal => No dejar loggearse.
		- Si el usuario está bien => Loggearse.
		- Etc.
- Abajo: Se refiere a la **ejecución** de la prueba.
	1. Componente: componente de SW asociado al requerimiento.
	2. Armado del entorno: entorno en donde se hace la prueba.
	3. Ejecución de casos:
		- La ocurrencia de un **caso de prueba** es la ejecución en sí del caso.
	4. Resultado obtenido.

> [!NOTE]
>
> - Resultado esperado == Resultado obtenido => El caso de prueba es exitoso.
> - Resultado esperado != Resultado obtenido => Se da lugar a un **incidente**.
> - No sabemos si el incidente está bien o está mal, pero el incidente existe.

---

Nombrar y explicar las etapas del proceso de Testing.
?
- Arriba: Se refiere al **diseño de la prueba**.
	1. Requerimiento: lo que hay que hacer.
	2. Condiciones de prueba: Caso general a realizar.
		- e.g., si se trata de un Login: "que el usuario complete usuario & password y pueda loggearse".
	3. Casos de prueba: Concreto.
		1. e.g., "usuario saraza y password 123".
	4. Resultado esperado.
		- Si el password está bien => Loggearse.
		- Si el password está mal => No dejar loggearse.
		- Si el usuario está bien => Loggearse.
		- Etc.
- Abajo: Se refiere a la **ejecución** de la prueba.
	1. Componente: componente de SW asociado al requerimiento.
	2. Armado del entorno: entorno en donde se hace la prueba.
	3. Ejecución de casos:
		- La ocurrencia de un **caso de prueba** es la ejecución en sí del caso.
	4. Resultado obtenido.
- Resultado esperado == Resultado obtenido => El caso de prueba es exitoso.
- Resultado esperado != Resultado obtenido => Se da lugar a un **incidente**.
- ![[02.1-el-proceso-de-testing.png]]
<!--SR:!2025-06-25,1,230-->

---

## Conceptos relacionados al proceso

La manifestación física (lo que nos encontramos):

![[02.2-conceptos-relacionados-al-proceso.png]]

- **Equivocación**:
	- Acción humana que produce un resultado incorrecto.
	- e.g., programación errónea, documento funcional erróneo o confuso, 
- **Defecto**:
	- Paso, proceso o definición de dato incorrecto.
	- Ausencia de cierta característica.
	- Esto conlleva a que el componente de SW no haga lo que dice que hace.
	- Se genera debido a una o más **equivocaciones**.
- **Falla**:
	- Resultado de ejecución incorrecta.
	- e.g., suponiendo que el incidente es efectivamente algo que no debiera pasar (nos dejó loggear cuando no debería) => La manifestación física es **falla**.
	- Se genera debido a un defecto.
- De alguna forma arranca todo a partir de un **[[#Incidentes en Testing|incidente]]** (es un 4to elemento a la derecha de todo).

---

¿Cuáles son los conceptos relacionados al proceso?
?
- **Equivocación**:
	- Acción humana que produce un resultado incorrecto.
	- e.g., programación errónea, documento funcional erróneo o confuso,
- **Defecto**:
	- Paso, proceso o definición de dato incorrecto.
	- Ausencia de cierta característica.
	- Esto conlleva a que el componente de SW no haga lo que dice que hace.
	- Se genera debido a una o más **equivocaciones**.
- **Falla**:
	- Resultado de ejecución incorrecta.
	- e.g., suponiendo que el incidente es efectivamente algo que no debiera pasar (nos dejó loggear cuando no debería) => La manifestación física es **falla**.
	- Se genera debido a un defecto.
- De alguna forma arranca todo a partir de un **incidente** (es un 4to elemento a la derecha de todo).
- ![[02.2-conceptos-relacionados-al-proceso.png]]
<!--SR:!2025-06-25,1,230-->

---

### Cardinalidad

- Equivocación -1---(1, N)- Defecto:
	- Una equivocación humana puede causar 1 o varios defectos en el SW.
	- e.g., un error al escribir código o al especificar un requerimiento. Si un programador malinterpreta un requerimiento, esa única equivocación puede provocar varios defectos en el código.
- Defecto -1---(0, N)- Falla:
	- Un defecto en el SW puede causar 0, 1 o varias fallas cuando el SW se ejecuta.
		- 0: No siempre un defecto se manifiesta como una falla. Puede que nunca se ejecute el código con defecto.
		- N: Pero un mismo defecto puede causar la aparición de varias fallas en diferentes ejecuciones o escenarios. El caso particular es N = 1 cuando un defecto se asocia exactamente con una única falla.
	- e.g., un defecto en una función puede no causar una falla si nunca se ejecuta esa función, o puede causar múltiples fallas si se usa muchas veces bajo distintas condiciones.

Una sola equivocación puede derivar en varios defectos, y un defecto puede manifestarse en ninguna, una o muchas fallas cuando se ejecuta el SW.

---

¿Qué significan las cardinalidades entre los 4 conceptos relacionados al proceso de Testing?
?
- Equivocación -1---(1, N)- Defecto:
	- Una equivocación humana puede causar 1 o varios defectos en el SW.
	- e.g., un error al escribir código o al especificar un requerimiento. Si un programador malinterpreta un requerimiento, esa única equivocación puede provocar varios defectos en el código.
- Defecto -1---(0, N)- Falla:
	- Un defecto en el SW puede causar 0, 1 o varias fallas cuando el SW se ejecuta.
		- 0: No siempre un defecto se manifiesta como una falla. Puede que nunca se ejecute el código con defecto.
		- N: Pero un mismo defecto puede causar la aparición de varias fallas en diferentes ejecuciones o escenarios. El caso particular es N = 1 cuando un defecto se asocia exactamente con una única falla.
	- e.g., un defecto en una función puede no causar una falla si nunca se ejecuta esa función, o puede causar múltiples fallas si se usa muchas veces bajo distintas condiciones.
- Es decir, una sola equivocación puede derivar en varios defectos, y un defecto puede manifestarse en ninguna, una o muchas fallas cuando se ejecuta el SW.
- ![[02.2-conceptos-relacionados-al-proceso.png]]
<!--SR:!2025-06-25,1,230-->

---

### Ejemplos

- No se probó lo suficiente: si en total tenemos 10 casos posibles, pero solamente probamos 4 de los 10, la falla no apareció pero el defecto sigue estando.
- También, para casos como `if (true) { // código sin error } else { // código con falla }`, el flujo de ejecución nunca llega a ejecutar el código con la falla.

## Incidentes en Testing

Según IEEE, un incidente es:

- Toda ocurrencia de un evento que ocurre durante la ejecución de una prueba de SW que requiere investigación.
- Un incidente puede deberse a:
	- Un defecto en el SW.
	- Un defecto en los casos de prueba.
	- Un defecto en el ambiente.
	- Entre otros eventos.

Entonces no todo incidente es una falla, por ejemplo:
- Defectos en los casos.
- Equivocaciones al ejecutar las pruebas.
- Interpretaciones erróneas.
- Dudas.

> [!NOTE]
>
> - Lo importante de un incidente es su **análisis** (analizarlo per sé).
> - El análisis conlleva a suponer que:
> 	- El SW posee características erróneas.
> 	- Los casos de pruebas son erróneos.
> 	- La ejecución de la prueba fue errónea.
> 	- El entorno se encuentra mal configurado (e.g., usuario para probar incorrecto).

---

(Control U6) ¿Qué es un incidente en Testing?
?
Según IEEE, un incidente es:
- Toda ocurrencia de un evento que ocurre durante la ejecución de una prueba de SW que requiere investigación.
- Un incidente puede deberse a:
	- Un defecto en el SW.
	- Un defecto en los casos de prueba.
	- Un defecto en el ambiente.
	- Entre otros eventos.
<!--SR:!2025-06-25,1,230-->

¿Todo incidente implica una falla? En caso de no serlo, dé ejemplos.
?
No todo incidente es una falla, por ejemplo:
- Defectos en los casos.
- Equivocaciones al ejecutar las pruebas.
- Interpretaciones erróneas.
- Dudas.
<!--SR:!2025-06-25,1,230-->

---

## Proceso de Depuración

Depuración:

- Depurar es eliminar un defecto que posee el SW.
- La depuración NO es una tarea de prueba aunque es consecuencia de ella.
- La prueba detecta la falla (efecto) de un defecto (causa).
- La depuración puede ser fuente de introducción de nuevos defectos.
- En la "Depuración" debemos:
	- Detectar:
		- Dada la falla debemos hallar el defecto (dado el efecto debemos encontrar la causa).
	- Depurar:
		- Encontrado el defecto debemos eliminarlo.
		- Debemos encontrar la razón del defecto.
		- Debemos encontrar una solución.
		- Debemos aplicarla.
	- Volver a probar:
		- Asegurar que sacamos el defecto.
		- Asegurar que no hemos introducido otros (regresión).
	- Aprender para el futuro:
		- Lecciones Aprendidas.

> [!NOTE]
>
> - A partir de la manifestación de una falla (efecto) => Nos ponemos a entender cuál es la causa (defecto).
> - Luego de analizar el defecto => Corregimos la equivocación.
> - La depuración usualmente posee asociado una "corrección".
> - Esta "corrección" puede ser la introducción a un nuevo error.
> - El proceso de depuración se encuentra en la arista "Defecto - Falla".

---

Depurar es ==1;;eliminar un defecto== que posee el SW.
<!--SR:!2025-06-25,1,230-->

La depuración permite, a partir de la manifestación de ==1;;una falla (efecto)==, poder a entender cuál es ==1;;la causa (defecto)== y luego corregir ==1;;la equivocación==.
<!--SR:!2025-06-25,1,230-->

La depuración NO es una ==1;;tarea de prueba==, es una ==1;;consecuencia== de ella.
<!--SR:!2025-06-25,1,230-->

La prueba detecta ==1;;la falla (efecto)== de ==1;;un defecto (causa)==.
<!--SR:!2025-06-25,1,230-->

La ==1;;corrección== de una depuración puede ser fuente de ==1;;introducción de nuevos defectos==.
<!--SR:!2025-06-25,1,230-->

El proceso de depuración se encuentra en la arista ==1;;Defecto== - ==1;;Falla==.
<!--SR:!2025-06-25,1,230-->

¿Qué debemos hacer en la "depuración"?
?
- Detectar:
	- Dada la falla debemos hallar el defecto (dado el efecto debemos encontrar la causa).
- Depurar:
	- Encontrado el defecto debemos eliminarlo.
	- Debemos encontrar la razón del defecto.
	- Debemos encontrar una solución.
	- Debemos aplicarla.
- Volver a probar:
	- Asegurar que sacamos el defecto.
	- Asegurar que no hemos introducido otros (regresión).
- Aprender para el futuro:
	- Lecciones Aprendidas.
<!--SR:!2025-06-25,1,230-->

---
