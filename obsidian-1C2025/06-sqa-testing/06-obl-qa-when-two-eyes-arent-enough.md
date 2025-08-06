---
tags:
- flashcards/swe/teoria/2P
---

#exam-question 

# When Two Eyes Aren't Enough

> Existen varios casos en donde le pedimos a nuestros colegas en que revisen el trabajo realizado por nosotros. Pero como nuestro cerebro recita lo que hemos creado hace poco, estamos siguiendo la misma lógica que hemos utilizado para cometer el error. Necesitamos otro par de ojos, cerebro que nunca hayan visto el código antes y piense de distinto.

> [!NOTE]
>
> - Esta lectura nos permite poder controlar y realizar seguimiento, desde lo menos formal a lo más formal, distintas componentes: código, minuta de una reunión, documento funcional, etc.
> - e.g., luego de una reunión, le pasamos a nuestro colega para que nos diga si falta algo que agregar de una reunión (en este caso fue un passaround).
> - La lectura habla de [[01-conceptos-generales#Paragua de SQA|pruebas estáticas]].

---

Mencione 3 pruebas estáticas. #exam-question
?
- Inspection.
- Team Review ("Structured Walkthroughs").
- Walkthrough.
- Pair Programming.
- Peer Deskcheck.
- Passaround.
- Ad Hoc Review.
<!--SR:!2025-06-25,1,230-->

#exam-question 
¿Por qué motivo las _review methods_ son consideradas como "pruebas estáticas"?::Es debido a que no existe código en ejecución. Es parte del SQA, más no es parte del QC: es parte del QA.
<!--SR:!2025-06-25,1,230-->

Nombre las pruebas estáticas desde la más formal a la menos formal.
?
1. Inspection.
2. Team Review ("Structured Walkthroughs").
3. Walkthrough.
4. Pair Programming.
5. Peer Deskcheck / Passaround.
6. Ad Hoc Review.
<!--SR:!2025-06-25,1,230-->

V o F. Las _review methods_ atacan fallas.::F, las _review methods_ atacan directamente el defecto, ya que no es posible ver las fallas debido a que no hay código en ejecución. Ejemplo: leyendo el código nos percatamos de que está mal codificado y no responde al requerimiento estipulado.
<!--SR:!2025-06-25,1,230-->

V o F. Las pruebas estáticas permiten solamente controlar y realizar seguimiento al código del SW.::F, es posible con distintas componentes: código, minuta de una reunión, documento funcional, etc.
<!--SR:!2025-06-25,1,230-->

---

## Peer Review Approaches (Review Methods)

- Solemos emplear terminologías conflictuantes para describirlas.
- Existen varias formas de revisión de a pares, las cuales abarcan un rango de formalidad y estructura.

![[06.1-formality-spectrum.png]]

---

Existen varias formas de revisión de a pares, las cuales abarcan un rango de ==1;;formalidad== y ==1;;estructura==.
<!--SR:!2025-06-25,1,230-->

---

- Las revisiones más formales son ejemplificadas por las inspecciones.
- Las revisiones informales valen la pena realizarlas y puede que satisfaga las necesidades en ciertas situaciones.
- Se requiere reconocer los puntos fuertes y limitaciones de varios métodos para poder seleccionar un proceso de revisión que sea adecuado para nuestra cultura, restricciones de tiempo y objetivos del negocio.
- Todos los tipos de revisiones involucran una combinación de:
	- Planificación.
	- Estudio del [[02-conceptos-clave-scm#Work Product|work product]].
	- Realizar una reunión de revisión.
	- Corregir errores.
	- Verificar las correcciones.

![[06.2-activities-peer-review-types.png]]

### Inspección

- Es el más sistemático y riguroso de los tipos de revisiones: la más formal.
- Posee las características:
	- Objetivos definidos.
	- Participación de un equipo capacitado.
	- Liderazgo por parte de un moderador capacitado.
	- Roles y responsabilidades específicos.
	- Un procedimiento de revisión documentado.
	- Reporte de resultados a la gerencia.
	- Criterios explícitos de entrada y salida para cada producto de trabajo.
	- Seguimiento de los defectos hasta su cierre.
	- Registro de datos de proceso y calidad para mejorar tanto el proceso de revisión como el proceso de desarrollo de SW.
- Sigue un proceso de varias etapas, bien definidas, con roles específicos asignados a cada participante.
- El proceso de inspección más común consta de 7 etapas:
	- Planificación.
	- Pantallazo.
	- Preparación.
	- Reunión.
	- Retrabajo.
	- Seguimiento.
	- Análisis causal.
- La mayor efectividad se logra cuando los inspectores son entrenados en el proceso de inspección y son capaces de cumplir cualquier rol.
- Las inspecciones dependen de una checklist de:
	- Defectos comunes encontrados en distintos tipos de [[02-conceptos-clave-scm#Work Product|work products]] del SW.
	- Reglas para construir los [[02-conceptos-clave-scm#Work Product|work products]].
	- Varias técnicas analíticas para encontrar bugs.
- Aspecto fundamental de una inspección:
	- Los participantes, otros que no sean el autor del work product:
		- Lideran la reunión (moderador).
		- Presentan el material al equipo de inspectores (lector).
		- Registran problemas a medida que surgen (registrador).
	- Participantes examinan el material desde su propio entendimiento para encontrar problemas.
	- Durante la reunión, el lector presenta una pequeña porción del material a otros inspectores, los cuáles generan dudas y objetan posibles defectos. Esto permite que se tenga una interpretación homogénea de cada porción del producto.
	- Al final de todo, el quipo consensua una valoración del [[02-conceptos-clave-scm#Work Product|work product]] y decide cómo verificar los cambios que el autor hará durante el retrabajo.
- Permite un escrutinio detallado respecto a la comprensibilidad y mantenibilidad del producto, revelando problemas.

---

La inspección es el más ==1;;sistemático== y ==1;;riguroso==, por ende la ==1;;más formal== de los tipos de revisiones.
<!--SR:!2025-06-25,1,230-->

Nombrar las características que posee una revisión.
?
- Objetivos definidos.
- Participación de un equipo capacitado.
- Liderazgo por parte de un moderador capacitado.
- Roles y responsabilidades específicos.
- Un procedimiento de revisión documentado.
- Reporte de resultados a la gerencia.
- Criterios explícitos de entrada y salida para cada producto de trabajo.
- Seguimiento de los defectos hasta su cierre.
- Registro de datos de proceso y calidad para mejorar tanto el proceso de revisión como el proceso de desarrollo de SW.
<!--SR:!2025-06-25,1,230-->

Una inspección sigue un ==1;;proceso== de varias etapas, bien ==1;;definidas==, con ==1;;roles específicos== asignados a cada participante.
<!--SR:!2025-06-25,1,230-->

El proceso de inspección más común consta de ==1;;7== etapas.
<!--SR:!2025-06-25,1,230-->

¿Cuáles son las 7 etapas de un proceso de inspección más común?
?
- Planificación.
- Pantallazo.
- Preparación.
- Reunión.
- Retrabajo.
- Seguimiento.
- Análisis causal.
<!--SR:!2025-06-25,1,230-->

¿De qué dependen las inspecciones?
?
Las inspecciones dependen de una checklist de:
- Defectos comunes encontrados en distintos tipos de work products del SW.
- Reglas para construir los work products.
- Varias técnicas analíticas para encontrar bugs.
<!--SR:!2025-06-25,1,230-->

¿Cuáles son los aspectos fundamentales de una inspección?
?
- Los participantes, otros que no sean el autor del work product:
	- Lideran la reunión (moderador).
	- Presentan el material al equipo de inspectores (lector).
	- Registran problemas a medida que surgen (registrador).
- Participantes examinan el material desde su propio entendimiento para encontrar problemas.
- Durante la reunión, el lector presenta una pequeña porción del material a otros inspectores, los cuáles generan dudas y objetan posibles defectos. Esto permite que se tenga una interpretación homogénea de cada porción del producto.
- Al final de todo, el quipo consensua una valoración del work product y decide cómo verificar los cambios que el autor hará durante el retrabajo.
<!--SR:!2025-06-25,1,230-->

Las inspecciones permiten un escrutinio ==1;;detallado== respecto a la ==1;;comprensibilidad== y ==1;;mantenibilidad== del producto, revelando problemas.
<!--SR:!2025-06-25,1,230-->

---

#### Efectividad

- Las inspecciones son más efectivas encontrando defectos que técnicas informales de revisión:
	- Inspección: Detección en promedio de 16 a 20 defectos por cada 1000 líneas de código.
	- Revisiones informales: Detección en promedio de 3 defectos por cada 1000 líneas de código.
- Si bien distintos inspectores pueden encontrar distintos problemas, la presente contribución [[06.1-ley-de-brooks#Impactos negativos de agregar más personal a un proyecto de SW en retraso|no se incrementa en forma lineal ante la adición de participantes]].
	- Si un inspector denota un defecto, es común escuchar a otro participante decir "yo también lo vi".
- Las interacciones entre inspectores durante la reunión pueden revelar nuevos bugs a medida que la observación de una persona estimula el pensamiento de otro.
	- Se pierde este efecto colaborativo en caso de que en la revisión de apares no se incluya una reunión, aunque existen estudios que se han cuestionado si la sinergia realmente posee algún valor añadido.

### Team review ("Structured Walkthroughs")

- Si bien posee planificación y estructuración, son menos formales y comprensivos ("_inspection-lite_").
- Siguen varios pasos de las inspecciones:
	- Participantes reciben el material de revisión días previos a la reunión y estudian por su cuenta.
	- El equipo colecciona datos en el esfuerzo de la revisión y la cantidad de defectos encontrados.
	- No obstante, las etapas de "pantallazo" y "seguimiento" son simplificadas u omitidas.
	- Algunos roles de los participantes son combinados.
	- El autor puede liderar la revisión y, a diferencia de inspecciones, se omite el rol del lector.
	- El registrador captura problemas que vayan surgiendo, empleando formularios estándares que la organización haya adoptado.
	- En vez tener a un participante describiendo una pequeña porción del producto, el líder de la revisión pregunta a participantes si poseen algún comentario en alguna sección o página en específico.

---

Las Team Reviews, si bien poseen planificación y estructuración, son menos formales y comprensivos, por lo que son conocidas también como ==1;;inspection-lite== o ==1;;structured walkthroughs==.
<!--SR:!2025-06-25,1,230-->

A diferencia de las inspecciones, las team reviews:
?
- Las etapas de "pantallazo" y "seguimiento" son simplificadas u omitidas.
- Algunos roles de los participantes son combinados.
- El autor puede liderar la revisión y, a diferencia de inspecciones, se omite el rol del lector.
- En vez tener a un participante describiendo una pequeña porción del producto, el líder de la revisión pregunta a participantes si poseen algún comentario en alguna sección o página en específico.
<!--SR:!2025-06-25,1,230-->

---

#### Efectividad

- Las team reviews solo encuentran 2/3 de los defectos de las inspecciones por horas-hombre.
- Las team reviews solamente posee casi la mitad de la productividad en comparación a las inspecciones.
- Poseen mayor costo que un deskcheck, pero varios participantes logran encontrar varios errores.
- Las team reviews son apropiadas para un equipo o producto que no requieren la rigurosidad completa del proceso de inspección.

### Walkthrough

- Es una revisión informal en donde el autor de un [[02-conceptos-clave-scm#Work Product|work product]] describe a un grupo de colegas y solicita por sus comentarios.
- Se diferencian en gran medida de las inspecciones ya que el autor toma el rol dominante: no existen otros roles inspectores en específico.
- Mientras que una inspección busca en cumplir los objetivos de calidad del equipo, una walkthrough principalmente satisface la necesidad del autor.
- Usualmente:
	- No poseen un procedimiento definido.
	- No requieren informar a la gerencia.
	- No generan métricas.
- Puede ser una forma ineficiente de revisar productos durante la etapa de mantenimiento:
	- El autor podría virar la atención de los críticos a las porciones modificadas de los entregables. No obstante, esto conlleva un riesgo de pasar por alto otras secciones que deberían haber sido modificadas, pero no lo fueron.
- En caso de que no sigan un procedimiento definido, personas pueden realizarlo de distintas formas.
	- Usualmente, el autor presenta el módulo o diseño del componente a otros participantes, describiendo:
		- Lo que hace.
		- Cómo está estructurado.
		- Las tareas que realiza.
		- El flujo de la lógica.
		- Las E/S.
	- Si bien encontrar problemas es uno de los objetivos, también es un objetivo lograr el consenso del entendimiento sobre:
		- El propósito del componente.
		- La estructura.
		- La implementación.
	- e.g., un walkthrough de diseño permite detectar si el diseño propuesto es suficientemente robusto y apropiado a lidiar con un problema.
- La confusión de una persona que revisa el trabajo usualmente es un indicio de un defecto.
- El rol dominante del autor y la naturaleza desestructurada hace que se retraten como un filtro de defectos de menor valor en comparación a las inspecciones o team reviews.

![[06.2-activities-peer-review-types.png]]

---

¿En qué consisten los walkthroughs?
?
Es una revisión informal en donde el autor de un work product describe a un grupo de colegas y solicita por sus comentarios.
<!--SR:!2025-06-25,1,230-->

A diferencia de las inspecciones, las structured walkthroughs:
?
- Se diferencian en gran medida de las inspecciones ya que el autor toma el rol dominante: no existen otros roles inspectores en específico.
- Mientras que una inspección busca en cumplir los objetivos de calidad del equipo, una walkthrough principalmente satisface la necesidad del autor.
- Usualmente:
	- No poseen un procedimiento definido.
	- No requieren informar a la gerencia.
	- No generan métricas.
<!--SR:!2025-06-25,1,230-->

Las walkthroughs podría ser una forma ineficiente de revisar productos durante la etapa de ==1;;mantenimiento==: ==1;;El autor podría virar la atención de los críticos a las porciones modificadas de los entregables, haciéndoles pasar por alto otras secciones que deberían haber sido modificadas, pero no lo fueron==.
<!--SR:!2025-06-25,1,230-->

La confusión de una persona que revisa el trabajo usualmente es un indicio de un ==1;;defecto==.
<!--SR:!2025-06-25,1,230-->

El rol ==1;;dominante== del autor y la naturaleza ==1;;desestructurada== hace que se retraten como un filtro de defectos de ==1;;menor valor== en comparación a las ==1;;inspecciones== o ==1;;team reviews==.
<!--SR:!2025-06-25,1,230-->

¿Cómo se conforma la tabla de las distintas revisiones en relación a las actividades que las componen?
?
![[06.2-activities-peer-review-types.png]]
<!--SR:!2025-06-25,1,230-->

---

#### Efectividad

- Descubren defectos en un 50% menos por cada 1000 líneas de código en comparación a las inspecciones.

### Pair Programming

- 2 devs trabajan sobre el mismo producto simultáneamente en la misma máquina.
- Facilita la comunicación y permite una revisión continua, incremental e informal de las ideas de ambos participantes. La revisión en tiempo real permite realizar correcciones de rumbo rápidamente.
- Cada línea de código es producto del trabajo conjunto de 2 cerebros y un solo teclado, lo que suele resultar en un trabajo de mayor calidad al aplicar literalmente el dicho "2 cabezas piensan mejor que 1".
- Puede utilizarse para crear cualquier [[02-conceptos-clave-scm#Work Product|work product]], no solo código.
- Culturalmente, fomenta la colaboración, la propiedad colectiva del código del equipo y un compromiso compartido con la calidad de cada componente.
- Disminuye la pérdida de conocimiento en caso de rotación de personal: Al menos 2 miembros del equipo llegan a conocer en profundidad cada parte del código.
- Se clasifica como un tipo de revisión informal:
	- Es poco estructurada.
	- No requiere procesos.
	- No requiere preparación ni documentación previa.
- Carece de la perspectiva de alguien externo y desapegado al código, tal que aporte una revisión formal.
- El pair programming no es considerado una técnica de revisión como tal, sino una **estrategia de desarrollo** que aprovecha la sinergia de 2 mentes enfocadas para crear productos superiores en diseño, ejecución y calidad.
- Implica un cambio cultural importante en la forma de operar del equipo de desarrollo, por lo que no suele ser un reemplazo directo de las revisiones formales entre pares en la mayoría de los casos.

---

El pair programming facilita la ==1;;comunicación== y permite una revisión ==1;;continua==, ==1;;incremental== e ==1;;informal== de las ideas de ambos participantes. La revisión en tiempo real permite realizar correcciones de rumbo rápidamente.
<!--SR:!2025-06-25,1,230-->

El pair programming suele resultar en un trabajo de mayor calidad al aplicar literalmente el dicho ==1;;"2 cabezas piensan mejor que 1"==.
<!--SR:!2025-06-25,1,230-->

El pair programming puede utilizarse para crear cualquier ==1;;work product, no solo código==.
<!--SR:!2025-06-25,1,230-->

El pair programming se clasifica como un tipo de revisión ==1;;informal==.
<!--SR:!2025-06-25,1,230-->

El pair programming carece de la ==1;;perspectiva de alguien externo== y desapegado al código, tal que aporte una revisión formal.
<!--SR:!2025-06-25,1,230-->

El pair programming no es considerado una técnica de revisión como tal, sino una ==1;;estrategia de desarrollo== que aprovecha la sinergia de 2 mentes enfocadas para crear productos superiores en diseño, ejecución y calidad.
<!--SR:!2025-06-25,1,230-->

El pair programming implica un cambio ==1;;cultural== importante en la forma de operar del equipo de desarrollo, por lo que no suele ser un reemplazo directo de las revisiones formales entre pares en la mayoría de los casos.
<!--SR:!2025-06-25,1,230-->

---

### Peer Deskcheck

- Solo una persona, además del autor, examina el [[02-conceptos-clave-scm#Work Product|work product]]. El autor puede no saber cómo el revisor abordó la tarea o cuán exhaustivo fue el análisis.
- Este tipo de revisión depende totalmente del conocimiento, habilidad y disciplina del revisor, por lo que los resultados pueden variar significativamente.
- Los Peer Deskchecks pueden ser bastante formales si el revisor usa una checklist de defectos, métodos de análisis específicos y formularios estándar para registrar hallazgos.
- Esta es la forma de revisión más económica, ya que solo requiere el tiempo de un revisor y, tal vez, una breve conversación posterior con el autor para explicar los hallazgos.
- Es recomendable para productos de bajo riesgo, cuando se cuenta con colegas hábiles para detectar defectos por sí mismos, o cuando hay restricciones severas de tiempo y recursos.
- Suele ser menos intimidante para el autor que una revisión grupal.
- Solo se encontrarán los errores que ese único revisor sea capaz de detectar y el autor no estará presente para responder preguntas o beneficiarse de discusiones que podrían ayudarle a identificar otros defectos.
- Son una buena manera de empezar a desarrollar una cultura de revisión.

---

El peer deskcheck solo ==1;;una persona==, además del autor, examina el work product. El autor puede no saber cómo el ==1;;revisor abordó la tarea== o ==1;;cuán exhaustivo fue el análisis==.
<!--SR:!2025-06-25,1,230-->

El peer deskcheck depende totalmente del ==1;;conocimiento==, ==1;;habilidad== y ==1;;disciplina== del revisor, por lo que los resultados pueden variar significativamente.
<!--SR:!2025-06-25,1,230-->

El peer deskcheck es la forma de revisión ==1;;más económica==, ya que solo requiere el tiempo de un revisor y, tal vez, una breve conversación posterior con el autor para explicar los hallazgos.
<!--SR:!2025-06-25,1,230-->

El peer deskcheck es recomendable para productos de ==1;;bajo riesgo==, cuando se cuenta con colegas hábiles para detectar defectos por sí mismos, o cuando hay restricciones severas de tiempo y recursos.
<!--SR:!2025-06-25,1,230-->

En el peer deskcheck solo se encontrarán los errores que ==1;;ese único revisor sea capaz de detectar== y ==1;;el autor no estará presente== para responder preguntas o beneficiarse de discusiones que podrían ayudarle a identificar otros defectos.
<!--SR:!2025-06-25,1,230-->

---

### Passaround

- Es una revisión peer deskcheck concurrente, en la que se entrega una copia del producto a varias personas y luego se recopila su retroalimentación.
- Mitiga 2 riesgos principales de la revisión individual:
	- La falta de respuesta oportuna en tiempo del revisor.
	- La baja calidad de la revisión.
- Permite involucrar a más revisores de los que sería posible reunir en comparación respecto a una reunión presencial.
- De igual manera, carece del estímulo mental que puede brindar una discusión grupal.
	- Todos pueden pasar por alto tareas importantes que solo se identificarían más tarde en una reunión de equipo, lo que sugiere que una revisión en grupo habría sido más efectiva.

---

¿En qué se diferencia un passaround de un peer deskcheck?
?
Es una revisión peer deskcheck concurrente, en la que se entrega una copia del producto a varias personas y luego se recopila su retroalimentación.
<!--SR:!2025-06-25,1,230-->

¿Cuáles 2 riesgos mitiga principalmente el passaround respecto de la revisión individual?
?
- La falta de respuesta oportuna en tiempo del revisor.
- La baja calidad de la revisión.
<!--SR:!2025-06-25,1,230-->

El passaround permite involucrar a ==1;;más revisores== de los que sería posible reunir en comparación respecto a una reunión presencial.
<!--SR:!2025-06-25,1,230-->

V o F. El passaround carece del estímulo mental que puede brindar una discusión grupal.::V
<!--SR:!2025-06-25,1,230-->

En un passaround todos pueden ==1;;pasar por alto tareas importantes== que solo se identificarían más tarde en una reunión de equipo, lo que sugiere que una ==1;;revisión en grupo== habría sido más efectiva.
<!--SR:!2025-06-25,1,230-->

---

#### Ejemplo

- Se suele dejar una copia del documento en una carpeta compartida.
- Los revisores agregan comentario en el documento durante un periodo determinado.
- Luego, el autor reconcilia los comentarios, hace las correcciones obvias e ignora las sugerencias poco útiles.
- Esta modalidad permite que cada revisor vea los comentarios ya realizados, lo que reduce la redundancia y pone en evidencia posibles diferencias de interpretación.
- Se debe evitar debates extensos en los mismos comentarios del documento, ya que es mejor resolverlos mediante comunicación directa.
- Las revisiones de este tipo son una buena opción cuando los revisores no pueden reunirse cara a cara por motivos de distancia geográfica o limitaciones de tiempo.

### Ad Hoc Review

- Las revisiones ad hoc son el tipo de revisión más informal.
- Situación representativa: un dev que le pide a otro si pueden juntarse unos minutos a ayudarle a localizar un bug difícil de encontrar.
- Este tipo de revisiones espontáneas deberían ser una parte natural de la colaboración en equipo y son una forma rápida de obtener otra perspectiva que en la mayoría de las veces permite descubrir problemas que uno mismo no puede ver.
- Pueden resolver el problema en forma inmediata, pero tienen poco impacto a largo plazo o más allá de dicho caso puntual.

---

Las revisiones ad hoc son el tipo de revisión más ==1;;informal==.
<!--SR:!2025-06-25,1,230-->

¿Cuál es una situación representativa de revisiones ad hoc?
?
Un dev que le pide a otro si pueden juntarse unos minutos a ayudarle a localizar un bug difícil de encontrar.
<!--SR:!2025-06-25,1,230-->

Las revisiones ad hoc espontáneas deberían ser una ==1;;parte natural de la colaboración en equipo== y son una ==1;;forma rápida de obtener otra perspectiva== que en la mayoría de las veces permite descubrir problemas que uno mismo no puede ver.
<!--SR:!2025-06-25,1,230-->

Las revisiones ad hoc pueden resolver el problema ==1;;en forma inmediata==, pero tienen ==1;;poco impacto a largo plazo== o más allá de dicho caso puntual.
<!--SR:!2025-06-25,1,230-->

---

## Eligiendo un Review Approach

- Una forma de seleccionar el método de revisión más adecuado para una situación es basarse en el riesgo: la probabilidad de que un producto tenga defectos y el potencial de daño si los tiene.
- Se recomienda usar inspecciones para productos de alto riesgo y técnicas más económicas para componentes de menor riesgo.
- Algunos factores que aumentan el riesgo son:
	- Uso de nuevas tecnologías, técnicas o herramientas.
	- Lógica o algoritmos complejos de entender pero deben ser precisos y optimizados.
	- Presión excesiva en el cronograma del dev.
	- Capacitación o experiencia insuficiente de los devs.
	- Partes del producto críticas para la misión o la seguridad, con modos de falla graves.
	- Componentes arquitectónicos claves que sirven de base para la evolución futura del producto.
	- Gran número de condiciones de excepción o modos de falla difíciles de estimular durante las pruebas.
	- Componentes que se pretende reutilizar.
	- Componentes que servirán como modelos o plantillas para otros componentes.
	- Componentes con múltiples interfaces que afectan a varias partes del producto.
- La siguiente tabla sugiere cuál de las revisiones se adaptan mejor a objetivos específicos:
	![[06.3-review-specific-objectives.png]]
- La mejor forma de elegir un método de revisión: mantener registros sobre la eficacia y eficiencia de las revisiones. Registrar:
	- Datos objetivos y subjetivos de revisiones realizadas.
	- Productos revisados.
	- Resultados obtenidos.
- Lo más importante: empezar a desarrollar una cultura que valore la revisión como un factor clave para mejorar la calidad del SW, la productividad y el aprendizaje individual.

---

Una forma de seleccionar el método de revisión más adecuado para una situación es basarse en el ==1;;riesgo==.
<!--SR:!2025-06-25,1,230-->

El riesgo a contemplar al momento de seleccionar un método de revisión se basa en la ==1;;probabilidad== de que un producto ==1;;tenga defectos== y el ==1;;potencial de daño== si los tiene.
<!--SR:!2025-06-25,1,230-->

Se recomienda usar inspecciones para ==1;;productos de alto riesgo== y técnicas más económicas para ==1;;componentes de menor riesgo==.
<!--SR:!2025-06-25,1,230-->

¿Cómo se conforma la tabla de la relación entre objetivos y métodos de revisión sugeridos?
?
![[06.3-review-specific-objectives.png]]
<!--SR:!2025-06-25,1,230-->

La mejor forma de elegir un método de revisión es manteniendo registros sobre la ==1;;eficacia== y ==1;;eficiencia== de las revisiones.
<!--SR:!2025-06-25,1,230-->

Para poder mantener registros sobre le eficacia y eficiencia de los métodos de revisión, se debe registrar:
?
- Datos objetivos y subjetivos de revisiones realizadas.
- Productos revisados.
- Resultados obtenidos.
<!--SR:!2025-06-25,1,230-->

Lo más importante es empezar a desarrollar una ==1;;cultura== que valore la revisión como un factor clave para mejorar: la ==1;;calidad del SW==, la ==1;;productividad== y el ==1;;aprendizaje individual==.
<!--SR:!2025-06-25,1,230-->

---

## Conclusiones

Si bien la estadística quedó vieja, nos interesan los conceptos:

![[06.4-conclusiones-ranges-of-defect-removal-efficiency.png]]

- Existen varios [[08-tipos-de-prueba|tipos de prueba]].
- Highest:
	- El test que máxima eficiencia tendríamos, en caso de hacerlo muy bien y que las condiciones sean favorables en el momento en que lo hagamos:
		- Code Inspection o Statis Analysis con 90%.
- Median:
	- Si nos paramos en el promedio: ninguno nos da más del 65%:
		- Detailed Functional Design Inspection: 65%.
		- Detailed Logic Design Inspection: 65%.
		- Code Inspection o Statis Analysis: 65%.

---

V o F. Para poder obtener la tendencia de la eficiencia de la remoción de efectos al 100%, debemos emplear diferentes métodos de revisión.::V
<!--SR:!2025-06-25,1,230-->

El ranking del highest ranges of defect removal efficiency es:
?
1. Code inspection or static analysis.
2. Detailed functional design inspection.
3. Detailed logic design inspection.
<!--SR:!2025-06-25,1,230-->

El ranking del median ranges of defect removal efficiency es:
?
1. Detailed functional design inspection & Detailed logic design inspection.
2. Code inspection or static analysis.
<!--SR:!2025-06-25,1,230-->

El ranking del lowest ranges of defect removal efficiency es:
?
1. Code inspection or static analysis & Detailed logic design inspection.
2. Detailed functional design inspection.
<!--SR:!2025-06-25,1,230-->

Si nos paramos en el promedio: ninguno nos da más del ==1;;65%==.
<!--SR:!2025-06-25,1,230-->

---
