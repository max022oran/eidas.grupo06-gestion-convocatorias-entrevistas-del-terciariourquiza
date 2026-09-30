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
| Independiente | Sí | Porque puede desarrollarse como una funcionalidad independiente para la creación de convocatorias. |
| Negociable | Sí | Porque los campos y detalles de la convocatoria pueden acordarse y modificarse durante el desarrollo. |
| Valiosa | Sí | Porque permite a la empresa publicar nuevas oportunidades laborales para recibir postulaciones. |
| Estimable | Sí | Porque tiene un alcance concreto y permite estimar las tareas necesarias para crear una convocatoria. |
| Pequeña | Sí | Porque se concentra únicamente en crear y registrar una convocatoria. |
| Verificable | Sí | Porque los criterios de aceptación permiten comprobar que la convocatoria se crea y registra correctamente. |

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
| Independiente | Sí | Porque puede desarrollarse como una funcionalidad específica para modificar o cerrar convocatorias existentes. |
| Negociable | Sí | Porque la forma de editar los datos y las condiciones para cerrar una convocatoria pueden acordarse durante el desarrollo. |
| Valiosa | Sí | Porque permite a la empresa mantener actualizada la información de sus convocatorias y controlar cuándo dejan de aceptar postulaciones. |
| Estimable | Sí | Porque las tareas necesarias para modificar y cerrar una convocatoria tienen un alcance definido. |
| Pequeña | No | Porque incluye dos acciones diferentes: editar una convocatoria y cerrarla. |
| Verificable | Sí | Porque se puede comprobar que los datos se modifican correctamente y que una convocatoria cerrada no acepta nuevas postulaciones.

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
| Independiente | Sí | Porque el registro de usuario puede desarrollarse como una funcionalidad específica del sistema. |
| Negociable | Sí | Porque los campos del formulario y la forma de validar los datos pueden acordarse durante el desarrollo. |
| Valiosa | Sí | Porque permite al usuario crear una cuenta para acceder al sistema y participar en las convocatorias. |
| Estimable | Sí | Porque tiene un alcance definido relacionado con completar, validar y guardar los datos del usuario. |
| Pequeña | Sí | Porque se concentra en una única funcionalidad: registrar un usuario. |
| Verificable | Sí | Porque se puede comprobar que un usuario válido se registra y que los datos incorrectos son rechazados. |

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
| Independiente | Sí | Porque la carga del CV puede desarrollarse como una funcionalidad específica asociada al usuario. |
| Negociable | Sí | Porque la forma de seleccionar, validar y mostrar el archivo puede acordarse durante el desarrollo. |
| Valiosa | Sí | Porque permite al usuario disponer de su CV para utilizarlo en sus postulaciones. |
| Estimable | Sí | Porque el alcance se limita a seleccionar, validar, almacenar y asociar el CV al usuario. |
| Pequeña | Sí | Porque se centra en cargar y almacenar el CV del usuario. |
| Verificable | Sí | Porque se puede comprobar que un archivo válido se almacena correctamente y queda asociado al usuario. |

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
| Independiente | Sí | Porque la postulación puede implementarse como una funcionalidad específica una vez disponibles los datos del usuario y la convocatoria. |
| Negociable | Sí | Porque la forma de confirmar la postulación y mostrar la información puede acordarse durante el desarrollo. |
| Valiosa | Sí | Porque permite al usuario participar en los procesos de selección publicados mediante el sistema. |
| Estimable | Sí | Porque tiene un alcance definido: validar las condiciones y registrar la postulación. |
| Pequeña | Sí | Porque se concentra en realizar una postulación a una convocatoria. |
| Verificable | Sí | Porque se puede comprobar que una postulación válida queda registrada y que se rechazan postulaciones que no cumplen los requisitos. |

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
| Independiente | Sí | Porque puede desarrollarse como una funcionalidad específica para consultar los postulantes de una convocatoria. |
| Negociable | Sí | Porque la forma de presentar la lista y los datos de los postulantes puede acordarse durante el desarrollo. |
| Valiosa | Sí | Porque permite a la empresa conocer los perfiles de las personas que se postularon a sus convocatorias. |
| Estimable | Sí | Porque el alcance está definido en consultar la lista de postulantes y su información asociada. |
| Pequeña | Sí | Porque se concentra en visualizar los postulantes de una convocatoria. |
| Verificable | Sí | Porque se puede comprobar que la empresa visualiza los postulantes correspondientes a sus propias convocatorias. |

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
| Independiente | Sí | Porque puede desarrollarse como una funcionalidad específica para registrar entrevistas de los postulantes. |
| Negociable | Sí | Porque la modalidad y la forma de mostrar los datos de la entrevista pueden acordarse durante el desarrollo. |
| Valiosa | Sí | Porque permite a la empresa organizar las entrevistas con los postulantes seleccionados. |
| Estimable | Sí | Porque los datos necesarios para programar una entrevista están definidos: postulante, fecha, hora y modalidad. |
| Pequeña | Sí | Porque se centra en programar y registrar una entrevista. |
| Verificable | Sí | Porque se puede comprobar que la entrevista queda registrada correctamente y asociada a la postulación correspondiente. |

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
| Independiente | Sí | Porque puede desarrollarse como una funcionalidad específica para que el usuario consulte sus entrevistas asignadas. |
| Negociable | Sí | Porque la forma de mostrar la fecha, hora, modalidad y convocatoria puede acordarse durante el desarrollo. |
| Valiosa | Sí | Porque permite al usuario conocer la fecha, hora y modalidad de la entrevista asignada. |
| Estimable | Sí | Porque el alcance se limita a consultar y mostrar la información de las entrevistas asignadas. |
| Pequeña | Sí | Porque se centra únicamente en visualizar las entrevistas asignadas al usuario. |
| Verificable | Sí | Porque se puede comprobar que el usuario visualiza correctamente la fecha, hora y modalidad de su entrevista. |

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
| Independiente	| Sí | Porque puede desarrollarse como una funcionalidad específica para registrar el resultado de una entrevista existente. |
| Negociable | Sí | Porque el tipo de resultado y la forma de registrarlo pueden acordarse durante el desarrollo. |
| Valiosa |	Sí | Porque permite a la empresa dejar registrado el resultado de las entrevistas y realizar el seguimiento del proceso de selección. |
| Estimable	| Sí | Porque se concentra en registrar el resultado de una entrevista. |
| Pequeña |	Sí | Porque se centra en registrar el resultado de una entrevista. |
| Verificable | Sí | Porque se puede comprobar que el resultado se guarda correctamente y queda asociado a la entrevista correspondiente. |

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
| Independiente |	Sí | Porque puede desarrollarse como una funcionalidad de administración independiente de las funciones del postulante y de la empresa. |
| Negociable | Sí | Porque la forma de consultar usuarios y modificar permisos puede acordarse durante el desarrollo. |
| Valiosa |	Sí | Porque permite al administrador controlar los usuarios y sus permisos dentro del sistema. |
| Estimable |	Sí | Porque el alcance está definido en consultar usuarios y gestionar sus permisos. |
| Pequeña	| Sí | Porque se concentra en la gestión de usuarios y permisos. |
| Verificable |	Sí | Porque se puede comprobar que los cambios de permisos se guardan correctamente y que cada usuario tiene el acceso correspondiente. |

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
| Independiente |	Sí | Porque puede desarrollarse como una funcionalidad específica para generar reportes a partir de la información existente. |
| Negociable | Sí | Porque los tipos de reportes, filtros y forma de presentación pueden acordarse durante el desarrollo. |
| Valiosa |	Sí | Porque permite al administrador consultar y analizar información registrada sobre las convocatorias y entrevistas. |
| Estimable |	Sí | Porque el alcance está definido en seleccionar información, aplicar filtros y generar el reporte. |
| Pequeña |	Sí | Porque se centra en generar reportes a partir de la información disponible. |
| Verificable	| Sí | Porque se puede comprobar que el reporte muestra la información correspondiente a los filtros seleccionados. |

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
| Independiente	| Sí | Porque puede desarrollarse como una funcionalidad específica para consultar el estado de las postulaciones del usuario. |
| Negociable | Sí | Porque la forma de mostrar el estado, la entrevista y el resultado puede acordarse durante el desarrollo. |
| Valiosa	| Sí | Porque permite al usuario conocer el avance de sus procesos de selección. |
| Estimable |	Sí | Porque el alcance está definido en consultar las postulaciones y mostrar su estado actual. |
| Pequeña |	Sí | Porque se concentra en consultar el estado de las postulaciones del usuario. |
| Verificable |	Sí | Porque se puede comprobar que el sistema muestra correctamente el estado correspondiente a cada postulación del usuario. |
