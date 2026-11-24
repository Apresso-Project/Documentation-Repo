# HISTORIAS DE USUARIO — APPRESSO

---

### **HU-01 — Autenticación de usuarios (RF-01)**

* **Historia de usuario:** Como usuario registrado del sistema, quiero iniciar sesión mediante mis credenciales (correo electrónico y contraseña si soy personal; número de documento y contraseña si soy cliente), para acceder de manera segura a la interfaz principal y a las funciones correspondientes a mi perfil.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el usuario se encuentra registrado en el sistema, *cuando* ingresa un correo electrónico y una contraseña válidos y hace clic en el botón de inicio de sesión, *entonces* el sistema valida las credenciales correctamente y le otorga acceso a la interfaz principal de la aplicación.
  * *Dado* que un usuario intenta iniciar sesión, *cuando* ingresa un correo electrónico no registrado o una contraseña incorrecta, *entonces* el sistema deniega el acceso y muestra un mensaje de error notificando que las credenciales son inválidas.
  * *Dado* que un cliente registrado ingresa su número de documento y su contraseña válidos, *cuando* presiona el botón de inicio de sesión, *entonces* el sistema le otorga acceso a las funciones de su rol.
  * *Dado* que un cliente intenta iniciar sesión con un correo electrónico, o un integrante del personal con un número de documento, *cuando* lo intenta, *entonces* el sistema deniega el acceso.
* **Análisis INVEST:**
  * **I (Independiente):** Es independiente y constituye la base de autenticación de todo el sistema.
  * **N (Negociable):** El diseño de la pantalla y los mensajes se pueden acordar. La recuperación de la contraseña del cliente se trata en HU-65.
  * **V (Valiosa):** Garantiza que solo el personal autorizado y clientes entren a la plataforma móvil.
  * **E (Estimable):** Complejidad baja y acotada.
  * **S (Pequeña):** Cabe perfectamente dentro de un sprint corto.
  * **T (Testeable):** Se prueba ingresando credenciales correctas e incorrectas midiendo la respuesta del servidor.

---

### **HU-02 — Administración de usuarios (RF-02)**

* **Historia de usuario:** Como administrador, quiero gestionar las cuentas del personal y asignarles los roles autorizados, para controlar quiénes tienen acceso a la aplicación móvil.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el administrador ha iniciado sesión, *cuando* crea o edita la información de un usuario y guarda los cambios, *entonces* el sistema actualiza la base de datos y refleja los datos del usuario en la lista global de usuarios.
  * *Dado* que el administrador gestiona una cuenta existente, *cuando* le asigna o cambia un rol autorizado (Administrador, Cajero, Mesero o Cocinero) y confirma la acción, *entonces* el sistema actualiza los permisos de dicha cuenta inmediatamente.
  * *Dado* que un usuario no administrador intenta acceder al módulo de gestión de cuentas o asignaciones de roles, *cuando* ingresa a la ruta correspondiente, *entonces* el sistema deniega el acceso y muestra el mensaje "No tienes permiso para realizar esta acción."
  * *Dado* que el administrador crea o edita un usuario con un correo electrónico que ya pertenece a otra cuenta (sin distinguir mayúsculas de minúsculas), *cuando* guarda los cambios, *entonces* el sistema rechaza la operación e indica que el correo ya está registrado.
  * *Dado* que el administrador ha iniciado sesión, *cuando* intenta desactivar su propia cuenta o cambiar su propio rol, *entonces* el sistema rechaza la operación.
  * *Dado* que solo queda un administrador activo, *cuando* se intenta desactivarlo o quitarle el rol de administrador, *entonces* el sistema rechaza la operación para que siempre exista al menos un administrador activo.
  * *Dado* que el administrador consulta la lista de usuarios o intenta crear o editar una cuenta con el rol Cliente, *cuando* realiza la acción, *entonces* la lista no incluye las cuentas de cliente y el sistema rechaza crear o editar cuentas de ese rol.
* **Análisis INVEST:**
  * **I (Independiente):** Depende lógicamente de HU-01 (autenticación).
  * **N (Negociable):** Los campos específicos del formulario de usuario pueden ajustarse.
  * **V (Valiosa):** Permite al negocio administrar al personal de manera autónoma.
  * **E (Estimable):** Alcance bien definido.
  * **S (Pequeña):** Factible de completar en una iteración.
  * **T (Testeable):** Se comprueba creando perfiles, alterando roles y verificando restricciones.

---

### **HU-03 — Acceso según el rol (RF-03)**

* **Historia de usuario:** Como usuario del sistema, quiero que se me presenten las funcionalidades correspondientes a mi rol (administrador, cajero, mesero, cocinero o cliente; el administrador tiene acceso a todas), para operar de manera adecuada sin exceder mis privilegios.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que un usuario inicia sesión con un rol específico, *cuando* navega en la plataforma, *entonces* el sistema le despliega el menú y las herramientas asignadas a su rol (al administrador, las de todos los roles).
  * *Dado* que un usuario con rol de Cliente, Mesero o Cocinero intenta realizar acciones reservadas para Administrador o Cajero, *cuando* intenta interactuar con dichas funciones, *entonces* el sistema no las muestra disponibles o bloquea la acción notificando falta de permisos.
  * *Dado* que el administrador modifica el rol de un usuario activo, *cuando* ese usuario vuelve a iniciar sesión, *entonces* las funcionalidades disponibles se ajustan de inmediato al nuevo rol.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de HU-01 y HU-02.
  * **N (Negociable):** La forma visual de ocultar las opciones se puede acordar.
  * **V (Valiosa):** Asegura la segmentación operacional del negocio en campo.
  * **E (Estimable):** Estimación clara con base en el esquema de permisos.
  * **S (Pequeña):** Funcionalidad estándar de control de acceso.
  * **T (Testeable):** Validando cada rol contra las vistas permitidas y prohibidas.

---

### **HU-04 — Restricción de operaciones no autorizadas (RF-04)**

* **Historia de usuario:** Como administrador, quiero impedir que cualquier usuario ejecute operaciones no autorizadas para su rol (tanto en interfaz como a nivel de API), para proteger la integridad de los datos de la app.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que un usuario autenticado intenta ejecutar una función no permitida desde la app o manipulando solicitudes a la API móvil, *cuando* la app envía la petición, *entonces* el servidor deniega la acción y responde con un código de error de autorización (ej. 403 Forbidden) evitando cambios en los datos.
  * *Dado* que un usuario intenta interactuar con un módulo o acción restringida, *cuando* presiona sobre el componente, *entonces* la app le muestra un aviso emergente en pantalla con el mensaje "No tienes permiso para realizar esta acción."
* **Análisis INVEST:**
  * **I (Independiente):** Complementa directamente el control de roles (HU-03).
  * **N (Negociable):** El diseño exacto de la alerta móvil o el formato del mensaje de error.
  * **V (Valiosa):** Previene vulnerabilidades de seguridad y malas prácticas operativas.
  * **E (Estimable):** Tarea técnica estándar de middleware y control en backend/frontend.
  * **S (Pequeña):** Acotada a la gestión de excepciones de seguridad.
  * **T (Testeable):** Realizando pruebas de penetración o solicitudes simuladas no autorizadas a endpoints.

---

### **HU-05 — Acceso remoto del administrador (RF-05)**

* **Historia de usuario:** Como administrador, quiero acceder a las funcionalidades autorizadas desde un dispositivo móvil conectado a Internet independientemente de mi ubicación, para supervisar el negocio fuera del establecimiento.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que el administrador se encuentra fuera del local con conexión de red celular o Wi-Fi externa, *cuando* inicia sesión desde la app móvil, *entonces* el sistema autentica sus credenciales e ingresa exitosamente sin requerir red local.
  * *Dado* que el administrador opera remotamente, *cuando* navega por la app, *entonces* el sistema le habilita todas las funciones de su rol en tiempo real.
  * *Dado* que la señal de Internet se interrumpe durante una operación remota, *cuando* ocurre la falla, *entonces* la app móvil muestra un mensaje descriptivo ("Sin conexión a Internet. Por favor, verifica tu red.") en lugar de cerrarse de manera inesperada.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de la conectividad general y del backend en la nube.
  * **N (Negociable):** El tiempo de tolerancia ante retardos de red.
  * **V (Valiosa):** Brinda movilidad absoluta y control gerencial continuo.
  * **E (Estimable):** Depende de la correcta arquitectura de despliegue web/móvil.
  * **S (Pequeña):** Factible en una iteración de pruebas de conectividad.
  * **T (Testeable):** Probando con datos móviles y simulando pérdida de paquetes o corte de red.

---

### **HU-06 — Administración de productos y categorías (RF-06)**

* **Historia de usuario:** Como administrador, quiero registrar, consultar, modificar y desactivar productos y categorías desde la aplicación móvil, para mantener el catálogo actualizado.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el administrador se encuentra en la pantalla de gestión del catálogo de la app móvil, *cuando* completa los campos para crear, editar o desactivar un producto o categoría y confirma la acción, *entonces* el sistema guarda los cambios y los refleja en la lista en tiempo real.
  * *Dado* que un usuario sin rol de administrador navega por la app, *cuando* intenta acceder al módulo de edición del catálogo, *entonces* la app oculta los botones o deniega la acción mostrando un mensaje de error.
* **Análisis INVEST:**
  * **I (Independiente):** Requiere tener activo el control de roles (HU-03).
  * **N (Negociable):** Los campos detallados del producto (imágenes, descripciones breves).
  * **V (Valiosa):** Permite gestionar la oferta de la cafetería de forma ágil desde el celular.
  * **E (Estimable):** Historia de complejidad moderada por formularios de base de datos.
  * **S (Pequeña):** Ajustada para completarse en un sprint.
  * **T (Testeable):** Creando, editando y desactivando ítems directamente en la interfaz móvil.

---

### **HU-07 — Ajustes manuales de inventario (RF-07)**

* **Historia de usuario:** Como administrador, quiero registrar entradas y salidas manuales de unidades de productos, para corregir el stock o registrar mermas directamente desde el dispositivo móvil.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el administrador selecciona un producto e ingresa una cantidad de entrada/salida manual con su justificación, *cuando* confirma la transacción, *entonces* el sistema actualiza el stock total de manera inmediata.
  * *Dado* que el administrador intenta registrar una salida superior al stock disponible o valores inválidos (negativos o nulos), *cuando* presiona guardar, *entonces* la app despliega una alerta de validación impidiendo la acción.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de la existencia previa de productos (HU-06).
  * **N (Negociable):** Los motivos o categorías de ajuste manual predefinidos.
  * **V (Valiosa):** Evita descuadres físicos en el inventario de la cafetería.
  * **E (Estimable):** Estimación simple sobre reglas de validación numérica.
  * **S (Pequeña):** Ideal para una iteración corta.
  * **T (Testeable):** Introduciendo ajustes positivos, negativos y erróneos verificando el stock resultante.

---

### **HU-08 — Consulta de existencias en tiempo real (RF-08)**

* **Historia de usuario:** Como usuario autorizado, quiero visualizar la cantidad disponible de cada producto actualizada al instante tras cada movimiento, para conocer el inventario actual en todo momento.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que se confirma una venta, comanda o ajuste de stock, *cuando* cualquier usuario autorizado consulta las existencias, *entonces* la interfaz muestra la cifra de stock actualizada de inmediato.
  * *Dado* que se revisa el detalle de un ítem en el catálogo, *cuando* el usuario accede a este, *entonces* la app exhibe el número exacto de unidades disponibles en pantalla.
* **Análisis INVEST:**
  * **I (Independiente):** Se apoya en los módulos de inventario y pedidos.
  * **N (Negociable):** El diseño visual de las etiquetas de cantidades.
  * **V (Valiosa):** Proporciona visibilidad precisa del estado físico de las mercancías.
  * **E (Estimable):** Baja complejidad técnica si las consultas están optimizadas.
  * **S (Pequeña):** Tarea directa de consulta en base de datos.
  * **T (Testeable):** Modificando stock mediante una comanda y comprobando el reflejo en la pantalla de inventario.

---

### **HU-09 — Configuración de umbrales mínimos de existencias (RF-09)**

* **Historia de usuario:** Como administrador, quiero configurar un umbral mínimo de existencias para cada producto activo, para establecer los límites de alerta de reabastecimiento.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que el administrador ingresa al detalle de un producto activo, *cuando* establece o modifica el valor numérico del "Umbral Mínimo" y guarda los cambios, *entonces* el sistema almacena este límite asociado al producto.
  * *Dado* que se intenta ingresar un valor negativo en el umbral mínimo, *cuando* se intenta guardar, *entonces* la app muestra un aviso de validación exigiendo un número entero mayor o igual a cero.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de la gestión de productos (HU-06).
  * **N (Negociable):** Valores por defecto sugeridos al crear productos nuevos.
  * **V (Valiosa):** Previene desabastecimientos imprevistos de insumos clave.
  * **E (Estimable):** Muy sencilla de dimensionar.
  * **S (Pequeña):** Campo adicional en la estructura de datos del producto.
  * **T (Testeable):** Asignando límites y validando restricciones de entrada en formularios.

---

### **HU-10 — Alertas de existencias bajas (RF-10)**

* **Historia de usuario:** Como administrador, quiero que el sistema genere una alerta visual cuando las existencias de un producto alcancen o bajen del umbral mínimo configurado, para tomar acción oportuna.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que el stock disponible de un producto disminuye y alcanza o queda por debajo del umbral mínimo, *cuando* ocurre dicho movimiento, *entonces* la app muestra un indicador visual destacado (ej. etiqueta o icono de advertencia) en la lista de inventario.
  * *Dado* que existen productos con stock crítico, *cuando* el administrador abre la app móvil, *entonces* visualiza un resumen o módulo de advertencia con los productos que requieren reabastecimiento.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de HU-08 y HU-09.
  * **N (Negociable):** El color o tipo de icono de advertencia utilizado.
  * **V (Valiosa):** Automatiza la supervisión del inventario crítico.
  * **E (Estimable):** Tarea rápida de lógica condicional en la interfaz.
  * **S (Pequeña):** Cabe holgadamente en un sprint.
  * **T (Testeable):** Bajando el stock de un producto por debajo del umbral y verificando la aparición de la alerta.

---

### **HU-11 — Consulta del menú disponible para meseros (RF-11)**

* **Historia de usuario:** Como mesero, quiero visualizar los productos disponibles agrupados por categoría con su precio y stock existente, para ofrecer al cliente alternativas reales de servicio.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el mesero abre la sección de menú en la app, *cuando* selecciona una categoría (ej. Bebidas, Platos Fuertes, Postres), *entonces* la app despliega los productos con nombre, precio formateado y existencias disponibles.
  * *Dado* que un producto no tiene unidades o está desactivado, *cuando* el mesero explora el catálogo, *entonces* la app no lo muestra.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de la existencia de un catálogo creado por el administrador (HU-06).
  * **N (Negociable):** Distribución visual de tarjetas o listados en la interfaz móvil.
  * **V (Valiosa):** Facilita una atención rápida y evita tomar pedidos de productos inexistentes.
  * **E (Estimable):** Complejidad baja centrada en consumo de API de catálogo.
  * **S (Pequeña):** Alcance muy acotado a la vista de lectura del mesero.
  * **T (Testeable):** Navegando por categorías y comprobando precios y estados de stock en pantalla.

---

### **HU-12 — Validación de cantidades solicitadas en comandas (RF-12)**

* **Historia de usuario:** Como mesero, quiero que el sistema rechace la incorporación a una comanda de una cantidad superior a las unidades disponibles, para evitar ventas de productos inexistentes.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que un producto cuenta con $N$ unidades disponibles, *cuando* el mesero intenta agregar a la comanda una cantidad mayor a $N$, *entonces* la app bloquea la adición y despliega una alerta advirtiendo la falta de stock.
  * *Dado* que se modifica la cantidad de un ítem ya seleccionado usando el botón incremental (+), *cuando* este alcanza el límite del stock en tiempo real, *entonces* el contador se detiene y emite un aviso en pantalla.
* **Análisis INVEST:**
  * **I (Independiente):** Vinculado con el control de inventario (HU-08) y toma de pedidos.
  * **N (Negociable):** El texto exacto de la advertencia emergente.
  * **V (Valiosa):** Previene errores operativos graves al registrar comandas en sala.
  * **E (Estimable):** Lógica de control en la capa de interfaz de pedidos.
  * **S (Pequeña):** Factible de implementar y probar rápidamente.
  * **T (Testeable):** Intentando añadir cantidades superiores al stock actual y comprobando el bloqueo.

---

### **HU-13 — Ocultamiento automático de productos agotados (RF-13)**

* **Historia de usuario:** Como mesero, quiero que el sistema oculte de forma automática del menú los productos cuyas existencias sean cero, para no ofrecer lo que no hay y no generar frustración en el servicio.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el stock de un producto llega a cero (0), *cuando* un mesero consulta el menú, *entonces* el producto no aparece y no se puede agregar a la comanda.
  * *Dado* que un producto agotado recibe un reabastecimiento manual por parte del administrador, *cuando* el mesero refresca la vista del menú, *entonces* el producto vuelve a aparecer y se puede vender de nuevo.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de los movimientos de inventario y la vista de menú.
  * **N (Negociable):** Si el producto desaparece del menú al instante o al refrescar la vista.
  * **V (Valiosa):** Automatiza la sincronización entre bodega y salón.
  * **E (Estimable):** Requerimiento técnico directo basado en estados de stock.
  * **S (Pequeña):** Ajustada para una iteración estándar.
  * **T (Testeable):** Agotando un producto en el sistema y comprobando su indisponibilidad inmediata en la interfaz del mesero.

---

### **HU-14 — Historial de movimientos de inventario (RF-14)**

* **Historia de usuario:** Como administrador, quiero registrar y consultar un historial detallado de entradas, salidas y ajustes manuales del inventario, para garantizar trazabilidad y auditoría completa.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que se ejecuta cualquier movimiento de inventario (venta, entrada manual, ajuste), *cuando* el administrador abre la pantalla de historial, *entonces* visualiza un registro con el producto afectado, la cantidad modificada, la fecha/hora exacta y la cuenta del usuario responsable.
  * *Dado* que el administrador consulta la bitácora en la app móvil, *cuando* aplica filtros por rango de fechas o nombre de producto, *entonces* el sistema muestra el listado filtrado correctamente.
* **Análisis INVEST:**
  * **I (Independiente):** Se apoya en los registros de transacciones de inventario (HU-07).
  * **N (Negociable):** Opciones de exportación de datos (si se requieren a futuro).
  * **V (Valiosa):** Otorga control gerencial riguroso sobre el flujo de mercancías.
  * **E (Estimable):** Complejidad baja orientada a reportes de consulta y filtrado.
  * **S (Pequeña):** Adecuada para un sprint de reportes y trazabilidad.
  * **T (Testeable):** Realizando movimientos de inventario y validando su correcta visualización en la bitácora con sus respectivos filtros.

---

### **HU-15 — Creación de comandas asociadas a una mesa (RF-15)**

* **Historia de usuario:** Como mesero, quiero crear una comanda nueva asociada directamente a una mesa identificada mediante el mapa de mesas, para organizar y estructurar los pedidos de los clientes con precisión.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el mesero selecciona una mesa disponible en el mapa de mesas de la app móvil, *cuando* confirma la apertura de un nuevo pedido, *entonces* el sistema crea una comanda vinculada a dicho número/nombre de mesa y cambia su estado a "Ocupada" o "En atención".
  * *Dado* que una mesa ya posee una comanda activa en curso, *cuando* el mesero intenta crear una nueva comanda para esa misma mesa, *entonces* la app le advierte de la existencia del pedido activo y le ofrece abrir el registro previo.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de la autenticación de meseros y la definición de mesas.
  * **N (Negociable):** El diseño gráfico de la distribución o cuadrícula de mesas en pantalla.
  * **V (Valiosa):** Es el punto de partida fundamental para el flujo operativo de atención en el restaurante.
  * **E (Estimable):** Historia clave de mediana complejidad dentro del flujo principal del negocio.
  * **S (Pequeña):** Encaja adecuadamente en el ciclo de desarrollo planificado.
  * **T (Testeable):** Abriendo comandas en distintas mesas, validando estados ocupados y controlando duplicidad de pedidos por mesa.

---

### **HU-16 — Registro de productos y preferencias en la comanda (RF-16)**

* **Historia de usuario:** Como mesero, quiero agregar a la comanda de una mesa los productos, las cantidades y las preferencias del cliente, para tomar pedidos completos sin usar papel.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que un mesero tiene una mesa seleccionada, *cuando* agrega un producto con su cantidad y una preferencia (texto libre de hasta 100 caracteres), *entonces* la comanda los muestra.
  * *Dado* que un producto tiene pocas unidades, *cuando* el mesero lo consulta, *entonces* ve la cantidad restante.
  * *Dado* que un producto está agotado o desactivado (por ejemplo, porque se agotó mientras armaba la comanda), *cuando* el mesero intenta agregarlo, *entonces* el sistema lo impide e informa.
* **Análisis INVEST:**
  * **I (Independiente):** Parcial; depende de que exista el inventario (productos y existencias).
  * **N (Negociable):** El diseño del campo de preferencias se puede acordar; el texto es libre y de hasta 100 caracteres (RF-16).
  * **V (Valiosa):** El mesero deja de usar papel y el cliente recibe lo que pidió.
  * **E (Estimable):** Alcance claro y conocido.
  * **S (Pequeña):** Cabe en un sprint.
  * **T (Testeable):** Se prueba agregando productos válidos, agotados y con preferencia.

---

### **HU-17 — Cálculo del total de la comanda (RF-17)**

* **Historia de usuario:** Como mesero, quiero ver el subtotal y el total de la comanda calculados con los descuentos autorizados, para cobrar el valor correcto sin hacer cuentas a mano.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que una comanda tiene productos, *cuando* cambia una cantidad o se agrega un producto, *entonces* el subtotal y el total se recalculan al instante.
  * *Dado* que se aplica un descuento autorizado (recompensa o promoción vigente), *cuando* se aplica, *entonces* el total lo refleja.
  * *Dado* que se intenta aplicar un descuento vencido o no autorizado, *cuando* el sistema lo evalúa, *entonces* lo rechaza.
* **Análisis INVEST:**
  * **I (Independiente):** Parcial; necesita comandas con productos (HU-16).
  * **N (Negociable):** Se puede negociar cómo se muestra el desglose.
  * **V (Valiosa):** Evita errores de cobro.
  * **E (Estimable):** El cálculo es simple y está definido.
  * **S (Pequeña):** Pequeña.
  * **T (Testeable):** Se compara el total del sistema con el cálculo manual.

---

### **HU-18 — Envío de comandas a cocina (RF-18)**

* **Historia de usuario:** Como mesero, quiero confirmar la comanda y enviarla a la cocina, para que los cocineros reciban el pedido sin errores de transcripción.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que una comanda tiene al menos un producto, *cuando* el mesero la confirma, *entonces* aparece en cocina en menos de 3 segundos con estado "Pendiente".
  * *Dado* que una comanda está vacía, *cuando* el mesero intenta confirmarla, *entonces* el sistema no la envía.
  * *Dado* que hay una falla de conexión al confirmar, *cuando* ocurre, *entonces* el sistema avisa y no la marca como enviada.
  * *Dado* que una comanda se confirma y se envía, *cuando* el sistema la procesa, *entonces* las existencias de sus productos se descuentan del inventario.
  * *Dado* que un producto de la comanda no tiene existencias suficientes, *cuando* el mesero la confirma, *entonces* el sistema no la envía, indica qué producto no alcanza y no descuenta ninguna existencia.
* **Análisis INVEST:**
  * **I (Independiente):** Parcial; depende de HU-16 y de la pantalla de cocina (HU-23).
  * **N (Negociable):** Se puede discutir el comportamiento sin conexión.
  * **V (Valiosa):** Elimina los post-its y la pérdida de información.
  * **E (Estimable):** Alcance claro.
  * **S (Pequeña):** Cabe en un sprint.
  * **T (Testeable):** Se prueba el envío, la comanda vacía y la falla de red.

---

### **HU-19 — Consulta de pedidos y estados (RF-19)**

* **Historia de usuario:** Como mesero o administrador, quiero consultar las comandas activas y su estado, para hacer seguimiento a los pedidos del turno o supervisar el restaurante en cualquier momento.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que el administrador tiene sesión activa, *cuando* abre la lista de comandas, *entonces* ve todas las del día con su mesa, total y estado.
  * *Dado* que el mesero tiene sesión activa, *cuando* abre la lista de comandas, *entonces* ve las del día con su mesa, total y estado.
  * *Dado* que se aplica un filtro por estado o mesa, *cuando* lo aplica, *entonces* solo aparecen las que cumplen el criterio.
  * *Dado* que un usuario sin permiso intenta consultar las comandas, *cuando* lo intenta, *entonces* el sistema se lo impide.
* **Análisis INVEST:**
  * **I (Independiente):** Parcial; requiere comandas ya registradas.
  * **N (Negociable):** Los filtros, la vista y si el mesero ve solo sus comandas o todas se pueden negociar.
  * **V (Valiosa):** El mesero gestiona sus pedidos y el dueño supervisa sin estar presente.
  * **E (Estimable):** Alcance claro.
  * **S (Pequeña):** Pequeña.
  * **T (Testeable):** Se prueba la lista, los filtros y el control de permisos con ambos roles.

---

### **HU-20 — Modificación de comandas enviadas (RF-20)**

* **Historia de usuario:** Como mesero, quiero agregar o eliminar productos de una comanda ya enviada, mientras no esté cerrada, cuando el cliente cambia su pedido, para atenderlo sin crear un pedido nuevo.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que una comanda está enviada y no pagada, *cuando* el mesero agrega un producto con existencias, *entonces* se actualiza y el total se recalcula.
  * *Dado* que un producto no tiene existencias suficientes, *cuando* el mesero intenta agregarlo, *entonces* el sistema lo rechaza.
  * *Dado* que una comanda enviada y no cerrada tiene un producto, *cuando* el mesero lo elimina, *entonces* la comanda se actualiza, el total se recalcula y las existencias de ese producto se reintegran.
  * *Dado* que una comanda ya está cerrada (pagada o cancelada), *cuando* el mesero intenta modificarla (agregar o eliminar productos), *entonces* el sistema no lo permite.
* **Análisis INVEST:**
  * **I (Independiente):** Parcial; depende de HU-16 y HU-18.
  * **N (Negociable):** El diseño de la pantalla y las reglas para eliminar productos que ya están en preparación o listos se pueden acordar con el dueño.
  * **V (Valiosa):** Cubre un caso muy frecuente del servicio.
  * **E (Estimable):** Alcance acotado a agregar y eliminar productos.
  * **S (Pequeña):** Pequeña.
  * **T (Testeable):** Se prueba con comanda enviada, con producto eliminado, sin stock y pagada.

---

### **HU-21 — Notificación de cambios a cocina (RF-21)**

* **Historia de usuario:** Como cocinero, quiero ser avisado y ver resaltado lo que se añadió o se eliminó en una comanda en curso, para preparar el cambio sin confundirlo con lo original.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que a una comanda en cocina se le agrega un producto, *cuando* ocurre, *entonces* en menos de 3 segundos aparece una alerta en pantalla.
  * *Dado* que llega el producto nuevo, *cuando* se muestra, *entonces* aparece resaltado como "Agregado".
  * *Dado* que llega el cambio, *cuando* se muestra, *entonces* los productos originales conservan su estado.
  * *Dado* que a una comanda en cocina se le elimina un producto, *cuando* ocurre, *entonces* en menos de 3 segundos aparece una alerta y el producto se marca como "Eliminado".
* **Análisis INVEST:**
  * **I (Independiente):** Parcial; depende de HU-20 y HU-23.
  * **N (Negociable):** El tipo de alerta (visual o sonora) se puede negociar.
  * **V (Valiosa):** Evita errores y platos olvidados.
  * **E (Estimable):** Alcance claro.
  * **S (Pequeña):** Pequeña.
  * **T (Testeable):** Se agrega un producto y se verifica la alerta y el resaltado.

---

### **HU-22 — Asociación de clientes a comandas (RF-22)**

* **Historia de usuario:** Como mesero, quiero asociar la comanda al documento de un cliente registrado, para que el cliente acumule puntos de fidelidad.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que el mesero ingresa un documento registrado, *cuando* lo busca, *entonces* la comanda queda asociada al cliente.
  * *Dado* que el documento no está registrado, *cuando* el mesero lo ingresa, *entonces* el sistema lo informa y permite continuar sin asociar.
  * *Dado* que una comanda ya está asociada a un cliente y se confirma el pago, *cuando* ocurre, *entonces* la visita queda disponible para sumar puntos de fidelidad.
* **Análisis INVEST:**
  * **I (Independiente):** Parcial; requiere clientes registrados y comandas.
  * **N (Negociable):** Se puede negociar el método de búsqueda (solo documento o también celular).
  * **V (Valiosa):** Habilita el programa de fidelización.
  * **E (Estimable):** Alcance claro.
  * **S (Pequeña):** Pequeña.
  * **T (Testeable):** Se prueba con documento válido, inexistente y con pago confirmado.

---

### **HU-22b — Consulta de puntos de fidelidad y recompensas al asociar cliente (RF-22)**

* **Historia de usuario:** Como mesero, quiero ver los puntos de fidelidad y las recompensas disponibles del cliente al asociar su documento, para sugerirle que las canjee en su pedido.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que un cliente queda asociado a la comanda, *cuando* el mesero abre su ficha, *entonces* ve sus puntos de fidelidad actuales y sus recompensas disponibles.
  * *Dado* que un cliente no tiene recompensas disponibles, *cuando* se consulta, *entonces* el sistema lo indica y muestra sus puntos de fidelidad.
  * *Dado* que hay una recompensa disponible, *cuando* el cliente decide canjearla, *entonces* el mesero puede aplicarla a la comanda.
* **Análisis INVEST:**
  * **I (Independiente):** Parcial; depende de HU-22 y de las reglas de los puntos de fidelidad.
  * **N (Negociable):** Se puede negociar qué datos de los puntos se muestran.
  * **V (Valiosa):** Aumenta los canjes y la fidelización.
  * **E (Estimable):** Alcance claro.
  * **S (Pequeña):** Pequeña.
  * **T (Testeable):** Se prueba con clientes con y sin recompensas disponibles.

---

### **HU-23 — Visualización de pedidos en cocina (RF-23)**

* **Historia de usuario:** Como cocinero, quiero ver las comandas confirmadas por orden de llegada, para saber qué preparar y en qué orden.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que una comanda fue confirmada, *cuando* llega, *entonces* aparece en las pantallas de cocina.
  * *Dado* que hay varias comandas, *cuando* se muestran, *entonces* van de la más antigua a la más reciente.
  * *Dado* que una comanda no fue confirmada, *cuando* se consulta cocina, *entonces* no aparece.
* **Análisis INVEST:**
  * **I (Independiente):** Parcial; depende de HU-18.
  * **N (Negociable):** Se puede negociar la disposición de la pantalla.
  * **V (Valiosa):** Cocina sabe qué preparar sin papeles.
  * **E (Estimable):** Alcance claro.
  * **S (Pequeña):** Pequeña.
  * **T (Testeable):** Se prueba con varias comandas y verificando el orden.

---

### **HU-24 — Detalle de las comandas en cocina (RF-24)**

* **Historia de usuario:** Como cocinero, quiero ver en cada comanda la mesa, los productos, las cantidades y las observaciones, para preparar exactamente lo que pidió el cliente.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que una comanda se muestra en pantalla, *cuando* el cocinero la consulta, *entonces* incluye mesa, productos, cantidades y observaciones.
  * *Dado* que una observación es larga, *cuando* se muestra, *entonces* el texto no se corta.
  * *Dado* que una comanda tiene observaciones, *cuando* se muestra, *entonces* estas aparecen resaltadas.
* **Análisis INVEST:**
  * **I (Independiente):** Parcial; comparte pantalla con HU-23.
  * **N (Negociable):** Se puede negociar el diseño y el tamaño del texto.
  * **V (Valiosa):** Evita preparaciones equivocadas.
  * **E (Estimable):** Alcance claro.
  * **S (Pequeña):** Pequeña.
  * **T (Testeable):** Se verifica visualmente con comandas de prueba.

---

### **HU-25 — Actualización del estado de preparación (RF-25)**

* **Historia de usuario:** Como cocinero, quiero marcar mis comandas como "en preparación" cuando empiezo a cocinarlas y como "lista" cuando termino, para que el mesero sepa cuándo puede recoger el pedido y llevarlo a la mesa.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que una comanda llega a cocina con estado `enviada` y el cocinero inicia su preparación, *cuando* confirma el cambio, *entonces* el estado pasa a `en preparación`.
  * *Dado* que una comanda está en estado `en preparación` y el cocinero termina, *cuando* confirma el cambio, *entonces* el estado pasa a `lista`.
  * *Dado* que se confirma cualquier cambio de estado, *cuando* queda registrado, *entonces* incluye fecha, hora y usuario responsable.
  * *Dado* que el cocinero intenta ejecutar una transición no autorizada para su rol (por ejemplo, marcar una comanda como `cerrada`), *cuando* lo intenta, *entonces* el sistema rechaza la acción.
  * *Dado* que un usuario que no es cocinero ni administrador intenta cambiar el estado de preparación de una comanda, *cuando* lo intenta, *entonces* el sistema le deniega el acceso.
* **Análisis INVEST:**
  * **I (Independiente):** Parcial; depende de HU-23.
  * **N (Negociable):** El diseño del botón de cambio de estado y el texto del mensaje de confirmación se pueden acordar. El orden de las transiciones está definido en RF-COMANDA-ESTADO y no es negociable.
  * **V (Valiosa):** Da trazabilidad al pedido y coordina en tiempo real al cocinero con el mesero.
  * **E (Estimable):** Alcance claro con dos transiciones permitidas para el cocinero.
  * **S (Pequeña):** Pequeña.
  * **T (Testeable):** Se prueba cada transición permitida, los intentos de transiciones no autorizadas y el control de permisos.

---

### **HU-26 — Sincronización de estados de cocina (RF-26)**

* **Historia de usuario:** Como mesero, quiero ver los cambios de estado de las comandas apenas ocurren, para saber cuándo recoger un pedido y avisar al cliente.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que se produce un cambio de estado en cocina, *cuando* se confirma, *entonces* la tableta del mesero lo muestra en menos de 3 segundos.
  * *Dado* que llega el cambio, *cuando* se refleja, *entonces* no hace falta recargar la pantalla.
  * *Dado* que una comanda es marcada como "Lista", *cuando* llega a la tableta, *entonces* el mesero la identifica con claridad.
* **Análisis INVEST:**
  * **I (Independiente):** Parcial; depende de HU-25.
  * **N (Negociable):** Se puede negociar el tipo de aviso (visual o sonoro).
  * **V (Valiosa):** El pedido se entrega a tiempo.
  * **E (Estimable):** El riesgo está en la sincronización en tiempo real.
  * **S (Pequeña):** Puede ser la más grande del grupo; si no cabe en un sprint, conviene dividirla.
  * **T (Testeable):** Se mide el tiempo entre el cambio y su aparición en la tableta.

---

### **HU-27 — Historial de pedidos (RF-27)**

* **Historia de usuario:** Como administrador, quiero consultar el historial de cada pedido con sus cambios, fechas y responsables, para revisar qué pasó si hay un reclamo o una duda.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que el administrador abre el historial de un pedido, *cuando* lo consulta, *entonces* ve cada cambio con fecha, hora y usuario.
  * *Dado* que un usuario intenta editar o eliminar un registro del historial, *cuando* lo intenta, *entonces* el sistema no lo permite.
  * *Dado* que un usuario sin rol de administrador intenta ver el historial, *cuando* lo intenta, *entonces* el sistema lo impide.
* **Análisis INVEST:**
  * **I (Independiente):** Parcial; depende de que se registren los cambios (HU-20, HU-25).
  * **N (Negociable):** Se puede negociar cuánto tiempo se conserva el historial.
  * **V (Valiosa):** Permite aclarar reclamos y auditar.
  * **E (Estimable):** Alcance claro.
  * **S (Pequeña):** Pequeña.
  * **T (Testeable):** Se prueba generando cambios y verificando el registro.

---

### **HU-28 — Registro de pagos (RF-28)**

* **Historia de usuario:** Como administrador, quiero que cada pago quede registrado con su valor, medio, fecha y responsable, para tener control del dinero y evitar descuadres.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que se confirma un pago, *cuando* se registra, *entonces* guarda valor, medio, fecha, hora y usuario.
  * *Dado* que el pago es en efectivo, *cuando* se registra, *entonces* suma a la caja; si es transferencia, suma al saldo de transferencias.
  * *Dado* que una comanda ya está pagada, *cuando* se intenta pagar otra vez, *entonces* el sistema lo rechaza.
  * *Dado* que se confirma el pago de una comanda, *cuando* queda registrado, *entonces* la comanda pasa a estado `cerrada`.
* **Análisis INVEST:**
  * **I (Independiente):** Parcial; depende de HU-29 y HU-41 para generar los pagos.
  * **N (Negociable):** Se puede negociar el nivel de detalle del registro.
  * **V (Valiosa):** Da control del dinero y facilita el cierre diario.
  * **E (Estimable):** Alcance claro.
  * **S (Pequeña):** Pequeña.
  * **T (Testeable):** Se prueba cada medio de pago y el pago duplicado.

---

### **HU-29 — Registro de pagos en efectivo (RF-29)**

* **Historia de usuario:** Como cajero, quiero registrar los pagos en efectivo que recibo, para que cada peso de la caja quede asociado a un responsable y se evite el descuadre.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que un cajero o el administrador con sesión activa confirma un pago en efectivo, *cuando* lo registra, *entonces* se suma a la caja a su nombre.
  * *Dado* que un mesero, un cocinero o un cliente intenta confirmar un pago en efectivo, *cuando* lo intenta, *entonces* la opción no está disponible.
  * *Dado* que se intenta confirmar el pago en efectivo por otra vía con un rol que no es cajero ni administrador, *cuando* ocurre, *entonces* el sistema lo rechaza.
* **Análisis INVEST:**
  * **I (Independiente):** Parcial; comparte registro con HU-28.
  * **N (Negociable):** Se puede negociar si se calcula el cambio al recibir el dinero.
  * **V (Valiosa):** Reduce los descuadres de caja.
  * **E (Estimable):** Alcance claro.
  * **S (Pequeña):** Pequeña.
  * **T (Testeable):** Se prueba con cajero y con otros roles.

---

### **HU-30 — Pago por transferencia con código QR (RF-30)**

* **Historia de usuario:** Como mesero, cajero o administrador, quiero mostrar el código QR de pago y confirmar la transferencia desde la misma tableta, para cobrar por transferencia sin stickers ni papeles que se dañen o no se lean de noche.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que hay una comanda lista para pagar, *cuando* el mesero, cajero o administrador solicita el pago por transferencia, *entonces* se muestra el código QR en pantalla.
  * *Dado* que el mesero, cajero o administrador confirma la transferencia, *cuando* la confirma, *entonces* el pago queda registrado como transferencia y suma al saldo de transferencias, no a la caja.
  * *Dado* que una transferencia ya fue confirmada, *cuando* se intenta confirmar de nuevo, *entonces* el sistema no lo permite.
* **Análisis INVEST:**
  * **I (Independiente):** Historia compuesta: reúne de punta a punta lo que detallan HU-40 (mostrar el QR), HU-41 (confirmar), HU-42 (saldo) y HU-43 (doble confirmación). Se prueba como flujo completo.
  * **N (Negociable):** Se puede negociar si el QR es fijo o incluye el valor.
  * **V (Valiosa):** Reemplaza los stickers y mejora el cobro.
  * **E (Estimable):** Alcance claro.
  * **S (Pequeña):** Pequeña si se construye sobre HU-40 a HU-43.
  * **T (Testeable):** Se prueba el flujo completo: mostrar el QR, confirmar y verificar el saldo.

---

### **HU-31 — Saldos diferenciados por medio de pago (RF-31)**

* **Historia de usuario:** Como administrador, quiero que el efectivo y las transferencias tengan registros y saldos separados, para cuadrar la caja sin que un medio afecte al otro.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que se registra un pago en efectivo, *cuando* se actualiza el saldo, *entonces* solo aumenta el saldo en efectivo.
  * *Dado* que se confirma un pago por transferencia, *cuando* se actualiza el saldo, *entonces* solo aumenta el saldo de transferencias.
  * *Dado* que se ejecuta un retiro de caja, *cuando* se actualiza el saldo, *entonces* solo disminuye el saldo en efectivo.
* **Análisis INVEST:**
  * **I (Independiente):** Es una regla transversal; se prueba junto con las historias de pagos, ingresos y retiros.
  * **N (Negociable):** Cómo se muestran los saldos se puede acordar.
  * **V (Valiosa):** Evita mezclar el dinero físico con el que está en la cuenta.
  * **E (Estimable):** Dos saldos y reglas de actualización claras.
  * **S (Pequeña):** Cabe en una iteración si el modelo de datos ya contempla ambos medios.
  * **T (Testeable):** Se comprueba con movimientos de cada medio.

---

### **HU-32 — Registro de ingresos a la caja (RF-32)**

* **Historia de usuario:** Como administrador, quiero registrar ingresos de dinero a la caja indicando valor, fecha y concepto, para dejar constancia de la base y de otros ingresos.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el administrador tiene sesión iniciada, *cuando* registra un ingreso con valor mayor a cero, fecha y concepto, *entonces* el saldo en efectivo aumenta en ese valor y el ingreso queda en el historial.
  * *Dado* que un usuario con rol distinto a administrador accede a la caja, *cuando* intenta registrar un ingreso, *entonces* no dispone de esa opción.
  * *Dado* que el administrador deja vacío el valor, la fecha o el concepto, o ingresa un valor menor o igual a cero, *cuando* intenta registrar el ingreso, *entonces* el sistema no lo registra e indica el campo inválido.
* **Análisis INVEST:**
  * **I (Independiente):** Solo depende del inicio de sesión por roles.
  * **N (Negociable):** El formulario y los conceptos sugeridos se pueden acordar.
  * **V (Valiosa):** Permite que la caja tenga una base documentada.
  * **E (Estimable):** Formulario, validación y registro.
  * **S (Pequeña):** Cabe en una iteración.
  * **T (Testeable):** Los tres criterios se verifican directamente.

---

### **HU-33 — Retiros directos por el administrador (RF-33)**

* **Historia de usuario:** Como administrador, quiero registrar retiros directos de dinero de la caja, para sacar efectivo cuando lo necesite sin pasar por una solicitud.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que el administrador tiene sesión iniciada, *cuando* registra un retiro con valor mayor a cero, *entonces* el saldo en efectivo disminuye de inmediato en ese valor y el retiro queda en el historial.
  * *Dado* que un usuario con rol distinto a administrador accede a la caja, *cuando* intenta un retiro directo, *entonces* no dispone de esa opción.
* **Análisis INVEST:**
  * **I (Independiente):** Solo depende del inicio de sesión por roles.
  * **N (Negociable):** Si se pide un motivo y cómo se presenta la confirmación se puede acordar.
  * **V (Valiosa):** Da al administrador control directo de la caja.
  * **E (Estimable):** Formulario y actualización del saldo.
  * **S (Pequeña):** Cabe en una iteración.
  * **T (Testeable):** Ambos criterios se verifican directamente.

---

### **HU-34 — Solicitudes de retiro por cajeros (RF-34)**

* **Historia de usuario:** Como cajero, quiero enviar una solicitud de retiro indicando el valor y el motivo, para obtener la autorización del administrador antes de retirar dinero, sin que el saldo de la caja cambie hasta que se apruebe.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el cajero tiene sesión iniciada, *cuando* ingresa un valor mayor a cero y un motivo y envía la solicitud, *entonces* el sistema la registra con estado "Pendiente" y muestra una confirmación de envío.
  * *Dado* que existe una solicitud de retiro pendiente, *cuando* se consulta el saldo de caja, *entonces* el saldo es igual al que había antes de enviar la solicitud.
  * *Dado* que el cajero deja vacío el valor o el motivo, o ingresa un valor menor o igual a cero, *cuando* intenta enviar la solicitud, *entonces* el sistema no la registra e indica cuál campo es inválido.
* **Análisis INVEST:**
  * **I (Independiente):** Solo depende del inicio de sesión por roles; HU-35 y HU-36 dependen de esta.
  * **N (Negociable):** El diseño de la pantalla y los textos se pueden acordar.
  * **V (Valiosa):** Da control al administrador sobre la salida de dinero y deja constancia del motivo.
  * **E (Estimable):** Formulario, validación y registro con estado pendiente.
  * **S (Pequeña):** Un formulario y un registro.
  * **T (Testeable):** Los tres criterios se verifican directamente.

---

### **HU-35 — Notificación push de solicitudes de retiro (RF-35)**

* **Historia de usuario:** Como administrador, quiero recibir una notificación push cuando un cajero envíe una solicitud de retiro, aunque no tenga la aplicación abierta, para atenderla a tiempo.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el administrador tiene la aplicación cerrada o en segundo plano, *cuando* un cajero registra una solicitud de retiro pendiente, *entonces* el dispositivo del administrador recibe una notificación con el cajero, el valor y el motivo.
  * *Dado* que el administrador tiene la aplicación abierta, *cuando* un cajero registra una solicitud de retiro pendiente, *entonces* el administrador ve el aviso en pantalla.
  * *Dado* que el dispositivo del administrador no tenía conexión a Internet, *cuando* la recupera, *entonces* recibe la notificación de las solicitudes pendientes.
  * *Dado* que el administrador no atendió la notificación, *cuando* abre la aplicación, *entonces* la solicitud sigue visible como pendiente hasta que sea aprobada o rechazada.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de HU-34 y del servicio de notificaciones push.
  * **N (Negociable):** El texto y el sonido de la notificación se pueden acordar.
  * **V (Valiosa):** El administrador se entera sin estar pendiente de la aplicación.
  * **E (Estimable):** Requiere configurar el servicio de mensajería y el permiso de notificaciones; es el punto de mayor incertidumbre.
  * **S (Pequeña):** Cabe en una iteración si el servicio de mensajería ya está configurado; si no, conviene separar esa configuración como tarea técnica.
  * **T (Testeable):** Los cuatro criterios se verifican en un dispositivo real.

---

### **HU-36 — Aprobación o rechazo de solicitudes de retiro (RF-36)**

* **Historia de usuario:** Como administrador, quiero aprobar o rechazar las solicitudes de retiro de los cajeros, para controlar las salidas de dinero y dejar constancia de mi decisión.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que existe una solicitud de retiro pendiente, *cuando* el administrador la aprueba, *entonces* el estado cambia a "Aprobada", el saldo en efectivo disminuye en el valor solicitado y la decisión queda registrada con fecha y administrador.
  * *Dado* que existe una solicitud de retiro pendiente, *cuando* el administrador la rechaza, *entonces* el estado cambia a "Rechazada", el saldo no cambia y la decisión queda registrada.
  * *Dado* que una solicitud ya fue aprobada o rechazada, *cuando* el administrador intenta resolverla de nuevo, *entonces* el sistema no lo permite.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de HU-34; no depende de HU-35, porque puede consultar las solicitudes pendientes directamente.
  * **N (Negociable):** La forma de mostrar la lista y de pedir confirmación se puede acordar.
  * **V (Valiosa):** Cierra el flujo de control del dinero.
  * **E (Estimable):** Lista, dos acciones y actualización de saldo.
  * **S (Pequeña):** Cabe en una iteración.
  * **T (Testeable):** Los tres criterios se verifican directamente.

---

### **HU-37 — Trazabilidad de movimientos financieros (RF-37)**

* **Historia de usuario:** Como administrador, quiero que cada movimiento financiero quede registrado con su valor, concepto, fecha y solicitante, y con mi autorización en los retiros, para poder rastrear el dinero de la caja.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que se consulta el detalle de cualquier movimiento registrado (pago, ingreso o retiro), *cuando* el usuario lo abre, *entonces* se muestran el valor, el concepto, la fecha y el solicitante.
  * *Dado* que se consulta el detalle de un retiro aprobado por el administrador, *cuando* el usuario lo abre, *entonces* se muestra también la autorización del administrador.
* **Análisis INVEST:**
  * **I (Independiente):** Es transversal; se verifica junto con HU-28, HU-32, HU-33 y HU-36.
  * **N (Negociable):** Qué se muestra como "concepto" en cada tipo de movimiento se puede acordar.
  * **V (Valiosa):** Da trazabilidad y reduce disputas sobre el dinero.
  * **E (Estimable):** Los campos están definidos.
  * **S (Pequeña):** Cabe en una iteración, ya que se apoya en los registros de las otras historias.
  * **T (Testeable):** Ambos criterios se verifican en el detalle de cada movimiento.

---

### **HU-40 — Visualización del código QR en dispositivos (RF-40)**

* **Historia de usuario:** Como mesero, cajero o administrador, quiero mostrar el código QR del establecimiento desde mi dispositivo, para que el cliente pueda pagar por transferencia.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el mesero, cajero o administrador tiene sesión iniciada, *cuando* selecciona el pago por transferencia, *entonces* el sistema muestra en pantalla el código QR configurado.
  * *Dado* que el código QR se muestra, *cuando* el cliente lo escanea, *entonces* dirige a la cuenta de recepción de transferencias del establecimiento.
  * *Dado* que el código QR se muestra, *cuando* el cliente lo intenta escanear con un celular en condiciones normales de luz, *entonces* tiene tamaño y contraste suficientes para escanearse.
* **Análisis INVEST:**
  * **I (Independiente):** Depende del inicio de sesión por roles y del flujo de pago de pedidos; HU-30 es el flujo completo que incluye esta historia.
  * **N (Negociable):** Tamaño y ubicación del QR en pantalla se pueden acordar.
  * **V (Valiosa):** Habilita el pago por transferencia en el local.
  * **E (Estimable):** Una pantalla que muestra una imagen configurada.
  * **S (Pequeña):** Cabe en una iteración.
  * **T (Testeable):** Se verifica mostrando el QR y escaneándolo.

---

### **HU-41 — Registro manual de confirmación de transferencia (RF-41)**

* **Historia de usuario:** Como mesero, cajero o administrador, quiero confirmar manualmente una transferencia después de revisar el comprobante que me muestra el cliente, para registrar el pago sin depender de una pasarela de pagos.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que hay un pago por transferencia pendiente de confirmar, *cuando* el mesero, cajero o administrador presiona el botón de confirmación, *entonces* el sistema registra el pago como confirmado y guarda el cambio en la base de datos.
  * *Dado* que hay un pago por transferencia que no ha sido confirmado, *cuando* se consulta el saldo de transferencias, *entonces* ese pago no está incluido.
  * *Dado* que un usuario con un rol distinto a mesero, cajero o administrador consulta un pago pendiente, *cuando* lo abre, *entonces* no dispone del botón de confirmación.
* **Análisis INVEST:**
  * **I (Independiente):** Depende del inicio de sesión por roles y del flujo de pago de pedidos; HU-42 y HU-43 dependen de esta.
  * **N (Negociable):** La ubicación y el aspecto del botón se pueden acordar.
  * **V (Valiosa):** Permite cobrar por transferencia con control del personal.
  * **E (Estimable):** Un botón, un cambio de estado y su guardado.
  * **S (Pequeña):** Cabe en una iteración.
  * **T (Testeable):** Los tres criterios se verifican directamente.

---

### **HU-42 — Actualización del saldo de transferencias (RF-42)**

* **Historia de usuario:** Como administrador, quiero que el saldo de transferencias se actualice con cada pago confirmado, para saber cuánto dinero se ha recibido por ese medio.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el saldo de transferencias es $S$ y se confirma una transferencia de valor $V$, *cuando* se registra, *entonces* el saldo pasa a ser $S + V$ y el valor $V$ queda en el registro de transferencias.
  * *Dado* que hay un pago por transferencia sin confirmar, *cuando* se consulta el saldo de transferencias, *entonces* el saldo no cambia.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de HU-41; si el equipo lo prefiere, puede fusionarse con ella.
  * **N (Negociable):** Cómo se muestra el registro de transferencias se puede acordar.
  * **V (Valiosa):** Mantiene el saldo de transferencias al día.
  * **E (Estimable):** Una suma y un registro por pago confirmado.
  * **S (Pequeña):** Es muy pequeña; conviene valorar fusionarla con HU-41.
  * **T (Testeable):** Ambos criterios se verifican con una transferencia de prueba.

---

### **HU-43 — Prevención de doble contabilización de transferencias (RF-43)**

* **Historia de usuario:** Como cajero, quiero que el sistema impida contabilizar dos veces una misma transferencia, para evitar saldos inflados por errores como una doble pulsación.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que un pago por transferencia ya fue confirmado, *cuando* el mesero, cajero o administrador intenta confirmarlo otra vez, *entonces* el sistema no lo vuelve a sumar e informa que ya fue confirmado.
  * *Dado* que un pago ya fue confirmado, *cuando* se consulta el saldo de transferencias, *entonces* el valor de ese pago aparece una sola vez.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de HU-41, ya que protege su flujo.
  * **N (Negociable):** El mensaje que ve el usuario se puede acordar.
  * **V (Valiosa):** Evita errores en el cuadre de caja.
  * **E (Estimable):** Una validación del estado del pago.
  * **S (Pequeña):** Es muy pequeña; igual que HU-42, conviene valorar agruparlas con HU-41.
  * **T (Testeable):** Se verifica confirmando dos veces el mismo pago.

---

### **HU-44 — Cierre de caja y de la jornada (RF-44)**

* **Historia de usuario:** Como cajero o administrador, quiero cerrar la jornada (la caja del día) con un botón y una confirmación, para darla por terminada de forma controlada.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el cajero o el administrador tiene sesión iniciada, *cuando* presiona el botón "Cerrar jornada", *entonces* el sistema solicita confirmar la acción.
  * *Dado* que el cajero confirma el cierre, *cuando* el sistema lo procesa, *entonces* el cierre queda registrado con la fecha y el usuario (cajero o administrador) que lo ejecutó.
  * *Dado* que quien cierra cancela la confirmación, *cuando* vuelve a la caja, *entonces* no se registra ningún cierre.
* **Análisis INVEST:**
  * **I (Independiente):** Depende del inicio de sesión por roles; HU-45 muestra los resultados al cierre.
  * **N (Negociable):** El texto de la confirmación se puede acordar.
  * **V (Valiosa):** Formaliza el fin del día y deja registro de quién cerró.
  * **E (Estimable):** Un botón, una confirmación y un registro.
  * **S (Pequeña):** Cabe en una iteración.
  * **T (Testeable):** Los tres criterios se verifican directamente.

---

### **HU-45 — Cálculo de ingresos, egresos y saldos al cierre (RF-45)**

* **Historia de usuario:** Como cajero o administrador, quiero ver al cerrar la jornada (la caja) los ingresos, egresos y saldos finales del día separados por efectivo y transferencias, para cuadrar la jornada.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que se ejecuta el cierre, *cuando* el sistema lo procesa, *entonces* muestra el total de ingresos, el total de egresos y el saldo final de efectivo, cada uno por separado de los de transferencias.
  * *Dado* que se comparan los totales del cierre con el historial de movimientos del día, *cuando* se verifica, *entonces* coinciden con la suma de esos movimientos.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de HU-44 y de los movimientos registrados por las demás historias.
  * **N (Negociable):** El formato del resumen se puede acordar.
  * **V (Valiosa):** Permite detectar descuadres el mismo día.
  * **E (Estimable):** Sumas por medio de pago sobre los movimientos del día.
  * **S (Pequeña):** Cabe en una iteración.
  * **T (Testeable):** Se compara el resumen con el historial.

---

### **HU-47 — Registro de base y retiro al cierre de jornada (RF-47)**

* **Historia de usuario:** Como cajero o administrador, quiero registrar la base de efectivo para la siguiente jornada (y, si soy administrador, el excedente que retiro al cerrar), para saber cuánto dinero queda en la caja y cuánto salió.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que el administrador está cerrando la jornada y la suma de la base y el retiro no supera el efectivo disponible, *cuando* presiona "Confirmar", *entonces* el sistema guarda ambos valores con fecha y usuario y muestra "Base y retiro registrados".
  * *Dado* que la suma de la base y el retiro es mayor al efectivo disponible, *cuando* el administrador presiona "Confirmar", *entonces* el sistema no guarda nada y muestra "La base y el retiro superan el efectivo disponible ($XXX)."
  * *Dado* que el cajero está cerrando la jornada y la base que ingresó no supera el efectivo disponible, *cuando* presiona "Confirmar", *entonces* el sistema guarda la base con fecha y usuario y muestra "Base registrada".
  * *Dado* que la base que ingresa el cajero es mayor al efectivo disponible, *cuando* presiona "Confirmar", *entonces* el sistema no guarda nada y muestra "La base supera el efectivo disponible ($XXX)".
  * *Dado* que el cajero cierra la jornada y hay excedente por retirar, *cuando* consulta las opciones del cierre, *entonces* no dispone de la opción de registrar el retiro y debe enviar una solicitud de retiro (HU-34), que el administrador aprueba o rechaza (HU-36).
* **Análisis INVEST:**
  * **I (Independiente):** Depende del flujo de cierre (HU-48) y del cálculo de efectivo disponible.
  * **N (Negociable):** Se puede decidir si la base se escribe a mano o se sugiere un valor.
  * **V (Valiosa):** Evita que se retire dinero que no existe.
  * **E (Estimable):** Dos campos y una validación.
  * **S (Pequeña):** Es muy pequeña; conviene agruparla con HU-48.
  * **T (Testeable):** Se prueba con sumas menores, iguales y mayores al efectivo.

---

### **HU-48 — Informe de cierre de jornada (RF-48)**

* **Historia de usuario:** Como administrador, quiero un informe de cierre con saldos iniciales, ingresos, egresos, base reservada y saldos finales, para revisar cómo le fue al negocio en el día y consultarlo después.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que se completaron los pasos del cierre (incluido el registro de la base y el retiro, HU-47), *cuando* el cajero o el administrador presiona "Cerrar jornada" (el mismo cierre de HU-44), *entonces* el sistema genera y guarda un informe con saldo inicial, ingresos, egresos, base reservada y saldo final, separados por efectivo y transferencia, donde saldo final = saldo inicial + ingresos − egresos.
  * *Dado* que existe el informe de una jornada cerrada y ya se abrió una nueva jornada, *cuando* el administrador consulta los informes anteriores, *entonces* el sistema muestra el informe de esa jornada sin cambios.
* **Análisis INVEST:**
  * **I (Independiente):** No. Necesita pagos y retiros registrados (RF-28, HU-47).
  * **N (Negociable):** El diseño del informe se puede acordar.
  * **V (Valiosa):** Da una vista clara del día sin hacer cuentas a mano.
  * **E (Estimable):** Sí, una vez definidas las fuentes de datos.
  * **S (Pequeña):** Puede ser grande. Conviene dividirla en "calcular saldos" y "guardar y consultar el informe".
  * **T (Testeable):** Se verifica con la fórmula del saldo final y consultando el informe después.

---

### **HU-49 — Apertura de nueva jornada (RF-49)**

* **Historia de usuario:** Como administrador, quiero abrir una nueva jornada con la base de efectivo del cierre anterior, para empezar el día con el dinero correcto sin conservar jornadas viejas abiertas.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que la jornada anterior está cerrada con una base de $X, *cuando* el administrador presiona "Abrir jornada", *entonces* el sistema crea la nueva jornada con saldo inicial de efectivo de $X y conserva las jornadas anteriores consultables.
  * *Dado* que la jornada anterior no está cerrada, *cuando* el administrador intenta abrir una nueva jornada, *entonces* el sistema muestra "Debes cerrar la jornada anterior antes de abrir una nueva."
* **Análisis INVEST:**
  * **I (Independiente):** Depende de HU-47 y HU-48, porque toma la base del cierre.
  * **N (Negociable):** Se puede decidir si la apertura es manual o automática.
  * **V (Valiosa):** Garantiza que cada día arranque con el saldo correcto.
  * **E (Estimable):** Crear una jornada y validar el estado de la anterior.
  * **S (Pequeña):** Sí.
  * **T (Testeable):** Se prueba abriendo con la anterior cerrada y sin cerrar.

---

### **HU-50 — Registro de clientes (RF-50)**

* **Historia de usuario:** Como cliente, quiero registrarme desde la app con mi nombre, apellido, documento, celular, correo electrónico y una contraseña, y aceptar el tratamiento de mis datos, para empezar a acumular mis puntos de fidelidad en pocos minutos.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el cliente ingresó nombre, apellido, documento, celular, correo electrónico y contraseña, y aceptó el tratamiento de datos personales, *cuando* presiona "Registrarme", *entonces* el sistema crea el registro con 0 puntos de fidelidad y muestra "Registro exitoso. ¡Ya puedes empezar a acumular tus puntos de fidelidad!" en menos de 4 minutos desde que inició el formulario.
  * *Dado* que falta algún dato o el cliente no aceptó el tratamiento de datos, *cuando* presiona "Registrarme", *entonces* el sistema no guarda el registro, resalta lo que falta y muestra "Completa todos los datos y acepta el tratamiento de datos personales."
  * *Dado* que ya existe un cliente con ese documento, *cuando* otro registro intenta usarlo, *entonces* el sistema muestra "Este documento ya está registrado."
  * *Dado* que la contraseña tiene menos de 8 o más de 72 caracteres, *cuando* presiona "Registrarme", *entonces* el sistema no guarda el registro y muestra "La contraseña debe tener entre 8 y 72 caracteres."
  * *Dado* que el correo electrónico no tiene un formato válido o ya pertenece a otra cuenta, *cuando* presiona "Registrarme", *entonces* el sistema no guarda el registro y muestra "Ingresa un correo electrónico válido." o "Este correo ya está registrado.", según el caso.
* **Análisis INVEST:**
  * **I (Independiente):** Sí. Es el punto de partida de las historias de fidelización.
  * **N (Negociable):** El texto de la autorización y el diseño del formulario se pueden acordar.
  * **V (Valiosa):** Sin registro no hay puntos de fidelidad. Además cumple la Ley 1581.
  * **E (Estimable):** Un formulario con validaciones.
  * **S (Pequeña):** Sí.
  * **T (Testeable):** Se prueba con registro completo, incompleto, sin autorización, con documento repetido y con correo repetido.

---

### **HU-51 — Búsqueda de clientes por documento (RF-51)**

* **Historia de usuario:** Como mesero, quiero buscar a un cliente por su número de documento, para asociarlo rápido a su pedido sin hacerlo esperar.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el cliente está registrado, *cuando* el mesero o el administrador ingresa su documento, *entonces* el sistema muestra su nombre y sus puntos de fidelidad en máximo 2 segundos.
  * *Dado* que el documento no está registrado, *cuando* el usuario lo busca, *entonces* el sistema muestra "Cliente no encontrado" e indica que el cliente puede registrarse desde la app.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de HU-50, porque necesita clientes registrados.
  * **N (Negociable):** Se puede decidir si se busca por documento completo o parcial.
  * **V (Valiosa):** Agiliza el servicio.
  * **E (Estimable):** Una búsqueda por un campo.
  * **S (Pequeña):** Sí.
  * **T (Testeable):** Se prueba con un documento existente y uno inexistente.

---

### **HU-52 — Acumulación de puntos de fidelidad (RF-52)**

* **Historia de usuario:** Como cliente, quiero que mis puntos de fidelidad aumenten cada vez que pago un pedido, para acumularlos y poder canjear recompensas.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que un cliente tiene 2 puntos de fidelidad, *cuando* se confirma el pago de una comanda asociada a él, *entonces* el sistema aumenta sus puntos a 3.
  * *Dado* que la comanda del cliente no tiene un pago confirmado, *cuando* el cliente termina su visita, *entonces* el sistema no modifica sus puntos de fidelidad.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de HU-50, de HU-22 (asociar comanda a cliente) y de los pagos (RF-28).
  * **N (Negociable):** Se puede negociar si se suman puntos fraccionados por monto o siempre 1 por pedido pagado.
  * **V (Valiosa):** Es el corazón del sistema de fidelización.
  * **E (Estimable):** Sí; la regla está definida: 1 punto por pedido con pago confirmado.
  * **S (Pequeña):** Sí.
  * **T (Testeable):** Se prueba con pago confirmado y comanda sin pago.

---

### **HU-54 — Configuración de niveles de recompensa (RF-54)**

* **Historia de usuario:** Como administrador, quiero definir los puntos mínimos requeridos y el costo en puntos de cada recompensa, para ajustar el programa de fidelización a lo que el negocio puede ofrecer.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que el administrador ingresó los puntos mínimos requeridos, el costo en puntos y una recompensa, *cuando* presiona "Guardar nivel", *entonces* el sistema guarda el nivel y lo aplica desde ese momento.
  * *Dado* que ya existe un nivel con esos puntos mínimos requeridos, *cuando* el administrador intenta guardar otro con los mismos puntos, *entonces* el sistema muestra "Ya existe un nivel para este umbral de puntos."
* **Análisis INVEST:**
  * **I (Independiente):** Depende de HU-52 y de las recompensas (HU-60).
  * **N (Negociable):** Se puede decidir si los niveles son editables o fijos, y si el costo en puntos es igual al mínimo requerido o configurable por separado.
  * **V (Valiosa):** Da flexibilidad al dueño sin pedir cambios al equipo.
  * **E (Estimable):** Un formulario con una validación de duplicados.
  * **S (Pequeña):** Sí.
  * **T (Testeable):** Se prueba creando un nivel y repitiendo el umbral de puntos.

---

### **HU-55 — Consulta de los puntos de fidelidad por el cliente (RF-55)**

* **Historia de usuario:** Como cliente, quiero consultar mis puntos de fidelidad actuales, para saber cuánto llevo acumulado y motivarme a volver.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el cliente registrado inició sesión, *cuando* abre la sección "Mis puntos de fidelidad", *entonces* el sistema muestra sus puntos actuales en máximo 2 segundos, igual a los registrados tras su último pago confirmado.
  * *Dado* que el cliente se registró pero aún no tiene pagos confirmados, *cuando* abre la sección "Mis puntos de fidelidad", *entonces* el sistema muestra 0 puntos y el mensaje "Haz tu primer pedido para empezar a acumular puntos de fidelidad."
* **Análisis INVEST:**
  * **I (Independiente):** Depende de HU-50 y HU-52.
  * **N (Negociable):** El diseño de la pantalla se puede acordar. Las recompensas se agregan cuando entren al alcance.
  * **V (Valiosa):** El cliente ve el resultado de volver, que es el objetivo del acta.
  * **E (Estimable):** Una pantalla de solo lectura.
  * **S (Pequeña):** Sí.
  * **T (Testeable):** Se prueba con un cliente con puntos y uno sin ellos.

---

### **HU-56 — Solicitud de recompensa por el cliente (RF-56)**

* **Historia de usuario:** Como cliente, quiero pedir una recompensa disponible mientras se arma mi comanda, para aprovechar mis puntos de fidelidad en esa misma visita.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que un cliente tiene puntos de fidelidad suficientes para acceder a ciertas recompensas, *cuando* se crea su comanda, *entonces* el sistema muestra solo las recompensas que sus puntos habilitan.
  * *Dado* que el cliente tiene recompensas disponibles, *cuando* selecciona una, *entonces* la comanda la muestra como "Recompensa solicitada, pendiente de aplicar".
* **Análisis INVEST:**
  * **I (Independiente):** No. Depende de HU-54, HU-55 y del flujo de comandas.
  * **N (Negociable):** Se puede decidir si el cliente elige o solo el mesero.
  * **V (Valiosa):** Hace visible el beneficio de los puntos de fidelidad.
  * **E (Estimable):** Sí.
  * **S (Pequeña):** Sí.
  * **T (Testeable):** Se prueba con clientes con distinta cantidad de puntos.

---

### **HU-57 — Consulta de los puntos de fidelidad por el mesero (RF-57)**

* **Historia de usuario:** Como mesero, quiero ver los puntos de fidelidad de un cliente después de identificarlo por su documento, para comentarle su avance y motivarlo a volver.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que el cliente está registrado, *cuando* el mesero ingresa su documento, *entonces* el sistema muestra los puntos de fidelidad del cliente en máximo 2 segundos.
  * *Dado* que el usuario no es mesero ni administrador, *cuando* intenta consultar los puntos de fidelidad de un cliente, *entonces* el sistema le niega el acceso y muestra "No tienes permiso para realizar esta acción."
* **Análisis INVEST:**
  * **I (Independiente):** Se verifica junto con HU-51: la búsqueda por documento (RF-51) y la consulta de puntos (RF-57) son la misma pantalla; se mantiene como historia aparte solo por trazabilidad con RF-57.
  * **N (Negociable):** Se puede mostrar en la misma pantalla de búsqueda.
  * **V (Valiosa):** Mejora el trato con el cliente.
  * **E (Estimable):** Muy sencilla si ya existe HU-51.
  * **S (Pequeña):** Es muy pequeña; se implementa dentro de HU-51 y aquí solo se verifica el control de permisos.
  * **T (Testeable):** Se prueba con un mesero y con un rol sin permiso.

---

### **HU-58 — Aplicación de recompensa por el mesero (RF-58)**

* **Historia de usuario:** Como mesero, quiero aplicar a la comanda la recompensa que eligió el cliente, para que reciba su beneficio sin hacer cálculos a mano.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que el cliente seleccionó una recompensa y cumple sus condiciones, *cuando* el mesero presiona "Aplicar recompensa", *entonces* el sistema aplica la recompensa y actualiza el total de la comanda.
  * *Dado* que el cliente no cumple las condiciones de la recompensa, *cuando* el mesero intenta aplicarla, *entonces* el sistema no la aplica y explica el motivo.
* **Análisis INVEST:**
  * **I (Independiente):** No. Depende de HU-56, HU-60 y del cálculo de totales (RF-17).
  * **N (Negociable):** Se puede decidir qué tipo de recompensa se aplica (descuento o producto gratis).
  * **V (Valiosa):** Evita errores de cobro.
  * **E (Estimable):** Depende de cómo sean las recompensas.
  * **S (Pequeña):** Puede crecer si hay varios tipos de recompensa.
  * **T (Testeable):** Se prueba con un cliente que cumple y uno que no.

---

### **HU-59 — Registro de canjes de recompensas (RF-59)**

* **Historia de usuario:** Como administrador, quiero que cada canje quede registrado y la recompensa se marque como usada, para evitar que un cliente la use dos veces.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que se aplicó una recompensa a una comanda, *cuando* el canje se confirma, *entonces* el sistema lo guarda con cliente, recompensa, fecha y usuario, y marca la recompensa como usada si es de un solo uso.
  * *Dado* que una recompensa de un solo uso ya fue canjeada, *cuando* se intenta canjear de nuevo, *entonces* el sistema lo rechaza y muestra "Esta recompensa ya fue utilizada."
  * *Dado* que se confirma el canje de una recompensa, *cuando* se registra, *entonces* el sistema descuenta del cliente el costo en puntos configurado para esa recompensa y el nuevo total de puntos queda visible de inmediato.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de HU-54 (para el costo en puntos) y de HU-58.
  * **N (Negociable):** Se puede decidir qué datos del canje se guardan.
  * **V (Valiosa):** Evita pérdidas por canjes repetidos y mantiene el saldo de puntos correcto.
  * **E (Estimable):** Un registro, una validación y un descuento de puntos.
  * **S (Pequeña):** Sí. Podría agruparse con HU-58.
  * **T (Testeable):** Se prueba canjeando dos veces la misma recompensa y verificando el descuento de puntos.

---

### **HU-60 — Gestión de promociones y recompensas (RF-60)**

* **Historia de usuario:** Como administrador, quiero crear, modificar, publicar y desactivar promociones y recompensas con sus condiciones y vigencia, para atraer clientes sin pedirle cambios al equipo de desarrollo.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que el administrador ingresó las condiciones, la fecha de inicio y la fecha de fin, *cuando* presiona "Publicar", *entonces* el sistema guarda la promoción y la muestra a los clientes mientras esté vigente.
  * *Dado* que una promoción venció o fue desactivada, *cuando* un cliente consulta las promociones, *entonces* el sistema no la muestra.
  * *Dado* que la fecha de fin es anterior a la de inicio, *cuando* el administrador intenta publicar, *entonces* el sistema muestra "La fecha de fin debe ser posterior a la de inicio."
* **Análisis INVEST:**
  * **I (Independiente):** Es bastante independiente, aunque HU-54 y HU-58 la usan.
  * **N (Negociable):** Los tipos de promoción y las condiciones se pueden acordar.
  * **V (Valiosa):** Da autonomía al dueño.
  * **E (Estimable):** Difícil mientras no se definan los tipos de promoción.
  * **S (Pequeña):** No. Es grande. Conviene dividirla en crear, publicar y desactivar.
  * **T (Testeable):** Se prueba con fechas válidas, vencidas e inválidas.

---

### **HU-61 — Notificaciones de fidelización (RF-61)**

* **Historia de usuario:** Como cliente registrado, quiero recibir notificaciones sobre nuevas recompensas disponibles y promociones que cumplan las condiciones de comunicación configuradas, para conocer los beneficios que puedo aprovechar en APPRESSO.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que un cliente cumple las condiciones para recibir una notificación, *cuando* se publica una promoción aplicable o se habilita una nueva recompensa para él, *entonces* el sistema genera la notificación correspondiente.
  * *Dado* que un cliente no cumple las condiciones de una promoción, *cuando* se publica dicha promoción, *entonces* el sistema no le envía una notificación personalizada como si fuera elegible.
  * *Dado* que se genera una notificación, *cuando* el cliente consulta sus notificaciones, *entonces* puede identificar la promoción o recompensa que la originó.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de la configuración de las promociones, las recompensas y los mecanismos de comunicación del sistema.
  * **N (Negociable):** El canal de notificación, el diseño y el contenido del mensaje se pueden acordar con el cliente.
  * **V (Valiosa):** Permite que los clientes conozcan los beneficios disponibles y favorece su fidelización.
  * **E (Estimable):** Su complejidad puede estimarse a partir de las reglas de elegibilidad y del mecanismo de notificaciones seleccionado.
  * **S (Pequeña):** Puede implementarse en una iteración si los módulos de fidelización y notificaciones ya existen.
  * **T (Testeable):** Se verifica generando promociones y recompensas con distintas condiciones y comprobando las notificaciones recibidas.

---

### **HU-62 — Consulta de promociones (RF-62)**

* **Historia de usuario:** Como cliente registrado, quiero consultar las promociones publicadas y vigentes desde mi aplicación, para conocer los beneficios y descuentos que puedo aprovechar en APPRESSO.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que el cliente registrado ha iniciado sesión, *cuando* accede a la sección de promociones, *entonces* el sistema muestra las promociones publicadas y vigentes.
  * *Dado* que una promoción está vencida, inactiva o no publicada, *cuando* el cliente consulta las promociones vigentes, *entonces* dicha promoción no aparece en el listado.
  * *Dado* que una promoción está vigente, *cuando* el cliente consulta su información, *entonces* puede visualizar sus condiciones y su periodo de vigencia, siempre que estos datos hayan sido configurados.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de la existencia del módulo de promociones y del mecanismo de autenticación de clientes.
  * **N (Negociable):** La presentación de las promociones, los filtros y la organización de la información se pueden acordar.
  * **V (Valiosa):** Facilita el acceso a los beneficios disponibles y mejora la experiencia del cliente.
  * **E (Estimable):** Tiene un alcance definido, centrado en consultar y presentar las promociones vigentes.
  * **S (Pequeña):** Puede completarse en una iteración si el módulo de promociones ya está implementado.
  * **T (Testeable):** Se comprueba consultando promociones vigentes, vencidas, inactivas y no publicadas.

---

### **HU-63 — Cancelación de comandas (RF-63)**

* **Historia de usuario:** Como mesero o administrador, quiero cancelar una comanda que ya no se va a preparar ni cobrar, para que cocina deje de prepararla y el inventario quede correcto.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que una comanda está en estado `pendiente`, `enviada`, `en_preparacion` o `lista`, *cuando* el mesero o el administrador la cancela y confirma la acción, *entonces* el estado pasa a `cerrada`, queda registrada como cancelada y el cambio se refleja en todos los dispositivos conectados en menos de 3 segundos.
  * *Dado* que se cancela una comanda ya enviada, *cuando* el sistema la procesa, *entonces* desaparece de las pantallas de cocina, las existencias de sus productos se reintegran al inventario y la mesa queda disponible.
  * *Dado* que una comanda ya está cerrada (pagada o cancelada), *cuando* alguien intenta cancelarla, *entonces* el sistema no lo permite.
  * *Dado* que un usuario que no es mesero ni administrador intenta cancelar una comanda, *cuando* lo intenta, *entonces* el sistema le deniega el acceso.
  * *Dado* que se cancela una comanda, *cuando* el administrador consulta su historial, *entonces* ve la fecha, la hora y el usuario que la canceló.
* **Análisis INVEST:**
  * **I (Independiente):** Parcial; depende de HU-18 (envío) y de la reposición de existencias (HU-08).
  * **N (Negociable):** Si se pide un motivo de cancelación y el diseño de la confirmación se pueden acordar.
  * **V (Valiosa):** Evita que cocina prepare pedidos anulados y deja el inventario y el historial correctos.
  * **E (Estimable):** Un cierre anticipado de la comanda con marca de cancelación, el reintegro de existencias y la propagación a cocina.
  * **S (Pequeña):** Pequeña.
  * **T (Testeable):** Se prueba cancelar en cada estado permitido, una comanda cerrada o ya cancelada, y un rol sin permiso.

---

### **HU-64 — Creación de mesas (RF-64)**

* **Historia de usuario:** Como administrador, quiero crear las mesas del establecimiento, para que los meseros puedan abrir comandas sobre ellas.
* **Prioridad:** Alta
* **Criterios de aceptación:**
  * *Dado* que el administrador tiene sesión iniciada, *cuando* registra una mesa con un número o nombre y confirma la acción, *entonces* la mesa queda creada como disponible y aparece en el mapa de mesas de los meseros.
  * *Dado* que ya existe una mesa con ese número o nombre, *cuando* el administrador intenta crear otra igual, *entonces* el sistema no la crea e indica que ya existe.
  * *Dado* que el administrador deja vacío el número o nombre, *cuando* intenta crear la mesa, *entonces* el sistema no la crea e indica el campo inválido.
  * *Dado* que un usuario con rol distinto a administrador intenta crear una mesa, *cuando* lo intenta, *entonces* no dispone de esa opción y el sistema lo rechaza.
* **Análisis INVEST:**
  * **I (Independiente):** Solo depende del inicio de sesión por roles; HU-15 depende de esta.
  * **N (Negociable):** El formulario y la disposición de las mesas en el mapa se pueden acordar.
  * **V (Valiosa):** Sin mesas los meseros no pueden abrir comandas.
  * **E (Estimable):** Un formulario, una validación de unicidad y un registro.
  * **S (Pequeña):** Pequeña.
  * **T (Testeable):** Se prueba creando una mesa, repitiendo el nombre, con el campo vacío y con otro rol.

---

### **HU-65 — Recuperación de la contraseña del cliente (RF-65)**

* **Historia de usuario:** Como cliente, quiero recuperar el acceso a mi cuenta con un código enviado a mi correo, para no perder mis puntos de fidelidad si olvido la contraseña.
* **Prioridad:** Media
* **Criterios de aceptación:**
  * *Dado* que un cliente registrado olvidó su contraseña, *cuando* ingresa su número de documento y presiona "Enviar código", *entonces* el sistema envía a su correo un código de 6 dígitos válido durante 15 minutos y muestra "Si el documento está registrado, enviamos un código al correo asociado."
  * *Dado* que el documento no pertenece a un cliente registrado, *cuando* se solicita el código, *entonces* el sistema muestra el mismo mensaje y no envía ningún correo.
  * *Dado* que el cliente ingresa el código vigente y una contraseña nueva de entre 8 y 72 caracteres, *cuando* presiona "Cambiar contraseña", *entonces* el sistema actualiza la contraseña, invalida el código y muestra "Tu contraseña se actualizó. Ya puedes iniciar sesión."
  * *Dado* que el código es incorrecto, ya se usó o venció, *cuando* el cliente intenta cambiar la contraseña, *entonces* el sistema no la cambia y muestra "El código no es válido o venció. Solicita uno nuevo."; tras 5 intentos fallidos con el mismo código, este deja de servir.
* **Análisis INVEST:**
  * **I (Independiente):** Depende de HU-50, porque necesita la cuenta del cliente con su correo.
  * **N (Negociable):** La vigencia del código y el texto del correo se pueden acordar.
  * **V (Valiosa):** El cliente recupera su cuenta sin intervención del personal.
  * **E (Estimable):** Dos solicitudes al servidor, un código temporal y el envío de un correo.
  * **S (Pequeña):** Pequeña.
  * **T (Testeable):** Se prueba con un código correcto, uno incorrecto, uno vencido, uno ya usado y un documento no registrado.
