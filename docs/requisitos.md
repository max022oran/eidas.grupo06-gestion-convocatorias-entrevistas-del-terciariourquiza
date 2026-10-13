# Requisitos del sistema

## Descripción del sistema

_Desarrollo de un sistema web que permite gestionar convocatorias, entrevistas y postulaciones, centralizando toda la información en una sola plataforma._

## Requisitos funcionales

### Módulo 1 — Inicio

| ID | Requisito |
|----|-----------|
|RF-24| Al iniciar sesión, el sistema debe mostrar una pantalla de inicio con acceso únicamente a los módulos habilitados para el rol del usuario. |
|RF-25| La pantalla de inicio debe mostrar un resumen según el rol: al postulante, sus postulaciones y sus próximas entrevistas; a la empresa, sus convocatorias vigentes con la cantidad de postulantes de cada una; al administrador, la cantidad de convocatorias, postulaciones y entrevistas registradas. |

### Módulo 2 — Usuario / Postulante

| ID | Requisito |
|----|-----------|
|RF-01| El postulante debe poder registrarse utilizando su correo institucional, indicando la carrera que cursa o de la que egresó. |
|RF-02| El usuario debe poder acceder al sistema mediante sus credenciales. |
|RF-03| El sistema debe validar las credenciales del usuario para permitir el acceso. |
|RF-04| El sistema debe manejar tres roles: Postulante, Empresa y Administrador. |
|RF-05| El sistema debe restringir el acceso a las funcionalidades de acuerdo con el rol del usuario. |
|RF-06| El sistema debe registrar los intentos de acceso fallidos. |
|RF-07| El sistema debe bloquear el acceso a una cuenta durante 15 minutos luego de 3 intentos de autenticación incorrectos consecutivos. |
|RF-08| El administrador debe poder dar de alta, modificar y dar de baja cuentas de usuario, y asignarles su rol. |
|RF-09| El usuario debe poder cargar y reemplazar su currículum vitae en formato PDF, de hasta 5 MB, quedando asociado a su cuenta. Cada usuario tiene un único CV vigente; si ya tiene uno cargado, el sistema debe pedir confirmación antes de reemplazarlo. |
|RF-26| El administrador debe poder dar de alta las cuentas de las empresas. Las empresas acceden con el correo y la contraseña registrados por el administrador, sin requerir correo institucional. |
|RF-27| El administrador debe poder consultar el listado de usuarios registrados, buscarlos por nombre, apellido o carrera y ver si tienen un CV cargado. |

### Módulo 3 — Carreras

| ID | Requisito |
|----|-----------|
|RF-28| El administrador debe poder crear, editar y desactivar las carreras del Terciario Urquiza. |
|RF-29| La empresa debe poder indicar una o más carreras destinatarias en cada convocatoria. |
|RF-30| El usuario debe poder filtrar las convocatorias disponibles por carrera. |
|RF-31| El sistema debe impedir desactivar una carrera que esté indicada en convocatorias vigentes. Las carreras desactivadas no se ofrecen en el registro ni en nuevas convocatorias. |

### Módulo 4 — Convocatorias

| ID | Requisito |
|----|-----------|
|RF-10| La empresa debe poder crear y editar sus convocatorias. |
|RF-11| El usuario debe poder visualizar las convocatorias disponibles y consultar el detalle de cada una. |
|RF-12| El usuario debe poder postularse a una convocatoria. |
|RF-13| El sistema debe validar que el usuario tenga un CV cargado antes de permitirle postularse. |
|RF-14| El sistema debe utilizar automáticamente el CV cargado por el usuario en cada postulación. |
|RF-15| El sistema debe impedir que un usuario se postule dos veces a la misma convocatoria. |
|RF-16| El sistema debe ocultar las convocatorias que se encuentren vencidas. |
|RF-17| La empresa debe poder visualizar los postulantes de sus convocatorias y consultar el CV de cada uno. |
|RF-18| La empresa debe poder registrar el resultado de cada postulación, quedando asociado a la entrevista correspondiente. |
|RF-19| El sistema debe mostrar al usuario el resultado de sus postulaciones una vez registrado por la empresa. |
|RF-20| La empresa debe poder cerrar sus convocatorias para impedir nuevas postulaciones. |
|RF-32| La empresa solo debe poder ver y modificar sus propias convocatorias, y los postulantes y entrevistas asociados a ellas. |
|RF-33| El sistema debe validar que la fecha de finalización de una convocatoria sea posterior a su fecha de inicio. |
|RF-34| El sistema debe manejar los siguientes estados. Convocatoria: Vigente, Cerrada (por la empresa) o Vencida (al superar la fecha de finalización). Postulación: Postulado, Entrevista programada, Aprobado o No aprobado. |

### Módulo 5 — Entrevistas

| ID | Requisito |
|----|-----------|
|RF-21| La empresa debe poder programar entrevistas para los postulantes de sus convocatorias, indicando fecha, hora y modalidad. |
|RF-22| El usuario debe poder consultar la información de las entrevistas asignadas a sus postulaciones. |
|RF-23| El administrador debe poder generar reportes de convocatorias y entrevistas aplicando filtros según la información seleccionada. |
|RF-35| El sistema debe impedir programar una entrevista con fecha y hora anteriores al momento actual. |
|RF-36| El sistema debe manejar los estados de la entrevista: Programada o Realizada. Al registrarse el resultado, la entrevista pasa a Realizada. |
|RF-37| El administrador debe poder consultar los resultados registrados de los procesos de selección. |

## Requisitos no funcionales

### Rendimiento y disponibilidad

| ID | Requisito |
|----|-----------|
|RNF-01|	El sistema debe ser accesible desde navegadores web modernos (Google Chrome, Mozilla Firefox y Microsoft Edge) sin requerir la instalación de software adicional.|
|RNF-02|	El sistema debe reflejar los cambios realizados en convocatorias, postulaciones y estados de entrevistas en un tiempo máximo de 5 segundos para los usuarios autorizados.|

### Usabilidad y accesibilidad

| ID | Requisito |
|----|-----------|
|RNF-03| El proceso de postulación no debe requerir más de 4 pasos una vez que el usuario ha iniciado sesión.|
|RNF-07| Los estados (convocatoria, postulación y entrevista) deben indicarse con texto, y todos los campos de formulario deben tener una etiqueta visible.|

### Seguridad y validación

| ID | Requisito |
|----|-----------|
|RNF-04| El sistema debe permitir el registro de postulantes únicamente con un correo electrónico institucional del dominio autorizado por la institución. Las cuentas de empresa son creadas por el administrador (RF-26).|
|RNF-05| El sistema debe requerir autenticación mediante correo y contraseña para acceder a las funciones que involucren información personal o administrativa. Las contraseñas no deben almacenarse en texto plano.|
|RNF-06| El sistema debe impedir el envío de formularios que contengan campos obligatorios vacíos o datos con formato inválido, mostrando un mensaje de error específico antes de permitir su envío.|
