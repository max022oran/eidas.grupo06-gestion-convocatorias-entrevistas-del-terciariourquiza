# Historias de usuario

_Presentar al menos una historia de usuario representativa por módulo._
_Cada historia debe incluir formato clásico, criterios de aceptación y validación INVEST._

---

# Módulo 1 — Inicio

## HU-01 — Ver la pantalla de inicio según mi rol

| Campo | Detalle |
|-------|---------|
| Historia | Como usuario del sistema (postulante, empresa o administrador), quiero ver al iniciar sesión un resumen de lo que me corresponde, para saber qué tengo pendiente sin recorrer cada módulo. |
| Módulo | Inicio |
| Requisitos relacionados | RF-05, RF-24, RF-25 |

### Criterios de aceptación

1. Al iniciar sesión, el menú muestra solo los módulos habilitados para mi rol; por ejemplo, un postulante no ve la administración de carreras ni la de usuarios.
2. El postulante ve sus postulaciones y sus próximas entrevistas.
3. La empresa ve sus convocatorias vigentes y la cantidad de postulantes de cada una.
4. El administrador ve la cantidad de convocatorias, postulaciones y entrevistas registradas.
5. Si no hay datos para mostrar (por ejemplo, un postulante sin postulaciones), el sistema muestra un mensaje en lugar de un bloque vacío.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | No | Para mostrar el resumen necesita que existan el inicio de sesión (HU-02), las convocatorias (HU-09), las postulaciones (HU-13) y las entrevistas (HU-16). Conviene construirla al final. |
| Negociable | Sí | Qué indicadores aparecen en cada resumen se puede acordar con la institución sin cambiar el objetivo. |
| Valiosa | Sí | Evita que cada actor tenga que entrar módulo por módulo para ver qué tiene pendiente. |
| Estimable | Parcial | Son tres resúmenes distintos, uno por rol; se puede estimar recién cuando estén definidos los datos de cada uno. |
| Pequeña | No | Agrupa tres pantallas diferentes. Se podría dividir en una historia por rol. |
| Verificable | Sí | Se prueba ingresando con un usuario de cada rol y comparando los números del resumen con los registros cargados. |

---

# Módulo 2 — Usuario / Postulante

## HU-02 — Registrarme con mi correo institucional

| Campo | Detalle |
|-------|---------|
| Historia | Como postulante, quiero registrarme con mi correo institucional, para poder postularme a las convocatorias de la bolsa de trabajo. |
| Módulo | Usuario / Postulante |
| Requisitos relacionados | RF-01, RNF-04, RNF-05, RNF-06 |

### Criterios de aceptación

1. El registro solicita nombre, apellido, correo, contraseña y carrera.
2. El sistema solo acepta correos del dominio institucional autorizado; con otro dominio informa que el correo no es válido.
3. Si el correo ya está registrado, el sistema lo informa y no crea una segunda cuenta.
4. La carrera se elige de la lista de carreras activas.
5. Si los datos son correctos, el sistema crea la cuenta con rol Postulante y confirma el registro.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Parcial | Necesita que existan carreras cargadas (HU-07) para poder elegir una. |
| Negociable | Sí | Se pueden acordar los campos opcionales y el texto de los mensajes de error. |
| Valiosa | Sí | Sin registro, ningún postulante puede usar el sistema. |
| Estimable | Sí | Los campos y las tres validaciones (dominio, duplicado, campos completos) están definidos. |
| Pequeña | Sí | Se limita a crear la cuenta del postulante. |
| Verificable | Sí | Se prueba registrando un correo institucional válido, uno de otro dominio y uno ya registrado. |

---

## HU-03 — Cargar o reemplazar mi CV

| Campo | Detalle |
|-------|---------|
| Historia | Como postulante, quiero cargar mi CV y poder reemplazarlo, para que las empresas vean mi información actualizada cuando me postulo. |
| Módulo | Usuario / Postulante |
| Requisitos relacionados | RF-09, RF-14 |

### Criterios de aceptación

1. Debo haber iniciado sesión.
2. El sistema acepta solo archivos PDF de hasta 5 MB; si no cumple, informa el motivo y no guarda el archivo.
3. Si ya tengo un CV cargado, el sistema me pide confirmar el reemplazo antes de guardar el nuevo.
4. El CV queda asociado a mi cuenta como único CV vigente.
5. El sistema muestra la confirmación de carga.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Parcial | Requiere que el postulante esté registrado (HU-02). |
| Negociable | Sí | El tamaño máximo y los formatos aceptados se pueden revisar con la institución. |
| Valiosa | Sí | Es condición para postularse (RF-13). |
| Estimable | Sí | Formato, tamaño y comportamiento al reemplazar están definidos. |
| Pequeña | Sí | Solo carga y reemplazo; no incluye historial de versiones. |
| Verificable | Sí | Se prueba subiendo un PDF de 4 MB (se acepta), uno de 6 MB y un .docx (se rechazan), y reemplazando un CV existente. |

---

## HU-04 — Administrar cuentas y roles

| Campo | Detalle |
|-------|---------|
| Historia | Como administrador, quiero dar de alta, modificar y dar de baja cuentas y asignarles un rol, para que cada persona acceda solo a lo que le corresponde. |
| Módulo | Usuario / Postulante |
| Requisitos relacionados | RF-04, RF-05, RF-08 |

### Criterios de aceptación

1. Solo un usuario con rol Administrador puede acceder a esta función.
2. El administrador puede asignar uno de los tres roles: Postulante, Empresa o Administrador.
3. Una cuenta dada de baja no puede iniciar sesión.
4. Al cambiar el rol, el usuario ve en su próximo ingreso solo los módulos del nuevo rol.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Parcial | Requiere que exista el inicio de sesión y al menos un usuario registrado (HU-02). |
| Negociable | Sí | Se puede acordar si la baja es definitiva o una suspensión reversible. |
| Valiosa | Sí | Controla quién accede a la información personal y administrativa. |
| Estimable | Parcial | Alta, modificación, baja y asignación de rol son cuatro operaciones; cada una se estima por separado. |
| Pequeña | No | Reúne cuatro operaciones distintas. Se podría separar en "asignar rol" y "dar de baja una cuenta". |
| Verificable | Sí | Se prueba cambiando el rol de un usuario y verificando que en el siguiente ingreso ve otros módulos, y que una cuenta dada de baja no puede ingresar. |

---

## HU-05 — Dar de alta una empresa

| Campo | Detalle |
|-------|---------|
| Historia | Como administrador, quiero crear la cuenta de una empresa, para que pueda publicar convocatorias en la bolsa de trabajo. |
| Módulo | Usuario / Postulante |
| Requisitos relacionados | RF-26, RNF-04 |

### Criterios de aceptación

1. El alta solicita nombre de la empresa, rubro, correo y contraseña inicial.
2. El correo de la empresa no necesita ser del dominio institucional.
3. Si el correo ya está registrado, el sistema lo informa y no crea la cuenta.
4. La cuenta creada tiene rol Empresa y puede iniciar sesión con esos datos.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Parcial | Requiere que el administrador pueda iniciar sesión. |
| Negociable | Sí | Se puede acordar si la empresa recibe la contraseña por correo o se la entrega la institución. |
| Valiosa | Sí | Sin empresas no hay convocatorias; es la única forma de que una empresa entre al sistema. |
| Estimable | Sí | Campos y validaciones definidos. |
| Pequeña | Sí | Solo crea la cuenta; editar los datos de la empresa queda fuera. |
| Verificable | Sí | Se prueba creando una empresa con correo no institucional e iniciando sesión con ella. |

---

## HU-06 — Consultar el padrón de usuarios

| Campo | Detalle |
|-------|---------|
| Historia | Como administrador, quiero buscar a los usuarios registrados y ver si tienen CV cargado, para saber quiénes están en condiciones de postularse. |
| Módulo | Usuario / Postulante |
| Requisitos relacionados | RF-27 |

### Criterios de aceptación

1. El listado muestra nombre, apellido, correo, carrera y si tiene CV cargado.
2. Se puede buscar por nombre, apellido o carrera.
3. Si la búsqueda no encuentra resultados, el sistema lo informa.
4. Solo el administrador puede acceder al padrón.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Parcial | Necesita usuarios registrados (HU-02) y carreras (HU-07) para poder buscar por ellas. |
| Negociable | Sí | Las columnas del listado y los filtros se pueden acordar. |
| Valiosa | Parcial | Es útil para la institución, pero no es necesaria para que postulantes y empresas usen el sistema. |
| Estimable | Sí | Es una consulta con tres filtros definidos. |
| Pequeña | Sí | Solo consulta; no modifica datos. |
| Verificable | Sí | Se prueba buscando por carrera y verificando que aparecen solo los usuarios de esa carrera. |

---

# Módulo 3 — Carreras

## HU-07 — Administrar las carreras

| Campo | Detalle |
|-------|---------|
| Historia | Como administrador, quiero crear, editar y desactivar las carreras del terciario, para que postulantes y empresas usen siempre la lista vigente. |
| Módulo | Carreras |
| Requisitos relacionados | RF-28, RF-31 |

### Criterios de aceptación

1. El administrador puede crear una carrera indicando su nombre; no se permiten dos carreras con el mismo nombre.
2. El administrador puede editar el nombre de una carrera.
3. El sistema impide desactivar una carrera indicada en convocatorias vigentes e informa el motivo.
4. Una carrera desactivada no aparece en el registro ni al crear convocatorias.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí | Solo requiere el acceso del administrador; es de las primeras que se pueden construir. |
| Negociable | Sí | Se puede acordar si además del nombre se guarda la duración o el título. |
| Valiosa | Sí | El registro (HU-02) y las convocatorias (HU-09) dependen de esta lista. |
| Estimable | Sí | Tres operaciones simples sobre una sola entidad. |
| Pequeña | Sí | Abarca una entidad con pocas reglas. |
| Verificable | Sí | Se prueba intentando desactivar una carrera usada en una convocatoria vigente (se rechaza) y otra sin uso (se desactiva). |

---

## HU-08 — Filtrar convocatorias por carrera

| Campo | Detalle |
|-------|---------|
| Historia | Como postulante, quiero filtrar las convocatorias por carrera, para encontrar rápido las búsquedas dirigidas a mi formación. |
| Módulo | Carreras |
| Requisitos relacionados | RF-29, RF-30 |

### Criterios de aceptación

1. En el listado de convocatorias puedo elegir una carrera de la lista de carreras activas.
2. El sistema muestra solo las convocatorias vigentes dirigidas a esa carrera.
3. Si no hay convocatorias para esa carrera, el sistema lo informa.
4. Puedo quitar el filtro y volver a ver todas las convocatorias vigentes.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | No | Necesita carreras (HU-07), convocatorias con carreras indicadas (HU-09) y el listado de convocatorias (HU-12). |
| Negociable | Sí | Se puede acordar si se filtra por una o por varias carreras a la vez. |
| Valiosa | Sí | Reduce el tiempo de búsqueda del postulante cuando hay muchas convocatorias. |
| Estimable | Sí | Es un filtro sobre un listado que ya existe. |
| Pequeña | Sí | Agrega un único filtro. |
| Verificable | Sí | Se prueba con dos convocatorias de carreras distintas y verificando que al filtrar aparece solo la que corresponde. |

---

# Módulo 4 — Convocatorias

## HU-09 — Crear una convocatoria

| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero crear una convocatoria laboral, para publicar una búsqueda de personal. |
| Módulo | Convocatorias |
| Requisitos relacionados | RF-10, RF-29, RF-33, RNF-06 |

### Criterios de aceptación

1. La empresa debe haber iniciado sesión.
2. Debe completar título, puesto, descripción, requisitos, ubicación, modalidad, fecha de inicio, fecha de finalización y al menos una carrera destinataria.
3. La fecha de finalización debe ser posterior a la de inicio; si no, el sistema lo informa y no guarda.
4. La convocatoria queda registrada a nombre de la empresa, con estado Vigente.
5. Una vez guardada, aparece entre las convocatorias disponibles para los postulantes.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Parcial | Requiere una cuenta de empresa (HU-05) y carreras cargadas (HU-07). |
| Negociable | Sí | Los campos opcionales (por ejemplo, el link externo) se pueden acordar. |
| Valiosa | Sí | Sin convocatorias el sistema no tiene nada que ofrecer a los postulantes. |
| Estimable | Sí | Campos y validaciones definidos. |
| Pequeña | Sí | Solo la creación; editar y cerrar son historias aparte (HU-10 y HU-11). |
| Verificable | Sí | Se prueba creando una convocatoria con fecha de fin anterior a la de inicio (se rechaza) y otra válida (aparece en el listado). |

---

## HU-10 — Editar una convocatoria propia

| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero editar mis convocatorias, para corregir o actualizar la información publicada. |
| Módulo | Convocatorias |
| Requisitos relacionados | RF-10, RF-32, RF-33 |

### Criterios de aceptación

1. La empresa solo ve la opción de editar en sus propias convocatorias.
2. Se aplican las mismas validaciones que al crearla.
3. Los cambios se reflejan para los postulantes en un máximo de 5 segundos.
4. Si intenta editar una convocatoria de otra empresa, el sistema lo impide.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Parcial | Requiere una convocatoria creada (HU-09). |
| Negociable | Parcial | Falta decidir si se pueden editar convocatorias que ya tienen postulantes, y qué campos. |
| Valiosa | Sí | Evita tener que cerrar y volver a crear una convocatoria por un error. |
| Estimable | Sí | Reutiliza el formulario y las validaciones de HU-09. |
| Pequeña | Sí | Al separarla de "cerrar", queda una sola operación. |
| Verificable | Sí | Se prueba editando una convocatoria propia y con una segunda empresa intentando editarla. |

---

## HU-11 — Cerrar una convocatoria

| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero cerrar una convocatoria, para dejar de recibir postulaciones cuando ya cubrí el puesto. |
| Módulo | Convocatorias |
| Requisitos relacionados | RF-20, RF-32, RF-34 |

### Criterios de aceptación

1. La empresa solo puede cerrar sus propias convocatorias.
2. El sistema pide confirmación antes de cerrar.
3. La convocatoria pasa a estado Cerrada y deja de aparecer entre las disponibles.
4. Las postulaciones existentes se conservan y la empresa puede seguir gestionando sus entrevistas.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Parcial | Requiere una convocatoria creada (HU-09). |
| Negociable | Sí | Se puede acordar si una convocatoria cerrada se puede volver a abrir. |
| Valiosa | Sí | Evita que lleguen postulaciones a un puesto ya cubierto. |
| Estimable | Sí | Es un cambio de estado con una regla clara. |
| Pequeña | Sí | Una sola acción. |
| Verificable | Sí | Se prueba cerrando una convocatoria e intentando postularse a ella con un postulante. |

---

## HU-12 — Ver las convocatorias disponibles

| Campo | Detalle |
|-------|---------|
| Historia | Como postulante, quiero ver las convocatorias vigentes y su detalle, para decidir a cuál postularme. |
| Módulo | Convocatorias |
| Requisitos relacionados | RF-11, RF-16, RF-34 |

### Criterios de aceptación

1. El sistema muestra solo las convocatorias en estado Vigente; las cerradas y vencidas no aparecen.
2. Cada convocatoria muestra título, empresa, ubicación, modalidad y fecha de finalización.
3. Al seleccionar una convocatoria, veo su detalle completo.
4. Si no hay convocatorias vigentes, el sistema lo informa.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Parcial | Necesita convocatorias creadas (HU-09) para tener algo que mostrar. |
| Negociable | Sí | El orden del listado y los datos visibles en cada tarjeta se pueden acordar. |
| Valiosa | Sí | Es el punto de entrada del postulante al sistema. |
| Estimable | Sí | Listado y detalle con datos definidos. |
| Pequeña | Sí | Solo consulta. |
| Verificable | Sí | Se prueba con una convocatoria vigente, una cerrada y una con fecha de fin pasada: solo aparece la primera. |

---

## HU-13 — Postularme a una convocatoria

| Campo | Detalle |
|-------|---------|
| Historia | Como postulante, quiero postularme a una convocatoria vigente, para participar en su proceso de selección. |
| Módulo | Convocatorias |
| Requisitos relacionados | RF-12, RF-13, RF-14, RF-15, RNF-03 |

### Criterios de aceptación

1. Debo haber iniciado sesión y tener un CV cargado; si no lo tengo, el sistema me lo informa y no registra la postulación.
2. La convocatoria debe estar Vigente.
3. Si ya me postulé a esa convocatoria, el sistema lo informa y no crea otra postulación.
4. La postulación se registra con la fecha del día, mi CV asociado automáticamente y estado Postulado.
5. El proceso no supera los 4 pasos desde que inicié sesión.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | No | No se puede probar sin un postulante registrado (HU-02), con CV (HU-03) y una convocatoria vigente (HU-09). |
| Negociable | Sí | La forma de confirmar y el mensaje final se pueden acordar. |
| Valiosa | Sí | Es la funcionalidad central del sistema para el postulante. |
| Estimable | Parcial | Reúne tres validaciones (CV, vigencia, duplicado); cada una suma esfuerzo. |
| Pequeña | Parcial | Es manejable, pero si se agrega cargar el CV dentro del mismo flujo, deja de serlo. |
| Verificable | Sí | Se prueba postulándose sin CV, a una convocatoria cerrada, dos veces a la misma y una vez correctamente. |

---

## HU-14 — Consultar el estado de mis postulaciones

| Campo | Detalle |
|-------|---------|
| Historia | Como postulante, quiero ver el estado y el resultado de mis postulaciones, para saber cómo avanza cada proceso. |
| Módulo | Convocatorias |
| Requisitos relacionados | RF-19, RF-34, RNF-02, RNF-07 |

### Criterios de aceptación

1. En "Mis postulaciones" veo solo mis postulaciones, con la convocatoria, la fecha y el estado.
2. Los estados posibles son Postulado, Entrevista programada, Aprobado o No aprobado, indicados con texto además de color.
3. Si la empresa registró el resultado, puedo verlo; si no, el sistema informa que aún no está disponible.
4. Los cambios de estado se reflejan en un máximo de 5 segundos.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Parcial | Requiere postulaciones registradas (HU-13); el resultado depende de HU-18. |
| Negociable | Sí | La forma de presentar el listado se puede acordar. |
| Valiosa | Sí | Resuelve el problema principal del proyecto: el postulante no sabía en qué quedaba su postulación. |
| Estimable | Sí | Los estados ya están definidos en RF-34. |
| Pequeña | Sí | Solo consulta; el detalle de la entrevista está en HU-17. |
| Verificable | Sí | Se prueba cambiando el estado desde la empresa y verificando que el postulante lo ve en menos de 5 segundos. |

---

## HU-15 — Ver los postulantes de mis convocatorias

| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero ver los postulantes de cada una de mis convocatorias y su CV, para evaluar los perfiles recibidos. |
| Módulo | Convocatorias |
| Requisitos relacionados | RF-17, RF-32 |

### Criterios de aceptación

1. La empresa elige una de sus convocatorias y ve la lista de postulantes con nombre, carrera, fecha de postulación y estado.
2. Puede abrir el CV de cada postulante.
3. Si la convocatoria no tiene postulantes, el sistema lo informa.
4. No puede ver postulantes de convocatorias de otra empresa.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | No | Necesita una convocatoria propia (HU-09) con postulaciones (HU-13). |
| Negociable | Sí | Se puede acordar si la lista se puede ordenar o filtrar por estado. |
| Valiosa | Sí | Es lo que la empresa necesita para elegir a quién entrevistar. |
| Estimable | Sí | Consulta con datos definidos más la apertura del CV. |
| Pequeña | Sí | Solo consulta; no incluye evaluar ni entrevistar. |
| Verificable | Sí | Se prueba con dos empresas: cada una ve solo los postulantes de sus convocatorias. |

---

# Módulo 5 — Entrevistas

## HU-16 — Programar una entrevista

| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero programar una entrevista con un postulante, para organizar las reuniones del proceso de selección. |
| Módulo | Entrevistas |
| Requisitos relacionados | RF-21, RF-32, RF-35, RF-36 |

### Criterios de aceptación

1. La entrevista se programa sobre una postulación existente de una convocatoria de la empresa.
2. Se deben indicar fecha, hora y modalidad (presencial o virtual).
3. El sistema impide una fecha y hora anteriores al momento actual.
4. Solo se permite una entrevista por postulación.
5. La entrevista queda en estado Programada y la postulación pasa a Entrevista programada.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | No | Requiere una postulación (HU-13) en una convocatoria de la empresa (HU-09). |
| Negociable | Parcial | Falta decidir si se controlan superposiciones de horario entre entrevistas de la misma empresa. |
| Valiosa | Sí | Ordena el proceso de selección dentro del sistema. |
| Estimable | Parcial | Depende de la decisión sobre superposiciones de horario. |
| Pequeña | Sí | Solo programar; reprogramar o cancelar quedan fuera. |
| Verificable | Sí | Se prueba con una fecha pasada (se rechaza), una válida y un segundo intento sobre la misma postulación (se rechaza). |

---

## HU-17 — Consultar mi entrevista

| Campo | Detalle |
|-------|---------|
| Historia | Como postulante, quiero ver la fecha, hora y modalidad de mi entrevista, para poder presentarme. |
| Módulo | Entrevistas |
| Requisitos relacionados | RF-22 |

### Criterios de aceptación

1. Al abrir una postulación con entrevista programada, veo fecha, hora, modalidad y la convocatoria correspondiente.
2. Si la postulación no tiene entrevista, el sistema muestra "Sin entrevista asignada".
3. Solo veo las entrevistas de mis propias postulaciones.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | No | Depende de que la empresa haya programado una entrevista (HU-16). |
| Negociable | Sí | Se puede acordar si además se avisa por correo. |
| Valiosa | Sí | Sin esta información el postulante no sabe cuándo presentarse. |
| Estimable | Sí | Consulta de pocos datos ya definidos. |
| Pequeña | Sí | Solo muestra la información. |
| Verificable | Sí | Se prueba con una postulación con entrevista y otra sin ella. |

---

## HU-18 — Registrar el resultado de una entrevista

| Campo | Detalle |
|-------|---------|
| Historia | Como empresa, quiero registrar el resultado de cada entrevista, para dejar constancia de la decisión y que el postulante la conozca. |
| Módulo | Entrevistas |
| Requisitos relacionados | RF-18, RF-19, RF-32, RF-36 |

### Criterios de aceptación

1. Solo se puede registrar el resultado de una entrevista Programada de una convocatoria propia.
2. La empresa ingresa un puntaje y el resultado: Aprobado o No aprobado.
3. La entrevista pasa a Realizada y la postulación toma el estado del resultado.
4. El postulante puede ver el resultado desde "Mis postulaciones".

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | No | Requiere una entrevista programada (HU-16). |
| Negociable | Parcial | Falta acordar la escala del puntaje y si se puede corregir un resultado ya registrado. |
| Valiosa | Sí | Cierra el proceso de selección dentro del sistema. |
| Estimable | Sí | Ya está definido que cambia dos estados (entrevista y postulación). |
| Pequeña | Parcial | Además de guardar el resultado actualiza dos estados; sigue siendo manejable, pero no es una sola operación. |
| Verificable | Sí | Se prueba registrando un resultado y verificando el estado de la entrevista, el de la postulación y lo que ve el postulante. |

---

## HU-19 — Consultar los resultados de los procesos

| Campo | Detalle |
|-------|---------|
| Historia | Como administrador, quiero consultar los resultados registrados, para supervisar cómo terminan los procesos de selección. |
| Módulo | Entrevistas |
| Requisitos relacionados | RF-37 |

### Criterios de aceptación

1. El administrador ve los resultados con postulante, convocatoria, empresa, puntaje y resultado.
2. Puede seleccionar un resultado para ver su detalle.
3. Si no hay resultados registrados, el sistema lo informa.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | No | Necesita resultados registrados (HU-18). |
| Negociable | Sí | Las columnas y el orden del listado se pueden acordar. |
| Valiosa | Parcial | Sirve para supervisar, pero se superpone en parte con los reportes (HU-20). |
| Estimable | Sí | Es un listado de datos ya existentes. |
| Pequeña | Sí | Solo consulta. |
| Verificable | Sí | Se prueba comparando el listado con los resultados cargados por las empresas. |

---

## HU-20 — Generar reportes

| Campo | Detalle |
|-------|---------|
| Historia | Como administrador, quiero generar reportes de convocatorias y entrevistas con filtros, para analizar cómo funciona la bolsa de trabajo. |
| Módulo | Entrevistas |
| Requisitos relacionados | RF-23 |

### Criterios de aceptación

1. El administrador elige el tipo de reporte: convocatorias o entrevistas.
2. Puede filtrar por período de fechas, empresa y carrera.
3. Si el período es inválido (fecha desde posterior a fecha hasta), el sistema lo informa.
4. Si no hay datos para los filtros elegidos, el sistema lo informa.
5. Los datos del reporte coinciden con los registros del sistema.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | No | Necesita convocatorias (HU-09) y entrevistas (HU-16) registradas. |
| Negociable | Parcial | Falta acordar qué columnas tiene cada reporte y si se puede exportar. |
| Valiosa | Sí | Permite a la institución medir el uso de la bolsa de trabajo. |
| Estimable | Parcial | Son dos reportes con tres filtros cada uno; se estima recién al definir su contenido. |
| Pequeña | No | Incluye dos reportes distintos. Conviene dividirla en un reporte de convocatorias y otro de entrevistas. |
| Verificable | Parcial | Se puede probar recién cuando estén definidas las columnas esperadas de cada reporte. |
