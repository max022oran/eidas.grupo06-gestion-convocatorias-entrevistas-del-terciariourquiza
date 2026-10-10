# Diseño UI

_Presentar al menos un wireframe por pantalla o módulo relevante._
_Los wireframes en imagen o PDF van en `diagramas/wireframes/`; acá se documenta la justificación de cada uno._

---

## Pantalla / Módulo 1 — Inicio

**Wireframe:** <img width="1083" height="465" alt="image" src="https://github.com/user-attachments/assets/139271d3-f143-42c4-a256-e9fc5656e351" />

**Patrones de diseño utilizados:** Dashboard, tarjetas de métricas, menú lateral y listado de actividad reciente.

**Justificación:** 

**Formulario (si aplica):**
- Cantidad de campos: No aplica.
- Flujo: Navegación desde la pantalla inicial hacia los módulos disponibles.
- Validaciones relevantes: Verificar que el usuario haya iniciado sesión y que tenga permisos para acceder a las funcionalidades seleccionadas.

---

## Pantalla / Módulo 2 — Usuarios

**Wireframe:** <img width="1088" height="498" alt="image" src="https://github.com/user-attachments/assets/1c556baf-3c31-4aa9-bd2c-36c782887ff0" />

**Patrones de diseño utilizados:** Tabla de datos, búsqueda/listado y acciones mediante botones.

**Justificación:**  
Se utiliza una tabla para organizar la información de los usuarios y facilitar la consulta de sus datos. Las acciones de editar y eliminar se presentan junto a cada registro para permitir la administración directa de las cuentas. Este patrón resulta adecuado para el Administrador porque permite consultar varios usuarios en una misma pantalla y gestionar sus roles.

El diseño también contempla la separación de roles del sistema: Administrador, Asistente y Empresa. Además, la interfaz debe validar que los usuarios utilicen correos institucionales autorizados.

**Formulario (si aplica):**
- Cantidad de campos: Los campos dependen de la operación de alta o modificación del usuario.
- Flujo (todo en una pantalla / por pasos): Todo en una pantalla mediante alta o modificación.
- Validaciones relevantes:
  - Validar el correo institucional.
  - Validar el rol asignado.
  - Solo los usuarios con permisos administrativos pueden gestionar cuentas.
  - No permitir accesos a funciones que correspondan a otro rol.

---

## Pantalla / Módulo 3 — Programas

**Wireframe:** Pendiente
**Patrones de diseño utilizados:** Pendiente

**Justificación:** Pendiente

**Formulario (si aplica):** Pendiente

---

## Pantalla / Módulo 4 — Convocatorias

**Wireframe:** <img width="1075" height="672" alt="image" src="https://github.com/user-attachments/assets/80853e65-9956-4cdb-b8ed-6828dd024e01" />

**Patrones de diseño utilizados:** Tabla de datos, formulario de alta, tarjetas de convocatorias y botones de acción.

**Justificación:**  
La tabla permite que la empresa consulte y administre sus convocatorias, identificando información como el puesto, la ubicación y el período de vigencia. El formulario de alta organiza los datos necesarios para publicar una búsqueda laboral y facilita la validación antes de guardar.
En el portal del postulante se utiliza el patrón Card para presentar las convocatorias de manera individual, con información relevante y un botón de acción para iniciar la postulación. Esta presentación permite comparar las oportunidades disponibles y acceder a sus detalles sin sobrecargar la pantalla.

**Formulario (si aplica):**
- Cantidad de campos: En el formulario de alta se identifican los campos de título o puesto, modalidad, fecha de inicio y fecha de fin. La cantidad definitiva deberá coincidir con el formulario completo implementado.
- Flujo: Alta y edición en una pantalla.
- Validaciones relevantes:
  - Los campos obligatorios deben estar completos.
  - La fecha de finalización debe ser posterior a la fecha de inicio.
  - La empresa solamente debe poder modificar sus propias convocatorias.
  - No se deben aceptar nuevas postulaciones a convocatorias cerradas, según el requisito correspondiente.

---

## Pantalla / Módulo 5 — Carreras

**Wireframe:**

**Patrones de diseño utilizados:**

**Justificación:**  

**Formulario (si aplica):**

---

## Pantalla / Módulo 6 — Docentes y Egresados

**Wireframe:** <img width="1075" height="312" alt="image" src="https://github.com/user-attachments/assets/9ff14dbc-b1ba-494b-ba88-9b3421c3b799" />

**Patrones de diseño utilizados:** Tabla de datos, buscador y acciones sobre registros.

**Justificación:**
La tabla permite consultar los datos de docentes y egresados de manera organizada. El buscador facilita localizar un registro por nombre o DNI, mientras que la información del CV permite identificar si el usuario tiene un currículum asociado a su cuenta.
Este diseño facilita las tareas de consulta y administración del padrón sin necesidad de abrir cada registro individualmente. El acceso a los datos y a los archivos adjuntos debe limitarse a los usuarios autorizados.

**Formulario (si aplica):**
- Cantidad de campos: No aplica para la consulta del padrón. El formulario de alta o modificación deberá definirse según los campos establecidos para esos procesos.
- Flujo: Consulta y búsqueda en una pantalla.
- Validaciones relevantes:
  - Validar los campos obligatorios al registrar o modificar información.
  - Verificar que el CV adjunto corresponda al usuario correcto.
  - Restringir el acceso a los datos personales y documentos según los permisos definidos.

---

## Pantalla / Módulo 7 — Entrevistas

**Wireframe:** <img width="1062" height="262" alt="image" src="https://github.com/user-attachments/assets/06d10027-f4b4-4c86-a2f5-723c5872f00d" />

**Patrones de diseño utilizados:** Tabla de evaluación, acciones por registro y formulario de carga de resultados.

**Justificación:**  
La tabla permite a la empresa consultar y evaluar a los postulantes de sus convocatorias. La información se organiza mediante datos del postulante, puesto, puntaje y resultado, facilitando el seguimiento del proceso de selección.
La acción para cargar una nota permite registrar la evaluación correspondiente a cada postulante. Sin embargo, el prototipo actual debe ampliarse para representar también la programación de entrevistas, incluyendo fecha, hora y modalidad, de acuerdo con los requisitos funcionales del sistema.

**Formulario (si aplica):**

- Cantidad de campos: El formulario de programación deberá incluir, como mínimo, fecha, hora y modalidad. Los campos para registrar la evaluación deberán corresponder a los datos definidos en el sistema.
- Flujo: Programación y registro de resultados en formularios específicos de una pantalla.
- Validaciones relevantes:
  - La entrevista debe estar asociada a una postulación existente.
  - La fecha, hora y modalidad deben estar completas al programar la entrevista.
  - La empresa solamente debe gestionar entrevistas correspondientes a sus convocatorias.
  - Los resultados deben quedar asociados a la entrevista y a la postulación correspondiente.

---

## Pantalla / Módulo 8 —

**Wireframe:**

**Patrones de diseño utilizados:**

**Justificación:**  

**Formulario (si aplica):**

---

## Consideraciones de accesibilidad

