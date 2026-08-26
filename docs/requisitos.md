# Requisitos del sistema

## Descripción del sistema

_Desarrollo de un sistema web que permite gestionar convocatorias, entrevistas y postulaciones, centralizando toda la información en una sola plataforma._

## Requisitos funcionales

### Módulo 1 — [Gestión de Usuarios y Control de Acceso]

| ID | Requisito |
|----|-----------|
|RF-01| El usuario debe poder registrarse utilizando su mail institucional. |
|RF-02|	El usuario debe poder acceder al sistema mediante sus credenciales. |
|RF-03|	El sistema debe validar las credenciales del usuario para permitir el acceso. |
|RF-04|	El sistema debe permitir diferentes tipos de usuarios según su rol. |
|RF-05|	El sistema debe restringir el acceso a las funcionalidades de acuerdo con el rol del usuario. |
|RF-06|	El sistema debe registrar los intentos de acceso fallidos. |
|RF-07|	El sistema debe bloquear temporalmente el acceso ante múltiples intentos de autenticación incorrectos. |
|RF-08|	El administrador debe poder gestionar las cuentas de los usuarios. |

### Módulo 2 — [Convocatorias]

| ID | Requisito |
|----|-----------|
|RF-09|	El administrador debe poder crear convocatorias. |
|RF-10|	El usuario debe poder visualizar las convocatorias disponibles. |
|RF-11|	El usuario debe poder postularse a una convocatoria. |
|RF-12|	El sistema debe validar que el usuario tenga un CV cargado antes de permitirle postularse. |
|RF-13|	El sistema debe utilizar automáticamente el CV cargado por el usuario en cada postulación. |
|RF-14|	El sistema debe impedir que un usuario se postule dos veces a la misma convocatoria. |
|RF-15|	El sistema debe ocultar las convocatorias que se encuentren vencidas. |
|RF-16|	El administrador debe poder visualizar y evaluar a los postulantes de una convocatoria. |
|RF-17|	El sistema debe permitir registrar los resultados de las postulaciones. |
|RF-18|	El sistema debe mostrar al usuario los resultados de sus postulaciones. |

## Requisitos no funcionales

### Rendimiento y disponibilidad

| ID | Requisito |
|----|-----------|
|RNF-01|	El sistema debe ser accesible desde el navegador web.|
|RNF-02|	El sistema debe actualizar la información en tiempo real.|

### Seguridad y usabilidad

| ID | Requisito |
|----|-----------|
|RNF-03|	El sistema debe ser fácil de usar. El proceso de postulación no debe requerir más de 4 pasos una vez que el usuario ha iniciado sesión.|
|RNF-04|	El sistema debe restringir el acceso únicamente a usuarios con correos institucionales válidos.|
|RNF-05|	El sistema debe garantizar la seguridad de los datos.|
|RNF-06|	El sistema debe validar correctamente los formularios.|
