---
tags:
- flashcards/swe/teoria/1P
- flashcards/swe/teoria/U4
---

# Métodos de estimación

- Es posible emplear distintos métodos de estimación en distintas etapas de un mismo proyecto.
- e.g., emplear método por analogía (juicio de experto), uno paramétrico para estimar y luego una especie de _Wideband Delphi_ ya que consulta a los expertos de cada sistema.

> [!IMPORTANT]
>
> - Los Métodos de Estimación nos brindan una **unidad de tamaño**.
> - Posteriormente hay que seguir el [[01-conceptos-de-estimaciones-de-sw#Ciclo (dorado) de estimación|ciclo dorado de estimación]], a partir del tamaño.
> - Al momento de medir "Tamaño":
> 	- Ya sabemos lo que tenemos que hacer ("Requerimientos").
> 	- No nos importa todavía quién lo llevará a cabo, si será en forma paralela, si será un equipo de expertos o de Juniors.
> 	- Si alguien es más experto que otro: En todo caso dicha persona lo hará más rápido en términos de "Duración", pero el "Tamaño" es el mismo para todos.
> - El "Tamaño" siempre es el mismo.
> - Tamaño -> Esfuerzo: Pasamos a horas-hombres.
> - Hacerlo en paralelo puede aumentar la complejidad en caso de necesitar mucha coordinación entre los equipos y hay que tenerlo en cuenta.

---

V o F. No es posible emplear distintos métodos de estimación en distintas etapas de un mismo proyecto.::F. Según las etapas del proyecto, puede convenirnos más un método que otro, e.g., emplear método por analogía (juicio de experto), uno paramétrico para estimar y luego una especie de _Wideband Delphi_ ya que consulta a los expertos de cada sistema.

---

## Métodos rudimentarios

- Caracterizado por: Emplear experiencias previas del equipo o el juicio de los expertos.
- Busca: Establecer analogías con proyectos anteriores y lograr el consenso grupal.
- Ventajas: Rápida, flexible y útil cuando hay poca información detallada.
- Desventajas: Puede ser subjetiva, depende de la experiencia y puede estar sesgada.
- Es posible comenzar las primeras estimaciones con éstos para luego poder transicionar y calibrar los métodos paramétricos, a medida que se dispone de más información.

- [[03-juicio-experto|Juicio Experto]].
- [[04-pert|PERT]].
- [[05-wideband-delphi|Wideband Delphi]].
- [[06-planning-poker|Planning Poker]].
- [[07-rec-tecnicas-agiles-metodos-rudimentarios-agile-no-vistas-en-clase|Métodos Agile Rudimentarios que no se trataron en clases]]:
	- [[07-rec-tecnicas-agiles-metodos-rudimentarios-agile-no-vistas-en-clase#T-Shirt Sizes|T-Shirt Sizing]].
	- [[07-rec-tecnicas-agiles-metodos-rudimentarios-agile-no-vistas-en-clase#Puntos de Votación (Dot Voting)|Puntos de votación (Dot Voting)]].
	- [[07-rec-tecnicas-agiles-metodos-rudimentarios-agile-no-vistas-en-clase#Sistema de Cubetas (The Bucket System)|Sistema de cubetas (The Bucket System)]].
	- [[07-rec-tecnicas-agiles-metodos-rudimentarios-agile-no-vistas-en-clase#Grande/Indeciso/Pequeño (Large/Uncertain/Small)|Grande/Indeciso/Pequeño (Large/Uncertain/Small)]].

---

(Control U4) ¿Qué diferencia hay entre los métodos de Juicio Experto, PERT y Wideband Delphi?
?
- Juicio Experto: Se basa en el juicio de una única persona (experto).
- PERT: Es el único de los métodos rudimentarios vistas que se emplea una cuenta matemática, el cuál considera factores optimistas y pesimistas para el cálculo de la estimación. La misma puede ser empleada también para estimar Esfuerzo (en vez de Tamaño) y también puede ser en forma grupal.
- Wideband Delphi: Se basa en el juicio consensuado de un grupo de personas (expertos).

---

## Métodos paramétricos

- Caracterizado por: Emplear modelos matemáticos o estadísticos, parámetros y variables para calcular las estimaciones.
- Busca: Registrar métricas objetivas (líneas de código, function points, story points, etc.).
- Ventajas: Más objetiva, reproducible y escalable.
- Desventajas: Requiere datos históricos confiables y suele ser más compleja de aplicar en caso de no tenerlos disponibles.

- [[08-object-points|Object Points]].
- [[09-function-points|Function Points]].
- [[10-use-case-points|Use Case Points]].

> [!IMPORTANT]
>
> Tipos de ejercicios:
> - Schivo aclaró que como mucho nos podrán dar las tablas y nos pedirá calcular los Function Points. Si bien solamente aclaró "Function Points", se sospecha que puede que se pidan las otras también.
> - Nos dan un contexto y nos piden definir el método de estimación a emplear, en qué contexto se encuentra, qué approach emplear. Justificar para todas.
> - En caso de que nos pregunten por "Entradas y salidas de los métodos", las entradas son los tipos de elementos para cada método paramétrico y las salidas son siempre Tamaño en las unidades que correspondan (X Points).

---

(Control U4) ¿Cómo se dividen los métodos de estimación? ¿Qué características tiene cada grupo?
?
- Métodos rudimentarios:
	- Caracterizado por: Emplear experiencias previas del equipo o el juicio de los expertos.
	- Busca: Establecer analogías con proyectos anteriores y lograr el consenso grupal.
	- Ventajas: Rápida, flexible y útil cuando hay poca información detallada.
	- Desventajas: Puede ser subjetiva, depende de la experiencia y puede estar sesgada.
	- Es posible comenzar las primeras estimaciones con éstos para luego poder transicionar y calibrar los métodos paramétricos, a medida que se dispone de más información.
- Métodos paramétricos:
	- Caracterizado por: Emplear modelos matemáticos o estadísticos, parámetros y variables para calcular las estimaciones.
	- Busca: Registrar métricas objetivas (líneas de código, function points, story points, etc.).
	- Ventajas: Más objetiva, reproducible y escalable.
	- Desventajas: Requiere datos históricos confiables y suele ser más compleja de aplicar en caso de no tenerlos disponibles.

(Control U4) ¿Cuándo conviene utilizar un método como Planning Poker y cuándo uno como Use Case Point?
?
- Planning Poker:
	- Conviene utilizarlo en proyectos ongoing o desarrollo incremental a largo plazo.
	- No tanto para primeras estimaciones o desarrollos de 0-100% en corto tiempo.
	- Si bien no es idóneo en situaciones en donde no se tenga una tarea de referencia (para aplicar el método debe existir una tarea de referencia), podemos iniciar con una estimación arbitraria. Posteriormente, se mide el resultado y se vuelve a calibrar la estimación.
- Use Case Point:
	- Conviene utilizarlo cuando ya tenemos histórico respecto a:
		- Cantidad y complejidad de los casos de uso.
		- Cantidad y complejidad de los actores intervinientes en el sistema.
		- Factores técnicos y ambientales.
	- El método requiere que sea posible contar el número de transacciones en cada caso de uso.
	- A inicios de nuevos proyectos o cuando el histórico no está disponible:
		- La aplicación de algún método paramétrico para comenzar a medir "Tamaño", es más complejo y probablemente tengamos que tener varias pasadas por el ciclo dorado antes de que nuestra estimación sea aceptable.

---
