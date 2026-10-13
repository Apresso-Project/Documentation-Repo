
# ACTA DE CONSTITUCIÓN DEL PROYECTO

## 1. Información general

**Appresso, septiembre de 2026.**

- **Proyecto:** Appresso, aplicación para la gestión de una cafetería/restaurante/bar.
- **Fecha:** 29/09/2026.
- **Gerente del proyecto:** Andrés Felipe Salcedo Buitrago.

## 2. Justificación

La cafetería registra hoy los pedidos y su fidelización de forma manual. Esto genera errores al anotar, demoras en la comunicación entre meseros y cocina, y ninguna forma de reconocer a los clientes frecuentes. Appresso centraliza la gestión de productos, pedidos y pagos en una sola aplicación, agiliza el servicio y fomenta la recurrencia de los clientes mediante un sistema de rachas.

## 3. Objetivo

Entregar, a más tardar el [fecha finalización de curso], la versión 1.0 de Appresso funcionando en la cafetería, con registro de productos, toma de pedidos con envío a cocina, racha de fidelización y pago por QR, y validarla en una prueba piloto de [X] días con al menos [X] pedidos completados de principio a fin sin usar papel.

## 4. Alcance

### 4.1. Qué incluye

- Módulo de administración: registro, edición y desactivación de productos y categorías.
- Módulo de meseros: creación de pedidos por mesa.
- Módulo de cocina: recepción de pedidos en tiempo real y cambio de estado (pendiente, en preparación, listo).
- Módulo de clientes: formulario de registro con un identificador (cédula) y racha acumulativa por pedido.
- Visualización de código QR para pagos por transferencia.
- Documentación básica.

### 4.2. Qué NO incluye

- Compra de insumos.
- Facturación electrónica y contabilidad.
- Pedidos a domicilio o en línea desde fuera de la cafetería.
- Programa de premios más allá de la racha (canje de puntos, descuentos automáticos) [si aplica].
- Versión para iOS o para otras sucursales.

## 5. Criterios de éxito

| Interesado | Criterio de éxito |
|---|---|
| Administrador | Puede registrar y modificar productos sin ayuda técnica. |
| Mesero | Toma un pedido en menos de 4 minutos y se muestra en la cocina al instante. |
| Cocinero | Recibe el 100 % de los pedidos en pantalla, sin errores de transcripción. |
| Cliente | Se registra en menos de 4 minutos, ve su racha aumentar y paga con QR o en efectivo sin inconvenientes. |
| Equipo de desarrollo | Entrega la versión 1.0 dentro del alcance acordado y en la fecha pactada, sin superar las [X] horas semanales por integrante y sin cambios de alcance no aprobados. |
| Profesor / patrocinador académico | Recibe los entregables completos en la fecha pactada. |

## 6. Interesados clave

| Nombre | Rol | Qué espera | Qué podría perder o le incomoda |
|---|---|---|---|
| Pepito Pérez | Dueño / administrador de la cafetería | Un sistema que ordene la operación y le muestre los productos y pedidos. | Control informal del negocio: lo que hoy maneja "de memoria" quedará registrado y visible. |
| [Nombres] | Meseros | Una herramienta rápida y fácil de usar durante el servicio. | Su forma habitual de anotar a mano; miedo a que la app los haga más lentos o a que se note cuando se equivocan. |
| [Nombres] | Cocineros | Recibir pedidos claros y a tiempo. | Su forma habitual de anotar a mano; miedo a que la app los haga más lentos o a que se note cuando se equivocan. |
| Clientes | Usuarios finales | Proceso de registro sencillo, pago cómodo y un beneficio por volver. | Privacidad (deben dar sus datos) y el trato informal de siempre; algunos prefieren pagar en efectivo. |
| Descompiladores | Equipo de desarrollo | Un alcance claro y realista. | Tiempo libre y otras materias. |
| Alvaro Hernando Salazar Victoria | Evaluador del proyecto | Aplicación correcta de la gestión de proyectos con PMBOK. | Nada relevante. |

## 7. Supuestos

- La cafetería cuenta con dispositivos móviles, como celulares o tablets y con una conexión a internet estable para el uso de la aplicación por parte de los meseros y el personal de la cocina.
- El administrador proporcionará oportunamente la información necesaria sobre productos, precios, disponibilidad, promociones y beneficios de fidelización.
- El administrador y el personal de la cafetería están dispuestos a utilizar la aplicación y a participar en las capacitaciones necesarias para su correcto funcionamiento.
- Los clientes aceptarán proporcionar los datos mínimos necesarios para identificarse y participar en la racha de visitas.
- La cafetería cuenta con un código QR habilitado para recibir pagos, el cual será mostrado en la aplicación para facilitar el proceso de pago.
- Se podrá hacer la prueba piloto en la cafetería real para validar la usabilidad, el registro de pedidos, la comunicación con la cocina y el funcionamiento del sistema de fidelización.

## 8. Restricciones

- **Tiempo:** el desarrollo del proyecto estará limitado al tiempo establecido por el cronograma definido por el equipo.
- **Recursos:** el proyecto estará condicionado por la disponibilidad de recursos humanos, económicos y tecnológicos del equipo de desarrollo y de la cafetería.
- **Alcance:** la primera versión se limitará a la gestión de menú, pedidos, comunicación con cocina y sistema de fidelización, evitando incorporar funcionalidades que no hayan sido aprobadas inicialmente.
- **Conectividad:** el funcionamiento de las funciones que requieran comunicación entre administrador, meseros y cocina dependerá de la disponibilidad de conexión a Internet.
- **Dispositivos:** el uso de la aplicación estará condicionado a que la cafetería disponga de dispositivos compatibles para los usuarios que participen en la operación.
- **Información:** la configuración inicial del sistema dependerá de que el administrador proporcione información actualizada sobre productos, precios, disponibilidad y reglas del programa de fidelización.
- **Pruebas:** las pruebas con usuarios reales estarán condicionadas a la disponibilidad y autorización de la cafetería y de su personal.
- **Pagos:** el procesamiento de pagos electrónicos no hará parte de la primera versión, por lo que cualquier funcionalidad relacionada con pagos deberá ser tratada como una ampliación futura del proyecto.
- **Datos personales:** cumplir con la normativa de protección de datos vigente en Colombia, Ley 1581 de 2012.

## 9. Riesgos iniciales

1. **Integración del pago por QR más compleja de lo previsto, que retrase la entrega.**

   **Mitigación:** Definir un flujo sencillo dentro de la aplicación donde se muestre el código QR para el pago y el cliente o mesero pueda confirmar la transacción de manera clara antes de despachar el pedido.

2. **Fallas de conexión a internet en la cafetería, que impidan que los pedidos lleguen a la cocina.**

   **Mitigación:** Implementar un mecanismo de reconexión automática en la app y diseñar una alerta visible en pantalla cuando la app detecte que está fuera de línea.

3. **Baja adopción del personal o de los clientes, por resistencia al cambio o por el formulario de registro.**

   **Mitigación:** Simplificar el registro al mínimo número de datos posibles (solo número de celular, número de documento, nombre y apellido) y realizar una sesión práctica de capacitación al personal antes de la prueba piloto.

4. **Falta de tiempo del equipo por la carga de otras materias.**

   **Mitigación:** Establecer tareas cortas por semanas y hacer reuniones de seguimiento rápido para redistribuir cargas de trabajo a tiempo.

## 10. Hitos principales

| Hito | Fecha |
|---|---|
| Aprobación del acta y del plan | [29 de septiembre 2026] |
| Diseño y prototipo aprobado | [6 de octubre 2026] |
| Módulos de administración, pedidos y cocina terminados | [25 de octubre 2026] |
| Racha de fidelización y pago por QR terminados | [10 de noviembre 2026] |
| Prueba piloto y entrega final | [17 de diciembre 2026] |

## 11. Aprobación

| Nombre | Rol | Fecha | Firma |
|---|---|---|---|
| [Andrés Felipe Salcedo Buitrago] | Gerente del proyecto y desarrollador | 29/09/2026 | Andrés Felipe Salcedo Buitrago |
| [Diego Gómez Puente] | Gerente del proyecto y desarrollador | 29/09/2026 | Diego Alejandro Gómez Puentes |
| [Juan David Asencio] | Programador | 29/09/2026 | Juan David Asencio Cacimance |
| [Juan Sebastián Aragón Campo] | Programador | 29/09/2026 | Juan Sebastián Aragón Campo |
| [David Steven Mujanajinsoy jajoy] | Programador | 29/09/2026 | David Steven Mujanajinsoy jayoy |
| [Alvaro Hernando Salazar Victoria] | Docente de la asignatura | 29/09/2026 | Alvaro Hernando Salazar Victoria |
| [Pepito Pérez] | Patrocinador y dueño de la cafetería | 29/09/2026 | Pepito Pérez |
