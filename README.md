# Engineering Bridge

**Engineering Bridge** es un flujo de trabajo liviano y agnóstico a herramientas para transformar documentación de arquitectura en especificaciones ejecutables de ingeniería.

Ayuda a los equipos a pasar de la intención arquitectónica a la implementación sin perder trazabilidad entre requisitos, diseño, tareas, código, pruebas y documentación.

```text
Artefactos de arquitectura → especificaciones ejecutables → tareas de implementación → código / pruebas / documentación
```

Engineering Bridge está pensado para trabajar especialmente bien con [Architect Journey](https://github.com/Salemi91/architect-journey), pero también puede usarse con cualquier proceso de documentación existente.

Kiro puede usarse como herramienta opcional. Este repositorio no depende de Kiro.

---

## Por qué existe este repo

Los equipos de ingeniería suelen tener dos problemas frecuentes:

1. La documentación de arquitectura se crea al inicio y luego queda desactualizada.
2. La implementación empieza antes de que los requisitos, los límites técnicos y el impacto documental estén claros.

Engineering Bridge busca cubrir ese espacio con un conjunto pequeño de artefactos en Markdown que conectan decisiones de arquitectura con trabajo implementable.

El objetivo no es crear más documentación.

El objetivo es que la documentación sea útil, trazable y cercana al desarrollo real.

---

## Qué es Engineering Bridge

Engineering Bridge es:

- Un puente entre documentación de arquitectura y ejecución técnica.
- Un flujo simple en Markdown para equipos técnicos, arquitectos y asistentes de IA.
- Una estructura reusable para nuevas funcionalidades, corrección de errores y cambios arquitectónicos.
- Una forma de mantener alineados requisitos, diseño, código, pruebas y documentación.
- Un enfoque agnóstico a herramientas que puede funcionar con Kiro, ChatGPT, Claude, OpenCode, Copilot o flujos manuales.

## Qué no es Engineering Bridge

Engineering Bridge no es:

- Un reemplazo de Architect Journey.
- Un reemplazo de Kiro.
- Un proceso atado a un IDE específico.
- Un framework pesado de documentación empresarial.
- Un duplicado de PRDs, RFCs, ADRs o diagramas C4.

---

## Idea central

Los artefactos de arquitectura deben definir contexto y decisiones.

Las especificaciones de ingeniería deben traducir esas decisiones en trabajo implementable.

```text
Architect Journey
  PRD / RFC / ADR / C4 / Technical Brief
        ↓
Engineering Bridge
  requirements.md / design.md / tasks.md / traceability.md
        ↓
Implementación
  código / pruebas / observabilidad / actualización documental
```

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
      requirements.md
      design.md
      tasks.md
      traceability.md

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

## Flujos principales

Engineering Bridge inicia con cuatro flujos básicos.

| Flujo | Cuándo usarlo | Salida |
|---|---|---|
| Nueva funcionalidad | Cuando se necesita implementar un nuevo comportamiento | `requirements.md`, `design.md`, `tasks.md` |
| Corrección de error | Cuando hay que corregir un defecto sin romper comportamiento existente | `bugfix.md`, `design.md`, `tasks.md` |
| Cambio arquitectónico | Cuando cambia una decisión técnica, integración, dependencia, despliegue o límite del sistema | `design.md`, `tasks.md`, checklist documental |
| Onboarding de proyecto existente | Cuando se necesita preparar un código existente para trabajo asistido por IA | archivos de contexto y estructura del proyecto |

---

## Artefactos principales

### `requirements.md`

Define qué debe hacer el sistema usando requisitos claros y verificables.

Formato recomendado:

```text
CUANDO <evento o condición>
EL SISTEMA DEBE <comportamiento esperado>
```

Ejemplo:

```text
CUANDO un usuario solicita generar un documento
EL SISTEMA DEBE validar que existan los datos necesarios antes de iniciar la generación.
```

---

### `design.md`

Explica cómo se implementará el requisito.

Debe cubrir solo lo necesario para que la implementación sea clara:

- módulos o servicios afectados
- flujo principal
- APIs o contratos
- cambios de datos
- manejo de errores
- consideraciones de seguridad
- impacto en observabilidad
- impacto en documentación

---

### `tasks.md`

Divide el trabajo en tareas pequeñas, revisables e implementables.

Una tarea debe ser lo suficientemente concreta como para poder desarrollarse, probarse y revisarse.

---

### `bugfix.md`

Documenta defectos usando tres límites:

- comportamiento actual
- comportamiento esperado
- comportamiento que no debe cambiar

La sección de comportamiento que no debe cambiar es importante porque protege funcionalidades existentes contra regresiones.

---

### `traceability.md`

Conecta la especificación con sus artefactos fuente, implementación y actualizaciones documentales.

Debe usarse cuando el cambio tiene impacto arquitectónico, auditoría, integración o coordinación entre equipos.

---

## Relación con Architect Journey

Architect Journey conserva los artefactos de arquitectura.

Engineering Bridge los consume y los transforma en especificaciones ejecutables.

| Artefacto | Dueño recomendado |
|---|---|
| PRD | Architect Journey |
| RFC | Architect Journey |
| ADR | Architect Journey |
| Modelo C4 | Architect Journey |
| Technical Brief | Architect Journey o Engineering Bridge |
| `requirements.md` | Engineering Bridge |
| `design.md` | Engineering Bridge |
| `tasks.md` | Engineering Bridge |
| `bugfix.md` | Engineering Bridge |
| `traceability.md` | Engineering Bridge |

Regla práctica:

```text
Si el artefacto explica por qué se hace algo o qué decisión se tomó, pertenece a Architect Journey.

Si el artefacto explica cómo implementar, probar y verificar el trabajo, pertenece a Engineering Bridge.
```

---

## Uso opcional con Kiro

Kiro puede usarse junto con Engineering Bridge, pero no es obligatorio.

La carpeta `.kiro/steering/` se incluye solo como una capa opcional de compatibilidad:

```text
.kiro/steering/product.md
.kiro/steering/tech.md
.kiro/steering/structure.md
```

La fuente principal y agnóstica a herramientas es:

```text
docs/context/product.md
docs/context/tech.md
docs/context/structure.md
```

Esto permite que el flujo pueda usarse con distintas herramientas, equipos y niveles de madurez técnica.

---

## Inicio rápido

### 1. Crear el contexto del proyecto

Completar primero estos archivos:

```text
docs/context/product.md
docs/context/tech.md
docs/context/structure.md
```

### 2. Elegir un flujo

Elegir uno:

```text
workflows/new-feature.md
workflows/bugfix.md
workflows/architecture-change.md
workflows/existing-project-onboarding.md
```

### 3. Crear una carpeta de especificación

```text
specs/<nombre-del-cambio>/
```

Ejemplo:

```text
specs/user-notification-preferences/
```

### 4. Copiar el template correspondiente

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

### 5. Implementar solo cuando los límites estén claros

Antes de implementar, verificar:

```text
[ ] Los requisitos están claros.
[ ] Las tareas son lo suficientemente pequeñas.
[ ] El impacto arquitectónico fue identificado.
[ ] Las pruebas necesarias fueron identificadas.
[ ] El impacto documental fue identificado.
```

---

## Primera regla

No generar código antes de que los requisitos, el diseño y las tareas estén lo suficientemente claros como para ser revisados.

---

## Roadmap

Mejoras previstas:

- Agregar más ejemplos reales.
- Agregar un ejemplo mínimo con Java y Spring Boot.
- Agregar checklist de sincronización documental para Pull Requests.
- Agregar recetas opcionales para Kiro hooks.
- Agregar recetas opcionales para OpenCode y GitHub Actions.

---

## Licencia

Este proyecto está pensado para ser open source.

Agregar una licencia antes de publicarlo formalmente.

Recomendación inicial: MIT License.
