@startwbs
* 0. Appresso (100 %)
     ** 1. Gestión del proyecto (10 %)
     *** 1.1 Inicio y planificación estructural
     **** 1.1.1 Documentos de inicio y planificación estructural
     *** 1.2 Planificación temporal, económica y de riesgos
     **** 1.2.1 Plan temporal, económico y de riesgos
     *** 1.3 Seguimiento, control y cierre
     **** 1.3.1 Seguimiento, control y cierre del proyecto
     ** 2. Gestión de usuarios y permisos (10 %)
     *** 2.1 Autenticación
     **** 2.1.1 Módulo de autenticación
     *** 2.2 Administración de usuarios
     **** 2.2.1 Módulo de administración de usuarios
     *** 2.3 Control de acceso y acceso remoto
     **** 2.3.1 Control de acceso por rol y acceso remoto del administrador
     ** 3. Catálogo e inventario (12 %)
     *** 3.1 Gestión de productos y categorías
     **** 3.1.1 Módulo de gestión de productos y categorías
     *** 3.2 Control de existencias
     **** 3.2.1 Módulo de control de existencias
     *** 3.3 Consulta del menú
     **** 3.3.1 Módulo de consulta del menú y visualización en cocina
     ** 4. Comandas y pedidos (13 %)
     *** 4.1 Creación de comandas
     **** 4.1.1 Módulo de creación de comandas
     *** 4.2 Gestión de pedidos
     **** 4.2.1 Módulo de envío, consulta y vinculación de clientes
     **** 4.2.2 Módulo de modificación y cancelación de pedidos
     ** 5. Pantalla de cocina (8 %)
     *** 5.1 Visualización de pedidos
     **** 5.1.1 Módulo de visualización de pedidos en cocina
     *** 5.2 Gestión de estados de preparación
     **** 5.2.1 Módulo de gestión de estados y notificación al mesero
     ** 6. Módulo de caja (22 %)
     *** 6.1 Registro de pagos
     **** 6.1.1 Módulo de registro de pagos
     *** 6.2 Gestión de transferencias
     **** 6.2.1 Módulo de gestión de transferencias QR
     *** 6.3 Ingresos, retiros y solicitudes
     **** 6.3.1 Módulo de ingresos y retiros directos
     **** 6.3.2 Módulo de solicitudes de retiro, aprobación y trazabilidad
     *** 6.4 Consulta financiera
     **** 6.4.1 Módulo de consultas financieras
     *** 6.5 Cierre y apertura de jornada
     **** 6.5.1 Módulo de cierre de caja y cálculo de totales
     **** 6.5.2 Módulo de informe de cierre y apertura de jornada
     ** 7. Fidelización de clientes (15 %)
     *** 7.1 Registro y búsqueda de clientes
     **** 7.1.1 Módulo de registro y búsqueda de clientes
     *** 7.2 Puntos de fidelidad
     **** 7.2.1 Módulo de acumulación y configuración de puntos de fidelidad
     **** 7.2.2 Módulo de consulta de puntos
     *** 7.3 Recompensas y canjes
     **** 7.3.1 Módulo de recompensas y canjes
     *** 7.4 Promociones y notificaciones
     **** 7.4.1 Módulo de promociones y notificaciones de fidelización
     ** 8. Infraestructura y calidad (10 %)
     *** 8.1 Arquitectura y configuración
     **** 8.1.1 Módulo de configuración de arquitectura del proyecto
     *** 8.2 Sincronización en tiempo real
     **** 8.2.1 Módulo de sincronización en tiempo real
     *** 8.3 Pruebas
     **** 8.3.1 Módulo de pruebas
     *** 8.4 Seguridad y cumplimiento normativo
     **** 8.4.1 Módulo de seguridad y cumplimiento normativo
     *** 8.5 Despliegue y entrega
     **** 8.5.1 Módulo de despliegue y documentación técnica
     @endwbs

' ─────────────────────────────────────────────
'  OBS — Estructura Organizacional del Proyecto
' ─────────────────────────────────────────────
@startwbs
* Proyecto Appresso
  ** Dirección del proyecto
  *** Felipe Salcedo — Gerente del proyecto (GP)
  ** Área de desarrollo
  *** Stiven Mujanajinsoy — Desarrollador Android (DA)
  *** Sebastián Aragón — Desarrollador Android (DA)
  *** Diego Bolaños — Desarrollador Backend (DB)
  *** Diego Gómez — Desarrollador Backend (DB)
  ** Área de calidad
  *** David Ascencio — Tester / QA (QA)
  ** Cliente (externo)
  *** Pepito Pérez — Patrocinador (CL)
  @endwbs



# Diccionario de la EDT — APPRESSO

> **Campos:** Código · Nombre · Descripción · Criterio de aceptación · Responsable · Esfuerzo estimado · Depende de

---

## 1. Gestión del proyecto

---

**Código:** 1.1.1
**Nombre:** Documentos de inicio y planificación estructural
**Descripción:** Entregable que agrupa los cuatro documentos que definen qué es el proyecto y cómo está organizado: (1) acta de constitución — autoriza formalmente el proyecto, define objetivo, alcance general, interesados clave y restricciones iniciales; (2) registro de interesados — lista de todas las personas y grupos con interés, con nivel de influencia, interés y estrategia de gestión; (3) EDT y diccionario de la EDT — descomposición jerárquica del alcance completo hasta nivel de entregables, con descripción, criterio de aceptación, responsable, esfuerzo y dependencias por paquete; y (4) OBS — estructura organizacional que mapea cada entregable al responsable o subequipo.
**Criterio de aceptación:** Acta firmada por el patrocinador y el equipo con objetivo, alcance, interesados y restricciones documentadas. Registro completo de interesados con nombre, rol, influencia, interés y estrategia de comunicación. EDT con 100 % del alcance cubierto y diccionario completo para todos los entregables. OBS con todos los paquetes asignados, revisada y aprobada por el equipo.
**Responsable:** Felipe Salcedo
**Esfuerzo estimado:** 13 h
**Depende de:** —

---

**Código:** 1.2.1
**Nombre:** Plan temporal, económico y de riesgos
**Descripción:** Entregable que agrupa los tres planes que definen cómo se ejecutará el proyecto: (1) cronograma — secuenciación de entregables con fechas de inicio y fin, holguras, hitos principales y ruta crítica; (2) presupuesto — estimación del costo total desglosada por paquete de trabajo, incluyendo mano de obra, herramientas y contingencias; y (3) plan de riesgos — identificación, análisis de probabilidad e impacto, y plan de respuesta para los principales riesgos, revisable en cada iteración.
**Criterio de aceptación:** Cronograma con todas las actividades secuenciadas, duraciones asignadas, holguras calculadas y ruta crítica identificada. Presupuesto detallado por paquete con costo total aprobado por el patrocinador. Registro con al menos 10 riesgos identificados, clasificados por probabilidad e impacto, con plan de respuesta documentado para los de nivel alto.
**Responsable:** Felipe Salcedo
**Esfuerzo estimado:** 12 h
**Depende de:** 1.1.1

---

**Código:** 1.3.1
**Nombre:** Seguimiento, control y cierre del proyecto
**Descripción:** Entregable que agrupa los documentos de monitoreo y cierre del ciclo de vida del proyecto: (1) informes de avance — reportes periódicos por iteración con avance real vs. planificado, indicadores SPI y CPI, riesgos activos y acciones pendientes; (2) control de cambios — proceso documentado para gestionar solicitudes de cambio al alcance, cronograma o presupuesto, con registro de decisiones; (3) lecciones aprendidas — consolidado de lo que funcionó bien y lo que debe mejorarse, organizado por área funcional; y (4) acta de cierre — documento formal que certifica la entrega y aceptación de todos los entregables y libera al equipo.
**Criterio de aceptación:** Un informe de avance emitido al cierre de cada iteración con indicadores actualizados. Todas las solicitudes de cambio registradas con decisión e impacto documentados. Documento de lecciones aprendidas aprobado por el equipo con al menos una lección por área funcional. Acta de cierre firmada por el patrocinador con todos los entregables listados y marcados como aceptados.
**Responsable:** Felipe Salcedo
**Esfuerzo estimado:** 14 h
**Depende de:** 1.2.1

---

## 2. Gestión de usuarios y permisos

---

**Código:** 2.1.1
**Nombre:** Módulo de autenticación
**Descripción:** Entregable que incluye la pantalla de inicio de sesión (campos de correo y contraseña, validación en cliente, navegación a la interfaz principal) y el endpoint de autenticación en el backend (verificación de credenciales, generación del token de sesión, respuesta con rol del usuario y manejo de intentos fallidos).
**Criterio de aceptación:** La pantalla muestra el error correcto ante credenciales inválidas y navega a la interfaz principal tras autenticación exitosa. El endpoint responde con token y rol para credenciales válidas, y con error 401 para inválidas. Las pruebas unitarias cubren credenciales válidas e inválidas.
**Responsable:** Stiven Mujanajinsoy (Android) / Diego Bolaños (Backend)
**Esfuerzo estimado:** 10 h
**Depende de:** 8.1.1
---

**Código:** 2.2.1
**Nombre:** Módulo de administración de usuarios
**Descripción:** Entregable que incluye la pantalla del administrador para listar, crear, editar y desactivar cuentas (con selector de rol y confirmación de cambios) y los endpoints de CRUD de usuarios en el backend (con validación de campos y control de acceso exclusivo para el administrador).
**Criterio de aceptación:** El administrador puede crear, editar y desactivar usuarios; los cambios se reflejan en la lista sin recargar; otros roles no acceden a la pantalla. Cada endpoint responde con error 403 para roles no autorizados. Las pruebas cubren creación, edición, desactivación y acceso no autorizado.
**Responsable:** Stiven Mujanajinsoy (Android) / Diego Bolaños (Backend)
**Esfuerzo estimado:** 10 h
**Depende de:** 2.1.1
---

**Código:** 2.3.1
**Nombre:** Control de acceso por rol y acceso remoto del administrador
**Descripción:** Entregable que integra tres componentes: (1) la capa de autorización del backend que verifica el rol en cada solicitud y bloquea operaciones no permitidas con error 403; (2) la lógica de la app que oculta o deshabilita los elementos de navegación y acciones no permitidas según el rol; y (3) la configuración del cliente HTTP para operar sobre redes externas con mensajes de error descriptivos ante pérdida de conexión.
**Criterio de aceptación:** Todo endpoint protegido rechaza solicitudes de roles no autorizados con error 403. Cada rol ve únicamente las opciones que le corresponden, verificado con los cinco roles. La app muestra "Sin conexión a Internet. Por favor, verifica tu red." ante pérdida de conexión y no se cierra inesperadamente. Las pruebas automatizadas cubren cada rol contra cada endpoint restringido.
**Responsable:** Diego Bolaños (Backend) / Stiven Mujanajinsoy (Android)
**Esfuerzo estimado:** 16 h
**Depende de:** 2.1.1, 8.1.1
---

## 3. Catálogo e inventario

---

**Código:** 3.1.1
**Nombre:** Módulo de gestión de productos y categorías
**Descripción:** Entregable que integra las pantallas del administrador para crear, editar y desactivar productos (nombre, precio, categoría, imagen y existencias iniciales) y categorías (crear, renombrar, desactivar), junto con los endpoints del backend que cubren el ciclo de vida completo de ambas entidades e incluyen validaciones de integridad referencial.
**Criterio de aceptación:** El administrador puede crear, editar y desactivar productos y categorías; los cambios se reflejan en el catálogo en tiempo real; los productos de una categoría desactivada no aparecen en el menú; roles sin permiso reciben error 403. Las pruebas cubren creación, edición, desactivación e integridad referencial.
**Responsable:** Sebastián Aragón (Android) / Diego Gómez (Backend)
**Esfuerzo estimado:** 14 h
**Depende de:** 2.3.1, 8.1.1
---

**Código:** 3.2.1
**Nombre:** Módulo de control de existencias
**Descripción:** Entregable que agrupa tres componentes de gestión de inventario: (1) la lógica de descuento automático de stock al confirmar una comanda, con manejo de concurrencia para evitar stock negativo; (2) la función de ajuste manual de existencias con registro histórico de cada movimiento; y (3) el mecanismo de alerta visual al administrador cuando el stock de un producto cae por debajo del umbral configurado.
**Criterio de aceptación:** Al confirmar una comanda las existencias disminuyen en la cantidad pedida; si no hay stock suficiente el sistema bloquea la confirmación. El administrador puede registrar ajustes manuales que quedan en el historial con concepto, valor anterior, valor nuevo y fecha. La alerta es visible para los productos con stock bajo el umbral y desaparece al reponerse.
**Responsable:** Diego Gómez (A, Backend) / Sebastián Aragón (R, Android)
**Esfuerzo estimado:** 14 h
**Depende de:** 3.1.1, 2.3.1

---

**Código:** 3.3.1
**Nombre:** Módulo de consulta del menú y visualización en cocina
**Descripción:** Entregable que incluye la pantalla de menú (vista de solo lectura para meseros y clientes con productos activos agrupados por categoría, precio y existencias actualizadas) y la pantalla de cocina en tiempo real (comandas activas ordenadas por llegada, con mesa, ítems y estado, actualizadas mediante el mecanismo de sincronización sin intervención del usuario).
**Criterio de aceptación:** La pantalla de menú muestra los productos activos con precio y existencias vigentes; los productos sin stock o desactivados no aparecen. Las comandas aparecen en la pantalla de cocina en menos de 3 segundos tras su envío y los cambios de estado se propagan en el mismo plazo. Verificado con pruebas de rendimiento bajo condiciones normales de red.
**Responsable:** Sebastián Aragón (Android) / Diego Gómez (Backend)
**Esfuerzo estimado:** 14 h
**Depende de:** 3.1.1, 8.2.1

---

## 4. Comandas y pedidos

---

**Código:** 4.1.1
**Nombre:** Módulo de creación de comandas
**Descripción:** Entregable que integra la pantalla del mesero para armar una comanda (selección de mesa, productos con cantidades y resumen previo al envío), la lógica de cálculo de subtotales y total (cantidad × precio vigente, con aplicación de descuentos autorizados) y el backend de comandas con el ciclo de vida completo: estados `pendiente`, `enviada`, `en_preparacion`, `lista` y `cerrada`, con transiciones autorizadas por rol y rechazo con error 400 ante transiciones no permitidas.
**Criterio de aceptación:** El mesero puede crear una comanda con al menos un producto y ver subtotales y total antes de confirmar; la comanda vacía no se puede enviar. El total coincide con la suma de subtotales y los descuentos se aplican correctamente. Cada transición de estado es ejecutada únicamente por el rol autorizado; cualquier transición inválida es rechazada. Las pruebas unitarias cubren los cálculos y el ciclo de vida completo.
**Responsable:** Stiven Mujanajinsoy (Android) / Diego Bolaños (Backend)
**Esfuerzo estimado:** 18 h
**Depende de:** 3.3.1, 2.3.1
---

**Código:** 4.2.1
**Nombre:** Módulo de envío, consulta y vinculación de clientes
**Descripción:** Entregable que agrupa tres funcionalidades sobre la comanda activa: (1) confirmación y envío a cocina con cambio de estado a `enviada` y manejo de errores de conexión; (2) listado de comandas del día con estado, mesa y total, con filtros por estado y por mesa, accesible para mesero y administrador; y (3) búsqueda de cliente por número de documento y vinculación a la comanda activa, mostrando puntos de fidelidad y recompensas disponibles al asociarlo.
**Criterio de aceptación:** La comanda aparece en cocina en menos de 3 segundos tras la confirmación; ante error de conexión la app avisa y no la marca como enviada. El mesero y el administrador ven las comandas del día con estado actualizado y los filtros funcionan correctamente. Un documento registrado vincula al cliente y muestra sus puntos; uno no registrado informa y permite continuar sin asociar.
**Responsable:** Stiven Mujanajinsoy (A, Android) / Diego Bolaños (R, Backend)
**Esfuerzo estimado:** 12 h
**Depende de:** 4.1.1, 3.3.1, 7.1.1

---

**Código:** 4.2.2
**Nombre:** Módulo de modificación y cancelación de pedidos
**Descripción:** Entregable que cubre las dos operaciones de alteración de una comanda ya enviada: (1) modificación, que permite al mesero agregar productos sin afectar los ítems ya en preparación, propagando los cambios a cocina y recalculando el total; y (2) cancelación, que permite al mesero o administrador anular una comanda activa, revirtiendo el descuento de stock y actualizando el estado en todos los dispositivos.
**Criterio de aceptación:** Los nuevos ítems de una modificación aparecen en cocina y el total se recalcula correctamente; los ítems en preparación no se alteran. La comanda cancelada desaparece de la vista de cocina y las existencias de los productos descontados se revierten.
**Responsable:** Diego Bolaños (A, Backend) / Stiven Mujanajinsoy (R, Android)
**Esfuerzo estimado:** 12 h
**Depende de:** 4.1.1, 3.2.1

---

## 5. Pantalla de cocina

---

**Código:** 5.1.1
**Nombre:** Módulo de visualización de pedidos en cocina
**Descripción:** Entregable que incluye la pantalla de solo lectura para cocineros (comandas activas ordenadas por hora de llegada, con mesa, ítems y estado actual, legible desde la distancia típica de una cocina) y el mecanismo de sincronización en tiempo real que entrega nuevas comandas y cambios de estado al dispositivo de cocina en menos de 3 segundos sin requerir acción del cocinero.
**Criterio de aceptación:** Todas las comandas enviadas aparecen en orden de llegada con sus ítems correctamente; una comanda confirmada por el mesero aparece en cocina en menos de 3 segundos en el 95 % de los casos bajo condiciones normales de red. Verificado con pruebas de rendimiento.
**Responsable:** Sebastián Aragón (Android) / Diego Gómez (Backend)
**Esfuerzo estimado:** 12 h
**Depende de:** 4.1.1, 8.2.1

---

**Código:** 5.2.1
**Nombre:** Módulo de gestión de estados y notificación al mesero
**Descripción:** Entregable que cubre dos componentes del flujo de preparación: (1) la función del cocinero para avanzar el estado de una comanda dentro de su dominio (`enviada → en_preparacion` al iniciar, `en_preparacion → lista` al terminar), bloqueando cualquier otra transición; y (2) el aviso visual en el dispositivo del mesero cuando el cocinero marca una comanda como "Lista", que persiste hasta ser atendido.
**Criterio de aceptación:** El cocinero puede marcar comandas como "en preparación" y "lista"; cualquier otra transición desde esta pantalla es bloqueada. El mesero ve el cambio y el aviso en su dispositivo en menos de 3 segundos. Otros roles no ven el botón de cambio de estado.
**Responsable:** Diego Gómez (A, Backend) / Sebastián Aragón (R, Android)
**Esfuerzo estimado:** 8 h
**Depende de:** 5.1.1, 4.1.1

---

## 6. Módulo de caja

---

**Código:** 6.1.1
**Nombre:** Módulo de registro de pagos
**Descripción:** Entregable que integra la pantalla de confirmación de pago (selección del medio —efectivo o transferencia— y confirmación de la transacción para cajero y mesero) y los endpoints del backend que registran cada pago con medio, valor, fecha y usuario, manteniendo los saldos de efectivo y transferencias estrictamente separados.
**Criterio de aceptación:** El cajero puede confirmar pagos en efectivo y por transferencia; el mesero solo puede confirmar transferencias; una comanda ya pagada no admite un segundo pago. Un pago en efectivo incrementa solo el saldo en efectivo y una transferencia confirmada solo el saldo de transferencias. Las pruebas verifican que los saldos no se cruzan.
**Responsable:** Stiven Mujanajinsoy (Android) / Diego Bolaños (Backend)
**Esfuerzo estimado:** 10 h
**Depende de:** 4.1.1, 2.3.1
---

**Código:** 6.2.1
**Nombre:** Módulo de gestión de transferencias QR
**Descripción:** Entregable que cubre el flujo completo de pago por transferencia: (1) pantalla que muestra el código QR del establecimiento con contraste y tamaño suficientes para ser escaneado desde un teléfono; (2) botón de confirmación manual disponible solo para mesero y cajero, que registra la verificación visual del comprobante; y (3) lógica del backend que suma el valor al saldo de transferencias únicamente al confirmar y bloquea confirmaciones duplicadas de la misma operación.
**Criterio de aceptación:** El QR se muestra al solicitar pago por transferencia y es escaneable en condiciones normales de luz. Solo mesero y cajero ven el botón de confirmación; tras confirmarlo el pago queda registrado. El saldo de transferencias aumenta exactamente el valor de cada pago confirmado una sola vez; una doble confirmación es rechazada y el saldo no cambia.
**Responsable:** Stiven Mujanajinsoy (Android) / Diego Bolaños (Backend)
**Esfuerzo estimado:** 14 h
**Depende de:** 6.1.1

---

**Código:** 6.3.1
**Nombre:** Módulo de ingresos y retiros directos
**Descripción:** Entregable que agrupa las dos operaciones de caja exclusivas del administrador: (1) registro de ingresos de efectivo con valor, fecha y concepto, que incrementa el saldo en efectivo de forma inmediata; y (2) retiros directos de efectivo que reducen el saldo al instante, ambos con registro histórico del movimiento.
**Criterio de aceptación:** Un ingreso con todos los campos válidos aumenta el saldo en efectivo y queda en el historial; campos vacíos o valor ≤ 0 son rechazados con indicación del error. El retiro reduce el saldo de inmediato y queda registrado. Roles distintos al administrador no ven ninguna de las dos opciones.
**Responsable:** Diego Bolaños (A, Backend) / Stiven Mujanajinsoy (R, Android)
**Esfuerzo estimado:** 8 h
**Depende de:** 6.1.1, 2.3.1

---

**Código:** 6.3.2
**Nombre:** Módulo de solicitudes de retiro, aprobación y trazabilidad
**Descripción:** Entregable que cubre el flujo de control de retiros del cajero y el historial financiero completo: (1) formulario del cajero para enviar solicitudes de retiro con valor y motivo, sin afectar el saldo hasta su aprobación, con notificación push al administrador aunque la app esté cerrada; (2) interfaz del administrador para aprobar o rechazar solicitudes pendientes, con efecto inmediato en el saldo al aprobar; y (3) historial de todos los movimientos de caja (pagos, ingresos, retiros) con valor, concepto, fecha, solicitante y autorización del administrador en los retiros aprobados.
**Criterio de aceptación:** La solicitud queda en estado "Pendiente" sin afectar el saldo; el administrador recibe la notificación push con cajero, valor y motivo. Aprobar reduce el saldo y cambia el estado a "Aprobada"; rechazar cambia el estado a "Rechazada" sin tocar el saldo; una solicitud resuelta no puede cambiarse. Cada movimiento del historial muestra valor, concepto, fecha y usuario; los retiros aprobados incluyen al administrador que los autorizó.
**Responsable:** Stiven Mujanajinsoy (Android) / Diego Bolaños (Backend)
**Esfuerzo estimado:** 16 h
**Depende de:** 6.3.1, 6.1.1

---

**Código:** 6.4.1
**Nombre:** Módulo de consultas financieras
**Descripción:** Entregable que incluye dos vistas de consulta diferenciadas por rol: (1) vista de solo lectura del cajero con los pagos y movimientos de la jornada actual, sin las opciones reservadas al administrador; y (2) vista completa del administrador con los saldos actuales de efectivo y transferencias por separado y el historial íntegro de movimientos con sus detalles.
**Criterio de aceptación:** El cajero ve los movimientos del día y no dispone de las opciones de registrar ingresos, retiros directos ni resolver solicitudes. El administrador ve los saldos actualizados al momento y el historial completo; los saldos coinciden con la suma de movimientos del período.
**Responsable:** Diego Bolaños (A, Backend) / Stiven Mujanajinsoy (R, Android)
**Esfuerzo estimado:** 10 h
**Depende de:** 6.3.2, 2.3.1

---

**Código:** 6.5.1
**Nombre:** Módulo de cierre de caja y cálculo de totales
**Descripción:** Entregable que cubre la ejecución del cierre de jornada: (1) función del cajero para cerrar con confirmación explícita, calculando ingresos, egresos y saldos finales diferenciados por medio de pago; y (2) paso del flujo de cierre en el que el administrador registra la base de efectivo para la siguiente jornada y el excedente que retira, validando que la suma no supere el efectivo disponible.
**Criterio de aceptación:** El cierre queda registrado con fecha y cajero; los totales de ingresos, egresos y saldos finales coinciden con la suma de los movimientos del día. La suma de base y retiro no puede superar el efectivo disponible; si la supera, el sistema rechaza la acción con el mensaje correspondiente.
**Responsable:** Diego Bolaños (Backend) / Stiven Mujanajinsoy (Android)
**Esfuerzo estimado:** 10 h
**Depende de:** 6.4.1

---

**Código:** 6.5.2
**Nombre:** Módulo de informe de cierre y apertura de jornada
**Descripción:** Entregable que cubre los dos pasos finales del ciclo de jornada: (1) generación y persistencia del informe de cierre con saldo inicial, ingresos, egresos, base reservada y saldo final separados por efectivo y transferencias, consultable en cualquier momento posterior sin cambios; y (2) apertura de la nueva jornada tomando como saldo inicial de efectivo la base registrada en el cierre anterior, bloqueando la apertura si la jornada anterior no está cerrada.
**Criterio de aceptación:** El informe se genera y guarda al cerrar; consultarlo después no muestra cambios; la fórmula saldo final = saldo inicial + ingresos − egresos se verifica con pruebas automatizadas. La nueva jornada arranca con el saldo inicial igual a la base del cierre anterior; intentar abrir sin cerrar la anterior muestra el mensaje de bloqueo.
**Responsable:** Diego Bolaños (A, Backend) / Stiven Mujanajinsoy (R, Android)
**Esfuerzo estimado:** 10 h
**Depende de:** 6.5.1

---

## 7. Fidelización de clientes

---

**Código:** 7.1.1
**Nombre:** Módulo de registro y búsqueda de clientes
**Descripción:** Entregable que integra el formulario de registro de clientes (nombre, apellido, número de documento y celular, con aceptación obligatoria del tratamiento de datos personales según la Ley 1581 de 2012) y el campo de búsqueda por número de documento para mesero y administrador, que devuelve el nombre y los puntos de fidelidad del cliente o ofrece la opción de registrarlo si no existe.
**Criterio de aceptación:** Un registro completo con autorización crea el cliente con 0 puntos en menos de 4 minutos; campos incompletos, sin autorización o con documento duplicado son rechazados con el mensaje correspondiente. Un documento registrado devuelve el cliente en menos de 2 segundos; uno no registrado muestra "Cliente no encontrado" con opción de registro. Roles sin permiso son bloqueados.
**Responsable:** Sebastián Aragón (A, Android) / Diego Gómez (R, Backend)
**Esfuerzo estimado:** 8 h
**Depende de:** 8.1.1, 8.1.2, 2.3.1

---

**Código:** 7.2.1
**Nombre:** Módulo de acumulación y configuración de puntos de fidelidad
**Descripción:** Entregable que cubre la lógica de negocio central del sistema de fidelización: (1) proceso que incrementa en 1 los puntos de un cliente cada vez que se confirma el pago de una comanda asociada a él, sin modificar los puntos si la comanda no tiene pago confirmado; y (2) interfaz y endpoints para que el administrador defina los niveles de recompensa con sus puntos mínimos requeridos y costo en puntos, rechazando umbrales duplicados.
**Criterio de aceptación:** Cada pago confirmado suma exactamente 1 punto al cliente y el nuevo saldo es visible en menos de 2 segundos; una comanda sin pago no modifica los puntos. El administrador puede crear niveles con umbral y costo en puntos; un umbral duplicado es rechazado; los niveles se aplican de inmediato. Las pruebas unitarias cubren la acumulación y los casos de borde.
**Responsable:** Diego Gómez (Backend) / Sebastián Aragón (Android)
**Esfuerzo estimado:** 12 h
**Depende de:** 7.1.1, 6.1.1, 4.2.1, 2.3.1

---

**Código:** 7.2.2
**Nombre:** Módulo de consulta de puntos
**Descripción:** Entregable que incluye las dos vistas de consulta del saldo de puntos: (1) sección "Mis puntos de fidelidad" en la app del cliente, que muestra el saldo actual con un mensaje motivacional si aún no tiene pedidos pagados; y (2) vista del mesero que muestra los puntos de un cliente identificado por su documento, implementable como extensión de la pantalla de búsqueda.
**Criterio de aceptación:** El saldo del cliente coincide con el registrado tras el último pago confirmado y se actualiza en menos de 2 segundos. El mesero ve los puntos del cliente en menos de 2 segundos tras la búsqueda. Roles sin permiso son bloqueados en ambas vistas.
**Responsable:** Sebastián Aragón
**Esfuerzo estimado:** 8 h
**Depende de:** 7.2.1, 2.3.1

---

**Código:** 7.3.1
**Nombre:** Módulo de recompensas y canjes
**Descripción:** Entregable que cubre el flujo completo de canje de recompensas: (1) paso opcional al crear la comanda que muestra solo las recompensas habilitadas por los puntos del cliente y permite seleccionar una; (2) función del mesero para aplicar la recompensa seleccionada verificando las condiciones y actualizando el total de la comanda; y (3) proceso que registra el canje con cliente, recompensa, fecha y usuario, marca la recompensa como usada si es de un solo uso, y descuenta del cliente el costo en puntos configurado de forma inmediata.
**Criterio de aceptación:** Solo se muestran recompensas cuyo umbral el cliente cumple; la seleccionada aparece como "Recompensa solicitada, pendiente de aplicar". La recompensa se aplica y el total se actualiza correctamente; si el cliente no cumple las condiciones el sistema explica el motivo. El canje queda registrado, el saldo de puntos se reduce en el costo configurado de inmediato y una recompensa de un solo uso no puede canjearse de nuevo.
**Responsable:** Sebastián Aragón (Android) / Diego Gómez (Backend)
**Esfuerzo estimado:** 14 h
**Depende de:** 7.2.1, 7.2.2, 4.1.1

---

**Código:** 7.4.1
**Nombre:** Módulo de promociones y notificaciones de fidelización
**Descripción:** Entregable que integra la gestión completa del ciclo de vida de promociones y su comunicación al cliente: (1) interfaz del administrador para crear, modificar, publicar y desactivar promociones con condiciones, fecha de inicio y fecha de fin, sin necesitar cambios en el código; (2) sección de la app del cliente que lista las promociones publicadas y vigentes con sus condiciones y período de vigencia; y (3) mecanismo de notificaciones personalizadas al cliente cuando se publica una promoción aplicable a él o se habilita una nueva recompensa acorde a sus puntos.
**Criterio de aceptación:** Una promoción publicada aparece a los clientes mientras esté vigente; una vencida o desactivada deja de mostrarse; fechas de fin anteriores al inicio son rechazadas. El cliente solo ve promociones vigentes con condiciones y fechas correctas. Un cliente elegible recibe la notificación y puede identificar la promoción o recompensa que la originó; uno no elegible no la recibe.
**Responsable:** Diego Gómez (A, Backend) / Sebastián Aragón (R, Android)
**Esfuerzo estimado:** 16 h
**Depende de:** 7.2.2, 8.1.2, 2.3.1

---

## 8. Infraestructura y calidad

---

**Código:** 8.1.1
**Nombre:** Módulo de configuración de arquitectura del proyecto
**Descripción:** Entregable que establece las bases técnicas del sistema: (1) creación del proyecto Android con Gradle, definición de la arquitectura de módulos, configuración del control de versiones y del entorno de desarrollo compartido; y (2) implementación del servidor de aplicaciones Spring Boot, conexión a la base de datos, modelos de datos iniciales de todas las entidades del proyecto y pipeline básico de integración continua.
**Criterio de aceptación:** El proyecto Android compila sin errores y la estructura de módulos está documentada. El backend responde a una solicitud de prueba y los modelos cubren todas las entidades del sistema. Cualquier integrante puede clonar y levantar ambos entornos siguiendo las instrucciones del repositorio sin asistencia adicional.
**Responsable:** Diego Gómez (A, Backend) / Sebastián Aragón (R, Android)
**Esfuerzo estimado:** 12 h
**Depende de:** —

---

**Código:** 8.2.1
**Nombre:** Módulo de sincronización en tiempo real
**Descripción:** Capa de comunicación en tiempo real mediante WebSocket STOMP sobre SockJS que propaga cambios de comandas y del catálogo a todos los dispositivos suscritos. Incluye reconexión automática con retroceso exponencial ante caídas de conexión.
**Criterio de aceptación:** Los cambios se propagan en menos de 3 segundos en el 95 % de los casos bajo condiciones normales de red. Ante una desconexión, el cliente reintenta automáticamente y reanuda la sesión al recuperar la conectividad. Verificado con pruebas de carga básicas.
**Responsable:** Diego Gómez
**Esfuerzo estimado:** 8 h
**Depende de:** 8.1.1

---

**Código:** 8.3.1
**Nombre:** Módulo de pruebas
**Descripción:** Entregable que cubre las tres capas de verificación del sistema: (1) pruebas unitarias automatizadas sobre la lógica crítica de negocio (cálculo de totales, saldos de caja, acumulación y descuento de puntos de fidelidad, cierre de jornada) con cobertura mínima del 70 %; (2) pruebas de integración que verifican los flujos completos entre módulos (comanda completa: creación → cocina → pago → puntos, y cierre de jornada); y (3) pruebas de rendimiento que verifican los tiempos de respuesta definidos en los RNF (menú en ≤ 2 s y propagación a cocina en ≤ 3 s en el 95 % de los casos).
**Criterio de aceptación:** Cobertura de al menos el 70 % de la lógica crítica medida por la herramienta de cobertura del proyecto. Los flujos de integración completos se ejecutan sin errores y los defectos encontrados están documentados y resueltos. Los tiempos medidos cumplen los umbrales de los RNF y los resultados están documentados.
**Responsable:** Diego Gómez (A) / Stiven Mujanajinsoy (R)
**Esfuerzo estimado:** 16 h
**Depende de:** 4.1.1, 6.1.1, 7.2.1, 6.5.1

---

**Código:** 8.4.1
**Nombre:** Módulo de seguridad y cumplimiento normativo
**Descripción:** Entregable que garantiza los requisitos de seguridad y legales del sistema: (1) implementación de HTTPS en todas las comunicaciones, hash de contraseñas con bcrypt y almacenamiento de tokens en Android Keystore; y (2) mecanismos requeridos por la Ley 1581 de 2012: texto de autorización en el registro de clientes, trazabilidad del consentimiento y mecanismo para solicitar la eliminación de datos personales.
**Criterio de aceptación:** Las contraseñas no se almacenan en texto plano; todas las comunicaciones usan HTTPS; los tokens se almacenan en Android Keystore. El registro de clientes exige la aceptación explícita; el texto de autorización cumple los requisitos legales; existe un mecanismo documentado para solicitar la eliminación de datos.
**Responsable:** Diego Gómez (A, Backend) / Sebastián Aragón (R, Android) / David Ascencio (R, QA)
**Esfuerzo estimado:** 10 h
**Depende de:** 8.1.1, 7.1.1

---

**Código:** 8.5.1
**Nombre:** Módulo de despliegue y documentación técnica
**Descripción:** Entregable que cierra el ciclo de entrega del sistema: (1) despliegue del backend en el servidor de producción con configuración de variables de entorno, certificados SSL y copias de seguridad automáticas de la base de datos; y (2) documento técnico con los pasos para clonar, configurar y ejecutar el proyecto en un entorno nuevo y descripción de la arquitectura para futuros mantenedores.
**Criterio de aceptación:** El backend responde en producción con HTTPS antes del 17 de diciembre de 2026; las copias de seguridad están programadas y verificadas. Un nuevo integrante puede levantar el entorno siguiendo el documento sin asistencia adicional; la arquitectura está descrita con los diagramas necesarios.
**Responsable:** Diego Gómez (Backend) / Felipe Salcedo (Documentación)
**Esfuerzo estimado:** 10 h
**Depende de:** 8.3.1

---

## Resumen de esfuerzo por bloque

| Bloque | Paquetes | Esfuerzo total estimado |
|--------|----------|------------------------|
| 1. Gestión del proyecto | 3 | 39 h |
| 2. Usuarios y permisos | 3 | 36 h |
| 3. Catálogo e inventario | 3 | 42 h |
| 4. Comandas y pedidos | 3 | 42 h |
| 5. Pantalla de cocina | 2 | 20 h |
| 6. Módulo de caja | 7 | 78 h |
| 7. Fidelización de clientes | 5 | 58 h |
| 8. Infraestructura y calidad | 5 | 56 h |
| **Total** | **31** | **371 h** |
