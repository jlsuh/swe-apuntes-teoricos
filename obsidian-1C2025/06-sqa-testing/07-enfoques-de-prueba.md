---
tags:
- flashcards/swe/teoria/2P
---

# Enfoques de Prueba

---

V o F. Es posible aplicar los 3 enfoques a la vez y que los enfoques nunca se crucen el uno con otro.::V, no es que "nos pasamos de un enfoque a otro" (negro <-> blanco <-> gris).
<!--SR:!2025-06-25,1,230-->

---

## Enfoque de Caja Negra

- Prueba funcional, producida por los datos o producida por la E/S.
- Prueba lo que el SW debería hacer:
	- Se basa en la definición del módulo a probar (definición necesaria para construir el módulo).
	- Nos desentendemos completamente del comportamiento y estructura interna del componente.
- ¿Qué hacemos?
	- Seleccionamos subconjuntos de los datos de entrada posibles, esperando que cubran un conjunto extenso de otros casos de prueba posibles.
	- Podemos suponer que la prueba de un valor representativo de cada clase es equivalente a la prueba de cualquier otro valor.
	- Llamamos a cada subconjunto "Clase de Equivalencia".
	- Estas pruebas son llamadas "Pruebas por Partición de Equivalencia" o "Pruebas basadas en subdominios".

> [!NOTE]
>
> - Por definición es una prueba funcional.
> 	- PO / usuarios: no entienden el código.
> - No sabemos cómo está construido por dentro ni tampoco lo que sucede exactamente.
> - Sabemos el "qué" pero no el "cómo".
> - --Entrada-->|  f  |--Salida-->
> - Cuando trabajamos con caja negra, a parte de saber qué hace la función que transforma, es pensar en los casos iniciales: ¿Qué metemos como input? ¿Qué esperamos de output?

---

(Control U6) ¿Qué es una prueba de caja negra?
?
- Prueba funcional, producida por los datos o producida por la E/S.
- Prueba lo que el SW debería hacer:
	- Se basa en la definición del módulo a probar (definición necesaria para construir el módulo).
	- Nos desentendemos completamente del comportamiento y estructura interna del componente.
<!--SR:!2025-06-25,1,230-->

¿Qué hacemos en una prueba de caja negra?
?
- Seleccionamos subconjuntos de los datos de entrada posibles, esperando que cubran un conjunto extenso de otros casos de prueba posibles.
- Podemos suponer que la prueba de un valor representativo de cada clase es equivalente a la prueba de cualquier otro valor.
- Llamamos a cada subconjunto "Clase de Equivalencia".
- Estas pruebas son llamadas "Pruebas por Partición de Equivalencia" o "Pruebas basadas en subdominios".
<!--SR:!2025-06-25,1,230-->

Por definición, una prueba de caja negra es una prueba ==1;;funcional==.
<!--SR:!2025-06-25,1,230-->

¿Quiénes son destinados a realizar pruebas de caja negra?
?
PO / usuarios que no entienden el código.
<!--SR:!2025-06-25,1,230-->

En una prueba de caja negra no sabemos cómo ==1;;está construido por dentro== ni tampoco lo que ==1;;sucede exactamente==.
<!--SR:!2025-06-25,1,230-->

En una prueba de caja negra sabemos el ==1;;qué== pero no el ==1;;cómo==.
<!--SR:!2025-06-25,1,230-->

La prueba de caja negra se representa mediante una función de la forma: ==1;;--Entrada-->|  f  |--Salida-->==
<!--SR:!2025-06-25,1,230-->

---

### Condiciones y casos

- Condiciones de Prueba:
	- Son descripciones de situaciones que quieren probarse ante las que el sistema debe responder.
	- e.g., "el sistema debe validar que el usuario ingrese una edad mayor o igual a 18".
- Casos de Prueba:
	- Son lotes de datos necesarios para que se dé una determinada condición de prueba.
	- e.g., se prueba con 17, 18 y 19 (son 3 casos de prueba distintos).

> [!NOTE]
>
> Cuando comenzamos a pensar los casos de prueba, nos damos cuenta de que tenemos que tener un criterio sobre la cuál apoyarnos para analizarlas.

---

(Control U6) ¿Qué es una condición y un caso de prueba?
?
- Condiciones de Prueba:
	- Son descripciones de situaciones que quieren probarse ante las que el sistema debe responder.
	- e.g., "el sistema debe validar que el usuario ingrese una edad mayor o igual a 18".
- Casos de Prueba:
	- Son lotes de datos necesarios para que se dé una determinada condición de prueba.
	- e.g., se prueba con 17, 18 y 19 (son 3 casos de prueba distintos).
<!--SR:!2025-06-25,1,230-->

Cuando comenzamos a pensar los casos de prueba, nos damos cuenta de que tenemos que tener un ==1;;criterio de selección de casos== sobre la cuál apoyarnos para analizarlas.
<!--SR:!2025-06-25,1,230-->

---

### Criterio de Selección de Casos

- Es una condición para seleccionar un conjunto de casos de prueba.
- De todas las combinaciones posibles sólo seleccionaremos algunas: La menor cantidad de aquellas que tengan mayor probabilidad de encontrar un defecto no encontrado por otra prueba.
- Partición (de casos):
	- Todos los posibles casos de prueba los dividimos en clases.
	- Todos los casos de una clase son equivalentes entre sí:
		- Detectan los mismos defectos.
		- Con solo ejemplos de cada clase cubrimos todas las pruebas.
		- El éxito está en la selección de la partición.
- Criterios:
	- Variaciones de Eventos.
	- Clase de Equivalencia:
		- De entrada.
		- De salida.
	- Condiciones de Borde.
	- Ingreso de valores de otro tipo.
	- Integridad del Modelo de datos:
		- De dominio.
		- De entidad.
		- De relación.

![[07.6-jamboard-ejemplos-criterios.png]]

---

¿Qué es un criterio de selección de casos y en qué consiste?
?
- Es una condición para seleccionar un conjunto de casos de prueba.
- Consiste en, de todas las combinaciones posibles, seleccionar algunas: La menor cantidad de aquellas que tengan mayor probabilidad de encontrar un defecto no encontrado por otra prueba.
<!--SR:!2025-06-25,1,230-->

¿En qué consiste una partición (de casos)?
?
- Todos los posibles casos de prueba los dividimos en clases.
- Todos los casos de una clase son equivalentes entre sí:
	- Detectan los mismos defectos.
	- Con solo ejemplos de cada clase cubrimos todas las pruebas.
	- El éxito está en la selección de la partición.
<!--SR:!2025-06-25,1,230-->

(Control U6) ¿Qué técnicas de caja negra conoce?
?
- Partición (Clases) de equivalencia.
	- De entrada.
	- De salida.
- Condición de Borde.
- Clases Inválidas.
- Conjetura de errores.
	- Ingreso de valores de otro tipo.
	- Hacer "submit" un form incompleto.
	- Para campos alfanuméricos, ingresar caracteres poco usuales.
<!--SR:!2025-06-25,1,230-->

---

#### Partición (Clases) de equivalencia

- Son clases que dan el mismo resultado.
- ¿Cómo lo hacemos?
	- El proceso incluye dos pasos:
		1. Identificar las clases de equivalencia.
		2. Definir casos de prueba.
	- La identificación de clases de equivalencia se hace dividiendo cada condición de entrada en 2 grupos:
		- Condición de entrada:
			1. Clases Válidas.
			2. Clases Inválidas.
		- Ejemplo de elección Por c/condición de entrada:
			- Rango de valores. Ej.: 100 < Nro. Sucursal < 200
				- 1 válida: 101 al 199
				- 2 inválidas: 0 a 100 y 200 al infinito.
			- Conjunto de valores. Ej.: DNI, CI, PAS.
				- Una válida y una inválida: pertenece o no al conjunto de valores.
			- "Debe ser", e.g., primera letra = "A"
				- Una válida y una inválida: comienza o no comienza con "A".
			- Si creemos que los elementos de una clase de equivalencia no son tratados en forma idéntica, debemos dividir la clase en clases menores.
				- e.g., las sucursales de Capital Federal son de la 100 a la 130.

> [!IMPORTANT]
>
> 1. Divide en 2 tipos de clases: válidas e inválidas.
> 2. Se define para un caso o campo concreto: la # de clases válidas e inválidas.
> 3. e.g., para un entero de largo 3, para 100 < Nro. Sucursal < 200:
> 	- ClaseVálida1 = 101 al 199
> 	- ClaseInválida1 = 0 a 100 y ClaseInválida2 = 200 al 999.
> 4. Dentro de dicho rango, podemos elegir a cualquiera como representante de dicha clase: dicha elección será el "[[#Condiciones y casos|caso de prueba]]" concreto.
> 	- Caso de prueba 1: ClaseInválida1 = 0 a 100 = Clase(50) => Caso de prueba para clase inválida 1 es el 50.
> 	- Caso de prueba 2: ClaseInválida2 = 200 al 999 = Clase(800) => Caso de prueba para clase inválida 2 es el 800.
> 	- Caso de prueba 3: ClaseVálida1 = 101 al 199 = Clase(150) => Caso de prueba para clase válida 1 es el 150.

![[07.8-caja-negra-ejemplo-condiciones.png]]

---

¿Qué son las particiones (clases) de equivalencia?
?
Son clases que dan el mismo resultado.
<!--SR:!2025-06-25,1,230-->

¿Cuáles son los pasos que incluye las particiones (clases) de equivalencia?
?
1. Identificar las clases de equivalencia: dividimos cada condición de entrada en 2 grupos:
	1. Clases Válidas.
	2. Clases Inválidas.
2. Definir casos de prueba: las siguientes son ejemplos de elección por cada condición de entrada y pueden ser referidas a:
	- Rango de valores: 100 < Nro. Sucursal < 200
		- 1 válida: 101 al 199
		- 2 inválidas: 0 a 100 y 200 al infinito.
	- Conjunto de valores: DNI, CI, PAS.
		- Una válida y una inválida: pertenece o no al conjunto de valores.
	- "Debe ser": primera letra = "A"
		- Una válida y una inválida: comienza o no comienza con "A".
	- Si creemos que los elementos de una clase de equivalencia no son tratados en forma idéntica, debemos dividir la clase en clases menores.
		- e.g., las sucursales de Capital Federal son de la 100 a la 130.
<!--SR:!2025-06-25,1,230-->

Contar un ejemplo de particiones (clases) de equivalencia.
?
1. Divide en 2 tipos de clases: válidas e inválidas.
2. Se define para un caso o campo concreto: la # de clases válidas e inválidas.
3. e.g., para un entero de largo 3, para 100 < Nro. Sucursal < 200:
	- ClaseVálida1 = 101 al 199
	- ClaseInválida1 = 0 a 100 y ClaseInválida2 = 200 al 999.
4. Dentro de dicho rango, podemos elegir a cualquiera como representante de dicha clase: dicha elección será el "caso de prueba" concreto.
	- Caso de prueba 1: ClaseInválida1 = 0 a 100 = Clase(50) => Caso de prueba para clase inválida 1 es el 50.
	- Caso de prueba 2: ClaseInválida2 = 200 al 999 = Clase(800) => Caso de prueba para clase inválida 2 es el 800.
	- Caso de prueba 3: ClaseVálida1 = 101 al 199 = Clase(150) => Caso de prueba para clase válida 1 es el 150.
<!--SR:!2025-06-25,1,230-->

---

##### Ejemplo

- Supongamos la transacción de alta de datos de un cliente (persona física) en un Banco.
- Definir las particiones para los atributos seleccionados:
	- Trabajaremos solo con algunos al solo efecto de incorporar el concepto de partición:
		- Si creemos que los elementos de una clase de equivalencia no son tratados en forma idéntica, debemos dividir la clase en clases menores.
			- e.g., las sucursales de Capital Federal son de la 100 a la 130.
		- Atributos considerados:
			- Apellido: Char (30) <> " ".
			- Nombres: Char (30) <> " ".
			- Documento:
				- Tipo Documento: Char (3) (DNI / CI / LE / LC / PAS).
				- Nro Documento: Num (9) > 0.
				- Cod. Provincia: Num (2) (01 a 23) o 40.
			- Estado Civil: Char (1) ( S / C / V / D / O ).
			- Cantidad de Hijos: Num (2) (0 a 20).
			- Condición IVA: Char (3) ( RI / RNI / EX ).
			- Ingreso Mensual: Num (15) >= 0.

#### Condición de Borde

- La experiencia muestra que los casos de prueba que exploran las condiciones de borde producen mejor resultado que aquellas que no lo hacen.
- Además de mirar las condiciones de entrada, podemos mirar salida:
	- Si creemos que los elementos de una clase de equivalencia no son tratados en forma idéntica, debemos dividir la clase en clases menores.
		- Ejemplos: Listados
			- "El código postal es un número entre 1000 y 8000": 998, 999, 1000, 1001, 1002, 7998, 7999, 8000, 8001, 8002.
- ¿Cómo hacemos?
	- Rango de Valores: Casos válidos para los extremos del rango y casos inválidos para los valores siguientes a los extremos.
- Aplicar lo mismo para los datos de salida.
- Si la entrada o salida es un conjunto ordenado, enfocar la atención en el primero y en el último de los elementos del conjunto.
	- Prestar especial atención a los archivos/tablas vacíos, primer registro / fila, último registro / fila, fin del archivo / tabla.

> [!NOTE]
>
> - Es el análisis que hacemos en el borde de la clase de equivalencia.
> - Este criterio va en línea con el principio de Testing: "Los errores se agrupan".
> 	- En general encontramos el 80% de los errores en el 20% del código (Pareto).
> 	- Dentro de dicho 20% del código, uno de los principales que agrupan los errores son justamente las condiciones de borde.
> 	- ¿Por qué motivo? Esto es porque las regulaciones, los requerimientos y las especificaciones no lo tienen claramente definido: "Nos entra la duda de si es > 100 o >= 100".
> - Los programadores en general tienen sus dudas respecto a este punto y sumado a los requerimientos que no lo especifican correctamente.
> 	- Es importante levantar la mano como dev y preguntar.
> 	- Pedir que, previo a la aceptación de una épica, las condiciones de borde estén bien claras.

---

La experiencia muestra que los casos de prueba que exploran las ==1;;condiciones de borde== producen ==1;;mejor resultado== que aquellas que no lo hacen.
<!--SR:!2025-06-25,1,230-->

Además de mirar las condiciones de ==1;;entrada==, es posible mirar las condiciones de ==1;;salida==.
<!--SR:!2025-06-25,1,230-->

Un ejemplo de listados de condiciones de borde es:
?
"El código postal es un número entre 1000 y 8000": ..., 998 ,999 | 1000 | 1001, 1002, ..., 7998, 7999 | 8000 | 8001, 8002, ...
<!--SR:!2025-06-25,1,230-->

¿En qué consisten las condiciones de borde?
?
Consisten en contemplar los casos válidos para los extremos del rango y casos inválidos para los valores siguientes a los extremos.
<!--SR:!2025-06-25,1,230-->

En caso de que la E/S sea un conjunto ordenado, debemos enfocar la atención en el ==1;;primer== y ==1;;último== de los elementos del conjunto.
<!--SR:!2025-06-25,1,230-->

Ejemplos de primeros y últimos elementos del conjunto (condiciones de borde) son:
?
- Archivos/tablas vacíos.
- Primer y último registro.
- Fin del archivo/tabla.
<!--SR:!2025-06-25,1,230-->

---

#### Clases Inválidas

- Hasta ahora hablamos del ingreso de clases inválidas del mismo tipo que la clase válida.
	- Pero también tenemos que probar el ingreso de valores de otro tipo:
		- Numéricos en vez de alfabéticos.
		- Alfabéticos en vez de numéricos.
		- Combinaciones de ambos.
		- Fechas erróneas.
	- En algunos casos, estas validaciones ya son resueltas por el entorno de desarrollo, y en consecuencia los casos de prueba no son necesarios.
- Muchas veces, la combinación de los datos de entrada es la que produce una clase válida o inválida:
	- Ejemplo: Podría ser que si el estado civil es divorciado, los datos del cónyuge se deben ignorar.
	- Ejemplo: El número de CUIT debe incluir el del documento.
- Estas condiciones cruzadas deben agregarse a la lista.

> [!NOTE]
>
> - Si existen clases válidas => Existen clases inválidas (clases que, en caso de que sean tomadas como "válidas", evidenciarían que el SW hace cosas que no debiera hacer).
> 	- Lo correcto sería que tiren un error.
> - Parte de la decisión de tomar clases válidas, está también decidir aquellas clases inválidas.

> [!NOTE]
>
> - Hasta ahora hablamos siempre del mismo tipo de dato para las clases válidas como las inválidas. Es decir, ambos pertenecen al mismo dominio de datos.
> - La técnica de clases inválidas plantea también el hecho de probar con dominio de datos que no pertenezcan al dominio "ordinario" de la prueba:
> 	- e.g., si son números enteros => Probar números racionales.
> 	- e.g., si son números enteros => Probar letras o caracteres no numéricos.
> - Esto es parte de la siguiente técnica: conjetura de errores.

---

¿En qué consiste la técnica de clases inválidas?
?
Consta de ingresar de clases inválidas de distintos tipo a las de clases válidas:
- Numéricos en vez de alfabéticos.
- Alfabéticos en vez de numéricos.
- Combinaciones de ambos.
- Fechas erróneas.
<!--SR:!2025-06-25,1,230-->

En algunos casos, las validaciones por un distinto tipo de clase inválida que la clase válida ya son resueltas por ==1;;el entorno de desarrollo== y en consecuencia los casos de prueba ==1;;no son necesarios==.
<!--SR:!2025-06-25,1,230-->

Muchas veces, la combinación de los ==1;;datos de entrada== es la que produce una clase válida o inválida. ==1;;Podría ser que si el estado civil es divorciado, los datos del cónyuge se deben ignorar; el número de CUIT debe incluir el del documento.==
<!--SR:!2025-06-25,1,230-->

La técnica de clases inválidas plantea también el hecho de probar con ==1;;dominio de datos== que no pertenezcan al ==1;;dominio "ordinario"== de la prueba. ==1;;Ejemplos: si son números enteros => Probar números racionales; si son números enteros => Probar letras o caracteres no numéricos==.
<!--SR:!2025-06-25,1,230-->

El hecho de probar con un dominio de datos que no pertenezcan al dominio "ordinario" de la prueba, es parte de la técnica ==1;;conjetura de errores==.
<!--SR:!2025-06-25,1,230-->

---

#### Conjetura de errores

- También llamada Prueba de Sospechas: "Sospechamos" que algo puede andar mal.
- Enumeramos una lista de errores posibles o de situaciones propensas a tener errores.
- Creamos casos de prueba basados en esas situaciones.
- Es un proceso muy efectivo. Formalizado a partir del análisis de las fallas.
- El programador es quien puede darnos información más relevante.
- Tiene generalmente dos orígenes:
	- Partes complejas de un componente.
	- Circunstancias del desarrollo.
- La creatividad juega un papel clave:
	- No hay una técnica para la conjetura de errores.
	- Es un proceso intuitivo y ad hoc.
	- Se basa mucho en la experiencia.
- ¿Cuándo hacerlo?
	- Un componente, o parte de él, hecho "a las apuradas".
	- Un componente modificado por varias personas en distintos momentos.
	- Un componente con estructura anidadas, condiciones compuestas, etc.
	- Un componente que sospechamos fue armado por la "técnica de copy & paste" de varios otros componentes.

> [!IMPORTANT]
>
> - En conjetura de errores definimos solamente clases inválidas (nos enfocamos solamente en clases inválidas).
> - Mientras que en las otras 3 técnicas partimos en clases de equivalencia y definimos clases válidas e inválidas.

> [!NOTE]
>
> Ejemplos: un buen tester:
> - Dado un form a completar, le daría "submit" sin completar ningún campo, a ver qué pasa.
> - En los campos alfanuméricos, poner caracteres inusuales: ampersand, "ñ", etc.
> - Si sospechamos que un cierto componente fue copiado de otra aplicación, ya que es muy similar y recordamos que dicha aplicación tenía problemas de SQL Injection => Probar en este caso SQL Injection.

---

¿En qué consiste la prueba de sospechas?
?
- Consiste en "sospechar" que algo puede andar mal.
- Enumerar una lista de errores posibles o de situaciones propensas a tener errores y creamos casos de prueba en base a estas.
<!--SR:!2025-06-25,1,230-->

La conjetura de errores es un proceso ==1;;muy efectivo==, formalizado a partir del análisis de las fallas.
<!--SR:!2025-06-25,1,230-->

El programador es quien puede darnos información más relevante.

¿Cuáles son los 2 orígenes generales de la conjetura de errores?
?
- Partes complejas de un componente.
- Circunstancias del desarrollo.
<!--SR:!2025-06-25,1,230-->

La ==1;;creatividad== juega un papel clave en la conjetura de errores.
<!--SR:!2025-06-25,1,230-->

V o F. No hay una técnica para la conjetura de errores.::V
<!--SR:!2025-06-25,1,230-->

V o F. Una pruebas sospecha es proceso intuitivo y ad hoc.::V
<!--SR:!2025-06-25,1,230-->

V o F. La conjetura de errores se basa mucho en la experiencia.::V
<!--SR:!2025-06-25,1,230-->

¿Cuándo conviene adoptar la conjetura de errores?
?
- Un componente, o parte de él, hecho "a las apuradas".
- Un componente modificado por varias personas en distintos momentos.
- Un componente con estructura anidadas, condiciones compuestas, etc.
- Un componente que sospechamos fue armado por la "técnica de copy & paste" de varios otros componentes.
<!--SR:!2025-06-25,1,230-->

A diferencia de las otras 3 técnicas, la conjetura de errores se enfoca solamente en ==1;;clases inválidas==. ==1;;(en las otras 3 técnicas partimos en clases de equivalencia y definimos clases válidas e inválidas)==
<!--SR:!2025-06-25,1,230-->

---

## Enfoque Caja Blanca

- Prueba estructural del SW:
	- También conocida como Clear Box Testing, Open Box Testing, Glass Box Testing, Transparent Box Testing, Code-Based Testing or Structural Testing.
	- Es un método de SW Testing en el cual **la estructura interna, el diseño y la implementación del SW es conocido por el Tester**.
	- The tester chooses inputs to exercise paths through the code and determines the appropriate outputs. Programming know-how and the implementation knowledge is essential. White box testing is testing beyond the UI and into the nitty-gritty of a system.
- El Tester elige qué valores de entrada utilizar para ejecutar ciertos caminos en el código, conociendo la potencial salida de ese camino.
- En este tipo de pruebas, es esencial que el Tester conozca el lenguaje de programación con el que el SW fue construido, debido a que se basa en cómo está estructurado el componente internamente y su definición.
- Se lo conoce como caja blanca porque desde el punto de vista del Tester, se puede ver cómo el SW está construido.
- Se lo utiliza también para incrementar el grado de cobertura de la lógica interna del componente.

> [!NOTE]
>
> - Conocemos cómo está construido.
> - Además de saber "qué" (importancia sobre las E/S), conocemos "cómo" (construcción).
> - Al saber el código, podemos ver los caminos y decidir cómo fluir en la lógica. Es una forma más puntillosa de recorrer un componente de SW.
> - Mayor complejidad: el tester debe ser capaz de leer código, cosa que muchas veces no sucede.

> [!IMPORTANT]
>
> - Los enfoques de pruebas (negro, blanco o gris) son definidos en base a:
> 	- Lo que tengamos que hacer.
> 	- De la gente que realiza la prueba.
> - No es que "nos pasamos de un enfoque a otro" (negro <-> blanco <-> gris). Podemos estar aplicando los 3 enfoques a la vez y que los enfoques nunca se crucen el uno con otro.

---

(Control U6) ¿Qué es una prueba de caja blanca?
?
- Prueba estructural del SW:
	- Es un método de SW Testing en el cual **la estructura interna, el diseño y la implementación del SW es conocido por el Tester**.
	- The tester chooses inputs to exercise paths through the code and determines the appropriate outputs. Programming know-how and the implementation knowledge is essential. White box testing is testing beyond the UI and into the nitty-gritty of a system.
- El Tester elige qué valores de entrada utilizar para ejecutar ciertos caminos en el código, conociendo la potencial salida de ese camino.
- En este tipo de pruebas, es esencial que el Tester conozca el lenguaje de programación con el que el SW fue construido, debido a que se basa en cómo está estructurado el componente internamente y su definición.
- Se lo conoce como caja blanca porque desde el punto de vista del Tester, se puede ver cómo el SW está construido.
- Se lo utiliza también para incrementar el grado de cobertura de la lógica interna del componente.
<!--SR:!2025-06-25,1,230-->

En White Box Testing, además de saber ==1;;"qué" (importancia sobre las E/S)==, conocemos el ==1;;"cómo" (construcción)==.
<!--SR:!2025-06-25,1,230-->

El enfoque de caja blanca posee una ==1;;mayor complejidad==.
<!--SR:!2025-06-25,1,230-->

En el enfoque de caja blanca el tester debe ser capaz de ==1;;leer código==, cosa que muchas veces no sucede.
<!--SR:!2025-06-25,1,230-->

(Control U6) ¿Qué técnicas de caja blanca conoce?
?
- Grados de cobertura:
	- Cobertura de Sentencias:
		- Prueba de cada instrucción.
	- Cobertura de Decisiones:
		- Prueba de cada salida de un "IF" o "WHILE".
		- Tabla de decisión.
	- Cobertura de Condiciones:
		- Prueba cada expresión lógica (A AND B) de los IF, WHILE.
		- Tabla de verdad.
	- Prueba del Camino Básico:
		- Prueba todos los caminos independientes.
		- Complejidad ciclomática.
			- Mediante # de regiones.
			- Mediante fórmula.
<!--SR:!2025-06-25,1,230-->

Los enfoques de pruebas (negro, blanco o gris) son definidos en base a:
?
- Lo que tengamos que hacer.
- De la gente que realiza la prueba.
<!--SR:!2025-06-25,1,230-->

---

### Grados de cobertura (En orden CRECIENTE de cobertura)

> 1 -> menor cobertura | 4 -> mayor cobertura

1. Cobertura de Sentencias:
	- Prueba de cada instrucción.
2. Cobertura de Decisiones:
	- Prueba de cada salida de un "IF" o "WHILE".
	- Tabla de decisión.
3. Cobertura de Condiciones:
	- Prueba cada expresión lógica (A AND B) de los IF, WHILE.
	- Tabla de verdad.
4. Prueba del Camino Básico:
	- Prueba todos los caminos independientes.

> [!NOTE]
>
> Debido a que conocemos el código, nos damos cuenta que podemos tener un grado o % de cobertura de lo que estamos probando.

![[07.7-caja-blanca-ejemplo-clase.png]]

> [!NOTE]
>
> En la imagen falta la prueba del camino básico (complejidad ciclomática).

```js
function foo(a, b, c) {
  console.log('start of foo'); // 1
  console.log(`values are: a=${a} | b=${b} | c=${c}`); // 2
  if (a > b || b > c) { // 3
    console.log('a > b || b > c'); // 4
  } else {} // 5 -> De alguna forma se expande an 5a, 5b y 5c.
  console.log('end of foo'); // 6
}
```

- Cobertura de sentencias:
	- Una cobertura de sentencias del 100% implica probar las líneas:
		- 1.
		- 2.
		- 3.
		- 4.
		- 6.
		- Observación: para la cátedra, la línea 5 no es una sentencia ya que no posee ninguna instrucción "que haga algo".
- Cobertura de decisiones:
	- Una cobertura de decisiones del 100% implica probar las líneas:
		- 1.
		- 2.
		- 3: es la sentencia condicional per sé.
		- 4: es una salida de la sentencia condicional.
		- 5b: es la otra salida de la sentencia condicional.
			- 5a sería la línea que contiene al "} else {".
			- 5c sería la línea que contiene a la "}".
		- 6.
- Cobertura de condiciones:
	- Una cobertura de condiciones del 100% implica probar las líneas:
		- 1.
		- 2.
		- 3: existen 4 posibles combinaciones: (por lo cuál son 4 "puntitos rojos")
			- F || F
			- F || V
			- V || F
			- V || V
		- 4: se da para los casos en que se evalúen en Verdadero la sentencia if:
			- F || V
			- V || F
			- V || V
		- 5: se da para el caso en que se evalúe en False la sentencia if:
			- F || F
		- 6: siempre se ejecuta y se llega por 2 caminos (sea mediante if o else).
		- Observación:
			- Debe haber un "puntito rojo" menos en la rama "No" del condicional.
			- Debe haber un "puntito rojo" más en la rama "Si" del condicional.
			- Esto es porque el else solamente se ejecuta cuando la sentencia if se evalúa en Falso: F || F

> [!IMPORTANT]
>
> - El análisis anterior es teniendo en cuenta que para la cátedra una "sentencia" es un código que realiza una instrucción.
> - En JavaScript existen los bloques de sentencias vacías, las cuáles técnicamente son "sentencias", pero no encaja en la definición que toma la cátedra.

![[07.4-diagrama-flujo.png]]

---

(Control U6) ¿Qué es cobertura cuando hablamos de testing?
?
- La cobertura de código es un parámetro con el que se puede saber qué parte del archivo fuente ha sido sometido a pruebas.
- Es muy útil para evaluar la calidad del conjunto de pruebas.
<!--SR:!2025-06-25,1,230-->

Nombrar los grados de cobertura en orden creciente de cobertura.
?
1. Cobertura de Sentencias:
	- Prueba de cada instrucción.
2. Cobertura de Decisiones:
	- Prueba de cada salida de un "IF" o "WHILE".
	- Tabla de decisión.
3. Cobertura de Condiciones:
	- Prueba cada expresión lógica (A AND B) de los IF, WHILE.
	- Tabla de verdad.
4. Prueba del Camino Básico:
	- Prueba todos los caminos independientes.
- ![[07.7-caja-blanca-ejemplo-clase.png]]
<!--SR:!2025-06-25,1,230-->

---

#### Cobertura de decisiones

- Ejemplo: Cálculo Raíz Cuadrada.
	- Ej. Caso de Clase Válida: 4.
	- Ej. Caso de Clase Inválida: -10.
- Un mismo conjunto de casos de prueba puede ofrecer distintos grados de cobertura en distintas implementaciones de una función.

![[07.1-cobertura-decisiones-sqrt.png]]

> [!NOTE]
>
> - Cada una de las implementaciones de sqrt hacen lo mismo como resultado, pero su implementación es distinta.
> - Por ende, los casos que necesitaremos para poder probar son distintos uno del otro.
> - Caja negra: si alguien es matemático, prueba la raíz de un valor menor a 0, la raíz de 0 y la raíz de un número positivo. Esto lo definimos en función del dominio de la raíz cuadrada: casos inválidos son los número negativos y los casos válidos todos los números positivos con el 0.
> - Caja blanca: **Los casos de prueba lo definimos leyendo el código**, para lograr la cobertura.
> 	- Implementación 1:
> 		1. Probamos un número < 0.
> 		2. Probamos un número > 0.
> 	- Implementación 2:
> 		1. Probamos un número < 0.
> 		2. Probamos un número == 0.
> 		3. Probamos un número > 0.
> 	- Implementación 3: Se prueba solamente una condición de error (status).

---

V o F. Un mismo conjunto de casos de prueba puede ofrecer distintos grados de cobertura en distintas implementaciones de una función.::V, cada una de las implementaciones hacen lo mismo como resultado (funcionalmente), pero su implementación es distinta.
<!--SR:!2025-06-25,1,230-->

---

#### Camino básico

Cuando hablamos de camino básico: es la representación de un flujo de control de una pieza de código a través de un grafo de flujo.

![[07.2-camino-basico.png]]

---

Cuando hablamos de ==1;;camino básico==: es la representación de un ==1;;flujo de control== de una pieza de código a través de un ==1;;grafo== de flujo.
<!--SR:!2025-06-25,1,230-->

---

##### Ejemplo

![[07.3-ejemplo-camino-basico-grafo.png]]

![[07.3-ejemplo-camino-basico-codigo.png]]

### Complejidad Ciclomática

- Métrica del SW que proporciona una medición cuantitativa de la complejidad lógica de un programa:
	- Calcula la cantidad de caminos independientes.
	- Camino independiente: agrega un nuevo conjunto de sentencias de procesamiento o una nueva condición.
		- e.g., un if posee 2 caminos independientes.
	- Me ayuda a probar la cobertura de decisiones. Plantea todas las combinaciones posibles.
- Formas de calcularla:
	- Número de regiones del grafo.
	- $$V(g) = A - N + 2, A: aristas \land N: nodos$$

> [!NOTE]
>
> Cuando hablamos de camino básico, hablamos de complejidad ciclomática.

> [!IMPORTANT]
>
> En obras posteriores, también en SonarQube, se habla del concepto de "complejidad cognitiva", pero la cátedra no lo da como temario => Tomar que la "complejidad cognitiva" = "complejidad ciclomática".

---

(Control U6) ¿Qué es la complejidad ciclomática y para qué sirve en testing?
?
- Es una métrica del SW.
- Sirve como una medición cuantitativa de la complejidad lógica de un programa.
	- Calcula la cantidad de caminos independientes.
		- Camino independiente: agrega un nuevo conjunto de sentencias de procesamiento o una nueva condición.
			- e.g., un if posee 2 caminos independientes.
	- Permite probar la cobertura de decisiones. Plantea todas las combinaciones posibles.
<!--SR:!2025-06-25,1,230-->

¿Cómo se calcula la complejidad ciclomática?
?
Existen 2 formas de hacerlo:
- Número de regiones del grafo.
- $$V(g) = A - N + 2, A: aristas \land N: nodos$$
<!--SR:!2025-06-25,1,230-->

Cuando hablamos de camino básico hablamos de ==1;;complejidad ciclomática==.
<!--SR:!2025-06-25,1,230-->

"Complejidad cognitiva" es lo mismo que decir ==1;;"complejidad ciclomática"==.
<!--SR:!2025-06-25,1,230-->

---

#### Mediante # regiones del grafo

![[07.5-complejidad-ciclomatica.png]]

> [!NOTE]
>
> - Existen 4 áreas cerradas.
> - La región exterior también es considerada un área cerrada.
> - No cuenta áreas de áreas.

---

V o F. Es posible tener una complejidad ciclomática de 0.::F, la complejidad ciclomática es >= 1 siempre.
<!--SR:!2025-06-25,1,230-->

---

#### Mediante fórmula

$$V(g) = A - N + 2 => V(g) = 11 - 9 + 2 = 4$$

#### Conclusiones

- En este caso 4 representa que "tendremos 4 caminos básicos" => Definir 4 casos de prueba diferentes para cubrir todos los caminos básicos.
- Si tuviésemos otro SW que posee una complejidad ciclomática de 8, quiere decir que:
	- Es el doble de complejo lógicamente que el de complejidad ciclomática 4.
	- Debemos definir más casos para probar: existen 4 caminos básicos más para probar.
- Por ambas formas deben dar lo mismo: por regiones = por fórmula.
- La complejidad ciclomática permite darnos una idea de qué tan rápido podemos mantener una lógica de SW, tiempo aproximado que incurriríamos para testear dicho componente y el grado de comprensibilidad de dicha lógica de SW para los devs.

---

Una complejidad ciclomática de 4 quiere decir que tendremos ==1;;4 caminos básicos==, por lo que debemos definir ==1;;4 casos de prueba== diferentes para cubrir todos los ==1;;caminos básicos==.
<!--SR:!2025-06-25,1,230-->

Que un SW que posee una complejidad ciclomática de 8, quiere decir que:
?
- Es el doble de complejo lógicamente que uno de complejidad ciclomática 4.
- Debemos definir más casos para probar: existen 4 caminos básicos más para probar.
<!--SR:!2025-06-25,1,230-->

La complejidad ciclomática permite darnos una idea de qué tan rápido podemos:
?
- Mantener una lógica de SW.
- Tiempo aproximado que incurriríamos para testear dicho componente.
- El grado de comprensibilidad de dicha lógica de SW para los devs.
<!--SR:!2025-06-25,1,230-->

---

## Acerca de la generación de condiciones & casos

- Ninguna técnica es completa.
- Las técnicas atacan distintos problemas.
- Lo mejor es combinar varias de estas técnicas para complementar las ventajas de cada una.
- Sin especificaciones de requerimientos todo es muchísimo mas difícil.
- Debemos tener en muy en cuenta la **[[#Conjetura de errores|conjetura de errores]]**.

## Conclusiones

- Ningún método por sí solo es super eficiente => Lo más recomendable en cualquier estrategia y plan de testing que hagamos es combinar diferentes métodos. Métodos tanto:
	- [[01-conceptos-generales#Paragua de SQA|Estáticos]].
	- [[01-conceptos-generales#Paragua de SQA|Dinámicos]].
- La idea es combinar distintas estrategias con la finalidad de encontrar la mayor # de defectos posibles.
- Si tuviésemos todo el tiempo del mundo posible, haríamos caja blanca a todo. No obstante, es imposible.
- Definir en la estrategia de pruebas, por ejemplo, si todos los PRs tendrán la misma intensidad de revisión o no, entre otros.

---

Lo más recomendable en cualquier estrategia y plan de testing es combinar diferentes métodos ==1;;estáticos== y ==1;;dinámicos==.
<!--SR:!2025-06-25,1,230-->

V o F. Ninguna técnica es completa y super eficiente por sí sola.::V
<!--SR:!2025-06-25,1,230-->

V o F. Las técnicas atacan distintos problemas.::V
<!--SR:!2025-06-25,1,230-->

V o F. Lo mejor es combinar varias de estas técnicas para complementar las ventajas de cada una.::V
<!--SR:!2025-06-25,1,230-->

---
