# Cronograma — Appresso

## Parámetros del cronograma

| Parámetro | Valor |
|-----------|-------|
| Fecha de inicio (día 0) | **Miércoles 28 oct 2026** (inicio real del desarrollo) |
| Fin planificado | **Sábado 12 dic 2026** (día 46, CC-03) |
| Fecha límite de entrega del curso | **Martes 15 dic 2026** |
| Festivos descontados | **Ninguno**: domingos y festivos son días de trabajo (CC-02) |
| Calendario | **Lunes a domingo** (7 días/semana) |
| Dedicación diaria | 4 h/día |
| Regla de conversión | Duración (d) = ⌈Esfuerzo (h) ÷ 4⌉ — redondeo al alza al día entero |
| Tipo de dependencia | Fin-a-Inicio (FS) por defecto — PMBOK |

> **Cambio CC-01 (aprobado el 15/11/2026):** el cronograma original usaba el 29/09/2026 como día 0. Se corrigió al 28/10/2026, fecha real de inicio del desarrollo. La secuencia, las duraciones y las dependencias no cambian; solo las fechas del calendario. Registro en [Métricas de Proyecto](Métricas%20de%20Proyecto%20Appresso.md), sección 2.4.

> **Cambio CC-02 (17/11/2026):** por el plan de acción aprobado el 16/11, domingos y festivos pasan a ser días de trabajo (calendario de lunes a domingo, sin festivos descontados). La secuencia, las duraciones y las dependencias no cambian; los 49 días de la ruta crítica terminan el 15/12/2026 (antes, 28/12), que es la nueva fecha de entrega del curso. Registro en [Métricas de Proyecto](Métricas%20de%20Proyecto%20Appresso.md), sección 2.4.

> **Cambio CC-03 (21/11/2026):** el recorte retira una actividad crítica de 3 días. El cierre de caja (6.5.1) pasa a depender directamente de 6.3.2. Se acuerda iniciar los despliegues internos continuos con Render y Neon en paralelo al desarrollo. El paquete 8.5.1 conserva el despliegue de la v1.0 en producción y la documentación técnica al final. Ver [registro del cambio](Métricas%20de%20Proyecto%20Appresso.md#24-registro-de-cambios-a-las-líneas-base).

---

## Parte 1 — Lista de entregables y duraciones

> Cada entregable vigente del Diccionario de la EDT corresponde a una actividad del cronograma. Se conservan los números de actividad de los paquetes vigentes para mantener la trazabilidad.

### Bloque 1 — Gestión del proyecto

| N° | Código | Nombre del entregable | Responsable | Esfuerzo (h) | Duración (d) |
|----|--------|-----------------------|-------------|:------------:|:------------:|
| 1  | 1.1.1  | Documentos de inicio y planificación estructural | Felipe | 13 | 4 |
| 2  | 1.2.1  | Plan temporal, económico y de riesgos | Felipe | 12 | 3 |
| 3  | 1.3.1  | Seguimiento, control y cierre del proyecto | Felipe | 14 | 4 |

### Bloque 2 — Gestión de usuarios y permisos

| N° | Código | Nombre del entregable | Responsable | Esfuerzo (h) | Duración (d) |
|----|--------|-----------------------|-------------|:------------:|:------------:|
| 4  | 2.1.1  | Módulo de autenticación | Stiven + Bolaños | 10 | 3 |
| 5  | 2.2.1  | Módulo de administración de usuarios | Stiven + Bolaños | 10 | 3 |
| 6  | 2.3.1  | Control de acceso por rol y acceso remoto del administrador | Bolaños + Stiven | 16 | 4 |

### Bloque 3 — Catálogo e inventario

| N° | Código | Nombre del entregable | Responsable | Esfuerzo (h) | Duración (d) |
|----|--------|-----------------------|-------------|:------------:|:------------:|
| 7  | 3.1.1  | Módulo de gestión de productos y categorías | Sebastián + Gómez | 14 | 4 |
| 8  | 3.2.1  | Módulo de control de existencias | Gómez + Sebastián | 14 | 4 |
| 9  | 3.3.1  | Módulo de consulta del menú y visualización en cocina | Sebastián + Gómez | 14 | 4 |

### Bloque 4 — Comandas y pedidos

| N° | Código | Nombre del entregable | Responsable | Esfuerzo (h) | Duración (d) |
|----|--------|-----------------------|-------------|:------------:|:------------:|
| 10 | 4.1.1  | Módulo de creación de comandas | Stiven + Bolaños | 18 | 5 |
| 11 | 4.2.1  | Módulo de envío, consulta y vinculación de clientes | Stiven + Bolaños | 12 | 3 |
| 12 | 4.2.2  | Módulo de modificación y cancelación de pedidos | Bolaños + Stiven | 12 | 3 |

### Bloque 5 — Pantalla de cocina

| N° | Código | Nombre del entregable | Responsable | Esfuerzo (h) | Duración (d) |
|----|--------|-----------------------|-------------|:------------:|:------------:|
| 13 | 5.1.1  | Módulo de visualización de pedidos en cocina | Sebastián + Gómez | 12 | 3 |
| 14 | 5.2.1  | Módulo de gestión de estados y notificación al mesero | Gómez + Sebastián | 8 | 2 |

### Bloque 6 — Módulo de caja

| N° | Código | Nombre del entregable | Responsable | Esfuerzo (h) | Duración (d) |
|----|--------|-----------------------|-------------|:------------:|:------------:|
| 15 | 6.1.1  | Módulo de registro de pagos | Stiven + Bolaños | 10 | 3 |
| 16 | 6.2.1  | Módulo de gestión de transferencias QR | Stiven + Bolaños | 14 | 4 |
| 17 | 6.3.1  | Módulo de ingresos y retiros directos | Bolaños + Stiven | 8 | 2 |
| 18 | 6.3.2  | Módulo de solicitudes de retiro, aprobación y trazabilidad | Stiven + Bolaños | 16 | 4 |
| 20 | 6.5.1  | Módulo de cierre de caja y cálculo de totales | Bolaños + Stiven | 10 | 3 |
| 21 | 6.5.2  | Módulo de informe de cierre y apertura de jornada | Bolaños + Stiven | 10 | 3 |

### Bloque 7 — Fidelización de clientes

| N° | Código | Nombre del entregable | Responsable | Esfuerzo (h) | Duración (d) |
|----|--------|-----------------------|-------------|:------------:|:------------:|
| 22 | 7.1.1  | Módulo de registro y búsqueda de clientes | Sebastián + Gómez | 8 | 2 |
| 23 | 7.2.1  | Módulo de acumulación y configuración de puntos de fidelidad | Gómez + Sebastián | 12 | 3 |
| 24 | 7.2.2  | Módulo de consulta de puntos | Sebastián | 8 | 2 |
| 25 | 7.3.1  | Módulo de recompensas y canjes | Sebastián + Gómez | 14 | 4 |
| 26 | 7.4.1  | Módulo de promociones y notificaciones de fidelización | Gómez + Sebastián | 16 | 4 |

### Bloque 8 — Infraestructura y calidad

| N° | Código | Nombre del entregable | Responsable | Esfuerzo (h) | Duración (d) |
|----|--------|-----------------------|-------------|:------------:|:------------:|
| 27 | 8.1.1  | Módulo de configuración de arquitectura del proyecto | Gómez + Sebastián | 12 | 3 |
| 28 | 8.2.1  | Módulo de sincronización en tiempo real | Gómez | 8 | 2 |
| 29 | 8.3.1  | Módulo de pruebas | Gómez + Stiven | 16 | 4 |
| 30 | 8.4.1  | Módulo de seguridad y cumplimiento normativo | Gómez + Sebastián + David | 10 | 3 |
| 31 | 8.5.1  | Módulo de despliegue y documentación técnica | Gómez + Felipe | 10 | 3 |

### Resumen Parte 1

| Concepto | Valor |
|----------|-------|
| Total de entregables | 30 |
| Entregables de 2 días (8 h) | 5 |
| Entregables de 3 días (9–12 h) | 13 |
| Entregables de 4 días (13–16 h) | 11 |
| Entregables de 5 días (17–20 h) | 1 |
| Suma de duraciones (secuencial puro) | 98 días |
| Semanas equivalentes (secuencial puro) | 14 semanas |

> Los 98 días representan la duración total si todos los entregables se desarrollaran en serie. Las partes 3 y 4 calculan la duración planificada con las dependencias y el trabajo en paralelo.

---

## Parte 2 — Declaración de dependencias

> Tipo de dependencia: **Fin-a-Inicio (FS)** en todos los casos.  
> Formato del predecesor: `N° (Código)`. Las actividades sin predecesor son nodos de inicio del proyecto.  
> ⚠️ **N°3 (1.3.1):** aunque los informes periódicos y el control de cambios ocurren durante todo el proyecto, el entregable se considera completo al firmar el acta de cierre, que ocurre tras el despliegue técnico (N°31).

### Bloque 1 — Gestión del proyecto

| N° | Código | Nombre del entregable | Predecesores |
|----|--------|-----------------------|--------------|
| 1  | 1.1.1  | Documentos de inicio y planificación estructural | — |
| 2  | 1.2.1  | Plan temporal, económico y de riesgos | 1 (1.1.1) |
| 3  | 1.3.1  | Seguimiento, control y cierre del proyecto | 31 (8.5.1) ⚠️ |

### Bloque 2 — Gestión de usuarios y permisos

| N° | Código | Nombre del entregable | Predecesores |
|----|--------|-----------------------|--------------|
| 4  | 2.1.1  | Módulo de autenticación | 27 (8.1.1) |
| 5  | 2.2.1  | Módulo de administración de usuarios | 4 (2.1.1) |
| 6  | 2.3.1  | Control de acceso por rol y acceso remoto del administrador | 4 (2.1.1) |

### Bloque 3 — Catálogo e inventario

| N° | Código | Nombre del entregable | Predecesores |
|----|--------|-----------------------|--------------|
| 7  | 3.1.1  | Módulo de gestión de productos y categorías | 6 (2.3.1) |
| 8  | 3.2.1  | Módulo de control de existencias | 7 (3.1.1) |
| 9  | 3.3.1  | Módulo de consulta del menú y visualización en cocina | 7 (3.1.1), 28 (8.2.1) |

### Bloque 4 — Comandas y pedidos

| N° | Código | Nombre del entregable | Predecesores |
|----|--------|-----------------------|--------------|
| 10 | 4.1.1  | Módulo de creación de comandas | 9 (3.3.1) |
| 11 | 4.2.1  | Módulo de envío, consulta y vinculación de clientes | 10 (4.1.1), 22 (7.1.1) |
| 12 | 4.2.2  | Módulo de modificación y cancelación de pedidos | 10 (4.1.1), 8 (3.2.1) |

### Bloque 5 — Pantalla de cocina

| N° | Código | Nombre del entregable | Predecesores |
|----|--------|-----------------------|--------------|
| 13 | 5.1.1  | Módulo de visualización de pedidos en cocina | 10 (4.1.1), 28 (8.2.1) |
| 14 | 5.2.1  | Módulo de gestión de estados y notificación al mesero | 13 (5.1.1) |

### Bloque 6 — Módulo de caja

| N° | Código | Nombre del entregable | Predecesores |
|----|--------|-----------------------|--------------|
| 15 | 6.1.1  | Módulo de registro de pagos | 10 (4.1.1) |
| 16 | 6.2.1  | Módulo de gestión de transferencias QR | 15 (6.1.1) |
| 17 | 6.3.1  | Módulo de ingresos y retiros directos | 15 (6.1.1) |
| 18 | 6.3.2  | Módulo de solicitudes de retiro, aprobación y trazabilidad | 17 (6.3.1) |
| 20 | 6.5.1  | Módulo de cierre de caja y cálculo de totales | 18 (6.3.2) |
| 21 | 6.5.2  | Módulo de informe de cierre y apertura de jornada | 20 (6.5.1) |

### Bloque 7 — Fidelización de clientes

| N° | Código | Nombre del entregable | Predecesores |
|----|--------|-----------------------|--------------|
| 22 | 7.1.1  | Módulo de registro y búsqueda de clientes | 6 (2.3.1) |
| 23 | 7.2.1  | Módulo de acumulación y configuración de puntos de fidelidad | 11 (4.2.1), 15 (6.1.1) |
| 24 | 7.2.2  | Módulo de consulta de puntos | 23 (7.2.1) |
| 25 | 7.3.1  | Módulo de recompensas y canjes | 24 (7.2.2), 10 (4.1.1) |
| 26 | 7.4.1  | Módulo de promociones y notificaciones de fidelización | 24 (7.2.2) |

### Bloque 8 — Infraestructura y calidad

| N° | Código | Nombre del entregable | Predecesores |
|----|--------|-----------------------|--------------|
| 27 | 8.1.1  | Módulo de configuración de arquitectura del proyecto | — |
| 28 | 8.2.1  | Módulo de sincronización en tiempo real | 27 (8.1.1) |
| 29 | 8.3.1  | Módulo de pruebas | 10 (4.1.1), 15 (6.1.1), 23 (7.2.1), 20 (6.5.1) |
| 30 | 8.4.1  | Módulo de seguridad y cumplimiento normativo | 22 (7.1.1) |
| 31 | 8.5.1  | Módulo de despliegue y documentación técnica | 29 (8.3.1) |

---

## Parte 3 — Recorridos (adelante y atrás)

> **Convención:** ES = 0 para nodos de inicio. EF = ES + d. LS = LF − d. TF = LS − ES = LF − EF.  
> **Recorrido adelante:** ES de cada actividad = max(EF de todas sus predecesoras).  
> **Recorrido atrás:** LF de actividades terminales = duración total del proyecto (46 d). LF de cada actividad = min(LS de todas sus sucesoras).
>
> **★** = actividad en la ruta crítica (TF = 0).

### Tabla de recorridos

| N° | Código | d | ES | EF | LS | LF | TF | RC |
|----|--------|:-:|:--:|:--:|:--:|:--:|:--:|:--:|
| 1  | 1.1.1  | 4 | 0  | 4  | 39 | 43 | 39 |    |
| 2  | 1.2.1  | 3 | 4  | 7  | 43 | 46 | 39 |    |
| 3  | 1.3.1  | 4 | 42 | 46 | 42 | 46 | 0  | ★  |
| 4  | 2.1.1  | 3 | 3  | 6  | 3  | 6  | 0  | ★  |
| 5  | 2.2.1  | 3 | 6  | 9  | 43 | 46 | 37 |    |
| 6  | 2.3.1  | 4 | 6  | 10 | 6  | 10 | 0  | ★  |
| 7  | 3.1.1  | 4 | 10 | 14 | 10 | 14 | 0  | ★  |
| 8  | 3.2.1  | 4 | 14 | 18 | 39 | 43 | 25 |    |
| 9  | 3.3.1  | 4 | 14 | 18 | 14 | 18 | 0  | ★  |
| 10 | 4.1.1  | 5 | 18 | 23 | 18 | 23 | 0  | ★  |
| 11 | 4.2.1  | 3 | 23 | 26 | 29 | 32 | 6  |    |
| 12 | 4.2.2  | 3 | 23 | 26 | 43 | 46 | 20 |    |
| 13 | 5.1.1  | 3 | 23 | 26 | 41 | 44 | 18 |    |
| 14 | 5.2.1  | 2 | 26 | 28 | 44 | 46 | 18 |    |
| 15 | 6.1.1  | 3 | 23 | 26 | 23 | 26 | 0  | ★  |
| 16 | 6.2.1  | 4 | 26 | 30 | 42 | 46 | 16 |    |
| 17 | 6.3.1  | 2 | 26 | 28 | 26 | 28 | 0  | ★  |
| 18 | 6.3.2  | 4 | 28 | 32 | 28 | 32 | 0  | ★  |
| 20 | 6.5.1  | 3 | 32 | 35 | 32 | 35 | 0  | ★  |
| 21 | 6.5.2  | 3 | 35 | 38 | 43 | 46 | 8  |    |
| 22 | 7.1.1  | 2 | 10 | 12 | 27 | 29 | 17 |    |
| 23 | 7.2.1  | 3 | 26 | 29 | 32 | 35 | 6  |    |
| 24 | 7.2.2  | 2 | 29 | 31 | 40 | 42 | 11 |    |
| 25 | 7.3.1  | 4 | 31 | 35 | 42 | 46 | 11 |    |
| 26 | 7.4.1  | 4 | 31 | 35 | 42 | 46 | 11 |    |
| 27 | 8.1.1  | 3 | 0  | 3  | 0  | 3  | 0  | ★  |
| 28 | 8.2.1  | 2 | 3  | 5  | 12 | 14 | 9  |    |
| 29 | 8.3.1  | 4 | 35 | 39 | 35 | 39 | 0  | ★  |
| 30 | 8.4.1  | 3 | 12 | 15 | 43 | 46 | 31 |    |
| 31 | 8.5.1  | 3 | 39 | 42 | 39 | 42 | 0  | ★  |

---

## Parte 4 — Ruta crítica

### 4.1 Identificación

La ruta crítica es la **cadena continua de entregables con TF = 0** que va del inicio al fin del proyecto. Cualquier retraso en uno de ellos retrasa la fecha de entrega en la misma cantidad de días.

**Duración total del proyecto: 46 días de trabajo**

```
N°27 → N°4 → N°6 → N°7 → N°9 → N°10 → N°15 → N°17 → N°18 → N°20 → N°29 → N°31 → N°3
```

### 4.2 Tabla de la ruta crítica

| N° | Código | Nombre del entregable | d | ES | EF | LS | LF | TF |
|----|--------|-----------------------|:-:|:--:|:--:|:--:|:--:|:--:|
| 27 | 8.1.1  | Módulo de configuración de arquitectura del proyecto | 3 | 0  | 3  | 0  | 3  | 0 |
| 4  | 2.1.1  | Módulo de autenticación | 3 | 3  | 6  | 3  | 6  | 0 |
| 6  | 2.3.1  | Control de acceso por rol y acceso remoto del administrador | 4 | 6  | 10 | 6  | 10 | 0 |
| 7  | 3.1.1  | Módulo de gestión de productos y categorías | 4 | 10 | 14 | 10 | 14 | 0 |
| 9  | 3.3.1  | Módulo de consulta del menú y visualización en cocina | 4 | 14 | 18 | 14 | 18 | 0 |
| 10 | 4.1.1  | Módulo de creación de comandas | 5 | 18 | 23 | 18 | 23 | 0 |
| 15 | 6.1.1  | Módulo de registro de pagos | 3 | 23 | 26 | 23 | 26 | 0 |
| 17 | 6.3.1  | Módulo de ingresos y retiros directos | 2 | 26 | 28 | 26 | 28 | 0 |
| 18 | 6.3.2  | Módulo de solicitudes de retiro, aprobación y trazabilidad | 4 | 28 | 32 | 28 | 32 | 0 |
| 20 | 6.5.1  | Módulo de cierre de caja y cálculo de totales | 3 | 32 | 35 | 32 | 35 | 0 |
| 29 | 8.3.1  | Módulo de pruebas | 4 | 35 | 39 | 35 | 39 | 0 |
| 31 | 8.5.1  | Módulo de despliegue y documentación técnica | 3 | 39 | 42 | 39 | 42 | 0 |
| 3  | 1.3.1  | Seguimiento, control y cierre del proyecto | 4 | 42 | 46 | 42 | 46 | 0 |

**13 entregables críticos de 30 (43 % del total) — suma de duraciones: 46 días**

### 4.3 Entregables quasi-críticos (holgura baja)

Estos entregables no están en la ruta crítica pero tienen poco margen; un retraso moderado puede crear una segunda ruta crítica.

| TF | N° | Código | Nombre |
|:--:|----|--------|--------|
| 6  | 11 | 4.2.1  | Módulo de envío, consulta y vinculación de clientes |
| 6  | 23 | 7.2.1  | Módulo de acumulación y configuración de puntos |
| 8  | 21 | 6.5.2  | Módulo de informe de cierre y apertura de jornada |
| 9  | 28 | 8.2.1  | Módulo de sincronización en tiempo real |

### 4.4 Conclusiones para la gestión del proyecto

1. **La ruta crítica sigue pasando íntegramente por el backend.** Los tres primeros entregables críticos (N°27, 4, 6) son de configuración, autenticación y control de acceso. Cualquier retraso en la puesta en marcha de la arquitectura bloquea todo el desarrollo posterior.

2. **Caja concentra cuatro entregables críticos** (N°15, 17, 18 y 20). La cadena de pagos, ingresos y retiros, solicitudes y cierre de caja ocupa 12 días sin holgura (ES 23 a EF 35).

3. **El módulo de pruebas es el cuello de botella final.** N°29 solo puede iniciar cuando terminen el módulo de creación de comandas (N°10), el registro de pagos (N°15), la acumulación de puntos (N°23) y el cierre de caja (N°20). El bloque de pruebas, despliegue de producción y cierre (N°29, 31 y 3) ocupa del ES 35 al EF 46, sin holgura.

4. **El frontend tiene holgura amplia.** N°5 (TF=37), N°12 (TF=20), N°13 y N°14 (TF=18), lo que permite priorizar el backend en las primeras semanas sin comprometer la fecha de entrega.

5. **N°11 y N°23 tienen la menor holgura fuera de la ruta crítica (TF=6).** El informe de cierre y apertura de jornada (N°21) mantiene 8 días de holgura y depende directamente del cierre de caja.

6. **La documentación de gestión (N°1 y N°2) tiene la holgura máxima (TF=39)**, lo que permite al gerente completarla de forma incremental durante casi todo el proyecto sin afectar la entrega técnica.
