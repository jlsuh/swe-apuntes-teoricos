# Apuntes clase

> [!TIP]
>
> - El TP es referido a la parte "estática" del SQA: QC.
> - Le da justicia a la descripción "analizadores de código estáticos".

- SonarQube: es una variante de código estático, no solamente se queda en cuestiones de indentaciones del código, sino que también habla de cuestiones de seguridad, performance, confiabilidad, mantenibilidad, bibliotecas de 3° (CVEs, etc.), entre otros.
- Estas 2 herramientas (CheckStyle & SonarQube) la estamos viendo debido a la lectura de [[06-obl-qa-when-two-eyes-arent-enough|When Two Eyes Aren't Enough]]:
	- Existen revisiones de menos a mayor formalidad, estas herramientas justamente hacen revisiones de código, parte del QA (todo previo a la ejecución del código).
- CheckStyle: Si en nuestra organización definimos algún estándar de codificación, lo agregamos y permite controlarlos.
- Ambas herramientas:
	- Eficiencia:
		- Abaratan costos: compramos las herramientas y es más barato que tener personas revisando el código.
		- Mayor velocidad.
	- Eficacia:
		- Son las métricas que pedía el TP: de todos los errores, ¿cuántos se corrigió realmente?
		- El hecho de agregar reglas propias seguramente aumente la eficacia.
		- El factor humano (de corrección) permite mejorar la eficacia al aplicar el discernimiento y racionalidad de lo que hace la herramienta.
		- La adopción en demasía de reglas puede generar ruido constante durante el proceso de desarrollo.
- Cosas que SonarQube no puede encontrar:
	- Lógica subyacente.
	- Buenas prácticas de diseño / arquitectura.
	- Errores en tiempo de ejecución.
		- Cuestiones de concurrencia.
	- Cuestiones de accesibilidad.

> [!TIP]
>
> - SonarQube posee un máximo de complejidad cognitiva por defecto de 15, es ajustable.
> - Integrable con GitHub. El análisis de puede disparar mediante el commit a una rama principal.

## Conclusiones

- Ambas herramientas:
	- Permiten ganar en eficiencia y, puliéndolas y trabajándolas, también en eficacia.
	- Estáticas: Las actividades se relacionan al QA, previo a la ejecución del código.
- IA: Cada vez más se automatizan estos tipos de revisiones, desde distintos puntos de vista:
	- CheckStyle.
	- Calidad de código como SonarQube: deuda técnica y complejidad, otras métricas que tengan que ver con la calidad del código per sé.
	- Qué tan documentado está el código.
	- Reglas de seguridad.
- SonarQube: se encarga de brindar métricas de deuda técnica:
	1. Detecta los errores en el código.
	2. Propone el código que lo arreglaría.
	3. Estima el **esfuerzo** (estimación) que le llevaría a un dev para corregirlo (tener deuda técnica 0).
- Deuda técnica:
	- En clases se mencionó que hacen alusión a los _code smells_.
	- Está mal asumir que la deuda técnica es únicamente cosas que la herramienta captura, e.g., las definiciones arquitecturales pobres sería complejo que SonarQube lo pueda capturar. Quizás adoptar alguna herramienta de IA.
