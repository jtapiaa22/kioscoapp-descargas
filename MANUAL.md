# Manual de uso — KioscoApp

## 1. Instalación

1. Descargá el instalador desde el [README](README.md).
2. Ejecutalo, aceptá los [Términos y Condiciones](TERMINOS.md), y elegí dónde instalar (o dejá la carpeta que sugiere por defecto).
3. Al abrir la app por primera vez, te va a pedir activar la licencia.

KioscoApp se abre una sola vez: si hacés doble clic en el ícono con la app ya abierta, te trae la ventana que ya estaba, no abre otra.

## 2. Activar la licencia

Hay dos formas — usá la que te resulte más cómoda:

**Con internet (recomendado):** en la pantalla de Licencia, tocá **"¿Tenés wifi en esta compu? Activar remotamente"**, completá el nombre de tu kiosco, tu nombre, email y teléfono, y enviá la solicitud. Del otro lado te la activamos y la licencia se aplica sola en tu computadora — no hace falta que hagas nada más ni copies ninguna clave.

**Sin internet / clave manual:** en la misma pantalla vas a ver tu **Machine ID** (un código único de tu computadora). Pasánoslo por WhatsApp o email — te vamos a mandar de vuelta una clave para pegar ahí mismo.

Los días que te quedan se ven siempre arriba a la izquierda, al lado del nombre del negocio (cambia de color cuando faltan 7 días o menos). También en Configuración → Sistema.

## 3. Usuarios y roles

KioscoApp maneja tres roles, cada uno con distinto nivel de acceso:

- **Dueño** — acceso total, incluida Configuración.
- **Encargado** — todo menos Configuración.
- **Cajero** — Ventas, Caja, Ventas del día y Clientes; no ve Inventario, Proveedores, Fondo ni Reportes. Puede anular solo **sus propias ventas del día**, y no puede corregir el monto contado de un cierre de caja.

Se entra eligiendo el usuario de una lista y escribiendo el PIN (4 a 6 números) — no hace falta usuario y contraseña como en una web. Usuario inicial: **Administrador**, PIN **1234** — cambialo apenas entres (Configuración → Usuarios).

Si un empleado se olvida el PIN, el dueño se lo cambia desde Configuración → Usuarios → Editar. Si el que se olvidó es el único dueño, hay una herramienta de recuperación (`recuperar-pin.bat`) que te podemos pasar por soporte.

## 4. Ventas

Es la pantalla principal — ahí se cobra.

1. **Agregá productos:** escaneá con el lector de código de barras, buscá por nombre o marca, o tocá la tarjeta del producto. Sin lector, podés escanear con la cámara de la PC o **con tu celular** (botón del celular → escaneás el QR con el celu conectado a la misma WiFi, y cada código que apuntes se agrega solo).
2. **¿El código no está cargado?** Te aparece "+ Crear producto con este código": lo das de alta en el momento y queda en el carrito.
3. **Productos por peso** (fiambre, verdura, alimento suelto): botón **"Vender por peso"** (F3), elegís el producto y cargás los kilos o gramos.
4. **Cobrar** (F4): elegís el medio de pago.
   - **Efectivo:** cargás con cuánto paga (o tocás un billete sugerido / "Exacto") y la app calcula el vuelto.
   - **Débito / Crédito:** cobrás con el posnet y confirmás.
   - **Transferencia:** anotás el nombre de quien transfiere. Confirmá que la plata llegó antes de entregar.
   - **Cta. Cte. (fiado):** elegís el cliente (o lo creás ahí mismo). Si tiene límite de crédito, te muestra cuánto le queda disponible y no deja pasarse.
5. Al confirmar, se descuenta el stock y podés **imprimir el ticket**.

Las **promociones** activas se aplican solas cuando conviene. También podés aplicar un **descuento %** a toda la venta.

Si cambiás de pantalla o se cierra la app con una venta a medio cargar, al volver a Ventas **se recupera sola**.

**Hay que tener la caja abierta para vender** — si no, la app te avisa.

**Atajos:** F2 buscar · F3 vender por peso · F4 cobrar · Enter agregar / confirmar · Esc cancelar · Alt+E efectivo · Alt+D débito · Alt+C crédito · Alt+T transferencia · Alt+F fiado · F1 ver todos los atajos.

## 5. Caja

**Abrir:** al empezar el turno, cargás el efectivo inicial del cajón y tocás "Abrir caja".

**Durante el turno** ves:
- Monto inicial, total vendido y cantidad de ventas.
- **Por medio de pago:** cuánto entró en efectivo (ya descontado el vuelto), débito, crédito, transferencia y fiado.
- **Movimientos manuales** (botón "+ Movimiento"): ingresos o egresos que no son ventas — sacar plata para un gasto del local, cambiar efectivo por una transferencia, etc. Si el movimiento no es en efectivo, queda anotado pero no cambia el arqueo del cajón.

Algunos movimientos se generan solos desde otras pantallas y aparecen marcados: **cobros de fiado** (se corrigen desde Clientes), **compras de stock** pagadas con la caja (desde Inventario) y movimientos del **Fondo de stock** (desde Fondo). Así, si se corrige algo, se corrige completo y el arqueo siempre cierra.

**Cerrar:** tocás "Cerrar caja", contás el efectivo del cajón y lo cargás. La app calcula cuánto tendría que haber (inicial + ventas en efectivo + ingresos − egresos en efectivo) y te muestra si sobra o falta.

**Historial:** ahí quedan todos los turnos cerrados, con sus ventas. Si se contó mal al cerrar, el dueño o el encargado pueden **corregir el monto contado** (con un motivo); queda registrado el valor original.

Si un día se olvidaron de cerrar la caja, al abrir la siguiente la anterior se cierra sola y queda anotado.

## 6. Ventas del día

Lista de las ventas de hoy (el cajero ve solo las suyas). Desde acá podés:
- Ver el detalle de cada venta y **reimprimir el ticket**.
- **Anular** una venta (con motivo): el stock vuelve al inventario y, si era fiado, se descuenta de la deuda del cliente.
- **Generar factura** electrónica (ver punto 13).

## 7. Inventario

Alta, baja y edición de productos: nombre, marca, categoría, código de barras, precio de costo y de venta, stock actual y stock mínimo. Cuando el stock de un producto queda por debajo del mínimo, se marca para reponer.

**Cargar muchos productos de una:** botón **Importar productos**, desde un Excel. Con **Descargar plantilla** te bajás el modelo para completar.

**Reponer stock** (botón ±): cargás la cantidad y, si querés, cómo lo pagaste — efectivo de la caja, fondo de stock, o a cuenta del proveedor. Cada ajuste queda en el historial del producto, y si te equivocaste lo podés **deshacer** desde ahí (se revierte el stock y la plata).

## 8. Proveedores

Cargá tus proveedores con sus datos de contacto — hay un botón para abrirles WhatsApp directo desde la ficha. Podés llevarles cuenta corriente (lo que les debés), ver el historial de compras y registrar pagos en efectivo, desde el fondo de stock u otros medios.

## 9. Fondo de stock

Es una caja separada, pensada para la plata dedicada a reponer mercadería — así no se mezcla con la caja de ventas del día a día. Podés depositar o retirar (indicando si la plata sale o entra al cajón), usarlo para pagar reposiciones o proveedores, y ver cuánto haría falta para reponer todo lo que está bajo el mínimo.

## 10. Clientes

Alta de clientes con cuenta corriente y, si querés, un límite de crédito — la app no deja vender fiado por encima del límite. Se registran los pagos que te van haciendo (un pago en efectivo entra solo a la caja del turno) y queda el historial completo por cliente. Los pagos se pueden editar o eliminar con motivo, y el saldo se recalcula solo.

## 11. Reportes

Filtrás por rango de fechas y ves: total vendido, ticket promedio, desglose por medio de pago, ventas por día, productos más vendidos y **ganancia por producto** (según el precio de costo cargado). Los movimientos manuales de caja aparecen en su propia tabla, separados de las ventas. También hay un reporte de cuentas corrientes (cuánto se fió, cuánto se cobró y quién debe).

## 12. Configuración (solo Dueño)

- **General** — nombre del negocio, dirección, teléfono y formato de número (afecta tickets y reportes).
- **Usuarios** — alta de encargados y cajeros, con su PIN.
- **Categorías** — para organizar el inventario (una categoría es de productos por unidad o por peso).
- **Promociones** — % de descuento o precio fijo por producto, con cantidad mínima.
- **Facturación** — datos para la factura electrónica (ver punto 13).
- **Backup** — exportar una copia de tus datos a un archivo, o restaurar una copia (por ejemplo, al pasar a una PC nueva).
- **Sistema** — estado de tu licencia, carpeta de logs para soporte, y buscar actualizaciones a mano.

## 13. Facturación electrónica (ARCA)

Para emitir **Factura C** (monotributo) desde KioscoApp:

1. En **Configuración → Facturación** cargá tu CUIT, el punto de venta y el token de acceso que te pasamos.
2. Probá primero **sin** tildar "Modo producción": las facturas salen en el ambiente de prueba de ARCA y no son válidas. Cuando confirmes que todo anda, tildalo.
3. Para facturar una venta: **Ventas del día → Generar factura**. Podés hacerla a Consumidor Final o con DNI/CUIT del cliente. El ticket impreso sale con el CAE y el código QR.

Una venta ya facturada no se puede anular desde la app (en ARCA hace falta una Nota de Crédito).

## 14. Backups

Tus datos se guardan automáticamente en la nube mientras KioscoApp está abierto y con internet, además de una copia diaria en tu propia PC. Si se te rompe la computadora, escribinos y te ayudamos a recuperarlos. Igual te recomendamos exportar un backup de vez en cuando (Configuración → Backup) y guardarlo en un lugar seguro.

## 15. Actualizaciones

KioscoApp se actualiza solo: cuando hay una versión nueva, la baja en segundo plano y **la instala cuando cerrás sesión o cerrás la app** — nunca en medio de una venta. Si querés instalarla en el momento, tocá **"Reiniciar ahora"** en el aviso que aparece abajo. No hace falta volver a descargar nada de acá.

Para ver qué versión tenés, mirá la esquina de abajo a la derecha de la app (por ejemplo, "v1.9").

## ¿Necesitás ayuda?

Mandanos la carpeta de logs (Configuración → Sistema → Abrir carpeta de logs) junto con una descripción de qué pasó, a: **tadevstudio@gmail.com**
