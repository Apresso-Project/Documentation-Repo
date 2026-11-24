# PRESUPUESTO — APPRESSO

> **Estado:** borrador v0.5. Incorpora el cambio CC-03 aprobado el 21/11/2026. Se actualiza la línea base de costo por el recorte. Las respuestas a riesgos, la reserva y el costo presupuestal total siguen en conciliación.
> **Responsable:** Felipe Salcedo (entregable 1.2.1 — Plan temporal, económico y de riesgos).
> **Moneda:** pesos colombianos (COP).
> **Fuentes:** [Cronograma](cronograma-Appresso.md) (horas por entregable), [Métricas del Proyecto](Métricas%20de%20Proyecto%20Appresso.md) y [Registro de Horas](Registro%20de%20Horas%20Appresso.md) (costo real), [Plan de Riesgos](Plan%20de%20Riesgos%20Appresso.md) (estimación inicial) y [Seguimiento de Riesgos](Seguimiento%20de%20Riesgos%20Appresso.md) (respuestas y exposición vigentes).

## 1. Supuestos

> Los importes de referencia se validan al aprobar el presupuesto. La tabla registra las decisiones y fechas ya confirmadas.

| Supuesto | Valor | Observación |
|----------|:-----:|-------------|
| Tarifa única por hora-persona | **$15.000** | Referencia para un desarrollador junior en Colombia. Es la misma para todo el equipo, incluido el gerente y el tester. |
| Horas por entregable | Las del cronograma | Se toma el esfuerzo (h) de cada entregable. Total vigente: **361 h** (CC-03). |
| Hosting: backend en Render y base de datos en Neon | **$0** | Planes gratuitos elegidos el 10/11/2026. El 21/11 se aprobó utilizarlos para los despliegues internos continuos. Si la configuración requiere gastos adicionales, se registran y se validan en R-12 o R-14. |
| Dominio | USD 12 al año | Dominio .com. Si se prefiere .co, el valor es mayor. |
| Claude Code | USD 20 al mes (plan Pro), 2 meses | Una sola licencia a cargo del gerente. Primer pago realizado el **28/10/2026** y segundo pago programado para el **28/11/2026**. Ambas fechas están confirmadas. |
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
| 6.5.1 | Módulo de cierre de caja y cálculo de totales | 10 | $150.000 |
| 6.5.2 | Módulo de informe de cierre y apertura de jornada | 10 | $150.000 |
| | **Subtotal** | **68** | **$1.020.000** |

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
| 1. Gestión del proyecto | 39 | $585.000 | 10,8 % |
| 2. Usuarios y permisos | 36 | $540.000 | 10,0 % |
| 3. Catálogo e inventario | 42 | $630.000 | 11,6 % |
| 4. Comandas y pedidos | 42 | $630.000 | 11,6 % |
| 5. Pantalla de cocina | 20 | $300.000 | 5,5 % |
| 6. Módulo de caja | 68 | $1.020.000 | 18,8 % |
| 7. Fidelización de clientes | 58 | $870.000 | 16,1 % |
| 8. Infraestructura y calidad | 56 | $840.000 | 15,5 % |
| **Total** | **361** | **$5.415.000** | **100 %** |

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
| Dominio | USD 12 × $4.000. Compra planificada para el 11/12, pendiente de confirmar | $48.000 |
| Certificado HTTPS | Incluido en el hosting | $0 |
| Claude Code (plan Pro, 1 licencia) | USD 20 × 2 meses × $4.000. Al corte del 21/11 se registra el pago de $80.000 del 28/10. El segundo está programado para el 28/11 | $160.000 |
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

## 6. Presupuesto de referencia tras CC-03

| Concepto | Costo | % del total |
|----------|------:|:-----------:|
| Entregables vigentes del cronograma (361 h) | $5.415.000 | 59,4 % |
| Respuestas a riesgos críticos (96 h, referencia inicial) | $1.440.000 | 15,8 % |
| Costos directos (dominio y Claude Code) | $208.000 | 2,3 % |
| **Estimación de costos** | **$7.063.000** | **77,5 %** |
| Reserva de contingencia (referencia inicial) | $2.054.500 | 22,5 % |
| **Presupuesto total de referencia** | **$9.117.500** | **100 %** |

- **Horas totales de referencia:** 361 h de entregables + 96 h de respuestas + 133,5 h de reserva = **590,5 h**.
- **Reserva de gestión:** no se incluye. Los imprevistos que no estén en el plan de riesgos requieren una decisión del patrocinador.
- **Sensibilidad a la tarifa del cálculo de referencia:** cada $1.000 de cambio en la tarifa por hora cambia el presupuesto en $590.500, porque las horas son 590,5 h (los costos directos no dependen de la tarifa).
- **Línea base de costo para las métricas (BAC):** 361 h de entregables ($5.415.000) + costos directos ($208.000) = **$5.623.000**. CC-03 reduce el BAC anterior de $5.773.000 en $150.000. Las respuestas a riesgos y la reserva siguen fuera del BAC.
- **Actualización pendiente de cuantificar:** costo de recuperación de R-01, R-02 y R-10, respuestas y exposición residual de los críticos abiertos (R-05, R-11, R-12 y R-13), y gastos directos asociados. El total actualizado queda pendiente de validar y aprobar. El presupuesto de referencia anterior fue $9.267.500. La reducción de $150.000 corresponde al recorte de 10 h, con los importes iniciales de riesgos y reserva sujetos a conciliación.

### 6.1 Seguimiento de costos al 21/11/2026

| Indicador | Mano de obra | Costos directos | Total |
|-----------|:------------:|----------------:|------:|
| Valor planificado (PV) | 159 h · $2.385.000 | $80.000 | **$2.465.000** |
| Valor ganado (EV) | 103 h · $1.545.000 | $80.000 | **$1.625.000** |
| Costo real (AC) | 166 h · $2.490.000 | $80.000 | **$2.570.000** |

- El costo real equivalía al **44,5 %** del BAC del corte. Sobre el BAC vigente tras CC-03 representa el **45,7 %**. La variación de costo (CV) es **−$945.000** y el CPI es **0,63**, frente a 0,43 al corte anterior.
- El pronóstico de costo final (EAC) con el BAC de CC-03 es **$6.568.000** si el trabajo restante sale según lo planificado, y **$8.893.000** si se mantiene el rendimiento acumulado. Son los escenarios de las métricas para el BAC, con la reserva y las respuestas a riesgos en líneas aparte.

---

## 7. Cómo se controla

- **Reserva de contingencia:** solo se gasta cuando un riesgo se materializa (estado *Materializado* en el [seguimiento de riesgos](Seguimiento%20de%20Riesgos%20Appresso.md)). Cada uso aprobado se anota con el riesgo, el paquete, las horas o el gasto directo y la fecha. Si el costo es compartido, se registra una sola vez con todos los riesgos relacionados.
- **Revisión:** en cada reunión de seguimiento se compara el esfuerzo real con las horas del cronograma. Si un bloque supera su subtotal, se registra como cambio.
- **Cierre de riesgos:** al cerrar un riesgo, la reserva que le correspondía queda liberada.
- **Horas extra:** las horas trabajadas por encima del plan de cada paquete se registran en el costo real. Para aplicarlas a la reserva se registra el uso aprobado con el riesgo, el paquete y las horas correspondientes.

### 7.1 Horas extra trabajadas al corte del 21/11/2026

Aprobación registrada el **23/11/2026**. El excedente de los paquetes terminados se detalla a continuación, con la tarifa de $15.000 por hora.

| Paquete | Horas plan | Horas reales | Diferencia | Costo de la diferencia |
|---------|-----------:|-------------:|-----------:|-----------------------:|
| 1.1.1 | 13 | 28 | +15 h | +$225.000 |
| 2.1.1 | 10 | 11 | +1 h | +$15.000 |
| 2.3.1 | 16 | 18 | +2 h | +$30.000 |
| 3.1.1 | 14 | 19 | +5 h | +$75.000 |
| 7.1.1 | 8 | 10 | +2 h | +$30.000 |
| 8.1.1 | 12 | 20 | +8 h | +$120.000 |
| 8.2.1 | 8 | 27 | +19 h | +$285.000 |
| **Horas extra aprobadas** | | | **+52 h** | **+$780.000** |
| 1.2.1 (ahorro) | 12 | 10 | −2 h | −$30.000 |
| 2.2.1 | 10 | 10 | 0 h | $0 |
| **Desviación neta de paquetes terminados** | **103** | **153** | **+50 h** | **+$750.000** |

Los $750.000 netos ya están dentro del AC. Los $195.000 restantes de la desviación de costo corresponden a 13 h en 6.1.1 y 8.4.1, que todavía no generan EV. La aprobación queda registrada en el seguimiento del costo real del 21/11. Para comparar con el presupuesto restante se usa el BAC vigente de $5.623.000.

