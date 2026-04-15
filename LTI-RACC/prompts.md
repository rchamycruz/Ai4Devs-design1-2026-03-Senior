# Prompts — LTI ATS Design Session

Registro de todos los prompts utilizados durante la sesión de diseño del sistema LTI ATS.

---

## Prompt 0 — Meta prompt inicial (usuario)

**Contexto:** Instrucción original del ejercicio recibida en `initial.md`.

> Contexto: LTI es una startup que quiere desarrollar el ATS del futuro. Un ATS lleva las siguientes fases circulares: Creating Jobs -> Jobs published on Job Boards, Website, Social Media, etc. -> Job Applications Received -> Applications are Reviewed -> Online Tests are Conducted -> Interviews are Scheduled -> Selected Applicants are Hired -> REPEAT PROCESS.
>
> Debes actuar como un product manager y definir esas funcionalidades clave que harán brillar a LTI por encima de los competidores: aumentar la eficiencia para los departamentos de HR, mejorar la colaboración en tiempo real entre reclutadores y managers, automatizaciones, asistencia de IA en diversas tareas.
>
> Tu misión es diseñar la primera versión del sistema, entregando los siguientes artefactos: descripción breve del software LTI, valor añadido y ventajas competitivas, funciones principales, Lean Canvas, 3 casos de uso principales con diagrama, modelo de datos, diseño del sistema a alto nivel con diagrama, diagrama C4 de un componente.
>
> Documenta todo en un único documento markdown con el nombre LTI-RACC.md. Documenta todos los prompts en el archivo prompts.md.

---

## Prompt 1 — Generación del meta prompt (usuario)

**Contexto:** El usuario solicita crear un prompt especializado para IA basado en `initial.md`.

> Genera un prompt especializado para IA (meta prompt) en base al archivo initial.md y guarda este prompt en un archivo llamado master-prompt.md

**Resultado:** Creación de `master-prompt.md` con rol, misión, artefactos requeridos, restricciones de formato, criterios de calidad y estrategia de ejecución.

---

## Prompt 2 — Generación del plan de ejecución (usuario)

**Contexto:** El usuario solicita un plan detallado para ejecutar el master-prompt.

> Genera un plan detallado para master-prompt.md y grabalo en master-prompt-plan.md para revisarlo

**Resultado:** Creación de `master-prompt-plan.md` con 6 fases secuenciales, prompts por fase, entregables y criterios de calidad.

---

## Prompt 3 — Ejecución del plan (usuario)

**Contexto:** El usuario aprueba el plan y solicita su ejecución completa.

> ejecuta el plan de master-prompt-plan.md

**Resultado:** Generación completa de `lti-racc.md` y actualización de `prompts.md`.

---

## Prompt 4 — Fase 1: Descripción del Producto (ejecutado internamente)

**Contexto:** Generación de la sección 1 de `lti-racc.md`.

> Actúa como Product Manager Senior de LTI, una startup de ATS. Genera la sección 1 del documento LTI-RACC.md con: (a) descripción breve del software en máx. 150 palabras, (b) valor añadido diferencial frente a Greenhouse, Lever y Workday, (c) mínimo 4 ventajas competitivas clave enfocadas en IA, colaboración en tiempo real y automatización, (d) listado y explicación de las funciones principales del sistema, (e) Diagrama Lean Canvas en formato tabla Markdown con los 9 bloques estándar y diagrama Mermaid.

**Artefactos generados:**
- Descripción breve (< 150 palabras)
- Tabla comparativa frente a competidores
- 6 ventajas competitivas
- Tabla de 10 funciones principales
- Tabla Lean Canvas (9 bloques)
- Diagrama Mermaid del Lean Canvas

---

## Prompt 5 — Fase 2: Casos de Uso (ejecutado internamente)

**Contexto:** Generación de los 3 casos de uso principales con diagramas UML.

> Basándote en el ciclo de reclutamiento de LTI (Creating Jobs → Published → Applications Received → Reviewed → Tests → Interviews → Hired), define los 3 casos de uso más representativos del sistema. Para cada uno incluye: nombre, descripción, actores, flujo principal paso a paso, flujos alternativos y un diagrama en Mermaid. Elige casos de uso que cubran distintas fases del ciclo.

**Casos de uso generados:**
- CU-01: Publicación de oferta de trabajo con asistencia de IA (diagrama `graph TD`)
- CU-02: Revisión colaborativa de candidatos (diagrama `sequenceDiagram`)
- CU-03: Programación automatizada de entrevistas (diagrama `sequenceDiagram`)

---

## Prompt 6 — Fase 3: Modelo de Datos (ejecutado internamente)

**Contexto:** Generación del modelo de datos completo con diagrama ER.

> Diseña el modelo de datos para el ATS de LTI. Lista todas las entidades necesarias con sus atributos (nombre y tipo de dato). Define las relaciones entre entidades indicando cardinalidad. Genera un diagrama entidad-relación en Mermaid usando la sintaxis erDiagram. Las entidades deben cubrir al menos: Job, Candidate, Application, Interview, User, Company, PipelineStage, Assessment.

**Artefactos generados:**
- 11 entidades con atributos tipados: Company, User, Job, JobPublication, Candidate, Application, PipelineStage, Scorecard, Interview, InterviewParticipant, Assessment, CommunicationLog
- Tabla de 16 relaciones con cardinalidad
- Diagrama `erDiagram` en Mermaid

---

## Prompt 7 — Fase 4: Diseño del Sistema a Alto Nivel (ejecutado internamente)

**Contexto:** Generación de la arquitectura de alto nivel con justificación y diagrama.

> Diseña la arquitectura de alto nivel del ATS LTI. Justifica la elección arquitectónica. Describe los componentes principales y su responsabilidad. Incluye las integraciones externas relevantes: job boards, proveedor de email, motor de IA/LLM, sistema de calendario, almacenamiento de documentos. Genera un diagrama de arquitectura en Mermaid.

**Artefactos generados:**
- Justificación de arquitectura microservicios event-driven
- Stack tecnológico completo
- Tabla de 14 servicios con responsabilidades
- Tabla de 12 integraciones externas
- Diagrama de arquitectura en Mermaid (`graph TD`)

---

## Prompt 8 — Fase 5: Diagrama C4 (ejecutado internamente)

**Contexto:** Generación del diagrama C4 completo para el AI Assistant Service.

> Genera el diagrama C4 completo para el componente 'AI Assistant Service' del ATS LTI. Incluye los 4 niveles: (1) System Context, (2) Container, (3) Component, (4) Code. Cada nivel debe tener su diagrama Mermaid y una descripción explicativa. El componente elegido es el AI Assistant Service por ser el más diferenciador de LTI.

**Artefactos generados:**
- Nivel 1: System Context (`graph TD`) — LTI en su entorno con usuarios y sistemas externos
- Nivel 2: Container (`graph TD`) — contenedores de LTI con AI Service en contexto
- Nivel 3: Component (`graph TD`) — 8 componentes internos del AI Assistant Service
- Nivel 4: Code (`classDiagram`) — 7 clases del Candidate Scoring Component con métodos y relaciones
