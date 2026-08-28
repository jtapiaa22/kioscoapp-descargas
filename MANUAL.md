# Manual de uso — KioscoApp

## 1. Instalación

1. Descargá el instalador desde el [README](README.md).
2. Ejecutalo, aceptá los [Términos y Condiciones](TERMINOS.md), y elegí dónde instalar (o dejá la carpeta que sugiere por defecto).
3. Al abrir la app por primera vez, te va a pedir activar la licencia.

## 2. Activar la licencia

Hay dos formas — usá la que te resulte más cómoda:

**Con internet (recomendado):** en la pantalla de Licencia, tocá **"Activar remotamente"**, completá el nombre de tu kiosco, tu nombre, email y teléfono, y enviá la solicitud. Del otro lado te la activamos y la licencia se aplica sola en tu computadora — no hace falta que hagas nada más ni copies ninguna clave.

**Sin internet / clave manual:** en la misma pantalla vas a ver tu **Machine ID** (un código único de tu computadora). Pasánoslo por WhatsApp o email — te vamos a mandar de vuelta una clave para pegar ahí mismo.

Cuando la licencia esté por vencer, la app te avisa con unos días de anticipación (Configuración → Sistema, o al abrir la app).

## 3. Usuarios y roles

KioscoApp maneja tres roles, cada uno con distinto nivel de acceso:

- **Dueño** — acceso total, incluida Configuración.
- **Encargado** — todo menos Configuración.
- **Cajero** — Ventas, Caja, Ventas del día y Clientes; no ve Inventario, Proveedores, Fondo ni Reportes.

Se entra eligiendo el usuario de una lista y escribiendo el PIN — no hace falta usuario y contraseña como en una web.

Si el único usuario dueño se olvida el PIN, hay una herramienta de recuperación (`recuperar-pin.bat`) que te podemos pasar por soporte para ese caso puntual.

## 4. Ventas

Es la pantalla principal — ahí se cobra. Buscás el producto por nombre o lo escaneás con lector de código de barras, se arma el carrito, y elegís el medio de pago al cobrar: efectivo, débito, crédito, transferencia o cuenta corriente (si el cliente tiene una cargada). En efectivo, cargás con cuánto paga el cliente y la app calcula el vuelto sola.

Si un producto tiene una **promoción** activa (ver Configuración → Promociones) y conviene más que el precio de lista, se aplica automáticamente al agregarlo.

Podés vender productos por peso (fraccionados) además de por unidad.

## 5. Caja

Antes de vender hay que **abrir la caja** con el monto inicial en efectivo. Durante el turno se pueden registrar movimientos manuales (ingresos o egresos) — por ejemplo, si cambiás efectivo por una transferencia, o sacás plata para un gasto del local. Estos movimientos manuales quedan separados de las ventas en los reportes, para que siempre sepas cuánto es venta real y cuánto es otro movimiento.

Al **cerrar caja** se hace el arqueo: la app calcula cuánto efectivo debería haber (inicial + ingresos − egresos + ventas en efectivo) para que lo compares con lo que contás a mano.

## 6. Inventario

Alta, baja y edición de productos: nombre, marca, categoría, código de barras, precio de costo y de venta, stock actual y stock mínimo. Cuando el stock de un producto queda por debajo del mínimo, aparece en las alertas de reposición.

Cada ajuste de stock (una reposición, una corrección) queda en el historial del producto, con la fuente de pago usada si aplica (caja, fondo de stock, o cuenta corriente con el proveedor).

## 7. Proveedores

Cargá tus proveedores con sus datos de contacto — hay un botón para abrirles WhatsApp directo desde la ficha. Podés llevarles cuenta corriente (lo que les debés) y registrar pagos, ya sea en efectivo, desde el fondo de stock, o dejarlo pendiente en la cuenta corriente.

## 8. Fondo de stock

Es una caja separada, pensada para la plata dedicada a reponer mercadería — así no se mezcla con la caja de ventas del día a día. Podés depositar o retirar, y usarlo como fuente de pago al reponer stock o pagarle a un proveedor.

## 9. Clientes

Alta de clientes con cuenta corriente y, si querés, un límite de crédito — la app no deja vender por encima del límite. Se registran los pagos que te van haciendo y queda el historial completo por cliente.

## 10. Reportes

Filtrás por rango de fechas y ves: total vendido, desglose por método de pago, productos más vendidos y márgenes. Los movimientos manuales de caja (los que no son ventas) aparecen en su propia tabla, separados — nunca se mezclan con la facturación real.

## 11. Configuración (solo Dueño)

- **General** — nombre del negocio, dirección, teléfono y formato de número (afecta tickets y reportes).
- **Usuarios** — alta de encargados y cajeros, con su PIN.
- **Categorías** — para organizar el inventario.
- **Promociones** — % de descuento o precio fijo por producto, con cantidad mínima opcional.
- **Backup** — estado del backup automático en la nube.
- **Sistema** — estado de tu licencia (días restantes, a nombre de quién), carpeta de logs para soporte, y buscar actualizaciones a mano.

## 12. Actualizaciones

KioscoApp se actualiza solo: cuando hay una versión nueva, la app te avisa y la instala sin que tengas que descargar nada de acá de nuevo.

## ¿Necesitás ayuda?

Mandanos la carpeta de logs (Configuración → Sistema → Abrir carpeta de logs) junto con una descripción de qué pasó, a: **tadevstudio@gmail.com**
