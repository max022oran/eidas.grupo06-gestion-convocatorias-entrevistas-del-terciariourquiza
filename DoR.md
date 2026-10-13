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
| 1 | La historia indica el rol que la usa y la funcionalidad que necesita, en formato "Como… quiero… para…". | Evita confusiones sobre quién utiliza la funcionalidad y para qué. |
| 2 | La historia tiene criterios de aceptación escritos, y cada uno se puede responder con sí o no al probarlo. | Permite comprobar objetivamente cuándo la historia está terminada. |
| 3 | La historia cita al menos un requisito funcional de `requisitos.md` y ese requisito existe. | Evita desarrollar funcionalidades que no estén contempladas en los requisitos y mantiene la trazabilidad. |
| 4 | Todas las reglas de negocio y validaciones que menciona tienen un valor definido (formatos, tamaños, estados, límites). | Evita que cada desarrollador interprete la regla a su manera ("tamaño máximo" sin número). |
| 5 | La historia nombra las historias o funcionalidades de las que depende. | Permite planificar el orden de desarrollo y saber qué tiene que existir antes para poder probarla. |
| 6 | El equipo puede estimarla y entra en una iteración: no quedan decisiones abiertas que cambien su tamaño. | Evita historias demasiado grandes o con decisiones pendientes que se descubren a mitad del desarrollo. |
| 7 | Al menos un criterio de aceptación describe un caso de error o excepción y la respuesta del sistema. | Evita probar solo el camino feliz y que los errores se definan recién al programar. |
| 8 | La historia indica qué requisitos no funcionales aplican (tiempo de respuesta, validación de formularios, accesibilidad). | Evita que los RNF se olviden porque no figuran en ninguna historia concreta. |

---

## Aplicación a tres historias propias

_Elijan TRES historias de usuario de su propio trabajo del primer semestre y pásenlas por su
propia checklist. Es esperable —y deseable— que alguna no pase._

### Historia 1 — Registrarme con mi correo institucional / HU-02

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
| 1. Rol y funcionalidad definidos | Sí | --- |
| 2. Criterios de aceptación verificables | Sí | --- |
| 3. Requisito funcional citado y existente | Sí | --- |
| 4. Reglas y validaciones con valor definido | Sí | --- |
| 5. Dependencias identificadas | Sí | --- |
| 6. Estimable y entra en una iteración | Sí | --- |
| 7. Caso de error en los criterios | Sí | --- |
| 8. RNF que aplican indicados | Sí | --- |

**Resultado:** pasa. Puede entrar a desarrollo una vez que esté hecha HU-07 (carreras), de la que depende.

_En la versión anterior esta historia no pasaba el ítem de dependencias. Se corrigió en
`historias-de-usuario.md`, que ahora indica que necesita carreras cargadas para el registro._

---

### Historia 2 — Cargar o reemplazar mi CV / HU-03

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
| 1. Rol y funcionalidad definidos | Sí | --- |
| 2. Criterios de aceptación verificables | Sí | --- |
| 3. Requisito funcional citado y existente | Sí | --- |
| 4. Reglas y validaciones con valor definido | Sí | --- |
| 5. Dependencias identificadas | Sí | --- |
| 6. Estimable y entra en una iteración | Sí | --- |
| 7. Caso de error en los criterios | Sí | --- |
| 8. RNF que aplican indicados | No | No cita ningún RNF. Le aplica RNF-06 (mensaje de error específico antes de enviar) y falta acordar un tiempo máximo de carga para un PDF de 5 MB. |

**Resultado:** no pasa. Vuelve a refinamiento para agregar los RNF; el resto está completo.

_En la versión anterior no pasaba el ítem de reglas y validaciones (faltaban formato, tamaño
y reemplazo). Eso se resolvió: PDF de hasta 5 MB y confirmación antes de reemplazar._

---

### Historia 3 — Programar una entrevista / HU-16

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
| 1. Rol y funcionalidad definidos | Sí | --- |
| 2. Criterios de aceptación verificables | Sí | --- |
| 3. Requisito funcional citado y existente | Sí | --- |
| 4. Reglas y validaciones con valor definido | No | No está decidido qué pasa si la empresa programa dos entrevistas en el mismo horario. Hay que definir si el sistema lo impide, avisa o lo permite. |
| 5. Dependencias identificadas | Sí | --- |
| 6. Estimable y entra en una iteración | No | Mientras no se decida lo de la superposición de horarios, el tamaño cambia: controlarla agrega una validación más sobre las entrevistas existentes. |
| 7. Caso de error en los criterios | Sí | --- |
| 8. RNF que aplican indicados | No | No cita RNF-02: el postulante debe ver la entrevista programada en un máximo de 5 segundos. |

**Resultado:** no pasa. Vuelve a refinamiento: la decisión sobre la superposición de horarios la tiene que tomar la institución con las empresas, no el equipo de desarrollo.
