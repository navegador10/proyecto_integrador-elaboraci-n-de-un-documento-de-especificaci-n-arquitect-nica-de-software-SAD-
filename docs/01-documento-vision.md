# Documento de visión

Este documento corresponde a la Fase 1 del proyecto y contiene los elementos iniciales solicitados:

- Descripción del problema.
- Objetivos del sistema.
- Alcance.
- Stakeholders.
- Identificación de los módulos funcionales.

Los requisitos funcionales, no funcionales y las restricciones técnicas/organizacionales se detallan en `docs/02-especificacion-requisitos.md`.

## Descripción del problema
Las redes hospitalarias con múltiples sedes suelen operar con sistemas de información fragmentados: cada sede maneja historias clínicas, agendas de citas y resultados de laboratorio de forma aislada. Esto genera duplicidad de información del paciente, dificultad para consolidar el historial clínico entre sedes, tiempos de espera prolongados en la asignación de citas y riesgos de seguridad al no existir un control centralizado sobre quién accede a la información sensible del paciente.

Se requiere una plataforma digital unificada que permita a cualquier sede de la red acceder a la información clínica actualizada del paciente, gestionar citas (presenciales y de telemedicina), integrarse con los laboratorios clínicos, y garantizar la confidencialidad de los datos conforme a normativa de protección de datos en salud.

## Objetivos del sistema
- Centralizar la gestión de pacientes y su historia clínica entre todas las sedes de la red hospitalaria.
- Permitir la programación de citas médicas presenciales y de telemedicina desde cualquier sede.
- Integrar automáticamente los resultados de laboratorio a la historia clínica del paciente.
- Garantizar la seguridad, trazabilidad y confidencialidad de la información clínica, cumpliendo normativa nacional e internacional de protección de datos en salud.
- Facilitar el acceso remoto y seguro de médicos y pacientes mediante consulta virtual.

## Alcance
El sistema cubrirá los procesos de:
- Registro y gestión de pacientes en todas las sedes.
- Gestión de historias clínicas electrónicas compartidas entre sedes.
- Agendamiento y gestión de citas médicas presenciales y virtuales (telemedicina).
- Integración con sistemas de laboratorio clínico para el envío y recepción de resultados.
- Control de acceso, autenticación y auditoría de la información según roles.

Quedan fuera del alcance: facturación y procesos financieros, gestión de inventario de farmacia/insumos, y sistemas de imagenología (PACS), salvo su integración futura como sistema externo.

## Stakeholders
| Stakeholder | Rol / Interés |
|---|---|
| Pacientes | Acceder a citas, telemedicina y su historia clínica de forma segura |
| Médicos / personal clínico | Consultar y actualizar historias clínicas, atender citas y teleconsultas |
| Personal administrativo | Gestionar agendas, registro de pacientes y reportes |
| Laboratorios clínicos (internos/externos) | Enviar resultados de exámenes integrados al sistema |
| Área de TI / seguridad de la información | Garantizar disponibilidad, seguridad y cumplimiento normativo |
| Dirección médica / administrativa de la red | Supervisar operación entre sedes, indicadores y calidad del servicio |
| Entes reguladores | Verificar cumplimiento normativo (Ley 1581, lineamientos tipo HIPAA) |

## Módulos funcionales identificados
1. Gestión de pacientes
2. Historias clínicas
3. Citas médicas (presenciales y telemedicina)
4. Integración con laboratorios
5. Seguridad y confidencialidad de la información
