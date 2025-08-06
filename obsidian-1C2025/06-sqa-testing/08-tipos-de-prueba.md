---
tags:
- flashcards/swe/teoria/2P
---

# Tipos de Prueba

## Prueba unitaria

- Se realiza sobre una unidad de código claramente definida.
- Generalmente lo realiza el área (devs) que construyó el módulo.
- Se basa en el diseño detallado.
- Comienza una vez codificado, compilado y revisado el módulo.
- Los módulos altamente cohesivos son los más sencillos de probar.

---

¿En qué consisten las pruebas unitarias?
?
- Se realiza sobre una unidad de código claramente definida.
- Generalmente lo realiza el área (devs) que construyó el módulo.
- Se basa en el diseño detallado.
- Comienza una vez codificado, compilado y revisado el módulo.
- Los módulos altamente cohesivos son los más sencillos de probar.
<!--SR:!2025-06-25,1,230-->

---

## Prueba de integración

![[08.1-pruebas-de-integracion.png]]

- Orientada a verificar que, las partes de un sistema que funcionan bien aisladamente, también lo hacen en su conjunto.
- Tipos (o formas de integraciones):
	- No Incrementales:
		- Big Bang.
	- Incrementales:
		- Bottom-Up.
		- Top-Down.
		- "Sandwich".
- Los puntos clave son:
	- Conectar de a poco las partes mas complejas.
	- Minimizar la necesidad de programas auxiliares.

---

¿En qué consisten las pruebas de integración?
?
- Orientada a verificar que, las partes de un sistema que funcionan bien aisladamente, también lo hacen en su conjunto.
- Los puntos clave son:
	- Conectar de a poco las partes mas complejas.
	- Minimizar la necesidad de programas auxiliares.
<!--SR:!2025-06-25,1,230-->

¿Cuáles son los tipos de pruebas de integración?
?
- No Incrementales:
	- Big Bang.
- Incrementales:
	- Bottom-Up.
	- Top-Down.
	- "Sandwich".
<!--SR:!2025-06-25,1,230-->

---

## Prueba de Aceptación de Usuario

- Prueba realizada por los usuarios para verificar que el sistema se ajusta a sus requerimientos.
- Las condiciones de pruebas están basadas en el documento de requerimientos.
- Es una prueba de "caja negra".
	- Es LA representación del enfoque de "caja negra".

---

¿En qué consisten las pruebas de aceptación de usuario?
?
- Prueba realizada por los usuarios para verificar que el sistema se ajusta a sus requerimientos.
- Las condiciones de pruebas están basadas en el documento de requerimientos.
- Es una prueba de "caja negra".
	- Es LA representación del enfoque de "caja negra".
<!--SR:!2025-06-25,1,230-->

---

## Prueba de Stress

- Orientada a someter al sistema excediendo los límites de su capacidad de procesamiento y almacenamiento.
- Teniendo en cuenta situaciones NO previstas originalmente.

> [!NOTE]
>
> - Se busca pasar por encima las capacidades definidas.
> - e.g., si fue pensado para 1000 transacciones por minuto => Probar con 10000.

---

¿En qué consisten las pruebas de stress?
?
- Orientada a someter al sistema excediendo los límites de su capacidad de procesamiento y almacenamiento.
- Teniendo en cuenta situaciones NO previstas originalmente.
<!--SR:!2025-06-25,1,230-->

En una prueba de stress se busca ==1;;pasar por encima las capacidades definidas==, ==1;;e.g., si fue pensado para 1000 transacciones por minuto => Probar con 10000==.
<!--SR:!2025-06-25,1,230-->

---

## Pen Testing / Ethical Hacking

- Es la práctica de testear un SW, red o aplicación web con el fin de encontrar **vulnerabilidades de seguridad** que un hacker pudiera explotar.
- El test en sí puede automatizarse utilizando aplicaciones SW o ser realizado en forma manual. De cualquier manera, el proceso involucra obtener información acerca del SW o servicio a probar, identificar potenciales puntos de entrada y reportar lo encontrado.

---

¿En qué consiste el Pen Testing / Ethical Hacking?
?
- Es la práctica de testear un SW, red o aplicación web con el fin de encontrar **vulnerabilidades de seguridad** que un hacker pudiera explotar.
- El test en sí puede automatizarse utilizando aplicaciones SW o ser realizado en forma manual. De cualquier manera, el proceso involucra obtener información acerca del SW o servicio a probar, identificar potenciales puntos de entrada y reportar lo encontrado.
<!--SR:!2025-06-25,1,230-->

---

## Prueba de Volumen

- Orientada a verificar a que el sistema soporta los volúmenes máximos definidos en la cuantificación de requerimientos:
	- Capacidad de Almacenamiento.
	- Capacidad de Procesamiento.

![[08.2-prueba-de-volumen.png]]

> [!NOTE]
>
> - Es probar el SW hacia la máxima capacidad de procesamiento o de almacenamiento que tenga, para el fin que fue diseñado.
> - e.g., si el SW hace 1000 transacciones por minuto => Probar 800, 900 y ver si funciona sin problemas.
> - A diferencia de la prueba de stress, la prueba de volumen es "probar el SW con lo que fue definido".
> - Valida si lo comprometido sirve para el fin por el que fue construido.

---

¿En qué consisten las pruebas de volumen?
?
- Orientada a verificar a que el sistema soporta los volúmenes máximos definidos en la cuantificación de requerimientos:
	- Capacidad de Almacenamiento.
	- Capacidad de Procesamiento.
- Probar el SW hacia la máxima capacidad de procesamiento o de almacenamiento que tenga, para el fin que fue diseñado.
	e.g., si el SW hace 1000 transacciones por minuto => Probar 800, 900 y ver si funciona sin problemas.
<!--SR:!2025-06-25,1,230-->

---

## Prueba de regresión

Orientada a verificar que, luego de introducido un cambio en el código, la funcionalidad original no ha sido alterada:
- Hay que probar "lo viejo".
- Re-uso de condiciones & casos.

> [!NOTE]
>
> Probar que funcionalidades relacionadas sigan funcionando bien luego de haber introducido una nueva funcionalidad que se relaciona con las que ya eran partícipes del SW.

---

¿En qué consisten las pruebas de regresión?
?
Orientada a verificar que, luego de introducido un cambio en el código, la funcionalidad original no ha sido alterada:
- Hay que probar "lo viejo".
- Re-uso de condiciones & casos.
<!--SR:!2025-06-25,1,230-->

---

## Prueba Alfa & Beta

Se entrega una primera versión al usuario que se considera está lista para ser probada por ellos:
- Normalmente plagada de defectos.
- Una forma económica de identificarlos (ya que el trabajo lo hace otro).
- En muchos casos no puede hacerse.
- Alternativa válida: ejecutar en "paralelo".
- Alfa: la hace el usuario en mis instalaciones.
- Beta: la hace el usuario en sus instalaciones.

> [!NOTE]
>
> Sirve también para calmar la ansiedad de los usuarios, ya que lo quieren ver funcionando.

---

¿En qué consisten las pruebas Alfa & Beta?
?
Se entrega una primera versión al usuario que se considera está lista para ser probada por ellos:
- Normalmente plagada de defectos.
- Una forma económica de identificarlos (ya que el trabajo lo hace otro).
- En muchos casos no puede hacerse.
- Alternativa válida: ejecutar en "paralelo".
- Alfa: la hace el usuario en mis instalaciones.
- Beta: la hace el usuario en sus instalaciones.
- Sirve también para calmar la ansiedad de los usuarios, ya que lo quieren ver funcionando.
<!--SR:!2025-06-25,1,230-->

---
