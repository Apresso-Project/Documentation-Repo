# MÉTRICAS DE PROYECTO — APPRESSO

> **Estado:** borrador v0.3 (17 de noviembre de 2026). Corte actual: **14/11/2026** (sábado de la semana 3). Cambios de la v0.3, por la sustentación de las métricas y el plan de acción del 16/11: calendario de lunes a domingo sin festivos y fin planificado el 15/12 (CC-02), costos directos (dominio y Claude Code) dentro del BAC y el AC, y valores de las secciones 3 a 8 recalculados.
> **Responsable del registro:** Felipe Salcedo (gerente del proyecto).
> **Fuentes:** [Cronograma](cronograma-Appresso.md), [Presupuesto](Presupuesto%20Appresso.md), [EDT Completa](EDT%20Completa.md), [Diccionario de la EDT](EDT%20y%20OBS/Diccionario-EDT-Appresso.md), [Plan de Calidad](Plan%20de%20Calidad%20Appresso.md) y [Seguimiento de Riesgos](Seguimiento%20de%20Riesgos%20Appresso.md).

Este archivo define **cómo se mide** el proyecto y registra las métricas de cada corte. La parte de seguimiento (lectura de los resultados y decisiones) se agrega después.

> **Datos provisionales.** Las cifras marcadas como *provisional* salen del historial del repositorio y de lo que el gerente conoce. Las horas reales (costo real) todavía no están registradas: ver sección 4.

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
| Paquetes de trabajo | 31 entregables en 8 bloques |
| Criterio de terminado | El criterio de aceptación de cada entregable en el diccionario, y las cinco condiciones de la definición de terminado del Plan de Calidad |

### 2.2 Línea base de tiempo

| Elemento | Contenido |
|----------|-----------|
| Documento | `cronograma-Appresso.md`: duración, dependencias y recorridos de cada paquete |
| Calendario | **Lunes a domingo, 4 h/día. Domingos y festivos son días de trabajo** (CC-02). Antes: lunes a sábado sin festivos (2/11, 16/11, 8/12, 25/12 y 1/1) |
| **Día 0** | **28/10/2026**, inicio real del desarrollo (cambio CC-01 aprobado, ver 2.4) |
| Fechas de cada paquete | Inicio y fin tempranos del recorrido hacia adelante (columnas ES y EF del cronograma), convertidos a fechas con el calendario anterior |
| Fin planificado del proyecto | **15/12/2026** (día 49) |

> Con el calendario de siete días (CC-02), los 49 días de la ruta crítica terminan el 15/12/2026, que es la nueva fecha de entrega del curso (antes 17/12). La secuencia, las duraciones y las dependencias no cambian. Antes de CC-02 el plan terminaba el 28/12 (calendario de lunes a sábado sin festivos).

### 2.3 Línea base de costo

Es la estimación del presupuesto repartida entre los 31 paquetes (**horas del cronograma × $15.000 por hora**) más los costos directos del proyecto (dominio y Claude Code).

| Concepto | Valor | ¿Entra en el EV? |
|----------|------:|:----------------:|
| 31 paquetes (371 h) | $5.565.000 | Sí |
| Dominio (USD 12 × $4.000) | $48.000 | Sí, al incurrirse |
| Claude Code (plan Pro, 1 licencia, 2 meses: USD 40 × $4.000) | $160.000 | Sí, al incurrirse |
| **BAC (línea base de costo)** | **$5.773.000** | |
| Respuestas a riesgos críticos | Pendiente de conciliación (referencia inicial: 96 h, $1.440.000) | No (línea aparte) |
| Reserva de contingencia | Pendiente de actualizar (referencia inicial: $2.054.500) | No (uso sujeto a aprobación) |
| Presupuesto total actualizado | Pendiente de validar (referencia inicial: $9.267.500) | — |

Los gastos de las respuestas a riesgos se siguen en su propia línea; no se mezclan con el EV de los paquetes.

**Costos directos.** No son horas: se pagan en pesos y se consideran **ganados cuando se incurren** (su EV es igual a su AC). Plan: Claude Code, $80.000 el 28/10 y $80.000 el 28/11; dominio, $48.000 antes del despliegue (al terminar 8.5.1, 11/12). *Por confirmar con el gerente:* se supone que el primer pago de Claude Code se hizo el 28/10 y que el dominio aún no se ha comprado.

La mano de obra se mide en horas ($15.000 por hora); como las métricas ahora incluyen costos directos, **PV, EV y AC se expresan en pesos**, y las horas se muestran junto a lo que corresponde a mano de obra.

### 2.4 Registro de cambios a las líneas base

| ID | Fecha | Línea base | Cambio | Motivo | Aprobación |
|----|-------|------------|--------|--------|------------|
| CC-01 | 12/11/2026 | Tiempo | El día 0 pasa del 29/09/2026 al **28/10/2026**. La secuencia, las duraciones y las dependencias no cambian | El cronograma usó como día 0 una fecha anterior al inicio real del desarrollo (R-01). Con el 29/09, el PV a la fecha incluiría trabajo que nunca pudo empezar | **Aprobado el 15/11/2026** por el gerente del proyecto. Las métricas usan el 28/10 |
| CC-02 | 17/11/2026 | Tiempo y costo | **Tiempo:** el calendario pasa de lunes a sábado sin festivos a **lunes a domingo sin festivos excluidos**; el fin planificado pasa del 28/12 al **15/12/2026** y se recalculan las fechas y el PV de todos los cortes desde el día 0. **Costo:** el **dominio** ($48.000) y **Claude Code** ($160.000) entran al BAC, que pasa de $5.565.000 a **$5.773.000**. La secuencia, las duraciones, las horas y las dependencias no cambian | Plan de acción de la reunión del 16/11 (domingos y festivos como días de trabajo, para recuperar el atraso) y correcciones de la sustentación de métricas (costos omitidos y nueva fecha de entrega del curso, 15/12) | **Calendario:** aprobado por el equipo el 16/11/2026. **Costos directos:** aprobado por el gerente el 17/11/2026. Las métricas usan ambos desde el día 0 |

No hay más cambios registrados. Un cambio posterior debe indicar el paquete afectado, el efecto en alcance, tiempo y costo, y quién lo aprobó.

---

## 3. Línea base paquete por paquete

Estado al corte del 14/11/2026. **Valor ganado con la regla 0/100:** un paquete terminado vale el 100 % de su costo, y uno no terminado vale 0 %, aunque esté a punto de completarse.

| Código | Entregable | Horas | BAC | Inicio plan | Fin plan | Estado | EV |
|--------|-----------|:-----:|----:|:-----------:|:--------:|--------|---:|
| 1.1.1 | Documentos de inicio y planificación estructural | 13 | $195.000 | 28/10 | 31/10 | Terminado (no estaba al corte del 31/10; sí al del 7/11) | $195.000 |
| 1.2.1 | Plan temporal, económico y de riesgos | 12 | $180.000 | 01/11 | 03/11 | Terminado (antes del corte del 7/11) | $180.000 |
| 1.3.1 | Seguimiento, control y cierre del proyecto | 14 | $210.000 | 12/12 | 15/12 | No iniciado | $0 |
| 2.1.1 | Módulo de autenticación | 10 | $150.000 | 31/10 | 02/11 | Terminado (12/11) | $150.000 |
| 2.2.1 | Módulo de administración de usuarios | 10 | $150.000 | 03/11 | 05/11 | No iniciado | $0 |
| 2.3.1 | Control de acceso por rol y acceso remoto | 16 | $240.000 | 03/11 | 06/11 | En curso (14 h reales) | $0 |
| 3.1.1 | Gestión de productos y categorías | 14 | $210.000 | 07/11 | 10/11 | No iniciado | $0 |
| 3.2.1 | Control de existencias | 14 | $210.000 | 11/11 | 14/11 | No iniciado | $0 |
| 3.3.1 | Consulta del menú y visualización en cocina | 14 | $210.000 | 11/11 | 14/11 | No iniciado | $0 |
| 4.1.1 | Creación de comandas | 18 | $270.000 | 15/11 | 19/11 | No iniciado | $0 |
| 4.2.1 | Envío, consulta y vinculación de clientes | 12 | $180.000 | 20/11 | 22/11 | No iniciado | $0 |
| 4.2.2 | Modificación y cancelación de pedidos | 12 | $180.000 | 20/11 | 22/11 | No iniciado | $0 |
| 5.1.1 | Visualización de pedidos en cocina | 12 | $180.000 | 20/11 | 22/11 | No iniciado | $0 |
| 5.2.1 | Gestión de estados y notificación al mesero | 8 | $120.000 | 23/11 | 24/11 | No iniciado | $0 |
| 6.1.1 | Registro de pagos | 10 | $150.000 | 20/11 | 22/11 | No iniciado | $0 |
| 6.2.1 | Transferencias QR | 14 | $210.000 | 23/11 | 26/11 | No iniciado | $0 |
| 6.3.1 | Ingresos y retiros directos | 8 | $120.000 | 23/11 | 24/11 | No iniciado | $0 |
| 6.3.2 | Solicitudes de retiro, aprobación y trazabilidad | 16 | $240.000 | 25/11 | 28/11 | No iniciado | $0 |
| 6.4.1 | Consultas financieras | 10 | $150.000 | 29/11 | 01/12 | No iniciado | $0 |
| 6.5.1 | Cierre de caja y cálculo de totales | 10 | $150.000 | 02/12 | 04/12 | No iniciado | $0 |
| 6.5.2 | Informe de cierre y apertura de jornada | 10 | $150.000 | 05/12 | 07/12 | No iniciado | $0 |
| 7.1.1 | Registro y búsqueda de clientes | 8 | $120.000 | 07/11 | 08/11 | No iniciado | $0 |
| 7.2.1 | Acumulación y configuración de puntos | 12 | $180.000 | 23/11 | 25/11 | No iniciado | $0 |
| 7.2.2 | Consulta de puntos | 8 | $120.000 | 26/11 | 27/11 | No iniciado | $0 |
| 7.3.1 | Recompensas y canjes | 14 | $210.000 | 28/11 | 01/12 | No iniciado | $0 |
| 7.4.1 | Promociones y notificaciones de fidelización | 16 | $240.000 | 28/11 | 01/12 | No iniciado | $0 |
| 8.1.1 | Configuración de arquitectura del proyecto | 12 | $180.000 | 28/10 | 30/10 | Terminado (10/11, *provisional*) | $180.000 |
| 8.2.1 | Sincronización en tiempo real | 8 | $120.000 | 31/10 | 01/11 | En curso (PR en revisión) | $0 |
| 8.3.1 | Pruebas | 16 | $240.000 | 05/12 | 08/12 | No iniciado | $0 |
| 8.4.1 | Seguridad y cumplimiento normativo | 10 | $150.000 | 09/11 | 11/11 | No iniciado | $0 |
| 8.5.1 | Despliegue y documentación técnica | 10 | $150.000 | 09/12 | 11/12 | No iniciado | $0 |
| | Costos directos incurridos (Claude Code, 1.er pago; el dominio aún no se compra; *por confirmar*) | | $80.000 | | | | $80.000 |
| | **Total (BAC)** | | **$5.773.000** | | | | **$785.000** |

Los 31 paquetes suman 371 h ($5.565.000) y su EV al corte es $705.000 (47 h).

Las fechas de inicio y fin son las tempranas del cronograma, con el calendario de lunes a domingo (CC-02). Un paquete sin holgura no puede moverse sin afectar la fecha final.

> Estados *provisional*: las fechas de cierre de 1.1.1 y 1.2.1 salen de lo informado por el equipo (1.1.1 no estaba terminado al corte del 31/10; al del 7/11 ya estaban terminados 1.1.1 y 1.2.1, pero no 8.1.1). 8.1.1 se tomó como terminado por la fusión de sus PR del 9 y 10/11. Hay que confirmar las fechas con el equipo.

---

## 4. Valor planificado, valor ganado y costo real

| Sigla | Nombre | Qué es | Cómo se calcula aquí |
|-------|--------|--------|----------------------|
| **PV** | Valor planificado | Cuánto trabajo debería estar hecho a esta fecha, según la línea base | Suma del BAC de los paquetes cuyo **fin planificado** es anterior o igual a la fecha de corte (regla 0/100), más los costos directos planificados hasta esa fecha |
| **EV** | Valor ganado | Cuánto trabajo está hecho de verdad, valorado con el plan | Suma del BAC de los paquetes **terminados** (regla 0/100), más los costos directos incurridos |
| **AC** | Costo real | Cuánto se ha gastado de verdad para llegar hasta aquí | Horas reales trabajadas × $15.000, de **todos** los paquetes con trabajo, estén o no terminados, más los costos directos pagados |

### 4.1 Corte del 14/11/2026 (día 18)

| Métrica | Mano de obra | Costos directos | Total | % del BAC |
|---------|:------------:|----------------:|------:|:---------:|
| PV | 141 h · $2.115.000 | $80.000 | **$2.195.000** | 38,0 % |
| EV | 47 h · $705.000 | $80.000 | **$785.000** | 13,6 % |
| AC | 95 h · $1.425.000 | $80.000 | **$1.505.000** | 26,1 % |

- **PV:** con el calendario de siete días, 12 paquetes debían estar terminados al 14/11: 8.1.1, 1.1.1, 8.2.1, 2.1.1, 1.2.1, 2.2.1, 2.3.1, 7.1.1, 3.1.1, 8.4.1, 3.2.1 y 3.3.1 (141 h). Con el calendario anterior eran 10 paquetes y 113 h.
- **EV:** 4 paquetes terminados: 1.1.1, 1.2.1, 8.1.1 y 2.1.1 (47 h). Se supone que desde el 12/11 no se cerró ningún otro paquete (por confirmar).
- **AC:** horas reales registradas por persona y semana en [Registro de Horas](Registro%20de%20Horas%20Appresso.md) (las de S1 y S2 son aproximadas), valoradas a $15.000 por hora, más $80.000 de Claude Code (supuesto por confirmar). Incluye los paquetes con trabajo, terminados o no.
- **Antes de CC-02** (lunes a sábado y solo mano de obra), al 14/11: PV 113 h ($1.695.000), EV 47 h ($705.000), AC 95 h ($1.425.000), SPI 0,42 y CPI 0,49.

| Paquete | Horas plan | Horas reales (estimadas) | AC | Estado |
|---------|:----------:|:------------------------:|---:|--------|
| 1.1.1 | 13 | 28 | $420.000 | Terminado |
| 1.2.1 | 12 | 10 | $150.000 | Terminado |
| 8.1.1 | 12 | 20 | $300.000 | Terminado |
| 2.1.1 | 10 | 11 | $165.000 | Terminado |
| 8.2.1 | 8 | 12 | $180.000 | En curso |
| 2.3.1 | 16 | 14 | $210.000 | En curso |
| **Mano de obra** | **71** | **95** | **$1.425.000** | |
| Claude Code (1.er pago) | | | $80.000 | |
| **Total** | | | **$1.505.000** | |

De las 95 h, 69 corresponden a los 4 paquetes terminados (47 h planificadas) y 26 a paquetes en curso, que por la regla 0/100 todavía no suman valor ganado. Las 22 h netas de los paquetes terminados por encima del plan son horas extra por aprobar (ver [Presupuesto](Presupuesto%20Appresso.md), sección 7).

### 4.2 Variaciones e índices

Las variaciones dicen **cuánto**, en términos absolutos. Los índices dicen **qué tan grave**, y permiten comparar entre semanas y entre proyectos. Por debajo de 1, el proyecto va peor de lo previsto.

| Métrica | Fórmula | Lectura | Corte 14/11 |
|---------|---------|---------|-------------|
| Variación de cronograma (SV) | EV − PV | Negativa: se hizo menos de lo previsto | $785.000 − $2.195.000 = **−$1.410.000** |
| Variación de costo (CV) | EV − AC | Negativa: se gastó más de lo que vale lo hecho | $785.000 − $1.505.000 = **−$720.000** |
| Índice de cronograma (SPI) | EV / PV | Menor que 1: se avanza a menos del ritmo planificado | 785 / 2.195 = **0,36** |
| Índice de costo (CPI) | EV / AC | Menor que 1: se gasta más de lo que vale lo hecho | 785 / 1.505 = **0,52** |

Un SPI de 0,36 dice que se avanza al 36 % del ritmo planificado. Un CPI de 0,52 dice que cada peso gastado ha producido 52 centavos de valor ganado.

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
| S3 (14/11) | $785.000 − $2.195.000 = **−$1.410.000** | Atrasado | $785.000 − $1.505.000 = **−$720.000** | Sobre presupuesto |

En los tres cortes ambas variaciones son negativas: el proyecto está atrasado y sobre presupuesto. El AC de S1 y S2 es aproximado, así que su CV también lo es.

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
| S3 (14/11) | 0,36 | 🔴 | 0,52 | 🔴 |

Los dos índices están en **rojo** en los tres cortes. Por la regla del semáforo, la acción es una intervención inmediata. El CPI de S1 y S2 es aproximado (usa el AC estimado).

### 4.3 Curva de trabajo acumulado

Eje Y: trabajo acumulado en % del BAC ($5.773.000). Eje X: semanas (lunes a domingo), con el corte al sábado. Las semanas se numeran desde la del 26/10 (el proyecto empezó el miércoles 28/10). Con el calendario de siete días el plan termina el 15/12, así que el PV llega al 100 % en el corte S8 (19/12).

| Semana | Corte | Día | PV | **PV %** | EV | **EV %** | AC |
|:------:|:-----:|:---:|---:|:--------:|---:|:--------:|----|
| S1 | 31/10 | 4 | $455.000 | 7,9 % | $80.000 | 1,4 % | ≈ $350.000 · 6,1 % |
| S2 | 07/11 | 11 | $1.295.000 | 22,4 % | $455.000 | 7,9 % | ≈ $680.000 · 11,8 % |
| S3 | 14/11 | 18 | $2.195.000 | 38,0 % | $785.000 | 13,6 % | $1.505.000 · 26,1 % |
| S4 | 21/11 | 25 | $2.465.000 | 42,7 % | | | |
| S5 | 28/11 | 32 | $4.225.000 | 73,2 % | | | |
| S6 | 05/12 | 39 | $4.975.000 | 86,2 % | | | |
| S7 | 12/12 | 46 | $5.563.000 | 96,4 % | | | |
| S8 | 19/12 | 53 | $5.773.000 | 100 % | | | |

**Gráfica:** [`metricas-grafico-Appresso.html`](metricas-grafico-Appresso.html) (se abre en el navegador) dibuja las tres curvas, PV, EV y AC, por semana, y una tabla con las variaciones y los índices de cada corte. Sus datos están en un arreglo al inicio del archivo, que se actualiza en cada corte. El AC se dibuja en los cortes que tienen horas reales registradas.

En cada corte se agregan el EV y el AC de la semana. El EV de S1 y S2 es *provisional*, según lo informado por el equipo: en S1 el paquete 1.1.1 aún no estaba terminado (0 h de EV en mano de obra); en S2 ya estaban terminados 1.1.1 y 1.2.1, pero no la arquitectura (8.1.1). El AC de S1 (unas 18 h) y el de S2 (unas 40 h) son aproximados, según lo informado por el equipo. Todos los cortes incluyen $80.000 de Claude Code (por confirmar); en S5 el PV suma el segundo pago (28/11) y en S7, el dominio.

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
| **BAC** | Presupuesto al terminar | El presupuesto de los 31 paquetes y de los costos directos (sección 2.3) | $5.773.000 |
| **EAC** | Estimado al terminar | Cuánto costará el proyecto completo | Ver abajo (dos escenarios) |
| **ETC** | Estimado para terminar | Cuánto falta por gastar | EAC − AC |
| **VAC** | Desviación al terminar | Cuánto se pasará (o ahorrará) frente al BAC | BAC − EAC |
| **TCPI** | Índice de desempeño para terminar | Qué rendimiento hay que tener de aquí en adelante para terminar dentro del BAC | (BAC − EV) / (BAC − AC) |

**Escenario A: el rendimiento actual se mantiene.** EAC = BAC / CPI.
**Escenario B: lo ocurrido fue una anomalía y lo que falta sale según el plan.** EAC = AC + (BAC − EV).

Corte del 14/11/2026 (BAC $5.773.000, EV $785.000, AC $1.505.000, CPI 0,52):

| Métrica | Escenario A | Escenario B |
|---------|:-----------:|:-----------:|
| **EAC** | ≈ $11.068.000 | $6.493.000 |
| **ETC** (EAC − AC) | ≈ $9.563.000 | $4.988.000 |
| **VAC** (BAC − EAC) | ≈ −$5.295.000 | −$720.000 |
| **TCPI** | 1,17 | 1,00 |

- **TCPI (1,17):** para terminar dentro del BAC habría que rendir un 17 % mejor que lo presupuestado de aquí en adelante, cuando hasta hoy se rinde al 52 %. Con ese rendimiento no es alcanzable. Un TCPI mayor que 1 indica que el BAC está en riesgo, y el escenario B lo trata como si el rendimiento volviera al plan (TCPI = 1,00).
- **El escenario A es muy pesimista:** el CPI sale de solo 4 paquetes terminados, y 1.1.1 costó 28 h contra 13 planificadas.
- **El escenario B es muy optimista:** nada indica que el rendimiento se corrija solo.
- **El resultado probable queda entre los dos.** Se reportan ambos para mostrar el rango.
- **Horas extra:** lo que exceda el BAC en mano de obra son horas extra que el patrocinador debe aprobar antes de cubrirlas con la reserva (ver [Presupuesto](Presupuesto%20Appresso.md), sección 7). La reserva de contingencia se registra por separado del BAC y está pendiente de actualización.
- **Datos aproximados:** el AC es una estimación del equipo, y cada pronóstico se recalcula en cada corte con el CPI y el AC acumulados.

---

## 5. Métricas de flujo

| Métrica | Qué dice |
|---------|----------|
| **Trabajo en curso (WIP)** | Cuántas cosas están empezadas y sin terminar |
| Ritmo de entrega | Cuántas cosas se terminan por semana |
| Tiempo de ciclo | Cuánto tarda una tarea desde que se empieza hasta que se termina |

Se relacionan por la **Ley de Little**: tiempo de ciclo = trabajo en curso ÷ ritmo de entrega.

**Se incluye en el tablero:** trabajo en curso, medido en paquetes (después, en subtareas de Jira). El ritmo y el tiempo de ciclo se calculan con las fechas de Jira cuando haya datos suficientes.

| Dato | Corte 14/11 |
|------|-------------|
| Paquetes en curso | **2** (2.3.1 y 8.2.1) |
| Paquetes terminados desde el 28/10 | 4 (1.1.1, 1.2.1, 8.1.1 y 2.1.1), en 15 días hábiles |

*Provisional.* Con tan pocos paquetes terminados, el ritmo y el tiempo de ciclo todavía no son confiables.

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

Frecuencia de despliegue, tiempo desde el cambio hasta producción, porcentaje de despliegues que fallan y tiempo de restauración. **No se incluyen en el tablero por ahora:** todavía no hay despliegue en Render, así que no medirían nada. Se revisan cuando exista el primer despliegue (8.5.1).

---

## 8. Tablero

Un grupo de cada tipo, para que optimizar una dimensión no destruya otra.

| Grupo | Métrica | Corte 14/11/2026 |
|-------|---------|------------------|
| Avance | SPI | **0,36** 🔴 (EV $785.000 / PV $2.195.000) |
| Costo o esfuerzo | CPI | **0,52** 🔴 (EV $785.000 / AC $1.505.000) |
| Flujo | Trabajo en curso | **2** paquetes |
| Calidad | Defectos encontrados por entrega (después, defectos que llegan al usuario) | 5 en 8.2.1 |

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

- A partir de S4, tomar el AC del registro de horas semana a semana. El AC de S1 (unas 18 h) y S2 (unas 40 h) sigue siendo aproximado.
- Confirmar con el gerente las fechas de pago de Claude Code (se supuso el 28/10) y del dominio (se supuso sin comprar al 14/11); si cambian, se recalculan EV y AC.
- Aprobar con el patrocinador las horas extra (22 h netas al 14/11).
- Plan de acción del 16/11: en la siguiente reunión se decide el recorte del proyecto según cómo evolucionen estas métricas; si hay recorte, se registra como CC-03.
- Parte de seguimiento: leer estas métricas y decidir qué hacer.
