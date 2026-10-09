# Modelo Entidad-Relación

## Diagrama

_Incluir el código PlantUML en `diagramas/er.puml`._
_Visualizar en [plantuml.com](https://www.plantuml.com/plantuml/uml/)._

## Entidades

| Entidad | Descripción | Relaciones clave |
|---------|-------------|-----------------|
| **Empresa** | Representa a las empresas que publican y gestionan convocatorias laborales. | Publica convocatorias. |
| **Usuario** | Representa a los usuarios que registrados en el sistema que pueden postularse a las convocatorias. | Realiza postulaciones y tiene asociado su CV. |
| **Convocatoria** | Representa una búsqueda laboral publicada por una empresa, con información sobre el puesto, requisitos, fechas y modalidad de trabajo. | Es publicada por una empresa y recibe postulaciones. |
| **Postulación** | Representa la inscripción de un usuario a una convocatoria y permite registrar información sobre el proceso de selección. | Es realizada por un usuario, corresponde a una convocatoria y puede generar una entrevista. |
| **Entrevista** | Representa una instancia de entrevista asociada a una postulación, donde se registra información como fecha, puntaje y estado. | Es generada por una postulación y puede existir como máximo una entrevista por postulación. |

## Descripción de atributos principales

_Para cada entidad, describir brevemente los atributos más relevantes y su propósito._

### Empresa

- `idEmpresa` (PK, Int): identificador único de la empresa.
- `nombre` (String): nombre de la empresa.
- `rubro` (String): actividad o sector al que pertenece.
- `email` (String): correo electrónico de contacto y acceso.
- `contraseña` (String): credencial utilizada para acceder al sistema, almacenada de forma segura.

### Usuario

- `idUsuario` (PK, Int): identificador único del usuario.
- `nombre` (String): nombre del usuario.
- `apellido` (String): apellido del usuario.
- `email` (String): correo electrónico utilizado para acceder al sistema.
- `contraseña` (String): credencial utilizada para acceder al sistema, almacenada de forma segura.
- `sexo` (String): información correspondiente al sexo del usuario.
- `tipoUsuario` (String): identifica el tipo o rol del usuario dentro del sistema.
- `cv` (String): ruta o referencia al archivo del currículum vigente del usuario.

### Convocatoria

- `idConvocatoria` (PK, Int): identificador único de la convocatoria.
- `idEmpresa` (FK, Int): identifica a la empresa que publica la convocatoria.
- `titulo` (String): título de la convocatoria laboral.
- `descripcion` (String): descripción general de la búsqueda.
- `puesto` (String): puesto o cargo ofrecido.
- `ubicacion` (String): lugar donde se desarrolla la actividad.
- `requisitos` (String): requisitos solicitados para el puesto.
- `fechaInicio` (Date): fecha de inicio de la convocatoria.
- `fechaFin` (Date): fecha de finalización de la convocatoria.
- `estado` (String): estado actual de la convocatoria.
- `modalidad` (String): modalidad de trabajo.
- `linkExterno` (String): enlace externo relacionado con la convocatoria.

### Postulación

- `idPostulacion` (PK, Int): identificador único de la postulación.
- `idUsuario` (FK, Int): identifica al usuario que realiza la postulación.
- `idConvocatoria` (FK, Int): identifica la convocatoria a la que se postula.
- `fecha` (Date): fecha en la que el usuario realiza la postulación.
- `estado` (String): estado actual de la postulación.
- `puntaje` (Float): puntaje asociado al proceso de selección.

### Entrevista

- `idEntrevista` (PK, Int): identificador único de la entrevista.
- `idPostulacion` (FK, Int): identifica la postulación a la que pertenece la entrevista.
- `fechaHora` (DateTime): fecha y hora programada para la entrevista.
- `puntaje` (Float): puntaje obtenido en la entrevista.
- `estado` (String): estado actual de la entrevista.

## Decisiones de diseño

_Justificar al menos dos decisiones de diseño relevantes: por qué se modeló de esa manera,
qué alternativas se consideraron y por qué se descartaron._

### Decisión 1 — Entidad Postulación.

Se modeló **Postulación** como una entidad independiente porque representa la relación entre un **Usuario** y una **Convocatoria** y, además, permite almacenar información propia de cada postulación, como la fecha, el estado y el puntaje asociado al proceso de selección.

Una alternativa hubiera sido relacionar directamente Usuario con Convocatoria, pero esta opción no permitiría registrar adecuadamente los datos específicos de cada postulación. Por este motivo, se decidió utilizar Postulación como entidad intermedia, incorporando `idUsuario` e `idConvocatoria` como claves foráneas.

### Decisión 2 — Relación entre Postulación y Entrevista.

Se modeló **Entrevista** como una entidad independiente relacionada con **Postulación**, ya que una postulación puede generar una entrevista cuando el postulante avanza en el proceso de selección.

La relación se definió como `1 — 0..1`, debido a que una postulación puede no tener una entrevista o puede tener una única entrevista. Cada entrevista pertenece obligatoriamente a una postulación.

Una alternativa hubiera sido permitir múltiples entrevistas por postulación, pero esto se descartó porque el modelo actual establece como máximo una entrevista para cada inscripción.

### Decisión 3 — La ubicación del CV.

Se decidió representar el `cv` como un atributo de **Usuario**, porque el sistema contempla que cada postulante tenga un currículum cargado que pueda reemplazar cuando necesite actualizarlo.

Una alternativa sería modelar el CV como una entidad independiente para conservar diferentes versiones del archivo. Pero se optó por mantenerlo como atributo de Usuario porque el alcance actual requiere administrar un único CV vigente por usuario y no contempla un historial de versiones.

### Decisión 4 — Representación del resultado.

Se decidió representar la información del resultado mediante los atributos `puntaje` y `estado` de **Entrevista**, mientras que **Postulación** mantiene sus propios atributos estado y puntaje para registrar la situación y la evaluación general de la inscripción.

Una alternativa sería crear una entidad Resultado independiente. Sin embargo, se descartó porque los requisitos actuales permiten registrar esta información dentro de las entidades existentes, sin agregar una entidad adicional.

### Decisión 5 — Diferenciación entre Usuario y Empresa.

Se decidió modelar **Usuario** y **Empresa** como entidades independientes porque representan conceptos diferentes dentro del sistema. **Usuario** representa a las personas registradas, mientras que **Empresa** representa a las organizaciones que publican convocatorias.

El atributo `tipoUsuario` permite distinguir los roles de las personas registradas, como postulante o administrador. La empresa mantiene sus propios datos de identificación y acceso.

Una alternativa sería utilizar una entidad general de cuenta para centralizar las credenciales de todos los actores. Pero se mantuvieron las entidades separadas para conservar la estructura del modelo actual y diferenciar los datos personales de los datos institucionales.
