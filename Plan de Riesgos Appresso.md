# PLAN DE RIESGOS — APPRESSO

> **Estado:** borrador v0.3 (3 de noviembre de 2026). Lista de riesgos candidatos para revisar con el equipo.
> **Responsable:** Felipe Salcedo (entregable 1.2.1 — Plan temporal, económico y de riesgos).

## 1. Cómo se redactan los riesgos

Cada riesgo se escribe con tres partes. Si falta una, el enunciado no está terminado.

```
Debido a      [causa: un hecho verificable de hoy]
podría ocurrir que   [evento incierto]
lo que provocaría    [efecto sobre el proyecto]
```

- **Causa:** dice dónde actuar.
- **Evento:** dice qué vigilar.
- **Efecto:** dice cuánto importa.

**Reglas para revisar cada enunciado**

- La causa debe ser un hecho que hoy se pueda comprobar (un documento, una fecha, un número), no una opinión ni algo futuro.
- El evento debe ser incierto: puede pasar o no. Si ya pasó, es un problema, no un riesgo.
- El efecto debe tocar un objetivo del proyecto: plazo (17/12/2026), alcance, costo o calidad.

---

## 2. Riesgos de gestión y del entorno

### R-01 — Plazo de la ruta crítica frente a la fecha de entrega

**Debido a** que el cronograma calcula la ruta crítica en 49 días hábiles (lunes a sábado) con holgura cero en 14 entregables, y que el desarrollo inició el 28/10/2026 (Sprint 0) y no el 29/09 que usa el cronograma como día 0,
**podría ocurrir que** la fecha de fin proyectada de la ruta crítica supere el 17/12/2026,
**lo que provocaría** que la v1.0 no esté desplegada ni validada en la prueba piloto en la fecha comprometida.

### R-02 — Disponibilidad del equipo por la carga académica

**Debido a** que el cronograma asume 4 h/día de dedicación, el acta registra que los integrantes tienen otras materias, y no hay ningún mecanismo de respaldo para los cargos con una sola persona clave (Diego Gómez en arquitectura, sincronización en tiempo real y pruebas),
**podría ocurrir que** la dedicación real baje de 4 h/día en las semanas de parciales y entregas finales (noviembre–diciembre),
**lo que provocaría** retrasos acumulados en entregables críticos y recorte forzado de alcance (p. ej. promociones, N°26).

### R-03 — Concentración de la carga en Diego Gómez

**Debido a** que el RACI asigna a Gómez 14 entregables como R y 9 como A, incluyendo 3 de la ruta crítica (8.1.1, 8.3.1, 8.5.1),
**podría ocurrir que** Gómez se enferme, se sobrecargue o no esté disponible unos días,
**lo que provocaría** que se bloqueen arquitectura, pruebas y despliegue, que no tienen holgura.

### R-04 — Módulo de caja: cadena larga sin holgura

**Debido a** que 5 de los 14 entregables críticos (6.1.1, 6.3.1, 6.3.2, 6.4.1, 6.5.1) están encadenados en serie, ocupan 15 días sin margen y tienen reglas financieras exigentes (saldos separados, ecuación de cierre),
**podría ocurrir que** un error o retrabajo en los saldos, los retiros o el cierre de caja se detecte tarde,
**lo que provocaría** que se retrase el módulo de pruebas (N°29) y, con él, el despliegue y el cierre del proyecto.

### R-05 — Pruebas con un solo tester y al final de la cadena

**Debido a** que el RACI asigna a David Ascencio como único tester, con 1 entregable como R, y que el módulo de pruebas (N°29) solo empieza cuando terminan comandas, pagos, puntos y cierre de caja,
**podría ocurrir que** los defectos se descubran todos juntos al final y no alcance el tiempo para corregirlos,
**lo que provocaría** que se entregue la v1.0 sin alcanzar el 70 % de cobertura de la lógica crítica o con errores en caja y comandas.

### R-06 — Conexión a Internet en la cafetería

**Debido a** que el acta restringe el sistema a funcionar con Wi-Fi y establece que la sincronización con cocina debe ser ≤ 3 s, pero aún no se ha medido la red real de CaffeBar,
**podría ocurrir que** la red de la cafetería sea inestable o lenta durante el servicio,
**lo que provocaría** que las comandas no lleguen a cocina a tiempo y que la prueba piloto no pueda cumplir los criterios de aceptación.

### R-07 — Cumplimiento de la Ley 1581 de 2012

**Debido a** que el sistema recolecta nombre, documento (cédula) y celular de los clientes y que el acta exige cumplir la Ley 1581 de 2012, pero no hay una política de tratamiento de datos ni responsable designado en el proyecto,
**podría ocurrir que** al piloto salgamos con datos personales sin una política de tratamiento aprobada o con el texto de aceptación incompleto,
**lo que provocaría** incumplimiento normativo para CaffeBar, posible sanción y que no se cumpla el objetivo específico de seguridad y cumplimiento.

### R-08 — Información del cliente para configurar el sistema

**Debido a** que las suposiciones del acta dependen de que Pepito Pérez entregue oportunamente productos, precios, promociones y reglas de fidelización, y de que no hay una fecha límite acordada para esa entrega,
**podría ocurrir que** los datos lleguen tarde o incompletos,
**lo que provocaría** que no se pueda cargar el menú real ni configurar la fidelización antes del piloto.

### R-09 — Alcance amplio frente al tiempo disponible

**Debido a** que el acta compromete siete funcionalidades con 31 entregables y que el documento de requerimientos ya tiene más de 50 requisitos funcionales (incluyendo notificaciones push, acceso remoto y promociones),
**podría ocurrir que** el equipo no alcance a implementar todo con calidad en el plazo,
**lo que provocaría** que se entreguen módulos incompletos o se recorte alcance sin acordarlo antes con el cliente.

---

## 3. Riesgos tecnológicos

> Las causas de R-10 a R-12 parten de que el equipo no domina estas tecnologías (dato aportado por el gerente). Conviene respaldarlas con evidencia, por ejemplo una encuesta corta de experiencia por integrante, antes de dar el plan por cerrado.

### R-10 — Falta de conocimiento en Spring Boot

**Debido a** que el backend se construye con Spring Boot, que el equipo de backend (Diego Gómez y Diego Bolaños) no tiene experiencia previa con este framework, y que la configuración de la arquitectura (8.1.1) es el primer entregable de la ruta crítica, con 3 días y sin holgura,
**podría ocurrir que** la curva de aprendizaje alargue la configuración de la arquitectura, la autenticación y el control de acceso por rol,
**lo que provocaría** que se retrase toda la ruta crítica, porque autenticación (2.1.1) y roles (2.3.1) dependen de ese entregable.

### R-11 — Falta de conocimiento en STOMP/SockJS y sincronización en tiempo real

**Debido a** que la comunicación entre meseros y cocina se basa en STOMP sobre SockJS, que el entregable de sincronización en tiempo real (8.2.1) tiene solo 2 días y un único responsable (Diego Gómez), y que el criterio de aceptación exige ≤ 3 s en el 95 % de los casos,
**podría ocurrir que** la conexión se caiga, no se reconecte sola o supere los 3 s al haber varios dispositivos conectados,
**lo que provocaría** que las comandas lleguen tarde o no lleguen a cocina, y que se incumpla el objetivo de comunicación en tiempo real y los requisitos RF-18, RF-21, RF-25 y RF-26.

### R-12 — Despliegue en producción sin experiencia ni entorno definido

**Debido a** que el acta exige el backend en producción con HTTPS antes del 17/12/2026, que el despliegue (8.5.1) dura 3 días al final de la ruta crítica, y que el equipo no tiene experiencia desplegando y todavía no se ha elegido el hosting ni se ha registrado un costo para él,
**podría ocurrir que** surjan problemas de configuración (servidor, base de datos, certificado HTTPS, variables de entorno) o que el hosting elegido tenga un costo o limitaciones no previstas,
**lo que provocaría** que la app no esté en producción para el piloto, o que se necesite un gasto adicional no contemplado en el presupuesto.


---

## 4. Escala de probabilidad e impacto

Se usa una escala de 5 niveles para la probabilidad y otra para el impacto (1 = muy bajo, 5 = muy alto). El nivel de un riesgo es **Probabilidad × Impacto** (de 1 a 25).

### 4.1 Probabilidad

| Nivel | Categoría | Probabilidad de que ocurra antes del 17/12/2026 | Criterio orientativo |
|:-----:|-----------|:-----------------------------------------------:|----------------------|
| 1 | Muy baja | < 10 % | Solo ocurriría por una circunstancia excepcional |
| 2 | Baja | 10 % – 30 % | Puede ocurrir, pero no hay señales hoy |
| 3 | Media | 30 % – 50 % | Hay señales parciales; ocurre en proyectos parecidos |
| 4 | Alta | 50 % – 70 % | Ya hay señales claras en los documentos o en el equipo |
| 5 | Muy alta | > 70 % | Es casi seguro si no se actúa |


### 4.2 Matriz de nivel de riesgo (P × I)

Cada celda muestra el color del nivel y los riesgos ubicados en ella. El nivel de un riesgo es el producto de su probabilidad por su impacto.

| P \ I | 1 Muy bajo | 2 Bajo | 3 Medio | 4 Alto | 5 Muy alto |
|:-----:|:----------:|:------:|:-------:|:------:|:----------:|
| **5 Muy alta** | 🟡 | 🟠 | 🔴 | 🔴 | 🔴 |
| **4 Alta** | 🟢 | 🟡 | 🟠<br>**R-09** | 🔴<br>**R-02**<br>**R-10**<br>**R-11** | 🔴<br>**R-01** |
| **3 Media** | 🟢 | 🟡 | 🟡<br>**R-08** | 🟠<br>**R-03**<br>**R-04**<br>**R-05**<br>**R-07** | 🔴<br>**R-12** |
| **2 Baja** | 🟢 | 🟢 | 🟡 | 🟡<br>**R-06** | 🟠 |
| **1 Muy baja** | 🟢 | 🟢 | 🟢 | 🟢 | 🟡 |

> La ubicación de cada riesgo es una propuesta inicial, por validar con el equipo.

| Riesgo | Tema | P | I | Nivel | Clasificación |
|:------:|------|:-:|:-:|:-----:|:-------------:|
| R-01 | Plazo de la ruta crítica | 4 | 5 | 20 | 🔴 Crítico |
| R-10 | Falta de conocimiento en Spring Boot | 4 | 4 | 16 | 🔴 Crítico |
| R-11 | Falta de conocimiento en STOMP/SockJS | 4 | 4 | 16 | 🔴 Crítico |
| R-02 | Disponibilidad del equipo | 4 | 4 | 16 | 🔴 Crítico |
| R-12 | Despliegue en producción | 3 | 5 | 15 | 🔴 Crítico |
| R-09 | Alcance amplio | 4 | 3 | 12 | 🟠 Alto |
| R-03 | Concentración de la carga en Gómez | 3 | 4 | 12 | 🟠 Alto |
| R-04 | Módulo de caja sin holgura | 3 | 4 | 12 | 🟠 Alto |
| R-05 | Pruebas con un solo tester | 3 | 4 | 12 | 🟠 Alto |
| R-07 | Ley 1581 de 2012 | 3 | 4 | 12 | 🟠 Alto |
| R-08 | Información del cliente | 3 | 3 | 9 | 🟡 Medio |
| R-06 | Conexión a Internet | 2 | 4 | 8 | 🟡 Medio |

### 4.3 Clasificación y qué se hace en cada nivel

| Puntaje | Nivel | Tratamiento |
|:-------:|-------|-------------|
| 1 – 4 | 🟢 Bajo | Se acepta y se revisa en el seguimiento quincenal |
| 5 – 9 | 🟡 Medio | Se asigna responsable y se vigila el evento cada semana |
| 10 – 14 | 🟠 Alto | Plan de respuesta obligatorio y revisión en cada reunión de seguimiento |
| 15 – 25 | 🔴 Crítico | Plan de respuesta inmediato, reserva de contingencia y aviso al patrocinador |
---

## 5. Costo esperado y respuesta a los riesgos críticos

El análisis se hace solo con los riesgos en rojo (🔴 Crítico): **R-01, R-02, R-10, R-11 y R-12**. Los demás se vigilan en el seguimiento según el nivel de la sección 4.3.

### 5.1 Método

Para cada riesgo se comparan dos opciones:

| Opción | Costo esperado |
|--------|----------------|
| No hacer nada | Probabilidad × Impacto |
| Mitigar | (Probabilidad reducida × Impacto) + Costo de mitigar |

Se elige la opción con menor costo esperado. Si mitigar cuesta más que el riesgo, lo legítimo es aceptarlo y dejarlo escrito.

**Unidad:** horas-persona. Todavía no hay presupuesto ni tarifa por hora; al hacer el presupuesto se multiplican estas horas por la tarifa que se defina. Los gastos directos en pesos (p. ej. hosting) se anotan aparte.

**Referencia:** el esfuerzo total planeado en el cronograma es de **371 h** (suma de los 31 entregables).

**Probabilidad:** se usa el punto medio del rango de cada nivel de la sección 4.1: nivel 4 = 60 %, nivel 3 = 40 %.

### 5.2 Impacto en horas-persona (supuestos)

> Todas las cifras de esta tabla son supuestos del gerente, por validar con el equipo.

| Riesgo | Nivel P / I | P | Impacto (h) | Cómo se calculó |
|:------:|:-----------:|:--:|:-----------:|-----------------|
| R-01 | 4 / 5 | 60 % | 160 | ≈ 8 días hábiles de retraso (hasta el ~23-29/12 según festivos) × 5 personas × 4 h |
| R-02 | 4 / 4 | 60 % | 90 | Capacidad perdida: 1 de cada 4 h/día durante ~18 días hábiles de parciales y entregas × 5 personas |
| R-10 | 4 / 4 | 60 % | 80 | 5 días de retraso en 8.1.1 × 4 personas bloqueadas (los demás entregables dependen de él) × 4 h |
| R-11 | 4 / 4 | 60 % | 64 | Retrabajo de la sincronización (8.2.1) y de los módulos que la usan: 8 días × 2 personas × 4 h |
| R-12 | 3 / 5 | 40 % | 120 | Despliegue de emergencia y repetición de la validación: 10 días × 3 personas × 4 h (más el hosting en pesos, pendiente) |

### 5.3 Comparación: no hacer nada frente a mitigar

| Riesgo | Costo esperado sin hacer nada (h) | P reducida | Riesgo residual (h) | Costo de mitigar (h) | Costo esperado mitigando (h) | Ahorro (h) | Decisión |
|:------:|:---:|:---:|:---:|:---:|:---:|:---:|----------|
| R-01 | 96,0 | 30 % | 48,0 | 32 | **80,0** | 16,0 | Mitigar y escalar |
| R-02 | 54,0 | 35 % | 31,5 | 12 | **43,5** | 10,5 | Mitigar |
| R-10 | 48,0 | 25 % | 20,0 | 16 | **36,0** | 12,0 | Mitigar |
| R-11 | 38,4 | 25 % | 16,0 | 16 | **32,0** | 6,4 | Mitigar |
| R-12 | 48,0 | 15 % | 18,0 | 20 | **38,0** | 10,0 | Transferir y mitigar |
| **Total** | **284,4** | | **133,5** | **96** | **229,5** | **54,9** | |

En los cinco riesgos mitigar cuesta menos que no hacer nada. El ahorro de R-11 es el más pequeño (6,4 h), así que si el equipo necesita recortar esfuerzo, esa mitigación es la primera que se puede reducir.

### 5.4 Respuesta a cada riesgo crítico

| Riesgo | Tipo de respuesta | Acciones | Costo (h) | Responsable | Disparador |
|:------:|-------------------|----------|:---------:|-------------|------------|
| R-01 | **Mitigar** + **Escalar** | Recalcular el cronograma con el inicio real (28/10) y los festivos; paralelizar lo que tiene holgura; si la fecha de fin proyectada supera el 17/12, escalar al docente y al patrocinador para acordar fecha o recorte de alcance (p. ej. 7.4.1 promociones), y registrar que se escaló | 32 | Felipe | Fecha de fin recalculada > 17/12, o cualquier retraso en un entregable de la ruta crítica |
| R-02 | **Mitigar** | Pedir a cada integrante su calendario de parciales y entregas; adelantar trabajo antes de esas semanas; reasignar en la reunión de seguimiento | 12 | Felipe | Un integrante informa que no cumplirá las 4 h/día, o un entregable crítico cierra con más de 1 día de retraso |
| R-10 | **Mitigar** | Tutorial dirigido de Spring Boot para Gómez y Bolaños (8 h cada uno) antes de entregables que dependan del backend; revisión de código entre ambos | 16 | Diego Gómez | 8.1.1 o 2.1.1 con más de 1 día de retraso |
| R-11 | **Mitigar** | Prototipo corto de STOMP/SockJS con reconexión automática (8 h) y prueba de latencia con varios dispositivos (8 h) antes de dar 8.2.1 por terminado | 16 | Diego Gómez | Prueba de latencia > 3 s o desconexiones sin reconexión |
| R-12 | **Transferir** + **Mitigar** | Elegir un hosting gestionado que ya entregue HTTPS y base de datos configurados (transfiere esa parte al proveedor) y hacer un despliegue de prueba temprano, antes de 8.5.1 | 20 + hosting | Felipe y Diego Gómez | Hosting sin elegir al 15/11, o despliegue de prueba fallido |

### 5.5 Reserva de contingencia

La reserva de contingencia se calcula con el costo esperado de los riesgos residuales: **133,5 h** (≈ 36 % de las 371 h planeadas). El costo de las mitigaciones (**96 h**) es trabajo adicional que debe quedar en el cronograma y en el presupuesto. Ambos valores pasan al presupuesto, donde se convierten a pesos con la tarifa que se defina.
