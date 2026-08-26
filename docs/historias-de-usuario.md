# Historias de usuario

_Presentar al menos una historia de usuario representativa por módulo._
_Cada historia debe incluir formato clásico, criterios de aceptación y validación INVEST._

---

## HU-01 — Empresa crea convocatoria laboral

| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero crear una convocatoria laboral para publicar nuevas búsquedas de personal. |
| Módulo | Inicio |
| Requisitos relacionados | RF-01, RF-02, RF-24 |

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
| Independiente | | |
| Negociable | | |
| Valiosa | | |
| Estimable | | |
| Pequeña | | |
| Verificable | | |


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
| Independiente | | |
| Negociable | | |
| Valiosa | | |
| Estimable | | |
| Pequeña | | |
| Verificable | | |

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
| Independiente | | |
| Negociable | | |
| Valiosa | | |
| Estimable | | |
| Pequeña | | |
| Verificable | | |


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
| Independiente | | |
| Negociable | | |
| Valiosa | | |
| Estimable | | |
| Pequeña | | |
| Verificable | | |


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
| Independiente | | |
| Negociable | | |
| Valiosa | | |
| Estimable | | |
| Pequeña | | |
| Verificable | | |

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
| Independiente | | |
| Negociable | | |
| Valiosa | | |
| Estimable | | |
| Pequeña | | |
| Verificable | | |

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
| Independiente | | |
| Negociable | | |
| Valiosa | | |
| Estimable | | |
| Pequeña | | |
| Verificable | | |

---

## HU-09 — Crear convocatorias

| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero crear una convocatoria para publicar una nueva búsqueda. |
| Módulo |Convocatoria|
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
| Independiente | | |
| Negociable | | |
| Valiosa | | |
| Estimable | | |
| Pequeña | | |
| Verificable | | |

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
| Independiente | | |
| Negociable | | |
| Valiosa | | |
| Estimable | | |
| Pequeña | | |
| Verificable | | |

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
| Independiente | | |
| Negociable | | |
| Valiosa | | |
| Estimable | | |
| Pequeña | | |
| Verificable | | |

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
| Independiente | | |
| Negociable | | |
| Valiosa | | |
| Estimable | | |
| Pequeña | | |
| Verificable | | |

---
