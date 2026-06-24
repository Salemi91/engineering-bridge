# Engineering Bridge

**Engineering Bridge** es un flujo liviano para transformar documentación de arquitectura en especificaciones ejecutables de ingeniería.

Su objetivo es ayudar a que los equipos pasen de una decisión o necesidad técnica a tareas implementables, sin perder trazabilidad entre:

```text
requisitos → diseño → tareas → código → pruebas → documentación
```

Funciona especialmente bien junto con [Architect Journey](https://github.com/Salemi91/architect-journey), pero puede usarse con cualquier proceso de documentación.

> Kiro puede usarse como herramienta opcional.
> Este repositorio no depende de Kiro.

---

## Problema que resuelve

En muchos equipos ocurre esto:

```text
Se documenta al inicio
        ↓
Se empieza a desarrollar
        ↓
El código cambia
        ↓
La documentación queda desactualizada
```

Engineering Bridge propone un puente simple:

```text
Arquitectura
PRD / RFC / ADR / C4 / Technical Brief
        ↓
Engineering Bridge
requirements.md / design.md / tasks.md / traceability.md
        ↓
Implementación
código / pruebas / observabilidad / documentación actualizada
```

---

## Qué es

Engineering Bridge es:

* Un puente entre arquitectura y desarrollo.
* Un flujo simple basado en Markdown.
* Una forma de ordenar el trabajo antes de implementar.
* Una guía para trabajar con personas o asistentes de IA.
* Un mecanismo para mantener trazabilidad técnica.

---

## Qué no es

Engineering Bridge no es:

* Un reemplazo de Architect Journey.
* Un reemplazo de Kiro.
* Un framework pesado de documentación.
* Un proceso atado a un IDE.
* Un duplicado de PRDs, RFCs, ADRs o diagramas C4.

---

## Flujo principal

```text
1. Entender el contexto
   docs/context/product.md
   docs/context/tech.md
   docs/context/structure.md

2. Elegir el tipo de trabajo
   Nueva funcionalidad
   Corrección de error
   Cambio arquitectónico
   Onboarding de proyecto existente

3. Crear una especificación
   specs/<nombre-del-cambio>/

4. Completar los artefactos mínimos
   requirements.md
   design.md
   tasks.md

5. Implementar, probar y actualizar documentación
```

---

## Artefactos principales

| Archivo           | Para qué sirve                                                          |
| ----------------- | ----------------------------------------------------------------------- |
| `requirements.md` | Define qué debe hacer el sistema                                        |
| `design.md`       | Explica cómo se va a implementar                                        |
| `tasks.md`        | Divide el trabajo en tareas pequeñas                                    |
| `bugfix.md`       | Describe un error, el comportamiento esperado y lo que no debe romperse |
| `traceability.md` | Conecta requisitos, decisiones, código, pruebas y documentación         |

---

## Estructura del repositorio

```text
engineering-bridge/
  README.md
  AGENTS.md

  docs/
    vision.md
    how-it-works.md
    context/
      product.md
      tech.md
      structure.md

  workflows/
    new-feature.md
    bugfix.md
    architecture-change.md
    existing-project-onboarding.md

  templates/
    feature-spec/
      requirements.md
      design.md
      tasks.md

    bugfix-spec/
      bugfix.md
      design.md
      tasks.md

    traceability/
      traceability.md
      docs-sync-checklist.md

  examples/
    java-springboot-feature/

  automation-recipes/
    kiro-optional.md
    github-actions.md
    opencode.md

  .kiro/
    steering/
      product.md
      tech.md
      structure.md
```

---

## Relación con Architect Journey

La regla es simple:

```text
Architect Journey explica el porqué y las decisiones.

Engineering Bridge explica cómo llevar eso a implementación.
```

| Tipo de artefacto | Vive principalmente en                 |
| ----------------- | -------------------------------------- |
| PRD               | Architect Journey                      |
| RFC               | Architect Journey                      |
| ADR               | Architect Journey                      |
| C4                | Architect Journey                      |
| Technical Brief   | Architect Journey o Engineering Bridge |
| requirements.md   | Engineering Bridge                     |
| design.md         | Engineering Bridge                     |
| tasks.md          | Engineering Bridge                     |
| bugfix.md         | Engineering Bridge                     |
| traceability.md   | Engineering Bridge                     |

---

## Uso opcional con Kiro

Kiro puede aprovechar esta estructura mediante archivos de contexto.

Fuente principal del repo:

```text
docs/context/product.md
docs/context/tech.md
docs/context/structure.md
```

Compatibilidad opcional con Kiro:

```text
.kiro/steering/product.md
.kiro/steering/tech.md
.kiro/steering/structure.md
```

Esto permite usar Engineering Bridge con Kiro, ChatGPT, Claude, OpenCode, Copilot o un flujo manual.

---

## Inicio rápido

### 1. Completar el contexto

```text
docs/context/product.md
docs/context/tech.md
docs/context/structure.md
```

### 2. Crear una carpeta para el cambio

```text
specs/<nombre-del-cambio>/
```

Ejemplo:

```text
specs/generate-salary-receipt/
```

### 3. Copiar un template

Para una nueva funcionalidad:

```text
templates/feature-spec/requirements.md
templates/feature-spec/design.md
templates/feature-spec/tasks.md
```

Para una corrección de error:

```text
templates/bugfix-spec/bugfix.md
templates/bugfix-spec/design.md
templates/bugfix-spec/tasks.md
```

### 4. Verificar antes de implementar

```text
[ ] Los requisitos están claros.
[ ] El diseño técnico es suficiente.
[ ] Las tareas son pequeñas.
[ ] Las pruebas fueron identificadas.
[ ] El impacto documental fue revisado.
```

---

## Regla principal

No generar código antes de que los requisitos, el diseño y las tareas estén claros.

---

## Licencia

Este proyecto está pensado para ser open source.

Licencia sugerida: MIT.
