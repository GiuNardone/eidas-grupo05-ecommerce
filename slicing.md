# Ejercicio: partir una épica en slices verticales

## La épica

> Como usuario de la billetera, quiero enviar dinero a otro usuario de la app para pagarle
> sin usar efectivo.

_Así como está, es una épica gorda: no se puede estimar, no se puede terminar en una
iteración, y esconde decisiones que nadie tomó todavía._

---

## Parte A — Historias verticales

_Entre 5 y 8 historias VERTICALES. Vertical significa que cada historia, sola, entrega algo
usable de punta a punta ("diseñar la pantalla de envío" no es vertical; "enviar dinero a un
contacto de la agenda con saldo suficiente" sí lo es)._

### Historia 1 — [Nombre]

| Campo | Detalle |
|-------|---------|
| Historia | Como [rol], quiero [acción], para [objetivo]. |

**Criterios de aceptación**

1. 
2. 

---

### Historia 2 — [Nombre]

| Campo | Detalle |
|-------|---------|
| Historia | Como [rol], quiero [acción], para [objetivo]. |

**Criterios de aceptación**

1. 
2. 

---

## Parte B — Los caminos que no salen bien

_Elijan UNA de las historias de la Parte A. Las últimas tres preguntas son las importantes:
para cada una, indiquen qué debería hacer el sistema y quién tendría que decidirlo._

**Historia elegida:** [Nombre / ID]

| Pregunta | Qué hace el sistema | Quién decide (analista / negocio / técnica) |
|----------|----------------------|-----------------------------------------------|
| ¿Qué pasa si el saldo es insuficiente? | | |
| ¿Qué pasa si el destinatario no existe o está dado de baja? | | |
| ¿Qué pasa si el sistema descuenta el saldo y falla antes de acreditarlo del otro lado? | | |
| ¿Qué pasa si el usuario aprieta "Enviar" dos veces? | | |
| ¿Qué pasa si se cae la conexión justo después de confirmar? | | |

==========================================================

# Slicing — HU-01 Crear usuario interno

## La épica

Como Administrador, quiero crear usuarios internos y asignarles un rol, para permitir que los empleados accedan al sistema según sus responsabilidades.

---

## Parte A — Historias verticales

### Historia 1 — Crear usuario interno con datos básicos

| Campo    | Detalle                                                                                                                                         |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Historia | Como Administrador, quiero crear un usuario interno ingresando sus datos básicos, para permitir que un nuevo empleado pueda acceder al sistema. |

**Criterios de aceptación**

1. El Administrador debe poder ingresar los datos requeridos para crear el usuario.
2. El sistema debe validar que los campos obligatorios estén completos.
3. Al confirmar, el sistema debe registrar el nuevo usuario.
4. El sistema debe informar que el usuario fue creado correctamente.

### Historia 2 — Crear usuario interno asignando un rol

| Campo    | Detalle                                                                                                                                  |
| -------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Historia | Como Administrador, quiero asignar un rol al crear un usuario interno, para definir las responsabilidades que tendrá dentro del sistema. |

**Criterios de aceptación**

1. El Administrador debe poder seleccionar un rol al crear el usuario.
2. El sistema debe mostrar únicamente los roles predefinidos: Administrador, Ventas, Depósito y Logística.
3. El usuario debe quedar asociado al rol seleccionado.
4. El sistema debe informar que el usuario fue creado correctamente con el rol asignado.

### Historia 3 — Validar datos del usuario interno

| Campo    | Detalle                                                                                                                                               |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Historia | Como Administrador, quiero que el sistema valide los datos ingresados al crear un usuario, para evitar registrar información incorrecta o incompleta. |

**Criterios de aceptación**

1. El sistema debe verificar que los campos obligatorios estén completos.
2. El sistema debe informar qué dato debe corregirse cuando exista un error.
3. El sistema no debe crear el usuario mientras existan datos inválidos.
4. Una vez corregidos los datos, el Administrador debe poder continuar con la creación.

### Historia 4 — Evitar usuarios internos duplicados

| Campo    | Detalle                                                                                                                                                                         |
| -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Historia | Como Administrador, quiero que el sistema controle que los datos identificatorios del usuario no estén registrados previamente, para evitar crear usuarios internos duplicados. |

**Criterios de aceptación**

1. El sistema debe verificar si el usuario ya se encuentra registrado.
2. Si existe un usuario con el mismo dato identificatorio, el sistema debe impedir la creación.
3. El sistema debe informar al Administrador que el usuario ya se encuentra registrado.
4. El Administrador debe poder modificar los datos e intentar nuevamente.

### Historia 5 — Confirmar creación del usuario interno

| Campo    | Detalle                                                                                                                                        |
| -------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Historia | Como Administrador, quiero recibir una confirmación luego de crear un usuario interno, para saber que el registro fue realizado correctamente. |

**Criterios de aceptación**

1. El sistema debe mostrar un mensaje de confirmación cuando la creación finalice correctamente.
2. La confirmación debe indicar que el usuario fue creado.
3. El sistema debe mostrar los datos principales del usuario creado.
4. El sistema debe mostrar el rol asignado al usuario.
