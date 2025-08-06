---
tags:
- flashcards/swe/teoria/2P
---

# Overview

- Auditoria Funcional.
- Auditoria Física.
- Auditoría de Proceso.

> [!NOTE]
>
> SWEBOK:
>
> - Determina el grado en que un item satisface los requerimientos de características funcionales y físicas.
> - Las auditorías informales pueden ser realizadas en puntos claves del ciclo de vida.
> - Existen 2 tipos de auditorías formales que pueden ser requeridos por contrato:
> 	- SW Functional Configuration Audit (SFCA):
> 		- Garantiza que el item SW auditado sea consistente con sus especificaciones (funcionalidades pedidas).
> 		- Posee como input clave a las salidas de las actividades "_SW Verification and Validation_" de la KA _SW Quality_.
> 	- SW Physical Configuration Audit (SPCA): Garantiza que el diseño y la documentación de referencia sean consistentes con el producto SW tal cual construido.
> - La compleción de estas auditorías pueden ser un pre-requisito para establecer el baselines del producto.
> - In-Process Audits of a SW Baseline:
> 	- Las auditorías pueden ser realizadas durante el proceso de desarrollo con la finalidad de investigar los estados de elementos específicos de configuración.
> 	- Puede ser aplicado sobre todos los items del baseline, para así garantizar que el desempeño sea consistente con las especificaciones o que la documentación evolutiva continue siendo consistente con el item del baseline siendo desarrollado.
> 	- "In-Process": En marcha.

---

Nombrar las actividades de la auditoría de la Configuración de SW.
?
- Auditoria Funcional.
- Auditoria Física.
- Auditoría de Proceso.
<!--SR:!2025-06-22,1,230-->

---

# Auditorías de la Configuración de SW

> Validando los distintos aspectos de la SCM.

De acuerdo al SWEBOK:

- Una auditoría de Configuración de SW es una examinación de un trabajo, producto o set de artefactos para evaluar aspectos técnicos, de seguridad, legales y de cumplimiento de normas con respecto a especificaciones, estándares, acuerdos contractuales u otros criterios.
- Las auditorías son llevadas a cabo de acuerdo a procesos definidos y pueden ser ejecutadas con diferentes niveles de formalidad, desde Revisiones informales basadas en checklists, hasta pruebas exhaustivas de la configuración que son planificadas con anticipación.

> [!NOTE]
>
> Las auditorías pueden ser tanto internas como externas.

---

Según el SWEBOK: ¿En qué consiste una auditoría de la configuración de SW?
?
Es una examinación de un trabajo, producto o set de artefactos para evaluar aspectos técnicos, de seguridad, legales y de cumplimiento de normas con respecto a especificaciones, estándares, acuerdos contractuales u otros criterios.
<!--SR:!2025-06-22,1,230-->

Según el SWEBOK: ¿Cómo se debe llevar a cabo una auditoría de la configuración de SW?
?
Son llevadas a cabo de acuerdo a procesos definidos y pueden ser ejecutadas con diferentes niveles de formalidad, desde Revisiones informales basadas en checklists, hasta pruebas exhaustivas de la configuración que son planificadas con anticipación.
<!--SR:!2025-06-22,1,230-->

---

## Tipos de auditorías

---

(Control U5) ¿Qué tipos de auditorías conoce y qué hace cada una?
?
- Auditoría Funcional:
	- Es una evaluación del producto SW que se realiza para verificar, vía testing, inspección, demostración o análisis de resultados, que el producto ha cumplido los requerimientos especificados en la línea base de documentación funcional.
	- Garantiza que una configuración dada sea consistente con su especificación de requerimientos previamente definida (funcionalidades pedidas).
- Auditoría Física:
	- Evalúa:
		- Que los elementos modificados (componentes físicos) de la configuración sean consistentes con las especificaciones técnicas de los cambios en la versión.
		- Los cambios realizados en el código y en los diferentes ambientes.
		- e.g., si decimos que modificaremos algo en la capa de datos, no debería modificar nada de la capa de presentación. Que estos cambios queden en los repositorios en los que deben estar.
- Auditoría de Proceso:
	- Evalúa que los cambios realizados al producto SW hayan seguido el proceso definido para los mismos.
	- Objetivo: confirmar que todos los cambios fueron solicitados, aprobados e implementados de acuerdo al proceso ([[06-sc-change-control#Change Management Process|Change Management Process]]) definido en la compañía.
	- Ejemplo:
		- Al identificar una línea base se identifica su composición: Qué items que la conforman.
		- Las inconsistencias se reportan y se determina si el defecto corresponde a la configuración misma o a la documentación.
<!--SR:!2025-06-22,1,230-->

Los 2 tipos de auditorías formales que pueden ser requeridos por contrato son las auditorías ==1;;funcionales== y las auditorías ==1;;físicas==.
<!--SR:!2025-06-22,1,230-->

La compleción de las auditorías ==1;;funcionales== y las auditorías ==1;;físicas== pueden ser un pre-requisito para ==1;;establecer el baselines del producto==.
<!--SR:!2025-06-22,1,230-->

---

### Auditoría Funcional

- Es una evaluación del producto SW que se realiza para verificar, vía testing, inspección, demostración o análisis de resultados, que el producto ha cumplido los requerimientos especificados en la línea base de documentación funcional.
- En las auditorías funcionales, básicamente se verifica que una configuración dada cumpla con alguna especificación de requerimientos previamente definida.

> [!IMPORTANT]
>
> - Todas las actividades asociadas al testing es una auditoría funcional.
> - Usualmente es interna, pero también podría ser externa:
> 	- e.g., hacer terciarización con una empresa externa para que nos haga testing y convalide las funcionalidades.

> [!NOTE]
>
> - Inspecciona la construcción funcional: Que el SW haga lo que dice que hace.
> - Repaso funcional sobre los componentes.
> - Puede ser rápidamente emparentado con testing, pero en realidad consta más de observar y no de ejecutar algo.

---

La auditoría funcional posee como input clave a las salidas de las actividades ==1;;"SW Verification and Validation"== de la KA ==1;;SW Quality==.
<!--SR:!2025-06-22,1,230-->

V o F. Todas las actividades asociadas al testing es una auditoría funcional.::V
<!--SR:!2025-06-22,1,230-->

Una auditoría funcional usualmente es ==1;;interna==, pero también podría ser ==1;;externa==.
<!--SR:!2025-06-22,1,230-->

Una auditoría funcional puede ser rápidamente emparentado con ==1;;testing==, pero en realidad consta más de ==1;;observar== algo y no de ==1;;ejecutarlo==.
<!--SR:!2025-06-22,1,230-->

---

### Auditoría Física

- Evalúa que los elementos modificados de la configuración sean consistentes con las especificaciones técnicas de los cambios en la versión.
- Esta auditoría también evalúa los cambios realizados en el código y en los diferentes ambientes.

> [!IMPORTANT]
>
> Posee los 2 tipos de auditorías:
> - e.g., tanto el BCRA (auditoría externa) y la casa matriz (auditoría interna) de un cierto banco, puede que hagan auditorías físicas en forma regular para asegurarse de que el banco tenga el código fuente de las aplicaciones empleadas para trabajar con los clientes.

> [!NOTE]
>
> - Hablamos de qué componentes son modificados físicamente. En sistemas, lo más físico que tenemos es:
> 	- .docx, .exe, .xlsx, .csv.
> 	- La infraestructura como código: Archivos .yml/.yaml
> 	- Nos interesan ver cambios como: "Antes era if (x < 7) y ahora es if (x >= 8)"
> - Que se trabaje en el archivo físicamente correspondiente y no en otro archivo cualquiera.
> - Que las aplicaciones se encuentren en lugares debidos: repositorios correspondientes.

---

Una auditoría física puede ser tanto ==1;;interna== como ==1;;externa==. ==1;;Ejemplo: tanto el BCRA (auditoría externa) y la casa matriz (auditoría interna) de un cierto banco, puede que hagan auditorías físicas en forma regular para asegurarse de que el banco tenga el código fuente de las aplicaciones empleadas para trabajar con los clientes==.
<!--SR:!2025-06-22,1,230-->

Una auditoría física garantiza que ==1;;el diseño== y ==1;;la documentación== de referencia sean consistentes con el ==1;;producto SW== tal cual construido.
<!--SR:!2025-06-22,1,230-->

---

### Auditoría de Proceso (In-Process Audits of a SW Baseline)

> In-Process: En marcha.

- Evalúa que los cambios realizados al producto SW hayan seguido el proceso definido para los mismos.
- El objetivo es confirmar que todos los cambios fueron solicitados, aprobados e implementados de acuerdo al proceso definido en la compañía.
- Ejemplo:
	- Al identificar una línea base se identifica su composición: Qué items la conforman.
	- Las inconsistencias se reportan y se determina si el defecto corresponde a la configuración misma o a la documentación.

> [!IMPORTANT]
>
> En general son auditorías internas pero también pueden ser externas:
> - e.g., en el caso de los bancos, KPMG les hace auditorías de proceso regularmente (externa).
> - e.g., SCAMPI es una auditoría de proceso, es más amplio ya que no solamente evalúa el SCM, pero parte de lo que evalúa es el proceso de SCM, con lo cual si serviría para el propósito aunque sea más amplia. Es interna ya que la propia empresa lo hace para sí misma.

> [!NOTE]
>
> - ¿Cómo estamos administrando nuestro proceso?
> - e.g., si estipulamos que el código será subido a Github, pero lo subimos Bitbucket, entonces no hemos cumplido con el proceso.

---

Las auditorías de proceso en general son auditorías ==1;;internas== pero también pueden ser ==1;;externas==. ==1;;Ejemplo: en el caso de los bancos, KPMG les hace auditorías de proceso regularmente (externa). SCAMPI es una auditoría de proceso, es más amplio ya que no solamente evalúa el SCM, pero parte de lo que evalúa es el proceso de SCM, con lo cual si serviría para el propósito aunque sea más amplia. Es interna ya que la propia empresa lo hace para sí misma.==
<!--SR:!2025-06-22,1,230-->

Las auditorías ==1;;informales (de proceso)== pueden ser realizadas en ==1;;puntos claves== del ciclo de vida.
<!--SR:!2025-06-22,1,230-->

Las auditorías de proceso pueden ser realizadas durante el ==1;;proceso de desarrollo== con la finalidad de investigar los ==1;;estados de elementos específicos== de configuración.
<!--SR:!2025-06-22,1,230-->

Las auditorías de proceso pueden ser aplicadas sobre todos los ==1;;items del baseline==, para así garantizar que el desempeño sea consistente con ==1;;las especificaciones== o que la ==1;;documentación== evolutiva continue siendo consistente con el ==1;;item del baseline== siendo desarrollado. ==1;;Ejemplo: si estipulamos que el código será subido a Github, pero lo subimos Bitbucket, entonces no hemos cumplido con el proceso.==
<!--SR:!2025-06-22,1,230-->

---
