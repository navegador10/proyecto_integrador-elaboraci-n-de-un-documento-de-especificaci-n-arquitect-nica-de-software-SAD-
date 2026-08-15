# Matriz de trazabilidad: Requisitos → Decisiones → Vistas

Esta matriz mapea los requisitos funcionales (RF) y no-funcionales (RNF) con las decisiones arquitectónicas y las vistas/artefactos que los soportan.

| ID | Requisito breve | Decisión arquitectónica | Vistas / Artefactos |
|---|---|---|---|
| RF01 | Registrar paciente | `pacientes-service` (microservicio) con API REST y validación única | `docs/03-documento-vision.md`, `docs/04-especificacion-requisitos.md`, `diagramas/vista-logica-componentes.svg` |
| RF02 | Consultar/actualizar paciente desde cualquier sede | ID único de paciente, API Gateway, réplica de datos por sede | `docs/07-vistas-arquitectonicas.md` (vista física, lógica) |
| RF03 | Evitar duplicados | Servicio de identidad/registro con validación por documento | `docs/06-decisiones-arquitectonicas.md` |
| RF04 | Identificador único paciente | UUID centralizado en `historia-clinica-service` | `docs/05-modelo-conceptual-dominio.md` |
| RF05 | Crear/actualizar historia clínica | `historia-clinica-service` como fuente única de verdad | `docs/06-decisiones-arquitectonicas.md`, `diagramas/modelo-conceptual-dominio.png` |
| RF06 | Consulta previa autorización | RBAC (servicio de seguridad), consentimientos | `docs/07-vistas-arquitectonicas.md` (contexto, seguridad) |
| RF07 | Registrar evento clínico con metadatos | Versionado y auditoría append-only | `docs/06-decisiones-arquitectonicas.md`, `docs/05-modelo-conceptual-dominio.md` |
| RF08 | Versionado histórico | Almacenamiento inmutable/append-only, servicio de auditoría | `docs/07-vistas-arquitectonicas.md` |
| RF09 | Agendar/reprogramar/cancelar citas | `agendamiento-service` con notificaciones | `docs/07-vistas-arquitectonicas.md`, `diagramas/vista-implementacion-componentes.svg` |
| RF10 | Agendar telemedicina con enlace seguro | `telemedicina-service` desacoplado, enlaces temporales | `diagramas/sequence-teleconsulta.puml`, `docs/07-vistas-arquitectonicas.md` |
| RF11 | Mostrar disponibilidad en tiempo real | Servicio de disponibilidad (cache/stream) | `docs/07-vistas-arquitectonicas.md` (lógica) |
| RF12 | Notificaciones | Servicio de notificaciones (asíncrono) | `diagramas/vista-implementacion-componentes.svg` |
| RF13 | Enviar órdenes a laboratorios | API Gateway y adaptador HL7/FHIR | `diagramas/sequence-hl7-integration.puml`, `docs/06-decisiones-arquitectonicas.md` |
| RF14 | Recibir e integrar resultados | Adaptador HL7/FHIR, eventos de integración | `diagramas/sequence-hl7-integration.puml` |
| RF15 | Notificar médico tratante | Servicio de notificaciones + eventos | `docs/07-vistas-arquitectonicas.md` |
| RF16 | Soporte HL7/FHIR | Adaptador/middleware HL7/FHIR | `docs/06-decisiones-arquitectonicas.md` |
| RF17 | MFA para roles clínicos | Servicio de seguridad/identidad central | `docs/07-vistas-arquitectonicas.md` (física, lógica) |
| RF18 | RBAC | Servicio de seguridad y políticas centralizadas | `docs/06-decisiones-arquitectonicas.md` |
| RF19 | Registro de auditoría | Servicio append-only de auditoría | `docs/05-modelo-conceptual-dominio.md` |
| RF20 | Paciente consulta accesos | Interfaz de usuario + registros de auditoría | `docs/07-vistas-arquitectonicas.md` |

> Nota: Se recomienda mantener esta matriz actualizada conforme evolucionen los RF y las decisiones arquitectónicas. Para revisión, vincular cada fila a la sección precisa del documento y/o al número de diagrama (línea/etiqueta).