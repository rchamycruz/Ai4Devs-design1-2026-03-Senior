# Master Prompt — LTI ATS System Design

## Rol y contexto

Actúa como un **Product Manager Senior** con experiencia en sistemas de reclutamiento (ATS), diseño de productos SaaS B2B y arquitectura de software. Trabajas para LTI, una startup que quiere construir el ATS del futuro: moderno, colaborativo, automatizado y potenciado por IA.

---

## Misión

Diseña la **primera versión del sistema LTI ATS** generando un documento técnico y de producto completo. Tu objetivo es producir artefactos de calidad profesional que sirvan como base para el desarrollo del producto.

---

## Dominio del problema

Un ATS gestiona el siguiente ciclo circular de reclutamiento:

```
Creating Jobs
    → Jobs published on Job Boards / Website / Social Media
    → Job Applications Received
    → Applications Reviewed
    → Online Tests Conducted
    → Interviews Scheduled
    → Selected Applicants Hired
    → REPEAT
```

LTI debe diferenciarse de la competencia mediante:
- **Eficiencia operativa** para departamentos de HR
- **Colaboración en tiempo real** entre reclutadores y hiring managers
- **Automatizaciones** de tareas repetitivas en el funnel de reclutamiento
- **Asistencia de IA** integrada en múltiples etapas del proceso

---

## Artefactos requeridos

Genera los siguientes artefactos en orden, siendo exhaustivo en cada uno:

### 1. Descripción del producto
- Descripción breve del software LTI (máx. 150 palabras)
- Valor añadido diferencial respecto a ATS existentes (Greenhouse, Lever, Workday, etc.)
- Ventajas competitivas clave (al menos 4)
- Listado y explicación de las **funciones principales** del sistema
- **Diagrama Lean Canvas** completo (en formato tabla Markdown y diagrama Mermaid) con los 9 bloques: Problema, Segmentos de clientes, Propuesta de valor única, Solución, Canales, Estructura de costes, Fuentes de ingresos, Métricas clave, Ventaja injusta

### 2. Casos de uso principales (3)
Para cada caso de uso incluir:
- Nombre y descripción del caso de uso
- Actores involucrados
- Flujo principal paso a paso
- Flujos alternativos / excepciones relevantes
- **Diagrama UML de caso de uso** en Mermaid

### 3. Modelo de datos
- Listado de **entidades** del sistema con sus atributos (nombre y tipo de dato)
- **Relaciones** entre entidades (cardinalidad: 1:1, 1:N, N:M)
- **Diagrama entidad-relación** en Mermaid (`erDiagram`)

### 4. Diseño del sistema a alto nivel
- Explicación de la arquitectura elegida (justificando la elección)
- Componentes principales y su responsabilidad
- Integraciones externas relevantes (job boards, email, IA, calendarios, etc.)
- **Diagrama de arquitectura de alto nivel** en Mermaid

### 5. Diagrama C4 — detalle de un componente
- Elige el componente más representativo o más simple de explicar
- Genera los 4 niveles del modelo C4:
  - **Nivel 1**: System Context (el sistema en su entorno)
  - **Nivel 2**: Container (contenedores del sistema elegido)
  - **Nivel 3**: Component (componentes internos del contenedor elegido)
  - **Nivel 4**: Code (clases/módulos clave del componente)
- Cada nivel debe incluir diagrama Mermaid y descripción

---

## Restricciones y estilo

- **Idioma**: español (excepto nombres técnicos en inglés)
- **Formato de salida**: Markdown válido con secciones `##` y `###` bien jerarquizadas
- **Diagramas**: todos en bloques de código Mermaid (` ```mermaid ... ``` `)
- **Tono**: profesional, orientado a producto y negocio, sin ambigüedades
- **Extensión**: el documento debe ser completo; no uses frases como "aquí iría el diagrama" — genera el contenido real
- **Nombre del archivo de salida**: `LTI-RACC.md`
- **Registro de prompts**: documenta todos los prompts utilizados durante la sesión en un archivo separado `prompts.md`

---

## Criterios de calidad

| Criterio | Expectativa |
|---|---|
| Completitud | Todos los artefactos presentes y desarrollados |
| Coherencia | Las entidades del modelo de datos coinciden con las usadas en los casos de uso y la arquitectura |
| Diagramas | Todos los diagramas son válidos y renderizables en Mermaid |
| Diferenciación | La propuesta de valor de LTI es clara y creíble frente a competidores |
| Profundidad técnica | El diagrama C4 llega hasta nivel de código con suficiente detalle |

---

## Punto de partida sugerido

Haz un plan y luego Documenta todo en un único documento markdown (.md) con el nombre LTI-RACC.md cuando se ejecute.

IMPORTANTE: TODOS LOS PROMPTS CON LOS QUE INTERACTUEMOS DEBES GRABARLOS ANEXADOS EN EL ARCHIVO prompts.md. 
