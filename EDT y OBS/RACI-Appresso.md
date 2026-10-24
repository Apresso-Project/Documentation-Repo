# Matriz RACI — APPRESSO

## Leyenda de roles

| Sigla | Rol | Personas |
|-------|-----|----------|
| GP | Gerente del proyecto | Felipe Salcedo |
| DA | Desarrolladores Android | Stiven Mujanajinsoy, Sebastián Aragón |
| DB | Desarrolladores Backend | Diego Bolaños, Diego Gómez |
| QA | Tester / QA | David Ascencio |
| CL | Patrocinador / Cliente | Pepito Pérez |

## Leyenda RACI

| Letra | Significado |
|-------|-------------|
| **R** | *Responsible* — ejecuta el trabajo |
| **A** | *Accountable* — responde por el resultado (único por fila) |
| **C** | *Consulted* — aporta criterio, comunicación bidireccional |
| **I** | *Informed* — recibe actualizaciones, comunicación unidireccional |

---

## Matriz

| Código | Paquete de trabajo | GP | DA | DB | QA | CL |
|--------|-------------------|----|----|----|----|----|
| **1. Gestión del proyecto** ||||||| 
| 1.1.1 | Acta de constitución | RA | I | I | I | C |
| 1.1.2 | Registro de interesados | RA | I | I | I | C |
| 1.2.1 | EDT y diccionario de la EDT | RA | C | C | C | I |
| 1.2.2 | OBS | RA | C | C | C | I |
| 1.2.3 | Cronograma | RA | C | C | C | I |
| 1.2.4 | Presupuesto | RA | C | C | C | I |
| 1.2.5 | Plan de riesgos | RA | C | C | C | C |
| 1.3.1 | Informes de avance | RA | C | C | C | I |
| 1.3.2 | Control de cambios | RA | C | C | C | C |
| 1.4.1 | Lecciones aprendidas | RA | C | C | C | I |
| 1.4.2 | Acta de cierre | RA | I | I | I | C |
| **2. Gestión de usuarios y permisos** |||||||
| 2.1.1 | Pantalla de inicio de sesión | A | R | C | I | I |
| 2.1.2 | Validación de credenciales en el backend | A | C | R | I | I |
| 2.2.1 | Pantalla de gestión de usuarios | A | R | C | I | I |
| 2.2.2 | CRUD de usuarios en el backend | A | C | R | I | I |
| 2.3.1 | Lógica de permisos en el backend | A | C | R | C | I |
| 2.3.2 | Filtrado de interfaz por rol | A | R | C | I | I |
| 2.4.1 | Configuración de acceso remoto y errores de red | A | R | C | I | I |
| **3. Catálogo e inventario** |||||||
| 3.1.1 | Pantalla CRUD de productos | A | R | C | I | I |
| 3.1.2 | Pantalla CRUD de categorías | A | R | C | I | I |
| 3.1.3 | Backend CRUD de productos y categorías | A | C | R | I | I |
| 3.2.1 | Descuento automático de stock al confirmar comanda | A | C | R | C | I |
| 3.2.2 | Ajuste manual de existencias | A | C | R | I | I |
| 3.2.3 | Alerta de stock bajo | A | C | R | I | I |
| 3.3.1 | Pantalla de menú para clientes y meseros | A | R | C | I | C |
| 3.3.2 | Sincronización en tiempo real del catálogo | A | C | R | C | I |
| **4. Comandas y pedidos** |||||||
| 4.1.1 | Pantalla de creación de comanda | A | R | C | I | I |
| 4.1.2 | Cálculo de subtotales y total | A | C | R | C | I |
| 4.1.3 | Backend de comandas | A | C | R | I | I |
| 4.2.1 | Confirmación y envío a cocina | A | R | C | I | I |
| 4.2.2 | Consulta de estado de pedidos (admin y mesero) | A | R | C | I | I |
| 4.2.3 | Modificación de comandas enviadas | A | R | C | I | I |
| 4.2.4 | Cancelación de comandas | A | C | R | I | I |
| 4.3.1 | Búsqueda y vinculación de cliente a comanda | A | R | C | I | I |
| **5. Pantalla de cocina** |||||||
| 5.1.1 | Pantalla de cocina (lista ordenada por llegada) | A | R | C | I | I |
| 5.1.2 | Sincronización en tiempo real con dispositivos de cocina | A | C | R | C | I |
| 5.2.1 | Cambio de estado por el cocinero | A | R | C | I | I |
| 5.2.2 | Notificación al mesero cuando el pedido está listo | A | R | C | I | I |
| **6. Módulo de caja** |||||||
| 6.1.1 | Pantalla de confirmación de pago | A | R | C | I | I |
| 6.1.2 | Backend de registro de pagos y saldos diferenciados | A | C | R | C | I |
| 6.2.1 | Pantalla de visualización del código QR | A | R | C | I | I |
| 6.2.2 | Confirmación manual de transferencia | A | R | C | I | I |
| 6.2.3 | Actualización de saldo y prevención de doble contabilización | A | C | R | C | I |
| 6.3.1 | Registro de ingresos por el administrador | A | R | C | I | I |
| 6.3.2 | Retiros directos del administrador | A | C | R | I | I |
| 6.3.3 | Solicitudes de retiro por cajero y notificación push | A | R | C | I | I |
| 6.3.4 | Aprobación o rechazo de solicitudes de retiro | A | R | C | I | I |
| 6.3.5 | Trazabilidad de movimientos financieros | A | C | R | I | I |
| 6.4.1 | Vista de caja del día para el cajero | A | R | C | I | I |
| 6.4.2 | Vista financiera completa para el administrador | A | R | C | I | I |
| 6.5.1 | Cierre de caja y cálculo de totales | A | C | R | C | I |
| 6.5.2 | Registro de base y retiro al cierre | A | R | C | I | I |
| 6.5.3 | Informe de cierre de jornada | A | C | R | C | I |
| 6.5.4 | Apertura de nueva jornada | A | C | R | I | I |
| **7. Fidelización de clientes** |||||||
| 7.1.1 | Formulario de registro de clientes | A | R | C | I | C |
| 7.1.2 | Búsqueda de cliente por número de documento | A | R | C | I | I |
| 7.2.1 | Lógica de acumulación de puntos por pedido | A | C | R | C | I |
| 7.2.2 | Configuración de niveles y costos de recompensa | A | R | C | I | C |
| 7.2.3 | Pantalla de consulta de puntos para el cliente | A | R | C | I | C |
| 7.2.4 | Consulta de puntos por el mesero | A | R | C | I | I |
| 7.3.1 | Solicitud de recompensa al crear la comanda | A | R | C | I | C |
| 7.3.2 | Aplicación de recompensa por el mesero | A | R | C | I | I |
| 7.3.3 | Registro de canje y descuento de puntos | A | C | R | C | I |
| 7.4.1 | Gestión de promociones por el administrador | A | R | C | I | C |
| 7.4.2 | Consulta de promociones por el cliente | A | R | C | I | C |
| 7.4.3 | Notificaciones de fidelización | A | C | R | I | C |
| **8. Infraestructura y calidad** |||||||
| 8.1.1 | Configuración del proyecto Android y estructura de módulos | A | R | C | I | I |
| 8.1.2 | Configuración del backend y base de datos | A | C | R | I | I |
| 8.2.1 | Implementación del mecanismo de sincronización | A | C | R | C | I |
| 8.3.1 | Pruebas unitarias de lógica crítica | A | C | C | R | I |
| 8.3.2 | Pruebas de integración | A | C | C | R | I |
| 8.3.3 | Pruebas de rendimiento | A | C | C | R | I |
| 8.4.1 | Cifrado de datos y protección de credenciales | A | C | R | C | I |
| 8.4.2 | Cumplimiento Ley 1581 (tratamiento de datos personales) | A | R | C | I | C |
| 8.5.1 | Configuración del entorno de producción | A | C | R | I | I |
| 8.5.2 | Documentación de instalación y manual técnico | RA | C | C | I | I |

---

## Carga por rol

| Rol | R (ejecuta) | A (responde) | C (consulta) | I (informado) |
|-----|-------------|--------------|--------------|---------------|
| GP | 12 | 76 | 0 | 0 |
| DA | 38 | 0 | 22 | 16 |
| DB | 26 | 0 | 34 | 16 |
| QA | 3 | 0 | 22 | 51 |
| CL | 0 | 0 | 18 | 58 |
