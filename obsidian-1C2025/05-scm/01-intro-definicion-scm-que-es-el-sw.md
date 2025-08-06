---
tags:
- flashcards/swe/teoria/2P
---

> [!NOTE]
>
> - General: Veremos la completitud del SCM para un proyecto relevante.
> - Particular: Adaptarlo a un caso particular es más fácil: General -> Particular.
> 	- Particular -> General: Es mucho más difícil.

> [!NOTE]
>
> Cuando estudiamos los procesos de la SWE: SCM es parte de las actividades de soporte.
> - No es el ciclo de vida en sí del proyecto o de programas.
> - Es un ciclo que acompaña a todas estas actividades de soporte.
> - Es uno de los procesos más importantes que acompaña al desarrollo de SW: Lo abarca E2E e incide sobre todo lo que se haga dentro de un proyecto.
> - "Siempre se premia al que apaga los incendios, pero nunca al que previene que un fósforo se encienda".
> - SCM no es una receta mágica, pero si permite socavar el incendio 🧯

# Introducción a la problemática

Las clásicas:

- "En mi máquina funciona".
- "Actualizamos la API, no sabíamos que todavía existen usuarios usando la v1.0".
- "Armar el entregable toma unos días".
- "¿En qué clientes estaba el bug?"
- "Pasa que probaste en el entorno de testing y no en desarrollo..."

## El problema de cualquier compañía con > 1 dev

![[01.1-problema-compania-con-mas-de-un-dev.png]]

> [!NOTE]
>
> 1) El equipo planifica: repartición de tareas y planificación de entregas.
> 2) El equipo de trabajo genera código.
> 3) Eventualmente existe un SW.
> 4) SW + Entregas = Release
> 5) Se prueba el SW en el entorno de ejecución (SW en producción).

> [!NOTE]
>
> - [[06.1-ley-de-brooks|Curva de aprendizaje]]: Incide en mayor medida sobre los temas de planificación que hemos visto en la [[01-conceptos-de-estimaciones-de-sw|primera mitad de la materia]], no tanto sobre SCM.
> - Los procesos de SCM comienzan a cobrar valor y relevancia cuando existe:
> 	- Un equipo distribuido geográficamente: distintas culturas, husos horarios.

Conclusión:

![[01.2-conclusion-problema-compania-con-mas-de-un-dev.png]]

---

V o F. SCM sirve para las compañías con > 1 dev::V
<!--SR:!2025-06-22,1,210-->

---

# Definición Gestión de Configuración de SW

La **Gestión de Configuración de SW** es:

- Una disciplina orientada a administrar la evolución de: (1)
	- **Productos**.
	- **Procesos**.
	- **Ambientes**.
- Definiendo mecanismos para administrar diferentes versiones de los mismos.
- Controlando los cambios efectuados.
- Auditando y reportando la actividad de cambios realizada.
- **Propósito**: Establecer y mantener la integridad de los artefactos del proyecto de SW a lo largo del ciclo de vida del mismo (2).

> [!NOTE]
>
> 1) La combinación de las 3 es administrado por SCM: Todo producto se ejecuta en un ambiente y tiene asociado un proceso que lo resuelve.
> 2) ¿Por qué usamos la palabra "artefacto"?
> 	- La definición aclara que SCM es "una disciplina orientada a administrar la evolución de los **Productos**".
> 	- Producto = SW.
> 	- **Productos que evolucionan**: son todas las partes que acompañan al producto:
> 		- Modelos / Documentación.
> 		- Manual de usuario / Capacitación.
> 		- Especificaciones del usuario.
> 		- El código del SW.
> 		- Archivos de configuraciones.
> 		- Scripts.
> 		- Servidores.
> 		- Bases de datos.
> 		- Entre otros.
> 	- **Pensamiento holístico**: El SW no solamente es el código.

---

¿Qué es el SCM?
?
La **Gestión de Configuración de SW** es una disciplina orientada a administrar la evolución de:
- **Productos**.
- **Procesos**.
- **Ambientes**.
<!--SR:!2025-06-22,1,210-->

V o F. El SCM administra la combinación de productos, procesos y ambientes.::V, todo **producto** se ejecuta en un **ambiente** y tiene asociado un **proceso** que lo resuelve.
<!--SR:!2025-06-22,1,210-->

(Control U5) ¿Para qué sirve el SCM?
?
Sirve para:
- Definir mecanismos para administrar diferentes versiones del producto SW.
- Controlar los cambios efectuados.
- Auditar y reportar la actividad de cambios realizados.
<!--SR:!2025-06-22,1,210-->

¿Cuál es el propósito de SCM?
?
Establecer y mantener la integridad de los artefactos del proyecto de SW a lo largo del ciclo de vida del mismo.
<!--SR:!2025-06-22,1,210-->

¿Qué es un artefacto?::Un artefacto es uno de los muchos productos derivados tangibles producidos durante el desarrollo de SW. Permiten describir la función, arquitectura, diseño del SW, proceso de desarrollo (plan de proyecto, casos de negocio y gestión de riesgos).
<!--SR:!2025-06-22,1,210-->

¿Por qué se emplea la palabra "artefacto" en SCM?
?
- La definición aclara que SCM es "una disciplina orientada a administrar la evolución de los **Productos**".
- Producto = SW.
- **Productos que evolucionan**: son todas las partes que acompañan al Producto = SW:
	- Modelos / Documentación.
	- Manual de usuario / Capacitación.
	- Especificaciones del usuario / de casos de uso.
	- El código del SW.
	- Diagramas de clases.
	- Documentos de diseño.
	- Archivos de configuraciones.
	- Scripts.
	- Servidores.
	- Bases de datos.
	- Entre otros.
- **Pensamiento holístico**: El SW no solamente es el código.
<!--SR:!2025-06-22,1,210-->

---

# ¿Qué es el SW?

![[01.3-que-es-el-sw.png]]

> [!NOTE]
>
> - Lo primero que uno piensa cuando habla de SW: Código. Pero también el resto de los elementos hace al SW: El código es una pequeña parte del SW.
> - e.g., si tenemos un código con las mejoras prácticas pero no tenemos una DB en dónde montar el código, el código es inservible.
> - e.g., desde la perspectiva de desarrollo es código, modelos y bases de datos.

---

¿Cuáles son algunos elemento que componen al SW y de alguna forma inciden en la definición del SW, dependiendo por quién lo mire?
?
- Código.
- Modelos.
- Bases de datos.
- Scripts.
- Especificaciones del usuario.
- Servidores.
<!--SR:!2025-06-22,1,210-->

---
