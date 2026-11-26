# Registro de Horas por Paquete — APPRESSO

> **Estado:** v0.4 (26 de noviembre de 2026).
> **Lleva el registro:** Felipe Salcedo (gerente del proyecto).
> **Para qué sirve:** es la fuente del **costo real (AC)** de las [Métricas de Proyecto](Métricas%20de%20Proyecto%20Appresso.md). Cada persona anota las horas que trabajó en cada paquete, por semana; el total de cada tabla y el acumulado por semana alimentan el AC de cada corte.

## Cómo se llena

- Una tabla por paquete de trabajo (código de la EDT y nombre).
- Una fila por **persona y semana**: nombre, semana y **las horas de esa semana** (no el acumulado).
- Las semanas son de lunes a sábado y se cierran con el corte del sábado: S1 = hasta el 31/10, S2 = hasta el 07/11, S3 = hasta el 14/11, S4 = hasta el 21/11, y así sucesivamente (misma numeración que las [Métricas de Proyecto](Métricas%20de%20Proyecto%20Appresso.md), sección 4.3).
- El **Total** de cada paquete es la suma de sus filas, y se valora a $15.000 por hora.
- El AC acumulado de un corte es la suma de las horas de todos los paquetes con trabajo hasta esa semana, estén terminados o no.
- Las horas se anotan antes del corte del sábado. Cuando empiece un paquete nuevo, se agrega su tabla con el mismo formato.

### Horas por semana de todo el proyecto

| Semana | Corte | Horas de la semana | AC acumulado |
| :----: | :---: | :----------------: | :----------: |
|   S1   | 31/10 |         18         |      18      |
|   S2   | 07/11 |         22         |      40      |
|   S3   | 14/11 |         75         |     115      |
|   S4   | 21/11 |         59         |     174      |
|   S5   | 28/11 |         21         |     195      |

_Las semanas de las horas registradas fueron confirmadas por el gerente el 16/11/2026._

_Al corte de S3 se habían registrado 55 h en la semana y 95 h acumuladas. El total actualizado de S3 incluye 20 h anotadas después del corte (12 h en 8.2.1 y 8 h en 2.2.1). Al corte de S4 se registraron 51 h en la semana y 166 h acumuladas. El total actualizado de S4 incorpora 5 h adicionales en 3.1.1 (Productos y categorías) y 3 h adicionales en 6.1.1. Las horas de S5 son parciales._

---

## 1.1.1 — Documentos de inicio y planificación estructural

| Nombre    | Semana | Horas  |
| --------- | :----: | :----: |
| Felipe    |   S1   |   18   |
| Felipe    |   S2   |   10   |
|           |        |        |
|           |        |        |
|           |        |        |
|           |        |        |
| **Total** |        | **28** |

## 1.2.1 — Plan temporal, económico y de riesgos

| Nombre    | Semana | Horas  |
| --------- | :----: | :----: |
| Felipe    |   S2   |   10   |
|           |        |        |
|           |        |        |
|           |        |        |
|           |        |        |
|           |        |        |
| **Total** |        | **10** |

## 2.1.1 — Módulo de autenticación

| Nombre    | Semana | Horas  |
| --------- | :----: | :----: |
| Felipe    |   S3   |   11   |
|           |        |        |
|           |        |        |
|           |        |        |
|           |        |        |
|           |        |        |
| **Total** |        | **11** |

## 2.2.1 — Administración de usuarios

| Nombre      | Semana | Horas  |
| ----------- | :----: | :----: |
| Diego Gómez |   S3   |   8    |
| Felipe      |   S4   |   2    |
|             |        |        |
|             |        |        |
|             |        |        |
|             |        |        |
| **Total**   |        | **10** |

## 2.3.1 — Control de acceso por rol y acceso remoto del administrador

| Nombre              | Semana | Horas  |
| ------------------- | :----: | :----: |
| Diego Bolaños       |   S3   |   11   |
| Stiven Mujanajinsoy |   S3   |   3    |
| Felipe Salcedo      |   S4   |   4    |
|                     |        |        |
|                     |        |        |
|                     |        |        |
| **Total**           |        | **18** |

## 3.1.1 — Productos y categorías

| Nombre      | Semana | Horas  |
| ----------- | :----: | :----: |
| Diego Gómez |   S4   |   8    |
| Juan Aragón |   S4   |   15   |
| Felipe      |   S4   |   1    |
|             |        |        |
|             |        |        |
|             |        |        |
| **Total**   |        | **24** |

## 3.2.1 — Control de existencias

| Nombre    | Semana | Horas |
| --------- | :----: | :---: |
| Felipe    |   S5   |   6   |
| **Total** |        | **6** |

## 3.3.1 — Consulta del menú y visualización en cocina

| Nombre      | Semana | Horas  |
| ----------- | :----: | :----: |
| Diego Gómez |   S5   |   9    |
| Felipe      |   S5   |   1    |
| **Total**   |        | **10** |

## 6.1.1 — Registro de pagos

| Nombre      | Semana | Horas |
| ----------- | :----: | :---: |
| Diego Gómez |   S4   |   9   |
|             |        |       |
|             |        |       |
|             |        |       |
|             |        |       |
|             |        |       |
| **Total**   |        | **9** |

## 7.1.1 — Registro y búsqueda de clientes

| Nombre      | Semana | Horas |
| ----------- | :----: | :---: |
| Juan Aragón |   S4   |   7   |
| Felipe      |   S4   |   3   |
|             |        |       |
|             |        |       |
|             |        |       |
|             |        |       |
| **Total**   |        | **10** |

## 8.1.1 — Módulo de configuración de arquitectura del proyecto

| Nombre      | Semana | Horas  |
| ----------- | :----: | :----: |
| Felipe      |   S2   |   2    |
| Felipe      |   S3   |   13   |
| Diego Gómez |   S3   |   5    |
|             |        |        |
|             |        |        |
|             |        |        |
| **Total**   |        | **20** |

## 8.2.1 — Módulo de sincronización en tiempo real

| Nombre      | Semana | Horas  |
| ----------- | :----: | :----: |
| Diego Gómez |   S3   |   12   |
| Juan Aragón |   S3   |   12   |
| Diego Gómez |   S4   |   3    |
|             |        |        |
|             |        |        |
|             |        |        |
| **Total**   |        | **27** |

## 8.4.1 — Seguridad y cumplimiento

| Nombre        | Semana | Horas |
| ------------- | :----: | :---: |
| Juan Aragón   |   S4   |   1   |
| Felipe        |   S4   |   1   |
| Diego Bolaños |   S4   |   2   |
| David jajoy   |   S4   |   3   |
|               |        |       |
|               |        |       |
| **Total**     |        | **7** |

## 8.5.1 — Despliegue y documentación técnica

| Nombre    | Semana | Horas |
| --------- | :----: | :---: |
| Felipe    |   S5   |   5   |
| **Total** |        | **5** |

_Las 5 h corresponden al despliegue interno adelantado por CC-03, fuera del alcance del despliegue final de producción de 8.5.1. Se incluyen en las horas reales trabajadas._
