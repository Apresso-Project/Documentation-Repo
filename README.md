# Documentation-Repo

Documentación del proyecto **Appresso** — aplicación móvil Android para la gestión de la cafetería CaffeBar.

Asignaturas: Introducción a la Gestión de Proyectos de Software + Desarrollo de Aplicaciones Móviles, Universidad del Valle, sede Tuluá. Principal responsable: Andrés Felipe Salcedo Buitrago.

## Alcance y despliegue vigentes

- El equipo y el patrocinador aprobaron el **21/11/2026 (CC-03)** retirar las vistas independientes de consulta de caja del cajero y consulta financiera del administrador (RF-38 y RF-39). La EDT y su diccionario conservan el paquete como eliminado. Se mantienen el historial de movimientos y los informes de cierre. [Decisiones de la reunión](Seguimiento%20de%20Riesgos%20Appresso.md#313-decisiones-de-la-reunión-de-control-del-21112026)
- Se acordó iniciar los despliegues internos continuos con **Render y Neon** durante el desarrollo. El despliegue de la **v1.0 en producción** queda en **8.5.1**. Se debe registrar la evidencia del entorno interno para R-12 y de las pruebas tras inactividad para R-14. [Seguimiento de riesgos](Seguimiento%20de%20Riesgos%20Appresso.md#3-respuesta-a-cada-riesgo)
- El código y las guías técnicas viven en [Appresso-App](https://github.com/Apresso-Project/Appresso-App). El [índice de pruebas en teléfono](https://github.com/Apresso-Project/Appresso-App/blob/main/android/README.md#pruebas-en-teléfono-y-evidencia) enlaza las tablas de roles, tiempo real, cocina, Keystore y supresión.

## Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `Acta de Constitución Appresso.md` | Acta de inicio: objetivos, alcance, hitos, riesgos, interesados y aprobaciones |
| `Requerimientos funcionales y no funcionales de Appresso.md` | RF-01 a RF-65 con criterios de aceptación |
| `Historias de usuario APPRESSO.md` | HU-01 a HU-65 con análisis INVEST |
| `EDT Completa.md` | EDT completa con la descripción y el criterio de aceptación de cada entregable |
| `EDT y OBS/` | Diccionario de la EDT, diagrama de la EDT (`.puml`) y matriz RACI |
| `cronograma-Appresso.md` | Actividades, duraciones (4 h/día, L-S), dependencias y ruta crítica |
| `cronograma-graficos-Appresso.html` | Diagrama de Gantt y de dependencias del cronograma |
| `Plan de Riesgos Appresso.md` | Riesgos identificados, escala, costo esperado y respuesta a los críticos (punto de partida) |
| `Seguimiento de Riesgos Appresso.md` | Registro vivo de riesgos: estados, respuestas, reuniones e historial de cambios |
| `Plan de Calidad Appresso.md` | Atributos de calidad, prácticas comprometidas y definición de terminado |
| `Presupuesto Appresso.md` | Costo de entregables, respuestas a riesgos, costos directos y reserva de contingencia |
| `Control de Asistencia Appresso.md` | Asistencia a los dailies y registro de bloqueos y compromisos |
| `Métricas de Proyecto Appresso.md` | Líneas base, valor planificado, ganado y costo real (EVM), métricas de flujo y calidad, tablero y cadencia semanal de revisión |
| `metricas-grafico-Appresso.html` | Curva de trabajo acumulado (PV, EV y AC) por semana, con variaciones e índices |
| `Registro de Horas Appresso.md` | Horas trabajadas por persona y paquete, fuente del costo real (AC) |

## Equipo (Descompiladores)

| Nombre | Código | Rol |
|---|---|---|
| Andrés Felipe Salcedo Buitrago | 2359304-3743 | Gerente del proyecto |
| Diego Alejandro Gómez Puentes | — | Desarrollador Backend |
| Diego Bolaños Isiquita | — | Desarrollador Backend |
| Juan Sebastián Aragón Campo | — | Desarrollador Android |
| David Stiven Mujanajinsoy Jayoy | — | Desarrollador Android |
| Juan David Ascencio Cancimance | 2359660-3743 | Tester / QA |
