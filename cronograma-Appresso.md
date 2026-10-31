# Cronograma — Appresso

## Parámetros del cronograma

| Parámetro | Valor |
|-----------|-------|
| Fecha de inicio | Martes 29 sep 2026 |
| Calendario | Lunes a sábado (6 días hábiles/semana) |
| Dedicación diaria | 4 h/día |
| Regla de conversión | Duración (d) = ⌈Esfuerzo (h) ÷ 4⌉ — redondeo al alza al día entero |
| Tipo de dependencia | Fin-a-Inicio (FS) por defecto — PMBOK |

---

## Parte 1 — Lista de entregables y duraciones

> Cada entregable del Diccionario de la EDT corresponde a una actividad de cronograma (1 entregable = 1 actividad).

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
| 19 | 6.4.1  | Módulo de consultas financieras | Bolaños + Stiven | 10 | 3 |
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
| Total de entregables | 31 |
| Entregables de 2 días (8 h) | 5 |
| Entregables de 3 días (9–12 h) | 14 |
| Entregables de 4 días (13–16 h) | 11 |
| Entregables de 5 días (17–20 h) | 1 |
| Suma de duraciones (secuencial puro) | 101 días |
| Semanas equivalentes (secuencial puro) | ≈ 16.8 semanas |

> El valor de 101 días es únicamente de referencia: representa la duración total **si todos los entregables se desarrollaran en serie**. El CPM en las Partes 3 y 4 calculará la duración real considerando la paralelización permitida por las dependencias.

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
| 19 | 6.4.1  | Módulo de consultas financieras | 18 (6.3.2) |
| 20 | 6.5.1  | Módulo de cierre de caja y cálculo de totales | 19 (6.4.1) |
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
> **Recorrido atrás:** LF de actividades terminales = duración total del proyecto (49 d). LF de cada actividad = min(LS de todas sus sucesoras).  
> **★** = actividad en la ruta crítica (TF = 0).

### Tabla de recorridos

| N° | Código | d | ES | EF | LS | LF | TF | RC |
|----|--------|:-:|:--:|:--:|:--:|:--:|:--:|:--:|
| 1  | 1.1.1  | 4 | 0  | 4  | 42 | 46 | 42 |    |
| 2  | 1.2.1  | 3 | 4  | 7  | 46 | 49 | 42 |    |
| 3  | 1.3.1  | 4 | 45 | 49 | 45 | 49 | 0  | ★  |
| 4  | 2.1.1  | 3 | 3  | 6  | 3  | 6  | 0  | ★  |
| 5  | 2.2.1  | 3 | 6  | 9  | 46 | 49 | 40 |    |
| 6  | 2.3.1  | 4 | 6  | 10 | 6  | 10 | 0  | ★  |
| 7  | 3.1.1  | 4 | 10 | 14 | 10 | 14 | 0  | ★  |
| 8  | 3.2.1  | 4 | 14 | 18 | 42 | 46 | 28 |    |
| 9  | 3.3.1  | 4 | 14 | 18 | 14 | 18 | 0  | ★  |
| 10 | 4.1.1  | 5 | 18 | 23 | 18 | 23 | 0  | ★  |
| 11 | 4.2.1  | 3 | 23 | 26 | 32 | 35 | 9  |    |
| 12 | 4.2.2  | 3 | 23 | 26 | 46 | 49 | 23 |    |
| 13 | 5.1.1  | 3 | 23 | 26 | 44 | 47 | 21 |    |
| 14 | 5.2.1  | 2 | 26 | 28 | 47 | 49 | 21 |    |
| 15 | 6.1.1  | 3 | 23 | 26 | 23 | 26 | 0  | ★  |
| 16 | 6.2.1  | 4 | 26 | 30 | 45 | 49 | 19 |    |
| 17 | 6.3.1  | 2 | 26 | 28 | 26 | 28 | 0  | ★  |
| 18 | 6.3.2  | 4 | 28 | 32 | 28 | 32 | 0  | ★  |
| 19 | 6.4.1  | 3 | 32 | 35 | 32 | 35 | 0  | ★  |
| 20 | 6.5.1  | 3 | 35 | 38 | 35 | 38 | 0  | ★  |
| 21 | 6.5.2  | 3 | 38 | 41 | 46 | 49 | 8  |    |
| 22 | 7.1.1  | 2 | 10 | 12 | 30 | 32 | 20 |    |
| 23 | 7.2.1  | 3 | 26 | 29 | 35 | 38 | 9  |    |
| 24 | 7.2.2  | 2 | 29 | 31 | 43 | 45 | 14 |    |
| 25 | 7.3.1  | 4 | 31 | 35 | 45 | 49 | 14 |    |
| 26 | 7.4.1  | 4 | 31 | 35 | 45 | 49 | 14 |    |
| 27 | 8.1.1  | 3 | 0  | 3  | 0  | 3  | 0  | ★  |
| 28 | 8.2.1  | 2 | 3  | 5  | 12 | 14 | 9  |    |
| 29 | 8.3.1  | 4 | 38 | 42 | 38 | 42 | 0  | ★  |
| 30 | 8.4.1  | 3 | 12 | 15 | 46 | 49 | 34 |    |
| 31 | 8.5.1  | 3 | 42 | 45 | 42 | 45 | 0  | ★  |

---

## Parte 4 — Ruta crítica

### 4.1 Identificación

La ruta crítica es la **cadena continua de entregables con TF = 0** que va del inicio al fin del proyecto. Cualquier retraso en uno de ellos retrasa la fecha de entrega en la misma cantidad de días.

**Duración total del proyecto: 49 días hábiles**

```
N°27 → N°4 → N°6 → N°7 → N°9 → N°10 → N°15 → N°17 → N°18 → N°19 → N°20 → N°29 → N°31 → N°3
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
| 19 | 6.4.1  | Módulo de consultas financieras | 3 | 32 | 35 | 32 | 35 | 0 |
| 20 | 6.5.1  | Módulo de cierre de caja y cálculo de totales | 3 | 35 | 38 | 35 | 38 | 0 |
| 29 | 8.3.1  | Módulo de pruebas | 4 | 38 | 42 | 38 | 42 | 0 |
| 31 | 8.5.1  | Módulo de despliegue y documentación técnica | 3 | 42 | 45 | 42 | 45 | 0 |
| 3  | 1.3.1  | Seguimiento, control y cierre del proyecto | 4 | 45 | 49 | 45 | 49 | 0 |

**14 entregables críticos de 31 (45 % del total) — suma de duraciones: 49 días**

### 4.3 Entregables quasi-críticos (holgura baja)

Estos entregables no están en la ruta crítica pero tienen poco margen; un retraso moderado puede crear una segunda ruta crítica.

| TF | N° | Código | Nombre |
|:--:|----|--------|--------|
| 8  | 21 | 6.5.2  | Módulo de informe de cierre y apertura de jornada |
| 9  | 11 | 4.2.1  | Módulo de envío, consulta y vinculación de clientes |
| 9  | 23 | 7.2.1  | Módulo de acumulación y configuración de puntos de fidelidad |
| 9  | 28 | 8.2.1  | Módulo de sincronización en tiempo real |

### 4.4 Conclusiones para la gestión del proyecto

1. **La ruta crítica sigue pasando íntegramente por el backend.** Los tres primeros entregables críticos (N°27, 4, 6) son de configuración, autenticación y control de acceso. Cualquier retraso en la puesta en marcha de la arquitectura bloquea todo el desarrollo posterior.

2. **El módulo de caja vuelve a dominar la fase central.** Cinco de los catorce entregables críticos (N°15, 17, 18, 19, 20) pertenecen al Bloque 6. La cadena registro de pagos → ingresos/retiros → solicitudes/aprobación/trazabilidad → consulta financiera → cierre ocupa 15 días sin ningún margen (días 23–38).

3. **El módulo de pruebas es el cuello de botella final.** N°29 solo puede iniciar cuando terminen el módulo de creación de comandas (N°10), el registro de pagos (N°15), la acumulación de puntos (N°23) y el cierre de caja (N°20). El bloque pruebas → despliegue → cierre (N°29 → 31 → 3) ocupa los días 38 a 49 sin margen.

4. **El frontend tiene holgura amplia.** N°5 (TF=40), N°12 (TF=23), N°13 y N°14 (TF=21), lo que permite priorizar el backend en las primeras semanas sin comprometer la fecha de entrega.

5. **N°21 (informe de cierre y apertura de jornada) es el entregable quasi-crítico con menor margen (TF=8).** Aunque no está en la ruta crítica, cualquier retraso en el módulo de cierre de caja (N°20) lo arrastra directamente.

6. **La documentación de gestión (N°1 y N°2) tiene la holgura máxima (TF=42)**, lo que permite al gerente completarla de forma incremental durante casi todo el proyecto sin afectar la entrega técnica.
