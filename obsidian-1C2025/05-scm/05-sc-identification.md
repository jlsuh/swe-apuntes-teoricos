---
tags:
- flashcards/swe/teoria/2P
---

# Overview

- Identificar items a ser Controlados.
- Identificar items de 3° o bibliotecas.

> [!NOTE]
>
> SWEBOK:
>
> También:
> - Establece esquemas de identificación de los items y sus versiones.
> - Establece las herramientas y técnicas a ser empleadas en adquirir y gestionar los items controlados.
> - Sirve de base para otras actividades del SCM.

> [!NOTE]
>
> - Como parte de la identificación del SCM, debemos tener presente los items de 3° o bibliotecas:
> 	- e.g., emplear la suite de la API de MercadoPago para no tener que desarrollar una pasarela de pago. El día de mañana, si MercadoPago nos modifica un parámetro en uno de sus EP => Nuestra aplicación explota.
> 	- e.g., volver a programar el mismo sistema pero en otro lenguaje, sin tener el código del sistema anterior a mano y que está en otro lenguaje, con solo ver cómo funciona al ejecutarse. En este caso es de interés tener a un componente de 3° bajo el SCM, ya que tomamos la decisión de mantener vigente un sistema **muy** _legacy_.
> 		- Usualmente el vendor del componente de 3° avisa el _end-of-life_ del producto, incluyendo su soporte asociado. Como empresa, lo coherente es migrar a la nueva versión.
> 	- e.g., por el simple hecho de que el _vendor_ puede definir los cambios => Hay que administrarlo.
> - Una buena práctica es emplear "conectores" (_adapters_) contra items de 3° o bibliotecas.
> - Además de las APIs por parte de 3°, nos pueden también afectar las DBs, compiladores, web servers, entre otros.

---

V o F. En caso de que se trate de un componente externo/dependencia (sea biblioteca, APIs, DBs, compiladores, web servers, etc.), la "modificación" proviene del simple hecho de que los vendors tienen la potestad de agregar más funcionalidad a dicho producto que estamos consumiendo como dependencia y, como consecuencia, hacer "bump" de la versión.::V, debido a que dicho componente de 3° no es nuestro, el vendor tiene la potestad de definir los cambios, por lo que tenemos que administrarlo.
<!--SR:!2025-06-22,1,230-->

---

# Identificación de la configuración

> Establecer cómo está compuesto nuestro SW.

- Es la actividad de definir qué elementos (ICs) estarán controlados por la gestión de configuración, ya que no todos los artefactos necesitan ser gestionados para garantizar la integridad del producto (1).
- La identificación de la configuración define:
	- Guías y criterios para entender qué elementos son parte o no de una configuración.
	- Momentos o condiciones para establecer una línea de base o bien para liberarla (es decir llevarla a otro ambiente, también conocido como "release").

> [!NOTE]
>
> 1. e.g., "garantizar la integridad del producto": que la versión productiva no sea la V2.0, cuando en realidad dice ser que es la V2.1.

La actividad tiene que identificar los ICs que serán gestionados. Para ello, se pueden ejecutar distintas acciones, como por ejemplo:

- Identificar Código:
	- Buscar fuentes.
	- Chequear repositorios.
	- Entender la arquitectura.
- Identificar ambientes de ejecución:
	- Tratar de instalar una versión.
		- ¿Qué versión del SW se encuentra en cada ambiente (Producción, staging, testing, etc.)?
	- Identificar bases de datos, servers, configuraciones.
- Identificar Documentación:
	- Buscar especificaciones.
	- Entender cambios anteriores.
		- ¿Trabajando sobre versión final / anterior?

---

(Control U5) ¿Qué actividades principales abarca la Identificación de la Configuración?
?
Todo se basa en identificar:
- Items a ser Controlados.
- Items de 3° o bibliotecas.
- Ejemplos:
	- Identificar Código:
		- Buscar fuentes.
		- Chequear repositorios.
		- Entender la arquitectura.
	- Identificar ambientes de ejecución:
		- Tratar de instalar una versión.
			- ¿Qué versión del SW se encuentra en cada ambiente (Producción, staging, testing, etc.)?
		- Identificar bases de datos, servers, configuraciones.
	- Identificar Documentación:
		- Buscar especificaciones.
		- Entender cambios anteriores.
			- ¿Trabajando sobre versión final / anterior?
	- Entre otros.
<!--SR:!2025-06-22,1,230-->

¿En qué consiste la identificación de la configuración?
?
Es la actividad de definir qué elementos (ICs) estarán controlados por la gestión de configuración, ya que no todos los artefactos necesitan ser gestionados para garantizar la integridad del producto.
<!--SR:!2025-06-22,1,230-->

La identificación de la configuración define ==1;;guías / criterios== para entender ==1;;qué elementos son parte o no== de una ==1;;configuración==.
<!--SR:!2025-06-22,1,230-->

La identificación de la configuración define ==1;;momentos o condiciones== para establecer ==1;;una línea de base== o bien para ==1;;liberarla (es decir llevarla a otro ambiente, también conocido como "release")==.
<!--SR:!2025-06-22,1,230-->

---

## Pasos para identificar un IC

Debido a que un item de configuración puede ser cualquier entregable del proyecto. Entonces:

- ¿Qué entregables deberían ser ICs?
- ¿Qué cosas deberían suceder para pensar que potencialmente es un IC?

Características que identifican si un componente es o no definible como un IC dentro del plan de SCM:

1. Debe ser un componente principal de nuestro proceso de desarrollo.
	- e.g., en Scrum, son buenos candidatos a ser ICs los componentes: Product Backlog, Sprint Backlog e Increment.
	- ¿Hace al producto SW?
	- ¿Es parte importante del producto SW?
	- ¿Es un item importante para todo el proyecto?
2. Debe ser un componente que vaya a sufrir cambios en el tiempo.
	- ¿Varía su versión?
3. Debe ser un componente compartido entre 2 o más personas / entre varias personas.
	- ¿Requerido por todo el equipo?
4. Posee relación con otros items (trazabilidades verticales y horizontales).

> [!IMPORTANT]
>
> - Para que sea un item de configuración: Un IC NO necesariamente debe cumplir si o si con los 4 criterios.
> - La idea es evaluar los 4 criterios y en función de estos definir si es o no un IC.

Ejemplos:
- Minuta de reunión:
	- ¿Hace al producto SW? Depende de lo que se defina en la minuta.
	- ¿Está sujeto a modificaciones? No, las definiciones de la reunión son inamovibles. Para poder consensuar otra decisión, debería ser una reunión completamente nueva.
	- ¿Compartido entre 2 o más personas? Si, todos los participantes y afectados por las decisiones de la reunión.
	- ¿Posee relación con otros items? La minuta seguramente afecte a otro conjunto de items.
	- Posee más indicios de que SI es un IC.
- IDE utilizado por desarrolladores:
	- ¿Hace al producto SW? Si, depende del lenguaje utilizado en el proyecto, existen casos en que no es relevante, pero si en otros casos, e.g., desarrollar en iOS (implica tener productos de Apple).
	- ¿Está sujeto a modificaciones? Si, un IDE sufre actualizaciones por el vendor.
	- ¿Compartido entre 2 o más personas? Si, idealmente queremos que todos utilicen el mismo.
	- ¿Posee relación con otros items? Si, posee una dependencia con el lenguaje (el lenguaje probablemente es otro IC).
	- Posee más indicios de que SI es un IC.
- Un email:
	- ¿Hace al producto SW?
		- Email de aprobación de vacaciones: No.
		- Email que contiene requerimientos del producto: Si.
	- ¿Está sujeto a modificaciones? No.
	- ¿Compartido entre 2 o más personas?
		- Email de aprobación de vacaciones: No, solo les interesa al líder y al solicitante.
		- Email que contiene requerimientos del producto: Si.
	- ¿Posee relación con otros items?
		- Email de aprobación de vacaciones: No.
		- Email que contiene requerimientos del producto: Si, seguramente afecte a otro conjunto de items.
	- Posee más indicios de que SI es un IC, suponiendo que es un email de requerimientos del producto.
- Un script SQL que permite resolver un bug en producción:
	- ¿Hace al producto SW? No, debido a que es un caso extraordinario del proyecto.
	- ¿Está sujeto a modificaciones? No, una vez empleado el script, como mucho lo adjuntamos en el ticket del bug y en principio nunca más será utilizado / modificado.
	- ¿Compartido entre 2 o más personas? No, en principio, una vez utilizado, a nadie le interesa dicho script.
	- ¿Posee relación con otros items? Si, se relaciona con la DB, el cual es un IC.
	- Posee más indicios de que NO es un IC.
- Un antivirus que no permite ejecutar un proceso.

---

¿Cuáles son las preguntas que nos tenemos que hacer respecto a las características que identifican si un componente es o no definible como un IC dentro del plan de SCM?
?
1. ¿Es un componente principal de nuestro proceso de desarrollo?
2. ¿Es un componente que sufrirá cambios en el tiempo?
3. ¿Es un componente compartido entre varias personas?
4. ¿Posee relación con otros ítems de configuración?
<!--SR:!2025-06-22,1,230-->

V o F. Para que sea un item de configuración, un IC NO necesariamente debe cumplir si o si con los 4 criterios.::V, la idea es evaluar los 4 criterios y en función de estos definir si es o no un IC.
<!--SR:!2025-06-22,1,230-->

¿Cuáles son algunos ejemplos de un IC? Pensar en las 4 preguntas.
?
- Minuta de reunión:
	- ¿Hace al producto SW? Depende de lo que se defina en la minuta.
	- ¿Está sujeto a modificaciones? No, las definiciones de la reunión son inamovibles. Para poder consensuar otra decisión, debería ser una reunión completamente nueva.
	- ¿Compartido entre 2 o más personas? Si, todos los participantes y afectados por las decisiones de la reunión.
	- ¿Posee relación con otros items? La minuta seguramente afecte a otro conjunto de items.
	- Posee más indicios de que SI es un IC.
- IDE utilizado por desarrolladores:
	- ¿Hace al producto SW? Si, depende del lenguaje utilizado en el proyecto, existen casos en que no es relevante, pero si en otros casos, e.g., desarrollar en iOS (implica tener productos de Apple).
	- ¿Está sujeto a modificaciones? Si, un IDE sufre actualizaciones por el vendor.
	- ¿Compartido entre 2 o más personas? Si, idealmente queremos que todos utilicen el mismo.
	- ¿Posee relación con otros items? Si, posee una dependencia con el lenguaje (el lenguaje probablemente es otro IC).
	- Posee más indicios de que SI es un IC.
- Un email:
	- ¿Hace al producto SW?
		- Email de aprobación de vacaciones: No.
		- Email que contiene requerimientos del producto: Si.
	- ¿Está sujeto a modificaciones? No.
	- ¿Compartido entre 2 o más personas?
		- Email de aprobación de vacaciones: No, solo les interesa al líder y al solicitante.
		- Email que contiene requerimientos del producto: Si.
	- ¿Posee relación con otros items?
		- Email de aprobación de vacaciones: No.
		- Email que contiene requerimientos del producto: Si, seguramente afecte a otro conjunto de items.
	- Posee más indicios de que SI es un IC, suponiendo que es un email de requerimientos del producto.
- Un script SQL que permite resolver un bug en producción:
	- ¿Hace al producto SW? No, debido a que es un caso extraordinario del proyecto.
	- ¿Está sujeto a modificaciones? No, una vez empleado el script, como mucho lo adjuntamos en el ticket del bug y en principio nunca más será utilizado / modificado.
	- ¿Compartido entre 2 o más personas? No, en principio, una vez utilizado, a nadie le interesa dicho script.
	- ¿Posee relación con otros items? Si, se relaciona con la DB, el cual es un IC.
	- Posee más indicios de que NO es un IC.
- Un antivirus que no permite ejecutar un proceso.
<!--SR:!2025-06-22,1,230-->

---

## Posterior a la identificación de un IC

- Cualquier elemento definido como un IC: Conformará parte de nuestro plan de SCM y luego lo tenemos que reflejarlo en alguna herramienta (repositorio) para lograr el seguimiento y proceso de un IC.
- Esto implica un esfuerzo y recursos: Requiere evaluar el _trade-off_ costo-beneficio.
- Pensar la "intensidad" de SCM aplicado a cada uno de los ICs definidos.
	- No todos los elementos poseen la misma intensidad / nivel de seguimiento / posibilidad de vuelta atrás, entre otros.
	- e.g., sabiendo que en un fragmento de código se cambió exactamente 1 línea de la V1 a la V2, en caso de querer volver de la V2 a la V1, si es posible, ya que tenemos todas las versiones guardadas. En cambio, en un documento, probablemente no tengamos todo ese escrutinio realizado y simplemente tengamos la última versión vigente en el cuerpo del documento, reflejando en una grilla de versionamiento los cambios que sufrió de una versión a la otra. En caso de querer volver a la versión anterior no será posible, pero considerado como correcto el hecho de que no se pueda, ya que consideramos que no es importante volver a la versión anterior como en el código.
	- e.g., en el proceso de revisión, validación y participación de las KAs del SWEBOK, cada línea del documento posee un identificador único, siendo éstas una especie de ICs. Es importante tener este nivel de granularidad en un documento mundial, pero en otro documento sería completamente inútil hacerlo.
	- El versionado es posible conseguirlo en las herramientas empleadas.
	- En cada proyecto / organización se debe evaluar la forma de trabajo y la relevancia de cada uno de los items.

---

V o F. Cualquier elemento definido como un IC conformará parte de nuestro plan de SCM y luego lo tenemos que reflejarlo en alguna herramienta (repositorio) para lograr el seguimiento y proceso de un IC.::V
<!--SR:!2025-06-22,1,230-->

V o F. El seguimiento y proceso de un IC implica un esfuerzo y recursos: Requiere evaluar el _trade-off_ costo-beneficio.::V
<!--SR:!2025-06-22,1,230-->

¿Qué se debe ponderar posterior a la identificación de un IC?
?
Se debe pensar la "intensidad" de SCM aplicado a cada uno de los ICs definidos.
- No todos los elementos poseen la misma intensidad / nivel de seguimiento / posibilidad de vuelta atrás, entre otros.
- e.g., sabiendo que en un fragmento de código se cambió exactamente 1 línea de la V1 a la V2, en caso de querer volver de la V2 a la V1, si es posible, ya que tenemos todas las versiones guardadas. En cambio, en un documento, probablemente no tengamos todo ese escrutinio realizado y simplemente tengamos la última versión vigente en el cuerpo del documento, reflejando en una grilla de versionamiento los cambios que sufrió de una versión a la otra. En caso de querer volver a la versión anterior no será posible, pero considerado como correcto el hecho de que no se pueda, ya que consideramos que no es importante volver a la versión anterior como en el código.
- e.g., en el proceso de revisión, validación y participación de las KAs del SWEBOK, cada línea del documento posee un identificador único, siendo éstas una especie de ICs. Es importante tener este nivel de granularidad en un documento mundial, pero en otro documento sería completamente inútil hacerlo.
- El versionado es posible conseguirlo en las herramientas empleadas.
- En cada proyecto / organización se debe evaluar la forma de trabajo y la relevancia de cada uno de los items.
<!--SR:!2025-06-22,1,230-->

---

## ¿Qué elementos se registran de un IC?

> ¿Qué elemento es indispensable guardar respecto a un IC?

- En general, es importante identificar para cada IC los siguientes atributos:
	- Nombre.
	- Versión.
	- Autor / Revisores.
		- ¿Lo hizo otra persona y lo aprobé? ¿Revisión de a pares?
	- Módulos o items relacionados.
		- ¿Con qué módulos / items se relaciona?
	- Última modificación.
	- Tipo de IC (código, scripts, diagramas, requerimientos, etc.)
	- [[#Posterior a la identificación de un IC|Algún atributo más]] que nos pueda interesar respecto a cada tipo de IC.
		- "Jerarquías": Existen aspectos más vitales que otros.
- Estos atributos serán registrados y se utilizarán como información útil en la actividad de Status Accounting de la configuración.

---

¿Qué elemento es indispensable guardar respecto a un IC?
?
- En general, es importante identificar para cada IC los siguientes atributos:
	- Nombre.
	- Versión.
	- Autor / Revisores.
		- ¿Lo hizo otra persona y lo aprobé? ¿Revisión de a pares?
	- Módulos o items relacionados.
		- ¿Con qué módulos / items se relaciona?
	- Última modificación.
	- Tipo de IC (código, scripts, diagramas, requerimientos, etc.)
	- [[#Posterior a la identificación de un IC|Algún atributo más]] que nos pueda interesar respecto a cada tipo de IC.
		- "Jerarquías": Existen aspectos más vitales que otros.
<!--SR:!2025-06-22,1,230-->

Los atributos registrados respecto a un IC se utilizarán como ==1;;información útil== en la actividad de ==1;;Status Accounting de la configuración==.
<!--SR:!2025-06-22,1,230-->

---
