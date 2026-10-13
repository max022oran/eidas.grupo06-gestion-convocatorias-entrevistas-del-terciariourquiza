# Modelo Entidad-Relación

## Diagrama

_Incluir el código PlantUML en `diagramas/er.puml`._
_Visualizar en [plantuml.com](//www.plantuml.com/plantuml/png/bLN1SXit3BtlLs1qQPA9tFhGIoRDnBMbYQQfcx6TGuzO4h6HS8aDYTKaxVHZ-WcTt7hLZvMpafRKhfhOFX7l0Ok7Hz1w6HM3TeshbDKH_2gMdC32ArkqyojoQ7ZpnSCShZagDGYMu6TniJ_S1ApnlLJL7QV8S32EglY1VOi16t3iIJ-t11BqBcLz1p_TwoybBYvlLXTd5ulh-nTLv9NrCypECGGAE0ECi3l3dnN04s2xZv_1oYiyV_xcbnSl4ZMVzxoNfWwKo6iDx6yJ_pRnFOL6UPtgql3Y27trLsxuDdOOMFg6k_FGS1yVQpYLiqpiCILR2IqvnrOEKMgGtL79Hhm6ZBJv1ykII9z6dr1kPT2P2RCUeco1P0jwaBsILubBxBN5xIY9gfryx0YjlCAecE0BLBhXXahd5aqRA6wlQdSUdDl7K-V6pcRlol6d5eQk3dd2KiUv-BKOL0cy5LC0ML49JcMDPO-lL5axDtBUKZI1MyFY3ucsewYZvAvcWzFKG1yxZgmI3_5tPEvmvJbLxDpFy99zYL5K7EzL8nOTMxGbxDX_M7nI2lxRFfRFS8f_qzMdC3YNtycOBdk_aPWCxWtgUnRnqAl47h9NnwLcFZlxDLlBnVSQQCrHj_xaS92QeUDAnzECNq4fwfM4yWN-__qUMuMsyuhlAK5B9wW92HGxDndDYnBKeYeDoBlI_bJoQF3rwSZ7nq0HDlzwDl8i9NOUkjq5U4czoHAqsq-5I60bmfeCnPIAu10QZWs2AI_cqTLoVlhZuvEAl0KlIW_wvRbQl3uxN_rskRY6t-7yxEfYTNds-i6_HVk5dVrmSd8wIrVMdvxC86-NwK94-1xeDb3SVAdsp2pdfrF-TuB6a2KmqaYrHsS7tnwjPzlLZWrM1PmhJYSL-OrHrCtVO3dmBLi4pDCSRJSk1ajHsQDY8e1yELbHVhYzWT3n7sEnNoqmN5DLWYFdoWTqIvu2LjLByhPhNFKV)._

## Entidades

| Entidad | Descripción | Relaciones clave |
|---------|-------------|-----------------|
| **Carrera** | Representa una carrera del Terciario Urquiza. Se usa para indicar la formación del postulante y a quiénes está dirigida cada convocatoria. | Es cursada por usuarios y es destinataria de convocatorias (a través de ConvocatoriaCarrera). |
| **Usuario** | Representa toda cuenta que accede al sistema: postulantes, empresas y administradores. Guarda las credenciales, el rol, el CV y los datos de control de acceso. | Pertenece opcionalmente a una carrera, realiza postulaciones y, si su rol es Empresa, tiene asociada una Empresa. |
| **Empresa** | Representa los datos institucionales de una organización que publica convocatorias. | Accede al sistema mediante un Usuario y publica convocatorias. |
| **Convocatoria** | Representa una búsqueda laboral publicada por una empresa, con información sobre el puesto, requisitos, fechas y modalidad de trabajo. | Es publicada por una empresa, está dirigida a una o más carreras y recibe postulaciones. |
| **ConvocatoriaCarrera** | Entidad intermedia que registra a qué carreras está dirigida cada convocatoria. | Relaciona Convocatoria con Carrera. |
| **Postulación** | Representa la inscripción de un usuario a una convocatoria y el estado de su proceso de selección. | Es realizada por un usuario, corresponde a una convocatoria y puede generar una entrevista. |
| **Entrevista** | Representa la entrevista asociada a una postulación, con su fecha, modalidad y el resultado registrado por la empresa. | Pertenece a una postulación; hay como máximo una entrevista por postulación. |

## Descripción de atributos principales

_PK = clave primaria. FK = clave foránea. UK = valor único. Los atributos marcados como opcionales pueden quedar vacíos._

### Carrera

- `idCarrera` (PK, Int): identificador único de la carrera.
- `nombre` (UK, String): nombre de la carrera; no puede repetirse.
- `activa` (Boolean): indica si la carrera se ofrece en el registro y al crear convocatorias (RF-28, RF-31).

### Usuario

- `idUsuario` (PK, Int): identificador único del usuario.
- `idCarrera` (FK, Int, opcional): carrera que cursa o de la que egresó. Obligatorio para postulantes; vacío para empresas y administradores (RF-01).
- `nombre` (String): nombre del usuario. En una cuenta de empresa, el de la persona de contacto.
- `apellido` (String): apellido del usuario.
- `email` (UK, String): correo utilizado para acceder al sistema. Para postulantes debe ser del dominio institucional (RNF-04).
- `contraseña` (String): credencial de acceso, almacenada de forma cifrada, nunca en texto plano (RNF-05).
- `sexo` (String, opcional): información correspondiente al sexo del usuario.
- `tipoUsuario` (String): rol dentro del sistema. Valores: Postulante, Empresa o Administrador (RF-04).
- `cv` (String, opcional): ruta al archivo PDF del currículum vigente. Vacío hasta que el postulante lo carga (RF-09).
- `activo` (Boolean): indica si la cuenta puede iniciar sesión; el administrador la desactiva al darla de baja (RF-08).
- `intentosFallidos` (Int): cantidad de intentos de acceso incorrectos consecutivos (RF-06).
- `bloqueadoHasta` (DateTime, opcional): momento hasta el que la cuenta queda bloqueada luego de 3 intentos fallidos (RF-07).

### Empresa

- `idEmpresa` (PK, Int): identificador único de la empresa.
- `idUsuario` (FK, UK, Int): cuenta con la que la empresa accede al sistema. Cada cuenta corresponde a una sola empresa.
- `nombre` (String): nombre de la empresa.
- `rubro` (String, opcional): actividad o sector al que pertenece.

### Convocatoria

- `idConvocatoria` (PK, Int): identificador único de la convocatoria.
- `idEmpresa` (FK, Int): empresa que publica la convocatoria.
- `titulo` (String): título de la convocatoria.
- `descripcion` (String): descripción general de la búsqueda.
- `puesto` (String): puesto o cargo ofrecido.
- `ubicacion` (String): lugar donde se desarrolla la actividad.
- `requisitos` (String): requisitos solicitados para el puesto.
- `fechaInicio` (Date): fecha de inicio de la convocatoria.
- `fechaFin` (Date): fecha de finalización; debe ser posterior a `fechaInicio` (RF-33).
- `estado` (String): Vigente, Cerrada o Vencida (RF-34).
- `modalidad` (String): modalidad de trabajo (presencial, remota o híbrida).
- `linkExterno` (String, opcional): enlace externo relacionado con la convocatoria.

### ConvocatoriaCarrera

- `idConvocatoria` (PK, FK, Int): convocatoria.
- `idCarrera` (PK, FK, Int): carrera a la que está dirigida.

_La clave primaria es la combinación de ambos atributos, por lo que una carrera no puede repetirse en la misma convocatoria._

### Postulación

- `idPostulacion` (PK, Int): identificador único de la postulación.
- `idUsuario` (FK, Int): usuario que se postula.
- `idConvocatoria` (FK, Int): convocatoria a la que se postula.
- `fecha` (Date): fecha en la que se realizó la postulación.
- `estado` (String): Postulado, Entrevista programada, Aprobado o No aprobado (RF-34).

_La combinación (`idUsuario`, `idConvocatoria`) es única: un usuario no puede postularse dos veces a la misma convocatoria (RF-15)._

### Entrevista

- `idEntrevista` (PK, Int): identificador único de la entrevista.
- `idPostulacion` (FK, UK, Int): postulación a la que pertenece. Al ser única, garantiza una sola entrevista por postulación.
- `fechaHora` (DateTime): fecha y hora programadas; no puede ser anterior al momento en que se programa (RF-35).
- `modalidad` (String): Presencial o Virtual (RF-21).
- `estado` (String): Programada o Realizada (RF-36).
- `puntaje` (Float, opcional): puntaje asignado por la empresa al registrar el resultado.
- `resultado` (String, opcional): Aprobado o No aprobado. Vacío mientras la entrevista está Programada (RF-18).

## Decisiones de diseño

### Decisión 1 — Entidad Postulación.

Se modeló **Postulación** como una entidad independiente porque representa la relación entre un **Usuario** y una **Convocatoria** y, además, permite almacenar información propia de cada postulación, como la fecha y el estado.

Una alternativa hubiera sido relacionar directamente Usuario con Convocatoria, pero esta opción no permitiría registrar los datos de cada postulación. Por eso se utiliza Postulación como entidad intermedia, con `idUsuario` e `idConvocatoria` como claves foráneas. Además, la combinación de ambas es única, lo que lleva al modelo la regla de que no se puede postular dos veces a la misma convocatoria.

### Decisión 2 — Relación entre Postulación y Entrevista.

Se modeló **Entrevista** como una entidad independiente relacionada con **Postulación**, ya que una postulación puede generar una entrevista cuando el postulante avanza en el proceso de selección.

La relación es `1 — 0..1`: una postulación puede no tener entrevista o tener una sola, y cada entrevista pertenece obligatoriamente a una postulación. Para que el modelo lo garantice, `idPostulacion` es único dentro de Entrevista.

Una alternativa hubiera sido permitir varias entrevistas por postulación (por ejemplo, una primera entrevista y una técnica). Se descartó porque los requisitos actuales contemplan una única entrevista por inscripción.

### Decisión 3 — La ubicación del CV.

Se representó el `cv` como un atributo de **Usuario**, porque cada postulante tiene un único CV vigente que puede reemplazar cuando lo necesita (RF-09), y el sistema lo usa automáticamente en cada postulación (RF-14).

Una alternativa sería modelar el CV como una entidad independiente para conservar sus versiones, o guardar una copia en cada Postulación. Se descartó porque el alcance actual no contempla historial: al reemplazar el CV, las empresas ven la versión vigente también en las postulaciones ya realizadas.

### Decisión 4 — Representación del resultado.

El resultado de la entrevista se guarda en los atributos `puntaje` y `resultado` de **Entrevista**. La **Postulación** no repite el puntaje: solo actualiza su `estado` (Aprobado o No aprobado) cuando la empresa registra el resultado.

En la versión anterior del modelo, Postulación también tenía un atributo `puntaje`. Se eliminó porque duplicaba el dato de Entrevista y podía quedar inconsistente si se modificaba uno solo de los dos. Otra alternativa era crear una entidad Resultado independiente; se descartó porque cada entrevista tiene un único resultado y no tiene datos propios que justifiquen otra entidad.

### Decisión 5 — Relación entre Usuario y Empresa.

Todas las cuentas que acceden al sistema (postulantes, empresas y administradores) son registros de **Usuario**, que guarda el email, la contraseña, el rol (`tipoUsuario`) y los datos de bloqueo. **Empresa** guarda solo los datos institucionales y se vincula a su cuenta mediante `idUsuario`.

En la versión anterior, Empresa tenía su propio email y contraseña. Se cambió porque los requisitos definen tres roles dentro del mismo sistema de acceso (RF-04) y exigen que el bloqueo por intentos fallidos y la baja de cuentas (RF-07, RF-08) funcionen igual para todos. Con credenciales en dos entidades, esas reglas tendrían que implementarse dos veces. El Administrador no necesita una entidad propia porque no tiene datos adicionales: es un Usuario con `tipoUsuario` = Administrador.

### Decisión 6 — Carreras y su relación con las convocatorias.

Se agregó la entidad **Carrera** en lugar de guardar la carrera como texto libre, para que el administrador mantenga una única lista (RF-28) y para poder filtrar convocatorias por carrera sin errores de escritura (RF-30).

Como una convocatoria puede estar dirigida a varias carreras y una carrera puede recibir muchas convocatorias, la relación es de muchos a muchos. Se resolvió con la entidad intermedia **ConvocatoriaCarrera**. La alternativa de poner un único `idCarrera` en Convocatoria se descartó porque obligaría a duplicar una convocatoria para ofrecerla a más de una carrera.

Las carreras no se borran: se desactivan con el atributo `activa`, porque eliminarlas dejaría sin carrera a los usuarios y convocatorias que ya la tienen registrada.
