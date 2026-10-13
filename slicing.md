# Ejercicio: partir una épica en slices verticales

## La épica

> Como usuario/postulante, quiero postularme a las convocatorias de la bolsa de trabajo y
> seguir mi proceso de selección, para conseguir un empleo sin tener que averiguar por fuera
> del sistema en qué quedó cada búsqueda.

_Así como está, es una épica gorda: no se puede estimar, no se puede terminar en una
iteración, y esconde decisiones que nadie tomó todavía (¿qué pasa si no tengo CV?, ¿cuándo veo el resultado?, ¿qué CV ve la empresa si lo reemplazo?)._

---

## Parte A — Historias verticales

_Cada historia, sola, entrega algo usable de punta a punta: pantalla, validación y dato
guardado. Están ordenadas en el orden en que conviene construirlas: la primera es la
postulación mínima que ya sirve, y cada una de las siguientes suma una capacidad nueva._

### Historia 1 — Postularme a una convocatoria vigente con mi CV ya cargado

| Campo | Detalle |
|-------|---------|
| Historia | Como postulante con CV cargado, quiero postularme a una convocatoria vigente, para participar en su proceso de selección. |
| Requisitos relacionados | RF-12, RF-13, RF-14, RNF-03 |

**Criterios de aceptación**

1. Si la convocatoria está vigente y tengo un CV cargado, al confirmar se registra la postulación con la fecha del día y mi CV asociado automáticamente, en no más de 4 pasos desde que inicié sesión.
2. Al terminar, el sistema muestra un mensaje de confirmación con el título de la convocatoria y la empresa.

---

### Historia 2 — Cargar mi CV en el momento de postularme

| Campo | Detalle |
|-------|---------|
| Historia | Como postulante sin CV cargado, quiero poder subirlo desde la misma pantalla de postulación, para no perder la convocatoria que me interesa. |
| Requisitos relacionados | RF-09, RF-13 |

**Criterios de aceptación**

1. Si intento postularme sin CV, el sistema me informa que necesito cargarlo y me ofrece subir un PDF ahí mismo; una vez cargado, puedo confirmar la postulación sin volver a buscar la convocatoria.
2. Si el archivo no es PDF o supera el tamaño máximo permitido, el sistema lo rechaza con un mensaje específico y la postulación no se registra.
   
---
### Historia 3 — Ver mis postulaciones y su estado

| Campo | Detalle |
|-------|---------|
| Historia | Como postulante, quiero ver la lista de convocatorias a las que me postulé con su estado, para saber cómo avanza cada proceso. |
| Requisitos relacionados | RF-19, RNF-02 |

**Criterios de aceptación**

1. En "Mis postulaciones" veo solo mis postulaciones, cada una con el título de la convocatoria, la fecha en que me postulé y su estado actual.
2. Cuando la empresa cambia el estado de una postulación, el cambio se refleja en mi lista en un máximo de 5 segundos.

---

### Historia 4 — Ver la entrevista que me asignaron

| Campo | Detalle |
|-------|---------|
| Historia | Como postulante, quiero ver la fecha, hora y modalidad de la entrevista que me programaron, para poder presentarme. |
| Requisitos relacionados | RF-21, RF-22 |

**Criterios de aceptación**

1. Si la empresa programó una entrevista para una de mis postulaciones, al abrir esa postulación veo la fecha, la hora y la modalidad.
2. Si todavía no hay entrevista programada, el sistema informa "Sin entrevista asignada" en lugar de dejar el dato vacío.

---

### Historia 5 — Ver el resultado de mi postulación

| Campo | Detalle |
|-------|---------|
| Historia | Como postulante, quiero ver el resultado de mi postulación cuando la empresa lo registra, para saber si avanzo o no en el proceso. |
| Requisitos relacionados | RF-18, RF-19 |

**Criterios de aceptación**

1. Cuando la empresa registra el resultado de mi entrevista, la postulación muestra ese resultado y su estado se actualiza.
2. Si el resultado todavía no fue registrado, el sistema informa que aún no está disponible.

---

### Historia 6 — Reemplazar mi CV

| Campo | Detalle |
|-------|---------|
| Historia | Como postulante, quiero reemplazar mi CV por una versión actualizada, para que las empresas vean mi información más reciente. |
| Requisitos relacionados | RF-09, RF-14 |

**Criterios de aceptación**

1. Si ya tengo un CV cargado y subo uno nuevo, el sistema me pide confirmar el reemplazo antes de guardarlo.
2. Una vez confirmado, el CV nuevo queda como el único vigente y es el que ven las empresas, tanto en las postulaciones nuevas como en las ya realizadas (un único CV vigente por usuario, según la decisión 3 del modelo ER).

---

## Parte B — Los caminos que no salen bien

_Elegimos la Historia 1. Adaptamos las preguntas de la billetera a nuestro sistema: el
"saldo insuficiente" es no tener CV, el "destinatario dado de baja" es la convocatoria
cerrada, y el "descuento sin acreditación" es la postulación guardada sin su CV._

**Historia elegida:** Historia 1 — Postularme a una convocatoria vigente con mi CV ya cargado

| Pregunta | Qué hace el sistema | Quién decide (analista / negocio / técnica) |
|----------|----------------------|-----------------------------------------------|
| ¿Qué pasa si el postulante no tiene un CV cargado? | No muestra la confirmación: informa que debe cargar un CV antes de postularse y no registra nada (la carga en el mismo flujo es la Historia 2). | **Negocio:** decide que el CV es obligatorio para postularse (RF-13). **Analista:** define el mensaje y en qué paso se valida. |
| ¿Qué pasa si la convocatoria vence o la empresa la cierra mientras el postulante está postulándose? | Vuelve a validar el estado de la convocatoria al confirmar. Si ya no está vigente, rechaza la postulación e informa que la convocatoria no acepta nuevas postulaciones. | **Negocio:** decide que una convocatoria cerrada no admite postulaciones aunque el usuario ya haya empezado (RF-20). **Analista:** define la revalidación al confirmar. |
| ¿Qué pasa si el sistema registra la postulación pero falla antes de asociarle el CV? | La postulación y la asociación del CV se guardan como una única operación: o se guardan las dos o ninguna. Si falla, no queda una postulación sin CV y se informa al postulante que vuelva a intentarlo. | **Técnica:** cómo garantizar que la operación sea atómica. **Analista:** exige que nunca exista una postulación sin CV y define el mensaje. |
| ¿Qué pasa si el postulante aprieta "Postularme" dos veces? | El botón se deshabilita apenas se presiona, y el sistema no permite dos postulaciones del mismo usuario a la misma convocatoria: el segundo pedido no crea otra, y se muestra la confirmación de la primera. | **Negocio:** decide que hay una sola postulación por usuario y convocatoria (RF-15). **Técnica:** el control en la base de datos que lo garantiza. |
| ¿Qué pasa si se cae la conexión justo después de confirmar? | La postulación se resuelve en el servidor aunque se corte la conexión. Al volver, el postulante ve en "Mis postulaciones" si quedó registrada; si intenta postularse de nuevo y ya existía, el sistema le informa que ya está postulado en lugar de dar un error. | **Técnica:** que la operación no dependa de la conexión del cliente. **Analista:** define que "Mis postulaciones" sea el lugar para verificar y el mensaje de "ya estás postulado". |

---

## Parte C — Defensa

_Se hace oral, en el plenario. No se documenta en este archivo._
