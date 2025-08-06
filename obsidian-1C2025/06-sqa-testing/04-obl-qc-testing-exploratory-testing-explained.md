---
tags:
- flashcards/swe/teoria/2P
---

#exam-question 

# Exploratory Testing Explained

> Hasta ahora vimos un testing bien estructurado, bien formulado, con requerimientos y premisas bien claras.

---

(Control U6) ¿En qué consiste el testing exploratorio?
?
- ET es una técnica de prueba de SW en la que el tester diseña, ejecuta y analiza las pruebas de manera simultánea, en lugar de seguir un conjunto de casos de prueba previamente definidos.
- En ET, el conocimiento, la creatividad y la experiencia del tester guían el proceso, permitiendo descubrir defectos que podrían pasar desapercibidos con pruebas más estructuradas.
<!--SR:!2025-06-25,1,230-->

---

## Un approach poderoso y flexible del SW Testing

- Todavía malentendida y subestimada.
- En ciertos contextos, puede ser mucho más productiva que las pruebas guiadas por scripts.
- De alguna forma, todos los testers practican ET. No se practica ET <=> Desde el vamos no creamos pruebas.
- Pocos estudian esta aproximación formalmente y no es muy respetada.
	- Ausencia de mención en textos de SW Testing: Si bien el concepto de la ET es simple, puede transmitir la sensación de que no posee estructura definida. La realidad es que ET puede ser tan disciplinado como cualquier otra actividad intelectual.
	- Esta actitud está cambiando ante la mayor adopción por la agilidad y métodos del desarrollo de SW _cost-effective_.

---

ET es un approach ==1;;poderoso== y ==1;;flexible== del SW Testing.
<!--SR:!2025-06-25,1,230-->

---

### Scripting

- Quiere decir un "guion".
	- e.g., "dado X, cuando toco en Y botón, etc."
- Un lenguaje posible sería Gherkin.

## Explicar algo que ya todos saben

- El autor cuenta que una de las cosas más difíciles de explicar es explicar algo que ya todos saben.
- ET es lo mismo que escuchar, leer, pensar y cómo contar anécdotas de vivencias propias.
- Lo que hace al ET interesante e importante es que cuando un tester posee las habilidades de escuchar, leer, pensar y reportar, rigurosa y efectivamente, sin el empleo del scripting, el approach exploratorio al testing puede ser varias veces más productivo (en términos de revelar información vital) que su alternativa del scripting.
- En caso de ser correctamente supervisado y esquematizado, es posible obtener resultados que posiblemente no hayan sido anticipados por un script.

> [!IMPORTANT]
>
> ET depende de la calidad de los testers que tengamos.

---

V o F. ET depende de la calidad de los testers que tengamos.::V
<!--SR:!2025-06-25,1,230-->

V o F. ET es lo mismo que escuchar, leer, pensar y cómo contar anécdotas de vivencias propias.::V
<!--SR:!2025-06-25,1,230-->

---

## Conocido originalmente como Ad hoc Testing

- Desafortunadamente, _Ad hoc_ es usualmente sinónimo de de "trabajo descuidado y negligente".
- En su lugar, un grupo de metodólogos del Testing (_Context-Driven School_) acuñaron el término "exploratorio" (publicado primera vez por Cem Kaner).

## No es una contraposición del scripting

- En algunos contextos, lograremos la misión del testing mediante el scripting.
- En otros contextos, nuestra misión obtendrá un mayor beneficio de la habilidad de poder crear y mejorar pruebas a medida que las ejecutamos.
- En la mayoría de los casos el beneficio se obtiene debido a una mezcla entre los approaches del scripting y la exploración.
- Se busca maximizar el uso de las habilidades por sobre el esfuerzo de querer representar toda acción en forma escrita.

> [!IMPORTANT]
>
> ET nos permite salir un poco de la estructura de los tests scripteados.

---

V o F. ET no es una contraposición al scripting.::V, en la mayoría de los casos el beneficio se obtiene debido a una mezcla entre los approaches del scripting y la exploración.
<!--SR:!2025-06-25,1,230-->

---

## Aprendizaje, diseño de pruebas y ejecución de pruebas, todo en simultáneo

- En otras palabras, es cualquier tipo de testing en la medida que el tester activamente:
	- Controle el diseño de las pruebas.
	- Realice las pruebas.
	- Emplee la información obtenida durante las pruebas.
- Con la finalidad de diseñar más y mejores pruebas.

- Desde esta perspectiva, virtualmente todas las pruebas realizadas por testers humanos son exploratorias hasta cierto grado.
- Esto evidencia que ET es un proceso mental que varios testers adoptan. La pregunta "¿Estás haciendo ET?", es mejor planteado de la forma "¿De qué formas y hasta qué grado son tus pruebas exploratorias?".

---

En ET, ==1;;el aprendizaje==, ==1;;diseño de pruebas== y ==1;;ejecución de pruebas== se da todo en simultáneo.
<!--SR:!2025-06-25,1,230-->

ET es cualquier tipo de Testing en la medida que el tester activamente controle ==1;;el diseño== de las pruebas, ==1;;ejecute== las pruebas y emplee la ==1;;información obtenida== durante las pruebas, con la finalidad de diseñar ==1;;más y mejores== pruebas.
<!--SR:!2025-06-25,1,230-->

---

### Freestyle ET

- Pruebas que son puras o muy cercanas (que de ser completamente guiadas por scripts) a puramente exploratorias.
- En otras palabras, pruebas que cumplen sustancialmente con la definición de ET antemencionada.

## ET es una práctica situacional en su completitud

- Si alguna vez en la vida hemos armado un rompecabezas => Hemos practicado ET.
	- Es absurdo y complejo intentar cuidadosamente documentar estos procesos mentales de antemano.
- El proceso _fluye_ y se mantiene continuo, _en cada momento_, bajo el control del practicante.
- Núcleo del ET: "El rompecabezas modifica el _acto de armar el rompecabezas_". Los detalles del rompecabezas emergen mediante el proceso de armado del rompecabezas, el cuál influye sobre las tácticas de resolución.

---

ET es una práctica ==1;;situacional== en su completitud. El proceso _fluye_ y se mantiene continuo, _en cada momento_, bajo el control del practicante.
<!--SR:!2025-06-25,1,230-->

Hemos practicado ET si alguna vez en la vida hemos armado un ==1;;rompecabezas==.
<!--SR:!2025-06-25,1,230-->

El ==1;;rompecabezas== modifica el ==1;;acto de armar== el rompecabezas.
<!--SR:!2025-06-25,1,230-->

---

## Aspectos específicos que afectan al ET

Algunos de los mismos:

- La misión del proyecto de pruebas.
- La misión de esta sesión de pruebas en particular.
- El rol del tester.
- El tester (sus habilidades, talentos y preferencias).
- Herramientas e instalaciones disponibles.
- Tiempo disponible.
- Datos y materiales de prueba disponibles.
- Ayuda disponible de otras personas.
- Accountability requirements.
- Qué es importante para los clientes.
- La estrategia de pruebas actual.
- El estado de otros esfuerzos de pruebas sobre el mismo producto.
- El producto en sí:
	- Su UI.
	- Su comportamiento.
	- Su estado de ejecución actual.
	- Sus defectos.
	- Su testeabilidad.
	- Su propósito.
- Lo que el tester conoce del producto:
	- Qué ocurrió en la prueba anterior.
	- Problemas conocidos.
	- Problemas pasados.
	- Fortalezas y debilidades.
	- Áreas de riesgo y magnitud del riesgo percibido.
	- Cambios recientes en el producto.
	- Observaciones directas.
	- Rumores sobre el producto.
	- Naturaleza de los usuarios y su comportamiento.
	- Cómo se supone que debe funcionar.
	- Cómo está construido.
	- En qué se parece o difiere de otros productos.
- Qué le gustaría saber al tester sobre el producto.

> [!NOTE]
>
> - "¿Cuál test ejecutar?" Vs. ET: "¿Cuál es el mejor test que puedo realizar ahora mismo?"
> - Pueden afectar el "qué test es requerido".
> - Cambian continuamente a lo largo del proyecto de pruebas o incluso de un momento a otro durante una sesión de test.
> - ET puede ser optimizado por el proceso de testing.
> - Mientras que los scripts suelen volverse menos potentes en el transcurso del tiempo, ya que no sufren cambios.
> 	- Motivos principales: Una vez que se ejecuta y se encuentra un problema, las chances de encontrar otros problemas en siguientes ejecuciones es, en la mayoría de los casos, sustancialmente más bajo, en comparación a si ejecutásemos un test completamente nuevo.

---

¿Cuáles son algunos aspectos específicos que afecta el ET?
?
- La misión del proyecto de pruebas.
- La misión de esta sesión de pruebas en particular.
- El rol del tester.
- El tester (sus habilidades, talentos y preferencias).
- Herramientas e instalaciones disponibles.
- Tiempo disponible.
- Datos y materiales de prueba disponibles.
- Ayuda disponible de otras personas.
- Accountability requirements.
- Qué es importante para los clientes.
- La estrategia de pruebas actual.
- El estado de otros esfuerzos de pruebas sobre el mismo producto.
- El producto en sí:
	- Su UI.
	- Su comportamiento.
	- Su estado de ejecución actual.
	- Sus defectos.
	- Su testeabilidad.
	- Su propósito.
- Lo que el tester conoce del producto:
	- Qué ocurrió en la prueba anterior.
	- Problemas conocidos.
	- Problemas pasados.
	- Fortalezas y debilidades.
	- Áreas de riesgo y magnitud del riesgo percibido.
	- Cambios recientes en el producto.
	- Observaciones directas.
	- Rumores sobre el producto.
	- Naturaleza de los usuarios y su comportamiento.
	- Cómo se supone que debe funcionar.
	- Cómo está construido.
	- En qué se parece o difiere de otros productos.
- Qué le gustaría saber al tester sobre el producto.
<!--SR:!2025-06-25,1,230-->

ET puede ser optimizado por el ==1;;proceso de testing==.
<!--SR:!2025-06-25,1,230-->

V o F. Los scripts suelen volverse menos potentes en el transcurso del tiempo, ya que no sufren cambios.::V, una vez que se ejecuta y se encuentra un problema, las chances de encontrar otros problemas en siguientes ejecuciones es, en la mayoría de los casos, sustancialmente más bajo, en comparación a si ejecutásemos un test completamente nuevo.
<!--SR:!2025-06-25,1,230-->

---

## ET en la práctica

### Charters

- Una sesión ET usualmente comienza con un charter, el cual indica:
	- La misión.
	- Tácticas a adoptar.
- Es asignado por el test manager, TL o bien seleccionado por el propio tester.
- En algunas organizaciones, los casos de prueba y procedimientos son documentados muy a la ligera que en esencia sirven como charters para el ET.
- Pueden resultar ambiguos ya que buscan comunicar la misión de una sesión de pruebas en forma clara y concisa a testers que ya poseen el entrenamiento de las expectativas, vocabulario, técnicas y herramientas empleadas por la organización.
- Algunos ejemplos de testing charters para la aplicación "DecideRight":
	- Explorar y analizar los elementos del producto "DecideRight". Elaborar un esquema de cobertura de pruebas.
	- Identificar y probar todas las afirmaciones (_claims_) del manual de "DecideRight" (emplear marcas de "verificación/X/?" en el manual impreso, o listar cada afirmación probada en las notas).
	- Definir flujos de trabajo a través de "DecideRight" y probar cada uno. Los flujos deben representar escenarios realistas de uso y, en conjunto, cubrir cada función principal del producto.
	- Probar todos los campos que permiten ingreso de datos (funcionalidad, estrés y límites, por favor).
	- Verificar la interfaz de usuario contra los estándares de interfaz de Windows.
	- ¿Hay alguna forma de corromper un archivo? ¿Cómo saber si está corrupto? Investigar la viabilidad de crear un verificador automático de archivos. Averiguar si ya existe algo implementado por los devs.
	- Ejecutar "DecideRight" bajo "AppVerifier" y reportar cualquier error.

> [!IMPORTANT]
>
> - ET posee un plan inicial (charters) (no llega a ser del nivel scripting).
> - El plan no es fijo, a medida que vamos aprendiendo y probando, vamos adaptando nuestro plan.

---

¿Qué es un charter y para qué sirve?
?
- Es un plan inicial del ET, que no llega a ser del nivel scripting.
- Sirve para indicar la misión y tácticas a adoptar durante una sesión ET.
- El plan no es fijo, a medida que vamos aprendiendo y probando, vamos adaptando nuestro plan.
- Pueden resultar ambiguos ya que buscan comunicar la misión de una sesión de pruebas en forma clara y concisa a testers que ya poseen el entrenamiento de las expectativas, vocabulario, técnicas y herramientas empleadas por la organización.
<!--SR:!2025-06-25,1,230-->

---

### Estructura externa ET

- Durante un período de _tiempo_, un _tester_ interactúa con un _producto_ para cumplir una _misión_ de testing e _informar_ resultados.
- Entonces, los elementos básicos externos del ET son:
	- Tiempo.
	- Tester.
	- Producto.
	- Misión.
	- Informe.

---

¿Cuáles son los elementos básicos externos del ET?
?
- Tiempo.
- Tester.
- Producto.
- Misión.
- Informe.
<!--SR:!2025-06-25,1,230-->

---

### Estructura interna ET

#### Lo que más importa: Lo que ocurre dentro de la mente del tester

- Acá es en donde un ET fracasa o resulta exitoso: distinción de un excelente explorador vs. amateur.
- Algunos de los principios básicos respecto a un explorador de pruebas:
	- Diseño de pruebas:
		- Ante todo, es un diseñador de pruebas.
		- Capaz de crear pruebas que exploran el producto de manera sistemática.
		- Requiere habilidades como la capacidad de analizar un producto, evaluar riesgos, usar herramientas y pensar críticamente, entre otras.
	- Observación cuidadosa:
		- Observadores más atentos que los novatos o incluso que testers experimentados que siguen scripts.
			- Los scripters solo observan lo que el script le indica que observe.
			- El explorador debe estar atento a cualquier cosa inusual o misteriosa.
		- Deben ser cuidadosos en distinguir la observación de la inferencia y no permiten que supuestos preconcebidos los cieguen ante pruebas o comportamientos importantes del producto.
	- Pensamiento crítico:
		- Capaces de revisar y explicar su lógica, buscando errores en su propio razonamiento.
		- Esto es especialmente importante al reportar el estado de una sesión de pruebas exploratorias o al investigar un defecto.
	- Diversidad de ideas:
		- Generan más y mejores ideas que los novatos.
		- Pueden [[05-obl-qc-using-heuristic-test-oracles|utilizar heurísticas]] para lograr esto: Dispositivos mentales como guías, listas de verificación genéricas, mnemotécnicos o reglas prácticas.
		- La diversidad de temperamentos y antecedentes de los testers en un equipo también puede aprovecharse mediante sesiones grupales de brainstorming, con la finalidad de producir mejores ideas para las pruebas.
	- Recursos abundantes:
		- Construyen un inventario profundo a los que recurrir durante las pruebas:
			- Herramientas.
			- Fuentes de información.
			- Datos de prueba.
			- Contactos.

> [!IMPORTANT]
>
> En la incertidumbre de la falta de requerimientos definidos:
> - Los Test Oracles buscan justificar que un hallazgo es un defecto.
> - Para armar los charters (plan de alto nivel) del ET, es posible emplear los oráculos para definir las pruebas a realizar.

---

¿Cuáles son los principios básicos que debe tener alguien que practique ET?
?
- Diseño de pruebas.
- Observación cuidadosa.
- Pensamiento crítico.
- Diversidad de ideas.
- Recursos abundantes.
<!--SR:!2025-06-25,1,230-->

¿Cuál es la relación entre ET y los oráculos del Testing?
?
Ante la incertidumbre de la falta de requerimientos definidos:
- Los Test Oracles buscan justificar que un hallazgo es un defecto.
- Para armar los charters (plan de alto nivel) del ET, es posible emplear los oráculos para definir las pruebas a realizar.
<!--SR:!2025-06-25,1,230-->

---

### Gestión del ET

#### Roles

- Test Manager: posee la autoridad de contratar y despedir personal, más otras responsabilidades administrativas.
- Test Lead: Enfocado solamente en la estrategia y tácticas del testing. Un Test Manager puede cumplir el presente rol.

#### Puede ser gestionado de 2 formas: delegación o participación

- Delegación:
	- TL especifica charters.
	- Los testers independientemente:
		- Diseñan.
		- Ejecutan pruebas que satisfagan el charter.
		- Realizan reportes.
	- En la práctica, un tester es asignado permanentemente a un conjunto de componentes, tal que pueda beneficiarse de una curva de aprendizaje ininterrumpida.
	- Recomendación Cem Kaner:
		- Tener reuniones la menos una vez a la semana con testers y preguntarles "¿Cuál es el bug más interesante que recientemente has encontrado?"
	- Ser un líder de exploradores significa ser un coach de agentes creativos semi-independientes: Cada tester es un ejecutivo que gestiona el valor de su propio tiempo.
- Participación:
	- Líder:
		- Realiza pruebas a la par de otros testers.
		- Esta es la mejor alternativa para líderes que han delegado sus responsabilidades administrativas y asistencia a reuniones a otras personas.
		- Le permite dirigir la estrategia de pruebas en tiempo real y continuamente demostrar los comportamientos que espera del equipo.
		- Su involucración íntima permite desparecer las preocupaciones de potenciales confusiones o ineficiencias durante el testing.
	- Gerente:
		- Debido a que es el responsable de la performance del equipo, la participación le permite estar en una posición para cumplir dicha responsabilidad.

#### "Pair Testing" para ET

Se tiende a converger en mejores ideas en comparación a si las personas trabajasen por sí solas.

Ver referencia Pair Programming (Heuristic Test Oracles).

---

Es posible aplicar el ==1;;Pair Testing== para converger en mejores ideas en comparación a si las personas trabajasen por sí solas.
<!--SR:!2025-06-25,1,230-->

---

## Situaciones en donde el ET es adecuado

- Cualquier situación en donde:
	- No es evidente cuál debería ser la siguiente prueba.
	- Se desea ir más allá de las pruebas "obvias".
- Es adecuado en cualquiera de las siguientes situaciones:
	- Se desea proporcionar un feedback rápido sobre un **nuevo producto o funcionalidad** (o bien hasta incluso de un sistema que heredamos y no hay ninguna documentación).
	- Se desea aprender el producto en poco tiempo (quizás no nos da tiempo para generar los tests scripteados).
	- Ya se ha probado scripts y se desea diversificar las pruebas.
	- Se desea encontrar el bug más importante en el menor tiempo posible.
	- Se desea verificar el trabajo de otro tester realizando una breve investigación independiente.
	- Se desea investigar y aislar un defecto en particular.
	- Se desea investigar el estado de un riesgo específico, para evaluar si es necesario crear pruebas guiadas por scripts en esa área.
- Dejando de lado al freestyle ET:
	- ET encaja en cualquier situación donde las pruebas no estén completamente definidas de antemano. Esto incluye todas las situaciones antemencionadas, adicionando al menos las siguientes, en donde se desea:
		- Improvisar sobre pruebas guiadas por scripts.
		- Interpretar instrucciones de prueba confusas.
		- Analizar un producto y planificar pruebas.
		- Mejorar pruebas existentes.
		- Escribir nuevos scripts de prueba.
		- Realizar regresiones en base a reportes de bugs antiguos.
		- Realizar pruebas en base a la lectura del manual de usuario y la verificación de cada afirmación (_claim_).

---

¿En qué situaciones el ET es adecuado?
?
- No es evidente cuál debería ser la siguiente prueba.
- Se desea ir más allá de las pruebas "obvias".
- Se desea proporcionar un feedback rápido sobre un **nuevo producto o funcionalidad** (o bien hasta incluso de un sistema que heredamos y no hay ninguna documentación).
- Se desea aprender el producto en poco tiempo (quizás no nos da tiempo para generar los tests scripteados).
- Se desea analizar un producto y planificar pruebas.
- Se desea mejorar pruebas existentes.
- Ya se ha probado scripts y se desea diversificar las pruebas.
- Se desea encontrar el bug más importante en el menor tiempo posible.
- Se desea verificar el trabajo de otro tester realizando una breve investigación independiente.
- Se desea investigar y aislar un defecto en particular.
- Se desea investigar el estado de un riesgo específico, para evaluar si es necesario crear pruebas guiadas por scripts en esa área.
<!--SR:!2025-06-25,1,230-->

---

## Situaciones en donde el ET no es adecuado

Partiendo de la base de que ET permite que la información fluya hacia atrás, desde la ejecución de pruebas hacia el rediseño de las mismas, este poder se pierde cada vez que:

- El ciclo de feedback es débil.
- El ciclo de feedback es largo, lento o costoso.
- Las pruebas son controversiales.
- Las pruebas son altamente dependientes a un alto grado de supervisión de la gerencia o aprobación del cliente.

En estos casos debemos recurrir a pruebas cuidadosamente guiadas por scripts.

No obstante, no debemos conformarnos con pruebas débiles solo porque complacen a los auditores. Debemos considerar el empleo de una estrategia híbrida de pruebas exploratorias y guiadas por scripts, obteniendo así lo mejor de ambos mundos.

---

ET permite que la información fluya hacia ==1;;atrás==, desde la ==1;;ejecución de pruebas== hacia el ==1;;rediseño== de las mismas.
<!--SR:!2025-06-25,1,230-->

¿En qué situaciones el ET NO es adecuado y recurrir a pruebas guiadas por scripts?
?
- El ciclo de feedback es débil.
- El ciclo de feedback es largo, lento o costoso.
- Las pruebas son controversiales.
- Las pruebas son altamente dependientes a un alto grado de supervisión de la gerencia o aprobación del cliente.
<!--SR:!2025-06-25,1,230-->

No debemos conformarnos con pruebas débiles solo porque complacen a los ==1;;auditores==. Debemos considerar el empleo de una estrategia ==1;;híbrida== de ==1;;pruebas exploratorias== y ==1;;guiadas por scripts==, obteniendo así lo mejor de ambos mundos.
<!--SR:!2025-06-25,1,230-->

---

## ET es disciplinado y decidido

- Es posible reportar lo que se ha cubierto y lo encontrado durante el testing.
- Es posible relacionar el testing con la misión adoptada.
- Es repetible o al menos tan repetible como las scripteadas: en todo momento seguimos una idea coherente de qué estamos probando y cómo probarlo.
- ET sería un testing "ad hoc" no-sistemático en caso de que:
	- No se haya podido contar la historia de los tests.
	- No se haya podido recordar qué se probó o la estrategia de pruebas.
	- No se haya podido relacionar el testing con la misión.

---

¿Por qué ET es disciplinado y decidido?
?
- Es posible reportar lo que se ha cubierto y lo encontrado durante el testing.
- Es posible relacionar el testing con la misión adoptada.
- Es repetible o al menos tan repetible como las scripteadas: en todo momento seguimos una idea coherente de qué estamos probando y cómo probarlo.
- ET sería un testing "ad hoc" no-sistemático en caso de que:
	- No se haya podido contar la historia de los tests.
	- No se haya podido recordar qué se probó o la estrategia de pruebas.
	- No se haya podido relacionar el testing con la misión.
<!--SR:!2025-06-25,1,230-->

---

## Productividad del ET

- No existen números razonables o estudios válidos que compare la productividad de las pruebas mediante ET en comparación a las scripteadas. Solamente existen anécdotas.
- La realidad es que la productividad depende de varios factores, por lo que hay que obtener las propias de uno y llevar a conclusiones mediante la experiencia.
