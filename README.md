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
## Local DB (Postgres)

1) Copia variables de entorno:
```bash
cp .env.example .env