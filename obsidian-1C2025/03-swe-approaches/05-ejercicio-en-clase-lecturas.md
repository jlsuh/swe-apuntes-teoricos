---
tags:
- flashcards/swe/teoria/1P
- flashcards/swe/teoria/U3
---

#exam-question 

> [!NOTE]
>
> El presente ejercicio se basa en las lecturas:
> - [[03-obl-a-leader-s-framework-for-decision-making-cynefin-+-opc-sobre-cynefin|A Leader's Framework for Decision Making]].
> - [[04-obl-chapter-2-standing-on-principle|Standing on Principle]].

# Consigna

> [!NOTE]
>
> Caso [Y2K](https://en.wikipedia.org/wiki/Year_2000_problem).

Estamos en **1998** y tenemos que preparar los sistemas para el año 2000. Somos una organización gubernamental que posee varias aplicaciones inmersas en este contexto.

## Peligros

- Cuando pongamos la primer fecha en el año 2000, terminará en 00.
- Existen sistemas que poseen la fecha del año con un 00 ("doble cero") y nada más.
- Hay que asegurarse que lo interprete como el año 2000 y no como 1900, ya que "00" puede referirse tanto a 1800, 1900, 2000, etc.
- Existen sistemas que con estas fechas gestionan tecnologías operacionales (OT) y pueden conllevar riesgos:
	- Sistemas de armas nucleares.
	- Sistemas medicinales.
	- Sistemas de centrales eléctricas.
	- Sistemas de control de usinas atómicas.
	- Sistemas impositivos.
	- Entre otros.

## Objetivos

- Asegurarnos que estos se encuentren preparados para seguir funcionando bien en el año 2000. Esto implica:
	- Bucear en el código de varios sistemas que posee la organización gubernamental.
	- Realizar la reingeniería de lo que haya que recodificar.
- Para ayudarnos en esta tarea, existe una especie de Copilot / ChatGPT que, al tirarle código y este artilugio IA, nos ubica potenciales riesgos y ubicaciones en el código en donde podríamos tener conflictos y nos brinda soluciones.
- No obstante, este artilugio no está probado al 100%. Solamente hicieron un PoC con un aplicativo pequeño y vieron que funcionaba bien. Tenía unos detalles mínimos pero nada grave.

## Se pide

1. Identificar driver, restricción y grado de libertad en base a la organización teórica, en base a la lectura [[04-obl-chapter-2-standing-on-principle|Standing on Principle]]. Justificar.
2. Dentro de los dominios de Cynefin, identificar en qué dominio se encuentra la organización teórica, en base a la lectura [[03-obl-a-leader-s-framework-for-decision-making-cynefin-+-opc-sobre-cynefin|A Leader's Framework for Decision Making]]. Justificar.

# Resolución y puesta en común: Standing on Principle

## Driver

### Alcance

Esto es debido a que las funcionalidades para, e.g., un sistema de control de usinas atómicas, en caso de que haya una programación errónea respecto a las fechas en que deben acelerar los motores de refrigeración, el resultado sería catastrófico.

## Restricción

### Calidad

La **calidad** es más una **restricción**:

- Existen varios sistemas de la organización gubernamental bajo el proceso de reingeniería.
- Pueden existir sistemas no críticos que hasta podrían terminar de implementar la reingeniería posterior al año 2000.
- No obstante, existe una cantidad considerable de sistemas críticos que debemos terminar si o si para el año 2000.
- De igual manera, según cómo esté redactado el proyecto, la **calidad** podría ser un **driver** o **restricción**. Lo importante es que no es posible considerarlo como grado de libertad, ya que por los tipos de sistemas con los que estamos tratando (la gran mayoría):
	- e.g., "no se tolerará ninguna falla crítica". En este caso nos están imponiendo una restricción. No obstante, en caso de que no nos hubiesen dicho esto, la justificación correcta es que **mínimamente debemos considerarlo como un driver por los tipos de sistemas con los que estamos lidiando en su mayoría**.

## Driver && Restricción

### Tiempo

- El objetivo principal es: "preparar todos los sistemas para el año 2000".
- El año 2000 (**tiempo**) es a su vez un **driver**, ya que es el objetivo principal del proyecto, pero a su vez es algo que sucederá y no tenemos el control sobre el mismo (**restricción**).
- Existen casos en que una dimensión puede ser tanto driver como restricción, siendo éste un caso:
	- Existe la restricción del tiempo.
	- También, el tiempo es una parte vital del proyecto.

## (Driver && Grado de libertad) || (Restricción && Grado de libertad)

Es contradictorio categorizar una dimensión tal que sea un driver y un grado de libertad al mismo tiempo, o bien una restricción y un grado de libertad al mismo tiempo, ya que por definición: "**Un grado de libertad es aquello que no es driver ni tampoco restricción**".

---

V o F. Es posible tener a un driver que sea un grado de libertad a la vez, o bien una restricción que sea un grado de libertad a la vez.::F. Es contradictorio categorizar una dimensión tal que sea un driver y un grado de libertad al mismo tiempo, o bien una restricción y un grado de libertad al mismo tiempo, ya que por definición: "Un grado de libertad es aquello que no es driver ni tampoco restricción".

---

## Grados de libertad

- **Costos**: Cubrir gastos extraordinarios por período relativamente corto y evitar una mayor catástrofe.
- **Personal**: En caso de que se requiera más mano de obra, debería ser agregable, siempre y cuando las tareas no generen problemas de coordinación extrema.

## LO IMPORTANTE

Más allá de ponerle una etiqueta a cada uno, lo importante es poder tener la discusión con el equipo y que tengamos todos **una misma concepción por dónde pasa el poder de negociación** que tenemos sobre las dimensiones:
- Driver: Posee poco o nada poder de negociación.
- Restricción: No posee poder de negociación (es un golpe seco).
- Grados de libertad: Es el resto.
	- Nos podemos mover pero tampoco son infinitos.
	- Son las variables más trabajables dentro del proyecto.

## Aclaraciones que no se hicieron al inicio de la consigna

- El artilugio de IA no es obligatorio usarlo: Nunca nos dijeron "si o si hay que usar el artilugio de IA". No es una de las 5 dimensiones conocidas de un proyecto, sino que es una herramienta.
- Diferente hubiese sido que nos digan: "el proyecto debe estar hecho en Java". En dicho caso sería una restricción que guía la categorización de las dimensiones.

# Resolución y puesta en común: Cynefin

La tarea a realizar sobre los sistemas era:
- Cambiar o evaluar si un formato fecha iba a o no a funcionar.
- Las herramientas para probarlo es simplemente una máquina, cambiamos la fecha para que tenga el año 2000, luego probamos con fechas anteriores y posteriores.

De entrada descartamos:
- **Contexto simple**:
	- No existe ninguna "mejor práctica" que permita lleva a cabo la reingeniería de las fechas.
	- Es más complejo que una cuestión de percibir, categorizar y responder.
- **Contexto caótico**:
	- Sería caótico si el contexto que nos hubiesen dado era: "Estamos en octubre del 1999". Solamente nos quedarían 3 meses para la reingeniería, mucho menos tiempo que "1998".
	- Estando en 1998, no se considera todavía una situación en donde tengamos que en primer lugar actuar para "frenar el sangrado".

Veredicto de los profes:

- **Contexto complicado**: Se inclina más por el complicado.
	- El problema no es difícil: Cuestión de cambiar fechas.
	- Lo novedoso de la reingeniería: Trabajar con fechas y realizar pruebas. No existe más complejidad que esto.
	- Como mucho: Necesidad de un experto para que nos diga, e.g., el criterio empleado para el año en el sistema N:
		- Experto sistema 1: "Para el año usamos 2 dígitos, está programado como 2 números separados que posteriormente se juntan y es por ende preferible aplicar la forma de resolución X".
		- Experto sistema 2: "En nuestro caso empleamos un campo de tipo fecha y no hay mayores inconvenientes para cualquier forma de resolución que se opte".
		- Experto sistema N: "...".
- **Contexto complejo**:
	- No hay nada que nos asuste como "organización" para considerarlo como:
		- "Esto es algo _novel_".
		- "Esto es algo que jamás se ha hecho".
		- "Para esto hay una práctica emergente".

Por ende, es más cómodo en este caso justificarlo por el lado de un **contexto complicado** que por el lado de un **contexto complejo**.

# Observaciones

Es importante tratar de desplazar lo más que se pueda a los proyectos para el cuadrante del contexto simple:
- Si estamos en caótico => Llevarlo al complejo.
- Si estamos en complejo => Llevarlo al complicado.
- Si estamos en complicado => Llevarlo al simple.

Puede que tengamos otra perspectiva:
- **Si bien no existen indicios que indiquen que sea un contexto complejo**, podríamos considerar que, el primer sistema (de los N sistemas de la organización gubernamental) y acercamiento que tomemos, estaremos en un contexto complejo, ya que no hay garantías de cómo terminaremos resolviendo las fechas para un primer acercamiento, y nos vemos en la necesidad de comenzar la secuencia de toma de decisiones con el sondeo y la experimentación.
- Si podría pasar que otras mentes opinen que "es un contexto complicado con un cierto pie en el contexto complejo" => En este caso es importante justificar ("depende") correctamente y se lo tomará como bien.
- Intentaríamos de igual manera que todo caiga en el contexto complicado, en vez del contexto complejo.
- En los sistemas posteriores, luego de haber catalogado varias combinaciones de fechas, las resoluciones serán todas iguales / similares, no hay mucha historia con las fechas: Campo fecha completo, fecha cortada, fecha con números separados, suma/resta de fechas, no más que eso.
- También, estando en 1998, todavía hay tiempo: 2 años por delante.

> [!IMPORTANT]
>
> - Todo influye en las dimensiones a evaluar: El tamaño del proyecto y la complejidad.
> - En este caso es el proyecto y no el producto. El proyecto es todo lo que nos compete a nuestra organización:
> 	- Si son 2 sistemas pequeños => Es un proyecto pequeño.
> 	- Si son 7 sistemas críticos => Es otro tamaño de problema.
> - e.g., si la dimensión del proyecto se agranda tanto y el tiempo pasa a ser pequeño considerado a lo que hay que hacer para el proceso de reingeniería => El dominio se desplaza.
> - e.g., nos es lo mismo comenzar en enero de 1998 que en octubre de 1999.
> 	- "A cantidades industriales, ¿se podrá tener todo el entorno para probar en el poco tiempo que tenemos?"
> 	- "¿Es posible trabajar concurrentemente modificando 20 sistemas a la vez?"
> 	- Etc.

# En lo que respecta a parciales y finales

Si nos basamos en algún supuesto para elegir nuestra solución, es importante mencionarlo en la respuesta, ya que nos evalúan en base a estos cómo justificamos nuestra elección.

Es importante que la solución no modifique la consigna original del problema.
- e.g., en la consigna, no podría caer en el contexto caótico, ya que nos comenzamos a irnos de la consigna original.
- e.g., en caso de no haber tenido una fecha de inicio, tenemos que hacer una suposición de cuándo se nos presentó el problema. Hubiese sido muy distinto la consideración de si es o no correcta nuestra respuesta si hubiésemos supuesto "enero del 1998" Vs. "octubre del 1999".

Esto es referido para ambas lecturas.
