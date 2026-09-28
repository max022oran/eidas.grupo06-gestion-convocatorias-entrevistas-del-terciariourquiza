# Historias de usuario

_Presentar al menos una historia de usuario representativa por módulo._
_Cada historia debe incluir formato clásico, criterios de aceptación y validación INVEST._

---

## HU-01 — Empresa crea convocatoria laboral

| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero crear una convocatoria laboral para publicar nuevas búsquedas de personal. |
| Módulo | Inicio |
| Requisitos relacionados | RF-10, RF-16 |

### Criterios de aceptación

1. La empresa debe haber iniciado sesión.
2. Debe completar todos los campos obligatorios.
3. La fecha de vencimiento debe ser posterior a la fecha de publicación.
4. El sistema debe validar los datos antes de guardar.
5. La convocatoria debe quedar registrada.
6. Si se encuentra vigente, debe aparecer entre las convocatorias disponibles.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí, porque puede desarrollarse como una funcionalidad independiente para la creación de convocatorias. | Requiere que la empresa esté autenticada. |
| Negociable | Sí, porque los campos y detalles de la convocatoria pueden acordarse y modificarse durante el desarrollo. | La información obligatoria ya está definida. |
| Valiosa | Sí, porque permite a la empresa publicar nuevas oportunidades laborales para recibir postulaciones. | Aporta una función principal al sistema. |
| Estimable | Sí, porque tiene un alcance concreto y permite estimar las tareas necesarias para crear una convocatoria. | Incluye completar, validar y guardar los datos. |
| Pequeña | Sí, porque se concentra únicamente en crear y registrar una convocatoria. | No incluye otras tareas de gestión. |
| Verificable | Sí, porque los criterios de aceptación permiten comprobar que la convocatoria se crea y registra correctamente. | Se puede comprobar mediante pruebas. |

---

## HU-02 — Empresa edita o cierra convocatorias

| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero editar o cerrar convocatorias para mantener actualizada la información disponible. |
| Módulo |Inicio |
| Requisitos relacionados | RF-10, RF-20 |

### Criterios de aceptación

1. La empresa debe estar autenticada.
2. Solo podrá modificar convocatorias pertenecientes a dicha empresa.
3. El sistema debe permitir modificar los datos habilitados.
4. La empresa debe poder cerrar una convocatoria.
5. Una convocatoria cerrada no deberá aceptar nuevas postulaciones.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí, porque puede desarrollarse como una funcionalidad específica para modificar o cerrar convocatorias existentes. | Requiere que exista una convocatoria y que la empresa esté autenticada. |
| Negociable | Sí, porque la forma de editar los datos y las condiciones para cerrar una convocatoria pueden acordarse durante el desarrollo. | Los detalles de la interfaz pueden modificarse sin cambiar el objetivo de la historia. |
| Valiosa | Sí, porque permite a la empresa mantener actualizada la información de sus convocatorias y controlar cuándo dejan de aceptar postulaciones. | Facilita la gestión de las búsquedas laborales. |
| Estimable | Sí, porque las tareas necesarias para modificar y cerrar una convocatoria tienen un alcance definido. | Se pueden identificar las tareas de edición, validación y cierre. |
| Pequeña | No, porque incluye dos acciones diferentes: editar una convocatoria y cerrarla. | Podría dividirse en dos historias más pequeñas. |
| Verificable | Sí, porque se puede comprobar que los datos se modifican correctamente y que una convocatoria cerrada no acepta nuevas postulaciones. | Los criterios de aceptación permiten realizar las pruebas. |

---

## HU-03 — Registrarme

| Campo | Detalle |
|-------|---------|
| Historia | Como usuario, quiero registrarme en el sistema para poder postularme a diferentes convocatorias.|
| Módulo | Usuario |
| Requisitos relacionados | RF-01, RF-03 |

### Criterios de aceptación

1. El usuario debe ingresar un correo institucional válido.
2. Los campos obligatorios deben estar completos.
3. El correo no debe estar registrado previamente.
4. El sistema debe validar los datos.
5. Si son correctos, debe registrar al usuario.
6. El sistema debe informar que el registro fue exitoso.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí, porque el registro de usuario puede desarrollarse como una funcionalidad específica del sistema. | No necesita que estén desarrolladas las demás funcionalidades para comprobar el registro. |
| Negociable | Sí, porque los campos del formulario y la forma de validar los datos pueden acordarse durante el desarrollo. | El objetivo principal de registrar al usuario se mantiene. |
| Valiosa | Sí, porque permite al usuario crear una cuenta para acceder al sistema y participar en las convocatorias. | Es necesaria para que el usuario pueda utilizar las funcionalidades destinadas a postulantes. |
| Estimable | Sí, porque tiene un alcance definido relacionado con completar, validar y guardar los datos del usuario. | Las tareas necesarias pueden identificarse y estimarse. |
| Pequeña | Sí, porque se concentra en una única funcionalidad: registrar un usuario. | No incorpora otras funcionalidades del sistema. |
| Verificable | Sí, porque se puede comprobar que un usuario válido se registra y que los datos incorrectos son rechazados. | Los criterios de aceptación permiten comprobar el funcionamiento. |

---

## HU-04 — Cargar CV

| Campo | Detalle |
|-------|---------|
| Historia | Como usuario, quiero cargar mi currículum y datos personales para facilitar el proceso de selección. |
| Módulo | Usuario |
| Requisitos relacionados | RF-09 |

### Criterios de aceptación

1. El usuario debe estar autenticado.
2. El archivo debe estar en formato PDF.
3. El sistema debe guardar el CV.
4. El CV debe quedar asociado al usuario.
5. El sistema debe mostrar una confirmación de carga.
6. El CV debe poder utilizarse posteriormente para realizar postulaciones.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí, porque la carga del CV puede desarrollarse como una funcionalidad específica asociada al usuario. | Requiere que el usuario esté registrado y autenticado. |
| Negociable | Sí, porque la forma de seleccionar, validar y mostrar el archivo puede acordarse durante el desarrollo. | El objetivo de almacenar el CV no cambia. |
| Valiosa | Sí, porque permite al usuario disponer de su CV para utilizarlo en sus postulaciones. | Facilita el proceso de selección. |
| Estimable | Sí, porque el alcance se limita a seleccionar, validar, almacenar y asociar el CV al usuario. | Las tareas necesarias están claramente definidas.El alcance de carga y asociación del CV está definido. |
| Pequeña | Sí, porque se centra en cargar y almacenar el CV del usuario. | No incluye la realización de una postulación. |
| Verificable | Sí, porque se puede comprobar que un archivo válido se almacena correctamente y queda asociado al usuario. | También se puede verificar el rechazo de archivos no válidos. |

---

## HU-05 — Postularme a una convocatoria

| Campo | Detalle |
|-------|---------|
| Historia | Como usuario, quiero postularme a una convocatoria para participar en el proceso de selección. |
| Módulo | Usuario |
| Requisitos relacionados | RF-12, RF-13, RF-14, RF-15 |

### Criterios de aceptación

1. El usuario debe estar autenticado.
2. El usuario debe tener un CV cargado.
3. La convocatoria debe encontrarse vigente.
4. El usuario no debe estar previamente postulado a esa convocatoria.
5. El sistema debe registrar la postulación.
6. El sistema debe registrar la fecha de postulación.
7. El sistema debe mostrar un mensaje de confirmación.
8. La postulación debe aparecer en "Mis postulaciones".

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí, porque la postulación puede implementarse como una funcionalidad específica una vez disponibles los datos del usuario y la convocatoria. | Utiliza información existente del usuario y de la convocatoria. |
| Negociable | Sí, porque la forma de confirmar la postulación y mostrar la información puede acordarse durante el desarrollo. | El objetivo de registrar la postulación permanece igual. |
| Valiosa | Sí, porque permite al usuario participar en los procesos de selección publicados mediante el sistema. | Es una de las funciones principales para el postulante. |
| Estimable | Sí, porque tiene un alcance definido: validar las condiciones y registrar la postulación. | Las tareas necesarias pueden identificarse y estimarse. |
| Pequeña | Sí, porque se concentra en realizar una postulación a una convocatoria. | Las validaciones forman parte de la misma funcionalidad. |
| Verificable | Sí, porque se puede comprobar que una postulación válida queda registrada y que se rechazan postulaciones que no cumplen los requisitos. | Los criterios de aceptación permiten realizar pruebas. |

---

## HU-06 — Visualizar postulantes

| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero visualizar la lista de postulantes para evaluar los perfiles recibidos. |
| Módulo | |
| Requisitos relacionados | RF-17 |

### Criterios de aceptación

1. La empresa debe estar autenticada.
2. Debe seleccionar una convocatoria propia.
3. El sistema debe mostrar sus postulantes.
4. La empresa debe poder consultar la información correspondiente.
5. La empresa debe poder consultar el CV del postulante.
6. No debe poder consultar postulantes de convocatorias pertenecientes a otra empresa.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí, porque puede desarrollarse como una funcionalidad específica para consultar los postulantes de una convocatoria. | Requiere que la empresa esté autenticada. |
| Negociable | Sí, porque la forma de presentar la lista y los datos de los postulantes puede acordarse durante el desarrollo. | La información que debe consultarse puede mantenerse definida. |
| Valiosa | Sí, porque permite a la empresa conocer los perfiles de las personas que se postularon a sus convocatorias. | Es necesaria para continuar con el proceso de selección. |
| Estimable | Sí, porque el alcance está definido en consultar la lista de postulantes y su información asociada. | Las tareas pueden identificarse y estimarse. |
| Pequeña | Sí, porque se concentra en visualizar los postulantes de una convocatoria. | No incluye la realización de entrevistas. |
| Verificable | Sí, porque se puede comprobar que la empresa visualiza los postulantes correspondientes a sus propias convocatorias. | También se puede verificar que no acceda a postulantes de otras empresas. |

---

## HU-07 — Programar entrevistas

| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero programar entrevistas para organizar las reuniones con los candidatos. |
| Módulo | Entrevista |
| Requisitos relacionados | RF-21 |

### Criterios de aceptación

1. Debe existir una postulación.
2. La empresa debe seleccionar un postulante.
3. Debe indicar fecha y hora.
4. Debe indicar la modalidad cuando corresponda.
5. El sistema debe registrar la entrevista.
6. La entrevista debe quedar asociada a la postulación.
7. El usuario debe poder consultar la entrevista.


### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí, porque puede desarrollarse como una funcionalidad específica para registrar entrevistas de los postulantes. | Requiere que exista una postulación previa. |
| Negociable | Sí, porque la modalidad y la forma de mostrar los datos de la entrevista pueden acordarse durante el desarrollo. | El objetivo de programar la entrevista permanece. |
| Valiosa | Sí, porque permite a la empresa organizar las entrevistas con los postulantes seleccionados. | Facilita la coordinación del proceso de selección. |
| Estimable | Sí, porque los datos necesarios para programar una entrevista están definidos: postulante, fecha, hora y modalidad. | El alcance permite estimar las tareas. |
| Pequeña | Sí, porque se centra en programar y registrar una entrevista. | No incluye registrar el resultado de la entrevista. |
| Verificable | Sí, porque se puede comprobar que la entrevista queda registrada correctamente y asociada a la postulación correspondiente. | Los criterios permiten verificar el resultado. |

---

## HU-08 — Recibir información de entrevista

| Campo | Detalle |
|-------|---------|
| Historia | Como usuario, quiero recibir información de las entrevistas para conocer la fecha y horario asignados. |
| Módulo | Convocatorias |
| Requisitos relacionados | RF-22 |

### Criterios de aceptación

1. El sistema debe mostrar las convocatorias vigentes.
2. Las convocatorias vencidas no deben aparecer.
3. El usuario debe poder consultar los datos de cada convocatoria.
4. El usuario debe poder seleccionar una convocatoria para consultar su información completa.


### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí, porque puede desarrollarse como una funcionalidad específica para que el usuario consulte sus entrevistas asignadas. | Requiere que exista una entrevista registrada. |
| Negociable | Sí, porque la forma de mostrar la fecha, hora, modalidad y convocatoria puede acordarse durante el desarrollo. | El objetivo de informar la entrevista no cambia. |
| Valiosa | Sí, porque permite al usuario conocer la fecha, hora y modalidad de la entrevista asignada. | Ayuda al postulante a conocer la información necesaria para participar. |
| Estimable | Sí, porque el alcance se limita a consultar y mostrar la información de las entrevistas asignadas. | Las tareas necesarias están definidas. |
| Pequeña | Sí, porque se centra únicamente en visualizar las entrevistas asignadas al usuario. | No incluye programar ni modificar entrevistas. |
| Verificable | Sí, porque se puede comprobar que el usuario visualiza correctamente la fecha, hora y modalidad de su entrevista. | La información mostrada puede compararse con los datos registrados. |

---

## HU-09 — Registrar resultado de entrevista

| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero registrar el resultado de cada entrevista para realizar el seguimiento del proceso. |
| Módulo | Entrevistas |
| Requisitos relacionados | RF-17 |

### Criterios de aceptación

1. Debe existir una entrevista registrada.
2. La empresa debe poder ingresar el resultado.
3. El sistema debe guardar el resultado.
4. El resultado debe quedar asociado a la entrevista.
5. El estado de la postulación debe actualizarse cuando corresponda.
6. El usuario debe poder consultar el resultado cuando sea habilitado.


### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente	| Sí, porque puede desarrollarse como una funcionalidad específica para registrar el resultado de una entrevista existente. | Requiere que previamente exista una entrevista. |
| Negociable | Sí, porque el tipo de resultado y la forma de registrarlo pueden acordarse durante el desarrollo. | El objetivo de registrar el resultado permanece. |
| Valiosa |	Sí, porque permite a la empresa dejar registrado el resultado de las entrevistas y realizar el seguimiento del proceso de selección. | Aporta información para el seguimiento de las postulaciones. |
| Estimable	| Sí, porque se concentra en registrar el resultado de una entrevista. | No incluye la realización de la entrevista. |
| Pequeña |	Sí | Se centra en registrar el resultado de una entrevista. |
| Verificable | Sí, porque se puede comprobar que el resultado se guarda correctamente y queda asociado a la entrevista correspondiente. | Se puede verificar la información almacenada. |

---

## HU-10 — Administrador gestiona usuarios y permisos

| Campo | Detalle |
|-------|---------|
| Historia | Como administrador, quiero gestionar usuarios y permisos para garantizar la seguridad del sistema. |
| Módulo | Usuario |
| Requisitos relacionados | RF-04, RF-05, RF-08 |

### Criterios de aceptación

1. El administrador debe haber iniciado sesión.
2. El sistema debe permitir consultar los usuarios registrados.
3. El administrador debe poder gestionar los roles o permisos correspondientes.
4. Los permisos deben aplicarse de acuerdo con el rol asignado.
5. Los usuarios sin permisos administrativos no deben poder acceder a las funciones de administración.
6. Los cambios realizados deben quedar registrados correctamente.
7. El sistema debe informar si la gestión de usuarios se realizó correctamente.


### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |	Sí, porque puede desarrollarse como una funcionalidad de administración independiente de las funciones del postulante y de la empresa. | Requiere autenticación administrativa. |
| Negociable | Sí, porque la forma de consultar usuarios y modificar permisos puede acordarse durante el desarrollo. | Los permisos principales pueden mantenerse definidos. |
| Valiosa |	Sí, porque permite al administrador controlar los usuarios y sus permisos dentro del sistema. | Contribuye a la correcta administración del sistema. |
| Estimable |	Sí, porque el alcance está definido en consultar usuarios y gestionar sus permisos. | Las tareas necesarias pueden identificarse y estimarse. |
| Pequeña	| Sí, porque se concentra en la gestión de usuarios y permisos. | No incluye la generación de reportes. |
| Verificable |	Sí, porque se puede comprobar que los cambios de permisos se guardan correctamente y que cada usuario tiene el acceso correspondiente. | Los resultados pueden comprobarse mediante pruebas. |

---

## HU-11 — Administrador genera reportes

| Campo | Detalle |
|-------|---------|
| Historia | Como administrador, quiero generar reportes de convocatorias y entrevistas para analizar los resultados del proceso de selección. |
| Módulo | Usuario |
| Requisitos relacionados | RF-23 |

### Criterios de aceptación

1. El administrador debe haber iniciado sesión.
2. El sistema debe permitir seleccionar el tipo de información que se desea consultar.
3. El administrador debe poder aplicar filtros según la información seleccionada.
4. El sistema debe mostrar los datos correspondientes a los registros existentes.
5. La información mostrada en el reporte debe coincidir con los datos almacenados en el sistema.
6. El sistema debe permitir consultar el reporte generado.
7. Si no existen datos para los filtros seleccionados, el sistema debe informar dicha situación.


### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |	Sí, porque puede desarrollarse como una funcionalidad específica para generar reportes a partir de la información existente. | Requiere que existan datos registrados. |
| Negociable | Sí, porque los tipos de reportes, filtros y forma de presentación pueden acordarse durante el desarrollo. | El objetivo de generar información para el administrador permanece. |
| Valiosa |	Sí, porque permite al administrador consultar y analizar información registrada sobre las convocatorias y entrevistas. | Facilita el seguimiento de la información del sistema. |
| Estimable |	Sí, porque el alcance está definido en seleccionar información, aplicar filtros y generar el reporte. | Las tareas pueden identificarse y estimarse. |
| Pequeña |	Sí, porque se centra en generar reportes a partir de la información disponible. | Los filtros forman parte de la generación del reporte. |
| Verificable	| Sí, porque se puede comprobar que el reporte muestra la información correspondiente a los filtros seleccionados. | Los datos del reporte pueden compararse con los registros del sistema. |

---

## HU-12 — Usuario consulta estado de su postulación

| Campo | Detalle |
|-------|---------|
| Historia | Como usuario, quiero consultar el estado de mi postulación para conocer el avance de mi proceso. |
| Módulo | Convocatorias |
| Requisitos relacionados | RF-18, RF-21 |

### Criterios de aceptación

1. El usuario debe haber iniciado sesión.
2. El sistema debe mostrar únicamente las postulaciones realizadas por el usuario.
3. El usuario debe poder consultar las convocatorias a las que se postuló.
4. El sistema debe mostrar el estado actual de cada postulación.
5. Si existe una entrevista asociada, el sistema debe mostrar su información correspondiente.
6. Si existe un resultado registrado, el sistema debe permitir consultarlo cuando se encuentre habilitado.
7. La información mostrada debe corresponder a los datos registrados en el sistema.


### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente	| Sí, porque puede desarrollarse como una funcionalidad específica para consultar el estado de las postulaciones del usuario. | Requiere que el usuario tenga postulaciones registradas. |
| Negociable | Sí, porque la forma de mostrar el estado, la entrevista y el resultado puede acordarse durante el desarrollo. | Evita que el usuario tenga que consultar el estado por otros medios. |
| Valiosa	| Sí, porque permite al usuario conocer el avance de sus procesos de selección. | Permite al usuario conocer el avance de su proceso de selección. |
| Estimable |	Sí, porque el alcance está definido en consultar las postulaciones y mostrar su estado actual. | No incluye modificar la postulación. |
| Pequeña |	Sí, porque se concentra en consultar el estado de las postulaciones del usuario. | Se centra en visualizar la información relacionada con las postulaciones del usuario. |
| Verificable |	Sí, porque se puede comprobar que el sistema muestra correctamente el estado correspondiente a cada postulación del usuario. | La información mostrada puede compararse con el estado registrado. |
