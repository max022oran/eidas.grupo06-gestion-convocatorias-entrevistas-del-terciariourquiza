# Definition of Ready (DoR)

_Antes de que una historia entre a desarrollo, tiene que pasar un filtro: el Definition of
Ready. Es un acuerdo del equipo sobre qué condiciones mínimas debe cumplir una historia para
considerarse "lista para trabajar". Si no las cumple, vuelve a refinamiento._

---

## Checklist del equipo

_Entre 6 y 10 ítems. Cada uno redactado como una condición verificable ("la historia tiene
criterios de aceptación escritos"), no como un deseo ("la historia está bien definida")._

| # | Ítem | Justificación (qué problema evita, máx. 3 renglones) |
|---|------|--------------------------------------------------------|
| 1 | La historia tiene establecida los roles de usuario y la funcionalidad que necesita. | Evita confusiones sobre quién utiliza la funcionalidad y qué necesita hacer. |
| 2 | La historia tiene criterios de aceptación escritos y verificables. | Permite comprobar objetivamente cuándo se considera cumplida. |
| 3 | La historia identifica los requisitos funcionales relacionados. | Evita desarrollar funcionalidades que no estén contempladas en los requisitos. |
| 4 | La historia tiene identificadas las reglas de negocio y validaciones necesarias. | Reduce errores y evita interpretaciones diferentes durante el desarrollo. |
| 5 | La historia tiene identificadas sus dependencias con otras funcionalidades. | Permite reconocer si necesita que otra funcionalidad esté disponible previamente. |
| 6 | La historia tiene un alcance claro y suficientemente pequeño para estimarse. | Evita historias demasiado grandes o difíciles de planificar dentro de una iteración. |

---

## Aplicación a tres historias propias

_Elijan TRES historias de usuario de su propio trabajo del primer semestre y pásenlas por su
propia checklist. Es esperable —y deseable— que alguna no pase._

### Historia 1 — Usuario se registra / HU-03

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
| 1. Rol y funcionalidad definidos | Sí | --- |
| 2. Criterios de aceptación escritos y verificables | Sí | --- |
| 3. Requisitos funcionales relacionados identificados | Sí | --- |
| 4. Reglas de negocio y validaciones identificadas | Sí | --- |
| 5. Dependencias identificadas | No | Especificar qué condiciones debe cumplir el usuario para registrarse y cómo se valida que el correo institucional no esté registrado previamente. |
| 6. Alcance claro y estimable | Sí | --- |

---

### Historia 2 — Usuario carga CV / HU-04

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
| 1. Rol y funcionalidad definidos | Sí | --- |
| 2. Criterios de aceptación escritos y verificables | Sí | --- |
| 3. Requisitos funcionales relacionados identificados | Sí | --- |
| 4. Reglas de negocio y validaciones identificadas | No | Especificar las validaciones del archivo, incluyendo el formato permitido, el tamaño máximo y qué sucede cuando el usuario ya tiene un CV cargado. |
| 5. Dependencias identificadas | No | | Aclarar si el usuario debe estar registrado e iniciar sesión antes de cargar o reemplazar su CV. |
| 6. Alcance claro y estimable | Sí | --- |

---

### Historia 3 — Empresa programa entrevistas / HU-07

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
| 1. Rol y funcionalidad definidos | Sí | --- |
| 2. Criterios de aceptación escritos y verificables | Sí | --- |
| 3. Requisitos funcionales relacionados identificados | Sí | --- |
| 4. Reglas de negocio y validaciones identificadas | No | Precisar las validaciones de fecha, hora y modalidad, y qué sucede si la postulación seleccionada no corresponde a una convocatoria de la empresa. |
| 5. Dependencias identificadas | No | Especificar que debe existir una postulación registrada antes de programar la entrevista. |
| 6. Alcance claro y estimable | Sí | --- |
