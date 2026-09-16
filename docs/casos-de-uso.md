# Casos de uso

## Diagrama general

_Incluir el código PlantUML en `diagramas/casos-de-uso.puml`._
_Visualizar en [plantuml.com](https://www.plantuml.com/plantuml/uml/)._

<img width="429" height="654" alt="image" src="https://github.com/user-attachments/assets/ff2ea0f7-4a6a-4008-a702-a681574bd9ee" />

_Describir brevemente los actores identificados y las relaciones principales (include, extend)._

1. Usuario
Es el postulante que utiliza el sistema para consultar las convocatorias disponibles y participar en los procesos de selección. Sus principales acciones son:
Ver convocatorias.
Postularse a una convocatoria.
Ver resultado de su postulación.

2. Administrador / Empresa
Es el actor encargado de gestionar las convocatorias y realizar el proceso de selección de los postulantes. Sus principales acciones son:
Crear convocatoria.
Ver postulantes.
Entrevistar postulantes.
Cargar resultado de las entrevistas.

<<include>>
Ver convocatorias → incluye → Postularse a convocatoria.
Postularse a convocatoria → incluye → Ver resultado.
Ver postulantes → incluye → Entrevistar postulantes.
Entrevistar postulantes → incluye → Cargar resultado.

<<extend>>
Crear convocatoria → extiende → Ver postulantes.

---

## CU-01 — [Ver convocatorias]

| Campo | Detalle |
|-------|---------|
| Identificador | CU-01 |
| Nombre | Ver convocatorias |
| Descripción | Permite al usuario consultar las convocatorias laborales disponibles en el sistema. |
| Actores | Principal: Usuario / Secundario: Sistema |
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

## CU-02 — [Postularse a convocatoria]

| Campo | Detalle |
|-------|---------|
| Identificador | CU-02 |
| Nombre | Postularse a convocatoria |
| Descripción | Permite al usuario enviar su postulación a una convocatoria laboral vigente. |
| Actores | Principal: Usuario / Secundario: Sistema |
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

## CU-03 — [Ver resultado]

| Campo | Detalle |
|-------|---------|
| Identificador | CU-03 |
| Nombre | Ver resultado |
| Descripción | Permite al usuario consultar el resultado de sus postulaciones una vez que haya sido registrado y habilitado para su consulta. |
| Actores | Principal: Usuario / Secundario: Sistema |
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

## CU-04 — [Crear convocatoria]

| Campo | Detalle |
|-------|---------|
| Identificador | CU-04 |
| Nombre | Crear convocatoria |
| Descripción | Permite a la empresa registrar una nueva convocatoria laboral en el sistema. |
| Actores | Principal: Administrador/Empresa / Secundario: Sistema |
| Precondiciones | El actor debe estar autenticado y contar con permisos para gestionar convocatorias. |
| Postcondiciones | Éxito: La convocatoria queda registrada y disponible según su vigencia. / Fallo: La convocatoria no se registra y el sistema informa los errores encontrados. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El administrador/empresa selecciona la opción para crear una convocatoria. | El sistema muestra el formulario de creación. |
| 2 | El actor completa los campos obligatorios. | El sistema valida los datos ingresados. |
| 3 | El actor confirma la creación. | El sistema verifica que la información sea válida y registra la convocatoria. |
| 4 | El actor finaliza la operación. | El sistema informa que la convocatoria fue creada correctamente. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | Faltan campos obligatorios. | El sistema solicita completar la información faltante. |
| E2 | La fecha de vencimiento es anterior o igual a la fecha de publicación. | El sistema informa que las fechas ingresadas no son válidas. |
| E3 | Los datos ingresados no cumplen con las validaciones. | El sistema informa los errores y solicita corregirlos. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | La convocatoria debe registrarse inmediatamente después de una validación exitosa. |
| Frecuencia | Media |
| Importancia | Alta |
| Urgencia | Alta |
