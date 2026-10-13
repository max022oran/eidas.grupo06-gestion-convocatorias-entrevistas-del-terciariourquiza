# Diseño UI

_Presentar al menos un wireframe por pantalla o módulo relevante._
_Los wireframes en imagen o PDF van en `diagramas/wireframes/`; acá se documenta la justificación de cada uno._

---

## Criterios generales

- **Estructura común:** todas las pantallas, salvo el acceso y el registro, comparten una barra superior (nombre del sistema, usuario con su rol y "Cerrar sesión") y un menú lateral que muestra solo los módulos del rol (RF-05, RF-24).
- **Menús por rol:**
  - Postulante: Inicio, Convocatorias, Mis postulaciones, Mi CV.
  - Empresa: Inicio, Mis convocatorias, Postulantes, Entrevistas.
  - Administrador: Inicio, Usuarios, Empresas, Padrón, Carreras, Resultados, Reportes.
- **Errores en formularios:** se muestran debajo del campo, antes de enviar, con un mensaje específico (RNF-06).
- **Confirmaciones:** las acciones que cambian un estado o reemplazan datos (postularse, reemplazar CV, cerrar convocatoria, cargar resultado) piden confirmación en una ventana modal.

| Wireframe | Pantalla | Rol | Casos de uso |
|-----------|----------|-----|--------------|
| WF-01 | Iniciar sesión | Todos | CU-13 |
| WF-02 | Registro de postulante | Postulante | CU-15 |
| WF-03 | Inicio del postulante | Postulante | CU-14 |
| WF-04 | Inicio de la empresa | Empresa | CU-14 |
| WF-05 | Inicio del administrador | Administrador | CU-14 |
| WF-06 | Convocatorias disponibles | Postulante | CU-01 |
| WF-07 | Detalle y confirmación de postulación | Postulante | CU-01, CU-02 |
| WF-08 | Mis postulaciones | Postulante | CU-03, CU-04, CU-16 |
| WF-09 | Mi CV | Postulante | CU-05 |
| WF-10 | Mis convocatorias | Empresa | CU-06 |
| WF-11 | Alta y edición de convocatoria | Empresa | CU-06 |
| WF-12 | Postulantes de una convocatoria | Empresa | CU-07 |
| WF-13 | Programar entrevista | Empresa | CU-08 |
| WF-14 | Entrevistas y carga de resultado | Empresa | CU-09 |
| WF-15 | Gestión de usuarios | Administrador | CU-10 |
| WF-16 | Alta de empresa | Administrador | CU-17 |
| WF-17 | Padrón de usuarios | Administrador | CU-19 |
| WF-18 | Carreras | Administrador | CU-18 |
| WF-19 | Resultados | Administrador | CU-12 |
| WF-20 | Reportes | Administrador | CU-11 |

---

## Pantalla / Módulo 1 — Inicio

### Iniciar sesión

**Wireframe:** WF-01 <img width="1200" height="720" alt="WF-01-iniciar-sesion" src="https://github.com/user-attachments/assets/01190b6d-b33f-447d-8131-81e369d98b1b" />

**Patrones de diseño utilizados:** Formulario centrado, mensaje de error en línea.

**Justificación:** Es una pantalla única para los tres roles, porque todos acceden con correo y contraseña (RF-02). El error no indica si falló el correo o la contraseña, para no dar pistas a quien intente adivinar una cuenta, pero sí avisa cuántos intentos quedan antes del bloqueo de 15 minutos (RF-07). Desde acá se accede al registro de postulantes; las empresas no se registran solas, las crea el administrador.

**Formulario:**
- Cantidad de campos: 2 (correo y contraseña).
- Flujo: todo en una pantalla.
- Validaciones relevantes: campos completos; cuenta activa y no bloqueada; 3 intentos fallidos consecutivos bloquean la cuenta durante 15 minutos.

### Inicio según el rol

**Wireframes:**
WF-03 <img width="1200" height="720" alt="WF-03-inicio-postulante" src="https://github.com/user-attachments/assets/9621b112-bdbc-4d25-af8d-a7864e3fba6c" />
WF-04 <img width="1200" height="720" alt="WF-04-inicio-empresa" src="https://github.com/user-attachments/assets/78ca1893-4a31-4fcb-bba1-d19d972fb125" />
WF-05 <img width="1200" height="720" alt="WF-05-inicio-administrador" src="https://github.com/user-attachments/assets/6b840e34-c6c2-4e27-974a-267545345f5e" />

**Patrones de diseño utilizados:** Dashboard con tarjetas de métricas, listas resumidas y accesos rápidos.

**Justificación:** Cada rol ve lo que tiene pendiente sin recorrer los módulos (RF-25). El postulante ve sus postulaciones y su próxima entrevista; la empresa, sus convocatorias vigentes con la cantidad de postulantes y un acceso directo a "Ver postulantes"; el administrador, los totales del sistema y accesos a sus tareas frecuentes. Los números son pocos y grandes para leerse de un vistazo; el detalle está siempre a un clic.

**Formulario:** No aplica.

---

## Pantalla / Módulo 2 — Usuario / Postulante

### Registro de postulante

**Wireframe:** WF-02 <img width="1200" height="720" alt="WF-02-registro" src="https://github.com/user-attachments/assets/c81ec49c-9a15-4c48-9095-5f73d56c0a81" />

**Patrones de diseño utilizados:** Formulario en una columna con campos agrupados en pares, validación en línea.

**Justificación:** El registro pide solo los datos necesarios para postularse. La carrera se elige de una lista desplegable con las carreras activas, en lugar de escribirse, para que el filtro de convocatorias funcione sin errores de tipeo (RF-30). El aviso del dominio institucional aparece debajo del campo en el momento en que el correo no corresponde (RNF-04).

**Formulario:**
- Cantidad de campos: 5 (nombre, apellido, correo, contraseña y carrera).
- Flujo: todo en una pantalla.
- Validaciones relevantes: correo del dominio @terciariourquiza.edu.ar; correo no registrado previamente; todos los campos obligatorios.

### Mi CV

**Wireframe:** WF-09 <img width="1200" height="720" alt="WF-09-mi-cv" src="https://github.com/user-attachments/assets/cf57178c-d614-4cc5-ba00-34ee1c3c5733" />

**Patrones de diseño utilizados:** Zona de carga de archivos (arrastrar o elegir), tarjeta del archivo actual, ventana modal de confirmación.

**Justificación:** Muestra primero el CV vigente, con su fecha de carga, para que el postulante sepa qué ven las empresas. La zona de carga indica los límites (solo PDF, máximo 5 MB) antes de elegir el archivo. Como cada usuario tiene un único CV, reemplazarlo pide confirmación y explica que el nuevo CV también se verá en las postulaciones existentes (RF-09, decisión 3 del modelo ER).

**Formulario:**
- Cantidad de campos: 1 (archivo).
- Flujo: carga en la misma pantalla, con confirmación modal si ya existe un CV.
- Validaciones relevantes: formato PDF; tamaño máximo de 5 MB; archivo seleccionado.

### Gestión de usuarios

**Wireframe:** WF-15 <img width="1200" height="720" alt="WF-15-gestion-usuarios" src="https://github.com/user-attachments/assets/72fde3b1-244d-48d8-a12b-054b3639098f" />

**Patrones de diseño utilizados:** Tabla de datos con buscador, filtro por rol y acciones por fila.

**Justificación:** La tabla permite ver muchas cuentas a la vez con su rol y su estado (activa, bloqueada o dada de baja). Las acciones "Editar rol" y "Dar de baja" están en cada fila para operar sin abrir otra pantalla. La propia cuenta del administrador no muestra "Dar de baja", para que el sistema no quede sin administrador. Los roles son solo los tres definidos en RF-04.

**Formulario:**
- Cantidad de campos: 1 al editar (rol).
- Flujo: edición en una ventana modal desde la tabla.
- Validaciones relevantes: solo el administrador accede; el rol debe ser Postulante, Empresa o Administrador; la baja pide confirmación.

### Alta de empresa

**Wireframe:** WF-16 <img width="1200" height="720" alt="WF-16-alta-empresa" src="https://github.com/user-attachments/assets/2dfa1a50-69f7-4b84-b605-bc8c8da872cd" />

**Patrones de diseño utilizados:** Formulario dividido en dos bloques.

**Justificación:** El formulario separa los datos de la empresa de los de la cuenta de acceso, igual que el modelo ER (Empresa y su Usuario). El correo no exige el dominio institucional, porque las empresas son externas (RF-26).

**Formulario:**
- Cantidad de campos: 6 (nombre de la empresa, rubro, nombre y apellido del contacto, correo, contraseña inicial).
- Flujo: todo en una pantalla.
- Validaciones relevantes: correo no registrado; campos obligatorios completos.

### Padrón de usuarios

**Wireframe:** WF-17 <img width="1200" height="720" alt="WF-17-padron-usuarios" src="https://github.com/user-attachments/assets/9ba60d7c-7fbd-44b9-b9b5-4f06a18179dd" />

**Patrones de diseño utilizados:** Tabla de datos con buscador y filtro por carrera.

**Justificación:** Reemplaza al módulo "Docentes y Egresados" de la versión anterior. Permite al administrador saber qué estudiantes y egresados están registrados y cuáles tienen CV cargado, que es la condición para postularse (RF-27). El estado del CV se indica con símbolo y texto ("✔ Cargado", "✘ Sin CV").

**Formulario:** No aplica (solo búsqueda).

---

## Pantalla / Módulo 3 — Carreras

**Wireframe:** WF-18 <img width="1200" height="720" alt="WF-18-carreras" src="https://github.com/user-attachments/assets/07e66cd6-0cd7-48ab-97a3-e2d27193a18c" />

**Patrones de diseño utilizados:** Tabla de datos con acciones por fila, mensaje de advertencia.

**Justificación:** La tabla muestra cuántos usuarios y convocatorias vigentes usa cada carrera, para que el administrador entienda por qué no puede desactivar una que está en uso (RF-31). Las carreras no se eliminan, se desactivan: así los usuarios y convocatorias que ya la tienen no quedan sin carrera. El postulante usa este módulo indirectamente, a través del filtro por carrera de WF-06.

**Formulario:**
- Cantidad de campos: 1 (nombre de la carrera).
- Flujo: alta y edición en una ventana modal.
- Validaciones relevantes: nombre no repetido; no desactivar carreras con convocatorias vigentes.

---

## Pantalla / Módulo 4 — Convocatorias

### Convocatorias disponibles (postulante)

**Wireframe:** WF-06 <img width="1200" height="720" alt="WF-06-convocatorias-disponibles" src="https://github.com/user-attachments/assets/c223e8dd-3524-4932-9ab1-08780932f7d3" />

**Patrones de diseño utilizados:** Tarjetas (cards), buscador y filtro por carrera.

**Justificación:** Las tarjetas presentan cada convocatoria por separado con los datos que el postulante usa para decidir: empresa, ubicación, modalidad, carreras y fecha de cierre. Se muestran solo las vigentes (RF-16). El filtro por carrera reduce la búsqueda a las convocatorias dirigidas a su formación (RF-30) y se puede quitar con un botón.

**Formulario:** No aplica (solo búsqueda y filtro).

### Detalle y postulación

**Wireframe:** WF-07 <img width="1200" height="720" alt="WF-07-detalle-y-postulacion" src="https://github.com/user-attachments/assets/fbc804e9-d73c-4b69-8d57-41493d639f54" />

**Patrones de diseño utilizados:** Página de detalle con panel de acción lateral, ventana modal de confirmación.

**Justificación:** El panel "Postularme" muestra qué CV se va a adjuntar antes de confirmar, porque el sistema lo toma automáticamente (RF-14). El flujo completo es: Convocatorias → Ver detalle → Postularme → Confirmar, es decir 4 pasos desde el inicio, como pide RNF-03. Si el postulante no tiene CV, la confirmación lo indica y lleva a "Mi CV".

**Formulario:**
- Cantidad de campos: ninguno; solo confirmación.
- Flujo: detalle y confirmación modal en la misma pantalla.
- Validaciones relevantes: CV cargado; convocatoria vigente al confirmar; sin postulación previa a la misma convocatoria.

### Mis postulaciones

**Wireframe:** WF-08 <img width="1200" height="720" alt="WF-08-mis-postulaciones" src="https://github.com/user-attachments/assets/cbd8191f-f38e-4876-b457-e82059a25c1d" />

**Patrones de diseño utilizados:** Tabla de seguimiento con estados.

**Justificación:** Resuelve el problema que da origen al proyecto: el postulante no sabía en qué quedaba su postulación. En una sola tabla ve el estado, los datos de la entrevista y el resultado de cada postulación (CU-03, CU-04, CU-16). Cuando todavía no hay entrevista o resultado, la celda lo dice ("Sin entrevista asignada", "Aún no disponible") en lugar de quedar vacía.

**Formulario:** No aplica.

### Mis convocatorias (empresa)

**Wireframe:** WF-10 <img width="1200" height="720" alt="WF-10-mis-convocatorias" src="https://github.com/user-attachments/assets/c74bee58-b570-4678-8b47-631a0ef79948" />

**Patrones de diseño utilizados:** Tabla de datos con acciones por fila según el estado.

**Justificación:** La empresa ve solo sus convocatorias (RF-32), con fechas, cantidad de postulantes y estado. Las acciones cambian según el estado: una convocatoria Vigente se puede editar o cerrar; una Cerrada o Vencida solo permite ver sus postulantes, porque las postulaciones se conservan.

**Formulario:** No aplica (las acciones llevan a WF-11 o a la confirmación de cierre).

### Alta y edición de convocatoria

**Wireframe:** WF-11 <img width="1200" height="720" alt="WF-11-alta-convocatoria" src="https://github.com/user-attachments/assets/47440423-3ce8-4587-9de8-bdb01da3494e" />

**Patrones de diseño utilizados:** Formulario en dos columnas, lista de casillas para las carreras.

**Justificación:** La columna izquierda agrupa los textos largos (descripción y requisitos) y la derecha los datos cortos (ubicación, modalidad, fechas y carreras). Las carreras se eligen con casillas porque una convocatoria puede estar dirigida a varias (RF-29). El mismo formulario se usa para editar.

**Formulario:**
- Cantidad de campos: 10 (título, puesto, descripción, requisitos, ubicación, modalidad, fecha de inicio, fecha de fin, carreras destinatarias y link externo opcional).
- Flujo: todo en una pantalla.
- Validaciones relevantes: campos obligatorios completos; fecha de fin posterior a la de inicio (RF-33); al menos una carrera; la empresa solo edita sus propias convocatorias.

### Postulantes de una convocatoria

**Wireframe:** WF-12 <img width="1200" height="720" alt="WF-12-postulantes" src="https://github.com/user-attachments/assets/7f643a93-3e94-4032-8c07-e6fc8c6424de" />

**Patrones de diseño utilizados:** Tabla de datos con selector de convocatoria y acciones por fila.

**Justificación:** La empresa elige una de sus convocatorias y ve sus postulantes con carrera, fecha, estado y acceso al CV (RF-17). La acción de cada fila depende del estado: a un postulante en estado Postulado se le puede programar una entrevista; a uno con entrevista programada, cargar el resultado.

**Formulario:** No aplica.

---

## Pantalla / Módulo 5 — Entrevistas

### Programar entrevista

**Wireframe:** WF-13 <img width="1200" height="720" alt="WF-13-programar-entrevista" src="https://github.com/user-attachments/assets/e4e7076a-cf28-43ae-a66f-9e911f2437ba" />

**Patrones de diseño utilizados:** Ventana modal con formulario corto.

**Justificación:** Se abre desde la lista de postulantes para no perder el contexto de la convocatoria. Muestra a qué postulante y convocatoria corresponde y pide solo fecha, hora y modalidad (RF-21).

**Formulario:**
- Cantidad de campos: 3 (fecha, hora y modalidad).
- Flujo: ventana modal sobre WF-12.
- Validaciones relevantes: campos completos; fecha y hora no anteriores al momento actual (RF-35); una sola entrevista por postulación.

### Entrevistas y carga de resultado

**Wireframe:** WF-14 <img width="1200" height="720" alt="WF-14-cargar-resultado" src="https://github.com/user-attachments/assets/cbc8a2b9-2261-4153-ac09-740f9f2ef5d4" />

**Patrones de diseño utilizados:** Tabla de entrevistas con estados, ventana modal de carga de resultado.

**Justificación:** La empresa ve todas sus entrevistas con fecha, modalidad y estado (Programada o Realizada). El resultado se carga desde la fila de cada entrevista Programada. La ventana explica qué pasa al confirmar (la entrevista pasa a Realizada y la postulación toma el resultado), porque la acción modifica dos estados a la vez (RF-36).

**Formulario:**
- Cantidad de campos: 2 (puntaje y resultado).
- Flujo: ventana modal sobre la tabla de entrevistas.
- Validaciones relevantes: puntaje numérico (la escala queda por acordar, ver HU-18); resultado Aprobado o No aprobado; solo entrevistas Programadas de convocatorias propias.

### Resultados (administrador)

**Wireframe:** WF-19 <img width="1200" height="720" alt="WF-19-resultados" src="https://github.com/user-attachments/assets/c4973783-adb3-4b0f-9ab3-2bcb60321ffc" />

**Patrones de diseño utilizados:** Tabla de datos con acceso al detalle.

**Justificación:** Reúne en una tabla los resultados que cargaron todas las empresas, con postulante, convocatoria, puntaje y resultado, para que el administrador supervise los procesos sin entrar a cada convocatoria (RF-37).

**Formulario:** No aplica.

### Reportes

**Wireframe:** WF-20 <img width="1200" height="720" alt="WF-20-reportes" src="https://github.com/user-attachments/assets/301a34ef-7d14-48aa-8436-d866f0d8a4fe" />

**Patrones de diseño utilizados:** Panel de filtros sobre tabla de resultados.

**Justificación:** Los filtros quedan arriba y el reporte debajo, para que el administrador vea en la misma pantalla qué filtró y qué obtuvo (RF-23). Los filtros son los datos que el sistema realmente guarda: tipo de reporte, período, empresa y carrera.

**Formulario:**
- Cantidad de campos: 5 (tipo de reporte, desde, hasta, empresa y carrera).
- Flujo: filtros y resultado en una pantalla.
- Validaciones relevantes: tipo de reporte obligatorio; fecha "desde" anterior a "hasta"; aviso si no hay datos para los filtros.

---

## Consideraciones de accesibilidad

- **Los estados no dependen solo del color (RNF-07):** cada estado se muestra con su nombre escrito dentro de una etiqueta (por ejemplo, "Entrevista programada", "No aprobado"), y además con un borde distinto: lleno, rayado o punteado. Así se entienden también en escala de grises o para personas con daltonismo.
- **Etiquetas visibles:** todos los campos tienen su etiqueta arriba, siempre visible, y no solo un texto de ejemplo dentro del campo que desaparece al escribir. Los obligatorios se marcan con * y se aclara qué significa.
- **Errores junto al campo:** los mensajes de error aparecen debajo del campo que los produce, con un símbolo de advertencia y un texto que dice cómo corregirlo, no solo "dato inválido" (RNF-06).
- **Botones con texto:** las acciones dicen lo que hacen ("Programar entrevista", "Confirmar resultado"); no se usan íconos solos.
- **Celdas sin datos explicadas:** cuando falta información, se escribe el motivo ("Sin entrevista asignada", "Aún no disponible") en lugar de dejar la celda vacía.
- **Contraste y tamaño:** textos oscuros sobre fondo claro y tamaño mínimo de 12 px en datos secundarios.
