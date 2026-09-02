# Historias de usuario

_Presentar al menos una historia de usuario representativa por módulo._
_Cada historia debe incluir formato clásico, criterios de aceptación y validación INVEST._

---
---
## HU-01 — Registro, Autenticación y Gestión de Perfil de Cliente

| Campo                   | Detalle                                                                                                                                                 |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Historia                | Como cliente, quiero registrarme ingresando mis datos obligatorios, iniciar sesión y acceder a mi perfil,  para administrar mi información personal, consultar el historial y estado de mis pedidos y realizar compras en la plataforma. |
| Módulo                  | 02- Clientes y Cuentas                                                                                                                                     |
| Requisitos relacionados | RF-08, RF-09, RF-10, RF-11, RF-12, RF-13, RF-14, RF-15, RF-16, RF-17                                                                                                                                     |

### Criterios de aceptación

1. El sistema exige todos los campos obligatorios para el alta de usuario, validando el formato del email y DNI e impidiendo el registro si el correo ya existe.
2. El cliente puede autenticarse con sus credenciales o recuperar la clave mediante un enlace enviado a su correo electrónico en caso de olvido. 
3. Desde la sección "Mi Cuenta", el cliente autenticado puede consultar y modificar sus datos de contacto (con el DNI bloqueado para edición) y revisar el historial de pedidos.


### Validación INVEST

| Criterio      | ¿Se cumple? | Observación                                                                                   |
| ------------- | ----------- | --------------------------------------------------------------------------------------------- |
| Independiente | Sí          | Se implementa y prueba de forma autónoma sin depender de los módulos de pago o envíos.                           |
| Negociable    | Sí          | Los datos requeridos en el registro pueden ajustarse.            |
| Valiosa       | Sí          | Permite personalizar la experiencia y asociar los pedidos a un usuario registrado.                       |
| Estimable     | Sí          | Representa un flujo de autenticación estándar.                             |
| Pequeña       | Sí          | Se limita al flujo de alta, acceso y edición de perfil de un cliente.                               |
| Verificable   | Sí          | Se verifica creando cuentas, iniciando sesión y editando campos. |

## HU-02 — Consulta, Búsqueda y Filtrado de Productos por Variante

| Campo | Detalle |
|-------|---------|
| Historia | Como cliente, quiero buscar prendas por palabra clave y aplicar filtros por categoría, talle, color y precio, para encontrar rápidamente las prendas que me interesan y agilizar mi proceso de compra. |
| Módulo |03 - Catálogo y Productos |
| Requisitos relacionados | RF-24, RF-25, RF-26, RF-27, RF-28, RF-32, RF-33, RF-34, RF-35 |

### Criterios de aceptación

1. El catálogo se encuentra disponible públicamente y exhibe para cada prenda entre 2 y 4 fotos, descripción, tabla de medidas y la matriz de variantes.
2. El sistema permite filtrar prendas por categoría, precio, talle, color y disponibilidad, así como ordenarlas por precio (asc/desc), novedad o popularidad.
3. Si una variante alcanza stock cero, la interfaz muestra el indicador "Sin stock" e inhabilita su agregado al carrito de compras.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |Sí  |Consulta directamente las lecturas del catálogo de la base de datos sin depender del carrito. |
| Negociable |Sí  |La distribución visual de los filtros y el diseño de la tabla de medidas pueden ajustarse. |
| Valiosa | Sí |Mejora la usabilidad y reduce el tiempo que el usuario busca un artículo. |
| Estimable | Sí |Basada en consultas estructuradas de lectura y maquetación de fichas de producto. |
| Pequeña | Sí |Se concentra exclusivamente en la búsqueda, filtrado y renderizado del catálogo. |
| Verificable | Sí |Se prueba aplicando filtros cruzados y verificando la ficha de prendas con y sin stock. |



## HU-03 — [Nombre de la historia]

| Campo | Detalle |
|-------|---------|
| Historia | Como [rol], quiero [acción], para [objetivo]. |
| Módulo | |
| Requisitos relacionados | RF-XX, RF-XX |

### Criterios de aceptación

1. 
2. 
3. 

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | | |
| Negociable | | |
| Valiosa | | |
| Estimable | | |
| Pequeña | | |
| Verificable | | |




## HU-02 — [Nombre de la historia]

| Campo | Detalle |
|-------|---------|
| Historia | Como [rol], quiero [acción], para [objetivo]. |
| Módulo | |
| Requisitos relacionados | RF-XX, RF-XX |

### Criterios de aceptación

1. 
2. 
3. 

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | | |
| Negociable | | |
| Valiosa | | |
| Estimable | | |
| Pequeña | | |
| Verificable | | |
