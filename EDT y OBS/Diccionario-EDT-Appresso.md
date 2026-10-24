# Diccionario de la EDT — APPRESSO

> **Campos:** Código · Nombre · Descripción · Criterio de aceptación · Responsable · Esfuerzo estimado · Depende de

---

## 1. Gestión del proyecto

---

**Código:** 1.1.1
**Nombre:** Acta de constitución
**Descripción:** Documento formal que autoriza el proyecto, define su objetivo, alcance general, partes interesadas clave y restricciones iniciales. Constituye el punto de partida de toda la planificación.
**Criterio de aceptación:** Documento firmado por el patrocinador y el equipo, con objetivo, alcance, interesados y restricciones documentadas.
**Responsable:** Felipe Salcedo
**Esfuerzo estimado:** 3 h
**Depende de:** —

---

**Código:** 1.1.2
**Nombre:** Registro de interesados
**Descripción:** Lista de todas las personas o grupos con interés en el proyecto (dueño, equipo, meseros, cajeros, cocineros, clientes). Incluye nivel de influencia, interés y estrategia de gestión para cada uno.
**Criterio de aceptación:** Registro completo con nombre, rol, nivel de influencia, interés y estrategia de comunicación para cada interesado.
**Responsable:** Felipe Salcedo
**Esfuerzo estimado:** 3 h
**Depende de:** 1.1.1

---

**Código:** 1.2.1
**Nombre:** EDT y diccionario de la EDT
**Descripción:** Descomposición jerárquica del alcance total hasta nivel de paquetes de trabajo. El diccionario describe cada paquete con descripción, criterio de aceptación, responsable, esfuerzo estimado y dependencias.
**Criterio de aceptación:** EDT con 100 % del alcance cubierto y diccionario completo para todos los paquetes de trabajo.
**Responsable:** Felipe Salcedo
**Esfuerzo estimado:** 4 h
**Depende de:** 1.1.1

---

**Código:** 1.2.2
**Nombre:** OBS
**Descripción:** Estructura organizacional del proyecto que mapea cada paquete de trabajo a la persona o subequipo responsable. Permite visualizar la distribución de carga de trabajo.
**Criterio de aceptación:** OBS completa con todos los paquetes asignados, revisada y aprobada por el equipo.
**Responsable:** Felipe Salcedo
**Esfuerzo estimado:** 3 h
**Depende de:** 1.2.1

---

**Código:** 1.2.3
**Nombre:** Cronograma
**Descripción:** Secuenciación de los paquetes de trabajo con fechas de inicio y fin, holguras e hitos principales. Incluye la ruta crítica del proyecto.
**Criterio de aceptación:** Cronograma con todas las actividades secuenciadas, duraciones asignadas, holguras calculadas y ruta crítica identificada.
**Responsable:** Felipe Salcedo
**Esfuerzo estimado:** 4 h
**Depende de:** 1.2.1, 1.2.2

---

**Código:** 1.2.4
**Nombre:** Presupuesto
**Descripción:** Estimación del costo total del proyecto desglosada por paquete de trabajo. Incluye costo de mano de obra, herramientas y contingencias.
**Criterio de aceptación:** Presupuesto detallado por paquete de trabajo con costo total calculado y aprobado por el patrocinador.
**Responsable:** Felipe Salcedo
**Esfuerzo estimado:** 4 h
**Depende de:** 1.2.1, 1.2.3

---

**Código:** 1.2.5
**Nombre:** Plan de riesgos
**Descripción:** Identificación, análisis (probabilidad e impacto) y plan de respuesta para los principales riesgos del proyecto. Se revisa en cada iteración.
**Criterio de aceptación:** Registro con al menos 10 riesgos identificados, clasificados por probabilidad e impacto, con plan de respuesta documentado para los de nivel alto.
**Responsable:** Felipe Salcedo
**Esfuerzo estimado:** 4 h
**Depende de:** 1.2.1

---

**Código:** 1.3.1
**Nombre:** Informes de avance
**Descripción:** Reportes periódicos del estado del proyecto: avance real versus planificado, indicadores SPI y CPI, riesgos activos y acciones pendientes. Se emite uno por iteración.
**Criterio de aceptación:** Un informe emitido al cierre de cada iteración, con indicadores actualizados, revisado por el equipo y archivado en el repositorio.
**Responsable:** Felipe Salcedo
**Esfuerzo estimado:** 4 h
**Depende de:** 1.2.3, 1.2.4

---

**Código:** 1.3.2
**Nombre:** Control de cambios
**Descripción:** Proceso documentado para gestionar solicitudes de cambio al alcance, cronograma o presupuesto. Incluye el registro de solicitudes y las decisiones tomadas.
**Criterio de aceptación:** Todas las solicitudes de cambio registradas con su decisión (aprobada/rechazada) e impacto documentado.
**Responsable:** Felipe Salcedo
**Esfuerzo estimado:** 4 h
**Depende de:** 1.2.1, 1.2.3

---

**Código:** 1.4.1
**Nombre:** Lecciones aprendidas
**Descripción:** Documento que consolida lo que funcionó bien y lo que debe mejorarse, organizado por área funcional. Sirve como referencia para proyectos futuros.
**Criterio de aceptación:** Documento revisado y aprobado por todo el equipo, con al menos una lección aprendida por área funcional.
**Responsable:** Felipe Salcedo
**Esfuerzo estimado:** 3 h
**Depende de:** 1.3.1

---

**Código:** 1.4.2
**Nombre:** Acta de cierre
**Descripción:** Documento formal que certifica la entrega y aceptación de todos los entregables del proyecto y libera al equipo de sus responsabilidades.
**Criterio de aceptación:** Acta firmada por el patrocinador y el líder del proyecto, con todos los entregables listados y marcados como aceptados.
**Responsable:** Felipe Salcedo
**Esfuerzo estimado:** 3 h
**Depende de:** 1.4.1

---

## 2. Gestión de usuarios y permisos

---

**Código:** 2.1.1
**Nombre:** Pantalla de inicio de sesión
**Descripción:** Interfaz para ingresar correo electrónico y contraseña. Incluye validación de campos, mensajes de error para credenciales inválidas y navegación a la pantalla principal tras autenticación exitosa.
**Criterio de aceptación:** La pantalla valida el formulario en el cliente, muestra el error correcto ante credenciales inválidas y navega a la interfaz principal tras autenticación exitosa.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 4 h
**Depende de:** 8.1.1

---

**Código:** 2.1.2
**Nombre:** Validación de credenciales en el backend
**Descripción:** Endpoint de autenticación que verifica correo y contraseña, genera el token de sesión y responde con el rol del usuario. Incluye manejo de intentos fallidos.
**Criterio de aceptación:** El endpoint responde con token y rol para credenciales válidas, y con error 401 para inválidas. Las pruebas unitarias cubren ambos casos.
**Responsable:** Diego Bolaños
**Esfuerzo estimado:** 6 h
**Depende de:** 8.1.2

---

**Código:** 2.2.1
**Nombre:** Pantalla de gestión de usuarios
**Descripción:** Interfaz del administrador para listar, crear, editar y desactivar cuentas de usuario. Incluye el selector de rol y la confirmación de cambios.
**Criterio de aceptación:** El administrador puede crear, editar y desactivar usuarios; los cambios se reflejan en la lista sin recargar; otros roles no acceden a esta pantalla.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 6 h
**Depende de:** 2.1.1, 2.3.2

---

**Código:** 2.2.2
**Nombre:** CRUD de usuarios en el backend
**Descripción:** Endpoints para crear, consultar, actualizar y desactivar cuentas. Incluye validación de campos y control de acceso (solo el administrador puede invocarlos).
**Criterio de aceptación:** Cada endpoint responde correctamente para el administrador y con error 403 para otros roles. Las pruebas cubren creación, edición, desactivación y acceso no autorizado.
**Responsable:** Diego Bolaños
**Esfuerzo estimado:** 4 h
**Depende de:** 2.1.2, 8.1.2

---

**Código:** 2.3.1
**Nombre:** Lógica de permisos en el backend
**Descripción:** Capa de autorización que verifica el rol del usuario en cada solicitud y bloquea las operaciones no permitidas con error 403. Define la matriz completa de roles y permisos.
**Criterio de aceptación:** Todo endpoint protegido rechaza solicitudes de roles no autorizados con error 403. Las pruebas automatizadas cubren cada rol contra cada endpoint restringido.
**Responsable:** Diego Bolaños
**Esfuerzo estimado:** 6 h
**Depende de:** 2.1.2

---

**Código:** 2.3.2
**Nombre:** Filtrado de interfaz por rol
**Descripción:** Lógica en la app móvil que oculta o deshabilita los elementos de navegación y las acciones no permitidas según el rol del usuario autenticado.
**Criterio de aceptación:** Cada rol solo ve las opciones que le corresponden. Verificado iniciando sesión con cada uno de los cinco roles (administrador, cajero, mesero, cocinero, cliente).
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 4 h
**Depende de:** 2.1.1, 2.3.1

---

**Código:** 2.4.1
**Nombre:** Configuración de acceso remoto y manejo de errores de red
**Descripción:** Configuración del cliente HTTP para operar sobre redes externas e implementación de mensajes de error descriptivos ante pérdida de conexión o latencia alta.
**Criterio de aceptación:** La app muestra el mensaje "Sin conexión a Internet. Por favor, verifica tu red." ante pérdida de conexión y no se cierra inesperadamente. Verificado simulando corte de red.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 6 h
**Depende de:** 8.1.1, 8.1.2

---

## 3. Catálogo e inventario

---

**Código:** 3.1.1
**Nombre:** Pantalla CRUD de productos
**Descripción:** Interfaz del administrador para crear, editar y desactivar productos, con campos de nombre, precio, categoría, imagen y existencias iniciales.
**Criterio de aceptación:** El administrador puede crear, editar y desactivar un producto; los cambios se reflejan en el catálogo en tiempo real; roles sin permiso no acceden a esta pantalla.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 6 h
**Depende de:** 3.1.3, 2.3.2

---

**Código:** 3.1.2
**Nombre:** Pantalla CRUD de categorías
**Descripción:** Interfaz del administrador para crear, renombrar y desactivar las categorías que agrupan los productos del menú.
**Criterio de aceptación:** El administrador puede crear, renombrar y desactivar categorías; los productos de una categoría desactivada no aparecen en el menú.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 4 h
**Depende de:** 3.1.3, 2.3.2

---

**Código:** 3.1.3
**Nombre:** Backend CRUD de productos y categorías
**Descripción:** Endpoints para gestionar el ciclo de vida completo de productos y categorías: creación, consulta, actualización y desactivación. Incluye validaciones de integridad referencial.
**Criterio de aceptación:** Cada operación se ejecuta correctamente para el administrador y es rechazada con error 403 para otros roles. Las pruebas cubren creación, edición, desactivación e integridad referencial.
**Responsable:** Diego Gómez
**Esfuerzo estimado:** 4 h
**Depende de:** 2.3.1, 8.1.2

---

**Código:** 3.2.1
**Nombre:** Descuento automático de stock al confirmar comanda
**Descripción:** Lógica que reduce las existencias de cada producto al confirmar una comanda. Incluye manejo de concurrencia para evitar stock negativo.
**Criterio de aceptación:** Al confirmar una comanda, las existencias disminuyen en la cantidad pedida; si no hay stock suficiente, el sistema lo informa y no permite confirmar.
**Responsable:** Diego Gómez
**Esfuerzo estimado:** 6 h
**Depende de:** 3.1.3, 4.1.3

---

**Código:** 3.2.2
**Nombre:** Ajuste manual de existencias
**Descripción:** Función para que el administrador corrija el stock de un producto ingresando el nuevo valor y un concepto de ajuste. El ajuste queda en el historial.
**Criterio de aceptación:** El administrador puede modificar las existencias de cualquier producto; el ajuste queda registrado con concepto, valor anterior, valor nuevo y fecha.
**Responsable:** Diego Gómez
**Esfuerzo estimado:** 4 h
**Depende de:** 3.1.3, 2.3.1

---

**Código:** 3.2.3
**Nombre:** Alerta de stock bajo
**Descripción:** Mecanismo que genera una alerta visible en la interfaz del administrador cuando las existencias de un producto caen por debajo del umbral configurado.
**Criterio de aceptación:** El administrador ve una alerta identificable para los productos con stock bajo el umbral; la alerta desaparece cuando el stock es repuesto.
**Responsable:** Diego Gómez
**Esfuerzo estimado:** 4 h
**Depende de:** 3.2.1, 3.2.2

---

**Código:** 3.3.1
**Nombre:** Pantalla de menú para clientes y meseros
**Descripción:** Vista de solo lectura que muestra los productos activos agrupados por categoría, con precio y existencias actualizadas. Es la base para crear comandas.
**Criterio de aceptación:** La pantalla muestra todos los productos activos con precio y existencias vigentes; los productos sin stock o desactivados no aparecen.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 6 h
**Depende de:** 3.1.3, 3.3.2

---

**Código:** 3.3.2
**Nombre:** Sincronización en tiempo real del catálogo
**Descripción:** Capa de comunicación que propaga los cambios del catálogo (precios, existencias, disponibilidad) a todos los dispositivos conectados sin requerir recarga manual.
**Criterio de aceptación:** Un cambio realizado por el administrador se refleja en los dispositivos de meseros y clientes en menos de 3 segundos.
**Responsable:** Diego Gómez
**Esfuerzo estimado:** 8 h
**Depende de:** 8.2.1, 3.1.3

---

## 4. Comandas y pedidos

---

**Código:** 4.1.1
**Nombre:** Pantalla de creación de comanda
**Descripción:** Interfaz del mesero para armar una comanda: seleccionar mesa, agregar productos con sus cantidades y ver el resumen antes de enviar a cocina.
**Criterio de aceptación:** El mesero puede crear una comanda con al menos un producto, ver el subtotal por ítem y el total, y confirmar el envío; la comanda vacía no se puede enviar.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 6 h
**Depende de:** 3.3.1, 2.3.2, 4.1.3

---

**Código:** 4.1.2
**Nombre:** Cálculo de subtotales y total
**Descripción:** Lógica de negocio que calcula el subtotal de cada ítem (cantidad × precio vigente) y la suma total de la comanda, aplicando descuentos autorizados como los de puntos de fidelidad.
**Criterio de aceptación:** El total coincide con la suma de subtotales; un descuento aplicado reduce el total correctamente. Los cálculos se verifican con pruebas unitarias.
**Responsable:** Diego Bolaños
**Esfuerzo estimado:** 6 h
**Depende de:** 4.1.3, 3.1.3

---

**Código:** 4.1.3
**Nombre:** Backend de comandas
**Descripción:** Endpoints para crear, consultar, actualizar y cancelar comandas. Define los estados del ciclo de vida (pendiente, enviada, en preparación, lista, cerrada) y las reglas de transición entre ellos.
**Criterio de aceptación:** Cada transición de estado válida se ejecuta correctamente; las transiciones inválidas son rechazadas. Las pruebas cubren el ciclo completo de una comanda.
**Responsable:** Diego Bolaños
**Esfuerzo estimado:** 6 h
**Depende de:** 2.3.1, 8.1.2

---

**Código:** 4.2.1
**Nombre:** Confirmación y envío a cocina
**Descripción:** Función que cambia el estado de la comanda a "Enviada" y la hace visible en la pantalla de cocina. Incluye manejo de errores de conexión al momento del envío.
**Criterio de aceptación:** La comanda aparece en la pantalla de cocina en menos de 3 segundos tras la confirmación; ante error de conexión, la app avisa y no marca la comanda como enviada.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 4 h
**Depende de:** 4.1.3, 5.1.1

---

**Código:** 4.2.2
**Nombre:** Consulta de estado de pedidos (admin y mesero)
**Descripción:** Listado de comandas del día con su estado, mesa y total, accesible para mesero y administrador. Incluye filtros por estado y por mesa.
**Criterio de aceptación:** El mesero y el administrador ven las comandas del día con estado actualizado; los filtros funcionan correctamente; otros roles son bloqueados.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 4 h
**Depende de:** 4.1.3, 2.3.2

---

**Código:** 4.2.3
**Nombre:** Modificación de comandas enviadas
**Descripción:** Función que permite al mesero agregar productos a una comanda ya enviada, registrando los nuevos ítems sin afectar los que ya están en preparación.
**Criterio de aceptación:** Los nuevos ítems aparecen en la comanda en cocina; el total se recalcula correctamente; los ítems en preparación no se alteran.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 6 h
**Depende de:** 4.1.3, 4.2.1

---

**Código:** 4.2.4
**Nombre:** Cancelación de comandas
**Descripción:** Función que permite al mesero o administrador cancelar una comanda activa, revertir el descuento de stock y actualizar el estado en todos los dispositivos.
**Criterio de aceptación:** La comanda cancelada desaparece de la vista de cocina; las existencias de los productos descontados se revierten correctamente.
**Responsable:** Diego Bolaños
**Esfuerzo estimado:** 6 h
**Depende de:** 4.1.3, 3.2.1

---

**Código:** 4.3.1
**Nombre:** Búsqueda y vinculación de cliente a comanda
**Descripción:** Función del mesero para asociar un cliente registrado a una comanda activa mediante su número de documento. Muestra sus puntos de fidelidad y recompensas disponibles al vincularlo.
**Criterio de aceptación:** Un documento registrado vincula al cliente y muestra sus puntos y recompensas; un documento no registrado muestra el mensaje correspondiente y permite continuar sin asociar.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 4 h
**Depende de:** 4.1.3, 7.1.2

---

## 5. Pantalla de cocina

---

**Código:** 5.1.1
**Nombre:** Pantalla de cocina (lista ordenada por llegada)
**Descripción:** Interfaz de solo lectura para cocineros que muestra las comandas activas ordenadas por hora de llegada, con sus ítems y estado actual.
**Criterio de aceptación:** Todas las comandas enviadas aparecen en orden de llegada; los ítems de cada comanda se muestran correctamente; la pantalla es legible desde la distancia típica de una cocina.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 4 h
**Depende de:** 4.1.3, 2.3.2

---

**Código:** 5.1.2
**Nombre:** Sincronización en tiempo real con dispositivos de cocina
**Descripción:** Implementación del mecanismo que entrega las nuevas comandas y los cambios de estado a la pantalla de cocina en menos de 3 segundos, sin requerir acción del cocinero.
**Criterio de aceptación:** Una comanda confirmada por el mesero aparece en cocina en menos de 3 segundos en el 95 % de los casos bajo condiciones normales de red.
**Responsable:** Diego Gómez
**Esfuerzo estimado:** 8 h
**Depende de:** 5.1.1, 8.2.1

---

**Código:** 5.2.1
**Nombre:** Cambio de estado por el cocinero
**Descripción:** Función que permite al cocinero marcar una comanda como "En preparación" o "Lista", actualizando el estado en el backend y en los dispositivos del mesero.
**Criterio de aceptación:** El mesero ve el cambio de estado en su dispositivo en menos de 3 segundos; solo el cocinero puede cambiar el estado desde esta pantalla.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 4 h
**Depende de:** 5.1.1, 4.1.3

---

**Código:** 5.2.2
**Nombre:** Notificación al mesero cuando el pedido está listo
**Descripción:** Aviso visual en el dispositivo del mesero cuando el cocinero marca una comanda como "Lista", para que la recoja y la lleve a la mesa.
**Criterio de aceptación:** El dispositivo del mesero muestra un aviso identificable cuando su comanda pasa a "Lista"; el aviso persiste hasta que el mesero lo atiende.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 4 h
**Depende de:** 5.2.1

---

## 6. Módulo de caja

---

**Código:** 6.1.1
**Nombre:** Pantalla de confirmación de pago
**Descripción:** Interfaz para cajero y mesero que permite seleccionar el medio de pago (efectivo o transferencia) de una comanda y confirmar la transacción.
**Criterio de aceptación:** El cajero puede confirmar pagos en efectivo y por transferencia; el mesero puede confirmar transferencias; una comanda ya pagada no admite un segundo pago.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 4 h
**Depende de:** 4.1.3, 2.3.2

---

**Código:** 6.1.2
**Nombre:** Backend de registro de pagos y saldos diferenciados
**Descripción:** Endpoints que registran cada pago con medio, valor, fecha y usuario, y actualizan el saldo correspondiente (efectivo o transferencias) sin mezclarlos.
**Criterio de aceptación:** Un pago en efectivo incrementa solo el saldo en efectivo; una transferencia confirmada incrementa solo el saldo de transferencias. Las pruebas verifican que los saldos no se cruzan.
**Responsable:** Diego Bolaños
**Esfuerzo estimado:** 6 h
**Depende de:** 4.1.3, 2.3.1, 8.1.2

---

**Código:** 6.2.1
**Nombre:** Pantalla de visualización del código QR
**Descripción:** Pantalla que muestra el código QR del establecimiento al seleccionar pago por transferencia, con contraste y tamaño suficientes para ser escaneado desde un teléfono a distancia normal.
**Criterio de aceptación:** El QR se muestra al solicitar pago por transferencia y un teléfono con condiciones normales de luz lo escanea sin dificultad.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 4 h
**Depende de:** 6.1.1

---

**Código:** 6.2.2
**Nombre:** Confirmación manual de transferencia
**Descripción:** Botón para el mesero y el cajero que registra la confirmación visual de una transferencia. Una transferencia sin confirmar no se suma al saldo.
**Criterio de aceptación:** Solo el mesero y el cajero ven el botón; tras confirmarlo, el pago queda registrado; una transferencia ya confirmada no puede confirmarse de nuevo.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 4 h
**Depende de:** 6.2.1, 6.1.2

---

**Código:** 6.2.3
**Nombre:** Actualización de saldo y prevención de doble contabilización
**Descripción:** Lógica que suma el valor de cada transferencia confirmada al saldo de transferencias y bloquea confirmaciones duplicadas de la misma operación.
**Criterio de aceptación:** El saldo de transferencias aumenta exactamente el valor de cada pago confirmado una sola vez; una doble confirmación es rechazada y el saldo no cambia.
**Responsable:** Diego Bolaños
**Esfuerzo estimado:** 6 h
**Depende de:** 6.2.2

---

**Código:** 6.3.1
**Nombre:** Registro de ingresos por el administrador
**Descripción:** Formulario y endpoint para que el administrador registre ingresos de efectivo a la caja con valor, fecha y concepto. Incrementa el saldo en efectivo de forma inmediata.
**Criterio de aceptación:** Un ingreso con todos los campos válidos aumenta el saldo en efectivo y queda en el historial; campos vacíos o valor ≤ 0 son rechazados con indicación del error.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 4 h
**Depende de:** 6.1.2, 2.3.1

---

**Código:** 6.3.2
**Nombre:** Retiros directos del administrador
**Descripción:** Función que permite al administrador retirar efectivo de la caja de forma inmediata, reduciendo el saldo al instante y dejando registro del movimiento.
**Criterio de aceptación:** El retiro reduce el saldo en efectivo de inmediato y queda registrado; roles distintos al administrador no ven esta opción.
**Responsable:** Diego Bolaños
**Esfuerzo estimado:** 4 h
**Depende de:** 6.1.2, 2.3.1

---

**Código:** 6.3.3
**Nombre:** Solicitudes de retiro por cajero y notificación push
**Descripción:** Formulario para que el cajero envíe una solicitud de retiro con valor y motivo. Al enviarse, el saldo no cambia y se despacha una notificación push al dispositivo del administrador, aunque la app esté cerrada.
**Criterio de aceptación:** La solicitud queda en estado "Pendiente" sin afectar el saldo; el administrador recibe la notificación push con cajero, valor y motivo; campos inválidos son rechazados.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 6 h
**Depende de:** 6.1.2, 2.3.1

---

**Código:** 6.3.4
**Nombre:** Aprobación o rechazo de solicitudes de retiro
**Descripción:** Interfaz del administrador para ver las solicitudes pendientes y aprobarlas o rechazarlas. La aprobación descuenta el valor del saldo; el rechazo lo deja intacto.
**Criterio de aceptación:** Aprobar reduce el saldo y cambia el estado a "Aprobada"; rechazar cambia el estado a "Rechazada" sin tocar el saldo; una solicitud resuelta no puede cambiarse.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 4 h
**Depende de:** 6.3.3

---

**Código:** 6.3.5
**Nombre:** Trazabilidad de movimientos financieros
**Descripción:** Historial completo de todos los movimientos de caja (pagos, ingresos, retiros) con valor, concepto, fecha, solicitante y, en retiros aprobados, la autorización del administrador.
**Criterio de aceptación:** Cada movimiento muestra valor, concepto, fecha y usuario; los retiros aprobados muestran también al administrador que los autorizó.
**Responsable:** Diego Bolaños
**Esfuerzo estimado:** 6 h
**Depende de:** 6.1.2, 6.3.1, 6.3.2, 6.3.4

---

**Código:** 6.4.1
**Nombre:** Vista de caja del día para el cajero
**Descripción:** Pantalla de solo lectura para el cajero con los pagos y movimientos de la jornada actual. No incluye las opciones reservadas al administrador.
**Criterio de aceptación:** El cajero ve los movimientos del día; no dispone de las opciones de registrar ingresos, retiros directos ni resolver solicitudes.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 4 h
**Depende de:** 6.3.5, 2.3.2

---

**Código:** 6.4.2
**Nombre:** Vista financiera completa para el administrador
**Descripción:** Pantalla del administrador con los saldos actuales (efectivo y transferencias por separado) y el historial completo de movimientos con sus detalles.
**Criterio de aceptación:** El administrador ve los saldos actualizados al momento y el historial completo; los saldos coinciden con la suma de movimientos del período.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 6 h
**Depende de:** 6.3.5, 2.3.2

---

**Código:** 6.5.1
**Nombre:** Cierre de caja y cálculo de totales
**Descripción:** Función para que el cajero ejecute el cierre de la jornada con confirmación explícita. Al cerrarse, el sistema calcula ingresos, egresos y saldos finales diferenciados por medio de pago.
**Criterio de aceptación:** El cierre queda registrado con fecha y cajero; los totales de ingresos, egresos y saldos finales coinciden con la suma de los movimientos del día.
**Responsable:** Diego Bolaños
**Esfuerzo estimado:** 6 h
**Depende de:** 6.4.2

---

**Código:** 6.5.2
**Nombre:** Registro de base y retiro al cierre
**Descripción:** Paso del flujo de cierre en el que el administrador registra el efectivo que queda como base de la siguiente jornada y el excedente que retira.
**Criterio de aceptación:** La suma de base y retiro no puede superar el efectivo disponible; si la supera, el sistema rechaza la acción con el mensaje correspondiente.
**Responsable:** Stiven Mujanajinsoy
**Esfuerzo estimado:** 4 h
**Depende de:** 6.5.1

---

**Código:** 6.5.3
**Nombre:** Informe de cierre de jornada
**Descripción:** Documento generado y guardado al finalizar el cierre, con saldo inicial, ingresos, egresos, base reservada y saldo final separados por efectivo y transferencias.
**Criterio de aceptación:** El informe se genera y guarda al cerrar; consultarlo después no muestra cambios; la fórmula saldo final = saldo inicial + ingresos − egresos se verifica con pruebas.
**Responsable:** Diego Bolaños
**Esfuerzo estimado:** 6 h
**Depende de:** 6.5.2

---

**Código:** 6.5.4
**Nombre:** Apertura de nueva jornada
**Descripción:** Función que inicia una nueva jornada tomando como saldo inicial de efectivo la base registrada en el cierre anterior. Bloquea la apertura si la jornada anterior no está cerrada.
**Criterio de aceptación:** La nueva jornada arranca con el saldo inicial igual a la base del cierre anterior; abrir sin cerrar la anterior muestra el mensaje de bloqueo.
**Responsable:** Diego Bolaños
**Esfuerzo estimado:** 4 h
**Depende de:** 6.5.3

---

## 7. Fidelización de clientes

---

**Código:** 7.1.1
**Nombre:** Formulario de registro de clientes
**Descripción:** Pantalla para registrar un cliente con nombre, apellido, número de documento y celular, con aceptación obligatoria del tratamiento de datos personales (Ley 1581 de 2012).
**Criterio de aceptación:** Un registro completo con autorización crea el cliente con 0 puntos en menos de 4 minutos; campos incompletos o sin autorización muestran el error; un documento duplicado es rechazado.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 4 h
**Depende de:** 8.1.1, 8.1.2

---

**Código:** 7.1.2
**Nombre:** Búsqueda de cliente por número de documento
**Descripción:** Campo de búsqueda para mesero y administrador que devuelve el nombre y los puntos de fidelidad del cliente en menos de 2 segundos. Si no existe, ofrece la opción de registrarlo.
**Criterio de aceptación:** Un documento registrado devuelve el cliente en menos de 2 segundos; uno no registrado muestra "Cliente no encontrado" con opción de registro; roles sin permiso son bloqueados.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 4 h
**Depende de:** 7.1.1, 2.3.2

---

**Código:** 7.2.1
**Nombre:** Lógica de acumulación de puntos por pedido
**Descripción:** Proceso que incrementa en 1 los puntos de fidelidad de un cliente cada vez que se confirma el pago de una comanda asociada a él. Una comanda sin pago no modifica los puntos.
**Criterio de aceptación:** Cada pago confirmado suma exactamente 1 punto al cliente; una comanda sin pago no modifica los puntos. Las pruebas unitarias cubren ambos casos.
**Responsable:** Diego Gómez
**Esfuerzo estimado:** 6 h
**Depende de:** 7.1.1, 6.1.2, 4.3.1

---

**Código:** 7.2.2
**Nombre:** Configuración de niveles y costos de recompensa
**Descripción:** Interfaz y endpoints para que el administrador defina los puntos mínimos requeridos y el costo en puntos de cada nivel de recompensa.
**Criterio de aceptación:** El administrador puede crear niveles con umbral y costo en puntos; un umbral duplicado es rechazado; los niveles creados se aplican de inmediato.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 6 h
**Depende de:** 7.2.1, 2.3.1

---

**Código:** 7.2.3
**Nombre:** Pantalla de consulta de puntos para el cliente
**Descripción:** Sección "Mis puntos de fidelidad" donde el cliente registrado consulta su saldo actual. Muestra 0 puntos con mensaje motivacional si aún no tiene pedidos pagados.
**Criterio de aceptación:** El saldo mostrado coincide con el registrado tras el último pago confirmado y se actualiza en menos de 2 segundos.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 4 h
**Depende de:** 7.2.1, 2.3.2

---

**Código:** 7.2.4
**Nombre:** Consulta de puntos por el mesero
**Descripción:** Vista del mesero que muestra los puntos de fidelidad de un cliente identificado por su documento. Puede implementarse como extensión de la pantalla de búsqueda (7.1.2).
**Criterio de aceptación:** El mesero ve los puntos del cliente en menos de 2 segundos tras la búsqueda; roles sin permiso son bloqueados.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 4 h
**Depende de:** 7.1.2, 7.2.1

---

**Código:** 7.3.1
**Nombre:** Solicitud de recompensa al crear la comanda
**Descripción:** Paso opcional al crear una comanda que muestra solo las recompensas habilitadas por los puntos del cliente y permite seleccionar una para aplicarla.
**Criterio de aceptación:** Solo se muestran recompensas cuyo umbral el cliente cumple; la seleccionada aparece en la comanda como "Recompensa solicitada, pendiente de aplicar".
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 4 h
**Depende de:** 7.2.2, 7.2.1, 4.1.1

---

**Código:** 7.3.2
**Nombre:** Aplicación de recompensa por el mesero
**Descripción:** Función del mesero para aplicar a la comanda la recompensa solicitada por el cliente, verificando condiciones y actualizando el total.
**Criterio de aceptación:** La recompensa se aplica y el total se actualiza correctamente; si el cliente no cumple las condiciones, el sistema explica el motivo y no la aplica.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 4 h
**Depende de:** 7.3.1, 4.1.2

---

**Código:** 7.3.3
**Nombre:** Registro de canje y descuento de puntos
**Descripción:** Proceso que guarda el canje con cliente, recompensa, fecha y usuario; marca la recompensa como usada si es de un solo uso; y descuenta del cliente el costo en puntos configurado para esa recompensa.
**Criterio de aceptación:** El canje queda registrado; el saldo de puntos se reduce en el costo configurado de inmediato; una recompensa de un solo uso no puede canjearse de nuevo.
**Responsable:** Diego Gómez
**Esfuerzo estimado:** 6 h
**Depende de:** 7.3.2, 7.2.2, 7.2.1

---

**Código:** 7.4.1
**Nombre:** Gestión de promociones por el administrador
**Descripción:** Módulo para crear, modificar, publicar y desactivar promociones con sus condiciones, fecha de inicio y fecha de fin. El administrador opera sin necesitar cambios en el código.
**Criterio de aceptación:** Una promoción publicada aparece a los clientes mientras esté vigente; una vencida o desactivada deja de mostrarse; fechas de fin anteriores al inicio son rechazadas.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 6 h
**Depende de:** 8.1.2, 2.3.1

---

**Código:** 7.4.2
**Nombre:** Consulta de promociones por el cliente
**Descripción:** Sección de la app del cliente que lista las promociones publicadas y vigentes con sus condiciones y período de vigencia.
**Criterio de aceptación:** El cliente solo ve promociones vigentes; las vencidas, inactivas o no publicadas no aparecen; condiciones y fechas se muestran correctamente.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 4 h
**Depende de:** 7.4.1, 2.3.2

---

**Código:** 7.4.3
**Nombre:** Notificaciones de fidelización
**Descripción:** Mecanismo que genera notificaciones personalizadas al cliente cuando se publica una promoción aplicable a él o se habilita una nueva recompensa acorde a sus puntos.
**Criterio de aceptación:** Un cliente elegible recibe la notificación; uno no elegible no la recibe; el cliente puede identificar la promoción o recompensa que la originó.
**Responsable:** Diego Gómez
**Esfuerzo estimado:** 6 h
**Depende de:** 7.4.1, 7.2.2

---

## 8. Infraestructura y calidad

---

**Código:** 8.1.1
**Nombre:** Configuración del proyecto Android y estructura de módulos
**Descripción:** Creación del proyecto Android con Gradle, definición de la arquitectura de módulos, configuración del control de versiones y del entorno de desarrollo compartido.
**Criterio de aceptación:** El proyecto compila sin errores; la estructura de módulos está documentada; cualquier integrante puede clonar y ejecutar el proyecto siguiendo las instrucciones del repositorio.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 6 h
**Depende de:** —

---

**Código:** 8.1.2
**Nombre:** Configuración del backend y base de datos
**Descripción:** Implementación del servidor de aplicaciones, conexión a la base de datos, modelos de datos iniciales de todas las entidades del proyecto y pipeline básico de integración continua.
**Criterio de aceptación:** El backend responde a una solicitud de prueba; los modelos cubren todas las entidades del sistema; el repositorio incluye instrucciones para levantar el entorno local.
**Responsable:** Diego Gómez
**Esfuerzo estimado:** 6 h
**Depende de:** —

---

**Código:** 8.2.1
**Nombre:** Implementación del mecanismo de sincronización (cocina y menú)
**Descripción:** Capa de comunicación en tiempo real (WebSocket, SSE u otra tecnología elegida) que propaga cambios de comandas y del catálogo a los dispositivos suscritos.
**Criterio de aceptación:** Los cambios se propagan en menos de 3 segundos en el 95 % de los casos bajo condiciones normales de red, verificado con pruebas de carga básicas.
**Responsable:** Diego Gómez
**Esfuerzo estimado:** 8 h
**Depende de:** 8.1.2

---

**Código:** 8.3.1
**Nombre:** Pruebas unitarias de lógica crítica
**Descripción:** Suite de pruebas automatizadas para la lógica de negocio crítica: cálculo de totales, saldos de caja, acumulación y descuento de puntos de fidelidad, y cierre de jornada.
**Criterio de aceptación:** Cobertura de al menos el 70 % de la lógica crítica, medida por la herramienta de cobertura del proyecto.
**Responsable:** David Ascencio
**Esfuerzo estimado:** 6 h
**Depende de:** 4.1.2, 6.1.2, 7.2.1, 6.5.1

---

**Código:** 8.3.2
**Nombre:** Pruebas de integración
**Descripción:** Pruebas que verifican la interacción entre módulos principales: flujo completo de una comanda (creación → cocina → pago → puntos) y flujo de cierre de jornada.
**Criterio de aceptación:** Los flujos completos identificados se ejecutan sin errores en el entorno de pruebas; los defectos encontrados están documentados y resueltos.
**Responsable:** David Ascencio
**Esfuerzo estimado:** 6 h
**Depende de:** 8.3.1

---

**Código:** 8.3.3
**Nombre:** Pruebas de rendimiento
**Descripción:** Verificación de los tiempos de respuesta definidos en los RNF: menú en ≤ 2 s y propagación de comandas a cocina en ≤ 3 s, ambos en el 95 % de los casos.
**Criterio de aceptación:** Los tiempos medidos cumplen los umbrales de los RNF en las condiciones de prueba definidas; los resultados están documentados.
**Responsable:** David Ascencio
**Esfuerzo estimado:** 4 h
**Depende de:** 8.3.2

---

**Código:** 8.4.1
**Nombre:** Cifrado de datos y protección de credenciales
**Descripción:** Implementación de HTTPS en todas las comunicaciones, hash de contraseñas con algoritmo seguro (bcrypt o similar) y almacenamiento seguro de tokens en el dispositivo.
**Criterio de aceptación:** Las contraseñas no se almacenan en texto plano; todas las comunicaciones usan HTTPS; los tokens se almacenan en el almacenamiento seguro del dispositivo (Android Keystore).
**Responsable:** Diego Gómez
**Esfuerzo estimado:** 6 h
**Depende de:** 8.1.2, 2.1.2

---

**Código:** 8.4.2
**Nombre:** Cumplimiento Ley 1581 (tratamiento de datos personales)
**Descripción:** Implementación de los mecanismos requeridos por la Ley 1581: texto de autorización en el registro de clientes, trazabilidad del consentimiento y mecanismo para solicitar eliminación de datos.
**Criterio de aceptación:** El registro exige la aceptación explícita; el texto de autorización cumple los requisitos legales; existe un mecanismo documentado para solicitar la eliminación de datos.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 4 h
**Depende de:** 7.1.1

---

**Código:** 8.5.1
**Nombre:** Configuración del entorno de producción
**Descripción:** Despliegue del backend en el servidor de producción, configuración de variables de entorno, certificados SSL y copias de seguridad automáticas de la base de datos.
**Criterio de aceptación:** El backend responde en producción con HTTPS; las copias de seguridad están programadas y verificadas; el entorno está documentado.
**Responsable:** Diego Gómez
**Esfuerzo estimado:** 6 h
**Depende de:** 8.3.2

---

**Código:** 8.5.2
**Nombre:** Documentación de instalación y manual técnico
**Descripción:** Documento con los pasos para clonar, configurar y ejecutar el proyecto en un entorno nuevo, y descripción de la arquitectura técnica para futuros mantenedores.
**Criterio de aceptación:** Un nuevo integrante puede levantar el entorno siguiendo el documento sin asistencia adicional; la arquitectura está descrita con los diagramas necesarios.
**Responsable:** Felipe Salcedo
**Esfuerzo estimado:** 4 h
**Depende de:** 8.5.1

---

## Resumen de esfuerzo por bloque

| Bloque | Paquetes | Esfuerzo total estimado |
|--------|----------|------------------------|
| 1. Gestión del proyecto | 11 | 39 h |
| 2. Usuarios y permisos | 7 | 36 h |
| 3. Catálogo e inventario | 8 | 42 h |
| 4. Comandas y pedidos | 8 | 42 h |
| 5. Pantalla de cocina | 4 | 20 h |
| 6. Módulo de caja | 16 | 78 h |
| 7. Fidelización de clientes | 12 | 58 h |
| 8. Infraestructura y calidad | 10 | 56 h |
| **Total** | **76** | **371 h** |
