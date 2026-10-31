# REQUERIMIENTOS DE SOFTWARE — APPRESSO

## 1. Requerimientos funcionales

### 1.1. Gestión de usuarios y permisos

---

### **RF-01 — Autenticación de usuarios**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir que los usuarios registrados inicien sesión mediante credenciales válidas con el correo electrónico y la contraseña para acceder a la aplicación.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, reunión por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el usuario se encuentra registrado en el sistema, *cuando* ingresa un correo electrónico y una contraseña válidos y hace clic en el botón de inicio de sesión, *entonces* el sistema valida las credenciales correctamente y le otorga acceso a la interfaz principal de la aplicación.
2. *Dado* que un usuario intenta iniciar sesión, *cuando* ingresa un correo electrónico no registrado o una contraseña incorrecta, *entonces* el sistema deniega el acceso y muestra un mensaje de error notificando que las credenciales son inválidas.

---

### **RF-02 — Administración de usuarios**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir al administrador gestionar las cuentas de usuario y asignarles los roles autorizados.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, reunión por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el administrador ha iniciado sesión, *cuando* crea o edita la información de un usuario y guarda los cambios, *entonces* el sistema actualiza la base de datos y refleja los datos del usuario en la lista global de usuarios.
2. *Dado* que el administrador gestiona una cuenta existente, *cuando* le asigna o cambia un rol autorizado (ej. Administrador, Usuario, etc.) y confirma la acción, *entonces* el sistema actualiza los permisos de dicha cuenta inmediatamente.
3. *Dado* que un usuario no administrador intenta acceder al módulo de gestión de cuentas o asignaciones de roles, *cuando* ingresa a la ruta correspondiente, *entonces* el sistema deniega el acceso y muestra un mensaje "Acceso no autorizado".

---

### **RF-03 — Acceso según el rol**

**Tipo:** Funcional

**Descripción:** El sistema deberá presentar a cada usuario las funcionalidades correspondientes a su rol: administrador, cajero, mesero, cocinero o cliente.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, reunión por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que un usuario inicia sesión con un rol específico (Administrador, Cajero, Mesero, Cocinero o Cliente), *cuando* navega en la plataforma, *entonces* el sistema le despliega únicamente el menú y las herramientas asignadas a su rol.
2. *Dado* que un usuario con rol de Cliente, Mesero o Cocinero intenta realizar acciones reservadas para Administrador o Cajero (como ver reportes financieros o procesar cobros), *cuando* intenta interactuar con dichas funciones, *entonces* el sistema no las muestra disponibles o bloquea la acción notificando falta de permisos.
3. *Dado* que el administrador modifica el rol de un usuario activo en el sistema, *cuando* ese usuario vuelve a cargar la interfaz o inicia sesión de nuevo, *entonces* las funcionalidades disponibles se ajustan de inmediato al nuevo rol.

---

### **RF-04 — Restricción de operaciones no autorizadas**

**Tipo:** Funcional

**Descripción:** El sistema deberá impedir que un usuario ejecute operaciones que no estén autorizadas para su rol.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, reunión por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que un usuario autenticado intenta ejecutar una función no permitida desde la app (o manipulando solicitudes a la API móvil), *cuando* la app envía la petición, *entonces* el servidor deniega la acción y responde con un código de error de autorización (ej. 403 Forbidden), evitando cualquier cambio en los datos.
2. *Dado* que un usuario intenta interactuar con un módulo o acción restringida, *cuando* presiona sobre el componente, *entonces* la app le despliega una alerta nativa o diálogo informativo con el mensaje "No cuentas con los permisos necesarios para realizar esta operación".

---

### **RF-05 — Acceso remoto del administrador**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir que el administrador acceda a las funcionalidades autorizadas desde un dispositivo móvil conectado a Internet, independientemente de su ubicación.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, reunión por Meet.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que el administrador se encuentra fuera de la red local del establecimiento y dispone de conexión a Internet (red celular 4G/5G o red Wi-Fi externa), *cuando* inicia sesión desde la aplicación móvil, *entonces* el sistema autentica sus credenciales e ingresa exitosamente sin requerir estar en la misma red local.
2. *Dado* que el administrador se ha autenticado remotamente, *cuando* navega por la app, *entonces* el sistema le habilita todas las funciones de su rol (gestión de usuarios, reportes, configuración, etc.) de forma fluida y sincronizada en tiempo real.
3. *Dado* que el administrador realiza una operación remota, *cuando* la señal de Internet se interrumpe o es inestable, *entonces* la app móvil muestra un mensaje descriptivo ("Sin conexión a Internet. Por favor, verifica tu red.") en lugar de cerrarse de manera inesperada o bloquear la pantalla.

---

### 1.2. Gestión de inventario y productos

---

### **RF-06 — Gestión del catálogo de productos**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir exclusivamente al administrador registrar, consultar, modificar y desactivar productos y categorías.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, reunión por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el administrador se encuentra en la pantalla de gestión del catálogo de la app móvil, *cuando* completa los campos para crear, editar o desactivar un producto o categoría y confirma la acción, *entonces* el sistema guarda los cambios y los refleja en la lista de productos en tiempo real.
2. *Dado* que un usuario con rol de Mesero, Cajero, Cocinero o Cliente navega por la app móvil, *cuando* intenta acceder al módulo de edición del catálogo, *entonces* la app no muestra los botones de edición/registro o deniega la acción mostrando un mensaje de error de permisos.

---

### **RF-07 — Ajustes manuales de inventario**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir exclusivamente al administrador registrar entradas y salidas manuales de unidades de productos.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, reunión por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el administrador selecciona un producto en la app móvil e ingresa una cantidad de entrada o salida manual junto con la justificación, *cuando* confirma la transacción, *entonces* el sistema actualiza el stock total de manera inmediata.
2. *Dado* que el administrador intenta registrar una salida manual superior al stock disponible o ingresa valores inválidos (ej. menores o iguales a cero), *cuando* presiona guardar, *entonces* la app despliega una alerta de validación e impide guardar el movimiento.

---

### **RF-08 — Consulta de existencias en tiempo real**

**Tipo:** Funcional

**Descripción:** El sistema deberá almacenar y mostrar la cantidad disponible de cada producto, actualizándose cuando se confirme un movimiento que afecte el inventario.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, reunión por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que se confirma una venta, comanda o ajuste manual que modifique el stock de un producto, *cuando* cualquier usuario consulta las existencias en la app, *entonces* la interfaz muestra la cifra de stock actualizada inmediatamente.
2. *Dado* que un usuario autorizado consulta la lista de productos, *cuando* revisa el detalle de un ítem, *entonces* la app exhibe el número exacto de unidades disponibles de forma clara en pantalla.

---

### **RF-09 — Configuración de umbrales mínimos de existencias**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir configurar un umbral mínimo de existencias para cada producto activo.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, reunión por Meet.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que el administrador ingresa al detalle de un producto activo en la app, *cuando* establece o modifica un valor numérico para el "Umbral Mínimo" y guarda los cambios, *entonces* el sistema almacena este límite asociado al producto.
2. *Dado* que el administrador intenta ingresar un valor negativo en el campo de umbral mínimo, *cuando* intenta guardar, *entonces* la app muestra un mensaje indicando que debe ingresar un entero mayor o igual a cero.

---

### **RF-10 — Alertas de existencias bajas**

**Tipo:** Funcional

**Descripción:** El sistema deberá generar una alerta cuando las existencias de un producto sean iguales o inferiores al umbral mínimo configurado.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, reunión por Meet.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que el stock disponible de un producto disminuye y alcanza o queda por debajo del umbral mínimo configurado, *cuando* ocurre dicho movimiento, *entonces* la app muestra un indicador visual (ej. etiqueta roja o icono de advertencia) en la lista de inventario.
2. *Dado* que existen productos con existencias bajas, *cuando* el administrador abre la app móvil, *entonces* visualiza un módulo o notificación con el resumen de productos que requieren reabastecimiento.

---

### **RF-11 — Consulta del menú disponible para meseros**

**Tipo:** Funcional

**Descripción:** El sistema deberá mostrar a los meseros los productos agrupados por categoría, con su precio, disponibilidad y cantidad existente.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, reunión por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que un mesero abre la sección de menú en la app móvil, *cuando* selecciona una categoría (ej. Bebidas, Platos Fuertes, Postres), *entonces* la app despliega los productos correspondientes con su nombre, precio formateado y stock disponible.
2. *Dado* que el mesero explora el catálogo, *cuando* visualiza un producto sin unidades, *entonces* la app le marca visualmente el producto como "Agotado" o "No disponible".

---

### **RF-12 — Validación de cantidades solicitadas en comandas**

**Tipo:** Funcional

**Descripción:** El sistema deberá rechazar la incorporación a una comanda de una cantidad superior a las unidades disponibles para ese producto.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, reunión por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que un producto tiene $N$ unidades disponibles, *cuando* el mesero intenta agregar a la comanda una cantidad mayor a $N$, *entonces* la app bloquea la adición y despliega una alerta notificando que no hay suficiente stock disponible.
2. *Dado* que una comanda tiene cierta cantidad seleccionada y el mesero intenta incrementarla sobrepasando el stock en tiempo real, *cuando* presiona el botón de incrementar (+), *entonces* el contador se detiene en el límite máximo disponible y muestra un aviso en pantalla.

---

### **RF-13 — Inhabilitación automática de productos agotados**

**Tipo:** Funcional

**Descripción:** El sistema deberá identificar como no disponibles para nuevos pedidos los productos cuyas existencias disponibles sean cero.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, reunión por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que las existencias de un producto llegan a cero (0), *cuando* un mesero consulta el menú en la app, *entonces* el botón de agregar a comanda para dicho producto se deshabilita automáticamente y se marca como "Agotado".
2. *Dado* que un producto estaba agotado y el administrador hace un ingreso manual de existencias, *cuando* el mesero actualiza la vista del menú, *entonces* el producto vuelve a habilitarse para nuevos pedidos.

---

### **RF-14 — Historial de movimientos de inventario**

**Tipo:** Funcional

**Descripción:** El sistema deberá registrar y permitir consultar el historial de entradas, salidas y ajustes manuales del inventario, incluyendo producto, cantidad, fecha y usuario responsable.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, reunión por Meet.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que se ejecuta cualquier movimiento de inventario (venta, entrada manual, ajuste de merma), *cuando* el administrador abre la pantalla de historial en la app, *entonces* visualiza un registro con el nombre del producto, la cantidad alterada (+/-), fecha/hora exacta y la cuenta del usuario que realizó la acción.
2. *Dado* que el administrador consulta la bitácora de inventario en la app móvil, *cuando* aplica filtros por rango de fechas o nombre de producto, *entonces* el sistema muestra el listado correspondiente filtrado correctamente.

---

### 1.3. Gestión de comandas y pedidos

---

### **RF-15 — Creación de comandas asociadas a una mesa**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir a los meseros crear una comanda asociada a una mesa identificada.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, reunión por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que un mesero selecciona una mesa disponible en el mapa de mesas de la app móvil, *cuando* confirma la apertura de un nuevo pedido, *entonces* el sistema crea una comanda vinculada explícitamente al número/nombre de esa mesa y la cambia a estado "Ocupada" o "En atención".
2. *Dado* que una mesa ya tiene una comanda activa abierta, *cuando* el mesero intenta crear una nueva comanda en la misma mesa, *entonces* la app le advierte que la mesa ya posee un pedido activo y le ofrece la opción de abrir la comanda existente.

---

### **RF-16 — Registro de productos y preferencias en la comanda**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir al mesero agregar a la comanda de una mesa los productos disponibles por categoría, la cantidad de cada uno y observaciones o preferencias del cliente en texto libre de hasta 100 caracteres. No se permite agregar cantidades mayores a la existencia ni productos desactivados.

**Origen:** El cliente Pepito Pérez — dueño.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que un mesero con sesión activa tiene una mesa seleccionada, *cuando* agrega un producto con su cantidad y observaciones, *entonces* la comanda muestra el producto, la cantidad y las observaciones.
2. *Dado* que un producto tiene pocas unidades, *cuando* el mesero lo consulta, *entonces* el sistema muestra la cantidad restante disponible.
3. *Dado* que un producto está agotado o desactivado, *cuando* el mesero intenta agregarlo, *entonces* el sistema impide la adición e informa al mesero.

---

### **RF-17 — Cálculo del total de la comanda**

**Tipo:** Funcional

**Descripción:** El sistema deberá calcular automáticamente el subtotal (cantidad por precio vigente de cada producto) y la suma total de una comanda, aplicando los descuentos autorizados aplicables, como los derivados de la acumulación de puntos de fidelidad.

**Origen:** El cliente Pepito Pérez — dueño, entrevista sobre cobro, caja y canje de recompensas.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que una comanda tiene productos, *cuando* se agrega, quita o cambia una cantidad, *entonces* el subtotal y el total se recalculan de inmediato.
2. *Dado* que se aplica un descuento autorizado, *cuando* se refleja en la comanda, *entonces* el total muestra el descuento correctamente.
3. *Dado* que se intenta aplicar un descuento no autorizado o vencido, *cuando* el sistema lo evalúa, *entonces* lo rechaza sin modificar el total.
4. *Dado* que se consulta el total de la comanda, *cuando* se compara con un cálculo manual de la misma comanda, *entonces* el resultado coincide exactamente.

---

### **RF-18 — Envío de comandas a cocina**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir al mesero confirmar una comanda y transmitirla a las pantallas de cocina, descontando del inventario los productos pedidos.

**Origen:** El cliente Pepito Pérez — dueño, entrevista.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que una comanda tiene al menos un producto, *cuando* el mesero la confirma, *entonces* aparece en las pantallas de cocina en menos de 3 segundos con estado "Pendiente".
2. *Dado* que una comanda está vacía, *cuando* el mesero intenta confirmarla, *entonces* el sistema no la envía.
3. *Dado* que falla la conexión al intentar confirmar, *cuando* ocurre el error, *entonces* el sistema avisa al mesero y no marca la comanda como enviada.

---

### **RF-19 — Consulta de pedidos y estados**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir a los usuarios autorizados consultar las comandas registradas con su mesa, los productos, el total y el estado actual (Pendiente, En preparación o Listo).

**Origen:** El cliente Pepito Pérez — dueño, entrevista.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que un usuario autorizado abre la lista de comandas, *cuando* la consulta, *entonces* ve todas las del día con su estado actual.
2. *Dado* que se aplica un filtro por estado o por mesa, *cuando* el filtro se ejecuta, *entonces* solo aparecen las comandas que cumplen el criterio.
3. *Dado* que un usuario sin permiso intenta acceder a la consulta, *cuando* intenta ingresar, *entonces* el sistema deniega el acceso.

---

### **RF-20 — Modificación de comandas enviadas**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir al mesero agregar productos a una comanda ya enviada y aún no pagada, validando las existencias de inventario. Los productos ya enviados no se eliminan y la comanda conserva el registro original.

**Origen:** El cliente Pepito Pérez — dueño, entrevista sobre clientes que añaden pedidos después del cierre de la comanda.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que una comanda está enviada y no pagada, *cuando* el mesero agrega un producto con existencias suficientes, *entonces* la comanda se actualiza y el total se recalcula.
2. *Dado* que un producto no tiene existencias suficientes, *cuando* el mesero intenta agregarlo, *entonces* el sistema rechaza la adición.
3. *Dado* que una comanda ya está pagada, *cuando* el mesero intenta modificarla, *entonces* el sistema no lo permite.

---

### **RF-21 — Notificación de cambios a cocina**

**Tipo:** Funcional

**Descripción:** El sistema deberá notificar a cocina cada adición o modificación de una comanda ya enviada, resaltando visualmente los productos añadidos para distinguirlos de los originales.

**Origen:** El cliente Pepito Pérez — dueño, entrevista para evitar pérdida de información y confusión.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que a una comanda ya enviada se le agrega un producto, *cuando* ocurre la modificación, *entonces* en menos de 3 segundos la pantalla de cocina muestra una alerta y marca el producto nuevo como "Agregado".
2. *Dado* que llega el cambio a cocina, *cuando* se muestra, *entonces* los productos originales conservan su estado previo.

---

### **RF-22 — Asociación de clientes a comandas**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir al mesero asociar una comanda a un cliente registrado mediante su número de documento, para que el cliente acumule puntos de fidelidad y pueda canjear recompensas.

**Origen:** El cliente Pepito Pérez — dueño, entrevista.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que el mesero ingresa un número de documento registrado, *cuando* lo busca, *entonces* la comanda queda asociada al cliente y se muestran sus puntos de fidelidad y sus recompensas disponibles.
2. *Dado* que el documento no está registrado, *cuando* el mesero lo ingresa, *entonces* el sistema lo informa y permite continuar sin asociar al cliente.

---

### **RF-COMANDA-ESTADO — Ciclo de vida del estado de la comanda**

**Tipo:** Funcional

**Descripción:** El sistema deberá gestionar el ciclo de vida de cada comanda mediante el campo `estado`, con cinco valores y transiciones autorizadas por rol. La secuencia completa es: `pendiente` (comanda creada, no enviada a cocina) → `enviada` (mesero confirma y despacha a cocina) → `en_preparacion` (cocinero inicia la preparación) → `lista` (cocinero termina la preparación) → `cerrada` (cajero confirma el pago). Solo el actor autorizado puede ejecutar cada transición; cualquier intento de transición no permitida es rechazado con código de error 400.

**Origen:** Diseño del equipo de desarrollo — el estado de la comanda es un concepto transversal a los módulos de mesero, cocina y caja.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el mesero confirma el envío de una comanda con estado `pendiente`, *cuando* lo hace, *entonces* el estado cambia a `enviada` y la comanda aparece en la pantalla de cocina (RF-18).
2. *Dado* que el cocinero inicia la preparación de una comanda con estado `enviada`, *cuando* confirma el cambio, *entonces* el estado cambia a `en_preparacion` (RF-25).
3. *Dado* que el cocinero termina la preparación de una comanda con estado `en_preparacion`, *cuando* confirma el cambio, *entonces* el estado cambia a `lista` y el mesero recibe un aviso (RF-26).
4. *Dado* que el cajero confirma el pago de una comanda con estado `lista`, *cuando* lo registra, *entonces* el estado cambia a `cerrada` (RF-28).
5. *Dado* que cualquier usuario intenta ejecutar una transición de estado no autorizada para su rol, *cuando* lo intenta, *entonces* el sistema rechaza la acción con código de error 400.

---

### 1.4. Gestión de cocina

---

### **RF-23 — Visualización de pedidos en cocina**

**Tipo:** Funcional

**Descripción:** El sistema deberá mostrar en las pantallas de cocina todas las comandas confirmadas por los meseros, ordenadas por hora de llegada.

**Origen:** El cliente Pepito Pérez — dueño, entrevista.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que una comanda ha sido confirmada, *cuando* aparece en cocina, *entonces* se muestra en todas las pantallas conectadas, ordenada de la más antigua a la más reciente.
2. *Dado* que una comanda no ha sido confirmada, *cuando* se consulta la pantalla de cocina, *entonces* dicha comanda no aparece.

---

### **RF-24 — Detalle de las comandas en cocina**

**Tipo:** Funcional

**Descripción:** El sistema deberá mostrar en cada comanda de cocina el número de mesa, los productos, las cantidades y las observaciones del cliente, con un tamaño de texto legible a distancia.

**Origen:** El cliente Pepito Pérez — dueño, entrevista (que se vea y se entienda bien).

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que una comanda se muestra en la pantalla de cocina, *cuando* el cocinero la consulta, *entonces* se ven el número de mesa, los productos, las cantidades y las observaciones sin truncar el texto.
2. *Dado* que una comanda incluye observaciones, *cuando* se muestra, *entonces* las observaciones aparecen resaltadas.

---

### **RF-25 — Actualización del estado de preparación**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir al cocinero avanzar el estado de una comanda según las dos transiciones autorizadas para su rol: de `enviada` a `en_preparacion` al iniciar la preparación, y de `en_preparacion` a `lista` al terminarla. El cocinero no puede ejecutar ninguna otra transición; en particular, el cierre de la comanda (`lista → cerrada`) es responsabilidad exclusiva del cajero al confirmar el pago (RF-28).

**Origen:** Juan Sebastián Aragón Campo, anexo.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que una comanda tiene estado `enviada` y el cocinero confirma el inicio de la preparación, *cuando* ejecuta el cambio, *entonces* el estado pasa a `en_preparacion` y el cambio se propaga a todos los dispositivos conectados en menos de 3 segundos.
2. *Dado* que una comanda tiene estado `en_preparacion` y el cocinero confirma que terminó, *cuando* ejecuta el cambio, *entonces* el estado pasa a `lista` y el cambio se propaga a todos los dispositivos conectados en menos de 3 segundos.
3. *Dado* que el cocinero intenta ejecutar cualquier transición no autorizada para su rol (por ejemplo, `lista → cerrada`), *cuando* lo intenta, *entonces* el sistema rechaza la acción con código de error 400.
4. *Dado* que un usuario sin rol de cocinero intenta cambiar el estado de preparación de una comanda, *cuando* lo intenta, *entonces* el sistema deniega el acceso.

---

### **RF-26 — Sincronización de estados de cocina**

**Tipo:** Funcional

**Descripción:** El sistema deberá reflejar en tiempo real, en todos los dispositivos conectados (tabletas, televisores y teléfonos), los cambios confirmados en las comandas, sin que se registre el pedido de nuevo.

**Origen:** Juan Sebastián Aragón Campo, anexo (llegada instantánea y sin errores de transcripción).

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que se produce un cambio de estado o una modificación de comanda, *cuando* ocurre, *entonces* todos los dispositivos conectados lo muestran en menos de 3 segundos sin recargar la pantalla.

---

### **RF-27 — Historial de pedidos**

**Tipo:** Funcional

**Descripción:** El sistema deberá conservar cada pedido y cada cambio de estado o modificación, con la fecha, la hora y el usuario que lo realizó.

**Origen:** El cliente Pepito Pérez — dueño, entrevista (tener registro de todo).

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que se consulta cualquier pedido, *cuando* el administrador abre su historial, *entonces* puede ver cada cambio con la fecha, la hora y el usuario responsable.
2. *Dado* que un usuario intenta editar o eliminar un registro del historial, *cuando* lo intenta, *entonces* el sistema no lo permite.

---

### 1.5. Gestión de caja y movimientos de dinero

---

### **RF-28 — Registro de pagos**

**Tipo:** Funcional

**Descripción:** El sistema deberá registrar cada pago de una comanda con su identificador, valor, fecha y hora, medio de pago (efectivo o transferencia) y el usuario que lo confirmó, y sumarlo al saldo que le corresponde (caja en efectivo o saldo de transferencias).

**Origen:** El cliente Pepito Pérez — dueño, entrevista (control de caja y saldo de transferencias separado).

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que se confirma un pago, *cuando* queda registrado, *entonces* incluye todos sus datos y suma al saldo correcto: efectivo a la caja, transferencia al saldo de transferencias.
2. *Dado* que una comanda ya fue pagada, *cuando* se intenta registrar un segundo pago sobre ella, *entonces* el sistema no lo admite.

---

### **RF-29 — Registro de pagos en efectivo**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir exclusivamente a los cajeros confirmar pagos en efectivo.

**Origen:** El cliente Pepito Pérez — dueño, entrevista (solo los cajeros aceptan efectivo); Juan Sebastián Aragón Campo, anexo.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que un usuario con rol de cajero confirma un pago en efectivo, *cuando* lo registra, *entonces* este se suma a la caja a su nombre.
2. *Dado* que un mesero u otro rol intenta confirmar un pago en efectivo, *cuando* lo intenta, *entonces* la opción no está disponible y el sistema rechaza la operación si se intenta por otra vía.

---

### **RF-30 — Visualización del código QR y confirmación de transferencia**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir a los meseros y cajeros mostrar el código QR de pago y registrar la confirmación de una transferencia una vez verificada su recepción. El valor confirmado se suma al saldo de transferencias, independiente del efectivo.

**Origen:** El cliente Pepito Pérez — dueño, entrevista; Juan Sebastián Aragón Campo, anexo.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que un mesero o cajero con una comanda lista para pagar selecciona el pago por transferencia, *cuando* lo solicita, *entonces* el sistema muestra el código QR en pantalla.
2. *Dado* que el mesero o cajero confirma la transferencia, *cuando* la confirma, *entonces* el pago queda registrado como transferencia y suma al saldo de transferencias, no a la caja.
3. *Dado* que una transferencia ya fue confirmada, *cuando* se intenta confirmar de nuevo, *entonces* el sistema no lo permite.

---

### **RF-31 — Saldos diferenciados por medio de pago**

**Tipo:** Funcional

**Descripción:** El sistema deberá mantener registros y saldos diferenciados para efectivo y transferencias, evitando que los movimientos de un medio alteren directamente el saldo del otro.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que se registra un pago en efectivo, *cuando* se actualiza el saldo, *entonces* solo aumenta el saldo en efectivo y el de transferencias no cambia.
2. *Dado* que se confirma un pago por transferencia, *cuando* se actualiza el saldo, *entonces* solo aumenta el saldo de transferencias y el de efectivo no cambia.
3. *Dado* que se ejecuta un retiro de caja, *cuando* se actualiza el saldo, *entonces* solo disminuye el saldo en efectivo.

---

### **RF-32 — Registro de ingresos a la caja**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir exclusivamente al administrador registrar ingresos de dinero a la caja, indicando valor, fecha y concepto.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el administrador tiene sesión iniciada, *cuando* registra un ingreso con valor mayor a cero, fecha y concepto, *entonces* el saldo en efectivo aumenta en ese valor y el ingreso queda en el historial.
2. *Dado* que un usuario con rol distinto a administrador accede a la caja, *cuando* intenta registrar un ingreso, *entonces* no dispone de esa opción.
3. *Dado* que el administrador deja vacío el valor, la fecha o el concepto, o ingresa un valor menor o igual a cero, *cuando* intenta registrar el ingreso, *entonces* el sistema no lo registra e indica el campo inválido.

---

### **RF-33 — Retiros directos por el administrador**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir exclusivamente al administrador registrar y ejecutar retiros directos de dinero de la caja.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que el administrador tiene sesión iniciada, *cuando* registra un retiro con valor mayor a cero, *entonces* el saldo en efectivo disminuye de inmediato en ese valor y el retiro queda en el historial.
2. *Dado* que un usuario con rol distinto a administrador accede a la caja, *cuando* intenta un retiro directo, *entonces* no dispone de esa opción.

---

### **RF-34 — Solicitudes de retiro por cajeros**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir a los cajeros enviar solicitudes de retiro que incluyan valor y motivo, sin modificar el saldo antes de su aprobación.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que un cajero tiene sesión iniciada, *cuando* ingresa un valor mayor a cero y un motivo y envía la solicitud, *entonces* el sistema la registra con estado "Pendiente" y muestra una confirmación de envío.
2. *Dado* que existe una solicitud de retiro pendiente, *cuando* se consulta el saldo de caja, *entonces* el saldo es igual al que había antes de enviar la solicitud.
3. *Dado* que el cajero deja vacío el valor o el motivo, o ingresa un valor menor o igual a cero, *cuando* intenta enviar la solicitud, *entonces* el sistema no la registra e indica cuál campo es inválido.

---

### **RF-35 — Notificación push de solicitudes de retiro**

**Tipo:** Funcional

**Descripción:** El sistema deberá enviar una notificación push al dispositivo del administrador, esté o no abierta la aplicación, cuando un cajero registre una solicitud de retiro pendiente.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el administrador tiene la aplicación cerrada o en segundo plano, *cuando* un cajero registra una solicitud de retiro pendiente, *entonces* el dispositivo del administrador recibe una notificación con el cajero, el valor y el motivo.
2. *Dado* que el administrador tiene la aplicación abierta, *cuando* un cajero registra una solicitud de retiro pendiente, *entonces* el administrador ve el aviso en pantalla.
3. *Dado* que el dispositivo del administrador no tenía conexión a Internet, *cuando* la recupera, *entonces* recibe la notificación de las solicitudes pendientes.
4. *Dado* que el administrador no atendió la notificación, *cuando* abre la aplicación, *entonces* la solicitud sigue visible como pendiente hasta que sea aprobada o rechazada.

---

### **RF-36 — Aprobación o rechazo de solicitudes de retiro**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir al administrador aprobar o rechazar las solicitudes de retiro de los cajeros y registrar la decisión.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que existe una solicitud de retiro pendiente, *cuando* el administrador la aprueba, *entonces* el estado cambia a "Aprobada", el saldo en efectivo disminuye en el valor solicitado y la decisión queda registrada con fecha y administrador.
2. *Dado* que existe una solicitud de retiro pendiente, *cuando* el administrador la rechaza, *entonces* el estado cambia a "Rechazada", el saldo no cambia y la decisión queda registrada.
3. *Dado* que una solicitud ya fue aprobada o rechazada, *cuando* el administrador intenta resolverla de nuevo, *entonces* el sistema no lo permite.

---

### **RF-37 — Trazabilidad de movimientos financieros**

**Tipo:** Funcional

**Descripción:** El sistema deberá registrar el valor, concepto, fecha y solicitante de cada movimiento financiero, así como la autorización del administrador en los retiros.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que se consulta el detalle de cualquier movimiento registrado (pago, ingreso o retiro), *cuando* el usuario lo abre, *entonces* se muestran el valor, el concepto, la fecha y el solicitante.
2. *Dado* que se consulta el detalle de un retiro aprobado por el administrador, *cuando* el usuario lo abre, *entonces* se muestra también la autorización del administrador.

---

### **RF-38 — Consulta de caja por el cajero**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir al cajero consultar los pagos y movimientos de caja del día, conforme a los permisos de su rol.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que un cajero tiene sesión iniciada, *cuando* abre la consulta de caja, *entonces* ve los pagos y movimientos registrados en el día en curso.
2. *Dado* que un cajero usa la consulta de caja, *cuando* navega por ella, *entonces* no dispone de las acciones reservadas al administrador (registrar ingresos, retiros directos o resolver solicitudes).

---

### **RF-39 — Consulta financiera por el administrador**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir al administrador consultar los saldos actuales y el historial de ingresos, pagos, retiros y demás movimientos financieros registrados.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el administrador tiene sesión iniciada, *cuando* abre la consulta financiera, *entonces* ve el saldo actual en efectivo y el saldo actual en transferencias por separado.
2. *Dado* que el administrador consulta el historial, *cuando* lo abre, *entonces* ve todos los ingresos, pagos, retiros y demás movimientos registrados, con su fecha.

---

### **RF-40 — Visualización del código QR en dispositivos**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir a meseros y cajeros visualizar desde sus dispositivos el código QR configurado por el establecimiento para recibir transferencias.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que un mesero o cajero con sesión iniciada selecciona el pago por transferencia, *cuando* lo solicita, *entonces* el sistema muestra en pantalla el código QR configurado.
2. *Dado* que el código QR se muestra en pantalla, *cuando* el cliente lo escanea, *entonces* dirige a la cuenta de recepción de transferencias del establecimiento.

---

### **RF-41 — Registro manual de confirmación de transferencia**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir a los meseros y cajeros registrar manualmente la confirmación de una transferencia, mediante un botón, después de verificar visualmente el comprobante presentado por el cliente, sin requerir integración con una pasarela de pagos.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que hay un pago por transferencia pendiente de confirmar, *cuando* el mesero o cajero presiona el botón de confirmación, *entonces* el sistema registra el pago como confirmado y guarda el cambio en la base de datos.
2. *Dado* que hay un pago por transferencia que no ha sido confirmado, *cuando* se consulta el saldo de transferencias, *entonces* ese pago no está incluido en el saldo.
3. *Dado* que un usuario con un rol distinto a mesero o cajero consulta un pago pendiente, *cuando* lo abre, *entonces* no dispone del botón de confirmación.

---

### **RF-42 — Actualización del saldo de transferencias**

**Tipo:** Funcional

**Descripción:** El sistema deberá incorporar al registro de transferencias el valor de cada pago confirmado y actualizar el saldo correspondiente.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el saldo de transferencias es $S$ y se confirma una transferencia de valor $V$, *cuando* se registra, *entonces* el saldo pasa a ser $S + V$ y el valor $V$ queda en el registro de transferencias.
2. *Dado* que hay un pago por transferencia sin confirmar, *cuando* se consulta el saldo de transferencias, *entonces* el saldo no cambia.

---

### **RF-43 — Prevención de doble contabilización de transferencias**

**Tipo:** Funcional

**Descripción:** El sistema deberá impedir que una misma transferencia se contabilice más de una vez para la misma operación de pago.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que un pago por transferencia ya fue confirmado, *cuando* un mesero o cajero intenta confirmarlo otra vez (por ejemplo, con doble pulsación), *entonces* el sistema no lo vuelve a sumar e informa que ya fue confirmado.
2. *Dado* que un pago ya fue confirmado, *cuando* se consulta el saldo de transferencias, *entonces* el valor de ese pago aparece una sola vez.

---

### **RF-44 — Cierre de caja**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir a cualquier cajero ejecutar el cierre de caja del día mediante un botón de cierre y una confirmación de la acción.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que un cajero tiene sesión iniciada, *cuando* presiona el botón de cierre de caja, *entonces* el sistema solicita confirmar la acción.
2. *Dado* que el cajero confirma el cierre, *cuando* el sistema lo procesa, *entonces* el cierre queda registrado con la fecha y el cajero que lo ejecutó.
3. *Dado* que el cajero cancela la confirmación, *cuando* vuelve a la caja, *entonces* no se registra ningún cierre.

---

### **RF-45 — Cálculo de ingresos, egresos y saldos al cierre**

**Tipo:** Funcional

**Descripción:** El sistema deberá calcular los ingresos, egresos y saldos finales de la jornada, diferenciando efectivo y transferencias.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que se ejecuta el cierre, *cuando* el sistema lo procesa, *entonces* muestra el total de ingresos, el total de egresos y el saldo final de efectivo, cada uno por separado de los de transferencias.
2. *Dado* que se comparan los totales del cierre con el historial de movimientos del día, *cuando* se verifica, *entonces* coinciden con la suma de esos movimientos.

---

### **RF-47 — Registro de base y retiro al cierre de jornada**

**Tipo:** Funcional

**Descripción:** Durante el cierre, el sistema deberá permitir al administrador registrar el valor de efectivo que queda como base de la siguiente jornada y el valor del excedente que retira.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que el administrador está cerrando la jornada e ingresó una base y un retiro cuya suma no supera el efectivo disponible, *cuando* presiona "Confirmar", *entonces* el sistema guarda la base y el retiro con fecha y usuario y muestra el mensaje "Base y retiro registrados".
2. *Dado* que la suma de la base y el retiro es mayor al efectivo disponible, *cuando* el administrador presiona "Confirmar", *entonces* el sistema no guarda nada y muestra "La base y el retiro superan el efectivo disponible ($XXX)".

---

### **RF-48 — Informe de cierre de jornada**

**Tipo:** Funcional

**Descripción:** Al cerrar la jornada, el sistema deberá generar y guardar un informe con saldo inicial, ingresos, egresos, base reservada y saldo final, separados por efectivo y transferencia.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el administrador completó los pasos del cierre, *cuando* presiona "Cerrar jornada", *entonces* el sistema genera y guarda un informe con saldo inicial, ingresos, egresos, base reservada y saldo final, separados por efectivo y transferencia, donde saldo final = saldo inicial + ingresos − egresos.
2. *Dado* que existe el informe de una jornada cerrada y ya se abrió una nueva jornada, *cuando* el administrador consulta los informes anteriores, *entonces* el sistema muestra el informe de esa jornada sin cambios.

---

### **RF-49 — Apertura de nueva jornada**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir iniciar una nueva jornada tomando como saldo inicial de efectivo la base registrada en el cierre anterior.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que la jornada anterior está cerrada con una base de $[X]$, *cuando* el administrador presiona "Abrir jornada", *entonces* el sistema crea la nueva jornada con saldo inicial de efectivo de $[X]$ y conserva las jornadas anteriores consultables.
2. *Dado* que la jornada anterior no está cerrada, *cuando* el administrador intenta abrir una nueva jornada, *entonces* el sistema muestra "Debes cerrar la jornada anterior antes de abrir una nueva."

---

### 1.6. Fidelización de clientes

---

### **RF-50 — Registro de clientes**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir registrar un cliente con nombre, apellido, número de documento y número de celular, exigiendo que acepte el tratamiento de sus datos personales (Ley 1581 de 2012).

**Origen:** El cliente Pepito Pérez — dueño; acta de constitución, 29 de septiembre del 2026.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el cliente ingresó nombre, apellido, número de documento y celular, y aceptó el tratamiento de datos personales, *cuando* presiona "Registrarme", *entonces* el sistema crea el registro con 0 puntos de fidelidad y muestra "Registro exitoso. ¡Ya puedes empezar a acumular tus puntos de fidelidad!" en menos de 4 minutos desde que inició el formulario.
2. *Dado* que falta algún dato o el cliente no aceptó el tratamiento de datos, *cuando* presiona "Registrarme", *entonces* el sistema no guarda el registro, resalta lo que falta y muestra "Completa todos los datos y acepta el tratamiento de datos personales."
3. *Dado* que ya existe un cliente con ese número de documento, *cuando* otro registro intenta usar el mismo documento, *entonces* el sistema muestra "Este documento ya está registrado."

---

### **RF-51 — Búsqueda de clientes por documento**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir a los usuarios autorizados (mesero y administrador) buscar un cliente por su número de documento.

**Origen:** El cliente Pepito Pérez — dueño; acta de constitución, 29 de septiembre del 2026.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el cliente está registrado, *cuando* el mesero o el administrador ingresa su número de documento, *entonces* el sistema muestra su nombre y sus puntos de fidelidad en máximo 2 segundos.
2. *Dado* que el documento no está registrado, *cuando* el usuario lo busca, *entonces* el sistema muestra "Cliente no encontrado" y ofrece la opción de registrarlo.

---

### **RF-52 — Acumulación de puntos de fidelidad**

**Tipo:** Funcional

**Descripción:** El sistema deberá incrementar en 1 los puntos de fidelidad de un cliente cada vez que se confirme el pago de una comanda asociada a él.

**Origen:** El cliente Pepito Pérez — dueño; acta de constitución, 29 de septiembre del 2026.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que un cliente tiene 2 puntos de fidelidad, *cuando* se confirma el pago de una comanda asociada a él, *entonces* el sistema aumenta sus puntos a 3.
2. *Dado* que la comanda del cliente no tiene un pago confirmado, *cuando* el cliente termina su visita, *entonces* el sistema no modifica sus puntos de fidelidad.

---

### **RF-54 — Configuración de niveles de recompensa**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir al administrador definir los puntos mínimos requeridos para acceder a cada recompensa y el costo en puntos que se descuenta al canjearla.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que el administrador ingresa los puntos mínimos requeridos, el costo en puntos y una recompensa, *cuando* presiona "Guardar nivel", *entonces* el sistema guarda el nivel y lo aplica desde ese momento.
2. *Dado* que ya existe un nivel con esos puntos mínimos requeridos, *cuando* el administrador intenta guardar otro con los mismos puntos, *entonces* el sistema muestra "Ya existe un nivel para este umbral de puntos."

---

### **RF-55 — Consulta de los puntos de fidelidad por el cliente**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir al cliente registrado consultar sus puntos de fidelidad actuales. Las recompensas y condiciones de canje se agregan cuando se incluyan en el alcance.

**Origen:** El cliente Pepito Pérez — dueño; acta de constitución, 29 de septiembre del 2026.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el cliente registrado inicia sesión, *cuando* abre la sección "Mis puntos de fidelidad", *entonces* el sistema muestra sus puntos actuales en máximo 2 segundos, igual a los registrados tras su último pago confirmado.
2. *Dado* que el cliente se registró pero aún no tiene pagos confirmados, *cuando* abre la sección "Mis puntos de fidelidad", *entonces* el sistema muestra 0 puntos y el mensaje "Haz tu primer pedido para empezar a acumular puntos de fidelidad."

---

### **RF-56 — Solicitud de recompensa por el cliente**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir al cliente solicitar una recompensa disponible mientras se crea su comanda.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que un cliente tiene puntos de fidelidad suficientes para acceder a ciertas recompensas, *cuando* se crea su comanda, *entonces* el sistema muestra solo las recompensas que sus puntos habilitan.
2. *Dado* que el cliente tiene recompensas disponibles, *cuando* selecciona una, *entonces* la comanda la muestra como "Recompensa solicitada, pendiente de aplicar".

---

### **RF-57 — Consulta de los puntos de fidelidad por el mesero**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir al mesero consultar los puntos de fidelidad de un cliente después de identificarlo por su número de documento. Las recompensas disponibles se incluyen cuando entren en el alcance.

**Origen:** El cliente Pepito Pérez — dueño; acta de constitución, 29 de septiembre del 2026.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que el cliente está registrado, *cuando* el mesero ingresa su número de documento, *entonces* el sistema muestra los puntos de fidelidad del cliente en máximo 2 segundos.
2. *Dado* que el usuario no es mesero ni administrador, *cuando* intenta consultar los puntos de fidelidad de un cliente, *entonces* el sistema le niega el acceso y muestra "No tienes permiso para esta acción."

---

### **RF-58 — Aplicación de recompensa por el mesero**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir al mesero aplicar a una comanda la recompensa que el cliente seleccionó, siempre que se cumplan sus condiciones de uso.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que el cliente seleccionó una recompensa y cumple sus condiciones, *cuando* el mesero presiona "Aplicar recompensa", *entonces* el sistema aplica la recompensa y actualiza el total de la comanda.
2. *Dado* que el cliente no cumple las condiciones de la recompensa, *cuando* el mesero intenta aplicarla, *entonces* el sistema no la aplica y explica el motivo.

---

### **RF-59 — Registro de canjes de recompensas**

**Tipo:** Funcional

**Descripción:** El sistema deberá registrar cada canje confirmado y marcar la recompensa como usada, para que no se pueda canjear de nuevo cuando es de un solo uso.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que se aplicó una recompensa a una comanda, *cuando* el canje se confirma, *entonces* el sistema lo guarda con cliente, recompensa, fecha y usuario, y marca la recompensa como usada si es de un solo uso.
2. *Dado* que una recompensa de un solo uso ya fue canjeada, *cuando* se intenta canjear de nuevo, *entonces* el sistema lo rechaza y muestra "Esta recompensa ya fue utilizada."
3. *Dado* que se confirma el canje de una recompensa, *cuando* se registra, *entonces* el sistema descuenta del cliente el costo en puntos configurado para esa recompensa y el nuevo total de puntos queda visible de inmediato.

---

### **RF-60 — Gestión de promociones y recompensas**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir al administrador crear, modificar, publicar y desactivar promociones y recompensas, con sus condiciones y fechas de vigencia.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que el administrador ingresa las condiciones, la fecha de inicio y la fecha de fin, *cuando* presiona "Publicar", *entonces* el sistema guarda la promoción y la muestra a los clientes mientras esté vigente.
2. *Dado* que una promoción venció o fue desactivada por el administrador, *cuando* un cliente consulta las promociones, *entonces* el sistema no la muestra.
3. *Dado* que la fecha de fin es anterior a la de inicio, *cuando* el administrador intenta publicar, *entonces* el sistema muestra "La fecha de fin debe ser posterior a la de inicio."

---

### **RF-61 — Notificaciones de fidelización**

**Tipo:** Funcional

**Descripción:** El sistema deberá generar notificaciones para informar al cliente sobre nuevas recompensas disponibles y promociones publicadas que cumplan las condiciones de comunicación configuradas.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que un cliente cumple las condiciones para recibir una notificación, *cuando* se publica una promoción aplicable o se habilita una nueva recompensa para él, *entonces* el sistema genera la notificación correspondiente.
2. *Dado* que un cliente no cumple las condiciones de una promoción, *cuando* se publica dicha promoción, *entonces* el sistema no le envía una notificación personalizada como si fuera elegible.
3. *Dado* que se genera una notificación, *cuando* el cliente consulta sus notificaciones, *entonces* puede identificar la promoción o recompensa que la originó.

---

### **RF-62 — Consulta de promociones**

**Tipo:** Funcional

**Descripción:** El sistema deberá permitir a los clientes registrados consultar las promociones publicadas y vigentes desde su aplicación.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que un cliente registrado ha iniciado sesión, *cuando* accede a la sección de promociones, *entonces* el sistema muestra las promociones publicadas y vigentes.
2. *Dado* que una promoción está vencida, inactiva o no publicada, *cuando* el cliente consulta las promociones vigentes, *entonces* dicha promoción no aparece en el listado.
3. *Dado* que una promoción está vigente, *cuando* el cliente consulta su información, *entonces* puede visualizar sus condiciones y el periodo de vigencia, siempre que estos datos hayan sido configurados.

---

## 2. Requerimientos no funcionales

### 2.1. Rendimiento

---

### **RNF-01 — Tiempo de respuesta del menú**

**Tipo:** No funcional (Rendimiento)

**Descripción:** El sistema deberá mostrar el menú, los precios y las existencias en un tiempo máximo de 2 segundos en al menos el 95 % de las consultas, bajo condiciones normales de conectividad y carga.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* un conjunto de consultas al menú bajo condiciones normales de conectividad y carga, *cuando* se ejecutan las pruebas, *entonces* al menos el 95 % muestran el menú, los precios y las existencias en un tiempo máximo de 2 segundos.
2. *Dado* que se muestran los productos, *cuando* el usuario los consulta, *entonces* los precios y las existencias corresponden a la información registrada en el sistema.

---

### **RNF-02 — Actualización de comandas**

**Tipo:** No funcional (Rendimiento)

**Descripción:** El sistema deberá reflejar las comandas confirmadas y sus modificaciones en las pantallas de cocina en un tiempo máximo de 3 segundos en al menos el 95 % de los casos, bajo condiciones normales de conectividad.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que una comanda se confirma o modifica, *cuando* se mide el tiempo hasta su visualización en cocina, *entonces* al menos el 95 % de las operaciones se reflejan en un máximo de 3 segundos.
2. *Dado* que una modificación de comanda llega a cocina, *cuando* se actualiza la pantalla, *entonces* se muestran los cambios registrados sin duplicar los productos originales.

---

### **RNF-03 — Procesamiento de operaciones**

**Tipo:** No funcional (Rendimiento)

**Descripción:** El sistema deberá procesar las operaciones de consulta y registro de pagos, inventario y movimientos de caja en un tiempo máximo de 2 segundos en al menos el 95 % de las solicitudes.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* un conjunto de solicitudes de consulta y registro de pagos, inventario y movimientos de caja, *cuando* se ejecutan bajo las condiciones de carga definidas, *entonces* al menos el 95 % se procesan en un tiempo máximo de 2 segundos.
2. *Dado* que una operación se procesa correctamente, *cuando* el sistema responde al usuario, *entonces* la información mostrada corresponde al resultado registrado.

---

### **RNF-04 — Acceso simultáneo**

**Tipo:** No funcional (Rendimiento)

**Descripción:** El sistema deberá permitir la conexión simultánea de al menos 30 usuarios y dispositivos sin superar los tiempos de respuesta establecidos, bajo las condiciones de carga definidas para las pruebas.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* un entorno de pruebas con 30 usuarios y dispositivos conectados simultáneamente, *cuando* realizan operaciones concurrentes, *entonces* el sistema mantiene los tiempos de respuesta establecidos en RNF-01, RNF-02 y RNF-03.
2. *Dado* que cada usuario tiene una sesión activa, *cuando* se ejecutan operaciones simultáneas autorizadas, *entonces* el sistema procesa las solicitudes sin mezclar la información de diferentes usuarios.

---

### 2.2. Seguridad y control de acceso

---

### **RNF-05 — Protección de las credenciales**

**Tipo:** No funcional (Seguridad)

**Descripción:** El sistema deberá almacenar las contraseñas mediante mecanismos seguros de hash diseñados para contraseñas, evitando su almacenamiento en texto plano.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que se consulta el almacenamiento de credenciales de un usuario registrado, *cuando* se verifica, *entonces* su contraseña no se encuentra almacenada en texto plano.
2. *Dado* que una contraseña está almacenada, *cuando* se verifica mediante el mecanismo de autenticación del sistema, *entonces* el sistema puede validarla sin necesidad de recuperar su valor original.
3. *Dado* que se crea la cuenta de un usuario, *cuando* se registra, *entonces* la contraseña se procesa mediante el mecanismo seguro de hash configurado.

---

### **RNF-06 — Protección de las comunicaciones**

**Tipo:** No funcional (Seguridad)

**Descripción:** El sistema deberá proteger la transmisión de información entre los dispositivos y el servidor mediante protocolos de comunicación cifrados, como HTTPS/TLS, cuando se encuentre desplegado.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el sistema está desplegado en producción, *cuando* un dispositivo establece comunicación con el servidor, *entonces* la conexión utiliza HTTPS/TLS.
2. *Dado* que se realiza una solicitud mediante HTTP no cifrado, *cuando* accede al servicio desplegado, *entonces* el sistema redirige la solicitud a HTTPS o la rechaza, según la configuración de seguridad establecida.
3. *Dado* que existe una conexión segura, *cuando* se verifica su configuración, *entonces* el certificado y los parámetros TLS cumplen con la configuración de seguridad definida para el despliegue.

---

### **RNF-07 — Control de acceso**

**Tipo:** No funcional (Seguridad y control de acceso)

**Descripción:** El sistema deberá verificar los permisos de cada usuario en el servidor antes de ejecutar operaciones restringidas, evitando que se puedan realizar acciones no autorizadas mediante solicitudes directas.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que un usuario autenticado sin permisos para una operación intenta ejecutarla mediante una solicitud directa al servidor, *cuando* el servidor la recibe, *entonces* rechaza la operación.
2. *Dado* que un usuario con los permisos correspondientes solicita una operación autorizada, *cuando* la ejecuta, *entonces* el sistema permite su ejecución si se cumplen las demás validaciones.
3. *Dado* que un usuario sin sesión válida intenta acceder a una operación protegida, *cuando* hace la solicitud, *entonces* el sistema la rechaza.

---

### **RNF-08 — Protección de la información financiera**

**Tipo:** No funcional (Seguridad y control de acceso)

**Descripción:** El sistema deberá restringir el acceso a los registros financieros según los permisos asignados a cada rol, protegiendo la información de pagos, saldos, retiros y cierres de caja frente a consultas o modificaciones no autorizadas.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que un usuario sin permisos intenta consultar determinada información financiera, *cuando* lo hace, *entonces* el sistema rechaza la consulta.
2. *Dado* que un usuario sin permisos intenta modificar registros financieros, *cuando* lo intenta, *entonces* el sistema rechaza la operación y conserva la información original.
3. *Dado* que un usuario autorizado consulta o modifica información financiera, *cuando* realiza la operación, *entonces* el sistema permite únicamente las acciones correspondientes a los permisos de su rol.

---

### **RNF-09 — Protección de datos personales**

**Tipo:** No funcional (Seguridad y privacidad)

**Descripción:** El sistema deberá proteger los datos personales de los clientes y limitar su consulta y tratamiento a las operaciones autorizadas, de acuerdo con las políticas de privacidad definidas para APPRESSO y la normativa aplicable.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que un usuario sin autorización intenta consultar los datos personales de un cliente, *cuando* lo hace, *entonces* el sistema impide la consulta.
2. *Dado* que un usuario autorizado consulta datos personales, *cuando* accede a ellos, *entonces* el sistema permite únicamente el acceso necesario para las funciones de su rol.
3. *Dado* que un registro contiene datos personales, *cuando* se consulta o utiliza, *entonces* su tratamiento se realiza conforme a las políticas de privacidad y las reglas de protección de datos aplicables.

---

### 2.3. Integridad y confiabilidad de la información

---

### **RNF-10 — Consistencia de las operaciones**

**Tipo:** No funcional (Integridad y confiabilidad de la información)

**Descripción:** El sistema deberá garantizar que las operaciones confirmadas sobre comandas, inventario y caja se registren de manera consistente, evitando que una operación incompleta produzca saldos o existencias incorrectos.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que una operación que modifica una comanda, el inventario o la caja se completa correctamente, *cuando* se verifica, *entonces* todos los cambios correspondientes quedan registrados de manera consistente.
2. *Dado* que una operación falla antes de completarse, *cuando* el sistema procesa el error, *entonces* no deja cambios parciales que generen saldos o existencias incorrectos.
3. *Dado* que una operación queda registrada, *cuando* se consultan los datos afectados, *entonces* los valores corresponden al resultado de la operación confirmada.

---

### **RNF-11 — Prevención de registros duplicados**

**Tipo:** No funcional (Integridad y confiabilidad de la información)

**Descripción:** El sistema deberá contar con mecanismos que impidan contabilizar dos veces una misma operación de pago confirmada o aplicar dos veces un mismo canje de recompensa cuando no esté permitido.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que un pago ya fue confirmado, *cuando* se intenta confirmar nuevamente la misma operación, *entonces* el sistema evita registrar o contabilizar el pago por segunda vez.
2. *Dado* que un canje de recompensa ya fue registrado, *cuando* se intenta ejecutar el mismo canje sin autorización para repetirlo, *entonces* el sistema rechaza la operación.
3. *Dado* que un pago o canje fue procesado correctamente, *cuando* se consulta su historial, *entonces* la operación aparece una sola vez para efectos de contabilización.

---

### **RNF-12 — Trazabilidad de las operaciones**

**Tipo:** No funcional (Integridad y confiabilidad de la información)

**Descripción:** El sistema deberá conservar registros de auditoría de las operaciones críticas, incluyendo el usuario responsable, la fecha, el tipo de operación y los datos necesarios para identificar los cambios realizados.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que se ejecuta una operación crítica, *cuando* ocurre, *entonces* el sistema registra el usuario responsable, la fecha, la hora, el tipo de operación y los datos necesarios para identificar el cambio.
2. *Dado* que existe un registro de auditoría, *cuando* un usuario autorizado consulta el historial, *entonces* puede identificar qué operación se realizó y quién la ejecutó.
3. *Dado* que un usuario sin permisos de administración de auditoría intenta alterar o eliminar un registro histórico, *cuando* lo intenta, *entonces* el sistema rechaza la operación.

---

### **RNF-13 — Conservación del historial**

**Tipo:** No funcional (Integridad y confiabilidad de la información)

**Descripción:** El sistema deberá conservar los registros históricos de inventario, comandas, pagos, movimientos de caja y cierres diarios, sin eliminarlos al iniciar una nueva jornada de trabajo.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que comienza una nueva jornada de trabajo, *cuando* se verifica, *entonces* los registros de inventario, comandas, pagos, movimientos de caja y cierres diarios anteriores permanecen almacenados.
2. *Dado* que existe un registro histórico de una jornada anterior, *cuando* un usuario autorizado lo consulta, *entonces* el sistema permite recuperar la información correspondiente.
3. *Dado* que un usuario sin permisos intenta eliminar registros históricos, *cuando* lo intenta, *entonces* el sistema rechaza la operación y conserva los registros.

---

### **RNF-14 — Copias de seguridad automáticas**

**Tipo:** No funcional (Integridad y confiabilidad de la información)

**Descripción:** El sistema deberá realizar copias de seguridad automáticas de la información almacenada al menos una vez cada 24 horas y permitir verificar la recuperación de los datos mediante pruebas de restauración.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet (conservar el registro de todo "por si algo llega a suceder").

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el sistema está en funcionamiento, *cuando* transcurren 24 horas desde la última copia, *entonces* se genera automáticamente una nueva copia de seguridad, registrada con fecha y hora.
2. *Dado* que existe una copia de seguridad generada, *cuando* se ejecuta una prueba de restauración en un entorno de pruebas, *entonces* se recuperan completos los datos de usuarios, inventario, comandas, pagos, movimientos de caja, cierres y clientes.
3. *Dado* que una copia de seguridad falla, *cuando* termina el proceso, *entonces* el fallo queda en el registro de errores técnicos (RNF-28) y se notifica al responsable técnico.

---

### 2.4. Usabilidad y experiencia de usuario

---

### **RNF-15 — Adaptabilidad a diferentes tamaños de pantalla**

**Tipo:** No funcional (Usabilidad y experiencia de usuario)

**Descripción:** La interfaz deberá adaptarse a los tamaños de pantalla de los teléfonos y las tabletas compatibles, permitiendo consultar la información y ejecutar las funciones autorizadas sin pérdida de contenido.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet (uso de tabletas para meseros y teléfono para el administrador).

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que se usa un teléfono o una tableta compatible, *cuando* el usuario abre cualquier pantalla de su rol, *entonces* el contenido se ajusta al ancho de la pantalla sin desplazamiento horizontal ni elementos cortados.
2. *Dado* que se usa una tableta y el usuario cambia la orientación entre vertical y horizontal, *cuando* ocurre el cambio, *entonces* la interfaz se reorganiza sin perder los datos ingresados, como una comanda en curso.
3. *Dado* que se mide el área de toque de cualquier botón o control táctil, *cuando* se verifica, *entonces* es de al menos 48 × 48 dp.

---

### **RNF-16 — Claridad de la interfaz**

**Tipo:** No funcional (Usabilidad y experiencia de usuario)

**Descripción:** El sistema deberá presentar botones, textos, etiquetas y mensajes de estado claros, facilitando la identificación de las acciones disponibles para cada tipo de usuario.

**Origen:** Equipo de desarrollo, a partir de la entrevista con el cliente Pepito Pérez (personal con distintos roles usando la app en horas de alta demanda).

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que un usuario nuevo de cualquier rol recibe una inducción de máximo 10 minutos, *cuando* intenta completar las tareas principales de su rol (por ejemplo, el mesero crea y envía una comanda), *entonces* las completa sin ayuda en al menos el 80 % de los intentos de la prueba de usabilidad.
2. *Dado* que se completa una acción que modifica datos (enviar comanda, confirmar pago, cerrar caja), *cuando* la app responde, *entonces* muestra un mensaje de estado en lenguaje claro, sin códigos técnicos.
3. *Dado* que se muestra un botón de acción en pantalla, *cuando* el usuario lo ve, *entonces* su texto describe la acción ("Enviar a cocina", "Confirmar pago") en lugar de textos genéricos como "Aceptar" u "OK".

---

### **RNF-17 — Indicadores de disponibilidad de productos**

**Tipo:** No funcional (Usabilidad y experiencia de usuario)

**Descripción:** El sistema deberá diferenciar visualmente los productos disponibles, con existencias bajas y agotados, utilizando textos o indicadores que permitan reconocer su estado sin depender exclusivamente de los colores.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet (mostrar si no hay o quedan pocas unidades, con su cantidad).

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que se muestra un producto en el menú, *cuando* el usuario lo consulta, *entonces*: si sus existencias superan el umbral mínimo, aparece como "Disponible" con su cantidad; si son iguales o inferiores al umbral y mayores a cero, aparece "Pocas unidades" con la cantidad restante; si son cero, aparece "Agotado".
2. *Dado* que la lista de productos se ve en escala de grises, *cuando* el usuario la revisa, *entonces* los tres estados siguen siendo distinguibles por su texto o ícono.
3. *Dado* que se mide el contraste de cualquier indicador de estado con el fondo, *cuando* se verifica, *entonces* es de al menos 4,5:1.

---

### **RNF-18 — Legibilidad de la interfaz de cocina**

**Tipo:** No funcional (Usabilidad y experiencia de usuario)

**Descripción:** La interfaz de cocina deberá presentar de forma legible la identificación de la mesa, los productos, las cantidades, las preferencias del cliente y el estado de preparación, tanto en los dispositivos de visualización seleccionados como en las resoluciones compatibles.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet (que en los televisores de cocina "se vea y entienda bien").

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que una comanda se muestra en el televisor de cocina y el cocinero la observa a 3 metros de distancia, *cuando* la lee, *entonces* puede leer la mesa, los productos, las cantidades y las observaciones.
2. *Dado* que una comanda tiene observaciones, *cuando* se muestra, *entonces* estas aparecen completas, sin truncar y resaltadas con fondo o ícono distinto al resto del texto.
3. *Dado* que una comanda tiene un estado asignado, *cuando* se muestra, *entonces* su estado aparece escrito ("Pendiente", "En preparación", "Listo") y no solo representado por color.
4. *Dado* que una comanda tiene productos agregados después del envío, *cuando* se muestra, *entonces* los productos nuevos se distinguen de los originales (RF-21).

---

### **RNF-19 — Mensajes de error descriptivos**

**Tipo:** No funcional (Usabilidad y experiencia de usuario)

**Descripción:** El sistema deberá informar al usuario cuando una operación no pueda completarse, indicando la causa conocida y, cuando sea posible, la acción necesaria para resolver el problema.

**Origen:** Equipo de desarrollo.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que una operación falla por una causa conocida (sin existencias, sin conexión, sin permisos o dato inválido), *cuando* el usuario la intenta, *entonces* el mensaje indica la causa y qué puede hacer (por ejemplo, "Sin conexión. Verifica tu red e intenta de nuevo").
2. *Dado* que se muestra cualquier mensaje de error, *cuando* el usuario lo ve, *entonces* no incluye trazas técnicas, códigos internos ni datos sensibles.
3. *Dado* que existe un error de validación en un formulario, *cuando* el usuario intenta guardar, *entonces* se señala el campo específico con el problema y se conservan los demás datos ingresados.

---

### 2.5. Disponibilidad y recuperación

---

### **RNF-20 — Disponibilidad del servicio**

**Tipo:** No funcional (Disponibilidad y recuperación)

**Descripción:** El sistema deberá alcanzar una disponibilidad mensual objetivo del 99 %, excluyendo los periodos de mantenimiento programado acordados y las interrupciones de servicios externos fuera de su control.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet (tener control del negocio esté o no en el local).

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* un mes de operación, *cuando* se calcula la disponibilidad a partir del monitoreo del servidor cada 5 minutos, *entonces* el servicio estuvo disponible al menos el 99 % del tiempo (máximo aproximado de 7,3 horas de caída no programada).
2. *Dado* que se planifica un mantenimiento programado, *cuando* se agenda, *entonces* se avisa al administrador con al menos 24 horas de anticipación y se realiza fuera del horario de atención.
3. *Dado* que ocurre una interrupción del servicio, *cuando* se resuelve, *entonces* queda registrada con hora de inicio, hora de fin y causa.

---

### **RNF-21 — Comportamiento ante pérdida de conexión**

**Tipo:** No funcional (Disponibilidad y recuperación)

**Descripción:** Cuando se pierda la comunicación con el servidor, el sistema deberá informar al usuario y evitar presentar operaciones pendientes como si hubieran sido registradas o confirmadas correctamente.

**Origen:** Equipo de desarrollo, a partir de la entrevista con el cliente Pepito Pérez (evitar pérdida de información en comandas y pagos).

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el dispositivo pierde la conexión con el servidor, *cuando* han pasado máximo 5 segundos, *entonces* la app muestra un indicador visible de "Sin conexión".
2. *Dado* que una operación fue enviada sin respuesta del servidor (comanda, pago o solicitud de retiro), *cuando* el usuario la consulta, *entonces* aparece como "Pendiente de confirmar" y nunca como confirmada.
3. *Dado* que existe un formulario en curso y se pierde la conexión, *cuando* ocurre la pérdida, *entonces* los datos ingresados se conservan en pantalla para reintentar el envío.

---

### **RNF-22 — Recuperación tras fallos de conexión**

**Tipo:** No funcional (Disponibilidad y recuperación)

**Descripción:** Después de una interrupción de conexión o un fallo del sistema, la aplicación deberá permitir consultar el estado de las operaciones previamente registradas y facilitar la recuperación de las operaciones que no se hayan confirmado, evitando duplicaciones.

**Origen:** Equipo de desarrollo.

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que se restablece la conexión, *cuando* la app vuelve a comunicarse con el servidor, *entonces* consulta el estado real de las operaciones pendientes y actualiza la vista.
2. *Dado* que el servidor registró una operación pero su confirmación no llegó al dispositivo, *cuando* el usuario la reintenta, *entonces* el servidor la reconoce por su identificador único y no la registra dos veces.
3. *Dado* que una operación no llegó al servidor, *cuando* el usuario la reintenta, *entonces* puede enviarla sin volver a ingresar los datos.

---

### **RNF-23 — Tiempo de entrega de notificaciones**

**Tipo:** No funcional (Disponibilidad y recuperación)

**Descripción:** Las notificaciones de solicitudes de retiro, alertas de inventario y cambios relevantes deberán entregarse en un tiempo máximo de 5 segundos en al menos el 95 % de los casos en que los servicios de comunicación estén disponibles y el dispositivo receptor pueda recibirlas.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet (recibir en el celular las solicitudes de dinero y saber a tiempo cuándo algo se va a acabar).

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que se envían 100 notificaciones de prueba a un dispositivo receptor con conexión, *cuando* se miden los tiempos, *entonces* al menos 95 llegan en 5 segundos o menos.
2. *Dado* que un dispositivo receptor no tenía conexión, *cuando* la recupera, *entonces* recibe las notificaciones pendientes (RF-35).
3. *Dado* que un evento genera una notificación, *cuando* esta se entrega, *entonces* el usuario la recibe una sola vez.

---

### 2.6. Compatibilidad y mantenibilidad

---

### **RNF-24 — Compatibilidad con Android**

**Tipo:** No funcional (Compatibilidad y mantenibilidad)

**Descripción:** La aplicación móvil deberá funcionar correctamente en dispositivos con Android 8.0 (API 26) o superior, manteniendo las funciones correspondientes a cada rol.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet (tabletas y teléfonos adquiridos para el negocio).

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que se instala la aplicación en un dispositivo con Android 8.0 o superior, *cuando* se ejecuta, *entonces* las funciones de cada rol operan sin cierres inesperados.
2. *Dado* que se valida la compatibilidad en la etapa de pruebas, *cuando* se prueban los dispositivos, *entonces* se incluye al menos un teléfono, una tableta y emuladores con la versión mínima y la más reciente de Android.
3. *Dado* que se intenta instalar la aplicación en un dispositivo con versión inferior a la mínima, *cuando* se hace la instalación, *entonces* esta no se permite.

---

### **RNF-25 — Visualización en televisores de cocina**

**Tipo:** No funcional (Compatibilidad y mantenibilidad)

**Descripción:** La interfaz de cocina deberá visualizarse correctamente en los televisores del establecimiento, mediante el mecanismo de acceso definido para el proyecto (navegador web del televisor o dispositivo Android conectado por HDMI).

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet (televisores en la cocina).

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que se conecta un televisor con resolución 1920 × 1080 mediante el mecanismo definido, *cuando* se abre la vista de cocina, *entonces* se muestra completa en orientación horizontal y sin elementos cortados.
2. *Dado* que la vista de cocina está abierta durante la jornada, *cuando* pasa el tiempo sin interacción, *entonces* la pantalla no se suspende ni cierra la sesión.
3. *Dado* que el televisor se reinicia o pierde la conexión, *cuando* se recupera, *entonces* la vista vuelve a mostrar las comandas activas sin registrarlas de nuevo.

---

### **RNF-26 — Acceso remoto seguro del administrador**

**Tipo:** No funcional (Compatibilidad y mantenibilidad / Seguridad)

**Descripción:** El sistema deberá permitir al administrador acceder de forma remota desde un dispositivo autorizado y con conexión a Internet, manteniendo los controles de autenticación y autorización establecidos.

**Origen:** El cliente Pepito Pérez — 29 de septiembre del 2026, llamada por Meet (controlar el negocio desde su teléfono esté o no en el local).

**Prioridad:** Alta

**Criterios de aceptación:**

1. *Dado* que el administrador está fuera del local y tiene Internet, *cuando* inicia sesión, *entonces* el servidor aplica las mismas validaciones de credenciales y rol que dentro del local (RNF-07), y la comunicación se realiza por HTTPS (RNF-06).
2. *Dado* que una sesión no tiene actividad durante 30 minutos, *cuando* el administrador intenta realizar una acción, *entonces* el sistema le solicita autenticarse de nuevo.
3. *Dado* que se registran 5 intentos fallidos consecutivos de inicio de sesión, *cuando* se intenta un sexto, *entonces* el acceso a esa cuenta se bloquea durante 15 minutos.

---

### **RNF-27 — Modularidad del software**

**Tipo:** No funcional (Compatibilidad y mantenibilidad)

**Descripción:** El software deberá organizarse en módulos y componentes diferenciados que faciliten la corrección de errores, la realización de pruebas y la incorporación de mejoras sin afectar innecesariamente las demás funcionalidades.

**Origen:** Equipo de desarrollo.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que se revisa la estructura del código fuente, *cuando* se analiza, *entonces* está organizado por módulos (usuarios, inventario, comandas, cocina, caja y fidelización), con la interfaz separada de la lógica de negocio y del acceso a datos.
2. *Dado* que se ejecutan las pruebas automatizadas sobre la lógica crítica (cálculo de totales, saldos, cierre de caja y puntos de fidelidad), *cuando* se mide la cobertura, *entonces* es de al menos el 70 %.
3. *Dado* que un nuevo integrante consulta el repositorio del proyecto, *cuando* lo revisa, *entonces* cuenta con control de versiones y un documento con las instrucciones de instalación y ejecución.

---

### **RNF-28 — Registro de errores técnicos**

**Tipo:** No funcional (Compatibilidad y mantenibilidad)

**Descripción:** El sistema deberá registrar los errores técnicos relevantes para facilitar su diagnóstico y mantenimiento, evitando incluir contraseñas u otros datos sensibles innecesarios en dichos registros.

**Origen:** Equipo de desarrollo.

**Prioridad:** Media

**Criterios de aceptación:**

1. *Dado* que ocurre un error técnico (excepción, fallo de conexión con la base de datos o fallo al enviar una notificación), *cuando* sucede, *entonces* queda registrado con fecha, hora, módulo, tipo de error y usuario o dispositivo cuando aplique.
2. *Dado* que se consulta un registro de error, *cuando* se revisa, *entonces* no contiene contraseñas ni tokens, y los números de documento de los clientes aparecen enmascarados.
3. *Dado* que se intenta acceder a los registros de errores, *cuando* se hace la solicitud, *entonces* solo el equipo técnico puede consultarlos, y se conservan durante al menos 30 días.
