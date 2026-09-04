# Requisitos del sistema

## Descripción del sistema

El sistema consiste en una plataforma de comercio electrónico para la tienda de indumentaria Mundo Sport, ubicada en Rosario. Actualmente, el negocio realiza sus ventas de manera presencial y mediante redes sociales, pero no cuenta con un canal de venta online propio. Esta modalidad genera problemas de gestión manual de pedidos, falta de control de stock en tiempo real, dificultades en el seguimiento de ventas y devoluciones, y una experiencia de compra limitada para los clientes. 

La solución plantea digitalizar y centralizar estos procesos, permitiendo administrar la información del negocio desde una única plataforma y mantener actualizado el inventario tanto del local físico como de la tienda online de forma sincronizada, ofreciendo a los clientes un catálogo organizado donde podrán seleccionar los artículos que desean comprar, utilizar un carrito de compras, realizar pagos de forma segura y consultar el estado de sus pedidos. 

Por otro lado, el personal de la tienda contará con un panel administrativo desde el cual podrá gestionar productos, stock, pedidos, ventas y devoluciones. El sistema también contará con autenticación y distintos roles de acceso para el personal. De esta manera, se busca mejorar la organización interna del negocio, garantizando una experiencia ágil tanto para el comprador como para el equipo de trabajo. 


## Requisitos funcionales


### Módulo 1 — Usuarios y Clientes

| ID | Requisito |
|----|-----------|
| RF-01 |El sistema gestionará usuarios internos (crear, modificar, desactivar, asignar roles). |
| RF-02 |El sistema implementará autenticación por usuario y contraseña con roles predefinidos (Administrador, Ventas, Depósito, Logística).|
| RF-03 |El sistema registrará en auditoría qué usuario realizó cada modificación y permitirá consultar el historial de cambios. |
| RF-04 | El sistema asignará permisos específicos a cada rol: Administrador (todo), Ventas (pedidos, stock consulta, clientes consulta), Depósito (stock completo), Logística (envíos y pedidos preparados).|
| RF-05 |El sistema permitirá a los clientes registrarse con sus datos (nombre, apellido, email, fecha nacimiento, teléfono, DNI, contraseña, dirección, CP, ciudad, provincia) e iniciar sesión con sus credenciales.|
| RF-06 | El sistema permitirá al cliente gestionar su cuenta (consultar y modificar datos personales, consultar historial de compras y estado de pedidos, solicitar devoluciones).|
| RF-07 |El sistema permitirá a clientes que hayan comprado un producto calificarlo (1-5 estrellas + comentario opcional).|
|RF-08 | El Administrador podrá eliminar reseñas con lenguaje inapropiado.|
| RF-09 | El sistema exigirá registro obligatorio para finalizar una compra y permitirá a ventas y al administrador consultar el listado de clientes registrados.|


### Módulo 2 — Productos, Stock y Proveedores

| ID | Requisito |
|----|-----------|
| RF-10 | El sistema permitirá consultar el catálogo sin necesidad de registrarse, mostrando descripción, precio, color, talle, disponibilidad, entre 2 y 4 fotografías y tabla de medidas por tipo de producto.|
| RF-11 |El sistema permitirá al Administrador gestionar productos y variantes (crear, modificar, desactivar). |
| RF-12 | Cuando una variante llegue a stock cero, el producto continuará visible en el catálogo pero no podrá agregarse al carrito. |
| RF-13 | El sistema mantendrá stock unificado para cada combinación de producto-talle-color, afectado tanto por ventas online como por ventas en local.|
| RF-14 |El sistema descontará stock al confirmar el pago, registrará historial de movimientos (fecha, variante, cantidad, tipo, usuario, ID pedido) y permitirá al rol Depósito gestionar ingresos de mercadería. |
| RF-15 |El sistema generará alertas de bajo stock (≤ 3 unidades) dirigidas al área de Depósito. |
| RF-16 |El sistema permitirá gestionar proveedores (registrar, modificar, desactivar) almacenando razón social, CUIT, teléfono, email y dirección, y asociar productos con sus proveedores. |


### Módulo 3 — Carrito, Pedidos y Promociones
| ID | Requisito |
|----|-----------|
| RF-17 | El sistema permitirá gestionar el carrito: agregar productos (exigiendo talle y color), visualizar, modificar cantidades, eliminar productos y vaciar carrito.|
| RF-18 | El sistema reservará los productos por 24 horas, verificará stock antes de confirmar, mostrará resumen con subtotal y total, y vaciará automáticamente el carrito al expirar el plazo.|
| RF-19 | Todos los mensajes de error deben estar redactados sin tecnicismos, e indicar una acción concreta a seguir.|
| RF-20 | El sistema gestionará el checkout solicitando confirmación de datos de entrega, permitiendo seleccionar envío a domicilio o retiro en local, y calculando el costo de envío correspondiente.|
| RF-21 |El sistema se integrará con Mercado Pago y se podrán procesar pagos con tarjeta de crédito y débito, registrando estado, fecha, importe y medio de pago. |
| RF-22 |El sistema gestionará los estados del pedido: "Pendiente de pago", "Pago aprobado", "En preparación", "Listo para retirar"/"Enviado", "Entregado"/"Retirado". Notificará al cliente mediante email por cada cambio de estado. |
| RF-23 | El sistema confirmará el pedido y descontará stock solo al aprobarse el pago; si es rechazado, permitirá reintentar; si queda pendiente, mantendrá el pedido en estado "Pendiente de pago".|
| RF-24 | El cliente podrá cancelar el pedido antes de su envío o retiro y se generará una nota de credito.|
| RF-25 | El sistema permitirá al Administrador crear promociones (descuento porcentual o fijo) aplicables a producto específico, categoría o catálogo completo, con fechas de inicio y fin configurables.|
| RF-26 | El sistema permitirá crear cupones configurados como uso único o múltiple, con límite de usos, fechas configurables y activación/desactivación automática según período.|


### Módulo 4 — Envios y Devoluciones

| ID | Requisito |
|----|-----------|
| RF-27 |El sistema se integrará con proveedor logístico para obtener número de seguimiento y permitirá calcular costos de envío. |
| RF-28 |El sistema permitirá al empleado confirmar retiro en local y establecerá plazo de 15 días para retirar. |
| RF-29 | El sistema notificará al cliente el vencimiento del plazo de retiro (día 12 y día 15).|
| RF-30 | El sistema permitirá al cliente solicitar devolución desde "Mi Cuenta", seleccionando el pedido y el motivo (talle incorrecto, defectuoso, equivocado), dentro de los 5 días hábiles posteriores a la entrega/retiro.|
| RF-31 | El sistema gestionará los estados de devolución ("Solicitada", "En revisión", "Aprobada", "Rechazada", "Finalizada") y notificará al cliente en su panel cada cambio.|
| RF-32 |El sistema permitirá al rol Ventas resolver las solicitudes de devolución, generando cambio o nota de crédito según corresponda.|


### Módulo 5 — Reportes y Dashboard

| ID | Requisito |
|----|-----------|
| RF-33 | El sistema permitirá consultar reportes de ventas por día, semana, mes, año y períodos anteriores (-5 años), filtrando por rango de fechas y productos, exportables a Excel.|
| RF-34 | El sistema mostrará productos más vendidos, productos con menor movimiento, ingresos totales, ventas por medio de pago, clientes nuevos (últimos 7 días) y recurrentes (más de 2 compras).|
| RF-35 |El panel de Administración mostrará indicadores clave de actividad (ventas diarias, stock crítico, pedidos pendientes, devoluciones).|


## Requisitos no funcionales

### Módulo 1 — Rendimiento y Disponibilidad

| ID | Requisito |
|----|-----------|
| RNF-01 | El sistema responderá a consultas de catálogo, carrito y Mi Cuenta en ≤ 3 segundos al probarse con 50 usuarios simultáneos. |
| RNF-02 | El sistema completará el flujo de checkout en ≤ 5 segundos, sin contar el tiempo de respuesta de Mercado Pago.|
| RNF-03 | El sistema procesará al menos 10 pedidos por minuto en horas pico sin errores. |
| RNF-04 | El sistema deberá permanecer disponible al menos el 95% del tiempo en horario comercial (9:00 a 20:00). | 


### Módulo 2 — Seguridad y Privacidad

| ID | Requisito |
|----|-----------|
| RNF-05 | Todo el tráfico de datos entre el navegador del usuario y el servidor web debe estar cifrado de extremo a extremo utilizando el protocolo HTTPS |
| RNF-06 | El sistema deberá proteger las contraseñas de los usuarios y no almacenarlas en texto visible. |
| RNF-07 | El sistema bloqueará el acceso de un cliente por 15 minutos tras 5 intentos fallidos de inicio de sesión; y de un empleado por 30 minutos tras 3 intentos fallidos. |
| RNF-08 | El sistema debe cumplir con la Ley 25.326 de Protección de Datos personales para el almacenamiento, privacidad y gestión de la información de los clientes. |


### Módulo 3 — Seguridad y Privacidad

| ID | Requisito |
|----|-----------|
| RNF-12 | El sistema debe cumplir estrictamente con la Ley 25.326 de Protección de Datos personales para el almacenamiento, privacidad y gestión de la información de los clientes. |
| RNF-13 |Todo el tráfico de datos entre el navegador del usuario y el servidor web debe estar cifrado de extremo a extremo utilizando el protocolo HTTPS con un certificado SSL/TLS válido.|
| RNF-14 | El sistema bloqueará el acceso de un cliente por 15 minutos tras 5 intentos fallidos consecutivos de inicio de sesión. |
| RNF-15 | El sistema bloqueará el acceso de un empleado por 30 minutos tras 3 intentos fallidos consecutivos y enviará un e-mail de aviso al Administrador. | 
| RNF-16 | El sistema nunca almacenará datos sensibles de tarjetas (como el CVV) y mostrará únicamente los últimos 4 dígitos en el panel administrativo. |
| RNF-17 | El panel administrativo debe exigir autenticación mediante usuario y contraseñas seguras (mínimo 8 caracteres, alfanuméricas). |
| RNF-18 | El sistema deberá ocultar la contraseña mientras el usuario la ingresa. | 


### Módulo 4 — Usabilidad y Experiencia de Usuario

| ID | Requisito | 
|----|-----------|
| RNF-19 | El diseño será completamente responsive, adaptándose a resoluciones desde 360px (smartphones) hasta 1920px (escritorio). | 
| RNF-20 | El sistema mostrará mensajes de error claros e indicativos especificando el campo incorrecto y la solución requerida. |
| RNF-21 | El sistema mostrará un icono de carga en operaciones que demoren más de 1s. | 
| RNF-22 | El flujo de compra completo debe requerir no mas de 4 pasos: Carrito, Datos de Envío, Método de Pago y Confirmación. | 
| RNF-23 | El buscador mostrará sugerencias de productos mientras el usuario escribe, con una demora máxima de 1 segundo. |
| RNF-24 | El panel de administración debe presentar una curva de aprendizaje baja, permitiendo al dueño y empleada usarlo eficazmente mediante una capacitación de 2 horas. |

### Módulo 5 — Integración y Compatibilidad

| ID | Requisito | 
|----|-----------|
| RNF-25 | El sistema deberá permitir realizar las operaciones principales desde una computadora y desde un dispositivo móvil. |
| RNF-26 | El sistema deberá funcionar correctamente en los navegadores Google Chrome, Mozilla Firefox y Microsoft Edge. |
| RNF-27 | El sistema utilizará el formato JSON para intercambio de datos en todas las integraciones con servicios externos. | 

### Módulo 6 — Base de Datos y Almacenamiento

| ID | Requisito |
|----|-----------|
| RNF-28 | Las consultas a la base de datos para mostrar productos y stock se ejecutarán en menos de 1 segundo. | 
| RNF-29 | La base de datos mantendrá índices en las claves primarias y foráneas de productos, stock y pedidos para optimizar las consultas. | 
| RNF-30 | Las imágenes subidas por el Administrador serán comprimidas a un tamaño menor a 300 KB para que el sitio cargue rápido.| 
| RNF-31 | El sistema mantendrá un historial de hasta 10000 pedidos pasados garantizando consultas en ≤ 3 segundos. | 
| RNF-32 | El sistema registrará los movimientos de stock en una tabla de auditoría dedicada sin pérdida ni sobrescritura de datos. | 

### Módulo 7 — Respaldo y Recuperación

| ID | Requisito |
|----|-----------|
| RNF-33 | El sistema realizará una copia de seguridad diaria de la base de datos.|
| RNF-34 | El sistema garantizará un tiempo máximo de restauración de 4 horas para levantar la plataforma tras una falla del servidor. | 
| RNF-35 | El Administrador podrá restaurar la base de datos desde el último backup en menos de 1 hora siguiendo una guía escrita. | 
| RNF-36 | El sistema realizará un backup completo semanal de imágenes y archivos del código + backup diario de la base de datos. | 

### Módulo 8 — Mantenibilidad y Soporte

| ID | Requisito |
|----|-----------|
| RNF-37 | Cuando ocurra un error en el sistema, se guardará un registro con fecha, hora y descripción del error | 
| RNF-38 | El código fuente del proyecto estará versionado en Git, permitiendo volver a una versión anterior si algo falla después de un cambio. |
