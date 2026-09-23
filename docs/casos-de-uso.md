# Casos de uso

## Diagrama general

_Incluir el código PlantUML en `diagramas/casos-de-uso.puml`._
_Visualizar en [plantuml.com](https://www.plantuml.com/plantuml/uml/)._

_Describir brevemente los actores identificados y las relaciones principales (include, extend)._

1. Usuario:
Es el postulante que utiliza el sistema para consultar las convocatorias disponibles y participar en los procesos de selección. Sus principales acciones son:
Ver convocatorias.
Postularse a una convocatoria.
Ver resultado de su postulación.
Consultar estado de su postulación.
Cargar CV.

2. Empresa:
Es el actor encargado de gestionar sus convocatorias y llevar adelante el proceso de selección de los postulantes. Sus principales acciones son:
Crear, editar o cerrar convocatoria.
Ver postulantes.
Entrevistar postulantes.
Cargar resultado de las entrevistas.

3. Administrador:
Es el actor encargado de administrar los usuarios y supervisar la información general del sistema. Sus principales acciones son:
Gestionar usuarios y permisos.
Generar reportes.
Ver resultados.

<<include>>
Ver convocatorias → incluye → Postularse a convocatoria.
Postularse a convocatoria → incluye → Ver resultado.
Editar o cerrar convocatoria → incluye → Ver postulantes.
Ver postulantes → incluye → Entrevistar postulantes.
Entrevistar postulantes → incluye → Cargar resultado.

<<extend>>
Crear, editar o cerrar convocatoria → extiende → Ver postulantes.
Consultar estado de su postulación → extiende → Ver resultado.

---

## CU-01 — Ver convocatorias

| Campo | Detalle |
|-------|---------|
| Identificador | CU-01 |
| Nombre | Ver convocatorias |
| Descripción | Permite al usuario consultar las convocatorias laborales disponibles en el sistema. |
| Actores | Principal: Usuario/Postulante |
| Precondiciones | El sistema debe estar disponible y deben existir convocatorias registradas. |
| Postcondiciones | Éxito: El usuario visualiza las convocatorias disponibles. / Fallo: El sistema informa que no existen convocatorias disponibles. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El usuario ingresa a la sección de convocatorias. | El sistema consulta las convocatorias registradas. |
| 2 | El usuario solicita visualizar las convocatorias.| El sistema muestra las convocatorias vigentes con su información principal. |
| 3 | El usuario selecciona una convocatoria. | El sistema muestra la información completa de la convocatoria seleccionada. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | No existen convocatorias vigentes. | El sistema informa que no hay convocatorias disponibles. |
| E2 | La convocatoria seleccionada se encuentra vencida. | El sistema informa que la convocatoria ya no se encuentra disponible. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | La información debe mostrarse en un tiempo adecuado para la consulta del usuario. |
| Frecuencia | Alta |
| Importancia | Alta |
| Urgencia | Alta |

---

## CU-02 — Postularse a convocatoria

| Campo | Detalle |
|-------|---------|
| Identificador | CU-02 |
| Nombre | Postularse a convocatoria |
| Descripción | Permite al usuario enviar su postulación a una convocatoria laboral vigente. |
| Actores | Principal: Usuario/Postulante |
| Precondiciones | El usuario debe estar registrado y autenticado, tener un CV cargado y la convocatoria debe estar vigente. |
| Postcondiciones | Éxito: La postulación queda registrada. / Fallo: El sistema informa el motivo por el cual no puede realizarse la postulación. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El usuario selecciona una convocatoria vigente. | El sistema muestra la información de la convocatoria y la opción para postularse. |
| 2 | El usuario selecciona la opción "Postularse". | El sistema verifica que el usuario tenga un CV cargado y que no exista una postulación previa. |
| 3 | El usuario confirma la postulación. | El sistema registra la postulación y la fecha correspondiente. |
| 4 | El usuario finaliza la operación. | El sistema informa que la postulación fue realizada correctamente. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El usuario no tiene un CV cargado. | El sistema informa que debe cargar un CV antes de postularse. |
| E2 | El usuario ya se encuentra postulado a la convocatoria. | El sistema informa que no puede realizar una segunda postulación. |
| E3 | La convocatoria se encuentra vencida o cerrada. | El sistema impide realizar la postulación e informa que la convocatoria no acepta nuevas postulaciones. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | La postulación debe registrarse inmediatamente después de la confirmación. |
| Frecuencia | Alta |
| Importancia | Alta |
| Urgencia | Alta |

---

## CU-03 — Ver resultado

| Campo | Detalle |
|-------|---------|
| Identificador | CU-03 |
| Nombre | Ver resultado |
| Descripción | Permite al usuario consultar el resultado de sus postulaciones una vez que haya sido registrado y habilitado para su consulta. |
| Actores | Principal: Usuario/Postulante |
| Precondiciones | El usuario debe estar registrado y debe tener al menos una postulación registrada. |
| Postcondiciones | Éxito: El usuario visualiza el resultado de su postulación. / Fallo: El sistema informa que el resultado aún no se encuentra disponible. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El usuario ingresa a sus postulaciones. | El sistema muestra las postulaciones realizadas por el usuario. |
| 2 | El usuario selecciona una postulación. | El sistema consulta el estado y resultado registrados. |
| 3 | El usuario solicita consultar el resultado. | El sistema muestra el resultado disponible. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | La postulación no tiene un resultado registrado. | El sistema informa que el resultado aún no se encuentra disponible. |
| E2 | El usuario intenta consultar una postulación que no le pertenece. | El sistema impide el acceso a la información. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | El resultado debe mostrarse en un tiempo adecuado. |
| Frecuencia | Media |
| Importancia | Alta |
| Urgencia | Media |

---

## CU-04 — Consultar estado de su postulación

| Campo | Detalle |
|-------|---------|
| Identificador | CU-04 |
| Nombre | Consultar estado de su postulación |
| Descripción | Permite al usuario consultar el estado actual de sus postulaciones. |
| Actores | Principal: Usuario/Postulante |
| Precondiciones | El usuario debe estar registrado y tener al menos una postulación. |
| Postcondiciones | Éxito: El usuario visualiza el estado de su postulación. / Fallo: El sistema informa que no existen postulaciones para consultar. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El usuario ingresa a la sección de sus postulaciones. | El sistema consulta sus postulaciones. |
| 2 | El usuario selecciona una postulación. | El sistema consulta su estado actual. |
| 3 | El usuario solicita consultar el estado. | El sistema muestra el estado correspondiente. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El usuario no posee postulaciones. | El sistema informa que no existen postulaciones registradas. |
| E2 | No se puede consultar el estado. | El sistema informa que la información no está disponible. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | El estado debe mostrarse rápidamente. |
| Frecuencia | Alta |
| Importancia | Alta |
| Urgencia | Media |

---

## CU-05 — Cargar CV

| Campo | Detalle |
|-------|---------|
| Identificador | CU-05 |
| Nombre | Cargar CV |
| Descripción | Permite al usuario cargar y almacenar su currículum vitae para utilizarlo durante el proceso de postulación. |
| Actores | Principal: Usuario/Postulante |
| Precondiciones | El usuario debe estar registrado y autenticado. |
| Postcondiciones | Éxito: El CV queda almacenado y asociado al usuario. / Fallo: El sistema informa el error de carga. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El usuario ingresa a la sección de CV. | El sistema muestra la opción para cargar el archivo. |
| 2 | El usuario selecciona su CV. | El sistema verifica el archivo. |
| 3 | El usuario confirma la carga. | El sistema almacena el CV y lo asocia a su cuenta. |
| 4 | El usuario finaliza la operación. | El sistema informa que el CV fue cargado correctamente. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El archivo no tiene un formato permitido. | El sistema informa que el formato no es válido. |
| E2 | No se seleccionó ningún archivo. | El sistema solicita seleccionar un CV. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | El archivo debe almacenarse luego de una carga exitosa. |
| Frecuencia | Media |
| Importancia | Alta |
| Urgencia | Media |

---

## CU-06 — Crear, editar o cerrar convocatoria

| Campo | Detalle |
|-------|---------|
| Identificador | CU-06 |
| Nombre | Crear, editar o cerrar convocatoria |
| Descripción | Permite a la empresa crear nuevas convocatorias, modificar su información o cerrarlas. |
| Actores | Principal: Empresa |
| Precondiciones | La empresa debe estar autenticada y contar con permisos para gestionar sus convocatorias. |
| Postcondiciones | Éxito: La convocatoria queda creada, modificada o cerrada. / Fallo: El sistema informa el error correspondiente. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | La empresa ingresa a la gestión de convocatorias. | El sistema muestra sus convocatorias. |
| 2 | La empresa selecciona crear o modificar una convocatoria. | El sistema muestra el formulario correspondiente. |
| 3 | La empresa completa o modifica los datos. | El sistema valida la información. |
| 4 | La empresa confirma la operación. | El sistema guarda los cambios. |
| 5 | La empresa selecciona cerrar una convocatoria cuando corresponda. | El sistema cambia el estado de la convocatoria y evita nuevas postulaciones. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | Faltan datos obligatorios. | El sistema solicita completar los campos faltantes. |
| E2 | Los datos ingresados no son válidos. | El sistema informa los errores. |
| E3 | La empresa intenta modificar una convocatoria ajena. | El sistema impide la modificación. |

| Campo | Detalle |
|-------|---------|
| Rendimiento	| Los cambios deben registrarse luego de una validación exitosa. |
| Frecuencia | Alta |
| Importancia	| Alta |
| Urgencia | Alta |

---

## CU-07 - Ver postulantes

| Campo | Detalle |
|-------|---------|
| Identificador | CU-07 |
| Nombre | Ver postulantes |
| Descripción | Permite a la empresa consultar los usuarios que se postularon a sus convocatorias. |
| Actores | Principal: Empresa |
| Precondiciones | La empresa debe estar autenticada y debe existir una convocatoria con postulantes. |
| Postcondiciones | Éxito: La empresa visualiza los postulantes. / Fallo: El sistema informa que no existen postulantes. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | La empresa selecciona una convocatoria. | El sistema muestra la información de la convocatoria. |
| 2 | La empresa solicita ver los postulantes. | El sistema consulta las postulaciones asociadas. |
| 3 | La empresa consulta la lista. | El sistema muestra los postulantes registrados. |
| 4 | La empresa selecciona un postulante. | El sistema muestra la información disponible del postulante y su CV. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | La convocatoria no tiene postulantes. | El sistema informa que no existen postulantes. |
| E2 | La empresa intenta consultar una convocatoria ajena. | El sistema impide el acceso. |

| Campo | Detalle |
|-------|---------|
| Rendimiento	| La lista debe mostrarse en un tiempo adecuado. |
| Frecuencia | Alta |
| Importancia	| Alta |
| Urgencia | Media |

---

## CU-08 - Entrevistar postulantes

| Campo | Detalle |
|-------|---------|
| Identificador | CU-08 |
| Nombre | Entrevistar postulantes |
| Descripción | Permite a la empresa gestionar las entrevistas de los postulantes seleccionados. |
| Principal: Empresa |
| Precondiciones | Debe existir una convocatoria y un postulante registrado. |
| Postcondiciones | Éxito: La entrevista queda registrada. / Fallo: La entrevista no se registra. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | La empresa selecciona un postulante. | El sistema muestra su información. |
| 2 | La empresa selecciona la opción de entrevista. | El sistema muestra los datos necesarios para registrar la entrevista. |
| 3 | La empresa ingresa fecha, hora y modalidad. | El sistema valida los datos. |
| 4 | La empresa confirma la entrevista. | El sistema registra la entrevista asociada a la postulación. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | No existe una postulación. | El sistema impide registrar la entrevista. |
| E2 | Faltan datos de la entrevista. | El sistema solicita completar la información. |
| E3 | La fecha u horario no es válido. | El sistema informa el error. |

| Campo | Detalle |
|-------|---------|
| Rendimiento	| La entrevista debe registrarse inmediatamente después de la confirmación. |
| Frecuencia | Media |
| Importancia	| Alta |
| Urgencia | Alta |

---

## CU-09 - Cargar resultado

| Campo | Detalle |
|-------|---------|
| Identificador | CU-09 |
| Nombre | Cargar resultado |
| Descripción | Permite a la empresa registrar el resultado obtenido por un postulante luego de una entrevista. |
| Principal: Empresa |
| Precondiciones | Debe existir una entrevista registrada para el postulante. |
| Postcondiciones | Éxito: El resultado queda registrado y asociado a la entrevista y postulación. / Fallo: El sistema informa el error. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | La empresa selecciona una entrevista. | El sistema muestra la información correspondiente. |
| 2 | La empresa selecciona la opción para cargar el resultado. | El sistema muestra el formulario. |
| 3 | La empresa ingresa el resultado. | El sistema valida la información. |
| 4 | La empresa confirma el resultado. | El sistema registra el resultado. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | No existe una entrevista. | El sistema impide cargar el resultado. |
| E2 | No se completa el resultado. | El sistema solicita completar la información. |

| Campo | Detalle |
|-------|---------|
| Rendimiento	| El resultado debe registrarse inmediatamente después de la confirmación. |
| Frecuencia | Media |
| Importancia	| Alta |
| Urgencia | Media |

---

## CU-10 - Gestionar usuarios y permisos

| Campo | Detalle |
|-------|---------|
| Identificador | CU-10 |
| Nombre | Gestionar usuarios y permisos |
| Descripción | Permite al administrador consultar y gestionar los usuarios, roles y permisos del sistema. |
| Principal: Administrador |
| Precondiciones | El administrador debe estar autenticado y contar con permisos administrativos. |
| Postcondiciones | Éxito: Los cambios en usuarios y permisos quedan registrados. / Fallo: El sistema informa el error. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El administrador ingresa a la gestión de usuarios. | El sistema muestra los usuarios registrados. |
| 2 | El administrador selecciona un usuario. | El sistema muestra la información disponible. |
| 3 | El administrador modifica el rol o permiso correspondiente. | El sistema valida los cambios.|
| 4 | El administrador confirma la operación. | El sistema guarda los cambios. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El administrador no tiene permisos suficientes. | El sistema impide realizar la operación. |
| E2 | Los datos ingresados no son válidos. | El sistema informa el error. |

| Campo | Detalle |
|-------|---------|
| Rendimiento	| Los cambios deben registrarse inmediatamente después de la confirmación. |
| Frecuencia | Media |
| Importancia	| Alta |
| Urgencia | Alta |

---
