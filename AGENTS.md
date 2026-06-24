# Instrucciones para agentes

Estas instrucciones aplican a cualquier asistente de IA o agente que trabaje dentro de este repositorio.

## Antes de implementar

1. Leer `docs/context/product.md`.
2. Leer `docs/context/tech.md`.
3. Leer `docs/context/structure.md`.
4. Verificar si existe un PRD, RFC, ADR, diagrama C4 o Technical Brief relacionado en Architect Journey.
5. No generar código antes de que `requirements.md` y `tasks.md` estén suficientemente claros.
6. Si la implementación cambia una decisión arquitectónica, sugerir una actualización de ADR.
7. Si la implementación cambia la estructura del sistema, sugerir una actualización de C4 o de estructura.
8. Si la implementación cambia comportamiento funcional, actualizar `requirements.md`.
9. Si la implementación se completa, actualizar el estado en `tasks.md`.

## Reglas de trabajo

- Preferir cortes verticales pequeños antes que cambios grandes y horizontales.
- Mantener los requisitos verificables.
- Declarar los supuestos explícitamente.
- En correcciones de error, preservar el comportamiento que no debe cambiar.
- No introducir dependencias nuevas sin justificación.
- No duplicar documentos de arquitectura; referenciarlos.
- Si hay incertidumbre, escribir la incertidumbre dentro de la especificación.

## Salidas esperadas

Para una nueva funcionalidad, crear o actualizar:

```text
requirements.md
design.md
tasks.md
traceability.md, si corresponde
```

Para una corrección de error, crear o actualizar:

```text
bugfix.md
design.md
tasks.md
notas de regresión, si corresponde
```

Para un cambio arquitectónico, crear o actualizar:

```text
design.md
tasks.md
docs-sync-checklist.md
referencia a ADR o C4, si corresponde
```
