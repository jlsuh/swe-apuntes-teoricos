---
tags:
- flashcards/swe/teoria/2P
---

# Economía del Testing

## ¿Hasta cuándo tengo que probar?

- Se puede invertir mucho esfuerzo en probar.
- Probar es el proceso de establecer confianza en que un programa hace lo que se supone que tiene que hacer.
- Ya que nunca voy a poder demostrar que un programa es correcto, continuar probando es una **decisión económica**.

> [!NOTE]
>
> - En "A + B" existen infinitos casos para probar, según conjunto de números considerados, etc. Esto nos hace pensar que el tiempo a invertir en pruebas es infinito.
> - El simple hecho de haberle dedicado tiempo al Testing y que [[13-obl-continuous-integration-martin-fowler#Hacer que el Build sea _Self-Testing_|ejecute en forma automática]], posee un costo asociado.
> - Debido a que las pruebas son infinitas y es esencial establecer un umbral de "nos sentimos cómodos con el Testing realizado", la cual es una decisión económica.
> - Previo a la herramienta de "¿Cuándo dejar de probar?", existe otra herramienta previa que es "Agrupar aquellas que sean iguales (clases de equivalencia - clustering)". Utilizar a un representante de cada clase. Si funciona bien => Asumo que el resto de los representantes funcionarán bien.
> - Si bien existen casos de prueba estandarizados por ser procesos conocidos o recomendados por algún proveedor de API de 3°, uno de los principios de Testing se lo conoce como "la paradoja del pesticida": "por cualquier cosa no es buena idea tomar un antibiótico", ya que luego el cuerpo construye tolerancia y dicho antibiótico no hace nada. Debido a que tenemos un conjunto de pruebas estándar para alguna funcionalidad conocida, e.g., conjunto estándar de pruebas para carritos de compra, aparecerán funcionalidades nuevas asociados a los carritos, los cuáles dicho conjunto original de pruebas conocidas no los detecta, por lo que hay que ir corrigiéndolos.
> 	- Es buena idea tener un conjunto conocido de pruebas, pero hay que mantenerlos actualizados y en constante vigencia.
> 	- Es posible "partir de algo".

---

Se puede invertir mucho ==1;;esfuerzo== en probar.
<!--SR:!2025-06-25,1,230-->

Probar es el proceso de establecer ==1;;confianza== en que un programa hace lo que se supone que tiene que hacer.
<!--SR:!2025-06-25,1,230-->

Ya que nunca voy a poder demostrar que un programa es correcto, continuar probando es una decisión ==1;;económica==.
<!--SR:!2025-06-25,1,230-->

---

## ¿Cuándo parar de probar?

- Nuestro Problema:
	- Imposibilidad en la práctica de estimar la intensidad del testing para alcanzar determinada densidad de defectos.
- Estrategias:
	- Pasa exitosamente el conjunto de pruebas diseñado. (1)
	- "Good Enough": cierta cantidad de fallas no críticas es aceptable (umbral de fallas no críticas por unidad de testing). (2)
	- Cantidad de fallas detectadas es similar a la cantidad de fallas estimadas. (3)

> [!NOTE]
>
> 1. ¿Pasaron las 100 pruebas del conjunto que definimos? => Listo.
> 2. "Aceptamos no tener fallas críticas, aceptamos hasta 2 fallas medias y hasta 5 fallas bajas. En caso de que en un futuro tengamos fallas críticas de tal característica, tenemos un workaround pensado." Esto define la suficiente comodidad para lanzar el SW.
> 3. Si hemos estimado en que iba a fallar 15 veces. Si fallamos entre 14 y 16 => Listo.

> [!NOTE]
>
> Estas estrategias nos permiten entender cómo aprovechar mejor los recursos para hacer pruebas de SW que nos dé la suficiente confianza y calidad para poder ser lanzado.

---

El problema es la imposibilidad en la práctica de estimar la ==1;;intensidad del testing== para alcanzar determinada densidad de ==1;;defectos==.
<!--SR:!2025-06-25,1,230-->

¿Cuáles son las estrategias para determinar "cuánto parar de probar"?
?
- Pasa exitosamente el conjunto de pruebas diseñado.
- "Good Enough": cierta cantidad de fallas no críticas es aceptable (umbral de fallas no críticas por unidad de testing).
- Cantidad de fallas detectadas es similar a la cantidad de fallas estimadas.
<!--SR:!2025-06-25,1,230-->

---

## Abaratamiento del Testing

¿Cómo hacer que el Testing sea más económico?

- Hacer pruebas es caro y trabajoso.
- La forma de abaratarlas y acelerarlas (sin degradar su utilidad) es:
	- **Diseñando el SW para ser testeado**.
- Algunas herramientas son:
	- Diseño Modular.
		- Nos abstraemos de probar "islas" ya probadas anteriormente.
	- Ocultamiento de Información.
		- "Information Hiding" en OOP.
		- Dejar bien en claro las variables globales y locales.
		- Emplear a consciencia modificadores de acceso.
	- Uso de Puntos de Control.
		- e.g., en metodologías ágiles cada Sprint debería contemplar puntos de control: Sprint Reviews.
	- Programación NO egoísta.
		- Documentar el código (incluso que sea auto documentado: expresivo).
		- Que otros puedan entenderlo.
		- PRs descriptivos.

---

Sabiendo que hacer pruebas es caro y trabajoso, la forma de abaratarlas y acelerarlas (sin degradar su utilidad) es ==1;;diseñando el SW para ser testeado==.
<!--SR:!2025-06-25,1,230-->

¿Cuáles son las herramientas para abaratar el Testing?
?
- Diseño Modular.
	- Nos abstraemos de probar "islas" ya probadas anteriormente.
- Ocultamiento de Información.
	- "Information Hiding" en OOP.
	- Dejar bien en claro las variables globales y locales.
	- Emplear a consciencia modificadores de acceso.
- Uso de Puntos de Control.
	- e.g., en metodologías ágiles cada Sprint debería contemplar puntos de control: Sprint Reviews.
- Programación NO egoísta.
	- Documentar el código (incluso que sea auto documentado: expresivo).
	- Que otros puedan entenderlo.
	- PRs descriptivos.
<!--SR:!2025-06-25,1,230-->

---
