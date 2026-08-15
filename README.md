# Sistema Hospitalario Digital — Documento de Especificación Arquitectónica de Software (SAD)

Repositorio del proyecto de **Arquitectura del Software**, elaborado siguiendo los lineamientos del **Rational Unified Process (RUP)** y el **modelo 4+1 de Kruchten** para la organización de las vistas arquitectónicas.

**Caso de estudio:** Sistema hospitalario digital — red de hospitales multisede con telemedicina.

## Tabla de contenido

- [Sistema Hospitalario Digital — Documento de Especificación Arquitectónica de Software (SAD)](#sistema-hospitalario-digital--documento-de-especificación-arquitectónica-de-software-sad)
  - [Tabla de contenido](#tabla-de-contenido)
  - [Descripción del proyecto](#descripción-del-proyecto)
  - [Estructura del repositorio](#estructura-del-repositorio)
  - [Contenido del SAD](#contenido-del-sad)
  - [Diagramas](#diagramas)
  - [Cumplimiento de requisitos](#cumplimiento-de-requisitos)
  - [Cómo navegar este repositorio](#cómo-navegar-este-repositorio)
  - [Equipo de trabajo](#equipo-de-trabajo)
  - [Fase 4 — Consolidación de la especificación arquitectónica](#fase-4--consolidación-de-la-especificación-arquitectónica)
  - [Metodología y referencias](#metodología-y-referencias)

## Descripción del proyecto

Este repositorio consolida la especificación arquitectónica de una plataforma digital para una red de hospitales con múltiples sedes, que centraliza la gestión de pacientes, historias clínicas, citas médicas (presenciales y de telemedicina) e integración con laboratorios clínicos, bajo un enfoque de arquitectura de microservicios con especial énfasis en seguridad y cumplimiento normativo (Ley 1581 de 2012 y lineamientos equivalentes a HIPAA).

El desarrollo del proyecto fue incremental, integrando en un único documento los artefactos producidos en cada unidad del curso: documento de visión, especificación de requisitos, modelo conceptual del dominio, decisiones arquitectónicas y las vistas arquitectónicas del sistema.

## Estructura del repositorio

```
sistema-hospitalario-sad/
├── README.md
├── SAD_Sistema_Hospitalario.docx        # Documento consolidado completo
├── docs/
│   ├── 01-portada
|   ├── 02-introduccion
|   ├── 03-documento-vision.md
|   ├── 04-especificacion-requisitos.md
|   ├── 05-modelo-conceptual-dominio.md
│   ├── 06-decisiones-arquitectonicas.md
│   ├── 07-vistas-arquitectonicas.md
│   ├── 08-conclusiones
│   └── 09-referencias-bibliograficas
├── diagramas/
│   ├── modelo-conceptual-dominio.png      # Diagrama de clases UML
│   ├── vista-logica-componentes.svg       # Diagrama de componentes UML (SVG)
│   ├── vista-logica-componentes.puml      # Fuente PlantUML
│   ├── vista-implementacion-componentes.svg # Diagrama de implementación UML (SVG)
│   ├── vista-implementacion-componentes.puml # Fuente PlantUML
│   └── vista-fisica-despliegue.png
│── imagenes-diagramas
└── LICENSE
```

## Contenido del SAD

| Sección | Descripción | Ubicación |
|---|---|---|
| Documento de visión | Descripción del problema, objetivos, alcance, stakeholders y módulos funcionales | `docs/01-documento-vision.md` |
| Especificación de requisitos | Requisitos funcionales por módulo y requisitos no funcionales (atributos de calidad) | `docs/02-especificacion-requisitos.md` |
| Modelo conceptual del dominio | Entidades principales y relaciones del dominio | `docs/03-modelo-conceptual-dominio.md` |
| Decisiones arquitectónicas | Estilo arquitectónico seleccionado y justificación de decisiones clave | `docs/04-decisiones-arquitectonicas.md` |
| Vistas arquitectónicas | Vistas de contexto, conceptual, casos de uso, lógica, implementación y física | `docs/05-vistas-arquitectonicas.md` |
| Documento consolidado | Versión completa en Word, con portada, tabla de contenido y diagramas incrustados | `SAD_Sistema_Hospitalario.docx` |

## Diagramas

- **Diagrama de clases del modelo conceptual del dominio** — `diagramas/modelo-conceptual-dominio.png`
- **Diagrama de componentes de la vista lógica** — `diagramas/vista-logica-componentes.svg`
- **Diagrama de implementación de componentes** — `diagramas/vista-implementacion-componentes.svg`

Los diagramas están elaborados con notación UML y se acompañan de sus fuentes en PlantUML para facilitar la edición y la legibilidad técnica.

## Cumplimiento de requisitos

- [x] Elaboración colaborativa por todos los integrantes del equipo: el repositorio está organizado por fases y módulos, facilitando la integración de aportes en un solo espacio de trabajo.
- [x] Diagramas claros, legibles y elaborados con herramientas de modelado UML: se incluyen diagramas en formato SVG y fuentes PlantUML.
- [x] Coherencia entre requisitos, decisiones arquitectónicas y vistas: la documentación está conectada por fases y se mantiene una relación directa entre los artefactos.
- [x] Justificación de las decisiones arquitectónicas adoptadas: se explican el estilo arquitectónico elegido y los beneficios para los atributos de calidad.
- [x] Presentación organizada y adecuada redacción técnica: la estructura del repositorio está dividida por documentos, secciones y diagramas claramente identificados.

## Cómo navegar este repositorio

1. Empieza por este `README.md` para una visión general del proyecto.
2. Revisa `docs/01-documento-vision.md` para entender el problema, objetivos y alcance.
3. Continúa con `docs/02-especificacion-requisitos.md` y `docs/03-modelo-conceptual-dominio.md`.
4. Consulta `docs/04-decisiones-arquitectonicas.md` para entender el porqué de la arquitectura de microservicios elegida.
5. Revisa `docs/05-vistas-arquitectonicas.md` para el detalle de cada vista, apoyado en las imágenes de `diagramas/`.
6. Si prefieres una lectura consolidada y con formato de entrega, abre `SAD_Sistema_Hospitalario.docx`.

## Equipo de trabajo

| Nombre | Rol en el proyecto |
|---|---|
| **ADELSON AGUIRRE RODRIGUEZ** | Integrante |
| **SERGIO ALONSO ARBOLEDA SÁNCHEZ** | Integrante |


## Fase 4 — Consolidación de la especificación arquitectónica

Este trabajo se entrega en un repositorio en GitHub, donde el equipo integra todos los artefactos desarrollados durante la asignatura. La consolidación verifica la coherencia entre requisitos, decisiones arquitectónicas y vistas del sistema.

Finalmente, se presenta la propuesta arquitectónica, justificando las principales decisiones tomadas y explicando cómo la arquitectura satisface los atributos de calidad definidos para el caso de estudio.

## Metodología y referencias

- Kruchten, P. (1995). *Architectural Blueprints — The "4+1" View Model of Software Architecture*. IEEE Software, 12(6), 42-50.
- Rational Software / IBM. *Rational Unified Process (RUP): Best Practices for Software Development Teams*.
- Congreso de Colombia. (2012). *Ley 1581 de 2012*, protección de datos personales.
- HL7 International. *HL7 FHIR (Fast Healthcare Interoperability Resources) Specification*.
- Bass, L., Clements, P., & Kazman, R. (2012). *Software Architecture in Practice* (3rd ed.). Addison-Wesley.
