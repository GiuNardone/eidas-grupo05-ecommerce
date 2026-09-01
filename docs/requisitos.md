# Requisitos del sistema

## Descripción del sistema

El sistema consiste en una plataforma de comercio electrónico para la tienda de indumentaria Mundo Sport, ubicada en Rosario. Actualmente, el negocio realiza sus ventas de manera presencial y mediante redes sociales, pero no cuenta con un canal de venta online propio. Esta modalidad genera problemas de gestión manual de pedidos, falta de control de stock en tiempo real, dificultades en el seguimiento de ventas y devoluciones, y una experiencia de compra limitada para los clientes. 

La solución plantea digitalizar y centralizar estos procesos, permitiendo administrar la información del negocio desde una única plataforma y mantener actualizado el inventario tanto del local físico como de la tienda online de forma sincronizada, ofreciendo a los clientes un catálogo organizado donde podrán seleccionar los artículos que desean comprar, utilizar un carrito de compras, realizar pagos de forma segura y consultar el estado de sus pedidos. 

Por otro lado, el personal de la tienda contará con un panel administrativo desde el cual podrá gestionar productos, stock, pedidos, ventas y devoluciones. El sistema también contará con autenticación y distintos roles de acceso para el personal. De esta manera, se busca mejorar la organización interna del negocio, garantizando una experiencia ágil tanto para el comprador como para el equipo de trabajo. 


## Requisitos funcionales


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

### Módulo 5 — Carrito de Compras

| ID | Requisito |
|----|-----------|
| RF-50 | El sistema exigirá que el cliente seleccione talle y color antes de agregar un producto al carrito.|
| RF-51 | El sistema permitirá agregar productos al carrito de compras.|
| RF-52 |El sistema permitirá visualizar los productos agregados al carrito con detalle de variante, cantidad y precio unitario |
| RF-53 | El sistema permitirá modificar la cantidad de cada producto en el carrito.|
| RF-54 | El sistema permitirá eliminar productos del carrito de forma individual.|
| RF-55 |El sistema permitirá vaciar completamente el carrito en un solo paso. |
| RF-56 | El sistema verificará nuevamente la disponibilidad de stock de cada variante antes de confirmar el pedido.|
| RF-57 |El sistema mostrará el resumen completo del pedido con productos, variantes, cantidades, subtotal, costo de envío y total final. |
| RF-58 |El sistema reservará los productos agregados al carrito durante un período de 24 horas |
| RF-59 | El sistema liberará automáticamente los productos reservados y vaciará el carrito si transcurren más de 24 horas sin finalizar la compra.|


### Módulo 6 — Pedidos y Pagos

| ID | Requisito |
|----|-----------|
| RF-60 |El sistema exigirá que el cliente esté registrado y autenticado para finalizar una compra. |
| RF-61 |El sistema solicitará al cliente la confirmación de los datos de entrega durante el proceso de checkout. |
| RF-62 |El sistema calculará y aplicará automáticamente el costo correspondiente al método de entrega seleccionado.|
| RF-63 | El sistema no generará costo de envío cuando el cliente seleccione "Retiro en el local".|
| RF-64 | El sistema permitirá pagar mediante tarjeta de crédito y tarjeta de débito.|
| RF-65 | El sistema se integrará con la pasarela de pagos Mercado Pago.|
| RF-66 | El sistema registrará en cada transacción: estado del pago, fecha, importe y medio de pago utilizado.|
| RF-67 | El sistema notificará al cliente cuando un pago sea rechazado, indicando que puede reintentar.|
| RF-68 | El sistema mantendrá el pedido en estado "Pendiente de pago" si la transacción queda en estado pendiente.|
| RF-69 |El sistema confirmará el pedido y descontará el stock cuando el pago sea aprobado. |
| RF-70 |El sistema generará un número de pedido único al confirmarse la compra. |
| RF-71 |El pedido generado registrará: productos, variantes, cantidades, precios, datos del cliente, medio de pago, total y método de entrega. |
| RF-72 | El sistema permitirá al cliente consultar el estado de sus pedidos desde "Mi Cuenta".|
| RF-73 |El sistema permitirá al cliente cancelar un pedido siempre que no haya sido enviado o retirado. |
| RF-74 | El sistema generará una nota de crédito cuando un pedido sea cancelado y el pago haya sido aprobado.|
| RF-75 | El sistema gestionará los siguientes estados de pedido: "Pendiente de pago", "Pago aprobado", "En preparación", "Listo para retirar" / "Enviado", y "Entregado" / "Retirado".|
| RF-76 | El sistema notificará al cliente mediante email y notificación en su cuenta por cada cambio de estado del pedido.|
| RF-77 | El sistema permitirá a Ventas actualizar manualmente el estado de un pedido cuando corresponda.|
| RF-78 | El sistema registrará la fecha y hora de cada cambio de estado del pedido.|


### Módulo 7 — Envíos y Retiros

| ID | Requisito |
|----|-----------|
| RF-79 | El sistema procesará los pedidos según el método de entrega seleccionado por el cliente. |
| RF-80 | El sistema permitirá al cliente seleccionar entre envío a domicilio y retiro en el local durante el checkout. |
| RF-81 | El sistema se integrará con el proveedor logístico para obtener automáticamente el número de seguimiento del envío. |
| RF-82 | El sistema permitirá al rol Logística registrar la empresa de envío utilizada. |
| RF-83 | El sistema permitirá al empleado del local confirmar en el sistema que el cliente retiró su pedido. |
| RF-84 | El sistema registrará la fecha y hora de retiro confirmado. |
| RF-85 | El sistema contemplará un plazo máximo de 15 días corridos para que el cliente retire el pedido en el local. |
| RF-86 | El sistema notificará al cliente 3 días antes del vencimiento del plazo de retiro (día 12). |
| RF-87 | El sistema notificará al cliente el día de vencimiento del plazo de retiro (día 15). |
| RF-88 | El sistema permitirá al cliente consultar el número de seguimiento de su envío desde "Mi Cuenta". |


### Módulo 8 — Devoluciones y Cambios

| ID | Requisito |
|----|-----------|
| RF-89 | El sistema permitirá al cliente solicitar una devolución desde la sección "Mi Cuenta". |
| RF-90 | El sistema permitirá al cliente seleccionar el pedido asociado a la devolución entre sus pedidos finalizados. |
| RF-91 | El sistema permitirá al cliente indicar el motivo de la devolución. |
| RF-92 | El sistema contemplará los siguientes motivos de devolución: talle incorrecto, producto defectuoso y producto equivocado. |
| RF-93 | El sistema permitirá al cliente agregar comentarios adicionales y fotografías adjuntas a la solicitud de devolución. |
| RF-94 | El sistema validará que la solicitud de devolución se realice dentro de los 5 días hábiles posteriores a la fecha de entrega o retiro del pedido. |
| RF-95 | El sistema impedirá solicitar devoluciones fuera del plazo establecido. |
| RF-96 | El sistema gestionará los siguientes estados de devolución: "Solicitada", "En revisión", "Aprobada", "Rechazada" y "Finalizada". |
| RF-97 | El sistema informará al cliente que la resolución consistirá en un cambio de producto o en la generación de una nota de crédito. |
| RF-98 | El sistema permitirá al rol Ventas visualizar, revisar y resolver las solicitudes de devolución. |
| RF-99 | El sistema notificará al cliente por email y en su cuenta cada cambio de estado de su solicitud de devolución. |
| RF-100 | El sistema registrará la fecha y hora de cada cambio de estado de la devolución. |
| RF-101 | El sistema generará una nota de crédito automática cuando una devolución sea aprobada y no se realice cambio. |
| RF-102 | El sistema registrará el ingreso al stock de los productos devueltos cuando la devolución sea aprobada. |


### Módulo 9 — Promociones y Cupones

| ID | Requisito |
|----|-----------|
| RF-103 | El sistema permitirá crear promociones basadas en descuentos porcentuales. |
| RF-104 | El sistema permitirá crear promociones basadas en descuentos fijos.|
| RF-105 | El sistema permitirá aplicar promociones a un producto específico. |
| RF-106 | El sistema permitirá aplicar promociones a una categoría completa de productos.|
| RF-107 | El sistema permitirá aplicar promociones a todo el catálogo|
| RF-108 | El sistema permitirá crear cupones de descuento. |
| RF-109 | El sistema permitirá configurar en cada cupón una fecha de inicio y una fecha de finalización. |
| RF-110 | El sistema permitirá configurar en cada promoción una fecha de inicio y una fecha de finalización. |
| RF-111 | El sistema permitirá configurar cupones como de uso múltiple (varios clientes, varias veces). |
| RF-112 | El sistema permitirá configurar un límite de usos totales para cupones múltiples. |
| RF-113 | El sistema activará las promociones y cupones en su fecha de inicio configurada. |
| RF-114 | El sistema desactivará automáticamente las promociones y cupones en su fecha de finalización configurada. |
| RF-115 | El sistema permitirá al Administrador activar o desactivar manualmente cualquier promoción o cupón. |
| RF-116 | El sistema validará que un cupón sea válido (vigente y con usos disponibles) antes de aplicarlo al carrito. |
| RF-117 | El sistema impedirá la aplicación de cupones vencidos o sin usos disponibles. |
| RF-118 | El sistema permitirá que un cliente aplique un solo cupón por pedido. |




### Módulo 10 — Proveedores

| ID | Requisito |
|----|-----------|
| RF-119 | El sistema permitirá registrar proveedores. |
| RF-120 | El sistema almacenará de cada proveedor los siguientes datos obligatorios: razón social, CUIT, teléfono, email y dirección. |
| RF-121 | El sistema permitirá modificar los datos de un proveedor existente. |
| RF-122 | El sistema permitirá eliminar proveedores. |
| RF-123 | El sistema permitirá asociar cada producto con uno o más proveedores. |
| RF-124 | El sistema permitirá consultar todos los productos asociados a un proveedor específico. |
| RF-125 | El sistema permitirá al rol Depósito y Administrador registrar ingresos de mercadería asociados a un proveedor. |
| RF-126 | El sistema permitirá al Administrador consultar el historial de ingresos de mercadería por proveedor. |



### Módulo 11 — Notificaciones

| ID | Requisito |
|----|-----------|
| RF-127 | El sistema enviará notificaciones por email para: confirmación de registro, recuperación de contraseña, confirmación de pedido, cambio de estado de pedido, alerta de bajo stock y resolución de devolución|
| RF-128 | El sistema mostrará notificaciones en el panel del cliente para: cambio de estado de pedido, recordatorio de retiro y resolución de devolución. |
| RF-129 | El sistema mostrará notificaciones en el panel del empleado para: alertas de bajo stock y nuevas solicitudes de devolución.|
| RF-130 | El sistema registrará el envío de cada notificación con fecha y hora. |


### Módulo 12 — Reportes de Ventas

| ID | Requisito |
|----|-----------|
| RF-131 | El sistema permitirá consultar ventas agrupadas por día, semana, mes y año. |
| RF-132 | El sistema permitirá consultar las ventas de períodos anteriores hasta 5 años atrás. |
| RF-133 | El sistema permitirá filtrar los reportes de ventas por rango de fechas personalizado. |
| RF-134 | El sistema permitirá filtrar los reportes de ventas por producto o categoría. |
| RF-135 | El sistema mostrará el listado de productos más vendidos en un período seleccionado. |
| RF-136 | El sistema mostrará el listado de productos con menor movimiento en un período seleccionado. |
| RF-137 | El sistema mostrará el total de ingresos en un período seleccionado. |
| RF-138 | El sistema mostrará las ventas distinguidas según el medio de pago utilizado. |
| RF-139 | El sistema mostrará la cantidad de ventas totales en un período seleccionado. |
| RF-140 | El sistema permitirá exportar todos los reportes en formato Excel. |
| RF-141 | El sistema permitirá al Administrador programar la generación de reportes periódicos (diarios, semanales, mensuales). |



### Módulo 13 — Panel de Administración

| ID | Requisito |
|----|-----------|
| RF-142 | El sistema deberá poseer un panel de administración que mostrará un dashboard con indicadores clave de actividad de la tienda. |
| RF-143 | El dashboard mostrará el número de clientes nuevos registrados en los últimos 7 días. |
| RF-144 | El dashboard mostrará el número de clientes recurrentes (con más de una compra). |
| RF-145 | El dashboard mostrará el total de ventas del día actual. |
| RF-146 | El dashboard mostrará el total de ventas de la semana actual. |
| RF-147 | El dashboard mostrará el total de ventas del mes actual. |
| RF-148 | El dashboard mostrará el número de pedidos pendientes de preparación. |
| RF-149 | El dashboard mostrará el número de pedidos pendientes de envío. |
| RF-150 | El dashboard mostrará el número de solicitudes de devolución pendientes de revisión. |



### Módulo 2 — [Nombre]

| ID | Requisito |
|----|-----------|
| RF-03 | | 





## Requisitos no funcionales

### Rendimiento y disponibilidad

| ID     | Requisito                                                                                                                                                                          |
| ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| RNF-01 | El sistema deberá procesar la creación de un usuario interno y mostrar el resultado de la operación en un tiempo máximo de 3 segundos bajo condiciones normales de funcionamiento. |
| RNF-02| El sistema deberá soportar al menos 100 solicitudes simultáneas sin degradar significativamente su funcionamiento.|

### Seguridad y usabilidad

| ID     | Requisito                                                                                                                                                                             |
| ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| RNF-02 | El sistema deberá garantizar que la creación de usuarios internos sea realizada únicamente por usuarios con rol Administrador y que las contraseñas sean almacenadas de forma segura. |