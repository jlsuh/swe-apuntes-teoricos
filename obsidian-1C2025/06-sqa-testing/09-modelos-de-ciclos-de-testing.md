---
tags:
- flashcards/swe/teoria/2P
---

# Modelos de Ciclos de Testing

## Clasificación de las pruebas

- Por el conocimiento:
	- Caja blanca.
	- Caja negra.
	- Caja gris: es hacer caja negra pero en alguno de los componentes hacer caja blanca.
		- e.g., para un carrito de compras, hacemos caja negra, pero al momento de realizar la compra hacemos caja blanca, ya que es un momento crítico del carrito.
		- Es una estrategia / enfoque de prueba.
		- e.g., si optamos en hacer caja blanca, pero en nuestro código tenemos una API de terceros, debido a que no tenemos el código de dicha API, no podremos hacer caja blanca de dicha API de punta a punta. Parte podremos hacer caja blanca y parte debemos hacer caja negra si o si, por más que seamos proficientes en el lenguaje, debido a que no lo tenemos a disposición nuestra el código.
- Por el tipo de ejecución:
	- Automatizadas.
	- Manuales.
	- Semi-automatizadas.
- Por el tipo de prueba:
	- Funcionales: algo que hace al SW.
	- No Funcionales: algo que hace a la utilización o el complemento del SW.
		- e.g., prueba de stress.
- Por el alcance o nivel:
	- Unitarias.
	- De integración.
	- De sistemas.
	- De aceptación de usuario.

> [!NOTE]
>
> Podemos clasificar las pruebas de cualquier combinación posible.

![[09.1-sw-testing-abilities.png]]

> [!NOTE]
>
> Son las distintas "habilidades" que debe poseer el tester.

---

Clasificar las pruebas.
?
- Por el conocimiento:
	- Caja blanca.
	- Caja negra.
	- Caja gris: es hacer caja negra pero en alguno de los componentes hacer caja blanca.
		- e.g., para un carrito de compras, hacemos caja negra, pero al momento de realizar la compra hacemos caja blanca, ya que es un momento crítico del carrito.
		- Es una estrategia / enfoque de prueba.
		- e.g., si optamos en hacer caja blanca, pero en nuestro código tenemos una API de terceros, debido a que no tenemos el código de dicha API, no podremos hacer caja blanca de dicha API de punta a punta. Parte podremos hacer caja blanca y parte debemos hacer caja negra si o si, por más que seamos proficientes en el lenguaje, debido a que no lo tenemos a disposición nuestra el código.
- Por el tipo de ejecución:
	- Automatizadas.
	- Manuales.
	- Semi-automatizadas.
- Por el tipo de prueba:
	- Funcionales: algo que hace al SW.
	- No Funcionales: algo que hace a la utilización o el complemento del SW.
		- e.g., prueba de stress.
- Por el alcance o nivel:
	- Unitarias.
	- De integración.
	- De sistemas.
	- De aceptación de usuario.
<!--SR:!2025-06-25,1,230-->

V o F. Es posible clasificar las pruebas en base a cualquier combinación posible.::V
<!--SR:!2025-06-25,1,230-->

¿Cuáles son las habilidades del testing de SW?
?
- Test Management.
- Functionality Testing.
- UX Testing.
- Performance & Load Testing.
- Compatibility Testing.
- Security Testing.
<!--SR:!2025-06-25,1,230-->

---

## Pirámide del Testing

![[09.2-piramide-del-testing.png]]

> [!NOTE]
>
> - Contesta la pregunta de cuánto nos cuesta o esfuerzo incurre en automatizar una prueba Vs. el tiempo de hacer la automatización.
> 	- Unit tests: bajo costo/esfuerzo y bajo tiempo. Son candidatos a realizar automatizaciones sobre estas. Esto es porque al codificar el código, podemos directamente realizar las pruebas unitarias, son acceso sencillo.
> 	- Component Tests: posee un mayor costo/esfuerzo e incurre un poco más de tiempo que los tests unitarios. En este caso juntamos varias funciones o procesos, ya que cada uno de estos componentes que son invocados en otro componente "cliente de los códigos".
> 	- Integration Tests: mayor que antes ya que estamos conectándonos con un componente de 3° o de otro equipo.
> 	- API Tests: quizás necesite coordinar con otro equipo que maneje las APIs.
> 	- Functional Tests (GUI): es el más cercano a los usuarios y de alguna forma se relaciona con el costo de fallas ante el usuario.
> - No siempre la automatización hará que ganemos tiempo como retorno de inversión.

> [!NOTE]
>
> Se preguntó en clase si esta pirámide es la "Pirámide de Testing de Mike Cohn", pero los profesores no supieron contestarlo. Se sospecha que si en base a otros resúmenes, pero no se dio una afirmación certera.

---

¿En qué consiste la pirámide del Testing?
?
Contesta la pregunta de cuánto nos cuesta o esfuerzo incurre en automatizar una prueba Vs. el tiempo de hacer la automatización.
<!--SR:!2025-06-25,1,230-->

Nombrar los segmentos de la pirámide de Testing en orden creciente de esfuerzo de automatización.
?
- Unit Tests: devs.
	- Bajo costo/esfuerzo y bajo tiempo.
	- Son candidatos a realizar automatizaciones sobre estas. Esto es porque al codificar el código, podemos directamente realizar las pruebas unitarias, son acceso sencillo.
- Component Tests: devs.
	- Posee un mayor costo/esfuerzo e incurre un poco más de tiempo que los tests unitarios.
	- En este caso juntamos varias funciones o procesos, ya que cada uno de estos componentes que son invocados en otro componente "cliente de los códigos".
- Integration Tests: devs.
	- Mayor que antes ya que estamos conectándonos con un componente de 3° o de otro equipo.
- API Tests: devs & QA.
	- Quizás necesite coordinar con otro equipo que maneje las APIs.
- Functional Tests (GUI): devs & QA.
	- Es el más cercano a los usuarios y de alguna forma se relaciona con el costo de fallas ante el usuario.
<!--SR:!2025-06-25,1,230-->

V o F. La automatización siempre hará que ganemos tiempo como retorno de inversión.::F, no siempre.
<!--SR:!2025-06-25,1,230-->

---

## Modelo de Ciclo de Vida V de Testing

![[09.3-modelo-de-ciclo-de-vida-V-en-testing.png]]

> [!NOTE]
>
> - Abarca desde el nace la idea desde los requerimientos hasta que el usuario nos confirma que efectivamente es lo que esperaba.
> - Desde el momento en que el usuario nos cuenta lo que necesita, ya que podemos pensar en cómo lo va a probar.
> 	- Ya podemos armar un "criterio de prueba de aceptación de usuario": en metodologías ágiles lo conocemos como "criterios de aceptación".
> 	- Por ende, los primeros casos de prueba que podemos generar son el Plan de Aceptación del Usuario.
> - Desde el momento en que comenzamos a pensar en el diseño del SW, ya podemos pensar si tenemos que conectarnos con otro sistema => Armamos un plan de pruebas de sistema.
> - Así con las etapas subsiguientes.

> [!IMPORTANT]
>
> - El modelo de ciclo de vida V en Testing nos marca que, para poder hacer Testing, no hace falta tener código. El Testing es posible realizarlo desde el momento inicial en donde recibimos los requerimientos.
> - Son actividades de [[01-conceptos-generales#Paragua de SQA|Quality Assurance]]: garantizamos la calidad previo a la ejecución del SW.
> - Este ciclo de vida son una perspectiva que tenemos que adoptar a la hora de que nuestro equipo deja de ser la coordinación de una única célula de Scrum, sino que de 15 células de Scrum.

---

¿Para hacer Testing es necesario tener código? #exam-question
?
No es necesario, existe el modelo de ciclo de vida V en Testing, en donde es posible tener, en cada una de las etapas de construcción de SW, una versión asociada para el Testing. Las mismas son:
- Acceptance Testing.
- System Testing.
- Integration Testing.
- Unit Testing.
<!--SR:!2025-06-25,1,230-->

V o F. El Testing es posible realizarlo desde el momento inicial en donde recibimos los requerimientos.::V
<!--SR:!2025-06-25,1,230-->

(Control U6) ¿Cuál es la idea del V-Model?
?
La idea del V-Model es reflejar que:
- Cada actividad previo a la construcción del SW, posee una actividad asociada al Testing.
- No es necesario tener código para hacer Testing y dichas actividades son parte del SQA, más no son parte del QC, sino que del QA.
<!--SR:!2025-06-25,1,230-->

---

## Cuadrantes, niveles y tipos de testing

![[09.4-cuadrantes-niveles-y-tipos-de-testing.png]]

> [!NOTE]
>
> Es posible orientar al Testing según distintas visiones:
> - Negocio.
> - Producto.
> - Tecnología.
> - Soporte al equipo.
>
> Cuadrantes:
> - Q1: Son tests que podemos resolver la parte técnica => Automatizadas.
> - Q2: El negocio pide que se ejecuten pero son generados por el equipo => Un poco automatizadas y un poco manuales, e.g., pruebas de usuario, pruebas de historia, etc.
> - Q3: Manuales por definición.
> - Q4: Semiautomatizadas con alguna herramienta que nos acompañe para ver cómo responde el producto, e.g., pruebas de stress / volumen /seguridad/ etc. y vemos cómo responde el producto.
>
> Los cuadrantes denotan si conviene o no automatizar, utilizar una herramienta.

---

Desarrollar los cuadrantes del testing.
?
![[09.4-cuadrantes-niveles-y-tipos-de-testing.png]]
<!--SR:!2025-06-25,1,230-->

---

## Agile Testing

![[09.5-agile-testing-tdd.png]]

Pros:
- Aplicaciones más modulares, flexibles y escalables.
- Código menos acoplado y más mantenible.
- El codificador puede hacer refactoring en cualquier momento con bajo riesgo.
- Soporta la regresión de bugs.
- Mejor cobertura de código.

Cons:
- Similares errores en el código y en el test case.
- Algunas funcionalidades son difíciles de probar con estos tests.
- Mantenimiento de los tests.
- Puede llevar a un falso nivel de confianza sobre la calidad del código.

> [!NOTE]
>
> - TDD: Propone que, en vez de que el código sea el driver de los casos de prueba, que los casos de prueba sean el driver del código.
> - Pasos:
> 	1. Escribir el tests y que rompa.
> 	2. Escribir el código que haga funcionar el test.
> 	3. Escribo el siguiente test -> Vuelvo a 1.
> - Pasa algo similar a DevOps: el equipo de construcción es el mismo equipo que el de testing.
> - Una de las técnicas con las que se combina el TDD es el [[06-obl-qa-when-two-eyes-arent-enough#Pair Programming|Pair Programming]]:
> 	- Mientras uno piensa el código, el otro piensa cómo probar el código.

---

¿Cuáles son las ventajas del Agile Testing?
?
- Aplicaciones más modulares, flexibles y escalables.
- Código menos acoplado y más mantenible.
- El codificador puede hacer refactoring en cualquier momento con bajo riesgo.
- Soporta la regresión de bugs.
- Mejor cobertura de código.
<!--SR:!2025-06-25,1,230-->

¿Cuáles son las desventajas del Agile Testing?
?
- Similares errores en el código y en el test case.
- Algunas funcionalidades son difíciles de probar con estos tests.
- Mantenimiento de los tests.
- Puede llevar a un falso nivel de confianza sobre la calidad del código.
<!--SR:!2025-06-25,1,230-->

V o F. El TDD propone que, en vez de que el código sea el driver de los casos de prueba, que los casos de prueba sean el driver del código.::V
<!--SR:!2025-06-25,1,230-->

¿Cuáles son los pasos del TDD?
?
1. Escribir el tests y que rompa.
2. Escribir el código que haga funcionar el test.
3. Escribo el siguiente test -> Vuelvo a 1.
<!--SR:!2025-06-25,1,230-->

Una de las técnicas con las que se combina el TDD es el ==1;;Pair Programming== ==1;;(mientras uno piensa el código, el otro piensa cómo probar el código)==.
<!--SR:!2025-06-25,1,230-->

---
