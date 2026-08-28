# Requisitos del sistema

## Descripción del sistema

_Describir brevemente el sistema, el problema que resuelve y el contexto en el que opera._

## Requisitos funcionales

_Agrupar por módulo o área funcional._

### Módulo 1 — Usuarios

| ID | Requisito |
|----|-----------|
| RF-01 |El sistema permitirá crear usuarios internos |
| RF-02 |El sistema permitirá autenticar a cada empleado mediante usuario y contraseña|
| RF-03 |El sistema permitirá asignar un rol a cada usuario interno al momento de su creación. |
| RF-04 | El sistema contará con los siguientes roles predefinidos: Administrador, Ventas, Depósito y Logística|
| RF-05 |El sistema permitirá al Administrador gestionar usuarios internos (crear, modificar, desactivar, asignar roles). |
| RF-06 | El sistema deberá registrar qué usuario realizó cada modificación.|
| RF-07 |El sistema permitirá al usuarios con rol Administrador consultar el historial de modificaciones filtrado por fecha, usuario y entidad afectada. |

### Módulo 2 — Clientes y Cuentas

| ID | Requisito |
|----|-----------|
| RF-08 | El sistema permitirá que un cliente se registre proporcionando los siguientes datos obligatorios: nombre, apellido, email, fecha de nacimiento, teléfono, DNI, contraseña, dirección, código postal, ciudad y provincia.|
| RF-09 |El sistema validará que el email ingresado tenga formato válido |
| RF-10 | El sistema validará que el DNI ingresado tenga formato válido|
| RF-11 | El sistema impedirá el registro de un cliente con un email ya existente en la base de datos.|
| RF-12 |El sistema permitirá al cliente iniciar sesión mediante email y contraseña. |
| RF-13 |El sistema permitirá al cliente recuperar su contraseña mediante un enlace enviado a su email registrado. |
| RF-14 |El sistema permitirá al cliente consultar sus datos personales desde la sección "Mi Cuenta". |
| RF-15 |El sistema permitirá al cliente modificar sus datos personales y de contacto (excepto DNI). |
| RF-16 |El sistema permitirá al cliente consultar su historial de compras desde "Mi Cuenta". |
| RF-17 | El sistema permitirá al cliente consultar el estado actualizado de sus pedidos desde "Mi Cuenta".|
| RF-18 | El sistema permitirá al cliente solicitar devoluciones desde "Mi Cuenta" para pedidos que cumplan los plazos establecidos.|
| RF-19 | El sistema permitirá al personal autorizado (Ventas y Administrador) consultar el listado completo de clientes registrados con sus datos.|
| RF-20 |El sistema permitirá al personal autorizado (Ventas y Administrador) buscar clientes por nombre, email o DNI. |
| RF-21 | El sistema permitirá que los clientes que hayan comprado un producto puedan calificarlo con una puntuación de 1 a 5 estrellas y un comentario opcional.|
| RF-22 |El sistema permitirá al Administrador eliminar reseñas de clientes que contengan lenguaje inapropiado |
| RF-23 | El sistema registrará la fecha y hora del registro de cada cliente.|


### Módulo 3 — Catalogo y Productos

| ID | Requisito |
|----|-----------|
| RF-24 | El sistema permitirá consultar el catálogo de productos sin necesidad de registrarse ni iniciar sesión|
| RF-25 | El sistema mostrará para cada producto al menos los siguientes atributos: descripción, precio, color, talle y disponibilidad por variante.|
| RF-26 | El sistema permitirá asociar entre 2 y 4 fotografías a cada producto.|
| RF-27 | El sistema diferenciará las variantes de cada producto según combinación de talle y color.|
| RF-28 |El sistema mostrará una tabla de medidas específica para cada tipo de producto. |
| RF-29 |El sistema permitirá al Administrador cargar nuevos productos al catálogo. |
| RF-30 | El sistema permitirá al Administrador modificar la información de productos existentes (descripción, precio, imágenes, tabla de medidas).|
| RF-31 | El sistema permitirá al Administrador desactivar temporalmente un producto sin eliminarlo del catálogo.|
| RF-32 | Cuando una variante de producto alcance stock cero, el producto permanecerá visible en el catálogo indicando "Sin stock".|
| RF-33 | El sistema impedirá que una variante con stock cero sea agregada al carrito de compras.|
| RF-34 |El sistema permitirá al cliente filtrar productos por categoría, precio, talle, color y disponibilidad. |
| RF-35 | El sistema permitirá al cliente ordenar productos por precio (ascendente/descendente), popularidad y novedad.|

### Módulo 4 — Inventario y Stock

| ID | Requisito |
|----|-----------|
| RF-36 |El sistema mantendrá el stock disponible para cada combinación única de producto, talle y color. |
| RF-37 |El sistema permitirá consultar la disponibilidad de cada variante en tiempo real. |
| RF-38 | El sistema unificará el stock entre ventas online y ventas realizadas en el local físico|
| RF-39 | El sistema registrará un historial completo de movimientos de stock.|
| RF-40 | El sistema registrará en el historial de movimientos los siguientes campos obligatorios: fecha, producto, cantidad, tipo de movimiento e ID de pedido asociado.|
| RF-41 |El sistema contemplará los siguientes tipos de movimiento de stock: venta, devolución, ingreso de mercadería y cancelación de pedido. |
| RF-42 | El sistema descontará el stock de las variantes correspondientes solo cuando el pago de una venta online sea aprobado.|
| RF-43 |El sistema dirigirá las alertas de bajo stock a Depósito mediante notificación en el panel y por email. |
| RF-44 |El sistema permitirá a Depósito registrar el ingreso de nueva mercadería. |
| RF-45 |El sistema registrará en cada ingreso de mercadería los siguientes campos obligatorios: tipo de artículo, nombre del proveedor, contacto, cantidad ingresada, ID de producto, fecha de ingreso y precio de costo unitario. |
| RF-46 |El sistema permitirá al Administrador y a Depósito consultar el historial de movimientos de stock filtrado por fecha, producto, tipo de movimiento y usuario. |
| RF-47 |El sistema permitirá al rol Ventas consultar el stock disponible de cualquier variante. |
| RF-48 | El sistema permitirá al rol Depósito consultar el stock disponible de cualquier variante.|
| RF-49 | El sistema permitirá al rol Depósito actualizar el stock (ingresos, egresos)|



| RF- | |
| RF- | |
| RF- | |
| RF- | |
| RF- | |
| RF- | |
| RF- | |
| RF- | |
| RF- | |
| RF- | |
| RF- | |
| RF- | |


### Módulo 2 — [Nombre]

| ID | Requisito |
|----|-----------|
| RF-03 | |

## Requisitos no funcionales

### Rendimiento y disponibilidad

| ID | Requisito |
|----|-----------|
| RNF-01 | |

### Seguridad y usabilidad

| ID | Requisito |
|----|-----------|
| RNF-02 | |
