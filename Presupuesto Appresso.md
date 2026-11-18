# PRESUPUESTO — APPRESSO

> **Estado:** borrador v0.3 (17 de noviembre de 2026), por aprobar por el patrocinador. Cambios frente a la v0.2 (correcciones de la sustentación de métricas): se agrega el costo de Claude Code a los costos directos y se aclara que las horas por encima del plan son horas extra que deben aprobarse (sección 7). Cambio de la v0.1 a la v0.2: el hosting pasó a planes gratuitos (Neon y Render).
> **Responsable:** Felipe Salcedo (entregable 1.2.1 — Plan temporal, económico y de riesgos).
> **Moneda:** pesos colombianos (COP).
> **Fuentes:** [Cronograma](cronograma-Appresso.md) (horas por entregable) y [Plan de Riesgos](Plan%20de%20Riesgos%20Appresso.md) (estimación inicial) y [Seguimiento de Riesgos](Seguimiento%20de%20Riesgos%20Appresso.md) (respuestas y exposición vigentes).

## 1. Supuestos

> **Estos valores son supuestos del gerente, no datos del cliente ni cotizaciones.** Hay que reemplazarlos por los valores reales antes de la aprobación. Cambiar una fila de esta tabla recalcula todo el presupuesto.

| Supuesto | Valor | Observación |
|----------|:-----:|-------------|
| Tarifa única por hora-persona | **$15.000** | Referencia para un desarrollador junior en Colombia. Es la misma para todo el equipo, incluido el gerente y el tester. |
| Horas por entregable | Las del cronograma | Se toma el esfuerzo (h) de cada entregable. Total: **371 h**. |
| Hosting: backend en Render y base de datos en Neon | **$0** | Planes gratuitos elegidos el 10/11/2026. Si resultan insuficientes (R-14), se agrega el costo de un plan de pago. |
| Dominio | USD 12 al año | Dominio .com. Si se prefiere .co, el valor es mayor. |
| Claude Code | USD 20 al mes (plan Pro), 2 meses | Una sola licencia, que paga el gerente. Cubre el desarrollo asistido de octubre a diciembre. Se paga el 28/10 y el 28/11 (por confirmar con el gerente). |
| Certificado HTTPS | $0 | Incluido en el hosting (por confirmar en Render). |
| Tasa de cambio | $4.000 por USD | Referencia; actualizar con la tasa del día de la compra. |
| Reserva para costos directos | 25 % | Cubre costos directos no previstos, como pasar a un plan de pago si los gratuitos no bastan (R-12, R-14). |

---

## 2. Costo de los entregables

Costo = horas del cronograma × tarifa por hora.

### Bloque 1 — Gestión del proyecto

| Código | Entregable | Horas | Costo |
|--------|-----------|:-----:|------:|
| 1.1.1 | Documentos de inicio y planificación estructural | 13 | $195.000 |
| 1.2.1 | Plan temporal, económico y de riesgos | 12 | $180.000 |
| 1.3.1 | Seguimiento, control y cierre del proyecto | 14 | $210.000 |
| | **Subtotal** | **39** | **$585.000** |

### Bloque 2 — Gestión de usuarios y permisos

| Código | Entregable | Horas | Costo |
|--------|-----------|:-----:|------:|
| 2.1.1 | Módulo de autenticación | 10 | $150.000 |
| 2.2.1 | Módulo de administración de usuarios | 10 | $150.000 |
| 2.3.1 | Control de acceso por rol y acceso remoto del administrador | 16 | $240.000 |
| | **Subtotal** | **36** | **$540.000** |

### Bloque 3 — Catálogo e inventario

| Código | Entregable | Horas | Costo |
|--------|-----------|:-----:|------:|
| 3.1.1 | Módulo de gestión de productos y categorías | 14 | $210.000 |
| 3.2.1 | Módulo de control de existencias | 14 | $210.000 |
| 3.3.1 | Módulo de consulta del menú y visualización en cocina | 14 | $210.000 |
| | **Subtotal** | **42** | **$630.000** |

### Bloque 4 — Comandas y pedidos

| Código | Entregable | Horas | Costo |
|--------|-----------|:-----:|------:|
| 4.1.1 | Módulo de creación de comandas | 18 | $270.000 |
| 4.2.1 | Módulo de envío, consulta y vinculación de clientes | 12 | $180.000 |
| 4.2.2 | Módulo de modificación y cancelación de pedidos | 12 | $180.000 |
| | **Subtotal** | **42** | **$630.000** |

### Bloque 5 — Pantalla de cocina

| Código | Entregable | Horas | Costo |
|--------|-----------|:-----:|------:|
| 5.1.1 | Módulo de visualización de pedidos en cocina | 12 | $180.000 |
| 5.2.1 | Módulo de gestión de estados y notificación al mesero | 8 | $120.000 |
| | **Subtotal** | **20** | **$300.000** |

### Bloque 6 — Módulo de caja

| Código | Entregable | Horas | Costo |
|--------|-----------|:-----:|------:|
| 6.1.1 | Módulo de registro de pagos | 10 | $150.000 |
| 6.2.1 | Módulo de gestión de transferencias QR | 14 | $210.000 |
| 6.3.1 | Módulo de ingresos y retiros directos | 8 | $120.000 |
| 6.3.2 | Módulo de solicitudes de retiro, aprobación y trazabilidad | 16 | $240.000 |
| 6.4.1 | Módulo de consultas financieras | 10 | $150.000 |
| 6.5.1 | Módulo de cierre de caja y cálculo de totales | 10 | $150.000 |
| 6.5.2 | Módulo de informe de cierre y apertura de jornada | 10 | $150.000 |
| | **Subtotal** | **78** | **$1.170.000** |

### Bloque 7 — Fidelización de clientes

| Código | Entregable | Horas | Costo |
|--------|-----------|:-----:|------:|
| 7.1.1 | Módulo de registro y búsqueda de clientes | 8 | $120.000 |
| 7.2.1 | Módulo de acumulación y configuración de puntos de fidelidad | 12 | $180.000 |
| 7.2.2 | Módulo de consulta de puntos | 8 | $120.000 |
| 7.3.1 | Módulo de recompensas y canjes | 14 | $210.000 |
| 7.4.1 | Módulo de promociones y notificaciones de fidelización | 16 | $240.000 |
| | **Subtotal** | **58** | **$870.000** |

### Bloque 8 — Infraestructura y calidad

| Código | Entregable | Horas | Costo |
|--------|-----------|:-----:|------:|
| 8.1.1 | Módulo de configuración de arquitectura del proyecto | 12 | $180.000 |
| 8.2.1 | Módulo de sincronización en tiempo real | 8 | $120.000 |
| 8.3.1 | Módulo de pruebas | 16 | $240.000 |
| 8.4.1 | Módulo de seguridad y cumplimiento normativo | 10 | $150.000 |
| 8.5.1 | Módulo de despliegue y documentación técnica | 10 | $150.000 |
| | **Subtotal** | **56** | **$840.000** |

### Resumen por bloque

| Bloque | Horas | Costo | % del costo de entregables |
|--------|:-----:|------:|:--------------------------:|
| 1. Gestión del proyecto | 39 | $585.000 | 10,5 % |
| 2. Usuarios y permisos | 36 | $540.000 | 9,7 % |
| 3. Catálogo e inventario | 42 | $630.000 | 11,3 % |
| 4. Comandas y pedidos | 42 | $630.000 | 11,3 % |
| 5. Pantalla de cocina | 20 | $300.000 | 5,4 % |
| 6. Módulo de caja | 78 | $1.170.000 | 21,0 % |
| 7. Fidelización de clientes | 58 | $870.000 | 15,6 % |
| 8. Infraestructura y calidad | 56 | $840.000 | 15,1 % |
| **Total** | **371** | **$5.565.000** | **100 %** |

---

## 3. Estimación inicial de las respuestas a los riesgos críticos

Referencia histórica de la sección 5.4 del plan. La estimación vigente se debe conciliar por tarea con el cronograma y el registro de horas, descontando el trabajo ya incluido en los entregables.

| Riesgo | Respuesta | Horas | Costo |
|:------:|-----------|:-----:|------:|
| R-01 | Recalcular el cronograma, paralelizar y escalar | 32 | $480.000 |
| R-02 | Calendario de parciales y reasignación de trabajo | 12 | $180.000 |
| R-10 | Tutorial dirigido de Spring Boot y revisión de código | 16 | $240.000 |
| R-11 | Prototipo de STOMP/SockJS y prueba de latencia | 16 | $240.000 |
| R-12 | Elección del hosting y despliegue de prueba temprano | 20 | $300.000 |
| | **Total** | **96** | **$1.440.000** |

---

## 4. Costos directos (no son horas de trabajo)

Entran en la línea base de costo (BAC) junto con la mano de obra. Se pagan en pesos, no en horas, y se consideran ganados cuando se incurren.

| Concepto | Cálculo | Costo |
|----------|---------|------:|
| Hosting (Render + Neon, planes gratuitos) | Gratuito | $0 |
| Dominio | USD 12 × $4.000 | $48.000 |
| Certificado HTTPS | Incluido en el hosting | $0 |
| Claude Code (plan Pro, 1 licencia) | USD 20 × 2 meses × $4.000 | $160.000 |
| | **Total** | **$208.000** |

---

## 5. Reserva de contingencia

El cálculo inicial combinó la exposición residual estimada de los cinco riesgos críticos originales (133,5 h) y una previsión para costos directos. La cifra queda como referencia histórica. La revisión vigente debe valorar los riesgos abiertos, la recuperación pendiente y los gastos directos por separado, según la conciliación en el seguimiento.

| Concepto | Cálculo | Costo |
|----------|---------|------:|
| Riesgos críticos residuales | 133,5 h × $15.000 | $2.002.500 |
| Costos directos | 25 % × $208.000 | $52.000 |
| | **Total** | **$2.054.500** |

---

## 6. Presupuesto inicial y estado vigente

| Concepto | Costo | % del total |
|----------|------:|:-----------:|
| Entregables del cronograma (371 h) | $5.565.000 | 60,0 % |
| Respuestas a los riesgos críticos (96 h) | $1.440.000 | 15,5 % |
| Costos directos (dominio y Claude Code; el hosting es gratuito) | $208.000 | 2,2 % |
| **Estimación de costos** | **$7.213.000** | **77,8 %** |
| Reserva de contingencia | $2.054.500 | 22,2 % |
| **Presupuesto total de referencia (estimación inicial de riesgos)** | **$9.267.500** | **100 %** |

- **Horas totales de referencia:** 371 h de entregables + 96 h de respuestas + 133,5 h de reserva = **600,5 h**.
- **Reserva de gestión:** no se incluye. Los imprevistos que no estén en el plan de riesgos requieren una decisión del patrocinador.
- **Sensibilidad a la tarifa del cálculo de referencia:** cada $1.000 de cambio en la tarifa por hora cambia el presupuesto en $600.500, porque las horas son 600,5 h (los costos directos no dependen de la tarifa).
- **Línea base de costo para las métricas (BAC):** 371 h de entregables ($5.565.000) + costos directos ($208.000) = **$5.773.000**. Las respuestas a riesgos y la reserva siguen fuera del BAC.
- **Actualización pendiente de cuantificar:** costo de recuperación de R-01, R-02 y R-10, respuestas y exposición residual de los críticos abiertos (R-05, R-11, R-12 y R-13), y gastos directos asociados. El total actualizado queda pendiente de validar y aprobar. El cálculo histórico permite reconstruir la estimación original.

---

## 7. Cómo se controla

- **Reserva de contingencia:** solo se gasta cuando un riesgo se materializa (estado *Materializado* en el [seguimiento de riesgos](Seguimiento%20de%20Riesgos%20Appresso.md)). Cada uso aprobado se anota con el riesgo, el paquete, las horas o el gasto directo y la fecha. Si el costo es compartido, se registra una sola vez con todos los riesgos relacionados.
- **Revisión:** en cada reunión de seguimiento se compara el esfuerzo real con las horas del cronograma. Si un bloque supera su subtotal, se registra como cambio.
- **Cierre de riesgos:** al cerrar un riesgo, la reserva que le correspondía queda liberada.
- **Horas extra:** las horas reales por encima de las horas de un paquete en el cronograma son horas extra, es decir, costo no presupuestado en la línea base. **No se cubren con la reserva sin aprobación:** el patrocinador debe aprobarlas antes, con el paquete, las horas y el motivo. Al corte del 14/11, los cuatro paquetes terminados llevan 22 h netas sobre lo planeado (69 h reales frente a 47 h; $330.000): 1.1.1 (+15 h), 8.1.1 (+8 h), 2.1.1 (+1 h) y 1.2.1 (−2 h). Están pendientes de aprobación.

