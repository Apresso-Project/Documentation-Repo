# SEGUIMIENTO DE RIESGOS — APPRESSO

> **Última actualización:** 3 de noviembre de 2026
> **Responsable del registro:** Felipe Salcedo (gerente del proyecto)
> **Fuente:** [Plan de Riesgos Appresso](Plan%20de%20Riesgos%20Appresso.md). Allí están los enunciados completos, la escala y el cálculo del costo esperado.

Este archivo se actualiza en cada reunión de seguimiento. Los enunciados, las probabilidades y los impactos cambian aquí; el plan se queda como referencia del punto de partida.

---

## 1. Preguntas de cada reunión

Estas cuatro preguntas se responden **en orden** en cada reunión de seguimiento. Lo que se decida se anota en la sección 5.

1. **¿Se disparó alguno?** Revisar los disparadores de la sección 3. Si alguno se cumplió, el riesgo pasó a problema (estado *Materializado*) y se activa la respuesta.
2. **¿Cambió alguna probabilidad o impacto?** A medida que el proyecto avanza, unos riesgos crecen y otros desaparecen solos. Actualizar la sección 2 y recalcular la severidad.
3. **¿Apareció alguno nuevo?** Cada cambio de alcance y cada decisión técnica trae riesgos que antes no existían. Redactarlo con la plantilla (Debido a / podría ocurrir que / lo que provocaría) y agregarlo.
4. **¿Se puede cerrar alguno?** Cuando el paquete al que afectaba ya se entregó, el riesgo se cierra. Cerrar riesgos es tan importante como abrirlos: mantiene la lista corta y creíble.

---

## 2. Registro de riesgos

**Severidad = Probabilidad × Impacto** (escala de 1 a 5 para cada una; ver sección 4 del plan).
**Clasificación:** 🟢 1–4 · 🟡 5–9 · 🟠 10–14 · 🔴 15–25.

| ID | Enunciado | Categoría | P | I | Severidad | Estado |
|:--:|-----------|-----------|:-:|:-:|:---------:|:------:|
| R-01 | **Debido a** que la ruta crítica dura 49 días hábiles sin holgura y el desarrollo inició el 28/10 y no el 29/09 que usa el cronograma, **podría ocurrir que** la fecha de fin supere el 17/12/2026, **lo que provocaría** que la v1.0 no esté desplegada ni validada en el piloto a tiempo. | Cronograma | 4 | 5 | 🔴 20 | Abierto |
| R-02 | **Debido a** que el cronograma asume 4 h/día y el equipo tiene otras materias, **podría ocurrir que** la dedicación real baje en semanas de parciales y entregas, **lo que provocaría** retrasos en entregables críticos y recorte forzado de alcance. | Recursos | 4 | 4 | 🔴 16 | Abierto |
| R-10 | **Debido a** que el equipo de backend no tiene experiencia en Spring Boot y 8.1.1 abre la ruta crítica, **podría ocurrir que** la curva de aprendizaje alargue arquitectura, autenticación y roles, **lo que provocaría** el retraso de toda la ruta crítica. | Tecnológico | 4 | 4 | 🔴 16 | Abierto |
| R-11 | **Debido a** que la sincronización con cocina usa STOMP/SockJS, 8.2.1 tiene 2 días y un solo responsable, y se exige ≤ 3 s, **podría ocurrir que** la conexión se caiga, no se reconecte o supere los 3 s, **lo que provocaría** que las comandas lleguen tarde o no lleguen a cocina. | Tecnológico | 4 | 4 | 🔴 16 | Abierto |
| R-12 | **Debido a** que se exige producción con HTTPS antes del 17/12, el despliegue dura 3 días al final de la ruta crítica y no hay hosting elegido ni experiencia, **podría ocurrir que** falle la configuración del servidor, la base de datos o el certificado, **lo que provocaría** que la app no esté en producción para el piloto o que haya un gasto no presupuestado. | Tecnológico | 3 | 5 | 🔴 15 | Abierto |
| R-03 | **Debido a** que Diego Gómez tiene 14 entregables como R y 9 como A, incluyendo 3 de la ruta crítica, **podría ocurrir que** se enferme o no esté disponible unos días, **lo que provocaría** el bloqueo de arquitectura, pruebas y despliegue. | Recursos | 3 | 4 | 🟠 12 | Abierto |
| R-04 | **Debido a** que 5 entregables críticos de caja están encadenados 15 días sin margen y con reglas financieras exigentes, **podría ocurrir que** un error en saldos, retiros o cierre se detecte tarde, **lo que provocaría** el retraso de las pruebas, el despliegue y el cierre. | Calidad | 3 | 4 | 🟠 12 | Abierto |
| R-05 | **Debido a** que hay un solo tester y las pruebas (N°29) solo empiezan cuando terminan comandas, pagos, puntos y cierre de caja, **podría ocurrir que** los defectos se descubran todos al final, **lo que provocaría** una entrega sin el 70 % de cobertura o con errores en caja y comandas. | Calidad | 3 | 4 | 🟠 12 | Abierto |
| R-07 | **Debido a** que se recolectan nombre, cédula y celular de clientes y no hay política de tratamiento de datos ni responsable designado, **podría ocurrir que** el piloto arranque sin política aprobada o con el texto de aceptación incompleto, **lo que provocaría** incumplimiento de la Ley 1581 de 2012 y posible sanción para CaffeBar. | Normativo | 3 | 4 | 🟠 12 | Abierto |
| R-09 | **Debido a** que el acta compromete 31 entregables y hay más de 50 requisitos funcionales, **podría ocurrir que** el equipo no alcance a implementar todo con calidad, **lo que provocaría** módulos incompletos o recortes sin acordar con el cliente. | Alcance | 4 | 3 | 🟠 12 | Abierto |
| R-08 | **Debido a** que no hay fecha límite acordada para que Pepito Pérez entregue productos, precios, promociones y reglas de fidelización, **podría ocurrir que** los datos lleguen tarde o incompletos, **lo que provocaría** que no se pueda cargar el menú real ni configurar la fidelización antes del piloto. | Externo (cliente) | 3 | 3 | 🟡 9 | En vigilancia |
| R-06 | **Debido a** que el sistema depende del Wi-Fi y se exige ≤ 3 s a cocina, pero no se ha medido la red de CaffeBar, **podría ocurrir que** la red sea inestable o lenta en el servicio, **lo que provocaría** que las comandas no lleguen a tiempo y el piloto no cumpla los criterios. | Externo (entorno) | 2 | 4 | 🟡 8 | En vigilancia |

---

## 3. Respuesta a cada riesgo

Los riesgos críticos (R-01, R-02, R-10, R-11, R-12) vienen del análisis de costo esperado del plan (sección 5). Los marcados con ✏️ son **propuestas** del gerente, sin análisis de costo esperado y por validar con el equipo.

| ID | Estrategia (decisión) | Acción concreta | Responsable | Disparador |
|:--:|-----------------------|-----------------|-------------|------------|
| R-01 | Mitigar + Escalar | Recalcular el cronograma con el inicio real (28/10) y los festivos; paralelizar lo que tiene holgura; si la fecha de fin supera el 17/12, escalar al docente y al patrocinador para acordar fecha o recorte de alcance (p. ej. 7.4.1) y registrar que se escaló. | Felipe | Fecha de fin recalculada > 17/12, o cualquier retraso en un entregable de la ruta crítica |
| R-02 | Mitigar | Pedir a cada integrante su calendario de parciales y entregas; adelantar trabajo antes de esas semanas; reasignar en la reunión de seguimiento. | Felipe | Un integrante avisa que no cumplirá las 4 h/día, o un entregable crítico cierra con más de 1 día de retraso |
| R-10 | Mitigar | Tutorial dirigido de Spring Boot para Gómez y Bolaños (8 h cada uno) antes de los entregables que dependen del backend; revisión de código entre ambos. | Diego Gómez | 8.1.1 o 2.1.1 con más de 1 día de retraso |
| R-11 | Mitigar | Prototipo corto de STOMP/SockJS con reconexión automática (8 h) y prueba de latencia con varios dispositivos (8 h) antes de dar 8.2.1 por terminado. | Diego Gómez | Prueba de latencia > 3 s, o desconexiones sin reconexión |
| R-12 | Transferir + Mitigar | Elegir un hosting gestionado que entregue HTTPS y base de datos configurados (transfiere esa parte al proveedor) y hacer un despliegue de prueba temprano, antes de 8.5.1. | Felipe y Diego Gómez | Hosting sin elegir al 15/11, o despliegue de prueba fallido |
| R-03 ✏️ | Mitigar | Que Diego Bolaños sea respaldo de Gómez en 8.1.1 y 8.5.1: documentar la arquitectura y los pasos de despliegue, y hacer revisión de código entre ambos. | Felipe | Gómez ausente más de 2 días, o un entregable suyo con más de 1 día de retraso |
| R-04 ✏️ | Mitigar | Escribir las pruebas unitarias de saldos separados y de la ecuación de cierre al terminar cada entregable del Bloque 6, sin esperar a 8.3.1; el tester revisa cada uno. | Diego Bolaños | Un entregable del Bloque 6 con más de 1 día de retraso, o una prueba de saldos que falle |
| R-05 ✏️ | Mitigar | El tester prueba cada módulo cuando se entrega y prepara los casos de prueba en paralelo, no solo en 8.3.1. | David Ascencio | Cobertura < 70 % al terminar los módulos de comandas y pagos, o defectos de prioridad Alta abiertos al llegar a 8.3.1 |
| R-07 ✏️ | Mitigar + Escalar | Redactar la política de tratamiento y el texto de aceptación; escalar a Pepito Pérez, como responsable del tratamiento, para que los apruebe, y registrar que se escaló. | Felipe | Sin política aprobada a una semana del piloto |
| R-09 ✏️ | Mitigar | Ordenar los entregables por prioridad, acordar con el cliente cuáles se pueden recortar (p. ej. 7.4.1 promociones) y registrar todo cambio de alcance. | Felipe | Una solicitud de cambio de alcance, o un avance semanal por debajo de lo planeado |
| R-08 ✏️ | Mitigar | Acordar con Pepito Pérez una fecha límite para entregar el menú, los precios y las reglas de fidelización (propuesta: 15/11). | Felipe | Datos incompletos en la fecha límite |
| R-06 ✏️ | Mitigar | Medir velocidad y estabilidad del Wi-Fi de CaffeBar con dispositivos reales; mantener la alerta de desconexión y la reconexión automática. | Felipe | Latencia > 3 s o caídas durante la medición |

---

## 4. Estados

| Estado | Significado |
|--------|-------------|
| **Abierto** | Identificado, con una respuesta por ejecutar o en ejecución. |
| **En vigilancia** | Sin acción pendiente; solo se revisa el disparador en cada reunión. |
| **Materializado** | Se cumplió el disparador o el evento ocurrió. Ya es un problema y se activa la respuesta. |
| **Cerrado** | Ya no puede ocurrir (el paquete al que afectaba se entregó) o se descartó. Se anota la fecha y el motivo. |

---

## 5. Registro de reuniones

Una fila por reunión. Los detalles de cada cambio van en la sección 6.

| Fecha | Asistentes | 1. ¿Se disparó alguno? | 2. ¿Cambió alguna P o I? | 3. ¿Apareció alguno nuevo? | 4. ¿Se puede cerrar alguno? |
|-------|------------|------------------------|--------------------------|----------------------------|-----------------------------|
| | | | | | |

---

## 6. Historial de cambios

| Fecha | ID | Cambio (estado, P, I, estrategia, etc.) | Valor anterior → nuevo | Motivo |
|-------|:--:|------------------------------------------|------------------------|--------|
| 3/11/2026 | Todos | Registro inicial | — | Primer registro a partir del Plan de Riesgos v0.3 |
