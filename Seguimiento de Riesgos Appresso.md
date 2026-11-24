# SEGUIMIENTO DE RIESGOS — APPRESSO

> **Última actualización:** 23 de noviembre de 2026 (corte del 21/11 y decisiones CC-03)
> **Responsable del registro:** Felipe Salcedo (gerente del proyecto)
> **Fuentes:** [Plan de Riesgos Appresso](Plan%20de%20Riesgos%20Appresso.md) (enunciados, escala y costo esperado), [Métricas del Proyecto](Métricas%20de%20Proyecto%20Appresso.md) y [Registro de Horas](Registro%20de%20Horas%20Appresso.md) (evidencia del corte), y [Presupuesto](Presupuesto%20Appresso.md) (costos y aprobaciones).

Este archivo se actualiza en cada reunión de seguimiento. Los enunciados, las probabilidades y los impactos cambian aquí; el plan se queda como referencia del punto de partida.

---

## 1. Preguntas de cada reunión

Estas cinco preguntas se responden **en orden** en cada reunión de seguimiento. Lo que se decida se anota en la sección 5.

1. **¿Se disparó alguno?** Revisar los disparadores de la sección 3. Si se cumple una alerta preventiva, ejecutar la acción acordada. Si ocurrió el evento, registrar el problema como *Materializado*, su impacto y la respuesta de recuperación.
2. **¿Cambió alguna probabilidad o impacto?** A medida que el proyecto avanza, unos riesgos crecen y otros desaparecen solos. Actualizar la sección 2 y recalcular la severidad.
3. **¿Apareció alguno nuevo?** Cada cambio de alcance y cada decisión técnica trae riesgos que antes no existían. Redactarlo con la plantilla (Debido a / podría ocurrir que / lo que provocaría) y agregarlo.
4. **¿Se puede cerrar alguno?** Cerrar cuando haya evidencia de que el evento incierto dejó de ser relevante o de que el problema materializado y sus acciones quedaron resueltos. Revisar el efecto sobre la reserva. Cerrar riesgos es tan importante como abrirlos: mantiene la lista corta y creíble.
5. **¿Se cumplieron las prácticas de calidad?** Según el [Plan de Calidad](Plan%20de%20Calidad%20Appresso.md): cobertura de pruebas sobre la lógica crítica (meta ≥ 70 %), revisión entre pares en cada cambio integrado y definición de terminado en cada entregable cerrado. Anotar lo que no se cumplió.

---

## 2. Registro de riesgos

**Severidad = Probabilidad × Impacto** (escala de 1 a 5 para cada una; ver sección 4 del plan).
**Clasificación:** 🟢 1–4 · 🟡 5–9 · 🟠 10–14 · 🔴 15–25.

| ID | Enunciado | Categoría | P | I | Severidad | Estado |
|:--:|-----------|-----------|:-:|:-:|:---------:|:------:|
| R-01 | **Debido a** que la ruta crítica vigente dura 46 días sin holgura tras CC-03 (calendario de lunes a domingo) y el desarrollo inició el 28/10 y no el 29/09 que usaba el cronograma, **podría ocurrir que** la fecha de fin supere el 15/12/2026, **lo que provocaría** que la v1.0 no esté desplegada ni validada en el piloto a tiempo. | Cronograma | 5 | 5 | 🔴 25 | **Materializado** (12/11/2026) |
| R-02 | **Debido a** que el cronograma asume 4 h/día y el equipo tiene otras materias, **podría ocurrir que** la dedicación real baje en semanas de parciales y entregas, **lo que provocaría** retrasos en entregables críticos y recorte forzado de alcance. | Recursos | 5 | 4 | 🔴 20 | **Materializado** (12/11/2026) |
| R-10 | **Debido a** que el equipo de backend no tiene experiencia en Spring Boot y 8.1.1 abre la ruta crítica, **podría ocurrir que** la curva de aprendizaje alargue arquitectura, autenticación y roles, **lo que provocaría** el retraso de toda la ruta crítica. | Tecnológico | 5 | 4 | 🔴 20 | **Materializado** (12/11/2026) |
| R-13 | **Debido a** que Felipe y Diego Gómez acumulan 112 de las 166 h al 21/11 y el respaldo para los trabajos críticos sigue pendiente de confirmar (ver 3.1.2), **podría ocurrir que** alguno de los dos se enferme, se sobrecargue o deje de estar disponible, **lo que provocaría** bloqueos en trabajos críticos y menos tiempo del gerente para gestionar el proyecto. | Recursos | 4 | 5 | 🔴 20 | Abierto |
| R-11 | **Debido a** que la sincronización con cocina usa STOMP/SockJS, 8.2.1 tiene 2 días y un solo responsable, y se exige ≤ 3 s, **podría ocurrir que** la conexión se caiga, no se reconecte o supere los 3 s, **lo que provocaría** que las comandas lleguen tarde o no lleguen a cocina. | Tecnológico | 4 | 4 | 🔴 16 | Abierto |
| R-12 | **Debido a** que se exige producción con HTTPS antes del 15/12, 8.5.1 dura 3 días al final de la ruta crítica y aún falta registrar la evidencia de los despliegues internos continuos acordados con Render y Neon, **podría ocurrir que** falle la configuración del servidor, la base de datos o el certificado, **lo que provocaría** que la app no esté en producción para el piloto o que haya un gasto no presupuestado. | Tecnológico | 3 | 5 | 🔴 15 | Abierto |
| R-03 | **Debido a** que Diego Gómez tiene 14 entregables como R y 9 como A, incluyendo 5 de la ruta crítica, **podría ocurrir que** se enferme o no esté disponible unos días, **lo que provocaría** el bloqueo de arquitectura, pruebas y despliegue. | Recursos | 3 | 4 | 🟠 12 | Abierto |
| R-04 | **Debido a** que 4 entregables críticos de caja están encadenados 12 días sin margen tras CC-03 y con reglas financieras exigentes, **podría ocurrir que** un error en saldos, retiros o cierre se detecte tarde, **lo que provocaría** el retraso de las pruebas, el despliegue y el cierre. | Calidad | 3 | 4 | 🟠 12 | Abierto |
| R-05 | **Debido a** que hay un solo tester y las pruebas (N°29) solo empiezan cuando terminan comandas, pagos, puntos y cierre de caja, **podría ocurrir que** los defectos se descubran todos al final, **lo que provocaría** una entrega sin el 70 % de cobertura o con errores en caja y comandas. | Calidad | 4 | 4 | 🔴 16 | Abierto |
| R-07 | **Debido a** que se recolectan nombre, cédula y celular de clientes y no hay política de tratamiento de datos ni responsable designado, **podría ocurrir que** el piloto arranque sin política aprobada o con el texto de aceptación incompleto, **lo que provocaría** incumplimiento de la Ley 1581 de 2012 y posible sanción para CaffeBar. | Normativo | 3 | 4 | 🟠 12 | Abierto |
| R-09 | **Debido a** que la línea base vigente conserva 30 entregables tras el recorte y el plazo del curso sigue siendo el 15/12, **podría ocurrir que** el equipo no alcance a implementar todo con calidad, **lo que provocaría** módulos incompletos o recortes sin acordar con el cliente. | Alcance | 4 | 3 | 🟠 12 | Abierto |
| R-14 | **Debido a** que el backend y la base de datos se alojarán en planes gratuitos de Render y Neon, que (por confirmar en su documentación) se suspenden tras un periodo sin tráfico, **podría ocurrir que** la primera petición tras la inactividad tarde mucho o que la conexión en tiempo real se corte, **lo que provocaría** que las comandas lleguen tarde a cocina (≤ 3 s) o que el piloto arranque con fallos. | Tecnológico | 3 | 4 | 🟠 12 | Abierto |
| R-15 | **Debido a** que los requisitos no definen cómo se usa la cuenta compartida de cocina (el inicio de sesión del cliente se decidió el 17/11: documento y contraseña; y el conflicto entre RNF-26.2 y RNF-25.2 se resolvió el 17/11 exceptuando al cocinero del cierre de sesión por inactividad), **podría ocurrir que** se implemente algo que luego haya que rehacer, **lo que provocaría** retrabajo en 2.3.1 y en el Bloque 7 y un cambio de requisitos sin acordar. | Alcance | 4 | 3 | 🟠 12 | Abierto |
| R-16 | **Debido a** que el acta y la EDT exigen notificaciones push (retiros al administrador en ≤ 5 s con la app cerrada, 6.3.2, y promociones, 7.4.1) y todavía no hay proyecto de Firebase ni responsable asignado, **podría ocurrir que** la integración de notificaciones se descubra tarde o no funcione con la app cerrada, **lo que provocaría** retraso en 6.3.2, que está en la ruta crítica, e incumplimiento de un criterio de aceptación del acta. | Tecnológico | 3 | 4 | 🟠 12 | Abierto |
| R-08 | **Debido a** que no hay fecha límite acordada para que Pepito Pérez entregue productos, precios, promociones y reglas de fidelización, **podría ocurrir que** los datos lleguen tarde o incompletos, **lo que provocaría** que no se pueda cargar el menú real ni configurar la fidelización antes del piloto. | Externo (cliente) | 3 | 3 | 🟡 9 | En vigilancia |
| R-06 | **Debido a** que el sistema depende del Wi-Fi y se exige ≤ 3 s a cocina, pero no se ha medido la red de CaffeBar, **podría ocurrir que** la red sea inestable o lenta en el servicio, **lo que provocaría** que las comandas no lleguen a tiempo y el piloto no cumpla los criterios. | Externo (entorno) | 2 | 4 | 🟡 8 | En vigilancia |

---

## 3. Respuesta a cada riesgo

El puntaje vigente está en la sección 2. Las acciones marcadas con ✏️ y las asignaciones o fechas indicadas como propuestas requieren validación del equipo.

| ID | Estrategia (decisión) | Acción concreta | Responsable | Disparador |
|:--:|-----------------------|-----------------|-------------|------------|
| R-01 | **Mitigar + Escalar** (plan de acción aprobado el 16/11/2026) | (a) Domingos y festivos pasan a ser días de trabajo (CC-02). (b) Cada integrante se compromete a entregar sus tareas a tiempo. (c) Aplicar el recorte aprobado el 21/11 (CC-03) y revisar el déficit pendiente. Ver secciones 3.1.1 y 3.1.3. | Felipe | **Cumplido el 12/11/2026:** fecha de fin recalculada (6/1/2027) > 17/12. La fecha de entrega del curso ahora es el 15/12 |
| R-02 | **Mitigar** (plan de acción aprobado el 16/11/2026, ver R-01) | El compromiso individual de entrega a tiempo y el calendario de siete días responden a la falta de dedicación (sección 3.2). La respuesta inicial del plan (calendario de parciales y reasignación) no cubría lo ocurrido. | Felipe | **Cumplido:** integrantes informaron que no cumplen las 4 h/día |
| R-10 | Materializado, recuperación pendiente | Revisar en pareja el siguiente cambio de backend en ruta crítica y verificar que ambos desarrolladores puedan explicarlo y probarlo. Registrar el esfuerzo incremental de acompañamiento. El tutorial inicial quedó sin ejecutar. | Diego Gómez (propuesta de recuperación) | Acordar la recuperación antes de iniciar el siguiente paquete crítico de backend. Evidencia: PR revisado y pruebas ejecutadas por ambos. |
| R-11 | Mitigar | Completar las pruebas pendientes en dispositivos reales y registrar red, equipos, latencias y reconexión. Repetir en el Wi-Fi de CaffeBar para el piloto. | Diego Gómez | Antes de dar 8.2.1 por aceptado, escalar si menos del 95 % de los eventos llega en 3 s o menos, si falta la medición o si la reconexión falla. |
| R-12 | Mitigar y usar servicios gestionados | Iniciar los despliegues internos continuos aprobados el 21/11 con Render y Neon. Registrar fecha, versión o commit y resultado, con evidencia del arranque, HTTPS y conexión a PostgreSQL. Coordinar la medición tras inactividad con R-14 y preparar la v1.0 en producción en 8.5.1. | Felipe coordina, Diego Gómez ejecuta (reparto propuesto) | Desde la reunión del 21/11. Escalar a Felipe si falta evidencia del entorno interno o falla una comprobación, y registrar la corrección antes de 8.5.1. |
| R-13 ✏️ | Mitigar, propuesta prioritaria | Revisar la carga de Felipe y Gómez y acordar un suplente con capacidad para cada trabajo crítico. Evidencia: responsables y suplentes en el tablero, traspaso registrado y una tarea revisada o ejecutada por el suplente. | Felipe | En la próxima reunión, escalar si un paquete crítico sigue dependiendo de una sola persona o si el titular prevé más de dos días de ausencia sin respaldo. |
| R-03 ✏️ | Mitigar | Proponer a Diego Bolaños como respaldo técnico de Gómez y comprobar que puede ejecutar el despliegue con los pasos documentados. Coordinar con R-13 y registrar las horas compartidas una sola vez. | Felipe | En la próxima reunión, confirmar respaldo. Escalar si un entregable crítico de Gómez queda sin suplente. |
| R-04 ✏️ | Mitigar | Escribir las pruebas unitarias de saldos separados y de la ecuación de cierre al terminar cada entregable del Bloque 6, sin esperar a 8.3.1; el tester revisa cada uno. | Diego Bolaños | Un entregable del Bloque 6 con más de 1 día de retraso, o una prueba de saldos que falle |
| R-05 ✏️ | Mitigar, propuesta prioritaria | Preparar pruebas por módulo y habilitar medición de cobertura de la lógica crítica antes de cerrar comandas o pagos. Evidencia: plan de casos, informe de cobertura y defectos abiertos. | David Ascencio (propuesto), Felipe confirma capacidad y respaldo | En la próxima reunión, confirmar quién prepara las pruebas. Escalar si comandas o pagos llegan a revisión sin informe, si la cobertura mide menos del 70 % o si queda un defecto de prioridad alta al inicio de 8.3.1. |
| R-07 ✏️ | Mitigar + Escalar | Redactar la política de tratamiento y el texto de aceptación; escalar a Pepito Pérez, como responsable del tratamiento, para que los apruebe, y registrar que se escaló. | Felipe | Sin política aprobada a una semana del piloto |
| R-09 ✏️ | Mitigar | Aplicar el recorte de las vistas de consulta aprobado por el patrocinador (CC-03). Revisar el alcance vigente y registrar cualquier cambio adicional acordado con el cliente. | Felipe | Una solicitud de cambio de alcance, o un avance semanal por debajo de lo planeado |
| R-14 ✏️ | Mitigar | Confirmar en la documentación de Render y Neon los límites de los planes gratuitos; medir el tiempo de la primera petición tras la inactividad en el entorno interno de Render y Neon; mantener el servicio activo antes del piloto o pasar a un plan de pago (costo por incluir en el presupuesto). | Felipe y Diego Gómez | Primera petición tras inactividad > 3 s, o conexión en tiempo real cortada por la suspensión |
| R-15 ✏️ | Mitigar | Llevar al equipo y al dueño la decisión sobre la cuenta de cocina (el inicio de sesión de clientes ya se decidió: documento y contraseña); implementar en 2.3.1 la excepción del cocinero al cierre de sesión por inactividad (RNF-26.2 / RNF-25.2, ya resuelta en los requisitos). | Felipe | 2.3.1 o 7.1.1 por empezar sin decisión |
| R-16 ✏️ | Mitigar | Confirmar responsable de FCM, crear el proyecto Firebase y probar una notificación de retiro con la app cerrada. Registrar el tiempo y el dispositivo. | Felipe coordina, responsable técnico por confirmar con el equipo | Confirmar responsable en la próxima reunión y probar antes de iniciar 6.3.2. Escalar si falta el prototipo, si la notificación tarda más de 5 s o si falla con la app cerrada. |
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
- El déficit de 15 días corresponde a la proyección de plazo de ese corte. El costo de recuperación se estima por tareas adicionales y gastos aprobados.
- Los hitos del acta del 15/11 (administración, pedidos y cocina) y del 29/11 (fidelización y QR) tampoco se cumplirán con este ritmo.

**Estrategia de respuesta:** definida el 16/11/2026 (ver 3.1.1).

### 3.1.1 R-01: plan de acción aprobado y recálculo (17/11/2026)

La reunión del equipo del 16/11/2026 aprobó este plan de acción:

1. **Domingos y festivos como días de trabajo.** El calendario pasa a lunes a domingo, sin festivos descontados (CC-02, ver [Métricas de Proyecto](Métricas%20de%20Proyecto%20Appresso.md), sección 2.4).
2. **Compromiso de entrega.** Cada integrante se compromete a entregar sus tareas a tiempo.
3. **Recorte del proyecto en la siguiente reunión**, cuando se vea cómo mejoran las métricas ahora que el equipo se estabilizó. El equipo y el patrocinador aprobaron el recorte el 21/11 y quedó registrado como CC-03 (sección 3.1.3).

Además, **la fecha de entrega del curso cambia al 15/12/2026** (antes 17/12). Con el calendario de siete días, el recálculo del 3.1 queda así:

| Dato | Valor |
|------|-------|
| Días transcurridos desde el inicio real (28/10) hasta el 12/11 | 16 |
| Ruta crítica completada | 6 de 49 días (8.1.1 y 2.1.1) |
| Ruta crítica pendiente | 43 días |
| Días disponibles del 13/11 al 15/12 | 33 |
| Déficit | **10 días** (antes 15) |
| Fin proyectado al ritmo del plan | **25 de diciembre de 2026** (antes 6 de enero de 2027) |
| Fin del plan con inicio perfecto el 28/10 | 15 de diciembre de 2026 (antes 28 de diciembre) |

- El déficit baja, pero no desaparece: el plan solo cierra si el equipo rinde mejor que hasta ahora (la tasa de avance real, SPI 0,36, no lo permite).
- El déficit de 10 días corresponde a la proyección del corte del 12/11 con el calendario revisado. La sección 3.1.2 registra el recálculo al 21/11.

### 3.1.2 Seguimiento al corte del 21/11/2026

| Indicador | S3 (14/11) | S4 (21/11) |
|-----------|-----------:|-----------:|
| Valor planificado (PV) | $2.195.000 | $2.465.000 |
| Valor ganado (EV) | $785.000 | $1.625.000 |
| Costo real (AC) | $1.805.000 | $2.570.000 |
| Variación de cronograma (SV) | −$1.410.000 | −$840.000 |
| Variación de costo (CV) | −$1.020.000 | −$945.000 |
| SPI | 0,36 🔴 | 0,66 🔴 |
| CPI | 0,43 🔴 | 0,63 🔴 |

- **R-01 y R-09.** En S4 se cerraron cinco paquetes y quedaron nueve terminados en total. La ruta crítica tiene 14 de sus 49 días de duración planificada cubiertos por paquetes terminados (8.1.1, 2.1.1, 2.3.1 y 3.1.1). Quedan 35 días de duración planificada para paquetes críticos sin cerrar frente a 24 días disponibles del 22/11 al 15/12. El déficit es de **11 días** con este cálculo. Si se dedica la duración completa del plan a cada paquete crítico sin cerrar, la fecha de este escenario es el **26/12/2026**. 6.1.1 está en revisión y su esfuerzo restante puede ser menor a su duración completa. Este cálculo corresponde a la línea base anterior al recorte. La sección 3.1.3 muestra el efecto de la decisión del 21/11.
- **R-02 y R-13.** En S4 se registraron 51 h. Felipe y Diego Gómez aportaron 23 h de ese corte y 112 de las 166 h acumuladas. El trabajo de S4 quedó más repartido. Sigue pendiente verificar el cumplimiento de la dedicación prevista y acordar suplentes para los trabajos críticos.
- **R-05 y R-11.** El tablero conserva el registro de cinco defectos detectados en la revisión de 8.2.1. Siguen pendientes el conteo de las entregas de S4 y la evidencia de las pruebas de latencia y reconexión en dispositivos reales para R-11.
- **Decisiones de costo registradas el 23/11.** Se aprobaron 52 h extra trabajadas al corte. El ahorro de 2 h en 1.2.1 deja una desviación neta de 50 h ($750.000) en los paquetes terminados, ya incluida en el AC. Se confirmaron las fechas de Claude Code: $80.000 pagados el 28/10 y $80.000 programados para el 28/11. La conciliación por riesgo y el uso de la reserva continúan pendientes de registro. Ver [Presupuesto](Presupuesto%20Appresso.md), sección 7.1.

### 3.1.3 Decisiones de la reunión de control del 21/11/2026

**Recorte de alcance (CC-03).** El equipo y el patrocinador aprobaron retirar las vistas independientes de consulta de caja del cajero y de consulta financiera del administrador (RF-38/RF-39). Continúan el historial de movimientos de 6.3.2 y los informes de cierre. El cierre de caja depende directamente de 6.3.2. La línea base vigente queda en **30 paquetes, 361 h, 46 días de ruta crítica y $5.623.000 de BAC**. El fin planificado pasa al **12/12/2026** y la entrega del curso sigue fijada para el **15/12/2026**. Ver [registro de cambios](Métricas%20de%20Proyecto%20Appresso.md#24-registro-de-cambios-a-las-líneas-base).

Con el mismo criterio de la sección 3.1.2, quedan **32 días de duración planificada** en paquetes críticos sin cerrar frente a 24 días disponibles. El déficit baja de 11 a **8 días**. Si se consume la duración completa de esos paquetes, el escenario termina el **23/12/2026**. Es una proyección con el trabajo pendiente al corte. R-01 sigue materializado y el calendario conserva la fecha límite del curso.

**Despliegue continuo interno.** El equipo y el patrocinador aprobaron iniciar desde la reunión los despliegues internos en Render (backend) y Neon (base de datos) para validar el sistema durante el desarrollo. El despliegue de la v1.0 en producción se mantiene al final, en 8.5.1. Queda por registrar la evidencia de ejecución del entorno interno y seguir R-12 y R-14.

### Conciliación de exposición y respuesta

| Riesgos | Qué estimar para actualizar el presupuesto | Responsable de coordinar |
|---|---|---|
| R-01, R-02, R-10 (materializados) | Conciliar las horas registradas con la recuperación aprobada y estimar las acciones que aún faltan. Asignar los costos compartidos una sola vez. | Felipe con Diego Gómez |
| R-05 y R-13 (críticos abiertos) | Estimar las horas adicionales de pruebas y traspaso. Valorar la exposición residual tras confirmar responsables y capacidad. Cruzar el traspaso con R-03. | Felipe con David Ascencio y Diego Gómez |
| R-11 y R-12 (críticos abiertos) | Separar las pruebas y los despliegues internos adicionales del trabajo de 8.2.1 y del despliegue final de 8.5.1. Estimar retrabajo y gastos residuales, y vincular los costos del alojamiento con R-14. | Diego Gómez con Felipe |

En la próxima reunión de seguimiento, validar fechas y responsables, revisar el registro de horas y documentar la estimación por tarea o gasto. Felipe consolida la propuesta y registra la decisión de aprobación en el presupuesto y en métricas cuando corresponda.

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

| Fecha | Asistentes | 1. ¿Se disparó alguno? | 2. ¿Cambió alguna P o I? | 3. ¿Apareció alguno nuevo? | 4. ¿Se puede cerrar alguno? | 5. Calidad |
|-------|------------|------------------------|--------------------------|----------------------------|-----------------------------|------------|
| 12/11/2026 | Felipe (revisión del gerente, sin reunión del equipo) | **Sí:** R-01 (ver 3.1) | R-01: P 4 → 5 (20 → 25). R-02: P 4 → 5 (16 → 20). R-10: P 4 → 5 (16 → 20). R-05: P 3 → 4 (12 → 16) | R-13 a R-16 (ver sección 2) | Ninguno | No registrado |
| 16/11/2026 | Equipo (reunión de seguimiento): todos menos David Ascencio; Diego Bolaños llegó tarde | No registrado | R-01 y R-02: estrategia definida (ver 3.1.1) | No registrado | No registrado | No registrado |
| 21/11/2026 | Reunión de control. Aprobación del equipo y del patrocinador registrada. Asistencia sin detalle en este registro | R-01 seguía materializado | CC-03 aprobado. Recorte de las vistas de consulta y puesta en marcha de despliegues internos continuos (R-12 y R-14) | Sin registro adicional | Sin registro adicional | Evidencia de despliegues internos por registrar. Ver 3.1.3 |

---

## 6. Historial de cambios

| Fecha | ID | Cambio (estado, P, I, estrategia, etc.) | Valor anterior → nuevo | Motivo |
|-------|:--:|------------------------------------------|------------------------|--------|
| 3/11/2026 | Todos | Registro inicial | — | Primer registro a partir del Plan de Riesgos v0.3 |
| 12/11/2026 | R-01 | Estado, probabilidad y estrategia | Abierto, P 4, severidad 20, mitigar + escalar → **Materializado, P 5, severidad 25, estrategia por definir** | Disparador cumplido: fin proyectado 6/1/2027 frente al 17/12/2026 (déficit de 15 días hábiles). Detalle en la sección 3.1 |
| 12/11/2026 | R-02 | Estado, probabilidad y estrategia | Abierto, P 4, severidad 16, mitigar → **Materializado, P 5, severidad 20, estrategia por definir** | Ningún integrante salvo el gerente y Gómez ha entregado tareas; los motivos informados no son solo parciales (sección 3.2) |
| 12/11/2026 | R-10 | Estado y probabilidad | Abierto, P 4, severidad 16 → **Materializado, P 5, severidad 20** | Disparador cumplido: 8.1.1 con retraso (unos 7 días hábiles frente a 3); el backend de 2.1.1 lo hizo el gerente |
| 12/11/2026 | R-05 | Probabilidad | P 3, severidad 12 → **P 4, severidad 16** | El único tester no ha realizado ninguna tarea (sección 3.2) |
| 12/11/2026 | R-12 | Enunciado, disparador | Hosting sin elegir al 15/11 → hosting elegido (Neon + Render, 10/11); disparador cambia a despliegue de prueba | Decisión del gerente del 10/11; el presupuesto de ese corte seguía con USD 15/mes |
| 12/11/2026 | R-13 a R-16 | Riesgos nuevos | — | R-13 trabajo concentrado en el gerente y Gómez; R-14 planes gratuitos que se suspenden; R-15 requisitos sin definir; R-16 notificaciones push sin proyecto de Firebase |
| 17/11/2026 | R-01 | Estrategia, enunciado y fecha | Por definir; fecha de entrega 17/12 → **Mitigar + Escalar (plan de acción del 16/11); fecha de entrega 15/12** | Plan de acción aprobado por el equipo (domingos y festivos laborables, compromiso de entrega, recorte en la siguiente reunión) y cambio de la fecha de entrega del curso. Detalle en la sección 3.1.1 |
| 17/11/2026 | R-02 | Estrategia | Por definir → **Mitigar** | Mismo plan de acción: compromiso individual de entrega a tiempo |
| 17/11/2026 | R-12 | Enunciado | Producción con HTTPS antes del 17/12 → **antes del 15/12** | Nueva fecha de entrega del curso |
| 17/11/2026 | R-15 | Enunciado y acción | El enunciado incluía que no estaba definido cómo inicia sesión un cliente → **solo queda pendiente la cuenta de cocina y el conflicto RNF-26.2 / RNF-25.2** | El equipo decidió que el cliente inicia sesión solo con número de documento y contraseña (RF-01, RF-50) |
| 17/11/2026 | — | Pregunta 5 (calidad) y columna «5. Calidad» en el registro de reuniones | Cuatro preguntas → cinco preguntas | Cumple el seguimiento de las prácticas del Plan de Calidad v0.3 |
| 17/11/2026 | R-03, R-15 | Enunciados | R-03: «3 de la ruta crítica» → **5**. R-15: pendiente «la cuenta de cocina y el conflicto RNF-26.2 / RNF-25.2» → **solo la cuenta de cocina** | R-03: Gómez participa como R en 5 entregables críticos. R-15: el conflicto se resolvió en los requisitos exceptuando al cocinero |
| 21/11/2026 | R-01, R-04, R-09 | Recorte aprobado (CC-03) | Salen las dos vistas independientes de consulta. Se conservan el historial de movimientos y los informes de cierre. La ruta crítica baja de 49 a 46 días, el esfuerzo de 371 a 361 h y el BAC de $5.773.000 a $5.623.000 | Acuerdo de la reunión de control aprobado por el equipo y el patrocinador |
| 21/11/2026 | R-12, R-14 | Respuesta de despliegue | Despliegue de prueba temprano → inicio de despliegues internos continuos con Render y Neon. La v1.0 se publica en producción al final | Acuerdo de la reunión de control aprobado por el equipo y el patrocinador |
| 23/11/2026 | R-01, R-02, R-05, R-09, R-11, R-13 | Evidencia del corte del 21/11 y enunciado de R-13 | SPI 0,36 → **0,66** y CPI 0,43 → **0,63**. R-13 pasa a documentar la concentración acumulada y el reparto de S4 | Métricas, registro de horas y recálculo de la ruta crítica. Detalle en 3.1.2 |
| 23/11/2026 | — | Aprobación de horas extra y fechas de Claude Code | **52 h extra aprobadas**. Desviación neta de 50 h ($750.000). Primer pago confirmado el 28/10 y segundo programado para el 28/11 | Decisiones registradas en el presupuesto y en las métricas del corte del 21/11 |
