# Casos de uso

## Diagrama general

_Incluir el código PlantUML en `diagramas/casos-de-uso.puml`._
_Visualizar en [plantuml.com](https://www.plantuml.com/plantuml/uml/)._

_Describir brevemente los actores identificados y las relaciones principales (include, extend)._

### Actores

1. **Usuario / Postulante:** estudiante o egresado del Terciario Urquiza que se registra con su correo institucional para consultar convocatorias y participar en los procesos de selección. Sus casos de uso son: Registrarse, Ver convocatorias, Postularse a convocatoria, Ver resultado, Consultar estado de su postulación, Cargar CV y Consultar entrevista.

2. **Empresa:** organización que publica convocatorias y lleva adelante el proceso de selección. Su cuenta la crea el administrador. Sus casos de uso son: Crear, editar o cerrar convocatoria, Ver postulantes, Programar entrevista y Cargar resultado.

3. **Administrador:** personal de la institución que administra las cuentas, las carreras y supervisa la información del sistema. Sus casos de uso son: Gestionar usuarios y permisos, Dar de alta empresa, Consultar padrón de usuarios, Gestionar carreras, Generar reportes y Ver resultados.

Los tres actores comparten **Iniciar sesión** y **Ver inicio**.

### Relaciones

El diagrama no utiliza relaciones include ni extend. Se evaluó usar include para "Iniciar sesión", pero casi todos los casos de uso lo requieren y se expresa mejor como precondición ("el actor debe haber iniciado sesión") que como una relación repetida en todo el diagrama.

### Índice

| ID | Caso de uso | Actor | Requisitos |
|----|-------------|-------|------------|
| CU-01 | Ver convocatorias | Usuario / Postulante | RF-11, RF-16, RF-30 |
| CU-02 | Postularse a convocatoria | Usuario / Postulante | RF-12 a RF-15, RNF-03 |
| CU-03 | Ver resultado | Usuario / Postulante | RF-19 |
| CU-04 | Consultar estado de su postulación | Usuario / Postulante | RF-34 |
| CU-05 | Cargar CV | Usuario / Postulante | RF-09 |
| CU-06 | Crear, editar o cerrar convocatoria | Empresa | RF-10, RF-20, RF-29, RF-32, RF-33 |
| CU-07 | Ver postulantes | Empresa | RF-17, RF-32 |
| CU-08 | Programar entrevista | Empresa | RF-21, RF-35, RF-36 |
| CU-09 | Cargar resultado | Empresa | RF-18, RF-36 |
| CU-10 | Gestionar usuarios y permisos | Administrador | RF-04, RF-05, RF-08 |
| CU-11 | Generar reportes | Administrador | RF-23 |
| CU-12 | Ver resultados | Administrador | RF-37 |
| CU-13 | Iniciar sesión | Todos | RF-02, RF-03, RF-06, RF-07 |
| CU-14 | Ver inicio | Todos | RF-24, RF-25 |
| CU-15 | Registrarse | Usuario / Postulante | RF-01, RNF-04 |
| CU-16 | Consultar entrevista | Usuario / Postulante | RF-22 |
| CU-17 | Dar de alta empresa | Administrador | RF-26 |
| CU-18 | Gestionar carreras | Administrador | RF-28, RF-31 |
| CU-19 | Consultar padrón de usuarios | Administrador | RF-27 |

---

## CU-01 — Ver convocatorias

| Campo | Detalle |
|-------|---------|
| Identificador | CU-01 |
| Nombre | Ver convocatorias |
| Descripción | Permite al usuario consultar las convocatorias vigentes, filtrarlas por carrera y ver el detalle de cada una. |
| Actores | Principal: Usuario / Postulante |
| Requisitos relacionados | RF-11, RF-16, RF-30 |
| Precondiciones | El usuario debe haber iniciado sesión. |
| Postcondiciones | Éxito: el usuario visualiza las convocatorias vigentes y el detalle de la seleccionada. / Fallo: el sistema informa que no hay convocatorias disponibles. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El usuario ingresa a la sección de convocatorias. | El sistema muestra las convocatorias en estado Vigente con título, empresa, ubicación, modalidad y fecha de finalización. |
| 2 | El usuario elige una carrera en el filtro (opcional). | El sistema muestra solo las convocatorias vigentes dirigidas a esa carrera. |
| 3 | El usuario selecciona una convocatoria. | El sistema muestra su información completa y la opción para postularse. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | No existen convocatorias vigentes. | El sistema informa que no hay convocatorias disponibles. |
| E2 | No hay convocatorias vigentes para la carrera elegida. | El sistema informa que no hay convocatorias para esa carrera y ofrece quitar el filtro. |
| E3 | La convocatoria seleccionada venció o fue cerrada mientras el usuario navegaba. | El sistema informa que la convocatoria ya no se encuentra disponible. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | El listado y el detalle se muestran en un máximo de 5 segundos (RNF-02). |
| Frecuencia | Alta |
| Importancia | Alta |
| Urgencia | Alta |

---

## CU-02 — Postularse a convocatoria

| Campo | Detalle |
|-------|---------|
| Identificador | CU-02 |
| Nombre | Postularse a convocatoria |
| Descripción | Permite al usuario postularse a una convocatoria vigente utilizando su CV cargado. |
| Actores | Principal: Usuario / Postulante |
| Requisitos relacionados | RF-12, RF-13, RF-14, RF-15, RNF-03 |
| Precondiciones | El usuario debe haber iniciado sesión y la convocatoria debe estar Vigente. |
| Postcondiciones | Éxito: la postulación queda registrada con estado Postulado y el CV vigente asociado. / Fallo: el sistema informa el motivo y no registra la postulación. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El usuario selecciona una convocatoria vigente. | El sistema muestra el detalle de la convocatoria y la opción "Postularme". |
| 2 | El usuario selecciona "Postularme". | El sistema verifica que tenga un CV cargado y que no exista una postulación previa, y muestra la confirmación. |
| 3 | El usuario confirma la postulación. | El sistema vuelve a verificar que la convocatoria siga vigente, registra la postulación con la fecha del día, asocia el CV y le asigna el estado Postulado. |
| 4 | — | El sistema informa que la postulación fue realizada y la muestra en "Mis postulaciones". |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El usuario no tiene un CV cargado. | El sistema informa que debe cargar un CV antes de postularse y no registra la postulación. |
| E2 | El usuario ya está postulado a la convocatoria. | El sistema informa que ya se postuló y no crea una segunda postulación. |
| E3 | La convocatoria venció o fue cerrada antes de confirmar. | El sistema informa que la convocatoria no acepta nuevas postulaciones. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | La postulación se registra y se confirma en un máximo de 5 segundos desde la confirmación (RNF-02), en no más de 4 pasos (RNF-03). |
| Frecuencia | Alta |
| Importancia | Alta |
| Urgencia | Alta |

---

## CU-03 — Ver resultado

| Campo | Detalle |
|-------|---------|
| Identificador | CU-03 |
| Nombre | Ver resultado |
| Descripción | Permite al usuario consultar el resultado de una postulación una vez que la empresa lo registró. |
| Actores | Principal: Usuario / Postulante |
| Requisitos relacionados | RF-19 |
| Precondiciones | El usuario debe haber iniciado sesión y tener al menos una postulación. |
| Postcondiciones | Éxito: el usuario visualiza el resultado y el puntaje de su entrevista. / Fallo: el sistema informa que el resultado aún no está disponible. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El usuario ingresa a "Mis postulaciones". | El sistema muestra sus postulaciones. |
| 2 | El usuario selecciona una postulación. | El sistema consulta si la entrevista asociada tiene resultado registrado. |
| 3 | El usuario solicita ver el resultado. | El sistema muestra el resultado (Aprobado o No aprobado) y el puntaje. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | La postulación no tiene entrevista o la entrevista todavía está Programada. | El sistema informa que el resultado aún no está disponible. |
| E2 | El usuario intenta consultar una postulación que no le pertenece. | El sistema impide el acceso a la información. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | El resultado se muestra en un máximo de 5 segundos (RNF-02). |
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
| Actores | Principal: Usuario / Postulante |
| Requisitos relacionados | RF-34, RNF-07 |
| Precondiciones | El usuario debe haber iniciado sesión. |
| Postcondiciones | Éxito: el usuario visualiza el estado de cada postulación. / Fallo: el sistema informa que no existen postulaciones. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El usuario ingresa a "Mis postulaciones". | El sistema muestra sus postulaciones con la convocatoria, la fecha y el estado (Postulado, Entrevista programada, Aprobado o No aprobado), indicado con texto. |
| 2 | El usuario selecciona una postulación. | El sistema muestra el detalle de la postulación y su estado actual. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El usuario no posee postulaciones. | El sistema informa que no existen postulaciones registradas y ofrece ir a las convocatorias. |
| E2 | La postulación seleccionada no pertenece al usuario. | El sistema impide el acceso a la información. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | El estado se muestra en un máximo de 5 segundos, y los cambios hechos por la empresa se reflejan en ese mismo plazo (RNF-02). |
| Frecuencia | Alta |
| Importancia | Alta |
| Urgencia | Media |

---

## CU-05 — Cargar CV

| Campo | Detalle |
|-------|---------|
| Identificador | CU-05 |
| Nombre | Cargar CV |
| Descripción | Permite al usuario cargar su currículum en PDF o reemplazar el que ya tiene cargado. |
| Actores | Principal: Usuario / Postulante |
| Requisitos relacionados | RF-09, RF-14 |
| Precondiciones | El usuario debe haber iniciado sesión. |
| Postcondiciones | Éxito: el CV queda almacenado como único CV vigente del usuario. / Fallo: el sistema informa el error y conserva el CV anterior, si existía. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El usuario ingresa a la sección de CV. | El sistema muestra el CV actual, si existe, y la opción para cargar un archivo. |
| 2 | El usuario selecciona un archivo. | El sistema verifica que sea PDF y no supere los 5 MB. |
| 3 | El usuario confirma la carga. | El sistema almacena el CV y lo asocia a su cuenta. |
| 4 | — | El sistema informa que el CV fue cargado correctamente. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El archivo no es PDF. | El sistema informa que solo se aceptan archivos PDF. |
| E2 | No se seleccionó ningún archivo. | El sistema solicita seleccionar un CV. |
| E3 | El archivo supera los 5 MB. | El sistema informa que el archivo excede el tamaño permitido y solicita seleccionar otro. |
| E4 | El usuario ya tiene un CV cargado. | El sistema pide confirmar el reemplazo. Si confirma, el nuevo CV pasa a ser el vigente también en sus postulaciones existentes; si cancela, se conserva el anterior. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | La confirmación de carga se muestra en un máximo de 5 segundos para un archivo de hasta 5 MB. |
| Frecuencia | Media |
| Importancia | Alta |
| Urgencia | Media |

---

## CU-06 — Crear, editar o cerrar convocatoria

| Campo | Detalle |
|-------|---------|
| Identificador | CU-06 |
| Nombre | Crear, editar o cerrar convocatoria |
| Descripción | Permite a la empresa crear convocatorias, modificar las propias o cerrarlas para dejar de recibir postulaciones. |
| Actores | Principal: Empresa |
| Requisitos relacionados | RF-10, RF-20, RF-29, RF-32, RF-33, RF-34 |
| Precondiciones | La empresa debe haber iniciado sesión. Deben existir carreras activas. |
| Postcondiciones | Éxito: la convocatoria queda creada (estado Vigente), modificada o cerrada (estado Cerrada). / Fallo: el sistema informa el error y no guarda cambios. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | La empresa ingresa a la gestión de convocatorias. | El sistema muestra solo las convocatorias de esa empresa. |
| 2 | La empresa selecciona crear una convocatoria o editar una existente. | El sistema muestra el formulario: título, puesto, descripción, requisitos, ubicación, modalidad, fechas, carreras destinatarias y link externo (opcional). |
| 3 | La empresa completa o modifica los datos. | El sistema valida los campos obligatorios, que la fecha de finalización sea posterior a la de inicio y que haya al menos una carrera. |
| 4 | La empresa confirma la operación. | El sistema guarda la convocatoria; si es nueva, con estado Vigente. |
| 5 | La empresa selecciona cerrar una convocatoria y confirma. | El sistema cambia su estado a Cerrada, la quita de las convocatorias disponibles y conserva sus postulaciones. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | Faltan datos obligatorios. | El sistema indica los campos faltantes. |
| E2 | La fecha de finalización no es posterior a la de inicio. | El sistema informa el error y no guarda. |
| E3 | No se seleccionó ninguna carrera destinataria. | El sistema solicita indicar al menos una carrera. |
| E4 | La empresa intenta modificar o cerrar una convocatoria ajena. | El sistema impide la operación. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | Los cambios se guardan y se reflejan para los postulantes en un máximo de 5 segundos (RNF-02). |
| Frecuencia | Alta |
| Importancia | Alta |
| Urgencia | Alta |

---

## CU-07 — Ver postulantes

| Campo | Detalle |
|-------|---------|
| Identificador | CU-07 |
| Nombre | Ver postulantes |
| Descripción | Permite a la empresa consultar los postulantes de sus convocatorias y su CV. |
| Actores | Principal: Empresa |
| Requisitos relacionados | RF-17, RF-32 |
| Precondiciones | La empresa debe haber iniciado sesión y tener al menos una convocatoria. |
| Postcondiciones | Éxito: la empresa visualiza los postulantes y puede abrir su CV. / Fallo: el sistema informa que no existen postulantes. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | La empresa selecciona una de sus convocatorias. | El sistema muestra la información de la convocatoria. |
| 2 | La empresa solicita ver los postulantes. | El sistema muestra la lista con nombre, carrera, fecha de postulación y estado. |
| 3 | La empresa selecciona un postulante. | El sistema muestra sus datos y permite abrir su CV vigente. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | La convocatoria no tiene postulantes. | El sistema informa que no existen postulantes. |
| E2 | La empresa intenta consultar una convocatoria ajena. | El sistema impide el acceso. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | La lista se muestra en un máximo de 5 segundos (RNF-02). |
| Frecuencia | Alta |
| Importancia | Alta |
| Urgencia | Media |

---

## CU-08 — Programar entrevista

| Campo | Detalle |
|-------|---------|
| Identificador | CU-08 |
| Nombre | Programar entrevista |
| Descripción | Permite a la empresa programar una entrevista para un postulante de una de sus convocatorias. |
| Actores | Principal: Empresa |
| Requisitos relacionados | RF-21, RF-32, RF-35, RF-36 |
| Precondiciones | La empresa debe haber iniciado sesión y debe existir una postulación a una de sus convocatorias. |
| Postcondiciones | Éxito: la entrevista queda registrada en estado Programada y la postulación pasa a Entrevista programada. / Fallo: la entrevista no se registra. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | La empresa selecciona un postulante de su convocatoria. | El sistema muestra sus datos y la opción "Programar entrevista". |
| 2 | La empresa selecciona "Programar entrevista". | El sistema muestra el formulario de fecha, hora y modalidad (Presencial o Virtual). |
| 3 | La empresa ingresa los datos. | El sistema valida que estén completos y que la fecha y hora no sean anteriores al momento actual. |
| 4 | La empresa confirma la entrevista. | El sistema registra la entrevista asociada a la postulación y actualiza ambos estados. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | La postulación ya tiene una entrevista. | El sistema informa que ya existe una entrevista para esa postulación. |
| E2 | Faltan fecha, hora o modalidad. | El sistema solicita completar la información. |
| E3 | La fecha y hora son anteriores al momento actual. | El sistema informa que debe elegir una fecha futura. |
| E4 | La postulación corresponde a una convocatoria de otra empresa. | El sistema impide registrar la entrevista. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | La entrevista se registra en un máximo de 5 segundos desde la confirmación y el postulante la ve en ese mismo plazo (RNF-02). |
| Frecuencia | Media |
| Importancia | Alta |
| Urgencia | Alta |

---

## CU-09 — Cargar resultado

| Campo | Detalle |
|-------|---------|
| Identificador | CU-09 |
| Nombre | Cargar resultado |
| Descripción | Permite a la empresa registrar el puntaje y el resultado de una entrevista. |
| Actores | Principal: Empresa |
| Requisitos relacionados | RF-18, RF-32, RF-36 |
| Precondiciones | La empresa debe haber iniciado sesión y debe existir una entrevista Programada de una de sus convocatorias. |
| Postcondiciones | Éxito: la entrevista pasa a Realizada con su puntaje y resultado, y la postulación pasa a Aprobado o No aprobado. / Fallo: el sistema informa el error. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | La empresa selecciona una entrevista. | El sistema muestra la información de la entrevista y del postulante. |
| 2 | La empresa selecciona cargar el resultado. | El sistema muestra el formulario de puntaje y resultado. |
| 3 | La empresa ingresa el puntaje y elige Aprobado o No aprobado. | El sistema valida la información. |
| 4 | La empresa confirma. | El sistema registra el resultado y actualiza el estado de la entrevista y de la postulación. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | La entrevista ya tiene un resultado registrado. | El sistema informa que el resultado ya fue cargado. |
| E2 | No se completa el resultado. | El sistema solicita completar la información. |
| E3 | La entrevista corresponde a una convocatoria de otra empresa. | El sistema impide la operación. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | El resultado se registra en un máximo de 5 segundos desde la confirmación y el postulante lo ve en ese mismo plazo (RNF-02). |
| Frecuencia | Media |
| Importancia | Alta |
| Urgencia | Media |

---

## CU-10 — Gestionar usuarios y permisos

| Campo | Detalle |
|-------|---------|
| Identificador | CU-10 |
| Nombre | Gestionar usuarios y permisos |
| Descripción | Permite al administrador modificar cuentas, asignarles un rol y darlas de baja. |
| Actores | Principal: Administrador |
| Requisitos relacionados | RF-04, RF-05, RF-08 |
| Precondiciones | El administrador debe haber iniciado sesión. |
| Postcondiciones | Éxito: los cambios en la cuenta y su rol quedan registrados. / Fallo: el sistema informa el error. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El administrador ingresa a la gestión de usuarios. | El sistema muestra los usuarios registrados con su rol y estado. |
| 2 | El administrador selecciona un usuario. | El sistema muestra sus datos. |
| 3 | El administrador modifica el rol (Postulante, Empresa o Administrador) o da de baja la cuenta. | El sistema valida los cambios. |
| 4 | El administrador confirma la operación. | El sistema guarda los cambios. Una cuenta dada de baja ya no puede iniciar sesión. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | Un usuario sin rol Administrador intenta acceder. | El sistema deniega el acceso. |
| E2 | El usuario seleccionado no existe. | El sistema informa que el usuario no fue encontrado. |
| E3 | El administrador intenta dar de baja su propia cuenta. | El sistema impide la operación para no dejar el sistema sin administrador. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | Los cambios se registran en un máximo de 5 segundos desde la confirmación (RNF-02). |
| Frecuencia | Media |
| Importancia | Alta |
| Urgencia | Alta |

---

## CU-11 — Generar reportes

| Campo | Detalle |
|-------|---------|
| Identificador | CU-11 |
| Nombre | Generar reportes |
| Descripción | Permite al administrador generar reportes de convocatorias o de entrevistas aplicando filtros. |
| Actores | Principal: Administrador |
| Requisitos relacionados | RF-23 |
| Precondiciones | El administrador debe haber iniciado sesión. |
| Postcondiciones | Éxito: el sistema muestra el reporte solicitado. / Fallo: el sistema informa que no hay datos para los filtros elegidos. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El administrador ingresa a la sección de reportes. | El sistema muestra los tipos de reporte: convocatorias o entrevistas. |
| 2 | El administrador selecciona el tipo de reporte. | El sistema muestra los filtros: período de fechas, empresa y carrera. |
| 3 | El administrador aplica los filtros y solicita el reporte. | El sistema genera y muestra el reporte. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | No existen datos para los filtros seleccionados. | El sistema informa que no hay información disponible. |
| E2 | La fecha "desde" es posterior a la fecha "hasta". | El sistema solicita corregir el período. |
| E3 | No se seleccionó un tipo de reporte. | El sistema solicita seleccionarlo. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | El reporte se genera en un máximo de 5 segundos. |
| Frecuencia | Media |
| Importancia | Media |
| Urgencia | Media |

---

## CU-12 — Ver resultados

| Campo | Detalle |
|-------|---------|
| Identificador | CU-12 |
| Nombre | Ver resultados |
| Descripción | Permite al administrador consultar los resultados registrados de los procesos de selección. |
| Actores | Principal: Administrador |
| Requisitos relacionados | RF-37 |
| Precondiciones | El administrador debe haber iniciado sesión. |
| Postcondiciones | Éxito: el administrador visualiza los resultados. / Fallo: el sistema informa que no existen resultados. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El administrador ingresa a la sección de resultados. | El sistema muestra los resultados con postulante, convocatoria, empresa, puntaje y resultado. |
| 2 | El administrador selecciona un resultado. | El sistema muestra el detalle de la entrevista y la postulación. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | No existen resultados registrados. | El sistema informa que no hay resultados disponibles. |
| E2 | Se produce un error al consultar la información. | El sistema informa que no fue posible obtener los resultados y permite reintentar. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | Los resultados se muestran en un máximo de 5 segundos (RNF-02). |
| Frecuencia | Media |
| Importancia | Alta |
| Urgencia | Media |

---

## CU-13 — Iniciar sesión

| Campo | Detalle |
|-------|---------|
| Identificador | CU-13 |
| Nombre | Iniciar sesión |
| Descripción | Permite a cualquier actor acceder al sistema con su correo y contraseña. |
| Actores | Principal: Usuario / Postulante, Empresa, Administrador |
| Requisitos relacionados | RF-02, RF-03, RF-06, RF-07, RNF-05 |
| Precondiciones | El actor debe tener una cuenta activa. |
| Postcondiciones | Éxito: el actor accede al inicio correspondiente a su rol. / Fallo: el sistema registra el intento fallido y no permite el acceso. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El actor ingresa a la pantalla de acceso. | El sistema solicita correo y contraseña. |
| 2 | El actor ingresa sus credenciales y confirma. | El sistema valida las credenciales y que la cuenta esté activa y no bloqueada. |
| 3 | — | El sistema reinicia el contador de intentos fallidos y muestra el inicio según el rol (CU-14). |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | Las credenciales son incorrectas. | El sistema informa el error sin indicar cuál dato falló y suma un intento fallido. |
| E2 | Es el tercer intento fallido consecutivo. | El sistema bloquea la cuenta durante 15 minutos e informa hasta cuándo. |
| E3 | La cuenta está bloqueada. | El sistema informa que la cuenta está bloqueada temporalmente. |
| E4 | La cuenta fue dada de baja. | El sistema informa que la cuenta no está habilitada. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | La validación responde en un máximo de 5 segundos. |
| Frecuencia | Alta |
| Importancia | Alta |
| Urgencia | Alta |

---

## CU-14 — Ver inicio

| Campo | Detalle |
|-------|---------|
| Identificador | CU-14 |
| Nombre | Ver inicio |
| Descripción | Muestra a cada actor un resumen de su información y acceso solo a los módulos de su rol. |
| Actores | Principal: Usuario / Postulante, Empresa, Administrador |
| Requisitos relacionados | RF-05, RF-24, RF-25 |
| Precondiciones | El actor debe haber iniciado sesión. |
| Postcondiciones | Éxito: el actor visualiza el resumen y el menú de su rol. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El actor ingresa al inicio. | El sistema identifica su rol y muestra el menú con los módulos habilitados. |
| 2 | — | El sistema muestra el resumen: al postulante, sus postulaciones y próximas entrevistas; a la empresa, sus convocatorias vigentes y la cantidad de postulantes; al administrador, la cantidad de convocatorias, postulaciones y entrevistas. |
| 3 | El actor selecciona un módulo o un elemento del resumen. | El sistema lo dirige a la sección correspondiente. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | No hay datos para el resumen (por ejemplo, un postulante sin postulaciones). | El sistema muestra un mensaje en lugar de un bloque vacío. |
| E2 | El actor intenta acceder por URL a un módulo de otro rol. | El sistema deniega el acceso. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | El inicio se muestra en un máximo de 5 segundos (RNF-02). |
| Frecuencia | Alta |
| Importancia | Media |
| Urgencia | Baja |

---

## CU-15 — Registrarse

| Campo | Detalle |
|-------|---------|
| Identificador | CU-15 |
| Nombre | Registrarse |
| Descripción | Permite a un estudiante o egresado crear su cuenta de postulante con el correo institucional. |
| Actores | Principal: Usuario / Postulante |
| Requisitos relacionados | RF-01, RNF-04, RNF-05, RNF-06 |
| Precondiciones | El usuario no debe tener una cuenta registrada. Deben existir carreras activas. |
| Postcondiciones | Éxito: la cuenta queda creada con rol Postulante. / Fallo: el sistema informa el error y no crea la cuenta. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El usuario selecciona "Registrarme". | El sistema muestra el formulario: nombre, apellido, correo, contraseña y carrera. |
| 2 | El usuario completa los datos y elige su carrera. | El sistema valida que el correo sea del dominio institucional, que no esté registrado y que los campos estén completos. |
| 3 | El usuario confirma el registro. | El sistema crea la cuenta con rol Postulante y guarda la contraseña cifrada. |
| 4 | — | El sistema informa que el registro fue exitoso. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El correo no es del dominio institucional. | El sistema informa que debe usar su correo institucional. |
| E2 | El correo ya está registrado. | El sistema informa que ya existe una cuenta con ese correo. |
| E3 | Faltan datos obligatorios o tienen formato inválido. | El sistema indica cada campo con error antes de enviar. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | El registro se confirma en un máximo de 5 segundos. |
| Frecuencia | Media |
| Importancia | Alta |
| Urgencia | Alta |

---

## CU-16 — Consultar entrevista

| Campo | Detalle |
|-------|---------|
| Identificador | CU-16 |
| Nombre | Consultar entrevista |
| Descripción | Permite al usuario ver la fecha, hora y modalidad de la entrevista asignada a una de sus postulaciones. |
| Actores | Principal: Usuario / Postulante |
| Requisitos relacionados | RF-22 |
| Precondiciones | El usuario debe haber iniciado sesión y tener al menos una postulación. |
| Postcondiciones | Éxito: el usuario visualiza los datos de la entrevista. / Fallo: el sistema informa que no hay entrevista asignada. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El usuario ingresa a "Mis postulaciones". | El sistema muestra sus postulaciones con su estado. |
| 2 | El usuario selecciona una postulación con estado Entrevista programada. | El sistema muestra la fecha, la hora, la modalidad y la convocatoria. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | La postulación no tiene entrevista. | El sistema muestra "Sin entrevista asignada". |
| E2 | La postulación no pertenece al usuario. | El sistema impide el acceso. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | La información se muestra en un máximo de 5 segundos (RNF-02). |
| Frecuencia | Media |
| Importancia | Alta |
| Urgencia | Alta |

---

## CU-17 — Dar de alta empresa

| Campo | Detalle |
|-------|---------|
| Identificador | CU-17 |
| Nombre | Dar de alta empresa |
| Descripción | Permite al administrador crear la cuenta de una empresa para que pueda publicar convocatorias. |
| Actores | Principal: Administrador |
| Requisitos relacionados | RF-26, RNF-04 |
| Precondiciones | El administrador debe haber iniciado sesión. |
| Postcondiciones | Éxito: quedan registrados la empresa y su cuenta con rol Empresa. / Fallo: el sistema informa el error y no crea la cuenta. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El administrador selecciona "Nueva empresa". | El sistema muestra el formulario: nombre de la empresa, rubro, nombre y apellido del contacto, correo y contraseña inicial. |
| 2 | El administrador completa los datos. | El sistema valida los campos y que el correo no esté registrado. No exige dominio institucional. |
| 3 | El administrador confirma. | El sistema crea la cuenta con rol Empresa y los datos de la empresa asociados a ella. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El correo ya está registrado. | El sistema informa que ya existe una cuenta con ese correo. |
| E2 | Faltan datos obligatorios. | El sistema indica los campos faltantes. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | El alta se confirma en un máximo de 5 segundos. |
| Frecuencia | Baja |
| Importancia | Alta |
| Urgencia | Alta |

---

## CU-18 — Gestionar carreras

| Campo | Detalle |
|-------|---------|
| Identificador | CU-18 |
| Nombre | Gestionar carreras |
| Descripción | Permite al administrador crear, editar y desactivar las carreras del terciario. |
| Actores | Principal: Administrador |
| Requisitos relacionados | RF-28, RF-31 |
| Precondiciones | El administrador debe haber iniciado sesión. |
| Postcondiciones | Éxito: la carrera queda creada, modificada o desactivada. / Fallo: el sistema informa el motivo y no guarda cambios. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El administrador ingresa a la sección de carreras. | El sistema muestra las carreras con su estado (activa o inactiva). |
| 2 | El administrador crea una carrera o edita una existente. | El sistema valida que el nombre no esté repetido. |
| 3 | El administrador selecciona desactivar una carrera y confirma. | El sistema verifica que no esté indicada en convocatorias vigentes y la desactiva. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | Ya existe una carrera con ese nombre. | El sistema informa que la carrera ya existe. |
| E2 | La carrera está indicada en convocatorias vigentes. | El sistema impide desactivarla e informa cuántas convocatorias la usan. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | Los cambios se registran en un máximo de 5 segundos. |
| Frecuencia | Baja |
| Importancia | Media |
| Urgencia | Alta |

---

## CU-19 — Consultar padrón de usuarios

| Campo | Detalle |
|-------|---------|
| Identificador | CU-19 |
| Nombre | Consultar padrón de usuarios |
| Descripción | Permite al administrador buscar usuarios registrados y ver si tienen CV cargado. |
| Actores | Principal: Administrador |
| Requisitos relacionados | RF-27 |
| Precondiciones | El administrador debe haber iniciado sesión. |
| Postcondiciones | Éxito: el administrador visualiza los usuarios que coinciden con la búsqueda. / Fallo: el sistema informa que no hay resultados. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El administrador ingresa al padrón. | El sistema muestra los usuarios con nombre, apellido, correo, carrera y si tienen CV cargado. |
| 2 | El administrador busca por nombre, apellido o carrera. | El sistema muestra los usuarios que coinciden. |
| 3 | El administrador selecciona un usuario con CV. | El sistema permite abrir su CV. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | La búsqueda no encuentra usuarios. | El sistema informa que no hay resultados. |
| E2 | Un usuario sin rol Administrador intenta acceder. | El sistema deniega el acceso. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | La búsqueda responde en un máximo de 5 segundos. |
| Frecuencia | Media |
| Importancia | Media |
| Urgencia | Baja |
