# Modelo Entidad-Relación

## Diagrama

_Incluir el código PlantUML en `diagramas/er.puml`._
_Visualizar en [plantuml.com](https://www.plantuml.com/plantuml/uml/)._

## Entidades

| Entidad | Descripción | Relaciones clave |
|---------|-------------|-----------------|
| **Empresa** | Representa a las empresas que publican y gestionan convocatorias laborales. | Publica convocatorias y consulta postulantes. |
| **Usuario** | Representa a los usuarios que se registran en el sistema y pueden postularse a las convocatorias. | Realiza postulaciones. |
| **Convocatoria** | Representa una búsqueda laboral publicada por una empresa, con información sobre el puesto, requisitos, fechas y modalidad. | Es publicada por una empresa y recibe postulaciones. |
| **Postulación** | Representa la inscripción de un usuario a una convocatoria determinada y permite registrar información sobre el proceso de selección. | Es realizada por un usuario, corresponde a una convocatoria y puede generar una entrevista. |
| **Entrevista** | Representa una instancia de entrevista asociada a una postulación, donde se registra información como fecha, puntaje y estado. | Es generada por una postulación. |

## Descripción de atributos principales

_Para cada entidad, describir brevemente los atributos más relevantes y su propósito._

### Empresa

- `idEmpresa` (PK): Identificador único de la empresa.
- `nombre`: Nombre de la empresa.
- `rubro`: Actividad o sector al que pertenece la empresa.
- `email`: Correo electrónico de contacto de la empresa.
- `contraseña`: Credencial utilizada para acceder al sistema.

### Usuario

- `idUsuario` (PK): Identificador único del usuario.
- `nombre`: Nombre del usuario.
- `apellido`: Apellido del usuario.
- `email`: Correo electrónico utilizado para acceder al sistema.
- `contraseña`: Credencial utilizada para acceder al sistema.
- `sexo`: Información correspondiente al sexo del usuario.
- `tipoUsuario`: Indica el tipo de usuario registrado en el sistema.

### Convocatoria

- `idConvocatoria` (PK): Identificador único de la convocatoria.
- `titulo`: Nombre o título de la convocatoria.
- `descripcion`: Descripción general de la búsqueda laboral.
- `puesto`: Puesto o cargo ofrecido.
- `ubicacion`: Lugar donde se desarrolla la actividad.
- `requisitos`: Requisitos solicitados para el puesto.
- `fechaInicio`: Fecha a partir de la cual se encuentra disponible la convocatoria.
- `fechaFin`: Fecha de finalización de la convocatoria.
- `estado`: Estado actual de la convocatoria.
- `modalidad`: Modalidad de trabajo.
- `linkExterno`: Enlace externo relacionado con la convocatoria.

### Postulación

- `idPostulacion` (PK): Identificador único de la postulación.
- `fecha`: Fecha en la que el usuario realiza la postulación.
- `estado`: Estado actual de la postulación.
- `puntaje`: Puntaje obtenido durante el proceso de selección.
- `cv`: Referencia al currículum utilizado en la postulación.

### Entrevista

- `idEntrevista` (PK): Identificador único de la entrevista.
- `fechaHora`: Fecha y hora en que se realiza la entrevista.
- `puntaje`: Puntaje obtenido en la entrevista.
- `estado`: Estado de la entrevista.

## Decisiones de diseño

_Justificar al menos dos decisiones de diseño relevantes: por qué se modeló de esa manera,
qué alternativas se consideraron y por qué se descartaron._

### Decisión 1 — Entidad Postulación

Se modeló **Postulación** como una entidad independiente porque permite representar la relación entre un **Usuario** y una **Convocatoria** y, además, almacenar información propia de cada postulación, como la fecha, el estado, el puntaje y el CV utilizado.

Una alternativa hubiera sido relacionar directamente Usuario con Convocatoria, pero esta opción no permitiría registrar adecuadamente los datos específicos de cada postulación. Por este motivo, se decidió utilizar Postulación como entidad intermedia.

### Decisión 2 — Relación entre Postulación y Entrevista

Se modeló **Entrevista** como una entidad independiente relacionada con **Postulación**, ya que una postulación puede generar una entrevista cuando el postulante avanza en el proceso de selección.

La relación se definió como `1 — 0..1`, debido a que una postulación puede no tener una entrevista o puede tener una única entrevista según el modelo actual. Una alternativa sería permitir múltiples entrevistas por postulación, pero el diagrama actual establece como máximo una entrevista.
