# SEGUIMIENTO DE RIESGOS — APPRESSO

> **Última actualización:** 12 de noviembre de 2026
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
| R-01 | **Debido a** que la ruta crítica dura 49 días hábiles sin holgura y el desarrollo inició el 28/10 y no el 29/09 que usa el cronograma, **podría ocurrir que** la fecha de fin supere el 17/12/2026, **lo que provocaría** que la v1.0 no esté desplegada ni validada en el piloto a tiempo. | Cronograma | 5 | 5 | 🔴 25 | **Materializado** (12/11/2026) |
| R-02 | **Debido a** que el cronograma asume 4 h/día y el equipo tiene otras materias, **podría ocurrir que** la dedicación real baje en semanas de parciales y entregas, **lo que provocaría** retrasos en entregables críticos y recorte forzado de alcance. | Recursos | 5 | 4 | 🔴 20 | **Materializado** (12/11/2026) |
| R-10 | **Debido a** que el equipo de backend no tiene experiencia en Spring Boot y 8.1.1 abre la ruta crítica, **podría ocurrir que** la curva de aprendizaje alargue arquitectura, autenticación y roles, **lo que provocaría** el retraso de toda la ruta crítica. | Tecnológico | 5 | 4 | 🔴 20 | **Materializado** (12/11/2026) |
| R-13 | **Debido a** que, al 12/11, todo lo entregado (8.1.1 y 2.1.1) lo hicieron el gerente y Diego Gómez, y los demás integrantes no han entregado ninguna tarea (ver 3.2), **podría ocurrir que** alguno de los dos se enferme, se sobrecargue o deje de estar disponible, **lo que provocaría** que el desarrollo se detenga casi por completo y que el gerente no pueda dedicarse a la gestión del proyecto. | Recursos | 4 | 5 | 🔴 20 | Abierto |
| R-11 | **Debido a** que la sincronización con cocina usa STOMP/SockJS, 8.2.1 tiene 2 días y un solo responsable, y se exige ≤ 3 s, **podría ocurrir que** la conexión se caiga, no se reconecte o supere los 3 s, **lo que provocaría** que las comandas lleguen tarde o no lleguen a cocina. | Tecnológico | 4 | 4 | 🔴 16 | Abierto |
| R-12 | **Debido a** que se exige producción con HTTPS antes del 17/12, el despliegue dura 3 días al final de la ruta crítica y, aunque el 10/11 se eligió Neon (base de datos) y Render (backend), con planes gratuitos, aún no hay `Dockerfile` ni despliegue de prueba y el equipo no tiene experiencia desplegando, **podría ocurrir que** falle la configuración del servidor, la base de datos o el certificado, **lo que provocaría** que la app no esté en producción para el piloto o que haya un gasto no presupuestado. | Tecnológico | 3 | 5 | 🔴 15 | Abierto |
| R-03 | **Debido a** que Diego Gómez tiene 14 entregables como R y 9 como A, incluyendo 3 de la ruta crítica, **podría ocurrir que** se enferme o no esté disponible unos días, **lo que provocaría** el bloqueo de arquitectura, pruebas y despliegue. | Recursos | 3 | 4 | 🟠 12 | Abierto |
| R-04 | **Debido a** que 5 entregables críticos de caja están encadenados 15 días sin margen y con reglas financieras exigentes, **podría ocurrir que** un error en saldos, retiros o cierre se detecte tarde, **lo que provocaría** el retraso de las pruebas, el despliegue y el cierre. | Calidad | 3 | 4 | 🟠 12 | Abierto |
| R-05 | **Debido a** que hay un solo tester y las pruebas (N°29) solo empiezan cuando terminan comandas, pagos, puntos y cierre de caja, **podría ocurrir que** los defectos se descubran todos al final, **lo que provocaría** una entrega sin el 70 % de cobertura o con errores en caja y comandas. | Calidad | 4 | 4 | 🔴 16 | Abierto |
| R-07 | **Debido a** que se recolectan nombre, cédula y celular de clientes y no hay política de tratamiento de datos ni responsable designado, **podría ocurrir que** el piloto arranque sin política aprobada o con el texto de aceptación incompleto, **lo que provocaría** incumplimiento de la Ley 1581 de 2012 y posible sanción para CaffeBar. | Normativo | 3 | 4 | 🟠 12 | Abierto |
| R-09 | **Debido a** que el acta compromete 31 entregables y hay más de 50 requisitos funcionales, **podría ocurrir que** el equipo no alcance a implementar todo con calidad, **lo que provocaría** módulos incompletos o recortes sin acordar con el cliente. | Alcance | 4 | 3 | 🟠 12 | Abierto |
| R-14 | **Debido a** que el backend y la base de datos se alojarán en planes gratuitos de Render y Neon, que (por confirmar en su documentación) se suspenden tras un periodo sin tráfico, **podría ocurrir que** la primera petición tras la inactividad tarde mucho o que la conexión en tiempo real se corte, **lo que provocaría** que las comandas lleguen tarde a cocina (≤ 3 s) o que el piloto arranque con fallos. | Tecnológico | 3 | 4 | 🟠 12 | Abierto |
| R-15 | **Debido a** que los requisitos no definen cómo inicia sesión un cliente ni cómo se usa la cuenta compartida de cocina, y que RNF-26.2 (cerrar sesión a los 30 min de inactividad) contradice a RNF-25.2 (la pantalla de cocina no cierra sesión), **podría ocurrir que** se implemente algo que luego haya que rehacer o que se incumpla uno de los dos requisitos, **lo que provocaría** retrabajo en 2.3.1 y en el Bloque 7 y un cambio de requisitos sin acordar. | Alcance | 4 | 3 | 🟠 12 | Abierto |
| R-16 | **Debido a** que el acta y la EDT exigen notificaciones push (retiros al administrador en ≤ 5 s con la app cerrada, 6.3.2, y promociones, 7.4.1) y todavía no hay proyecto de Firebase ni responsable asignado, **podría ocurrir que** la integración de notificaciones se descubra tarde o no funcione con la app cerrada, **lo que provocaría** retraso en 6.3.2, que está en la ruta crítica, e incumplimiento de un criterio de aceptación del acta. | Tecnológico | 3 | 4 | 🟠 12 | Abierto |
| R-08 | **Debido a** que no hay fecha límite acordada para que Pepito Pérez entregue productos, precios, promociones y reglas de fidelización, **podría ocurrir que** los datos lleguen tarde o incompletos, **lo que provocaría** que no se pueda cargar el menú real ni configurar la fidelización antes del piloto. | Externo (cliente) | 3 | 3 | 🟡 9 | En vigilancia |
| R-06 | **Debido a** que el sistema depende del Wi-Fi y se exige ≤ 3 s a cocina, pero no se ha medido la red de CaffeBar, **podría ocurrir que** la red sea inestable o lenta en el servicio, **lo que provocaría** que las comandas no lleguen a tiempo y el piloto no cumpla los criterios. | Externo (entorno) | 2 | 4 | 🟡 8 | En vigilancia |

---

## 3. Respuesta a cada riesgo

Los riesgos críticos (R-01, R-02, R-10, R-11, R-12) vienen del análisis de costo esperado del plan (sección 5). Los marcados con ✏️ son **propuestas** del gerente, sin análisis de costo esperado y por validar con el equipo.

| ID | Estrategia (decisión) | Acción concreta | Responsable | Disparador |
|:--:|-----------------------|-----------------|-------------|------------|
| R-01 | **Por definir** | Pendiente de decisión del equipo. La respuesta inicial del plan (mitigar y escalar, sección 5.4 del Plan de Riesgos) ya no basta: el disparador se cumplió (ver sección 3.1). | Felipe | **Cumplido el 12/11/2026:** fecha de fin recalculada (6/1/2027) > 17/12 |
| R-02 | **Por definir** | Pendiente de decisión del equipo (se trata junto con R-01). La respuesta inicial del plan (calendario de parciales y reasignación) no cubre lo ocurrido: ver sección 3.2. | Felipe | **Cumplido:** integrantes informaron que no cumplen las 4 h/día |
| R-10 | Mitigar (sin ejecutar) | Tutorial dirigido de Spring Boot para Gómez y Bolaños (8 h cada uno) antes de los entregables que dependen del backend; revisión de código entre ambos. Hoy el backend de 2.1.1 lo hizo el gerente, así que el conocimiento no pasó al equipo de backend. | Diego Gómez | **Cumplido:** 8.1.1 con más de 1 día de retraso (unos 7 días hábiles frente a 3) |
| R-11 | Mitigar | Prototipo corto de STOMP/SockJS con reconexión automática (8 h) y prueba de latencia con varios dispositivos (8 h) antes de dar 8.2.1 por terminado. | Diego Gómez | Prueba de latencia > 3 s, o desconexiones sin reconexión |
| R-12 | Transferir + Mitigar | Elegir un hosting gestionado que entregue HTTPS y base de datos configurados (transfiere esa parte al proveedor) y hacer un despliegue de prueba temprano, antes de 8.5.1. | Felipe y Diego Gómez | Despliegue de prueba sin hacer o fallido antes de 8.5.1. (El hosting ya se eligió el 10/11: Neon + Render, gratuitos; el presupuesto aún considera USD 15/mes y hay que actualizarlo) |
| R-13 ✏️ | **Por definir** | Pendiente de decisión del equipo (se trata junto con R-01 y R-02). | Felipe | Gómez o el gerente ausentes más de 2 días |
| R-03 ✏️ | Mitigar | Que Diego Bolaños sea respaldo de Gómez en 8.1.1 y 8.5.1: documentar la arquitectura y los pasos de despliegue, y hacer revisión de código entre ambos. | Felipe | Gómez ausente más de 2 días, o un entregable suyo con más de 1 día de retraso |
| R-04 ✏️ | Mitigar | Escribir las pruebas unitarias de saldos separados y de la ecuación de cierre al terminar cada entregable del Bloque 6, sin esperar a 8.3.1; el tester revisa cada uno. | Diego Bolaños | Un entregable del Bloque 6 con más de 1 día de retraso, o una prueba de saldos que falle |
| R-05 ✏️ | Mitigar | El tester prueba cada módulo cuando se entrega y prepara los casos de prueba en paralelo, no solo en 8.3.1. | David Ascencio | Cobertura < 70 % al terminar los módulos de comandas y pagos, o defectos de prioridad Alta abiertos al llegar a 8.3.1 |
| R-07 ✏️ | Mitigar + Escalar | Redactar la política de tratamiento y el texto de aceptación; escalar a Pepito Pérez, como responsable del tratamiento, para que los apruebe, y registrar que se escaló. | Felipe | Sin política aprobada a una semana del piloto |
| R-09 ✏️ | Mitigar | Ordenar los entregables por prioridad, acordar con el cliente cuáles se pueden recortar (p. ej. 7.4.1 promociones) y registrar todo cambio de alcance. | Felipe | Una solicitud de cambio de alcance, o un avance semanal por debajo de lo planeado |
| R-14 ✏️ | Mitigar | Confirmar en la documentación de Render y Neon los límites de los planes gratuitos; medir el tiempo de la primera petición tras la inactividad en el despliegue de prueba; mantener el servicio activo antes del piloto o pasar a un plan de pago (costo por incluir en el presupuesto). | Felipe y Diego Gómez | Primera petición tras inactividad > 3 s, o conexión en tiempo real cortada por la suspensión |
| R-15 ✏️ | Mitigar | Llevar al equipo y al dueño la decisión sobre el inicio de sesión de clientes y la cuenta de cocina; pasar el conflicto RNF-26.2 / RNF-25.2 por control de cambios (1.3.1) antes de implementar 2.3.1. | Felipe | 2.3.1 o 7.1.1 por empezar sin decisión |
| R-16 ✏️ | Mitigar | Crear el proyecto de Firebase y asignar un responsable de FCM; hacer un prototipo de notificación con la app cerrada antes de 6.3.2; si se recorta el alcance, revisar si el requisito se mantiene. | Por asignar | 6.3.2 por empezar sin proyecto de Firebase, o notificación > 5 s |
| R-08 ✏️ | Mitigar | Acordar con Pepito Pérez una fecha límite para entregar el menú, los precios y las reglas de fidelización (propuesta: 15/11). | Felipe | Datos incompletos en la fecha límite |
| R-06 ✏️ | Mitigar | Medir velocidad y estabilidad del Wi-Fi de CaffeBar con dispositivos reales; mantener la alerta de desconexión y la reconexión automática. | Felipe | Latencia > 3 s o caídas durante la medición |

### 3.1 R-01 materializado: evidencia (12/11/2026)

El disparador de R-01 ("fecha de fin recalculada > 17/12") se cumplió. Cálculo, con calendario de lunes a sábado y sin festivos (2/11, 16/11, 8/12, 25/12, 1/1):

| Dato | Valor |
|------|-------|
| Días hábiles transcurridos desde el inicio real (28/10) hasta el 12/11 | 13 |
| Ruta crítica completada | 6 de 49 días (8.1.1 y 2.1.1) |
| Ruta crítica pendiente | 43 días |
| Días hábiles disponibles del 13/11 al 17/12 | 28 |
| Déficit | **15 días hábiles** |
| Fin proyectado al ritmo del plan | **6 de enero de 2027** |
| Fin del plan aun con inicio perfecto el 28/10 | 28 de diciembre de 2026 |

- El cronograma tomaba el 29/09 como día 0, pero el desarrollo inició el 28/10. El plan ya superaba el 17/12 desde su origen.
- 8.1.1 tomó cerca de 7 días hábiles frente a los 3 planeados; 2.1.1 se cerró dentro de su duración una vez iniciado.
- Se da por terminado 8.1.1. Si quedaran partes pendientes, el déficit sería mayor.
- Efecto sobre la reserva: el Plan de Riesgos supuso 8 días de retraso (160 h). Con 15 días serían unas 300 h (15 días × 5 personas × 4 h), por encima de la reserva de contingencia de 133,5 h. Hay que recalcular el presupuesto una vez se defina la respuesta.
- Los hitos del acta del 15/11 (administración, pedidos y cocina) y del 29/11 (fidelización y QR) tampoco se cumplirán con este ritmo.

**Estrategia de respuesta:** por definir.

### 3.2 Disponibilidad del equipo (R-02, R-05, R-10, R-13), al 12/11/2026

Lo que cada integrante informó al gerente, junto con el avance entregado y la asistencia a los 4 dailies realizados (3, 5, 9 y 10/11):

| Persona | Avance entregado | Motivo informado | Dailies ✅ |
|---------|------------------|------------------|:----------:|
| Felipe (gerente) | Spring Boot, base de datos, pipelines de CI, proyecto Android y 2.1.1 completo (backend y Android) | — | 4 de 4 |
| Diego Gómez | Modelo de datos inicial (8.1.1) | — | 4 de 4 |
| Diego Bolaños | Ninguna tarea | No ha podido desarrollar por los retrasos en las tareas de Sebastián y Stiven, de las que depende | 1 de 4 |
| Sebastián Aragón | Ninguna tarea | Exceso de carga en las demás materias | 1 de 4 |
| Stiven Mujanajinsoy | Ninguna tarea | Exceso de carga en las demás materias | 2 de 4 |
| David Ascencio | Ninguna tarea | Razones personales y laborales | 2 de 4 |

- Solo el gerente y Diego Gómez han hecho el trabajo, incluido el de los demás para adelantar.
- Esto es una causa distinta a la prevista en R-02 (semanas de parciales): la falta de dedicación ya es general y no pasajera.
- R-05 sube de P 3 a P 4: el único tester no ha realizado ninguna actividad y todavía no hay pruebas por módulo.
- Pendiente: acordar con cada integrante qué dedicación real puede asumir desde ahora.

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
| 12/11/2026 | Felipe (revisión del gerente, sin reunión del equipo) | **Sí:** R-01 (ver 3.1) | R-01: P 4 → 5 (20 → 25). R-02: P 4 → 5 (16 → 20). R-10: P 4 → 5 (16 → 20). R-05: P 3 → 4 (12 → 16) | R-13 a R-16 (ver sección 2) | Ninguno |

---

## 6. Historial de cambios

| Fecha | ID | Cambio (estado, P, I, estrategia, etc.) | Valor anterior → nuevo | Motivo |
|-------|:--:|------------------------------------------|------------------------|--------|
| 3/11/2026 | Todos | Registro inicial | — | Primer registro a partir del Plan de Riesgos v0.3 |
| 12/11/2026 | R-01 | Estado, probabilidad y estrategia | Abierto, P 4, severidad 20, mitigar + escalar → **Materializado, P 5, severidad 25, estrategia por definir** | Disparador cumplido: fin proyectado 6/1/2027 frente al 17/12/2026 (déficit de 15 días hábiles). Detalle en la sección 3.1 |
| 12/11/2026 | R-02 | Estado, probabilidad y estrategia | Abierto, P 4, severidad 16, mitigar → **Materializado, P 5, severidad 20, estrategia por definir** | Ningún integrante salvo el gerente y Gómez ha entregado tareas; los motivos informados no son solo parciales (sección 3.2) |
| 12/11/2026 | R-10 | Estado y probabilidad | Abierto, P 4, severidad 16 → **Materializado, P 5, severidad 20** | Disparador cumplido: 8.1.1 con retraso (unos 7 días hábiles frente a 3); el backend de 2.1.1 lo hizo el gerente |
| 12/11/2026 | R-05 | Probabilidad | P 3, severidad 12 → **P 4, severidad 16** | El único tester no ha realizado ninguna tarea (sección 3.2) |
| 12/11/2026 | R-12 | Enunciado, disparador | Hosting sin elegir al 15/11 → hosting elegido (Neon + Render, 10/11); disparador cambia a despliegue de prueba | Decisión del gerente del 10/11; el presupuesto sigue con USD 15/mes |
| 12/11/2026 | R-13 a R-16 | Riesgos nuevos | — | R-13 trabajo concentrado en el gerente y Gómez; R-14 planes gratuitos que se suspenden; R-15 requisitos sin definir; R-16 notificaciones push sin proyecto de Firebase |
