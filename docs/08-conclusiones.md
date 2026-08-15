## Conclusiones

## Conclusión general

La elaboración de la Especificación Arquitectónica de Software (SAD) para el Sistema Hospitalario Digital permitió definir una propuesta arquitectónica orientada a las necesidades de una red hospitalaria multisede, considerando los requisitos funcionales, los atributos de calidad y las necesidades de interoperabilidad, seguridad y evolución del sistema.

El proceso permitió establecer una relación coherente entre el análisis del dominio, los requisitos del sistema, las decisiones arquitectónicas y las diferentes vistas utilizadas para representar la solución.

Como resultado, se propone una arquitectura de microservicios orientada a dominios, complementada con un API Gateway y mecanismos especializados para seguridad, interoperabilidad, telemedicina y auditoría.

---

## Arquitectura basada en microservicios orientada a dominios

La principal decisión arquitectónica consiste en adoptar un estilo de microservicios orientado a dominios.

Esta decisión permite organizar el sistema en servicios con responsabilidades claramente delimitadas, favoreciendo la separación de responsabilidades y la evolución independiente de las capacidades del sistema.

La arquitectura resulta adecuada para el escenario planteado debido a que la red hospitalaria requiere soportar múltiples sedes, diferentes tipos de usuarios, integración con sistemas externos y crecimiento progresivo de la plataforma.

El escalamiento independiente de los microservicios permite asignar recursos de acuerdo con las necesidades particulares de cada capacidad, evitando que el crecimiento de un módulo obligue necesariamente a escalar todo el sistema.

---

## Escalabilidad y disponibilidad

La arquitectura propuesta favorece la escalabilidad mediante el despliegue independiente de los microservicios.

Cada servicio puede disponer de réplicas de acuerdo con su nivel de demanda, permitiendo adaptar la infraestructura a las necesidades reales de operación.

Para la disponibilidad 24/7 se plantea utilizar mecanismos de redundancia y aislamiento de fallos. De esta manera, un problema localizado en un servicio no necesariamente deberá provocar la indisponibilidad completa de la plataforma.

La disponibilidad, sin embargo, dependerá también de una correcta implementación de infraestructura, monitoreo, recuperación ante fallos y operación de la plataforma.

---

## Historia clínica como fuente única de verdad

Una de las decisiones arquitectónicas centrales consiste en establecer la historia clínica como fuente única de verdad para la información clínica del paciente.

Esta decisión permite evitar diferentes versiones inconsistentes de la información clínica entre las distintas sedes y servicios.

La información clínica deberá mantenerse centralizada y controlada, mientras que los demás servicios podrán acceder a ella mediante mecanismos de integración definidos por la arquitectura.

Esta decisión resulta especialmente importante en un entorno multisede, donde un paciente puede recibir atención en diferentes establecimientos de la red.

---

## Seguridad y control de acceso

La seguridad constituye una preocupación transversal del Sistema Hospitalario Digital.

Para atender esta necesidad se estableció como decisión arquitectónica la existencia de un servicio de seguridad e identidad independiente, encargado de centralizar mecanismos relacionados con autenticación, autorización y control de acceso.

Esta separación permite aplicar políticas de seguridad de manera consistente sobre los diferentes servicios.

La arquitectura deberá garantizar que el acceso a la información clínica se encuentre restringido de acuerdo con los roles y permisos definidos, aplicando el principio de mínimo privilegio.

---

## Auditoría y trazabilidad

La trazabilidad de las operaciones sobre información sensible constituye otro elemento fundamental de la arquitectura.

Para ello se estableció un **registro de auditoría append-only**, orientado a conservar evidencia de las operaciones realizadas sobre el sistema sin permitir modificaciones arbitrarias sobre los registros históricos.

Esta decisión favorece la integridad de la información de auditoría y facilita procesos posteriores de revisión, seguimiento y análisis de eventos relacionados con seguridad y acceso a información clínica.

---

## Interoperabilidad con laboratorios externos

La integración con laboratorios externos constituye una de las principales necesidades de interoperabilidad identificadas durante el análisis.

Para responder a esta necesidad se definió el uso de un **adaptador HL7/FHIR**, permitiendo separar la lógica interna del sistema hospitalario de las particularidades de los sistemas externos.

El API Gateway complementa esta estrategia al proporcionar un punto controlado para la interacción con los servicios de la plataforma.

Esta combinación permite establecer una arquitectura preparada para incorporar diferentes laboratorios y otros sistemas externos sin modificar directamente la lógica principal de los servicios hospitalarios.

---

## Telemedicina desacoplada de la gestión de citas

La arquitectura establece el **servicio de telemedicina como un componente desacoplado del servicio de citas**.

Esta decisión permite mantener separadas dos responsabilidades diferentes:

- La gestión y programación de las citas.
- La prestación y administración de la atención mediante telemedicina.

El desacoplamiento facilita la evolución independiente de las funcionalidades de telemedicina y permite integrar proveedores o mecanismos especializados sin introducir dependencias innecesarias en el servicio de citas.

---

## API Gateway

El **API Gateway** se establece como un punto de entrada controlado para las aplicaciones y consumidores externos de la plataforma.

Su incorporación permite centralizar aspectos relacionados con:

- Enrutamiento de solicitudes.
- Interoperabilidad.
- Control de acceso.
- Gestión de solicitudes.
- Integración con servicios internos.

Esta decisión contribuye a evitar que los clientes tengan que conocer directamente la ubicación o estructura interna de cada microservicio.

---

## Beneficios esperados de la propuesta

La arquitectura propuesta proporciona los siguientes beneficios:

- Separación clara de responsabilidades.
- Escalabilidad independiente de los servicios.
- Mayor facilidad para evolucionar funcionalidades.
- Integración estructurada con sistemas externos.
- Centralización de la información clínica crítica.
- Control de acceso y seguridad centralizados.
- Mayor trazabilidad mediante auditoría.
- Posibilidad de incorporar nuevas sedes.
- Desacoplamiento de los servicios de telemedicina.
- Mayor capacidad para integrar nuevos proveedores y sistemas.

---

## Consideraciones y desafíos

Aunque la arquitectura propuesta presenta ventajas importantes, la adopción de microservicios también introduce desafíos que deberán ser considerados durante las siguientes etapas del proyecto.

Entre ellos se encuentran:

- Complejidad de comunicación entre servicios.
- Gestión de fallos distribuidos.
- Monitoreo y observabilidad.
- Administración de múltiples servicios.
- Gestión de consistencia entre diferentes procesos.
- Seguridad de las comunicaciones internas.
- Automatización de despliegues.
- Gestión de configuración.
- Recuperación ante fallos.

Por esta razón, la arquitectura deberá estar acompañada de prácticas adecuadas de integración, despliegue, monitoreo, seguridad y operación.

---

## Consideración profesional para una implementación real

La arquitectura definida en este SAD constituye una **propuesta arquitectónica de alto nivel** y una base para las siguientes etapas del proyecto.

Antes de implementar la solución en un entorno productivo será necesario profundizar aspectos como:

- Selección de tecnologías.
- Definición de contratos API.
- Especificación detallada de interfaces.
- Definición de modelos de datos.
- Estrategia de despliegue.
- Configuración de alta disponibilidad.
- Gestión de respaldos.
- Recuperación ante desastres.
- Pruebas de rendimiento.
- Pruebas de seguridad.
- Monitoreo y observabilidad.
- Gestión de infraestructura.
- Definición detallada de los mecanismos de interoperabilidad HL7/FHIR.

Esto permite diferenciar la arquitectura conceptual y lógica definida en el SAD de las decisiones de implementación que deberán tomarse posteriormente.

---

## Conclusión final

El Sistema Hospitalario Digital requiere una arquitectura capaz de responder simultáneamente a necesidades funcionales y atributos de calidad críticos como seguridad, disponibilidad, escalabilidad, interoperabilidad y auditabilidad.

A partir del análisis realizado se seleccionó una arquitectura de microservicios orientada a dominios, complementada por un API Gateway, un servicio independiente de seguridad e identidad, una historia clínica como fuente única de verdad, un adaptador HL7/FHIR para laboratorios externos, un servicio de telemedicina desacoplado de citas y un mecanismo de auditoría append-only.

Estas decisiones proporcionan una estructura coherente para una red hospitalaria multisede y permiten que la plataforma pueda evolucionar de manera controlada.

La arquitectura propuesta no pretende únicamente organizar los componentes del software, sino establecer una base técnica que permita mantener la integridad de la información clínica, controlar el acceso a los datos, facilitar la interoperabilidad y soportar el crecimiento de la organización.

En consecuencia, el SAD constituye una guía arquitectónica para las siguientes fases del proyecto y proporciona una base para avanzar hacia el diseño detallado, la selección tecnológica y la posterior implementación de una solución hospitalaria segura, interoperable, escalable y mantenible.