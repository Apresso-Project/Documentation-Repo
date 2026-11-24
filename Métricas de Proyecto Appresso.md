# MÉTRICAS DE PROYECTO — APPRESSO

> **Estado:** borrador v0.5. Último corte medido: **21/11/2026** (S4). La actualización incorpora CC-03, aprobado en la reunión de control del 21/11, y conserva la ejecución acumulada registrada en S1 a S4.
> **Responsable del registro:** Felipe Salcedo (gerente del proyecto).
> **Fuentes:** [Cronograma](cronograma-Appresso.md), [Presupuesto](Presupuesto%20Appresso.md), [EDT Completa](EDT%20Completa.md), [Diccionario de la EDT](EDT%20y%20OBS/Diccionario-EDT-Appresso.md), [Plan de Calidad](Plan%20de%20Calidad%20Appresso.md) y [Seguimiento de Riesgos](Seguimiento%20de%20Riesgos%20Appresso.md).

Este archivo define **cómo se mide** el proyecto y registra las métricas de cada corte. La lectura del corte del 21/11 y las decisiones registradas se recogen en [Seguimiento de Riesgos](Seguimiento%20de%20Riesgos%20Appresso.md), sección 3.1.2.

> **Datos provisionales.** Las cifras marcadas como *provisional* salen del historial del repositorio y de lo que el gerente conoce. Las horas reales (costo real) salen del [Registro de Horas](Registro%20de%20Horas%20Appresso.md).

---

## 1. Regla de las líneas base

Una línea base es el plan aprobado contra el cual se compara lo que ocurre. **No se modifica porque el proyecto se atrase.** Solo cambia cuando un **cambio de alcance aprobado por el procedimiento de control de cambios** lo exige, y ese cambio queda registrado en la sección 2.4.

Si el proyecto se atrasa, la línea base queda igual y la diferencia aparece en las métricas. Ese es su propósito.

---

## 2. Líneas base

### 2.1 Línea base de alcance

| Elemento | Contenido |
|----------|-----------|
| Documentos | `EDT Completa.md` y `EDT y OBS/Diccionario-EDT-Appresso.md` |
| Paquetes de trabajo | 30 entregables vigentes en 8 bloques (CC-03) |
| Criterio de terminado | El criterio de aceptación de cada entregable en el diccionario, y las cinco condiciones de la definición de terminado del Plan de Calidad |

### 2.2 Línea base de tiempo

| Elemento | Contenido |
|----------|-----------|
| Documento | `cronograma-Appresso.md`: duración, dependencias y recorridos de cada paquete |
| Calendario | **Lunes a domingo, 4 h/día. Domingos y festivos son días de trabajo** (CC-02). Antes: lunes a sábado sin festivos (2/11, 16/11, 8/12, 25/12 y 1/1) |
| **Día 0** | **28/10/2026**, inicio real del desarrollo (cambio CC-01 aprobado, ver 2.4) |
| Fechas de cada paquete | Inicio y fin tempranos del recorrido hacia adelante (columnas ES y EF del cronograma), convertidos a fechas con el calendario de siete días |
| Fin planificado del proyecto | **12/12/2026** (día 46, CC-03) |
| Fecha límite de entrega del curso | **15/12/2026** |

> CC-02 situó el fin del plan en el 15/12/2026 con una ruta crítica de 49 días. CC-03 reduce la ruta crítica a 46 días y el fin del plan al 12/12/2026. La entrega del curso sigue prevista para el 15/12.

### 2.3 Línea base de costo

Es la estimación del presupuesto repartida entre los 30 paquetes vigentes (**horas del cronograma × $15.000 por hora**) más los costos directos del proyecto (dominio y Claude Code).

| Concepto | Valor | ¿Entra en el EV? |
|----------|------:|:----------------:|
| 30 paquetes (361 h) | $5.415.000 | Sí |
| Dominio (USD 12 × $4.000) | $48.000 | Sí, al incurrirse |
| Claude Code (plan Pro, 1 licencia, 2 meses: USD 40 × $4.000) | $160.000 | Sí, al incurrirse |
| **BAC vigente (línea base de costo)** | **$5.623.000** | |
| Respuestas a riesgos críticos | Pendiente de conciliación (referencia inicial: 96 h, $1.440.000) | No (línea aparte) |
| Reserva de contingencia | Pendiente de actualizar (referencia inicial: $2.054.500) | No (uso sujeto a aprobación) |
| Presupuesto total de referencia tras CC-03 | $9.117.500, con respuestas a riesgos y reserva pendientes de conciliación | — |

Los gastos de las respuestas a riesgos se siguen en su propia línea; no se mezclan con el EV de los paquetes.

**Costos directos.** Se registran en pesos y se consideran **ganados cuando se incurren** (su EV es igual a su AC). Claude Code tiene dos fechas confirmadas: $80.000 pagados el 28/10/2026 y $80.000 programados para el 28/11/2026. El dominio ($48.000) sigue previsto para el 11/12, con la compra y su fecha pendientes de confirmar.

La mano de obra se mide en horas ($15.000 por hora); como las métricas ahora incluyen costos directos, **PV, EV y AC se expresan en pesos**, y las horas se muestran junto a lo que corresponde a mano de obra.

### 2.4 Registro de cambios a las líneas base

| ID | Fecha | Línea base | Cambio | Motivo | Aprobación |
|----|-------|------------|--------|--------|------------|
| CC-01 | 12/11/2026 | Tiempo | El día 0 pasa del 29/09/2026 al **28/10/2026**. La secuencia, las duraciones y las dependencias no cambian | El cronograma usó como día 0 una fecha anterior al inicio real del desarrollo (R-01). Con el 29/09, el PV a la fecha incluiría trabajo que nunca pudo empezar | **Aprobado el 15/11/2026** por el gerente del proyecto. Las métricas usan el 28/10 |
| CC-02 | 17/11/2026 | Tiempo y costo | **Tiempo:** el calendario pasa de lunes a sábado sin festivos a **lunes a domingo sin festivos excluidos**; el fin planificado pasa del 28/12 al **15/12/2026** y se recalculan las fechas y el PV de todos los cortes desde el día 0. **Costo:** el **dominio** ($48.000) y **Claude Code** ($160.000) entran al BAC, que pasa de $5.565.000 a **$5.773.000**. La secuencia, las duraciones, las horas y las dependencias no cambian | Plan de acción de la reunión del 16/11 (domingos y festivos como días de trabajo, para recuperar el atraso) y correcciones de la sustentación de métricas (costos omitidos y nueva fecha de entrega del curso, 15/12) | **Calendario:** aprobado por el equipo el 16/11/2026. **Costos directos:** aprobado por el gerente el 17/11/2026. Las métricas usan ambos desde el día 0 |
| CC-03 | 21/11/2026 | Alcance, tiempo y costo | Se elimina el módulo de consultas financieras de la v1.0 (vistas de RF-38 y RF-39). Se conservan el historial de movimientos de 6.3.2 y los informes de cierre. Quedan 30 paquetes y 361 h, la ruta crítica baja de 49 a 46 días y el BAC de $5.773.000 a $5.623.000. Se aprueba iniciar despliegues internos continuos con Render y Neon. La v1.0 se despliega en producción al final | Recuperar plazo y validar las integraciones del sistema desde el desarrollo | **Aprobado por el equipo y el patrocinador** en la reunión de control del 21/11/2026. Ver [registro de la reunión](Seguimiento%20de%20Riesgos%20Appresso.md#5-registro-de-reuniones) |

Desde CC-03 se usa la línea base revisada para planificar lo pendiente. Los valores acumulados de PV, EV y AC de S1 a S4 en pesos coinciden con el registro anterior al cambio. Un cambio posterior debe indicar el paquete afectado, el efecto en alcance, tiempo y costo, y quién lo aprobó.

---

## 3. Línea base paquete por paquete

Estado al corte del 21/11/2026 y fechas del plan vigente tras CC-03. **Valor ganado con la regla 0/100:** un paquete terminado vale el 100 % de su costo, y uno no terminado vale 0 %, aunque esté a punto de completarse.

| Código | Entregable | Horas | BAC | Inicio plan | Fin plan | Estado | EV |
|--------|-----------|:-----:|----:|:-----------:|:--------:|--------|---:|
| 1.1.1 | Documentos de inicio y planificación estructural | 13 | $195.000 | 28/10 | 31/10 | Terminado (no estaba al corte del 31/10; sí al del 7/11) | $195.000 |
| 1.2.1 | Plan temporal, económico y de riesgos | 12 | $180.000 | 01/11 | 03/11 | Terminado (antes del corte del 7/11) | $180.000 |
| 1.3.1 | Seguimiento, control y cierre del proyecto | 14 | $210.000 | 09/12 | 12/12 | No iniciado | $0 |
| 2.1.1 | Módulo de autenticación | 10 | $150.000 | 31/10 | 02/11 | Terminado (12/11) | $150.000 |
| 2.2.1 | Módulo de administración de usuarios | 10 | $150.000 | 03/11 | 05/11 | Terminado (18/11) | $150.000 |
| 2.3.1 | Control de acceso por rol y acceso remoto | 16 | $240.000 | 03/11 | 06/11 | Terminado (17/11) | $240.000 |
| 3.1.1 | Gestión de productos y categorías | 14 | $210.000 | 07/11 | 10/11 | Terminado (20/11) | $210.000 |
| 3.2.1 | Control de existencias | 14 | $210.000 | 11/11 | 14/11 | No iniciado | $0 |
| 3.3.1 | Consulta del menú y visualización en cocina | 14 | $210.000 | 11/11 | 14/11 | No iniciado | $0 |
| 4.1.1 | Creación de comandas | 18 | $270.000 | 15/11 | 19/11 | No iniciado | $0 |
| 4.2.1 | Envío, consulta y vinculación de clientes | 12 | $180.000 | 20/11 | 22/11 | No iniciado | $0 |
| 4.2.2 | Modificación y cancelación de pedidos | 12 | $180.000 | 20/11 | 22/11 | No iniciado | $0 |
| 5.1.1 | Visualización de pedidos en cocina | 12 | $180.000 | 20/11 | 22/11 | No iniciado | $0 |
| 5.2.1 | Gestión de estados y notificación al mesero | 8 | $120.000 | 23/11 | 24/11 | No iniciado | $0 |
| 6.1.1 | Registro de pagos | 10 | $150.000 | 20/11 | 22/11 | En revisión (6 h reales) | $0 |
| 6.2.1 | Transferencias QR | 14 | $210.000 | 23/11 | 26/11 | No iniciado | $0 |
| 6.3.1 | Ingresos y retiros directos | 8 | $120.000 | 23/11 | 24/11 | No iniciado | $0 |
| 6.3.2 | Solicitudes de retiro, aprobación y trazabilidad | 16 | $240.000 | 25/11 | 28/11 | No iniciado | $0 |
| 6.5.1 | Cierre de caja y cálculo de totales | 10 | $150.000 | 29/11 | 01/12 | No iniciado | $0 |
| 6.5.2 | Informe de cierre y apertura de jornada | 10 | $150.000 | 02/12 | 04/12 | No iniciado | $0 |
| 7.1.1 | Registro y búsqueda de clientes | 8 | $120.000 | 07/11 | 08/11 | Terminado (20/11) | $120.000 |
| 7.2.1 | Acumulación y configuración de puntos | 12 | $180.000 | 23/11 | 25/11 | No iniciado | $0 |
| 7.2.2 | Consulta de puntos | 8 | $120.000 | 26/11 | 27/11 | No iniciado | $0 |
| 7.3.1 | Recompensas y canjes | 14 | $210.000 | 28/11 | 01/12 | No iniciado | $0 |
| 7.4.1 | Promociones y notificaciones de fidelización | 16 | $240.000 | 28/11 | 01/12 | No iniciado | $0 |
| 8.1.1 | Configuración de arquitectura del proyecto | 12 | $180.000 | 28/10 | 30/10 | Terminado (10/11, *provisional*) | $180.000 |
| 8.2.1 | Sincronización en tiempo real | 8 | $120.000 | 31/10 | 01/11 | Terminado (16/11) | $120.000 |
| 8.3.1 | Pruebas | 16 | $240.000 | 02/12 | 05/12 | No iniciado | $0 |
| 8.4.1 | Seguridad y cumplimiento normativo | 10 | $150.000 | 09/11 | 11/11 | En curso (7 h reales) | $0 |
| 8.5.1 | Despliegue y documentación técnica | 10 | $150.000 | 06/12 | 08/12 | No iniciado | $0 |
| | Costos directos incurridos (Claude Code, pago del 28/10 confirmado) | | $80.000 | | | | $80.000 |
| | **Total (BAC vigente)** | | **$5.623.000** | | | | **$1.625.000** |

Los 30 paquetes vigentes suman 361 h ($5.415.000) y su EV al corte es $1.545.000 (103 h).

Las fechas de inicio y fin son las tempranas del cronograma, con el calendario de lunes a domingo y el recorte de CC-03. Un paquete sin holgura no puede moverse sin afectar la fecha final.

> Estados *provisional*: las fechas de cierre de 1.1.1 y 1.2.1 salen de lo informado por el equipo (1.1.1 no estaba terminado al corte del 31/10; al del 7/11 ya estaban terminados 1.1.1 y 1.2.1, pero no 8.1.1). 8.1.1 se tomó como terminado por la fusión de sus PR del 9 y 10/11. Los de S4 usan la fecha en que su PR entró a `main` (2.2.1, la de su última pantalla). Hay que confirmar las fechas con el equipo.

---

## 4. Valor planificado, valor ganado y costo real

| Sigla | Nombre | Qué es | Cómo se calcula aquí |
|-------|--------|--------|----------------------|
| **PV** | Valor planificado | Cuánto trabajo debería estar hecho a esta fecha, según la línea base | Suma del BAC de los paquetes cuyo **fin planificado** es anterior o igual a la fecha de corte (regla 0/100), más los costos directos planificados hasta esa fecha |
| **EV** | Valor ganado | Cuánto trabajo está hecho de verdad, valorado con el plan | Suma del BAC de los paquetes **terminados** (regla 0/100), más los costos directos incurridos |
| **AC** | Costo real | Cuánto se ha gastado de verdad para llegar hasta aquí | Horas reales trabajadas × $15.000, de **todos** los paquetes con trabajo, estén o no terminados, más los costos directos pagados |

### 4.1 Corte del 21/11/2026 (día 25)

Los porcentajes de esta tabla usan el BAC de $5.773.000 con el que se registró el corte. La sección 4.3 muestra los porcentajes sobre el BAC vigente de CC-03.

| Métrica | Mano de obra | Costos directos | Total | % del BAC |
|---------|:------------:|----------------:|------:|:---------:|
| PV | 159 h · $2.385.000 | $80.000 | **$2.465.000** | 42,7 % |
| EV | 103 h · $1.545.000 | $80.000 | **$1.625.000** | 28,1 % |
| AC | 166 h · $2.490.000 | $80.000 | **$2.570.000** | 44,5 % |

- **PV:** 13 paquetes debían estar terminados al 21/11: 8.1.1, 1.1.1, 8.2.1, 2.1.1, 1.2.1, 2.2.1, 2.3.1, 7.1.1, 3.1.1, 8.4.1, 3.2.1, 3.3.1 y 4.1.1 (159 h).
- **EV:** 9 paquetes terminados (103 h): los 4 que ya lo estaban (1.1.1, 1.2.1, 8.1.1 y 2.1.1) y 5 de S4 (8.2.1, 2.3.1, 2.2.1, 3.1.1 y 7.1.1). 6.1.1 (en revisión) y 8.4.1 (en curso) valen 0 %. De los planificados faltan 8.4.1, 3.2.1, 3.3.1 y 4.1.1.
- **AC:** horas reales registradas por persona y semana en [Registro de Horas](Registro%20de%20Horas%20Appresso.md), valoradas a $15.000 por hora, más $80.000 de Claude Code pagados el 28/10. Incluye los paquetes con trabajo, terminados o no.
- **Antes de CC-02** (lunes a sábado y solo mano de obra), al 14/11: PV 113 h ($1.695.000), EV 47 h ($705.000), AC 95 h ($1.425.000), SPI 0,42 y CPI 0,49 (con las horas registradas entonces).

| Paquete | Horas plan | Horas reales | AC | Estado |
|---------|:----------:|:------------------------:|---:|--------|
| 1.1.1 | 13 | 28 | $420.000 | Terminado |
| 1.2.1 | 12 | 10 | $150.000 | Terminado |
| 8.1.1 | 12 | 20 | $300.000 | Terminado |
| 2.1.1 | 10 | 11 | $165.000 | Terminado |
| 8.2.1 | 8 | 27 | $405.000 | Terminado |
| 2.3.1 | 16 | 18 | $270.000 | Terminado |
| 2.2.1 | 10 | 10 | $150.000 | Terminado |
| 3.1.1 | 14 | 19 | $285.000 | Terminado |
| 7.1.1 | 8 | 10 | $150.000 | Terminado |
| 6.1.1 | 10 | 6 | $90.000 | En revisión |
| 8.4.1 | 10 | 7 | $105.000 | En curso |
| **Mano de obra** | **123** | **166** | **$2.490.000** | |
| Claude Code (1.er pago) | | | $80.000 | |
| **Total** | | | **$2.570.000** | |

De las 166 h, 153 corresponden a los 9 paquetes terminados (103 h planificadas) y 13 a los dos que aún no terminan, que por la regla 0/100 todavía no suman valor ganado. El 23/11 se registró la aprobación de 52 h extra trabajadas al corte. El ahorro de 2 h en 1.2.1 deja una desviación neta de 50 h ($750.000) en los paquetes terminados. El mayor excedente viene de 8.2.1 (+19 h), 1.1.1 (+15 h) y 8.1.1 (+8 h). Ver [Presupuesto](Presupuesto%20Appresso.md), sección 7.1.

### 4.2 Variaciones e índices

Las variaciones dicen **cuánto**, en términos absolutos. Los índices dicen **qué tan grave**, y permiten comparar entre semanas y entre proyectos. Por debajo de 1, el proyecto va peor de lo previsto.

| Métrica | Fórmula | Lectura | Corte 21/11 |
|---------|---------|---------|-------------|
| Variación de cronograma (SV) | EV − PV | Negativa: se hizo menos de lo previsto | $1.625.000 − $2.465.000 = **−$840.000** |
| Variación de costo (CV) | EV − AC | Negativa: se gastó más de lo que vale lo hecho | $1.625.000 − $2.570.000 = **−$945.000** |
| Índice de cronograma (SPI) | EV / PV | Menor que 1: se avanza a menos del ritmo planificado | 1.625 / 2.465 = **0,66** |
| Índice de costo (CPI) | EV / AC | Menor que 1: se gasta más de lo que vale lo hecho | 1.625 / 2.570 = **0,63** |

Un SPI de 0,66 dice que se avanza al 66 % del ritmo planificado. Un CPI de 0,63 dice que cada peso gastado ha producido 63 centavos de valor ganado.

**Reglas de interpretación**

| Variación | Si es mayor que 0 | Si es igual a 0 | Si es menor que 0 |
|-----------|-------------------|-----------------|-------------------|
| **SV** = EV − PV | Adelantado: se hizo más de lo planificado | En el plan exactamente | Atrasado: se hizo menos de lo planificado |
| **CV** = EV − AC | Bajo presupuesto: se produce más de lo que se gasta | Exactamente en el presupuesto | Sobre presupuesto: se gasta más de lo que se produce |

**Valores por corte** (acumulados, en pesos; las horas de mano de obra valen $15.000 cada una)

| Corte | SV (EV − PV) | Lectura | CV (EV − AC) | Lectura |
|:-----:|:------------:|---------|:------------:|---------|
| S1 (31/10) | $80.000 − $455.000 = **−$375.000** | Atrasado | $80.000 − $350.000 = **−$270.000** | Sobre presupuesto |
| S2 (07/11) | $455.000 − $1.295.000 = **−$840.000** | Atrasado | $455.000 − $680.000 = **−$225.000** | Sobre presupuesto |
| S3 (14/11) | $785.000 − $2.195.000 = **−$1.410.000** | Atrasado | $785.000 − $1.805.000 = **−$1.020.000** | Sobre presupuesto |
| S4 (21/11) | $1.625.000 − $2.465.000 = **−$840.000** | Atrasado | $1.625.000 − $2.570.000 = **−$945.000** | Sobre presupuesto |

En los cuatro cortes ambas variaciones son negativas: el proyecto está atrasado y sobre presupuesto. En S4 el atraso bajó por primera vez (de −$1.410.000 a −$840.000) y el sobrecosto se redujo frente a S3 (de −$1.020.000 a −$945.000). El AC de S3 (115 h) incluye 20 h anotadas después de su corte. Con las 95 h registradas en ese momento, su CV era −$720.000 y su CPI, 0,52.

**Semáforo RAG para SPI y CPI**

En proyectos reales se usan umbrales de color para alertar rápidamente. Los índices se redondean a dos decimales.

| Color | Rango (SPI o CPI) | Acción |
|-------|-------------------|--------|
| 🟢 Verde | ≥ 0,95 | Bien: monitorear |
| 🟡 Ámbar | Entre 0,85 y 0,94 | Atención: revisar causas y planear correcciones |
| 🔴 Rojo | < 0,85 | Alerta: intervención inmediata |

**Dónde vamos**

| Corte | SPI | Semáforo | CPI | Semáforo |
|:-----:|:---:|:--------:|:---:|:--------:|
| S1 (31/10) | 0,18 | 🔴 | 0,23 | 🔴 |
| S2 (07/11) | 0,35 | 🔴 | 0,67 | 🔴 |
| S3 (14/11) | 0,36 | 🔴 | 0,43 | 🔴 |
| S4 (21/11) | 0,66 | 🔴 | 0,63 | 🔴 |

Los dos índices están en **rojo** en los cuatro cortes, aunque en S4 ambos mejoraron frente a S3. Por la regla del semáforo, la acción es una intervención inmediata.

### 4.3 Curva de trabajo acumulado

Eje Y: trabajo acumulado en % del BAC vigente ($5.623.000). La serie conserva los importes en pesos de S1 a S4 y usa el mismo denominador para todos los cortes. Eje X: semanas de lunes a domingo con corte al sábado. El plan vigente llega al 100 % en S7 (12/12).

| Semana | Corte | Día | PV | **PV %** | EV | **EV %** | AC |
|:------:|:-----:|:---:|---:|:--------:|---:|:--------:|----|
| S1 | 31/10 | 4 | $455.000 | 8,1 % | $80.000 | 1,4 % | $350.000 · 6,2 % |
| S2 | 07/11 | 11 | $1.295.000 | 23,0 % | $455.000 | 8,1 % | $680.000 · 12,1 % |
| S3 | 14/11 | 18 | $2.195.000 | 39,0 % | $785.000 | 14,0 % | $1.805.000 · 32,1 % |
| S4 | 21/11 | 25 | $2.465.000 | 43,8 % | $1.625.000 | 28,9 % | $2.570.000 · 45,7 % |
| S5 | 28/11 | 32 | $4.225.000 | 75,1 % |  |  |  |
| S6 | 05/12 | 39 | $5.215.000 | 92,7 % |  |  |  |
| S7 | 12/12 | 46 | $5.623.000 | 100 % |  |  |  |
| S8 | 19/12 | 53 | $5.623.000 | 100 % |  |  |  |

**Gráfica:** [`metricas-grafico-Appresso.html`](metricas-grafico-Appresso.html) (se abre en el navegador) dibuja las tres curvas, PV, EV y AC, por semana, y una tabla con las variaciones y los índices de cada corte. Sus datos están en un arreglo al inicio del archivo, que se actualiza en cada corte. El AC se dibuja en los cortes que tienen horas reales registradas.

En cada corte se agregan el EV y el AC de la semana. El EV de S1 y S2 es *provisional*, según lo informado por el equipo: en S1 el paquete 1.1.1 aún no estaba terminado (0 h de EV en mano de obra); en S2 ya estaban terminados 1.1.1 y 1.2.1, pero no la arquitectura (8.1.1). Para el AC se registran 18 h acumuladas en S1 y 40 h en S2. Los cortes S1 a S4 incluyen los $80.000 de Claude Code pagados el 28/10. En S5 el PV suma el segundo pago programado para el 28/11 y en S7 suma el dominio.

### 4.4 Cómo se actualiza

1. Se fija la fecha de corte (al final de cada semana).
2. Se marcan como terminados los paquetes que cumplen sus cinco condiciones de terminado. Los demás valen 0 %.
3. Se suman las horas reales de la semana de todos los paquetes con trabajo **al acumulado anterior**, y los costos directos pagados en la semana (a su EV y a su AC).
4. Se calculan PV, EV, AC, las variaciones y los índices con los valores **acumulados desde el 28/10** (no los de la semana), y se agrega una fila a la tabla 4.3.

Las tres curvas son acumuladas: cada punto es el total desde el inicio del proyecto hasta el corte, y nunca baja.

### 4.5 Pronósticos

Con lo ocurrido hasta el corte se estima cómo terminará el proyecto en **costo**. Estos pronósticos no miden la fecha de fin.

| Sigla | Nombre | Qué dice | Fórmula |
|-------|--------|----------|---------|
| **BAC** | Presupuesto al terminar | El presupuesto de los 30 paquetes vigentes y de los costos directos (sección 2.3) | $5.623.000 |
| **EAC** | Estimado al terminar | Cuánto costará el proyecto completo | Ver abajo (dos escenarios) |
| **ETC** | Estimado para terminar | Cuánto falta por gastar | EAC − AC |
| **VAC** | Desviación al terminar | Cuánto se pasará (o ahorrará) frente al BAC | BAC − EAC |
| **TCPI** | Índice de desempeño para terminar | Qué rendimiento hay que tener de aquí en adelante para terminar dentro del BAC | (BAC − EV) / (BAC − AC) |

**Escenario A: el rendimiento actual se mantiene.** EAC = BAC / CPI.
**Escenario B: lo ocurrido fue una anomalía y lo que falta sale según el plan.** EAC = AC + (BAC − EV).

Pronóstico con la línea base de CC-03 y la ejecución al 21/11/2026 (BAC $5.623.000, EV $1.625.000, AC $2.570.000, CPI 0,63). Para las fórmulas se usa el índice sin redondear.

| Métrica | Escenario A | Escenario B |
|---------|:-----------:|:-----------:|
| **EAC** | ≈ $8.893.000 | $6.568.000 |
| **ETC** (EAC − AC) | ≈ $6.323.000 | $3.998.000 |
| **VAC** (BAC − EAC) | ≈ −$3.270.000 | −$945.000 |
| **TCPI** | 1,31 | 1,00 |

- **TCPI (1,31):** para terminar dentro del BAC habría que rendir un 31 % mejor que lo presupuestado de aquí en adelante, cuando hasta hoy se rinde al 63 %. Con ese rendimiento no es alcanzable. Un TCPI mayor que 1 indica que el BAC está en riesgo, y el escenario B lo trata como si el rendimiento volviera al plan (TCPI = 1,00).
- **El escenario A es pesimista:** el CPI sale de 9 paquetes terminados, y dos concentran la mayor parte del exceso: 8.2.1 costó 27 h contra 8 planificadas y 1.1.1, 28 h contra 13.
- **El escenario B es optimista:** el CPI mejoró en S4 (de 0,43 a 0,63), pero sigue lejos de 1.
- **El resultado probable queda entre los dos.** Se reportan ambos para mostrar el rango.
- **Horas extra:** la aprobación registrada para S4 ya está reflejada en el seguimiento del AC. La aplicación a la reserva se registra por separado del BAC. Ver [Presupuesto](Presupuesto%20Appresso.md), sección 7.
- Cada pronóstico se recalcula en cada corte con el CPI y el AC acumulados.

---

## 5. Métricas de flujo

| Métrica | Qué dice |
|---------|----------|
| **Trabajo en curso (WIP)** | Cuántas cosas están empezadas y sin terminar |
| Ritmo de entrega | Cuántas cosas se terminan por semana |
| Tiempo de ciclo | Cuánto tarda una tarea desde que se empieza hasta que se termina |

Se relacionan por la **Ley de Little**: tiempo de ciclo = trabajo en curso ÷ ritmo de entrega.

**Se incluye en el tablero:** trabajo en curso, medido en paquetes (después, en subtareas de Jira). El ritmo y el tiempo de ciclo se calculan con las fechas de Jira cuando haya datos suficientes.

| Dato | Corte 21/11 |
|------|-------------|
| Paquetes en curso | **2** (6.1.1, en revisión, y 8.4.1) |
| Paquetes terminados desde el 28/10 | 9 (1.1.1, 1.2.1, 8.1.1, 2.1.1, 8.2.1, 2.3.1, 2.2.1, 3.1.1 y 7.1.1), en 25 días |
| Paquetes terminados en la semana | 5 en S4 |

*Provisional.* Varios de los terminados en S4 venían de semanas anteriores, así que el ritmo y el tiempo de ciclo todavía no son confiables.

---

## 6. Métricas de calidad

| Métrica | Qué dice | Cuidado | ¿En el tablero? |
|---------|----------|---------|:---------------:|
| Defectos encontrados por entrega | Cuánta calidad está entrando | Si sube, puede ser que se prueba mejor, no que se programa peor | **Sí** |
| **Defectos que llegan al usuario** | Qué se le escapa a las pruebas | Es la que de verdad importa | **Sí, desde el piloto** |
| Cobertura de pruebas | Qué proporción del código ejecutan las pruebas | Se manipula con facilidad: hay pruebas que ejecutan mucho y verifican nada | No (el Plan de Calidad la vigila con la meta ≥ 70 %) |
| Tiempo de corrección | Cuánto tarda en arreglarse un defecto | Si crece, el código se está volviendo difícil de tocar | No |

La más honesta es la de **defectos que llegan al usuario**, porque mide el resultado y no el proceso. Hoy no hay usuarios, así que esa métrica empieza a tener datos en la prueba piloto con CaffeBar. Mientras tanto se registran los defectos encontrados por entrega.

### 6.1 Defectos encontrados por entrega

Se cuenta como defecto lo que una revisión de código, una prueba o el piloto encuentran y obliga a corregir algo ya entregado.

| Entrega | Fecha | Encontrados | Tipo | Cómo se encontraron |
|---------|-------|:-----------:|------|---------------------|
| 8.2.1 (PR de tiempo real) | 12/11/2026 | 5 | 1 de código (`estadoAnterior` mal llenado) y 4 de documentación (estado `BORRADOR` inexistente, comentarios de tipos de evento, texto de `PRODUCTO_ACTUALIZADO` y un TODO desactualizado) | Revisión entre pares |

*Provisional.* Es el primer registro; las entregas anteriores no tienen conteo.

### 6.2 Defectos que llegan al usuario

| Entrega | Defectos reportados en el piloto | Estado |
|---------|:--------------------------------:|--------|
| — | — | El piloto aún no empieza |

---

## 7. Métricas de entrega (DORA)

El 21/11 se aprobó iniciar despliegues internos continuos del backend en Render con base de datos en Neon. Al contar con ejecuciones registradas, se podrá medir la frecuencia, el tiempo entre el cambio y el despliegue interno, la proporción de fallos y el tiempo de restauración de ese entorno. Las métricas de producción se registrarán por separado desde la publicación de la v1.0.

---

## 8. Tablero

Un grupo de cada tipo, para que optimizar una dimensión no destruya otra.

| Grupo | Métrica | Corte 21/11/2026 |
|-------|---------|------------------|
| Avance | SPI | **0,66** 🔴 (EV $1.625.000 / PV $2.465.000) |
| Costo o esfuerzo | CPI | **0,63** 🔴 (EV $1.625.000 / AC $2.570.000) |
| Flujo | Trabajo en curso | **2** paquetes (6.1.1 y 8.4.1) |
| Calidad | Defectos encontrados por entrega (después, defectos que llegan al usuario) | 5 en 8.2.1; las entregas de S4 están por registrar |

---

## 9. Cadencia de revisión del tablero

El tablero (sección 8) se revisa **cada semana, en una reunión de seguimiento**. La reunión se hace con los cortes de la curva de trabajo acumulado (sección 4.3): el corte es el **sábado** de cada semana, y la reunión revisa los números de ese corte.

| Aspecto | Definición |
|---------|------------|
| Frecuencia | Semanal. La misma reunión de seguimiento en la que se revisan los riesgos (ver [Seguimiento de Riesgos](Seguimiento%20de%20Riesgos%20Appresso.md), sección 1) |
| Corte | Sábado de cada semana, con los datos hasta esa fecha. El primer corte fue el sábado 14/11/2026 |
| Quién prepara y registra | Felipe Salcedo (gerente del proyecto) |

**Antes de la reunión** (pasos de la sección 4.4): se marcan los paquetes terminados, se suman las horas reales de la semana al acumulado, y se calculan PV, EV, AC, variaciones, índices y pronósticos (EAC, ETC, VAC y TCPI) con los valores acumulados.

**En la reunión se revisan** las cuatro métricas del tablero:

| Grupo | Métrica | Qué se mira |
|-------|---------|-------------|
| Avance | SPI | Si está por debajo de 1 y cómo cambia frente a la semana anterior |
| Costo o esfuerzo | CPI | Si está por debajo de 1 y cómo cambia frente a la semana anterior |
| Flujo | Trabajo en curso | Cuántos paquetes hay empezados sin terminar |
| Calidad | Defectos encontrados por entrega (y, desde el piloto, defectos que llegan al usuario) | Cuántos se encontraron en las entregas de la semana |

**Qué se registra y dónde:**
1. Una fila nueva en la tabla de la sección 4.3 y en el arreglo de datos de `metricas-grafico-Appresso.html`.
2. Los valores del tablero de la sección 8.
3. Una fila en el registro de reuniones del [Seguimiento de Riesgos](Seguimiento%20de%20Riesgos%20Appresso.md) (sección 5), con las decisiones tomadas.

**Reglas de la revisión:**
- Se leen las cuatro métricas juntas: ninguna se interpreta sola.
- **La línea base no se cambia en la reunión** porque el proyecto vaya atrasado. Solo cambia por un cambio de alcance aprobado por el procedimiento de control de cambios, y se anota en la sección 2.4.
- Si un índice está por debajo de 1, la reunión decide qué hacer y lo registra. El semáforo RAG (sección 4.2) indica la urgencia: ámbar pide revisar causas y rojo, intervención inmediata. La lectura de los resultados y las decisiones se desarrollan en la parte de seguimiento.

---

## 10. Pendientes de este documento

- Anotar las horas antes de cada corte. En S3 se registraron 20 h después del corte.
- Confirmar la compra y la fecha de pago del dominio. Incorporar el gasto en EV y AC cuando se incurra.
- Registrar los defectos encontrados en las entregas de S4 (sección 6.1).
- Registrar la evidencia de los primeros despliegues internos y, cuando haya datos, medir su desempeño en la sección 7.
- Continuar el seguimiento semanal y registrar las decisiones en el [Seguimiento de Riesgos](Seguimiento%20de%20Riesgos%20Appresso.md).
