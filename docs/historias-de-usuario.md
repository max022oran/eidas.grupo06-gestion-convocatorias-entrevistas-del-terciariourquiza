# Historias de usuario

_Presentar al menos una historia de usuario representativa por módulo._
_Cada historia debe incluir formato clásico, criterios de aceptación y validación INVEST._

---

## HU-01 — Empresa crea convocatoria laboral

| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero crear una convocatoria laboral para publicar nuevas búsquedas de personal. |
| Módulo | Inicio |
| Requisitos relacionados | RF-, RF-, RF- |

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
| Requisitos relacionados | RF-, RF-, RF- |

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
| Requisitos relacionados | RF-XX, RF-XX |

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
| Requisitos relacionados | RF-XX, RF-XX |

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
| Requisitos relacionados | RF-XX, RF-XX |

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
| Requisitos relacionados | RF-XX, RF-XX |

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
| Requisitos relacionados | RF-00, RF-01 |

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
| Requisitos relacionados | RF-00, RF-01 |

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

## HU-09 — Crear convocatorias

| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero crear una convocatoria para publicar una nueva búsqueda. |
| Módulo | Convocatoria |
| Requisitos relacionados | RF-00, RF-01 |

### Criterios de aceptación

1. La empresa debe estar autenticada.
2. Debe completar los campos obligatorios.
3. La fecha de vencimiento debe ser posterior a la fecha de publicación.
4. El sistema debe validar la información.
5. La convocatoria debe quedar registrada.
6. Si se encuentra vigente, debe aparecer entre las convocatorias disponibles.


### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí | Puede desarrollarse como una funcionalidad independiente |
| Negociable | Sí | Los datos y condiciones de la convocatoria pueden acordarse |
| Valiosa | Sí | Permite a la empresa publicar nuevas búsquedas laborales. |
| Estimable | Sí | El alcance está definido y permite estimar las tareas. |
| Pequeña | Sí | Se concentra exclusivamente en crear una convocatoria. |
| Verificable | Sí | Los criterios de aceptación permiten comprobar su funcionamiento. |

---

## HU-10 — Editar convocatoria
| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero editar una convocatoria para mantener actualizada la información publicada. |
| Módulo | Convocatorias |
| Requisitos relacionados | RF-00, RF-01 |

### Criterios de aceptación

1. La empresa debe estar autenticada.
2. Solo puede modificar convocatorias pertenecientes a ella.
3. El sistema debe permitir modificar los campos habilitados.
4. Los datos deben ser validados.
5. Los cambios deben quedar guardados correctamente.


### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí | Puede implementarse independientemente de la creación de nuevas convocatorias. |
| Negociable | Sí | Los campos que podrán modificarse pueden definirse durante el desarrollo. |
| Valiosa | Sí | Permite mantener actualizada la información de las búsquedas. |
| Estimable | Sí | El alcance y las tareas necesarias están definidos. |
| Pequeña | Sí | Se limita a modificar una convocatoria existente. |
| Verificable | Sí | Se puede comprobar que los cambios se validan y guardan correctamente. |

---

## HU-11 —  Cerrar convocatoria

| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero cerrar una convocatoria para impedir nuevas postulaciones cuando la búsqueda haya finalizado. |
| Módulo | Convocatorias |
| Requisitos relacionados | RF-00, RF-01 |

### Criterios de aceptación

1. La empresa debe estar autenticada.
2. Debe seleccionar una convocatoria propia.
3. El sistema debe solicitar confirmación.
4. Al confirmar, la convocatoria debe cambiar a estado cerrada.
5. Una convocatoria cerrada no debe permitir nuevas postulaciones.


### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí | Puede implementarse como una funcionalidad separada de la edición. |
| Negociable | Sí | La forma de confirmación y las condiciones de cierre pueden acordarse. |
| Valiosa | Sí | Permite impedir postulaciones cuando una búsqueda ya finalizó. |
| Estimable | Sí | El alcance es concreto y permite estimar el trabajo. |
| Pequeña | Sí | Se concentra en una única acción: cerrar una convocatoria. |
| Verificable | Sí | Se puede comprobar que cambia el estado y que ya no acepta postulaciones. |

---

## HU-12 — Ver postulantes
| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero visualizar los postulantes de una convocatoria para evaluar los perfiles recibidos. |
| Módulo | Convocatorias |
| Requisitos relacionados | RF-00, RF-01 |

### Criterios de aceptación

1. La empresa debe estar autenticada.
2. Debe seleccionar una convocatoria propia.
3. El sistema debe mostrar los postulantes correspondientes.
4. La empresa debe poder consultar los datos necesarios para evaluar el perfil.
5. La empresa debe poder consultar el CV del postulante.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí | Puede desarrollarse como una funcionalidad independiente para la empresa. |
| Negociable | Sí | Se puede acordar qué información del postulante será visible. |
| Valiosa | Sí | Permite a la empresa analizar los perfiles que se postularon. |
| Estimable | Sí | El alcance está definido y las tareas son identificables. |
| Pequeña | Sí | Se limita a consultar los postulantes de una convocatoria. |
| Verificable | Sí | Los criterios permiten comprobar que se muestran los postulantes correctos y sus CV. |

---
