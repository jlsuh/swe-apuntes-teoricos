---
tags:
- flashcards/swe/teoria/1P
- flashcards/swe/teoria/U2
---

# Lo mejor de todos los mundos

- Los usuarios quieren lo mejor de todos los mundos:
	- Desarrollo de SW instantáneo, sin costo y sin defectos: imposible.
	- Cada vez en más dominios "rápido, barato y mejor" se traduce en "lo suficientemente rápido, lo suficientemente barato y lo suficientemente bueno".
- El concepto de "SWLSB" desafía nuestros prejuicios:
	- Un defecto sobre un cierto SW puede hacer que no sea un "SWLSB", mientras que otros productos SW enlatados y conocidos, con varios defectos, sugieren que dichos productos son "SWLSB".
- El concepto de "SWLSB" desafía nuestra forma de gestionar el desarrollo de SW.
- Sustento: El approach "SWLSB" nos permite:
	- Que un proyecto de desarrollo de SW sea más racional.
	- **Una forma más racional de negociar respecto a "qué es lo que constituye como éxito"** con nuestros clientes y gerentes.

> [!TIP]
>
> **Rápido, bueno y barato nunca pueden ir juntas**. _Just choose 2_.

> [!TIP]
>
> - "SWLSB": No buscar cumplir por de más por una autoexigencia.
> - Puede pasar que tengamos el concepto de "SW de calidad" como un SW con 0 defectos, lo cual es incorrecto y no benigno.

> [!TIP]
>
> ¿Cuándo aplica el concepto "SWLSB"?
>
> Ejemplo: En un contexto de un sistema crítico / de tiempo real, el concepto "no aplicaría" o bien "aplicaría de otra forma".
> 	- En un sistema de un avión: Los cambios se realizan tal que se pide a 2 equipos distintos que lo implementen, para ver si ambos cumplen con lo mismo y que un SW sea el auditor del otro SW. En este caso debe ser "bueno", no sabemos si "rápido" y el "barato" no nos preocupa (en este caso no nos importa lo "barato") (también, en un avión, existen varios sistemas con el fin de pasarse al mismo ante alguna falla: si falla el 1° -> pasa al 2° -> si falla el 2° -> pasa al 1° del otro proveedor -> ...).
> 	- Otro ejemplo es Gmail: Hubo varios años en donde se mantuvieron en una versión beta, hasta que evolucionó a la versión productiva. Durante los años en la versión beta, tuvieron varios defectos, pero aún con estos defectos era mejor que el resto de los web mails del mercado en dicho momento (todos se pasaban a Gmail aunque tuviera defectos). En este caso logró acaparar al mercado y el mercado fue ocupado por Gmail.

---

V o F. La definición de "SW lo suficientemente bueno" es distinto según el tipo de SW.::V. Un SW con un cierto defecto puede no ser considerado un SWLSB, mientras que otro SW con un cierto defecto si.
<!--SR:!2025-05-06,2,249-->

¿Qué permite el approach "SW lo suficientemente bueno"?
?
Nos permite:
- Que un proyecto de desarrollo de SW sea más racional.
- **Una forma más racional de negociar respecto a "qué es lo que constituye como éxito"** con nuestros clientes y gerentes.
<!--SR:!2025-05-05,1,208-->

V o F. Rápido, bueno y barato podrían llegar a ir juntas.::F. Nunca pueden ir juntas.
<!--SR:!2025-05-06,2,248-->

(Control U2) ¿Hay alguna diferencia entre el enfoque presentado por Ed Yourdon en "When Good Enough"... a decir: "lo mando así como está y que sea lo que Dios quiera..."?
?
Si, la diferencia yace en que:
- "Good Enough" **no implica baja calidad**, sino que se prioriza lo esencial para cumplir con los objetivos del proyecto.
- "Lo mando así como está y que sea lo que Dios quiera..." implica falta de definición respecto a "qué es lo que constituye al éxito".
<!--SR:!2025-05-05,1,230-->

---

# Ideal mal aplicado

- Se solía negociar los factores del éxito una única vez al inicio del proyecto.
- Siempre nos dicen que debemos entregar un sistema SW con:
	- Una cierta (usualmente ambigua, mal entendida y pobremente documentada) cantidad de **funcionalidades**.
	- Dentro de un cierto **tiempo** (optimistamente histérico).
	- Y **presupuesto** (impuesto por decreto) .
	- Con un **personal** (relativamente fijo) de desarrolladores.
- Posteriormente, dentro de estas restricciones, los desarrolladores intentaban optimizar unos cuántos otros parámetros que el cliente no estaba al tanto: mantenibilidad, portabilidad, fiabilidad y eficiencia.
- SW críticos:
	- e.g., sistemas de aviación o bancarios.
	- En estos, es esencial la ausencia de errores.
- SW no críticos: Sistemas en donde otros factores como:
	- La **rapidez de entrega al cliente**: Es más importante que la **cantidad de defectos**.
	- La **riqueza en la cantidad de funcionalidades**: Puede ser que sea el **factor más importante**.
	- El **costo**: Puede ser que sea lo **único que le importe al cliente**.

> [!IMPORTANT]
>
> **La cantidad de defectos es un parámetro más.**

---

Se sabe que en los SW críticos / de tiempo real, es esencial la ausencia de errores. En caso de los SW no críticos, ¿cuáles son factores que podrían llegar a considerarse?
?
- La **rapidez de entrega al cliente**: es más importante que la **cantidad de defectos**.
- La **riqueza en la cantidad de funcionalidades**: puede ser que sea el **factor más importante**.
- El **costo**: puede ser que sea **lo único que le importe al cliente**.
<!--SR:!2025-05-05,1,209-->

---

# Cuando "lo mejor" no lo es

- Las expectativas en el desarrollo de SW han cambiado debido a que la tecnología se ha convertido en un producto de consumo masivo, accesible y económico.
- Antes: los sistemas se desarrollaban a medida, con plazos largos y presupuestos altos.
- Hoy: aunque aún existen proyectos personalizados, los calendarios y presupuestos se han reducido en gran medida. Los clientes priorizan **rapidez y bajo costo**, optando muchas veces por SW comercial enlatado (como Word, Excel, etc.), a pesar de sus limitaciones, debido a que son **baratos y de alta disponibilidad**.

> [!TIP]
>
> Lo mejor no es siempre "lo mejor".

---

Los clientes priorizan ==1;;rapidez== y ==1;;bajo costo==, optando muchas veces por ==1;;SW comercial enlatado (como Word, Excel, etc.)==, a pesar de sus limitaciones, debido a que son ==1;;baratos== y ==1;;de alta disponibilidad==.
<!--SR:!2025-05-05,1,209-->

---

# Tarde nunca es mejor

- Un caso:
	1. Un cliente necesita un procesador de texto _ya mismo_ y elige entre opciones disponibles (A y B), basándose en precio y funcionalidad, aunque ninguna sea perfecta. La opción C todavía no salió al mercado, pero sus reviews lo deja como un producto muy prometedor.
	2. El usuario termina eligiendo B, aunque B tenga sus defectos.
	3. Aunque luego se lance al mercado una opción superior (C), más barata y de mejor calidad, el cliente puede rechazarla por la **molestia de migrar** (cambio de formato, sistema operativo, adaptación, etc.), aunque sea objetivamente mejor.
	4. El cliente concluye que B es lo suficientemente bueno.
- La opción B logró ser un "SWLSB" y se integró primero a la rutina del usuario.

> [!TIP]
>
> Cuando ya se está usando un SW es muy difícil cambiarlo por otro por más que este sea mucho mejor. Conviene lanzar SW mejor antes con menor cantidad de funcionalidades pero que sea "Good enough".

---

Conviene lanzar un SW ==1;;más temprano==, con ==1;;menor cantidad de funcionalidades==, pero que sea ==1;;"lo suficientemente bueno"==.
<!--SR:!2025-05-05,1,210-->

V o F. El cliente puede experimentar molestias de migrar de herramienta, aunque salga al mercado un producto objetivamente mejor que el que esté usando (cambio de formato, SO, adaptación, etc.).::V. El PM del producto que fue lanzado más temprano le ganó en viveza al PM del producto que es objetivamente mejor, incluso aunque haya perseguido el conjunto de objetivos admirable para todo profesional de SW.
<!--SR:!2025-05-06,2,249-->

---

# Cuestión de matemáticas

- Gerentes de proyectos de SW deben estar al tanto de que _cada_ parámetro es potencialmente crítico:
	- Tiempo.
	- Alcance.
	- Costo.
	- Personal (o recursos).
	- Calidad.
- **El cliente es quién decide el balance adecuado de los parámetros**.
- También, el balance entre parámetros es dinámico y debe ser reajustado diariamente:
	- El entorno cambiante del negocio se presta a cambios dramáticos e impredecibles.
	- Esto puede hacer que el cliente cambie su percepción sobre la importancia de los parámetros.
- Existen clientes que entienden que se deben realizar _trade-offs_ y balancear las prioridades, pero en la mayoría de los casos, los clientes son ingenuos respecto a los detalles:
	- e.g., puede que no se les ocurra que _los defectos_ sean un parámetro por los que debemos planificar y por los que debemos realizar _trade-offs_ con otros parámetros.
	- A los clientes no les gusta tomar decisiones racionales y calculadas respecto de dichos _trade-offs_.
- El project manager debe ser lo más detallado posible respecto a todo criterio de éxito:
	- e.g., no asumir que el cliente quiere ningún defecto, sino que aseverar algo como "Nuestro enfoque estándar para desarrollar el SW descrito requerirá X número de personas e Y unidades de tiempo, con un costo de Z $. Entregaremos P unidades de funcionalidad con un nivel de defectos de Q errores por punto de función".
- En caso de que la combinación X, Y, Z, P y Q propuesta no sea aceptable, existen 2 tipos de clientes:
	- "No pueden tener Y unidades de tiempo, necesitamos el SW en la mitad de ese plazo".
	- Un cliente menos racional: "Queremos el doble de funcionalidades de las que proponen, pero solo pueden usar la mitad del personal, la mitad del tiempo y la mitad del presupuesto".
		- La respuesta entonces es que esto sería posible, si y solamente si **el cliente relaja por completo la restricción de defectos** (supuesto poco realista). **Al fin y cabo, podemos entregar cualquier clase de SW en poco tiempo, si es que no tiene por qué funcionar :)**.
	- Algunos clientes aún menos racionales podrían fijar todos los parámetros en niveles **imposibles de alcanzar**. No obstante, es comprensible que cuestionen nuestra propuesta inicial, **siempre y cuando analicen un parámetro a la vez**.
		- e.g., si exigen reducir el plazo a la mitad, nuestra obligación es presentar una contrapropuesta que muestre cómo afectaría esto a los demás factores (costo, calidad, etc.).

> [!TIP]
>
> - **Balance entre costo, tiempo, recursos, funcionalidades y calidad (5 ejes fundamentales)**: Esto debe ser determinado por el cliente, mientras que nosotros debemos limitarnos a exhibir, mostrar ventajas y desventajas de cada uno. (Ejemplo: calculadora SW Vs. calculadora de mano).
> - Si bien es el cliente quien es el que define, como desarrolladores, gerentes de IT, representantes del área IT, tenemos "la solemne responsabilidad" de mostrarle al cliente el estado actual del SW, tal que pueda tomar decisiones (levantar la mano cuando algo no nos convence). En última instancia, la decisión del cliente pesa más ya que será este quién usará el SW.

---

¿Cuáles son los 5 ejes fundamentales (parámetros / factores) que todo gerente de un proyecto de SW debe estar al tanto?
?
- Costo.
- Calendario.
- Personal.
- Funcionalidad.
- Calidad.
<!--SR:!2025-05-05,1,228-->

¿Quién debe determinar el balance de los 5 parámetros?::El cliente.
<!--SR:!2025-05-06,2,249-->

V o F. El balance entre los 5 parámetros fundamentales debe ser reajustado diariamente.::V. El entorno cambiante del negocio se presta a cambios dramáticos e impredecibles, lo cual puede hacer que el cliente cambie su percepción sobre la importancia de los parámetros.
<!--SR:!2025-05-06,2,249-->

¿Cómo debemos actuar al momento en que el cliente comienza a cuestionar nuestra propuesta de combinación de los 5 ejes fundamentales?::Debemos estar limitados a exhibir, mostrar ventajas y desventajas de cada uno.
<!--SR:!2025-05-05,1,229-->

V o F. El cliente debería analizar todos los factores al mismo tiempo.::F. Ejemplo: si exigen reducir el plazo a la mitad, nuestra obligación es presentar una contrapropuesta que muestre cómo afectaría esto a los demás factores (costo, calidad, etc.).
<!--SR:!2025-05-06,2,248-->

(Control U2) ¿Qué significan las variables X, Y, Z, P y Q en la lectura y para que sirven?
?
Las variables X, Y, Z, P y Q representan la combinación de las variables: personal, calendario, costo, unidades de funcionalidad (alcance) y errores por punto de función (calidad / cantidad defectos), que conforman una propuesta racional al cliente. Guían la forma de cómo se debe negociar el "criterio del éxito" de un proyecto de SW, sin realizar suposiciones.
<!--SR:!2025-05-05,1,230-->

---

# The Mythical Man-Month

> [!IMPORTANT]
>
> [[06.1-ley-de-brooks#The'Man-Month|No es posible intercambiar tiempo y mano de obra linealmente]]. - Fred P. Brooks Jr.

- Podemos reducir el calendario del proyecto a la mitad, pero aumentará más que el doble en la mano de obra requerida.
- Podemos reducir el calendario del proyecto a la mitad, mantener la mano de obra constante, pero aumentará el costo en forma no lineal:
	- Teniendo presente que la mano de obra estará trabajando durante períodos de tiempos exorbitantes.

---

¿Qué sustenta Fred P. Brooks respecto al intercambio entre tiempo y mano de obra?::En su libro _Mythical Man-Month_, sustenta que no es posible intercambiar tiempo y mano de obra linealmente.
<!--SR:!2025-05-05,1,229-->

Dar 2 ejemplos de cómo variarían los factores de un proyecto de SW.
?
- Podemos reducir el calendario del proyecto a la mitad, pero aumentará más que el doble en la mano de obra requerida.
- Podemos reducir el calendario del proyecto a la mitad, mantener la mano de obra constante, pero aumentará el costo en forma no lineal:
	- Teniendo presente que la mano de obra estará trabajando durante períodos de tiempos exorbitantes.
<!--SR:!2025-05-05,1,209-->

---

# Negociando un proyecto exitoso

- La renegociación de los parámetros puede no ser tan importante para proyectos que solo duren 3 meses, pero para proyectos que duren más de 1 o 2 años, la renegociación es casi inevitable.
- Las mayores dificultades yacen sobre las políticas y los gerenciamientos.
- Es complicado el hecho de:
	- Hacer que nuestros clientes sean racionales a la hora de negociar (probablemente requiera educarlos).
	- Hacer que nuestros gerentes negocien de la forma prevista.

> It is indeed difficult to say to a customer, "I’m going to deliver a system to you in six months that will have 5000 bugs in it, and you’re going to be very happy!" But that may well be the world many of us live in for the next several years. - Edward Yourdon.

> [!TIP]
>
> - La "racionalidad" proviene del dominio: No es lo mismo construir un SW para un avión, un SW médico, un SW bancario, un juego, etc.
> - Hasta qué punto deberíamos mejorar cierta cualidad (robusto, seguro, etc.), hasta qué punto deberíamos invertir en costos, etc.
> - Ejemplo: un requerimiento de un SW es "el SW debe tener un tiempo de respuesta menor a 3 segundos", pero en la etapa de pruebas se dio una métrica de 5 segundos. En caso de comunicarle al cliente de que esto le costará un dineral, probablemente entre en razón y diga que se aguantará los 2 segundos adicionales, ya que para el cliente dicho dineral no lo vale para esos 2 segundos adicionales.

---

V o F. La renegociación de los parámetros puede no ser tan importante para proyectos que duren más de 1 o 2 años, pero para proyectos que duran 3 meses, la renegociación es casi inevitable.::F
<!--SR:!2025-05-06,2,249-->

¿Dónde yace la dificultad al momento de tener que negociar un proyecto exitoso?
?
- Hacer que nuestros clientes puedan ser racionales a la hora de negociar (probablemente requiera educarlos).
- Hacer que nuestros gerentes negocien de la forma prevista.
<!--SR:!2025-05-05,1,209-->

¿Qué quiere decir que un proyecto de SW sea "racional"?::Significa que no es posible obtener lo mejor de todos los mundos, sino que siempre debe existir una situación de _trade-off_ entre los distintos factores de calidad ponderados.
<!--SR:!2025-05-05,1,230-->

---
