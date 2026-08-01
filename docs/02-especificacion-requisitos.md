# Especificación de requisitos

Este documento corresponde a la Fase 1 del proyecto y presenta los siguientes elementos:

- Requisitos funcionales organizados por módulos.
- Requisitos no funcionales (atributos de calidad).
- Restricciones técnicas y organizacionales.

## Requisitos funcionales por módulo

### Módulo: Gestión de pacientes
- RF01: Registrar un nuevo paciente con datos demográficos y de contacto.
- RF02: Consultar y actualizar los datos de un paciente desde cualquier sede de la red.
- RF03: Evitar el registro duplicado de pacientes mediante validación por documento de identidad.
- RF04: Mantener un identificador único de paciente válido en todas las sedes.

### Módulo: Historias clínicas
- RF05: Crear y actualizar la historia clínica electrónica del paciente.
- RF06: Permitir a un médico de cualquier sede consultar el historial clínico completo, previa autorización de acceso.
- RF07: Registrar cada evento clínico (diagnóstico, tratamiento, evolución) con fecha, hora y profesional responsable.
- RF08: Mantener versionado/histórico de cambios en la historia clínica.

### Módulo: Citas médicas
- RF09: Agendar, reprogramar y cancelar citas médicas presenciales.
- RF10: Agendar citas de telemedicina, generando un enlace/sala de videoconsulta segura.
- RF11: Mostrar disponibilidad de médicos en tiempo real por sede y especialidad.
- RF12: Notificar al paciente y al médico sobre la cita.

### Módulo: Integración con laboratorios
- RF13: Enviar electrónicamente órdenes de laboratorio desde la historia clínica.
- RF14: Recibir e integrar automáticamente los resultados de laboratorio a la historia clínica.
- RF15: Notificar al médico tratante cuando un resultado esté disponible.
- RF16: Soportar integración con laboratorios externos mediante HL7/FHIR.

### Módulo: Seguridad y confidencialidad de la información
- RF17: Autenticación segura con MFA para roles clínicos/administrativos.
- RF18: Control de acceso basado en roles (RBAC).
- RF19: Registro de auditoría de cada acceso o modificación a información sensible.
- RF20: Permitir al paciente consultar quién ha accedido a su historia clínica.

## Requisitos no funcionales (atributos de calidad)
| Categoría | Requisito |
|---|---|
| Seguridad | Cifrado en tránsito (TLS) y en reposo (AES-256). Cumplimiento Ley 1581 / HIPAA. |
| Disponibilidad | 99.5% del tiempo (24/7) |
| Interoperabilidad | Integración vía HL7/FHIR |
| Escalabilidad | Soporta crecimiento en sedes y usuarios concurrentes |
| Rendimiento | Consultas de historia clínica < 2 segundos |
| Usabilidad | Interfaz accesible, baja curva de aprendizaje |
| Auditabilidad | Trazabilidad completa de accesos y cambios |
| Confidencialidad y privacidad | Mínimo privilegio y consentimiento informado |
| Recuperación ante desastres | Backups periódicos y plan de recuperación |

## Restricciones técnicas y organizacionales
- Cumplimiento con la Ley 1581 de 2012 y lineamientos equivalentes a HIPAA.
- Entorno multisede con distinta capacidad de infraestructura local.
- Telemedicina con protocolos seguros de videoconferencia.
- Posible necesidad de adaptadores/middleware para laboratorios sin soporte nativo HL7/FHIR.
- Distintos niveles de madurez tecnológica del personal de TI por sede.
