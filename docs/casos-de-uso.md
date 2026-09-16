# Casos de uso

## Diagrama general

_Incluir el código PlantUML en `diagramas/casos-de-uso.puml`._
_Visualizar en [plantuml.com](https://www.plantuml.com/plantuml/uml/)._

<img width="1302" height="848" alt="image" src="https://github.com/user-attachments/assets/126a1c90-e1d0-4ef7-af2d-13d608fac845" />

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
