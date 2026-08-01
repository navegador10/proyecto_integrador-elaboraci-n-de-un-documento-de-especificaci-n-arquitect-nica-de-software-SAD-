# Sistema Hospitalario Digital – Documento de Especificación Arquitectónica de Software (SAD)

Repositorio del proyecto de **Arquitectura del Software**, elaborado siguiendo los lineamientos del **Rational Unified Process (RUP)** y el **modelo 4+1 de Kruchten** para la organización de las vistas arquitectónicas.

**Caso de estudio:** Sistema hospitalario digital – red de hospitales multisede con telemedicina.

## Tabla de contenido

- Descripción del proyecto
- Estructura del repositorio
- Contenido del SAD
- Diagramas
- Cómo navegar este repositorio
- Equipo de trabajo
- Metodología y referencias

## Descripción del proyecto

Este repositorio consolida la especificación arquitectónica de una plataforma digital para una red de hospitales con múltiples sedes, centralizando la gestión de pacientes, historias clínicas, citas médicas (presenciales y de telemedicina) e integración con laboratorios clínicos. La propuesta hace énfasis en seguridad y cumplimiento normativo (Ley 1581 de 2012 y lineamientos equivalentes a HIPAA).

## Estructura del repositorio

```
sistema-hospitalario-sad/
  README.md
  SAD_Sistema_Hospitalario.docx        # Documento consolidado completo
  docs/
    03-documento-vision.md
    04-especificacion-requisitos.md
    05-modelo-conceptual-dominio.md
    06-decisiones-arquitectonicas.md
    07-vistas-arquitectonicas.md
    08-conclusiones.md
    09-referencias-bibliograficas.md
  diagramas/
  imagenes-diagramas/
  LICENSE
```

## Contenido del SAD

| Sección | Descripción | Ubicación |
|---|---|---|
| Documento de visión | Problema, objetivos, alcance, stakeholders y módulos funcionales | `docs/03-documento-vision.md` |
| Especificación de requisitos | Requisitos funcionales y no funcionales | `docs/04-especificacion-requisitos.md` |
| Modelo conceptual del dominio | Entidades principales y relaciones | `docs/05-modelo-conceptual-dominio.md` |
| Decisiones arquitectónicas | Estilo seleccionado y justificación | `docs/06-decisiones-arquitectonicas.md` |
| Vistas arquitectónicas | Contexto, conceptual, casos de uso, lógica, implementación y física | `docs/07-vistas-arquitectonicas.md` |

## Diagramas

- `diagramas/modelo-conceptual-dominio.png` – Diagrama de clases
- `diagramas/vista-logica-componentes.svg` – Diagrama de componentes (vista lógica)
- `diagramas/vista-implementacion-componentes.svg` – Diagrama de implementación

## Cómo navegar este repositorio

1. Lee este `README.md` para una visión general.
2. Revisa `docs/03-documento-vision.md` para entender el problema y alcance.
3. Continúa con `docs/04-especificacion-requisitos.md` y `docs/05-modelo-conceptual-dominio.md`.
4. Consulta `docs/06-decisiones-arquitectonicas.md` y `docs/07-vistas-arquitectonicas.md` para detalles arquitectónicos.

## Equipo de trabajo

| Nombre | Rol en el proyecto |
|---|---|
| ADELSON AGUIRRE RODRIGUEZ | Integrante |
| SERGIO ALONSO ARBOLEDA SÁNCHEZ | Integrante |

## Metodología y referencias

- Kruchten, P. (1995). Architectural Blueprints – The "4+1" View Model of Software Architecture.
- Rational Unified Process (RUP) practices.
- Ley 1581 de 2012 (protección de datos personales).
- HL7 FHIR specification.
