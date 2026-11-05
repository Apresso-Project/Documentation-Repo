# PLAN DE CALIDAD — APPRESSO

> **Estado:** borrador v0.2 (4 de noviembre de 2026).
> **Responsable:** Felipe Salcedo (gerente del proyecto).
> **Fuentes:** criterios de éxito del acta de constitución (objetivos específicos 1, 3, 4 y 6), requerimientos no funcionales y [Seguimiento de Riesgos](Seguimiento%20de%20Riesgos%20Appresso.md).

## 1. Objetivo y alcance

Asegurar que Appresso v1.0 cumpla los criterios de éxito del acta y que los defectos se detecten cuando aparecen, no al final del proyecto.

El plan define **cuatro atributos de calidad**. De ellos, **el equipo se compromete a aplicar como práctica dos: corrección funcional y revisión entre pares**. Los otros dos (rendimiento en tiempo real y seguridad y control de acceso) quedan como estándares que se verifican en el módulo de pruebas (8.3.1) y en el piloto, sin seguimiento propio en cada reunión.

Otros requisitos (usabilidad, compatibilidad con Android 8.0, copias de seguridad, disponibilidad del 99 %) también se verifican en 8.3.1 y en el piloto.

---

## 2. Atributos de calidad

| Atributo | Estándar | Cómo se verifica | Quién y cuándo | Si falla |
|----------|----------|------------------|----------------|----------|
| **1. Corrección funcional** ✅ *práctica comprometida* | Saldo final = saldo inicial + ingresos − egresos. Efectivo y transferencia nunca se mezclan. Exactamente 1 punto por pago confirmado. Un pago no se cuenta dos veces. Cobertura ≥ 70 % de la lógica crítica. | Pruebas unitarias automatizadas, una prueba de integración del flujo comanda → cocina → pago → puntos, y la herramienta de cobertura. | Cada desarrollador escribe las pruebas junto con su módulo. David las ejecuta cuando recibe cada entregable, y se repiten en 8.3.1. | Un defecto que incumpla el estándar detiene el cierre del entregable y no se avanza al siguiente de la cadena de caja. Si la cobertura está por debajo de 70 % al terminar comandas y pagos, se registra en R-05 y se reasignan horas. |
| **2. Rendimiento en tiempo real** | Comanda en cocina en ≤ 3 s en el 95 % de los casos. Menú, pagos e inventario en ≤ 2 s. 30 dispositivos conectados a la vez. | Prueba de latencia con varios dispositivos y carga básica, repetida en el Wi-Fi de CaffeBar. | Diego Gómez al terminar 8.2.1. David lo repite en 8.3.1 y en CaffeBar antes del piloto. | Si supera 3 s, se optimiza antes de dar 8.2.1 por terminado. Si el problema es la red de la cafetería, se escala a Pepito Pérez (R-06). Todo queda en el seguimiento de riesgos (R-11). |
| **3. Seguridad y control de acceso** | Todo acceso no autorizado devuelve 403 en los 5 roles. Contraseñas con hash, HTTPS y tokens en Android Keystore. El registro exige aceptar el tratamiento de datos (Ley 1581). | Prueba con un usuario de cada rol, lista de chequeo de código y configuración, y prueba del formulario de registro. | David prueba los roles al terminar 2.3.1 y otra vez en 8.3.1. Gómez, Sebastián y David revisan hash, HTTPS y Keystore en 8.4.1, antes del despliegue. | Una falla de seguridad impide el despliegue y el piloto hasta corregirla. Si falta la política de datos, se escala a Pepito Pérez (R-07). |
| **4. Revisión entre pares** ✅ *práctica comprometida* | Ningún cambio llega a la rama principal sin que otro integrante lo revise. En backend, Gómez y Bolaños se revisan entre sí. El código compila y pasa las pruebas antes de integrarse. | Historial de solicitudes de integración del repositorio: cada una debe tener una aprobación. | El autor pide la revisión al terminar cada entregable. Felipe revisa el historial en cada reunión de seguimiento. | Un cambio sin revisión se revierte o se revisa de inmediato. Si se repite, se asigna un revisor fijo por módulo y se anota en R-10 y R-03. |

---

## 3. Definición de terminado

Un entregable se da por terminado solo si cumple las cinco condiciones:

1. Cumple su criterio de aceptación, el que se escribió antes de empezar.
2. Tiene pruebas y pasan.
3. Otra persona lo revisó y lo aprobó.
4. Está integrado en la rama principal.
5. Está desplegado donde alguien lo pueda ver funcionando.

> La condición 5 depende de tener un entorno donde desplegar desde temprano. Es la misma acción que la respuesta al riesgo R-12 (elegir hosting y hacer un despliegue de prueba temprano).

---

## 4. Seguimiento

**Quién registra:** Felipe Salcedo, gerente del proyecto.

En cada reunión de seguimiento, Felipe revisa y registra:

| Práctica comprometida | Qué se revisa | Dónde se registra |
|-----------------------|---------------|-------------------|
| Corrección funcional | Cobertura de pruebas sobre la lógica crítica (meta ≥ 70 %); pruebas del flujo de caja y de puntos en verde | [Seguimiento de riesgos](Seguimiento%20de%20Riesgos%20Appresso.md): R-04 y R-05 |
| Revisión entre pares | Que cada cambio integrado tenga una aprobación en el historial del repositorio | [Seguimiento de riesgos](Seguimiento%20de%20Riesgos%20Appresso.md): R-03 y R-10 |
| Definición de terminado | Que cada entregable cerrado cumpla las cinco condiciones | Registro de reuniones del seguimiento de riesgos |

Si algo no cumple, Felipe lo registra y se actúa según la columna "Si falla" de la tabla de la sección 2.

