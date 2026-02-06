# CONVENTIONS

## Reglas generales
- Tickets en `tasks/M-XX-*.md` (XX con cero a la izquierda).
- Cada ticket define: objetivo, alcance sí/no, criterios de aceptación, archivos esperados, comandos de validación.
- Al cerrar ticket: actualizar `docs/STATE.md`.

## Idioma
- Endpoints y recursos: Español (plural).
- Código (paquetes/clases/variables): Inglés.

## API
- Base: `/api/v1`
- Plurales: `/clientes`, `/mascotas`, `/turnos`, etc.
- DTOs request: `XxxCreateRequest`, `XxxUpdateRequest`
- DTOs response: `XxxResponse`
- Errores: `{ "codigo": "...", "mensaje": "...", "detalles": [], "traceId": "..." }`

## Naming en backend (cuando exista)
Paquetes sugeridos:
- `...web` (controllers)
- `...service`
- `...repo`
- `...domain`
- `...dto`

## Git / commits
Commits estilo:
- `chore: ...`
- `docs: ...`
- `feat: ...`
- `fix: ...`
- `test: ...`
