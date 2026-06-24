# Cómo funciona

Engineering Bridge trabaja con tres flujos principales.

## 1. Nueva funcionalidad

Usar este flujo cuando el equipo necesita construir una nueva capacidad funcional o técnica.

```text
Entrada: idea, PRD, RFC o Technical Brief
Salida: requirements.md, design.md, tasks.md
```

Carpeta recomendada:

```text
specs/<feature-name>/
  requirements.md
  design.md
  tasks.md
  traceability.md
```

## 2. Corrección de error

Usar este flujo cuando el comportamiento actual es incorrecto y debe corregirse sin romper funcionalidades existentes.

```text
Entrada: reporte de error, logs, comportamiento actual
Salida: bugfix.md, design.md, tasks.md
```

Carpeta recomendada:

```text
specs/<bugfix-name>/
  bugfix.md
  design.md
  tasks.md
```

## 3. Cambio arquitectónico

Usar este flujo cuando cambia una decisión técnica, integración, dependencia, enfoque de despliegue o límite del sistema.

```text
Entrada: RFC, ADR, C4, Technical Brief o restricción técnica
Salida: design.md, tasks.md, docs-sync-checklist.md
```

Carpeta recomendada:

```text
specs/<architecture-change-name>/
  design.md
  tasks.md
  docs-sync-checklist.md
```

## Regla de decisión

Usar el artefacto más pequeño que haga claro el trabajo.

No crear un PRD si una especificación de funcionalidad es suficiente.

No crear un RFC si no hay una decisión arquitectónica relevante.

No crear un ADR si todavía no se tomó una decisión.
