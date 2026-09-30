# Diseño UI

_Presentar al menos un wireframe por pantalla o módulo relevante._
_Los wireframes en imagen o PDF van en `diagramas/wireframes/`; acá se documenta la justificación de cada uno._

---

## Pantalla / Módulo 1 — Dashboard General

**Wireframe:** `diagramas/wireframes/WF-01-dashboard-general.png`

**Patrones de diseño utilizados:** Dashboard, tarjetas de métricas, menú lateral y listado de actividad reciente.

**Justificación:** Se utiliza un patrón Dashboard porque permite que el Administrador o Empresa tenga una vista general de la información más importante del sistema. Las tarjetas de métricas permiten identificar rápidamente la cantidad de usuarios, carreras, docentes, egresados, convocatorias y entrevistas. El menú lateral organiza el acceso a los diferentes módulos del sistema, mientras que la sección de actividad reciente permite consultar las últimas acciones realizadas.

**Formulario (si aplica):**
- Cantidad de campos: No aplica.
- Flujo (todo en una pantalla / por pasos): Navegación desde el dashboard hacia los diferentes módulos.
- Validaciones relevantes: Se debe controlar el acceso según el rol del usuario autenticado.

---

## Pantalla / Módulo 2 — Gestión de Usuarios

**Wireframe:** `diagramas/wireframes/WF-02-usuarios.png`

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

## Pantalla / Módulo 3 — Docentes y Egresados

**Wireframe:** `diagramas/wireframes/WF-03-docentes-egresados.png`

**Patrones de diseño utilizados:** Tabla, buscador y acciones sobre registros.

**Justificación:**  
La tabla permite al Administrador consultar de manera ordenada el padrón de docentes y egresados. El buscador facilita encontrar rápidamente un candidato mediante datos como DNI o nombre. La columna correspondiente al CV permite verificar si el usuario posee un currículum adjunto y acceder a él cuando sea necesario.

Este diseño resulta adecuado porque concentra en una única pantalla la información necesaria para administrar y verificar los candidatos.

**Formulario (si aplica):**
- Cantidad de campos: No aplica para la consulta. El alta de un nuevo registro utiliza un formulario específico.
- Flujo (todo en una pantalla / por pasos): Consulta y búsqueda en una pantalla.
- Validaciones relevantes:
  - Verificar que el usuario corresponda a un docente o egresado.
  - Validar los datos obligatorios al agregar un nuevo registro.
  - El acceso a esta información debe estar restringido al Administrador.

---

## Pantalla / Módulo 4 — Gestión de Convocatorias

**Wireframe:** `diagramas/wireframes/WF-04-convocatorias.png`

**Patrones de diseño utilizados:** Tabla de datos, acciones por registro y filtros/consulta.

**Justificación:**  
La tabla permite visualizar las convocatorias de forma organizada, mostrando información relevante como empresa, puesto, lugar y período de vigencia. Las acciones permiten acceder a los postulantes o editar una convocatoria.

Este patrón es adecuado para la gestión de convocatorias porque permite administrar múltiples búsquedas sin necesidad de ingresar a cada una individualmente. Además, el diseño diferencia las acciones disponibles para la Empresa y el Administrador.

**Formulario (si aplica):**
- Cantidad de campos: No aplica para la consulta de convocatorias.
- Flujo (todo en una pantalla / por pasos): Consulta en una pantalla.
- Validaciones relevantes:
  - Solo la empresa correspondiente puede modificar sus convocatorias.
  - Las convocatorias deben mostrar correctamente su período de vigencia.
  - Las convocatorias caducadas deben ocultarse automáticamente.

---

## Pantalla / Módulo 5 — Alta de Convocatoria

**Wireframe:** `diagramas/wireframes/WF-05-alta-convocatoria.png`

**Patrones de diseño utilizados:** Formulario y ventana modal/pantalla de alta.

**Justificación:**  
Se utiliza un formulario para permitir que la Empresa registre los datos necesarios de una nueva convocatoria de forma organizada. Los campos se agrupan en una única pantalla para que la carga sea directa y sencilla.

El formulario permite registrar información relacionada con el puesto, modalidad y período de vigencia. La validación de fechas es especialmente importante porque determina cuándo la convocatoria se encuentra disponible para recibir postulaciones.

**Formulario (si aplica):**
- Cantidad de campos: 5 campos visibles en el wireframe: título/puesto, modalidad, fecha de inicio y fecha de fin, considerando los datos mostrados en el diseño.
- Flujo (todo en una pantalla / por pasos): Todo en una pantalla.
- Validaciones relevantes:
  - Completar los campos obligatorios.
  - La fecha de fin debe ser posterior a la fecha de inicio.
  - La convocatoria debe quedar asociada a la empresa que la crea.
  - Las convocatorias caducadas deben dejar de estar disponibles.

---

## Pantalla / Módulo 6 — Entrevistas y Evaluación

**Wireframe:** `diagramas/wireframes/WF-06-panel-evaluacion.png`

**Patrones de diseño utilizados:** Tabla de evaluación y acciones por registro.

**Justificación:**  
Se utiliza una tabla para que la Empresa pueda consultar y evaluar a los postulantes que participan del proceso de selección. La información se organiza por postulante, puesto, puntaje y resultado, permitiendo comparar los registros de manera ordenada.

La acción "Cargar Nota" permite registrar la evaluación correspondiente a cada postulante sin abandonar la pantalla principal del módulo.

**Formulario (si aplica):**
- Cantidad de campos: La carga de evaluación se realiza sobre el postulante seleccionado.
- Flujo (todo en una pantalla / por pasos): Todo en una pantalla.
- Validaciones relevantes:
  - El postulante debe pertenecer a una convocatoria de la empresa.
  - El puntaje debe ser válido.
  - El resultado debe quedar asociado al postulante correspondiente.
  - Solo la Empresa responsable de la convocatoria debe poder realizar la evaluación.

---

## Pantalla / Módulo 7 — Portal Web del Postulante

**Wireframe:** `diagramas/wireframes/WF-07-portal-postulante.png`

**Patrones de diseño utilizados:** Cards de convocatorias, botón de acción principal y diseño responsive.

**Justificación:**  
Se utiliza el patrón Card para mostrar las convocatorias disponibles de forma clara y permitir que el usuario consulte rápidamente el puesto, empresa, ubicación y descripción. El botón "Postularme Ahora" funciona como acción principal y facilita el acceso al proceso de postulación.

El diseño está pensado para ser responsive, permitiendo su utilización tanto desde computadoras como desde dispositivos móviles. Además, el portal permite acceder al perfil y a las postulaciones del usuario.

Una característica importante del diseño es la vinculación automática del CV: al seleccionar "Postularme Ahora", el sistema verifica que el usuario tenga un CV cargado y lo adjunta automáticamente a la postulación, evitando que tenga que cargarlo nuevamente. :contentReference[oaicite:2]{index=2}

**Formulario (si aplica):**
- Cantidad de campos: No requiere nuevos campos para la postulación cuando el usuario ya posee un CV cargado.
- Flujo (todo en una pantalla / por pasos): Todo en una pantalla.
- Validaciones relevantes:
  - El usuario debe estar autenticado.
  - Debe existir un CV cargado.
  - La convocatoria debe estar vigente.
  - No se debe permitir una segunda postulación a la misma convocatoria.
  - El CV debe adjuntarse automáticamente a la postulación.

---

## Pantalla / Módulo 8 — Registro de Usuario

**Wireframe:** `diagramas/wireframes/WF-08-registro.png`

**Patrones de diseño utilizados:** Formulario de registro y validación de campos.

**Justificación:**  
Se utiliza un formulario simple para facilitar el registro de docentes y egresados. La interfaz solicita el tipo de usuario, correo institucional y contraseña, evitando incorporar información innecesaria en esta primera etapa.

El formulario incorpora una validación específica del dominio institucional, ya que el sistema solamente permite el registro mediante correos pertenecientes al dominio `@terciariourquiza.edu.ar`. Esto permite controlar quién puede registrarse y mantener el acceso restringido a usuarios de la institución. :contentReference[oaicite:3]{index=3}

**Formulario (si aplica):**
- Cantidad de campos: 3 campos visibles: tipo de usuario, correo institucional y contraseña.
- Flujo (todo en una pantalla / por pasos): Todo en una pantalla.
- Validaciones relevantes:
  - El correo debe pertenecer al dominio `@terciariourquiza.edu.ar`.
  - El tipo de usuario debe estar seleccionado.
  - La contraseña debe ser ingresada.
  - No se debe permitir registrar un correo que ya exista.

---

## Consideraciones de accesibilidad

- Los botones de acciones principales, como **"Postularme Ahora"**, **"Crear Mi Cuenta"**, **"Editar"** y **"Cargar Nota"**, deben utilizar textos descriptivos y no depender únicamente de íconos.
- Los estados de las convocatorias, postulaciones y entrevistas no deben comunicarse únicamente mediante colores. Deben acompañarse de texto, por ejemplo: **"Activo"**, **"Aprobado"** o **"Desaprobado"**.
- Los formularios deben presentar etiquetas visibles para cada campo y mensajes claros cuando se produzca un error de validación.
- El portal de postulantes debe mantener botones y campos suficientemente grandes para poder utilizarse desde dispositivos móviles, teniendo en cuenta que el WF-07 está planteado como una vista responsive Desktop/Mobile. :contentReference[oaicite:4]{index=4}
- La navegación del menú lateral y las tablas debe mantener un orden lógico para permitir el uso mediante teclado.
- Los archivos PDF asociados a los CV deben identificarse mediante texto, y no únicamente mediante el ícono de PDF.
