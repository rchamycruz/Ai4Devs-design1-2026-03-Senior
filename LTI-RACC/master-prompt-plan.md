# Plan de Ejecución — LTI ATS (master-prompt.md)

## Objetivo

Generar el documento `LTI-RACC.md` con todos los artefactos de diseño del sistema LTI ATS, siguiendo las instrucciones del `master-prompt.md`. Registrar todos los prompts utilizados en `prompts.md`.

---

## Archivos de salida

| Archivo | Descripción |
|---|---|
| `LTI-RACC/LTI-RACC.md` | Documento principal con todos los artefactos |
| `LTI-RACC/prompts.md` | Registro de todos los prompts utilizados |

---

## Fases de ejecución

### Fase 1 — Descripción del producto

**Prompt a ejecutar:**
> "Actúa como Product Manager Senior de LTI, una startup de ATS. Genera la sección 1 del documento LTI-RACC.md con: (a) descripción breve del software en máx. 150 palabras, (b) valor añadido diferencial frente a Greenhouse, Lever y Workday, (c) mínimo 4 ventajas competitivas clave enfocadas en IA, colaboración en tiempo real y automatización, (d) listado y explicación de las funciones principales del sistema, (e) Diagrama Lean Canvas en formato tabla Markdown con los 9 bloques estándar."

**Entregables de esta fase:**
- Sección `## 1. Descripción del Producto` en `LTI-RACC.md`
- Tabla Lean Canvas completa (9 bloques)
- Diagrama Mermaid del Lean Canvas

**Criterio de calidad:**
- La propuesta de valor debe ser concreta y diferenciada
- Las ventajas competitivas deben hacer referencia explícita a IA y colaboración
- El Lean Canvas debe tener los 9 bloques sin vacíos

---

### Fase 2 — Casos de uso principales (x3)

**Prompt a ejecutar:**
> "Basándote en el ciclo de reclutamiento de LTI (Creating Jobs → Published → Applications Received → Reviewed → Tests → Interviews → Hired), define los 3 casos de uso más representativos del sistema. Para cada uno incluye: nombre, descripción, actores, flujo principal paso a paso, flujos alternativos y un diagrama UML de caso de uso en Mermaid. Elige casos de uso que cubran distintas fases del ciclo."

**Casos de uso sugeridos (ajustables):**
1. Publicación de oferta de trabajo con asistencia de IA
2. Revisión colaborativa de candidatos entre reclutador y hiring manager
3. Programación automatizada de entrevistas

**Entregables de esta fase:**
- Sección `## 2. Casos de Uso` en `LTI-RACC.md`
- 3 subsecciones `### CU-01`, `### CU-02`, `### CU-03`
- 3 diagramas Mermaid (uno por caso de uso)

**Criterio de calidad:**
- Los actores deben ser consistentes entre los 3 casos de uso
- Los flujos alternativos deben contemplar al menos 1 excepción por caso
- Los diagramas deben usar sintaxis `graph TD` o `sequenceDiagram` válida en Mermaid

---

### Fase 3 — Modelo de datos

**Prompt a ejecutar:**
> "Diseña el modelo de datos para el ATS de LTI. Lista todas las entidades necesarias con sus atributos (nombre y tipo de dato). Define las relaciones entre entidades indicando cardinalidad (1:1, 1:N, N:M). Genera un diagrama entidad-relación en Mermaid usando la sintaxis `erDiagram`. Las entidades deben cubrir al menos: Job, Candidate, Application, Interview, User, Company, Pipeline Stage, Assessment."

**Entregables de esta fase:**
- Sección `## 3. Modelo de Datos` en `LTI-RACC.md`
- Tabla de entidades y atributos por entidad
- Diagrama `erDiagram` en Mermaid

**Criterio de calidad:**
- Mínimo 8 entidades
- Cada entidad con mínimo 4 atributos tipados
- Las relaciones deben ser coherentes con los casos de uso de la Fase 2
- No debe haber entidades huérfanas (sin relación)

---

### Fase 4 — Diseño del sistema a alto nivel

**Prompt a ejecutar:**
> "Diseña la arquitectura de alto nivel del ATS LTI. Justifica la elección arquitectónica (microservicios, monolito modular, event-driven, etc.). Describe los componentes principales y su responsabilidad. Incluye las integraciones externas relevantes: job boards (LinkedIn, Indeed), proveedor de email, motor de IA/LLM, sistema de calendario, almacenamiento de documentos. Genera un diagrama de arquitectura en Mermaid usando `graph TD` o `C4Context`."

**Entregables de esta fase:**
- Sección `## 4. Diseño del Sistema` en `LTI-RACC.md`
- Justificación de la arquitectura elegida
- Tabla de componentes con responsabilidades
- Diagrama de arquitectura en Mermaid

**Criterio de calidad:**
- La arquitectura debe justificarse en relación a los requisitos de escalabilidad y colaboración en tiempo real
- Los componentes deben ser coherentes con las entidades del modelo de datos
- Las integraciones externas deben estar explícitamente representadas en el diagrama

---

### Fase 5 — Diagrama C4 (componente seleccionado)

**Componente objetivo:** `AI Assistant Service` (módulo de asistencia IA)
*(Elegido por ser el más diferenciador y suficientemente acotado para los 4 niveles)*

**Prompt a ejecutar:**
> "Genera el diagrama C4 completo para el componente 'AI Assistant Service' del ATS LTI. Incluye los 4 niveles: (1) System Context — el sistema en su entorno con usuarios y sistemas externos, (2) Container — los contenedores del AI Assistant Service, (3) Component — los componentes internos del servicio IA, (4) Code — las clases o módulos clave del componente más relevante. Cada nivel debe tener su diagrama Mermaid y una descripción explicativa."

**Entregables de esta fase:**
- Sección `## 5. Diagrama C4` en `LTI-RACC.md`
- 4 subsecciones: `### Nivel 1`, `### Nivel 2`, `### Nivel 3`, `### Nivel 4`
- 4 diagramas Mermaid (uno por nivel)

**Criterio de calidad:**
- Cada nivel debe añadir detalle sobre el anterior (no repetir)
- El Nivel 4 debe llegar a clases/módulos con métodos o responsabilidades específicas
- El componente elegido debe conectarse con otros componentes ya definidos en la Fase 4

---

### Fase 6 — Ensamblado final y registro de prompts

**Acciones:**
1. Verificar que `LTI-RACC.md` tiene todas las secciones en orden correcto
2. Verificar que todos los diagramas Mermaid tienen sintaxis válida
3. Verificar coherencia cruzada: entidades del modelo de datos = actores/objetos en casos de uso = componentes en arquitectura
4. Crear/actualizar `prompts.md` con todos los prompts utilizados en las fases 1–5, numerados y con su contexto

**Estructura de `prompts.md`:**
```
# Prompts — LTI ATS Design Session

## Prompt 1 — Descripción del Producto
[contexto + prompt completo]

## Prompt 2 — Casos de Uso
[contexto + prompt completo]

## Prompt 3 — Modelo de Datos
[contexto + prompt completo]

## Prompt 4 — Diseño del Sistema
[contexto + prompt completo]

## Prompt 5 — Diagrama C4
[contexto + prompt completo]
```

---

## Estructura final de `LTI-RACC.md`

```
# LTI ATS — Diseño del Sistema

## 1. Descripción del Producto
### 1.1 Descripción breve
### 1.2 Valor añadido y ventajas competitivas
### 1.3 Funciones principales
### 1.4 Lean Canvas

## 2. Casos de Uso Principales
### CU-01: [Nombre]
### CU-02: [Nombre]
### CU-03: [Nombre]

## 3. Modelo de Datos
### 3.1 Entidades y atributos
### 3.2 Relaciones
### 3.3 Diagrama ER

## 4. Diseño del Sistema a Alto Nivel
### 4.1 Arquitectura elegida
### 4.2 Componentes principales
### 4.3 Integraciones externas
### 4.4 Diagrama de arquitectura

## 5. Diagrama C4 — AI Assistant Service
### Nivel 1: System Context
### Nivel 2: Container
### Nivel 3: Component
### Nivel 4: Code
```

---

## Orden de ejecución

```
Fase 1 → Fase 2 → Fase 3 → Fase 4 → Fase 5 → Fase 6
```

Cada fase es secuencial. La coherencia entre fases se verifica en la Fase 6.

---

## Notas

- Si algún diagrama Mermaid falla al renderizar, reescribirlo con sintaxis simplificada (`graph TD` en lugar de `C4Context`)
- Los nombres de entidades y actores deben mantenerse en inglés para consistencia técnica
- El documento final debe superar las 400 líneas de contenido útil
