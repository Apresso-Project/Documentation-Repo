# Matriz RACI — APPRESSO

## Leyenda de roles

| Sigla | Rol | Persona |
|-------|-----|---------|
| Fel | Gerente del proyecto | Felipe Salcedo |
| Sti | Desarrollador Android | Stiven Mujanajinsoy |
| Seb | Desarrollador Android | Sebastián Aragón |
| Bol | Desarrollador Backend | Diego Bolaños |
| Góm | Desarrollador Backend | Diego Gómez |
| Dav | Tester / QA | David Ascencio |
| CL | Patrocinador / Cliente | Pepito Pérez |

## Leyenda RACI

| Letra | Significado |
|-------|-------------|
| **R** | *Responsible* — ejecuta el trabajo |
| **A** | *Accountable* — responde por el resultado (único por fila) |
| **C** | *Consulted* — aporta criterio, comunicación bidireccional |
| **I** | *Informed* — recibe actualizaciones, comunicación unidireccional |

## Restricciones de asignación

| Integrante | Condición aplicada |
|---|---|
| Felipe Salcedo | Pocos entregables con R/A; involucrado en ruta crítica (★) |
| David Ascencio | Pocos entregables con R; fuera de ruta crítica |

---

## Matriz

### Bloque 1 — Gestión del proyecto

| Código | Entregable | Fel | Sti | Seb | Bol | Góm | Dav | CL | RC |
|--------|-----------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| 1.1.1 | Documentos de inicio y planificación estructural | RA | C | C | C | C | C | C |  |
| 1.2.1 | Plan temporal, económico y riesgos | RA | C | C | C | C | I | I |  |
| 1.3.1 | Seguimiento, control y cierre del proyecto | RA | I | I | I | I | I | I | ★ |

### Bloque 2 — Gestión de usuarios y permisos

| Código | Entregable | Fel | Sti | Seb | Bol | Góm | Dav | CL | RC |
|--------|-----------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| 2.1.1 | Módulo de autenticación | C | RA | I | R | I | C | I | ★ |
| 2.2.1 | Módulo de administración de usuarios | C | RA | I | R | I | I | I |  |
| 2.3.1 | Control de acceso y acceso remoto del administrador | C | R | I | RA | I | C | I | ★ |

### Bloque 3 — Catálogo e inventario

| Código | Entregable | Fel | Sti | Seb | Bol | Góm | Dav | CL | RC |
|--------|-----------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| 3.1.1 | Módulo de gestión de productos y categorías | C | I | RA | I | R | I | I | ★ |
| 3.2.1 | Módulo de control de existencias | C | I | R | I | RA | C | I |  |
| 3.3.1 | Módulo de consulta del menú y visualización en cocina | C | I | RA | I | R | I | C | ★ |

### Bloque 4 — Comandas y pedidos

| Código | Entregable | Fel | Sti | Seb | Bol | Góm | Dav | CL | RC |
|--------|-----------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| 4.1.1 | Módulo de creación de comandas | C | RA | I | R | I | C | I | ★ |
| 4.2.1 | Módulo de envío, consulta y vinculación de clientes | C | RA | I | R | I | C | I |  |
| 4.2.2 | Módulo de modificación y cancelación de pedidos | C | R | I | RA | I | C | I |  |

### Bloque 5 — Pantalla de cocina

| Código | Entregable | Fel | Sti | Seb | Bol | Góm | Dav | CL | RC |
|--------|-----------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| 5.1.1 | Módulo de visualización de pedidos en cocina | C | I | RA | I | R | I | I |  |
| 5.2.1 | Módulo de gestión de estados y notificación al mesero | C | I | R | I | RA | C | I |  |

### Bloque 6 — Módulo de caja

| Código | Entregable | Fel | Sti | Seb | Bol | Góm | Dav | CL | RC |
|--------|-----------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| 6.1.1 | Módulo de registro de pagos | C | RA | I | R | I | I | I | ★ |
| 6.2.1 | Módulo de gestión de transferencias QR | C | RA | I | R | I | I | I |  |
| 6.3.1 | Módulo de ingresos y retiros directos | C | R | I | RA | I | I | I | ★ |
| 6.3.2 | Módulo de solicitudes de retiro, aprobación y trazabilidad | C | RA | I | R | I | I | I | ★ |
| 6.4.1 | Módulo de consultas financieras | C | R | I | RA | I | C | I | ★ |
| 6.5.1 | Módulo de cierre de caja y cálculo de totales | C | R | I | RA | I | C | I | ★ |
| 6.5.2 | Módulo de informe de cierre y apertura de jornada | C | R | I | RA | I | I | I |  |

### Bloque 7 — Fidelización de clientes

| Código | Entregable | Fel | Sti | Seb | Bol | Góm | Dav | CL | RC |
|--------|-----------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| 7.1.1 | Módulo de registro y búsqueda de clientes | C | I | RA | I | R | I | C |  |
| 7.2.1 | Módulo de acumulación y configuración de puntos de fidelidad | C | I | R | I | RA | C | I |  |
| 7.2.2 | Módulo de consulta de puntos | C | I | RA | I | I | I | C |  |
| 7.3.1 | Módulo de recompensas y canjes | C | I | RA | I | R | C | C |  |
| 7.4.1 | Módulo de promociones y notificaciones de fidelización | C | I | R | I | RA | I | C |  |

### Bloque 8 — Infraestructura y calidad

| Código | Entregable | Fel | Sti | Seb | Bol | Góm | Dav | CL | RC |
|--------|-----------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| 8.1.1 | Módulo de configuración de arquitectura del proyecto | C | I | R | I | RA | I | I | ★ |
| 8.2.1 | Módulo de sincronización en tiempo real | C | I | I | I | RA | C | I |  |
| 8.3.1 | Módulo de pruebas | C | R | I | I | RA | C | I | ★ |
| 8.4.1 | Módulo de seguridad y cumplimiento normativo | C | I | R | I | RA | R | I |  |
| 8.5.1 | Módulo de despliegue y documentación técnica | R | I | I | I | RA | I | A | ★ |

---

## Carga por integrante

| Integrante | R (ejecuta) | A (responde) | C (consulta) | I (informado) |
|---|:---:|:---:|:---:|:---:|
| Fel (Felipe) | 4 | 3 | 27 | 0 |
| Sti (Stiven) | 14 | 7 | 2 | 15 |
| Seb (Sebastián) | 12 | 6 | 2 | 17 |
| Bol (Bolaños) | 13 | 6 | 2 | 16 |
| Góm (Gómez) | 14 | 9 | 2 | 15 |
| Dav (David) | 1 | 0 | 14 | 16 |
| CL (Cliente) | 0 | 1 | 6 | 24 |
