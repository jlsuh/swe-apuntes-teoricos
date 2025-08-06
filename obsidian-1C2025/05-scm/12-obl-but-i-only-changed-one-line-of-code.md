---
tags:
- flashcards/swe/teoria/2P
---

# But I Only Changed One Line of Code!

> Introducción a conceptos básicos de SCM + Sustento lógico para su implementación.

> [!NOTE]
>
> - SCM es un concepto básico ampliamente aceptado como una de las mejores prácticas del SW.
> - Sus actividades básicas del CM usualmente son ignoradas => Impactos negativos graves sobre el desarrollo de SW y proyectos de adquisición.

## Contexto

- El autor cuenta que estuvo en un avión sentado durante 1 hora para poder despegar, pero al final no pudieron porque el piloto no pudo hacer arrancar uno de los motores.
- Un mecánico pudo determinar que el problema provenía de una manguera: la misma era esencial para garantizar el funcionamiento correcto del motor.
- El mecánico pudo:
	- Entender la configuración del motor del avión.
	- Referirse a una lista de:
		- Piezas que componen al motor.
		- Cómo interactúan entre las mismas.
		- Métodos para ensamblarlos en el avión.
- Esto es lo que se conoce como **configuración**.

## Pregunta

- Como desarrolladores de SW: ¿Es acaso menos importante que sepamos gestionar los activos que creamos?
- El SW que creamos se mantiene:
	- De distintas formas, con distintas herramientas, durante varios instancias del desarrollo.
	- En diversas ubicaciones, formatos y por diversas organizaciones.
- Los componentes de SW son compuestos por _partes_:
	- Dichas partes a su vez son SW.
	- Creados y empaquetados mediante herramientas que también son SW.
- Los sistemas SW son:
	- Compuestos por partes intangibles, que no pueden ser físicamente puestos en algún lugar o manipularlos.
- La configuración de sistemas SW son naturalmente complejos.
- En caso de perder trazabilidad:
	- Sobre una de las piezas del SW => Debemos re-crearlo.
	- Sobre una de las herramientas => Le pedimos a Dios que procurar uno nuevo no contraiga problemas 🙏🏻
		- e.g., el _vendor_ podría dejar de dar soporte o se retira del mercado.

## SCM

- "Arte de identificar, organizar y controlar las modificaciones del SW".
- Es un proceso que se debe realizar a lo largo de todo el desarrollo y mantenimiento del ciclo de vida del SW.
- Organización bien definida de:
	- Partes que componen al SW.
	- Procedimientos y herramientas empleadas para la construcción del producto o del sistema a partir de dichas partes.
		- Incluye procedimientos para reconstruir distintas versiones y releases.

---

El SCM es un proceso que se debe realizar a lo largo de todo el ==1;;desarrollo y mantenimiento del ciclo de vida del SW==.
<!--SR:!2025-06-25,1,230-->

---

### Composición

Usualmente se encuentra compuesto en 4 áreas funcionales:

- [[05-sc-identification|Configuration Identification]]:
	- Identificar activos de SW importantes para la organización.
- [[06-sc-change-control|Configuration Control]]:
	- Implica controlar los cambios a estos activos para garantizar su integridad.
- [[07-sc-status-and-accounting|Configuration Status Accounting]]:
	- Llevar un registro del estado de estos activos es importante para continuar el éxito de la organización.
- [[08-sc-auditing|Configuration Auditing]]:
	- Para asegurar que los activos de SW estén siendo debidamente registrados, se deben realizar auditorías de configuración periódicas.

![[12.1-the-basic-functions-of-scm.png]]

### Configuration Identification

> [!NOTE]
>
> Para gestionar debidamente todos los elementos del motor de un avión, cada parte crítica debe ser correctamente identificada, convirtiéndose en un elemento clave en poder propiciar la debida gestión de varias configuraciones de motores.

Para proveer un nivel de CM apropiado en las partes del SW, también debemos identificar todos los items a ser gestionados.

#### Items de Configuración

Los items a ser identificados son conocidos como [[02-conceptos-clave-scm#Item de Configuración (IC)|Items de Configuración]]:
- Considerados esenciales para gestionar el producto SW en cuestión.
- Son los objetos necesarios para diseñar, desarrollar, construir, mantener, probar y poner en funcionamiento un producto SW.
- Los SCIs no son necesariamente elementos que puedan compartirse entre organizaciones o proyectos.
	- Lo que una organización puede y debe hacer es desarrollar criterios documentados que puedan aplicarse consistentemente para determinar qué elementos relacionados al SW deben quedar bajo el control de configuración.

---

V o F. Los ICs son considerados esenciales para gestionar el producto SW en cuestión.::V
<!--SR:!2025-06-25,1,230-->

V o F. Los ICs son objetos necesarios para diseñar, desarrollar, construir, mantener, probar y poner en funcionamiento un producto SW.::V
<!--SR:!2025-06-25,1,230-->

V o F. Los SCIs no son necesariamente elementos que puedan compartirse entre organizaciones o proyectos.::V
<!--SR:!2025-06-25,1,230-->

Lo que una organización puede y debe hacer es desarrollar ==1;;criterios documentados== que puedan aplicarse consistentemente para determinar qué ==1;;elementos relacionados== al SW deben quedar bajo ==1;;el control de configuración==.
<!--SR:!2025-06-25,1,230-->

---

#### La identificación es la función más importante del SCM

- Items no identificados => Items que no pueden ser gestionados.
- Cualquier cosa que necesitemos para crear nuestro producto SW => Dicho item debe ser identificado y controlado, ejemplos:
	- Compiladores.
	- SOs.
	- Bibliotecas.
	- Herramientas de desarrollo.
	- Ambientes: dev, testing, producción, etc.
	- Manuales: de usuario, etc.
	- Documentación.
	- Programas:
		- De hojas de cálculo.
		- De DB.
		- Procesadores de texto.

En resumen, si lo necesitamos para llevar a cabo el desarrollo, probablemente deberíamos asignarle un ID.

---

La identificación es la función ==1;;más importante== del SCM.
<!--SR:!2025-06-25,1,230-->

V o F. Los items no identificados pueden ser gestionados.::F, items no identificados => Items que no pueden ser gestionados.
<!--SR:!2025-06-25,1,230-->

Dar ejemplos de ICs.
?
- Compiladores.
- SOs.
- Bibliotecas.
- Herramientas de desarrollo.
- Ambientes: dev, testing, producción, etc.
- Manuales: de usuario, etc.
- Documentación.
- Programas:
	- De hojas de cálculo.
	- De DB.
	- Procesadores de texto.
<!--SR:!2025-06-25,1,230-->

---

### Configuration Control

- El autor cuenta que fue influenciado por un stakeholder en realizar un pequeño cambio en la aplicación que mantenía.
	- Dicho cambio de 1 línea de código tiró abajo producción.
	- Un sistema crítico que requería una entrada por la aplicación no fue capaz de satisfacer su propósito.
- Problema:
	- La organización ni tampoco el desarrollador estuvieron controlando los activos de SW.
	- Cualquiera es libre de realizar cambios.
	- Pasaje a producción de un cambio con pocas pruebas realizadas.
- SW Configuration Control:
	- Proceso de controlar y limitar los cambios realizados a activos de SW.
	- Según IEEE:
		- El control de configuración es un elemento del CM que consiste de la evaluación, coordinación, aprobación o desaprobación, e implementación de cambios a ICs, posterior al establecimiento formal de su identificación de configuración.
	- Es decir:
		- El control de configuración garantiza que los cambios a activos de SW solamente sean posibles posterior a su análisis, evaluación, revisión y aprobación por parte de un grupo autorizado en controlar los cambios de activos de SW.

---

El SW Configuration Control es el proceso de ==1;;controlar== y ==1;;limitar== los cambios realizados a ==1;;activos de SW==.
<!--SR:!2025-06-25,1,230-->

V o F. El control de configuración garantiza que los cambios a activos de SW solamente sean posibles posterior a su análisis, evaluación, revisión y aprobación por parte de un grupo autorizado en controlar los cambios de activos de SW.::V
<!--SR:!2025-06-25,1,230-->

---

#### SCCB

"Grupo autorizado en controlar los cambios de activos de SW":

- Conocidos como Change Control Board o Configuration Control Board (CCB).
- Actúan como guardianes del control de flujo de cambios de ICs.
- Debe incluir representantes de:
	- La gestión del programa.
	- Ingeniería en sistemas.
	- Ingeniería de SW.
	- SQAs.
	- SCM.
	- Testers independientes.
	- Representante del cliente.
- Responsabilidades: garantizar que, previo a su incorporación, cada propuesta / petición por un cambio a un IC sea apropiadamente:
	- Considerada y coordinada.
	- Entendida.
	- Analizada respecto al impacto y valor, previo a:
		- La aceptación.
		- Postergación hasta el siguiente release.
		- Desaprobación.
	- Investigada, tal que su modificación no impacte a otros ICs de forma imprevista.

---

¿Cuál es una descripción representativa del SCCB?::"Grupo autorizado en controlar los cambios de activos de SW".
<!--SR:!2025-06-25,1,230-->

Nombrar las responsabilidades del SCCB.
?
Garantizar que, previo a su incorporación, cada propuesta / petición por un cambio a un IC sea apropiadamente:
- Considerada y coordinada.
- Entendida.
- Analizada respecto al impacto y valor, previo a:
	- La aceptación.
	- Postergación hasta el siguiente release.
	- Desaprobación.
- Investigada, tal que su modificación no impacte a otros ICs de forma imprevista.
<!--SR:!2025-06-25,1,230-->

---

#### SW Change Control Process

Ejemplo:

![[12.2-the-sw-change-process.png]]

1. Previo al desarrollo de la Engineering Change Proposal (ECP), el SW Design Review Board (SDRB) revisa los cambios propuestos, mejoras propuestas o reportes de problemas.
2. Una vez desarrolladas las ECPs, el SCCB las evalúa.
3. Este comité controla cuál de las ECPs serán aprobadas para ser incorporadas al SW.
4. Posterior a la aprobación y priorización, la propuesta de cambio o mejora es realizada al SW.

---

Visualizar el diagrama del proceso de control de cambios del SW.
?
![[12.2-the-sw-change-process.png]]
<!--SR:!2025-06-25,1,230-->

---

### Configuration Status Accounting

> [!NOTE]
>
> - Los contadores deben llevar contabilidad de los activos de la empresa, respecto a los costos directos e indirectos asociados a la manufactura y provisión de bienes y servicios.
> - Implica identificar los activos, los costos directos e indirectos incurridos en el desarrollo y mantenimiento de dicho activo, cómo el activo funciona en conjunto con otros activos y poder realizar un análisis del estado de dichos activos y reportarlos.
> - En un contexto de manufactura implican activos que se integran en otros activos.
> - El desglose del trabajo o del producto debe ser documentado.
> - Se debe tener una trazabilidad de los elementos.

- ICs: Son los activos de un producto de SW => Deben ser debidamente registrados.
- Status Accounting: Es la actividad del SCM responsable de:
	- Aportar trazabilidad y mantener los datos relacionados con cada uno de los ICs.
	- Realizar seguimiento de los cambios realizados a los ICs.
	- Determinar el estado de cada uno de los ICs en cualquier etapa del desarrollo o mantenimiento del SW.
	- Recopilar información para responder a las preguntas:
		- ¿Qué cambios han sido solicitados?
		- ¿Qué cambios se han realizado?
		- ¿Cuándo ocurrió cada cambio?
		- ¿Cuál fue la razón de cada cambio?
		- ¿Quién autorizó cada cambio?
		- ¿Quién realizó cada cambio?
		- ¿Qué ICs se vieron afectados por cada cambio?
- Se necesita mantener un repositorio de activos claves del SW para asegurar que estos se encuentren debidamente contabilizados.
- Los cambios en el estado de estos activos deben ser documentados y rastreados: Permite en cualquier momento a la organización conocer el estado de cualquier activo de SW.
- Los informes que indican la configuración de estos productos SW deben ser definidos y generados como parte crítica del proceso de contabilización.
- La presente actividad debe proporcionar diversos informes:
	- Logs de transacciones.
	- Change log.
	- Delta report (de diferencias) de ICs.
	- Informe de uso de recursos.
	- Informe de estado de ICs.
	- Informe de "cambios actualmente en curso".
	- Informe de "los estados de las solicitudes de cambio".
	- Informe de compleción por devs, aplicación, etc.

---

El Configuration Status Accounting aporta ==1;;trazabilidad== y ==1;;mantiene los datos relacionados== con cada uno de los ICs.
<!--SR:!2025-06-25,1,230-->

El Configuration Status Accounting realiza ==1;;seguimiento de los cambios== realizados a los ICs.
<!--SR:!2025-06-25,1,230-->

El Configuration Status Accounting determinar el ==1;;estado de cada uno de los ICs== en cualquier ==1;;etapa del desarrollo o mantenimiento== del SW.
<!--SR:!2025-06-25,1,230-->

---

### Configuration Auditing

> [!NOTE]
>
> - Las grandes firmas de contabilidad realizan auditorías _independientes_ a los libros (contables) corporativos: Buscan dar fe de la congruencia de la información financiera reportada por las corporaciones.
> - Los auditores ciertamente no son considerados como figuras positivas: suelen ser percibidos como "aquellos que después de un bélico apuñalan a los heridos".
> - El autor cuenta que al auditar el cumplimiento de políticas, procesos y procedimientos, la corporación pudo demostrar a su cliente gubernamental que la misma seguía prácticas sólidas y consistentes en la entrega de productos y servicios.
> 	- Las personas tienden a seguir las prácticas establecidas si saben que alguien por su ocurrencia.
> - Si se recopilan métricas que nunca son evaluadas, los devs pronto aprenden que pueden ignorarlas. De igual manera, si no se les exige responsabilidad, aprenden que pueden ignorar políticas, procesos y procedimientos. Debe haber rendición de cuentas.

- Las auditorías de configuración de SW son importantes por las mismas razones.
	- Se acepta generalmente que seguir buenas prácticas de desarrollo de SW contribuye a la entrega constante de productos de calidad (activos).
	- Las auditorías deben realizarse tal que garanticen el seguimiento y cumplimiento consistente de las políticas, procesos y procedimientos de desarrollo de SW.
- Según Tim Kasse en "SW Configuration Management for Project Leaders" (1997):
	- Las auditorías de configuración verifican que:
		- El producto SW se construya conforme a los requisitos, estándares o acuerdos contractuales.
		- Todos los productos de SW hayan sido producidos, correctamente identificados, descritos y que todos los cambios solicitados hayan sido resueltos.
- Una auditoría de configuración de SW debe:
	- Realizarse en forma periódica para garantizar que las prácticas y procedimientos de SCM se sigan rigurosamente.
	- Evaluar la integridad de la línea base del SW.
	- Verificar la completitud y exactitud del contenido de la biblioteca de líneas base (repositorios de líneas base).
	- Asegurarse de que los cambios realizados sean realmente los que se pretendían.
	- Ser continua, con cada vez mayor frecuencia y profundidad a lo largo del ciclo de vida.
- Es importante realizar una auditoría de configuración de SW antes de cada cambio importante en la línea base.
- Tipos de auditorías de configuración:
	- Funcional: Verificar que el SW funcione según lo definido en la documentación de requisitos.
	- Física: Comprobar que todos los items identificados para ser incluidos en un release del SW estén efectivamente incluidos y que no se agregue ningún item adicional.

---

La auditoría de configuración debe realizarse en forma ==1;;periódica== para garantizar que ==1;;las prácticas== y ==1;;procedimientos== de SCM se sigan rigurosamente.
<!--SR:!2025-06-25,1,230-->

La auditoría de configuración evalúa la ==1;;integridad== de la ==1;;línea base== del SW.
<!--SR:!2025-06-25,1,230-->

La auditoría de configuración verifica la ==1;;completitud== y ==1;;exactitud== del ==1;;contenido de la biblioteca de líneas base (repositorios de líneas base)==.
<!--SR:!2025-06-25,1,230-->

La auditoría de configuración se asegura de que los ==1;;cambios realizados== sean realmente los que se pretendían.
<!--SR:!2025-06-25,1,230-->

La auditoría de configuración debe ser ==1;;continua==, con cada vez mayor ==1;;frecuencia== y ==1;;profundidad== a lo largo del ciclo de vida.
<!--SR:!2025-06-25,1,230-->

---

## ¿Pero a quién le importa?

- Evaluaciones del SW indican que:
	- Ausencia de cumplimiento de prácticas básicas y sólidas de desarrollo y adquisición del SW => Impacto negativo sobre los costos y calendarios de proyectos de desarrollo, mantenimiento y adquisición del SW.
	- SCM: Es una de estas prácticas básicas y sólidas.
- Watts Humphrey:
	- "Los problemas de SW más frustrantes usualmente son causados por una mala gestión de la configuración. Los problemas son frustrantes porque toman tiempo arreglarlos, suelen ocurrir en el peor momento posible y son totalmente innecesarios".
- Situaciones que denotan que nos debe importar el SCM:
	- Un error de SW que se corrigió hace 6 meses ha vuelto a aparecer de la nada.
	- Un dev estuvo 12 horas haciendo cambios sobre una versión equivocada del SW.
	- No existe trazabilidad de los requerimientos en base a los documentos de requerimientos, la documentación de usuario y código fuente.
	- 2 programadores han sobrescrito el código del otro, tirando a la basura 40 horas de trabajo de cada uno.
	- Nadie puede encontrar la última versión del código fuente.
	- Lo que funcionaba bien ayer misteriosamente no funciona hoy.
	- Una aplicación instalada en varios lugares funciona bien en algunos, pero no en otros.
	- No existe forma de evaluar el impacto de los requerimientos de los cambios propuestos.

## Conclusiones

- No existe tal cosa como "un cambio de una sola línea de código".
- Cualquier cambio del SW se basa en algún tipo de cambio en los requerimientos.
- Para responder a los cambios de requerimientos, es esencial identificar adecuadamente todos los elementos críticos (ICs) del desarrollo del SW.
- Un "cambio de una sola línea de código" requiere:
	- La identificación precisa de lo que realmente necesita cambiar.
	- El análisis de cómo la parte afectada del código interactúa (_interface_) con porciones del mismo.
	- El análisis del impacto de ese cambio en otras porciones del código.
	- La revisión y aprobación por personas conocedoras de la aplicación, capaces de determinar el impacto del cambio solicitado.
	- La documentación y trazabilidad de:
		- Qué cambio es realmente necesario.
		- Quién ha aprobado el cambio.
		- Cuándo se realizó el cambio.
		- Por qué se realizó el cambio.
	- De alguien quién supervise el proceso.
	- La realización de auditorías para asegurar que se sigue el proceso aprobado para realizar cambios.
	- La coincidencia del producto SW con la documentación.
- La aplicación de conceptos de SCM mejorará la capacidad de la organización para controlar los activos de SW:
	- Los items y componentes esenciales para el desarrollo y mantenimiento del SW serán identificados, gestionados y controlados.
	- Los cambios no se realizarán sin el análisis previo adecuado y la aprobación.
	- El estado de los activos de SW será conocido y rastreable en todo momento.
	- Las auditorías periódicas asegurarán que se sigue el proceso.
- La probabilidad de que cambios supuestamente simples impacten gravemente a los proyectos se reducirá considerablemente.

---

Nombrar las ventajas que obtienen sobre el control de los activos de SW para una organización que aplica SCM.
?
- Los items y componentes esenciales para el desarrollo y mantenimiento del SW serán identificados, gestionados y controlados.
- Los cambios no se realizarán sin el análisis previo adecuado y la aprobación.
- El estado de los activos de SW será conocido y rastreable en todo momento.
- Las auditorías periódicas asegurarán que se sigue el proceso.
<!--SR:!2025-06-25,1,230-->

---
