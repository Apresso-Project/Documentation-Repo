
# ACTA DE CONSTITUCIÓN DEL PROYECTO

## 1. Información general

**Appresso, septiembre de 2026.**

- **Proyecto:** Appresso, aplicación para la gestión de una cafetería.
- **Fecha:** 29/09/2026.
- **Cliente:** Cafetería CaffeBar.
- **Responsable/Patrocinador:**: Pepito Pérez.
- **Gerente del proyecto:** Andrés Felipe Salcedo Buitrago.
- **Fecha de inicio esperada:** 28/10/2026.
- **Fecha de finalización esperada:** 17/12/2026.

## 2. Definición del problema

La cafetería registra hoy los pedidos, cuadres de caja a mano, el inventario se realiza "a ojo" y se desea crear un sistema de fidelización. Esto genera errores al anotar, pérdida de información, demoras en la comunicación entre meseros y cocina, y ninguna forma de reconocer a los clientes frecuentes. Appresso centraliza la gestión de productos, pedidos y pagos en una sola aplicación, agiliza el servicio y fomenta la recurrencia de los clientes mediante un sistema de puntos de fidelidad.

## 3. Definición de los objetivos

## Objetivo general:

Entregar, a más tardar el 17 de diciembre del año 2026, la versión v1.0 de Appresso funcionando en la cafetería CaffeBar, con registro de productos, toma de pedidos con envío a cocina, módulo de puntos de fidelidad y pago por QR, y validarla en una prueba piloto de [X] días con al menos [X] pedidos completados de principio a fin sin usar papel. El desarrollo sigue el esquema semver (semver.org): las siete funcionalidades principales del sistema se liberan de forma incremental como versiones v0.1 a v0.7, y su integración completa constituye la versión v1.0.

## Objetivos específicos:

| Objetivo | Criterios de evaluación |
|----------|------------------------|
| Implementar el control de acceso por roles | (1) Los 5 roles (administrador, mesero, cajero, cocinero, cliente) acceden únicamente a las funciones que les corresponden. (2) Todo intento de acceso no autorizado retorna error 403. (3) Verificado iniciando sesión con un usuario de cada rol. |
| Registrar y gestionar productos, categorías e inventario | (1) El administrador crea, edita y desactiva productos y categorías sin asistencia técnica. (2) El stock disminuye automáticamente al confirmar una comanda; si las existencias son insuficientes, el sistema bloquea la confirmación con un mensaje de error. (3) Se genera una alerta visible en la interfaz del administrador cuando el stock de un producto cae por debajo del umbral configurado. |
| Gestionar la toma de pedidos y su comunicación en tiempo real con la cocina | (1) El mesero arma y confirma una comanda en menos de 4 minutos. (2) La comanda aparece en la pantalla de cocina en ≤ 3 s en el 95 % de los casos bajo condiciones normales de red. (3) El cocinero recibe el 100 % de los pedidos enviados sin omisiones ni errores de transcripción. |
| Procesar pagos y gestionar la caja diaria | (1) Los saldos de efectivo y transferencia se mantienen siempre separados y nunca se mezclan. (2) El informe de cierre satisface la ecuación: saldo final = saldo inicial + ingresos − egresos, verificado con pruebas automatizadas. (3) Las solicitudes de retiro del cajero llegan como notificación push al administrador en ≤ 5 s, incluso con la app cerrada. |
| Registrar clientes y operar el sistema de fidelización | (1) Un cliente nuevo se registra en menos de 4 minutos. (2) El saldo de puntos aumenta en exactamente 1 punto por cada pago confirmado y se refleja en pantalla en ≤ 2 s. (3) El cliente puede canjear una recompensa disponible según su saldo de puntos; el descuento de puntos configurado se ejecuta de inmediato. |
| Garantizar la calidad, seguridad y cumplimiento normativo del sistema | (1) La suite de pruebas unitarias cubre al menos el 70 % de la lógica crítica, medido con la herramienta de cobertura del proyecto. (2) Las contraseñas se almacenan con hash (bcrypt o equivalente); todas las comunicaciones usan HTTPS; los tokens de sesión se guardan en Android Keystore. (3) El formulario de registro exige la aceptación explícita del tratamiento de datos personales (Ley 1581 de 2012). |
| Desplegar y validar la versión v1.0 en un entorno de producción real | (1) El backend responde en producción con HTTPS antes del 17 de diciembre de 2026. (2) La prueba piloto completa al menos [X] pedidos de principio a fin sin usar papel. (3) Un nuevo integrante puede levantar el entorno de desarrollo siguiendo la documentación técnica sin asistencia adicional. |

## 4. Alcance

### 4.1. Dentro del alcance

- Inicio de sesión y acceso por roles.
- Módulo de administración: registro, edición y desactivación de productos y categorías. Inventario, existencias mínimas, alertas  y ajustes manuales.
- Módulo de caja: registro de pagos con efectivo y transferencia, con historial. Retiros, ingresos, cierre diario.
- Módulo de meseros: creación de pedidos por mesa, consulta y estados de pedido. Consulta de puntos de fidelidad del cliente por documento.
- Módulo de cocina: recepción de pedidos en tiempo real y cambio de estado (pendiente, en preparación, listo).
- Módulo de clientes: formulario de registro con un identificador (cédula), puntos de fidelidad acumulados por pedido, recompensas canjeables y promociones configurables.
- Visualización de código QR para pagos por transferencia: el QR sólo se muestra sin implementación de pasarela de pagos.
- Documentación básica.

### 4.2. Fuera del alcance

- Compra de insumos.
- Facturación electrónica y contabilidad.
- Pedidos a domicilio o en línea desde fuera de la cafetería.
- Integración automática con pasarelas de pago externas para validar transferencias (el QR se muestra, la confirmación es manual).
- Versión para iOS o para otras sucursales, sólo Android.

## 5. Suposiciones

- La cafetería cuenta con dispositivos móviles, como celulares, tablets o computadores, y con una conexión a internet estable para el uso de la aplicación por parte de los meseros y el personal de la cocina.
- El administrador proporcionará oportunamente la información necesaria sobre productos, precios, disponibilidad, promociones y beneficios de fidelización.
- El administrador y el personal de la cafetería están dispuestos a utilizar la aplicación y a participar en las capacitaciones necesarias para su correcto funcionamiento.
- Los clientes aceptarán proporcionar los datos mínimos necesarios para identificarse y participar en el programa de puntos de fidelidad.
- La cafetería cuenta con un código QR habilitado para recibir pagos, el cual será mostrado en la aplicación para facilitar el proceso de pago.
- Se podrá hacer la prueba piloto en la cafetería real para validar la usabilidad, el registro de pedidos, la comunicación con la cocina y el funcionamiento del sistema de fidelización.

## 6. Restricciones

- **Tiempo:** el desarrollo del proyecto estará limitado al tiempo establecido por el cronograma definido por el equipo.
- **Recursos:** el proyecto estará condicionado por la disponibilidad de recursos humanos, económicos y tecnológicos del equipo de desarrollo y de la cafetería.
- **Conectividad:** el funcionamiento de las funciones que requieran comunicación entre administrador, meseros y cocina rquieren de conexión a Internet Wi-fi.
- **Dispositivos:** el uso de la aplicación estará condicionado a que la cafetería disponga de dispositivos con sistema operativo Android compatibles para los usuarios que participen en la operación.
- **Información:** la configuración inicial del sistema precisa que el administrador proporcione información actualizada sobre productos, precios, disponibilidad y reglas del programa de fidelización.
- **Pruebas:** el plan de pruebas comprende: (1) **pruebas unitarias** sobre la lógica crítica de negocio — cálculo de totales, ecuación de cierre de caja y acumulación/descuento de puntos de fidelidad; (2) **pruebas de integración** para los flujos principales — comanda completa (creación → cocina → pago → puntos) y cierre de jornada; (3) **pruebas E2E** sobre los módulos de pedidos, caja y fidelización; (4) **pruebas de rendimiento** para verificar los tiempos de respuesta definidos en los requisitos no funcionales (sincronización con cocina ≤ 3 s, carga de menú ≤ 2 s, búsqueda de cliente ≤ 2 s); (5) **pruebas de control de acceso por rol** para verificar que cada endpoint y pantalla rechaza correctamente a roles no autorizados. La prueba piloto con usuarios reales estará condicionada a la disponibilidad y autorización de la cafetería CaffeBar y su personal.
- **Pagos:** los pagos se realizarán por el QR ya establecido en la cafetería.
- **Datos personales:** cumplir con la normativa de protección de datos vigente en Colombia, Ley 1581 de 2012.

## 7. Factores generales de riesgos

1. **Fallas de conexión a internet en la cafetería, que impidan que los pedidos lleguen a la cocina.**

   **Mitigación:** La app detecta el estado de la red mediante `ConnectivityManager.NetworkCallback` de Android y muestra una alerta visible en pantalla ante cualquier desconexión. Cuando la conectividad se restaura, el cliente STOMP sobre SockJS reintenta la conexión al backend Spring Boot de forma automática con retroceso exponencial, reanudando la sesión sin intervención del usuario.

2. **Baja adopción del personal o de los clientes, por resistencia al cambio o por el formulario de registro.**

   **Mitigación:** Simplificar el registro al mínimo número de datos posibles (solo número de celular, número de documento, nombre y apellido) y realizar sesiones de práctica de capacitación al personal antes de la prueba piloto.

3. **Falta de tiempo del equipo por la carga de otras materias.**

   **Mitigación:** Establecer tareas cortas por semanas y hacer reuniones de seguimiento rápido para redistribuir cargas de trabajo a tiempo.

## 8. Interesados clave

| Nombre | Rol | Qué espera | Qué podría perder o le incomoda |
|---|---|---|---|
| Pepito Pérez | Dueño / administrador de la cafetería | Un sistema que ordene la operación y le muestre los productos y pedidos. | Control informal del negocio: lo que hoy maneja "de memoria" quedará registrado y visible. |
| Carlos Andrés Ríos Torres, Laura Milena Castro López, Jorge Iván Moreno Silva | Meseros | Una herramienta rápida y fácil de usar durante el servicio. | Su forma habitual de anotar a mano; miedo a que la app los haga más lentos o a que se note cuando se equivocan. |
| María del Pilar Rodríguez Vargas, Edwin Fabián Herrera Ospina, Claudia Patricia Nieto Guerrero, Jhon Alexander Parra Reyes, Sandra Milena Useche Bermúdez | Cocineros | Recibir pedidos claros y a tiempo. | Su forma habitual de anotar a mano; miedo a que la app los haga más lentos o a que se note cuando se equivocan. |
| Diana Carolina Suárez Peña, Luis Fernando Acosta Quintero | Cajeros | Realizar cuadres de caja sin equivocaciones. | Su forma habitual de contar el dinero. Desconfianza en el sistema. |
| Clientes | Usuarios finales | Proceso de registro sencillo, pago cómodo y un beneficio por volver. | Privacidad (deben dar sus datos) y el trato informal de siempre; algunos prefieren pagar en efectivo. |
| Descompiladores | Equipo de desarrollo | Un alcance claro y realista. | Tiempo libre y otras materias. |
| Alvaro Hernando Salazar Victoria | Evaluador del proyecto | Aplicación correcta de la gestión de proyectos con PMBOK. | Nada relevante. |

## 9. Hitos principales

| Hito                                                                   | Fecha                   |
|------------------------------------------------------------------------|-------------------------|
| Aprobación del acta y del plan                                         | [29 de septiembre 2026] |
| Requisitos aprobados por el cliente                                    | [10 de octubre ]        
| Diseño y prototipo aprobado                                            | [27 de octubre 2026]    |
| Inicio de desarrollo (Sprint 0)                                        | [28 de octubre 2026]    |
| Módulos de administración, pedidos y cocina terminados                 | [15 de noviembre 2026]  |
| Módulo de fidelización (puntos y recompensas) y pago por QR terminados | [29 de noviembre 2026]  |
| Prueba piloto y entrega final                                          | [17 de diciembre 2026]  |

## 10. Aprobación

| Nombre | Rol | Fecha | Firma |
|---|---|---|---|
| Andrés Felipe Salcedo Buitrago | Gerente del proyecto | 29/09/2026 | Andrés Felipe Salcedo Buitrago |
| Diego Alejandro Gómez Puentes | Desarrollador Backend | 29/09/2026 | Diego Alejandro Gómez Puentes |
| Juan David Asencio Cacimance | Tester / QA | 29/09/2026 | Juan David Asencio Cacimance |
| Juan Sebastián Aragón Campo | Desarrollador Android | 29/09/2026 | Juan Sebastián Aragón Campo |
| David Stiven Mujanajinsoy Jayoy | Desarrollador Android | 29/09/2026 | David Stiven Mujanajinsoy Jayoy |
| Diego Bolaños Isiquita | Desarrollador Backend | 29/09/2026 | Diego Bolaños Isiquita |
| Alvaro Hernando Salazar Victoria | Docente de la asignatura | 29/09/2026 | Alvaro Hernando Salazar Victoria |
| Pepito Pérez | Patrocinador y dueño de la cafetería | 29/09/2026 | Pepito Pérez |
