# tasks/M-01-bootstrap-docs.md

## Objetivo
Dejar el repositorio listo para Sprint 0 con documentación base consistente y reglas de trabajo claras (docs + convenciones), sin implementar backend todavía.

## Alcance (Sí)
- Población de:
  - docs/BRIEF.md
  - docs/ARCH.md
  - docs/DECISIONS.md
  - docs/STATE.md
  - docs/CONVENTIONS.md
- README.md mínimo con propósito del repo y cómo se trabajará por tickets
- Asegurar consistencia: dominio veterinaria, booking público, multi-sucursal, multi-tenant, staff+room, endpoints ES y código EN.

## Alcance (No)
- No crear proyecto Spring Boot todavía
- No docker-compose todavía
- No CI todavía

## Defaults cerrados (para evitar ambigüedad)
- Timezone por tenant: `America/Guayaquil` (puede cambiarse después en ADR)
- Tiempo en DB: `timestamptz` UTC; API ISO-8601 con offset
- Estados de turno (API ES): RESERVADO, CONFIRMADO, CANCELADO, COMPLETADO, NO_ASISTIO, REPROGRAMADO
- `PENDIENTE`: fuera del MVP por ahora

## Criterios de aceptación
- Los 5 archivos en docs/ existen y tienen contenido completo (no placeholders).
- README.md existe y explica el flujo de trabajo (tickets en tasks/).
- docs/STATE.md queda con:
  - Hecho: M-01 (cuando se cierre)
  - En progreso: Sprint 0
  - Próximo (máx 3): M-02, M-03, M-04

## Archivos esperados
- README.md
- docs/BRIEF.md
- docs/ARCH.md
- docs/DECISIONS.md
- docs/STATE.md
- docs/CONVENTIONS.md
- tasks/M-01-bootstrap-docs.md (este mismo)

## Contenido exacto a escribir

### README.md
```md
# turnos-vet-saas

SaaS de turnos para veterinarias/clínicas con booking público, multi-sucursal y multi-tenant.

## Cómo trabajamos
- Este repo se construye por tickets pequeños en `tasks/` (M-01, M-02, ...).
- Antes de programar features, cerramos alcance y contratos en `docs/`.
- Cada ticket debe tener: objetivo, alcance sí/no, criterios de aceptación, archivos esperados, comandos de validación.
- Al cerrar un ticket: actualizar `docs/STATE.md` (Hecho / En progreso / Próximo máx 3).

## Docs clave
- `docs/BRIEF.md`: producto y alcance
- `docs/ARCH.md`: arquitectura y estructura
- `docs/DECISIONS.md`: ADRs (decisiones)
- `docs/CONVENTIONS.md`: reglas de naming/rutas/código
- `docs/STATE.md`: estado actual y próximos pasos
