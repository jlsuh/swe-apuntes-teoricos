---
tags:
- flashcards/swe/teoria/2P
---

#exam-question 

# Using Heuristic Test Oracles

- Nos permite contestar: ¿Cómo saber si el comportamiento encontrado durante las pruebas realmente es un bug?, sin tener ningún requerimiento a mano que determine qué es lo que el SW debe hacer.
- Nos permite:
	- Desarrollar un vocabulario para explicar "por qué algo que parece incorrecto es de hecho un bug".
	- Tener un buen fundamento para justificarlo.
	- Ganar seguidores.
- Una heurística es una solución a un problema que funciona la mayor parte del tiempo.
	- Son falibles.
	- No se recomienda únicamente depender de estos.
	- Es mejor emplear los requisitos en caso de que los tengamos disponibles.
	- Es mejor citar usuarios reales disponibles.
	- Solamente utilizar los oráculos para respaldar datos existentes sobre un error o para explicar otros aspectos del error que pueden no ser evidentes solamente con los requisitos.

## Heurística HICCUPP

- **H**istory.
- **I**mage.
- **C**omparable Product.
- **C**laims.
- **U**ser Expectation.
- **P**roduct.
- **P**urpose.

---

(Control U6) ¿Qué son los oráculos de testing?
?
- Son heurísticas que nos permite contestar: ¿Cómo saber si el comportamiento encontrado durante las pruebas realmente es un bug?, sin tener ningún requerimiento a mano que determine qué es lo que el SW debe hacer.
- Nos permite:
	- Desarrollar un vocabulario para explicar "por qué algo que parece incorrecto es de hecho un bug".
	- Tener un buen fundamento para justificarlo.
	- Ganar seguidores.
<!--SR:!2025-06-25,1,230-->

Una heurística es ==1;;una solución a un problema== que funciona ==1;;la mayor parte del tiempo==.
<!--SR:!2025-06-25,1,230-->

Nombrar los motivos por el cuál una heurística es una solución a un problema que funciona la mayor parte del tiempo.
?
- Son falibles.
- No se recomienda únicamente depender de estos.
- Es mejor emplear los requisitos en caso de que los tengamos disponibles.
- Es mejor citar usuarios reales disponibles.
- Solamente utilizar los oráculos para respaldar datos existentes sobre un error o para explicar otros aspectos del error que pueden no ser evidentes solamente con los requisitos.
<!--SR:!2025-06-25,1,230-->

---

### Inconsistente con la Historia

- Un producto debe ser consistente con versiones anteriores (su historia).
- La historia puede incluir versiones previas, parches, declaraciones, etc.
- Si algo ha cambiado y nadie dijo que debía cambiar, entonces probablemente hemos encontrado un problema.

---

¿En qué consiste el oráculo "Inconsistente con la Historia"?
?
- Un producto debe ser consistente con versiones anteriores (su historia).
- La historia puede incluir versiones previas, parches, declaraciones, etc.
- Si algo ha cambiado y nadie dijo que debía cambiar, entonces probablemente hemos encontrado un problema.
<!--SR:!2025-06-25,1,230-->

---

### Inconsistente con la Imagen

- La mayoría de las empresas quieren tener una buena imagen en el mercado => Su SW necesita verse profesional y ser coherente con los estándares aceptados.
- Si un producto es inconsistente con la imagen deseada, estamos diciendo que: "Quedaremos ridiculizados (poco profesionales) si lanzamos este SW al mercado".

---

¿En qué consiste el oráculo "Inconsistente con la Imagen"?
?
- La mayoría de las empresas quieren tener una buena imagen en el mercado => Su SW necesita verse profesional y ser coherente con los estándares aceptados.
- Si un producto es inconsistente con la imagen deseada, estamos diciendo que: "Quedaremos ridiculizados (poco profesionales) si lanzamos este SW al mercado".
<!--SR:!2025-06-25,1,230-->

---

### Inconsistente con un Producto Comparable

- Otro producto sirve como nuestro oráculo para esta prueba.
- Este oráculo puede ser muy convincente, siempre que:
	- El producto comparable realmente sea comparable y queremos el producto sea una alternativa a dicho producto.
	- Queremos captar a los usuarios que ese producto tiene.

> [!TIP]
>
> Si queremos implementar una indexación en un buscador, no puede ser tan distinto al funcionamiento de los demás buscadores con indexación.

---

¿En qué consiste el oráculo "Inconsistente con un Producto Comparable"?
?
- Otro producto sirve como nuestro oráculo para esta prueba.
- Este oráculo puede ser muy convincente, siempre que:
	- El producto comparable realmente sea comparable y queremos el producto sea una alternativa a dicho producto.
	- Queremos captar a los usuarios que ese producto tiene.
- e.g., si queremos implementar una indexación en un buscador, no puede ser tan distinto al funcionamiento de los demás buscadores con indexación.
<!--SR:!2025-06-25,1,230-->

---

### Inconsistente con las Declaraciones

- Una "declaración" puede ser cualquier cosa que alguien en nuestra empresa diga sobre el producto.
- Si algo es inconsistente con las declaraciones, es inconsistente con, en relación al producto:
	- Los requisitos declarados.
	- La ayuda.
	- El material de marketing.
	- Simplemente algo que un interesado del proyecto dijo en el pasillo.

---

¿En qué consiste el oráculo "Inconsistente con las Declaraciones"?
?
- Una "declaración" puede ser cualquier cosa que alguien en nuestra empresa diga sobre el producto.
- Si algo es inconsistente con las declaraciones, es inconsistente con, en relación al producto:
	- Los requisitos declarados.
	- La ayuda.
	- El material de marketing.
	- Simplemente algo que un interesado del proyecto dijo en el pasillo.
<!--SR:!2025-06-25,1,230-->

---

### Inconsistente con las Expectativas del Usuario

- El producto no hace algo que un usuario razonable esperaría que hiciera, o no realiza una tarea de la manera que el usuario esperaría.
- Usar este oráculo significa que tenemos alguna idea de quién es el usuario y alguna indicación de lo que espera.

---

¿En qué consiste el oráculo "Inconsistente con las Expectativas del Usuario"?
?
- El producto no hace algo que un usuario razonable esperaría que hiciera, o no realiza una tarea de la manera que el usuario esperaría.
- Usar este oráculo significa que tenemos alguna idea de quién es el usuario y alguna indicación de lo que espera.
<!--SR:!2025-06-25,1,230-->

---

### Inconsistente dentro del Producto

- Algo se comporta de una manera en una parte del producto, pero de una manera diferente en otra parte del producto.
- El cambio podría estar relacionado con:
	- La terminología.
	- El aspecto visual.
	- La funcionalidad.
	- El conjunto de características.
- Todo lo que hacemos es señalar dónde el producto es inconsistente consigo mismo y suelen ser errores convincentes.

---

¿En qué consiste el oráculo "Inconsistente dentro del Producto"?
?
- Algo se comporta de una manera en una parte del producto, pero de una manera diferente en otra parte del producto.
- El cambio podría estar relacionado con:
	- La terminología.
	- El aspecto visual.
	- La funcionalidad.
	- El conjunto de características.
- Todo lo que hacemos es señalar dónde el producto es inconsistente consigo mismo y suelen ser errores convincentes.
<!--SR:!2025-06-25,1,230-->

---

### Inconsistente con el Propósito

- Según el autor, este es el oráculo más convincente.
- Afirma que el comportamiento que encontramos es contradictorio con lo que un usuario querría hacer con este SW.
- Podríamos estar hablando del propósito de una función, por ejemplo: ingresar un valor negativo para campos que no tienen sentido que acepten valores negativos.
- Este oráculo suele usarse junto con [[#Inconsistente con las Declaraciones|Inconsistente con las Declaraciones]] o [[#Inconsistente con las Expectativas del Usuario|Inconsistente con las Expectativas del Usuario]], porque dichos oráculos también tienden a abordar el propósito del SW.

---

¿En qué consiste el oráculo "Inconsistente con el Propósito"?
?
- Según el autor, este es el oráculo más convincente.
- Afirma que el comportamiento que encontramos es contradictorio con lo que un usuario querría hacer con este SW.
- Podríamos estar hablando del propósito de una función, por ejemplo: ingresar un valor negativo para campos que no tienen sentido que acepten valores negativos.
- Este oráculo suele usarse junto con Inconsistente con las Declaraciones o Inconsistente con las Expectativas del Usuario, porque dichos oráculos también tienden a abordar el propósito del SW.
<!--SR:!2025-06-25,1,230-->

---

## Crossover entre oráculos

- Cuando un producto incumple un oráculo, a menudo incumple otros también.
	- La mayoría de las inconsistencias entran en conflicto con las expectativas del usuario, y si creemos que algo es inconsistente, pensamos que eso es malo para la imagen de la empresa.
	- Esto señala la fuerza relativa de cada uno de estos oráculos (mayor a menor fuerza):
		1. Inconsistente con las Declaraciones, Inconsistente con un Producto Comparable e Inconsistente con la Historia: son los más efectivos para lograr que se corrijan errores.
		2. Inconsistente dentro del Producto e Inconsistente con el Propósito: tienden a influir en los devs, pero rara vez en los gerentes.
		3. "Inconsistente con la Imagen" e "Inconsistente con las Expectativas del Usuario":
			- No suelen recibir mucha atención en el mundo de la resolución de defectos.
			- Son significativos para usuarios expertos y expertos en marketing.
			- Tienden a ser considerados extrañamente subjetivos por quienes priorizan los defectos.
			- Normalmente no se reportan defectos en base solo en estos dos oráculos. Los usamos como _el "glaseado en una dona" que ya está llena de errores_.

---

Cuando un producto incumple un oráculo, a menudo ==1;;incumple otros también==. ==1;;La mayoría de las inconsistencias entran en conflicto con las expectativas del usuario, y si creemos que algo es inconsistente, pensamos que eso es malo para la imagen de la empresa.==
<!--SR:!2025-06-25,1,230-->

H I C C U P P

¿Cómo es el ranking de los oráculos respecto a la fuerza relativa? De mayor a menor.
?
1. Inconsistente con las Declaraciones, Inconsistente con un Producto Comparable e Inconsistente con la Historia: son los más efectivos para lograr que se corrijan errores.
2. Inconsistente dentro del Producto e Inconsistente con el Propósito: tienden a influir en los devs, pero rara vez en los gerentes.
3. "Inconsistente con la Imagen" e "Inconsistente con las Expectativas del Usuario":
	- No suelen recibir mucha atención en el mundo de la resolución de defectos.
	- Son significativos para usuarios expertos y expertos en marketing.
	- Tienden a ser considerados extrañamente subjetivos por quienes priorizan los defectos.
	- Normalmente no se reportan defectos en base solo en estos dos oráculos. Los usamos como _el "glaseado en una dona" que ya está llena de errores_.
<!--SR:!2025-06-25,1,230-->

---

## Aplicación del HICCUPP

### Caso 1: Altitud negativa

En Google Earth, se encontró que si se hace zoom completamente hacia afuera, se inclina la vista completamente hacia abajo y se mantiene presionado el zoom-in, se puede hacer que se muestre altitudes negativas.

Este resultado ilustra los siguientes comportamientos:

- Inconsistente dentro del producto: No es posible acercarse a una altitud negativa si no se aplica previamente una inclinación.
- Inconsistente con el propósito: El propósito de hacer zoom e inclinar no es obtener altitudes negativas, sino lograr una mejor vista del paisaje.
- Inconsistente con las expectativas del usuario: Ciertamente, no esperan ver un valor negativo.

### Caso 2: Renderización de líneas al seleccionar capas

En Google Earth, al seleccionar más de 1 o 2 capas, una serie de líneas blancas se vuelve visible durante el renderizado.

Este resultado ilustra los siguientes comportamientos:

- Inconsistente con el propósito: Las líneas dificultan la capacidad para ver realmente el mapa.
- Inconsistente con la imagen: Problema bastante básico que descubierto en los primeros días de la aplicación. Se ve mal y dado que es un SW de Google, se espera más de Google.

### Caso 3: Tiempos de viaje diferentes para las indicaciones

En la comparación de Google Earth con Google Local, al buscar las indicaciones para llegar de una ubicación a otra, se descubrió que los tiempos de conducción sugeridos diferían en 24 minutos, a pesar de tener la misma distancia en millas y la misma ruta sugerida.

Este resultado ilustra los siguientes comportamientos:

- Inconsistente con el producto: Ambos productos de Google deberían obtener el mismo resultado.
- Inconsistente con la imagen: Google produce ambos productos y sus comportamientos inconsistentes no son buenos para la imagen de Google.

### Caso 4: Documentación inexacta

El archivo de ayuda de Google Earth afirmó: "La página web de Google Maps aparece en la mitad inferior de la pantalla con las indicaciones resaltadas en la página junto con las instrucciones", al hacer click en el enlace Vista para imprimir. Al hacer click, en lugar de aparecer en la parte inferior de la página, la página web se abre en Firefox.

Esto es inconsistente con las declaraciones.

Por otro lado, el autor no cree que sea inconsistente con las expectativas del usuario ni con la imagen, ya que la funcionalidad en sí cumplió las expectativas del usuario y es bueno para la imagen de Google mostrar que su aplicación funciona con otros productos como Firefox.

> [!NOTE]
>
> - El autor no mostró un ejemplo de inconsistencia con la historia, ya que Google Earth estaba en beta y es lo que ocurre cuando una aplicación está en beta.

## Preguntas a hacernos previo a un reporte de defectos

- Es este defecto:
	- ¿Inconsistente con la historia del producto?
	- ¿Inconsistente con la imagen que nuestra empresa (o equipo de proyecto) intenta proyectar?
	- ¿Inconsistente con un producto comparable?
	- ¿Inconsistente con las declaraciones hechas sobre el producto?
	- ¿Inconsistente con las expectativas del usuario sobre el producto?
	- ¿Una muestra de una inconsistencia dentro del producto?
	- ¿Inconsistente con el propósito del producto?
- Nos permite entrenar la mente para encontrar defectos en base a estos criterios en el futuro.
- Es una manera rápida y poderosa de mejorar la forma en que pensamos las pruebas.

---

¿Cuáles son las preguntas que debemos hacernos previo a un reporte de defectos?
?
- ¿Inconsistente con la historia del producto?
- ¿Inconsistente con la imagen que nuestra empresa (o equipo de proyecto) intenta proyectar?
- ¿Inconsistente con un producto comparable?
- ¿Inconsistente con las declaraciones hechas sobre el producto?
- ¿Inconsistente con las expectativas del usuario sobre el producto?
- ¿Una muestra de una inconsistencia dentro del producto?
- ¿Inconsistente con el propósito del producto?
<!--SR:!2025-06-25,1,230-->

HICCUPP es una manera ==1;;rápida== y ==1;;poderosa== de mejorar la forma en que pensamos las ==1;;pruebas==.
<!--SR:!2025-06-25,1,230-->

HICCUPP nos permite entrenar la mente para encontrar ==1;;defectos== en base a estos ==1;;criterios== en el futuro.
<!--SR:!2025-06-25,1,230-->

---
