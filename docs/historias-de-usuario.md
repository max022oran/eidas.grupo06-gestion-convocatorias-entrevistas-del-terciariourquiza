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
| Independiente | Sí | Puede desarrollarse sin depender directamente de otras historias, aunque requiere autenticación de la empresa. |
| Negociable | Sí | Los detalles de la convocatoria pueden acordarse y modificarse durante el desarrollo. |
| Valiosa | Sí | Permite a la empresa publicar nuevas búsquedas laborales. |
| Estimable | Sí | Tiene un alcance concreto y se pueden estimar las tareas necesarias. |
| Pequeña | Sí | Se centra únicamente en crear y publicar una convocatoria. |
| Verificable | Sí | Los criterios de aceptación permiten comprobar si la convocatoria se crea correctamente. |

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
| Independiente | Sí | Puede implementarse de forma separada de otras funcionalidades.5 |
| Negociable | Sí | Los campos editables y las condiciones de cierre pueden definirse durante el desarrollo. |
| Valiosa | Sí | Permite mantener actualizada la información y controlar el estado de las convocatorias. |
| Estimable | Sí | Las tareas necesarias para editar y cerrar una convocatoria son identificables. |
| Pequeña | No | Incluye dos funcionalidades distintas: editar y cerrar una convocatoria. |
| Verificable | Sí | Los criterios permiten comprobar que la edición y el cierre funcionan correctamente. |

---

## HU-03 — Registrarme

| Campo | Detalle |
|-------|---------|
| Historia |Como usuario, quiero registrarme en el sistema para poder postularme a diferentes convocatorias.|
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
| Independiente | Sí | El registro puede desarrollarse independientemente de las funcionalidades posteriores. |
| Negociable | Sí | Los datos requeridos y las reglas de validación pueden definirse durante el desarrollo. |
| Valiosa | Sí | Permite al usuario acceder al sistema y utilizar las funcionalidades destinadas a postulantes. |
| Estimable | Sí | El alcance está claramente definido y permite estimar el trabajo. |
| Pequeña | Sí | Se limita al proceso de registro del usuario. |
| Verificable | Sí | Los criterios permiten comprobar el registro correcto y los casos de error. |

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
| Independiente | Sí | Puede implementarse una vez disponible la autenticación, sin depender de las postulaciones. |
| Negociable | Sí | Se pueden acordar formatos, tamaño máximo y otras condiciones del archivo. |
| Valiosa | Sí | Permite que el usuario tenga su CV disponible para participar en búsquedas laborales. |
| Estimable | Sí | El alcance de carga y asociación del CV está definido. |
| Pequeña | Sí | Se concentra en cargar y guardar el CV del usuario. |
| Verificable | Sí | Se puede comprobar el formato, almacenamiento, asociación y confirmación de carga. |


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
| Independiente | Sí | Aunque requiere usuario registrado y CV, la funcionalidad de postulación puede desarrollarse como una historia independiente. |
| Negociable | Sí | Las condiciones y datos de la postulación pueden ajustarse según las necesidades del sistema. |
| Valiosa | Sí | Permite al usuario participar efectivamente en los procesos de selección. |
| Estimable | Sí | Las tareas necesarias para registrar y validar una postulación son identificables. |
| Pequeña | Sí | Se enfoca en una única acción principal: realizar una postulación. |
| Verificable | Sí | Los criterios permiten comprobar que la postulación se registra correctamente y no se duplica. |


----

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
| Independiente | Sí | Puede desarrollarse como una funcionalidad independiente para la empresa. |
| Negociable | Sí | La forma de mostrar la información y los datos visibles puede acordarse. |
| Valiosa | Sí | Permite a la empresa consultar y evaluar los perfiles recibidos. |
| Estimable | Sí | El alcance está definido: listar postulantes y consultar su información y CV. |
| Pequeña | Sí | Se concentra en la consulta de postulantes de una convocatoria. |
| Verificable | Sí | Se puede comprobar que solo se muestran postulantes de convocatorias propias. |

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
| Independiente | Sí | Puede desarrollarse como una funcionalidad específica dentro del proceso de selección. |
| Negociable | Sí | Los datos de la entrevista y las modalidades pueden definirse según las necesidades. |
| Valiosa | Sí | Permite organizar las entrevistas con los candidatos seleccionados. |
| Estimable | Sí | Las tareas necesarias para registrar una entrevista están claramente delimitadas. |
| Pequeña | Sí | Se centra en programar una entrevista para un postulante. |
| Verificable | Sí | Los criterios permiten comprobar que la entrevista queda registrada y asociada correctamente. |

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
| Independiente | Sí | Puede desarrollarse como consulta de las entrevistas asignadas al usuario. |
| Negociable | Sí | La forma de mostrar la información puede acordarse. |
| Valiosa | Sí | Permite al usuario conocer cuándo y cómo debe realizar la entrevista. |
| Estimable | Sí | El alcance se limita a consultar la información de las entrevistas. |
| Pequeña | Sí | Se centra en visualizar las entrevistas asignadas. |
| Verificable | Sí | Se puede comprobar que el usuario visualiza correctamente fecha, hora y modalidad. |

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
| Independiente	| Sí | Puede desarrollarse independientemente de otras funcionalidades de gestión de entrevistas. |
| Negociable | Sí | La forma de registrar y mostrar el resultado puede acordarse. |
| Valiosa |	Sí | Permite a la empresa realizar el seguimiento del proceso de selección. |
| Estimable	| Sí | El alcance se limita al registro y actualización del resultado de la entrevista. |
| Pequeña |	Sí | Se centra en registrar el resultado de una entrevista. |
| Verificable | Sí	| Se puede comprobar que el resultado queda correctamente registrado y asociado a la entrevista. |

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
| Independiente |	Sí | Puede desarrollarse como una funcionalidad de administración de usuarios y permisos. |
| Negociable | Sí |	La forma de gestionar los roles y permisos puede acordarse. |
| Valiosa |	Sí | Permite controlar el acceso a las diferentes funcionalidades del sistema. |
| Estimable |	Sí | El alcance se limita a la gestión de usuarios, roles y permisos. |
| Pequeña	| Sí | Se concentra en las funciones administrativas relacionadas con usuarios. |
| Verificable |	Sí | Se puede comprobar que los permisos se asignan correctamente y que las restricciones se cumplen. |

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
| Independiente |	Sí | Puede desarrollarse como una funcionalidad de consulta y generación de reportes. |
| Negociable | Sí |	Los tipos de reportes y filtros pueden acordarse durante el desarrollo. |
| Valiosa |	Sí | Permite al administrador analizar la información de convocatorias y entrevistas. |
| Estimable |	Sí | El alcance se limita a la generación y consulta de reportes. |
| Pequeña |	Sí | Se concentra en generar reportes a partir de información existente. |
| Verificable	| Sí | Se puede comprobar que los reportes muestran correctamente la información almacenada. |

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
| Independiente	| Sí | Puede desarrollarse como una consulta del estado de las postulaciones del usuario. |
| Negociable | Sí	| La forma de mostrar los estados y resultados puede acordarse. |
| Valiosa	| Sí | Permite al usuario conocer el avance de su proceso de selección. |
| Estimable |	Sí | El alcance se limita a consultar el estado, entrevistas y resultados de sus postulaciones. |
| Pequeña |	Sí | Se centra en visualizar la información relacionada con las postulaciones del usuario. |
| Verificable |	Sí | Se puede comprobar que el usuario visualiza correctamente el estado y la información correspondiente a sus postulaciones. |
