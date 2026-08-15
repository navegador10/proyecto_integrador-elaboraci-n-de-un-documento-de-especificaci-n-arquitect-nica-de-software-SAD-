# Decisiones arquitectónicas

Este documento corresponde a la Fase 2 del proyecto y recoge las decisiones arquitectónicas adoptadas a partir del análisis del dominio y de los requisitos.

Incluye:
- La justificación de las decisiones arquitectónicas adoptadas.
- La selección del estilo arquitectónico más adecuado.

## Selección del estilo arquitectónico
**Estilo propuesto:** arquitectura de microservicios orientada a dominios, con API Gateway para la interoperabilidad con laboratorios externos.

| Atributo de calidad | Cómo lo favorece el estilo elegido |
|---|---|
| Escalabilidad | Escalado independiente por microservicio |
| Disponibilidad 24/7 | Redundancia; fallo aislado por módulo |
| Interoperabilidad | Adaptador HL7/FHIR para laboratorios externos |
| Seguridad y auditabilidad | Servicio de seguridad centralizado |
| Mantenibilidad | Evolución independiente por servicio |
| Multisede | Réplicas cercanas a cada sede; datos críticos centralizados |

## Decisiones arquitectónicas clave
- Servicio de seguridad/identidad independiente.
- API Gateway como punto único de entrada.
- Historia clínica como fuente única de verdad.
- Adaptador HL7/FHIR para laboratorios externos.
- Servicio de telemedicina desacoplado de citas.
- Registro de auditoría append-only.

## Coherencia con requisitos y vistas

La arquitectura propuesta se alinea con los requisitos funcionales y no funcionales del sistema:

| Requisito | Decisión arquitectónica | Vista relacionada |
|---|---|---|
| Gestión centralizada de historias clínicas | Historia clínica como fuente única de verdad | Vista lógica y vista conceptual |
| Integración con laboratorios externos | Adaptador HL7/FHIR y API Gateway | Vista lógica y vista de contexto |
| Seguridad y trazabilidad | Servicio de seguridad independiente y auditoría append-only | Vista lógica y vista física |
| Disponibilidad y escalabilidad | Microservicios con despliegue independiente por servicio | Vista física y vista de implementación |
