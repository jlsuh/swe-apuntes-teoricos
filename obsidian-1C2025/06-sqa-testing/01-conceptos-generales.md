---
tags:
- flashcards/swe/teoria/2P
---

# Conceptos Generales de SW Testing

## ¿Qué es el testing de SW?

### Según IEEE

Actividad en la cual un sistema o componente es:
- Ejecutado bajo condiciones específicas.
	- Condiciones específicas: El SW Testing depende mucho del contexto, condiciones o el sistema (en el sentido holístico) en donde realizamos las pruebas.
	- Generalmente probamos en un entorno de pruebas, siendo dicho entorno nuestro contexto.
- Los resultados de dicha ejecución son observados o registrados.
- A partir de los mismos, se realiza una evaluación de algún aspecto del sistema o componente.

### Definición usual

SW Testing es usualmente definida como:
- Una actividad para evaluar si los resultados obtenidos en la ejecución del SW coinciden los los resultados esperados.
- Propósito: Determinar si el sistema está libre de defectos.
- Involucra la ejecución de un componente de SW o de un sistema para evaluar una o varias propiedades de interés.

### Otra definición (Cem Kaner)

Investigación técnica empírica ejecutada para proveer a los stakeholders con información de la calidad del producto o servicio que se encuentra a prueba.

### Las pruebas por sí solas encuentran fallas, NO defectos

A lo cual solo pueden demostrar su presencia pero nunca su ausencia.

> [!NOTE]
>
> - Probar más =/=> Encontrar más fallas.
> - Probar menos =/=> Encontrar menos fallas.
> - La falla existe desde un momento previo, las pruebas permiten traer a la luz dichas fallas.
> - Situación:
> 	- Probamos algo y vemos que no funciona correctamente. Esto por sí mismo no identifica dónde se encuentra el problema.
> 	- Teniendo dicha falla, tenemos que comenzar a buscar en el código para ver dónde se encuentra el problema realmente.
> 	- Esto es a lo que nos referimos con "encuentran fallas, NO defectos".

---

Las pruebas por sí solas encuentran ==1;;fallas==, NO ==1;;defectos==.
<!--SR:!2025-06-25,1,230-->

Las pruebas solo pueden demostrar la ==1;;presencia== de ==1;;fallas==, pero nunca ==1;;su ausencia==.
<!--SR:!2025-06-25,1,230-->

V o F. Probar más implica encontrar más fallas y probar menos implica encontrar menos fallas.::F, probar más no implica encontrar más fallas y probar menos no implica encontrar menos fallas. La falla existe desde un momento previo, las pruebas permiten traer a la luz dichas fallas.
<!--SR:!2025-06-25,1,230-->

---

### Suposición

- Partimos de la suposición: Que el SW a probar contiene defectos (lo cual casi siempre es válido) y se trata de encontrar tantos como sea posible.
	- e.g., si nuestro objetivo es intentar romper el SW (encontrar fallas), nuestro mindset es distinto:
		- No probamos que "nuestro SW debe hacer A + B = C", sino que en vez de A + B hacemos B + A.
		- Esta es una posición más crítica y desencadena otra serie de casos o condiciones totalmente distintos, en comparación a si pensamos en hacer el camino feliz (en demostrar que el SW hace lo que tiene que hacer).
- Por el contrario, si nuestro objetivo es mostrar que el SW no contiene errores, estaremos inconscientemente orientados a ese fin.
	- e.g., si nuestro objetivo es mostrar que el SW no contiene errores:
		- En base a un requerimiento decimos que "nuestro SW debe hacer A + B = C".
		- Probamos que "nuestro SW debe hacer A + B = C", concluyendo simplemente en si falla o no.
- El adoptar una u otra actitud tiene profundas implicancias en el éxito de la prueba.

---

(Control U6) ¿Qué es el testing y que "mindset" requiere?
?
SW Testing es usualmente definida como:
- Una actividad para evaluar si los resultados obtenidos en la ejecución del SW coinciden los los resultados esperados.
- Propósito: Determinar si el sistema está libre de defectos.
- Involucra la ejecución de un componente de SW o de un sistema para evaluar una o varias propiedades de interés.
- Requiere de un mindset de partir de la suposición: Que el SW a probar contiene defectos (lo cual casi siempre es válido) y se trata de encontrar tantos como sea posible.
<!--SR:!2025-06-25,1,230-->

V o F. El adoptar una u otra actitud tiene profundas implicancias en el éxito de la prueba.::V, si nuestro objetivo es mostrar que el SW no contiene errores (camino feliz), estaremos inconscientemente orientados a ese fin. En cambio, la suposición de que el SW a probar contiene defectos (lo cual casi siempre es válido) y se trata de encontrar tantos como sea posible, es una posición más crítica y desencadena otra serie de casos o condiciones totalmente distintos.
<!--SR:!2025-06-25,1,230-->

---

## ¿Por qué es importante el Testing?

El Testing es importante porque los [[03-costo-de-la-no-calidad#Etapas del desarrollo de SW|bugs pueden ser costosos]] o incluso peligrosos. Los bugs de SW pueden causar potencialmente problemas económicos o de pérdidas humanas.

Motivos de por qué el Testing se hace cada vez más importante:
- Cada vez existe SW más crítico y más complejo.
- El SW está escrito por personas y cometen errores => SW puede cometer defectos que llevarán potencialmente a fallas.

> [!NOTE]
>
> 2 postulados universales del Testing:
>
> 1. El Testing es una actividad dependiente del contexto.
> 2. Cuanto más antes encuentre los problemas => Mejor y más baratos corregirlos.

---

¿Por qué es la importante el Testing?
?
El Testing es importante porque las fallas pueden ser costosas / peligrosas y pueden causar potencialmente problemas económicas / pérdidas humanas.
<!--SR:!2025-06-25,1,230-->

¿Por qué el Testing se hace cada vez más importante?
?
- Cada vez existe SW más crítico y más complejo.
- El SW está escrito por personas y cometen errores => SW puede cometer defectos que llevarán potencialmente a fallas.
<!--SR:!2025-06-25,1,230-->

¿Cuáles son los 2 postulados universales del Testing?
?
1. El Testing es una actividad dependiente del contexto.
2. Cuanto más antes encuentre los problemas => Mejor y más baratos corregirlos.
<!--SR:!2025-06-25,1,230-->

---

## ¿Qué es la crisis del SW?

- Este término fue acuñado ya en los años 70, cuando la industria del SW ya había producido los suficientes programas para darse cuenta de que había algo que fallaba. En concreto estas eran sus principales inquietudes:
	- ¿Por qué lleva tanto tiempo terminar los programas?
	- ¿Por qué es tan elevado el coste?
	- ¿Por qué no podemos encontrar todos los errores antes de entregar el SW a nuestros clientes
	- ¿Por qué es tan difícil constatar el progreso durante el desarrollo?
	- ¿Por qué es tan difícil calcular cuánto tiempo va a costar?
- Esto pasaba entonces y pasa ahora, y por eso se dice que el SW está en crisis. Ante dicha situación se planteó el aplicar métodos científicos y rigurosos al proceso de desarrollo de programas, apareciendo en escena la Ingeniería del SW y la Ingeniería de Requerimientos.
- Aunque quizás:
	- "El SW no está en crisis. La crisis le viene desde que nació. Lo que hay que plantearse es por qué no ha salido de esa crisis en todo este tiempo."

> [!NOTE]
>
> La crisis del SW fue un punto de inflexión:
> - Hasta dicho momento era más caro adquirir el HW que desarrollar el SW de dicho HW.
> - La ecuación se invierte con la crisis del SW: HW ya no es tan caro pero si es más costos desarrollar el SW.
> - En vez de tener el foco sobre la electrónica, el foco viró hacia el desarrollo de SW => Se puso foco en el Testing y la llamada "ingeniería de SW".

## ¿Cuál es el objetivo del Testing?

- Básicamente: encontrar fallas en el producto.
	- TODO SW POSEE FALLAS.
- De forma eficiente:
	- Hacerlo lo más rápido posible (tiempo).
	- Hacerlo lo más barato posible (costo).
- De forma eficaz:
	- Encontrar la mayor # de fallas.
	- No detectar fallas que en realidad no son.
	- Encontrar las más importantes.

Cuando se dice "No detectar fallas que en realidad no son", se refiere a minimizar los falsos positivos (FP):

```js
// index.js
export function add(a, b) {
	return a + b;
}

// index.test.js
describe("...", () => {
	it("Should return 4", () => {
		expect(add(2, 2)).toBe(5);
	});
});
```

- Tenemos un test que verifica que `sumar(2, 2)` devuelve 4. Pero por error definimos que `sumar(2, 2)` devuelva 5.
- El test va a marcar esto como una "falla", pero en realidad NO lo es: el código está bien, el test está mal.

| Caso                    | ¿El objeto posee una falla? | ¿Se detecta la falla? | Descripción breve                                            |
| ----------------------- | --------------------------- | --------------------- | ------------------------------------------------------------ |
| Verdadero Positivo (VP) | Sí                          | Sí                    | El objeto tiene una falla y esta es detectada correctamente. |
| Falso Positivo (FP)     | No                          | Sí                    | El objeto no tiene falla, pero se detecta una por error.     |
| Verdadero Negativo (VN) | No                          | No                    | El objeto no tiene falla y no se detecta ninguna falla.      |
| Falso Negativo (FN)     | Sí                          | No                    | El objeto tiene una falla, pero no se detecta la falla.      |

---

¿Cuál es el objetivo del Testing? #exam-question
?
- Encontrar fallas del producto de manera eficaz y eficiente.
	- Todo SW posee fallas
- Eficiente: Hacerlo más rápido y barato posible.
	- Mínima utilización de recursos: tiempo y costo.
- Eficaz:
	- Encontrar verdaderas fallas: no perder tiempo encontrando cosas que no son fallas o que tengan que ver con otras cosas y no compete al SW.
	- Encontrar la mayor # de fallas.
	- Encontrar las más importantes.
<!--SR:!2025-06-25,1,230-->

V o F. "No detectar fallas que en realidad no son" hace alusión a minimizar los falsos verdaderos.::F, hace alusión a minimizar los falsos positivos.
<!--SR:!2025-06-25,1,230-->

---

## ¿Por qué se producen fallas?

- Requerimientos poco claros. (1)
- Requerimientos incorrectos. (1)
- Requerimientos cambiantes. (1)
- Diseño Complejo.
- Desarrolladores sin experiencia.
- Lógica Complicada.
- Falta de tiempo.
- Falta de conocimiento del producto.
- Testers sin experiencia.
- Problemas del entorno o de sistemas.

> [!NOTE]
>
> 1. Si no tenemos definidos bien las épicas, de nada sirven las herramientas e IA.
> 2. Los demás puntos tienen que ver con nosotros mismos.

> [!NOTE]
>
> Usualmente es un cóctel y negligencia sistemática de varias partes.

---

Nombrar algunos motivos de por qué se producen fallas.
?
- Requerimientos:
	- Poco claros.
	- Incorrectos.
	- Cambiantes.
- Con nosotros mismos:
	- Diseño Complejo.
	- Desarrolladores sin experiencia.
	- Lógica Complicada.
	- Falta de tiempo.
	- Falta de conocimiento del producto.
	- Testers sin experiencia.
	- Problemas del entorno o de sistemas.
<!--SR:!2025-06-25,1,230-->

---

## ¿Qué es SW de Calidad?

- Aquel que cumpla con los requisitos.
- El que al ser usado NO tenga fallas.

> [!NOTE]
>
> Para esta parte nos abstraemos de la unidad [[05-visiones-de-la-calidad|visiones de calidad]].

---

¿Qué quiere decir que un SW sea de calidad?
?
- Aquel que cumpla con los requisitos.
- El que al ser usado NO tenga fallas.
<!--SR:!2025-06-25,1,230-->

---

## Aseguramiento de la calidad

- El aseguramiento de la calidad es un patrón planificado y sistemático de todas las acciones necesarias para brindar una adecuada confianza que un producto o componente cumple con los requerimientos técnicos establecidos.
- La Prueba del SW es una de las actividades involucradas en el Aseguramiento de Calidad.
- El SW, según algunos conceptos de Brooks:
	- **[[12-obl-but-i-only-changed-one-line-of-code|Engañosamente fácil de cambiar]] (causas y efectos)**.
	- Es un producto mental, no físico: no se rige por las leyes de la física.
	- Se desarrolla, no se fabrica: (1)
		- Mecanismo de replicación.
		- A medida vs. componentes.
		- La calidad no es en la producción sino el desarrollo.
	- Envejecimiento diferente: no se desgasta por el uso. (2)

> [!NOTE]
>
> 1. Comparándolo con la fabricación de un auto: luego del prototipo, se prueba, se manda a producirlo en serie para su venta. El foco se encuentra en el proceso de fabricación por sobre el prototipo.
> 	- En cambio, en el SW el "proceso de fabricación" es la primera vez que lo construimos. Luego es cuestión de ejecutarlo. El foco se encuentra en la primera vez que lo construimos.
> 	- El "aseguramiento de la calidad" permite que lo hagamos bien en esa "primera vez que lo construimos" y no que al llegar al final del camino nos demos cuenta recién que hicimos las cosas mal. Tener puntos de calidad que ayuden a darnos cuenta desde temprano de si estamos desarrollando las cosas correctamente.
> 2. No envejece, se degrada. Los errores pueden ser degradación y no por envejecimiento.

---

¿Qué es el aseguramiento de la calidad?
?
Es un patrón planificado y sistemático de todas las acciones necesarias para brindar una adecuada confianza que un producto o componente cumple con los requerimientos técnicos establecidos.
<!--SR:!2025-06-25,1,230-->

Es una de las actividades involucradas en el Aseguramiento de Calidad: ==1;;La Prueba del SW==.
<!--SR:!2025-06-25,1,230-->

Explicar el SW según algunos conceptos de Brooks.
?
- **Engañosamente fácil de cambiar (causas y efectos)**.
- Es un producto mental, no físico: no se rige por las leyes de la física.
- Se desarrolla, no se fabrica:
	- Mecanismo de replicación.
	- A medida vs. componentes.
	- La calidad no es en la producción sino el desarrollo.
- Envejecimiento diferente:
	- No se desgasta por el uso.
	- Errores pueden ser por degradación, no por envejecimiento.
<!--SR:!2025-06-25,1,230-->

A diferencia de un proceso de fabricación, en el SW, el foco se encuentra en ==1;;la primera vez que lo construimos==. Luego es cuestión de ejecutarlo.
<!--SR:!2025-06-25,1,230-->

El "aseguramiento de la calidad" permite que lo hagamos bien en esa ==1;;"primera vez que lo construimos"== y no que al llegar al final del camino nos demos cuenta recién que hicimos las cosas mal. Tener puntos de calidad que ayuden a darnos cuenta desde temprano de si estamos desarrollando las cosas correctamente.
<!--SR:!2025-06-25,1,230-->

---

## Paragua de SQA

![[01.2-paragua-sqa.png]]

SW Quality Assurance implica:

- Quality Assurance:
	- Tareas que realizamos ANTES de que el código exista.
	- Peer Review / Estático:
		- Código.
		- Documentos de diseño / approach.
		- Requerimientos:
			- Épicas (inclusive criterios de aceptación, criterios de prueba):
				- Observamos la importancia de tener la épica validada, ya que si la misma está mal => Todas las actividades que le siguen estarán mal.
				- Al realizar actividades de calidad sobre la épica, es una actividad de Quality Assurance.
			- Backlog.
		- Pruebas C&C.
	- "Estático":
		- NO estamos ejecutando código / NO estamos ejecutando el producto SW.
		- Estamos leyendo un documento, desarrollado una épica, trabajando sobre una herramienta.
	- Podemos detectarlo solamente revisando la definición de la épica.
	- **Es todo lo relacionado y lo que vemos NO-Runtime**.
- Quality Control:
	- Testing / Dinámico.
	- "Dinámico":
		- SI estamos ejecutando código / SI estamos ejecutando el producto SW.
		- Tenemos ya el código construido, compilado en un ejecutable.
		- Realizado en hitos de control para revisar que lo construido sea correcto.
		- Posterior a la construcción del SW y existencia del código.
	- Podemos detectarlo solamente ejecutando primero el producto SW.
	- **Es todo lo relacionado y lo que vemos Runtime**.

> [!IMPORTANT]
>
> - El punto clave para distinguir Quality Assurance de Quality Control es: lo vimos o no en Runtime.
> - No importa tanto lo que detectemos, e.g., "es una definición que debería estar en un requerimiento y es más visual que de ejecución".
> - SQA es agnóstico a los ambientes: Las actividades de calidad incurridas sobre las épicas (QA) son agnósticas a los ambientes, pueden existir mucho más previo a la existencia de un ambiente. Incluso, al tener un poco de código en funcionamiento (QC), dicho SW mínimo y viable, puede no encontrarse en un ambiente como staging y las pruebas se realizan desde la propia máquina del dev.

---

V o F. Las pruebas estáticas atacan fallas.::F, las pruebas estáticas atacan directamente el defecto, ya que no es posible ver las fallas debido a que no hay código en ejecución.
<!--SR:!2025-06-25,1,230-->

(Control U6) ¿Qué diferencias existen entre prueba estática y dinámica?
?
- Prueba estática:
	- Las actividades se encuentran asociadas al QA.
	- NO es necesario tener código en ejecución para poder llevarlas a cabo (tampoco tener código construido per sé).
	- ¿Qué analiza? Artefactos: código, documentación, modelos, entre otros.
- Prueba dinámica:
	- Las actividades se encuentran asociadas al QC.
	- SI es necesario tener código en ejecución para poder llevarlas a cabo.
	- ¿Qué analiza? Aspectos que solamente se pueden ser validados posterior a la ejecución del código, e.g., comportamiento en ejecución.
<!--SR:!2025-06-25,1,230-->

(Control U6) ¿Cuáles son las diferencias entre SQA, QA y QC?
?
SW Quality Assurance implica:
- Quality Assurance:
	- Tareas que realizamos ANTES de que el código exista.
	- Peer Review / Estático:
		- Código.
		- Documentos de diseño / approach.
		- Requerimientos:
			- Épicas (inclusive criterios de aceptación, criterios de prueba).
			- Backlog.
		- Pruebas C&C.
	- "Estático":
		- NO estamos ejecutando código.
		- Estamos leyendo un documento, desarrollado una épica, trabajando sobre una herramienta.
	- Podemos detectarlo solamente revisando la definición de la épica.
	- **Es todo lo relacionado y lo que vemos NO-Runtime**.
- Quality Control:
	- Testing / Dinámico.
	- "Dinámico":
		- SI estamos ejecutando código.
		- Tenemos ya el código construido, compilado en un ejecutable.
		- Realizado en hitos de control para revisar que lo construido sea correcto.
		- Posterior a la construcción del SW y existencia del código.
	- Podemos detectarlo solamente ejecutando primero el producto SW.
	- **Es todo lo relacionado y lo que vemos Runtime**.
- ![[01.2-paragua-sqa.png]]
<!--SR:!2025-06-25,1,230-->

V o F. SQA solamente ocurre en el ambiente de pruebas.::F, las actividades de calidad incurridas sobre las épicas (QA) son agnósticas a los ambientes, pueden existir mucho más previo a la existencia de un ambiente. Incluso, al tener un poco de código en funcionamiento (QC), dicho SW mínimo y viable, puede no encontrarse en un ambiente como staging y las pruebas se realizan desde la propia máquina del dev.
<!--SR:!2025-06-25,1,230-->

---

## Asegurar Vs Controlar la Calidad

- Una vez definidos los requerimientos de calidad tengo que tener en cuenta que:
	- La calidad no puede "inyectarse" al final.
	- La calidad del producto depende de tareas realizadas durante el proceso.
- Detectar errores en forma temprana ahorra esfuerzos, tiempo, recursos.
- SQA vs. Testing.

> [!TIP]
>
> - En la jerga de sistemas, llamamos erróneamente "QA" a "SQA", teniendo en mente solamente la parte de "QC".
> - Orígenes:
> 	- Generalmente dividimos en 2 mundos: desarrollo y calidad.
> 	- El mundo de la calidad suele mirar "calidad de proceso" y "calidad de producto", por lo que se le llama en la jerga "QA" directamente, pero hace ambas cosas.

---

V o F. Una vez definidos los requerimientos de calidad, la calidad es "inyectable" al final.::F, la calidad no puede "inyectarse" al final.
<!--SR:!2025-06-25,1,230-->

V o F. Una vez definidos los requerimientos de calidad, la calidad del producto depende de tareas realizadas durante el proceso.::V
<!--SR:!2025-06-25,1,230-->

Detectar errores en forma temprana ahorra ==1;;esfuerzos==, ==1;;tiempo==, ==1;;recursos==.
<!--SR:!2025-06-25,1,230-->

---

## Verificación y Validación

![[01.1-asegurar-vs-controlar-la-calidad.png]]

- Verificación:
	- Pregunta: ¿Estoy construyendo el producto correctamente?
	- Nos preguntamos si lo estamos haciendo bien desde la propia concepción del producto.
	- e.g., situación: en la épica dice que tenemos que tener un padding de 14px.
		- Nos equivocamos en el documento de diseño (Figma) y ponemos 13px.
		- El dev lo programa como 13px.
		- El paso de verificación en este caso deberíamos de haberla realizado entre la épica con el diseño. En este caso tuvimos un error en el puente entre la épica y el diseño.
		- Desde el punto de vista del dev, su verificación fue correcta y no hay nada que reprocharle.
		- Recordando la analogía con el proceso de fabricación, en el SW, la primera vez que lo estamos construyendo ya es el proceso de fabricación del SW, por lo que a dicho proceso hay ponerle todos los cañones.
	- Tipos de pruebas que mejor calzan:
		- Unitarios: Nos permite saber si el código funciona correctamente, en base a las reglas de negocio detalladas en la épica (criterios de aceptación).
		- Integración.
- Validación:
	- Pregunta: ¿Estoy construyendo el producto correcto?
	- Nos preguntamos si estamos construyendo algo que el usuario o cliente necesita.
	- Tipos de pruebas que mejor calzan:
		- UAT: pruebas del usuario final: nos lo dirá el usuario si el producto siendo construido es el correcto.
		- UI / UX.
- Grises entre ambos: Pruebas de [[08-tipos-de-prueba#Prueba de regresión|regresión]] y de sistema.

> [!NOTE]
>
> - Si bien pudimos haber construido el producto correctamente, siguiendo tal cual los requerimientos, diseño, etc.
> - Luego resulta que en la etapa de validación nos dice el cliente que no es lo que deseaba.
> - Si nos basamos pura y exclusivamente en nuestro proceso: está todo bien, pero al usuario no le sirve.
> - Algo tuvimos que haber hecho mal: capturar o definir mal los requerimientos, le entendimos mal al cliente, etc., en definitiva nos equivocamos en algún paso.
> - Por este motivo debe haber alguien de negocio / producto metido.

---

(Control U6) ¿Cuáles son las diferencias entre validación y verificación?
?
- Verificación:
	- Pregunta: ¿Estoy construyendo el producto correctamente?
	- Nos preguntamos si lo estamos haciendo bien desde la propia concepción del producto.
	- e.g., situación: en la épica dice que tenemos que tener un padding de 14px.
		- Nos equivocamos en el documento de diseño (Figma) y ponemos 13px.
		- El dev lo programa como 13px.
		- El paso de verificación en este caso deberíamos de haberla realizado entre la épica con el diseño. En este caso tuvimos un error en el puente entre la épica y el diseño.
		- Desde el punto de vista del dev, su verificación fue correcta y no hay nada que reprocharle.
		- Recordando la analogía con el proceso de fabricación, en el SW, la primera vez que lo estamos construyendo ya es el proceso de fabricación del SW, por lo que a dicho proceso hay ponerle todos los cañones.
	- Tipos de pruebas que mejor calzan:
		- Unitarios: Nos permite saber si el código funciona correctamente, en base a las reglas de negocio detalladas en la épica (criterios de aceptación).
		- Integración.
- Validación:
	- Pregunta: ¿Estoy construyendo el producto correcto?
	- Nos preguntamos si estamos construyendo algo que el usuario o cliente necesita.
	- Tipos de pruebas que mejor calzan:
		- UAT: pruebas del usuario final: nos lo dirá el usuario si el producto siendo construido es el correcto.
		- UI / UX.
- Grises entre ambos: Pruebas de regresión y de sistema.
- ![[01.1-asegurar-vs-controlar-la-calidad.png]]
<!--SR:!2025-06-25,1,230-->

---
