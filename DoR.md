# Definition of Ready (DoR)

_Antes de que una historia entre a desarrollo, tiene que pasar un filtro: el Definition of
Ready. Es un acuerdo del equipo sobre qué condiciones mínimas debe cumplir una historia para
considerarse "lista para trabajar". Si no las cumple, vuelve a refinamiento._

---

## Checklist del equipo

_8 ítems, tomados de la checklist que compartió la cátedra en
`DoR — Dos ejemplos resueltos — 3°1°`, en formato sí/no verificable._

| # | Ítem | Justificación (qué problema evita) |
|---|------|--------------------------------------------------------|
| 1 | ¿Tiene al menos 2 criterios de aceptación verificables (se responde sí/no sin discutir)? | Sin criterios objetivos no hay forma de acordar cuándo la historia está terminada. |
| 2 | ¿El actor/rol está identificado sin ambigüedad? | Evita errores de permisos y de diseño de pantallas para el rol equivocado. |
| 3 | ¿Hay al menos un flujo alternativo o excepción documentado en la propia historia? | Evita que los casos borde (errores, límites) aparezcan recién durante el desarrollo. |
| 4 | ¿Están listadas las dependencias con otras historias o módulos? | Evita empezar a desarrollar algo que no se puede probar hasta que exista lo que depende. |
| 5 | ¿Hay al menos un requisito no funcional relevante asociado a esta historia puntual? | Evita que un RNF genérico del proyecto quede sin cumplirse en la práctica. |
| 6 | ¿El equipo puede estimar el esfuerzo sin preguntas abiertas de diseño? | Evita estimar a ciegas y tener que rehacer la estimación después. |
| 7 | ¿Están especificados los datos de entrada/salida necesarios? | Evita que cada desarrollador defina el formulario o la salida a su criterio. |
| 8 | ¿Hay una forma concreta de verificar que la historia está terminada? | Evita que el cierre de la historia quede a juicio subjetivo de quien la revisa. |

---

## Aplicación a tres historias propias

_Las tres historias corresponden al propio proyecto (Sistema de e-commerce Mundo Sport). La
Historia 1 ya está redactada en `docs/historias-de-usuario.md`; las Historias 2 y 3 se
construyeron para este ejercicio a partir de requisitos funcionales ya relevados. Es
esperable —y deseable— que alguna no pase._

### Historia 1 — HU-01: Crear usuario interno

> Como Administrador, quiero crear usuarios internos y asignarles un rol, para permitir que
> los empleados accedan al sistema según sus responsabilidades. (RF-01, RF-03, RF-04)

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
| 1 | Sí | Tiene 4 criterios de aceptación numerados en `docs/historias-de-usuario.md`. |
| 2 | Sí | Actor "Administrador" identificado sin ambigüedad. |
| 3 | **No** | Ningún criterio contempla qué pasa si falta un dato obligatorio o si el usuario ya existe. |
| 4 | **No** | No declara que necesita que ya exista un Administrador previo para poder ejecutarse (ningún RF cubre la creación del primer usuario del sistema). |
| 5 | Sí | RNF-01 (tiempo de respuesta) y RNF-04 (solo Administrador puede crear usuarios) la referencian puntualmente. |
| 6 | **No** | No están definidos los campos exactos del formulario de alta. |
| 7 | **No** | Sin campos de entrada enumerados ni formato de salida especificado. |
| 8 | Sí | El sistema informa al Administrador si el usuario fue creado correctamente. |

---

### Historia 2 — Aplicar cupón de descuento en el carrito

> Como Cliente, quiero aplicar un cupón de descuento en mi carrito, para pagar menos por mi
> compra. (RF-116, RF-117, RF-118)

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
| 1 | **No** | No tiene ningún criterio de aceptación redactado. |
| 2 | Sí | Actor "Cliente" identificado sin ambigüedad. |
| 3 | **No** | No contempla cupón vencido, sin usos disponibles, o intento de aplicar un segundo cupón. |
| 4 | Parcial | Depende de "Crear un cupón de descuento" (ya existe como HU-09), pero esta historia no la menciona. |
| 5 | **No** | Ningún RNF está vinculado puntualmente a la aplicación de cupones. |
| 6 | **No** | Mezcla validar el cupón, calcular el descuento y actualizar el resumen sin desglosar. |
| 7 | **No** | No especifica el dato de entrada (código del cupón) ni cómo se muestra el descuento aplicado. |
| 8 | **No** | No hay ningún criterio de terminado definido. |

---

### Historia 3 — Consultar estado de pedido desde "Mi Cuenta"

> Como Cliente, quiero consultar el estado actual de mis pedidos desde "Mi Cuenta", para saber
> en qué etapa se encuentra mi compra sin tener que contactar a la tienda. (RF-72, RF-75)

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
| 1 | Sí | Los estados posibles (RF-75) y la fecha del último cambio (RF-78) ya están definidos, lo que permite escribir criterios de aceptación concretos. |
| 2 | Sí | Actor "Cliente" identificado sin ambigüedad. |
| 3 | Sí | Contempla el caso del Cliente sin pedidos registrados. |
| 4 | Sí | Depende de RF-75 y RF-78, ya relevados y cerrados en el mismo módulo. |
| 5 | **No** | Ningún RNF de tiempo de respuesta está asociado a esta consulta puntual. |
| 6 | Sí | El conjunto de estados y datos ya está cerrado, sin preguntas de diseño abiertas. |
| 7 | Sí | Entrada: ninguna. Salida: estado actual, fecha del último cambio, mensaje si no hay pedidos. |
| 8 | Sí | Se puede comprobar que el estado mostrado coincide con el registrado en la base. |
