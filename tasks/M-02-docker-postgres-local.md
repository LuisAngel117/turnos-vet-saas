# tasks/M-02-docker-postgres-local.md

## Objetivo
Levantar PostgreSQL local con Docker Compose, con persistencia, healthcheck y variables de entorno estandarizadas para Sprint 0.

## Alcance (Sí)
- Crear/actualizar `docker-compose.yml` en raíz con servicio `postgres`
- Crear `.env.example` en raíz con variables necesarias
- Documentar en `README.md` cómo:
  - copiar `.env.example` a `.env`
  - levantar/bajar Postgres
  - verificar salud del contenedor
- Añadir un healthcheck para que `docker compose ps` muestre `healthy`
- Actualizar `docs/STATE.md` al cerrar el ticket (Hecho / En progreso / Próximo máx 3)

## Alcance (No)
- No crear proyecto Spring Boot todavía
- No configurar datasource en backend todavía
- No agregar pgAdmin
- No CI todavía

## Convenciones y defaults
- Imagen: `postgres:16-alpine`
- Contenedor: `turnosvet-postgres`
- Puerto host configurable vía `.env` (default 5432)
- Volumen nombrado para persistencia (no bind mount)
- Variables en `.env.example` (NO commitear `.env`)

## Criterios de aceptación
1) `docker compose up -d` levanta Postgres sin errores.
2) `docker compose ps` muestra el servicio `postgres` en estado `healthy`.
3) Los datos persisten al reiniciar contenedor (por volumen).
4) Existe `.env.example` con valores default razonables.
5) README explica comandos exactos.
6) `docs/STATE.md` queda actualizado con:
   - Hecho: M-01, M-02
   - En progreso: Sprint 0
   - Próximo (máx 3): M-03, M-04, M-05

## Archivos esperados
- docker-compose.yml
- .env.example
- README.md (sección “Local DB / Postgres”)
- docs/STATE.md

## Implementación requerida (contenido exacto)

### .env.example (en raíz)
```env
# Postgres (local via Docker)
POSTGRES_DB=turnosvet
POSTGRES_USER=turnosvet
POSTGRES_PASSWORD=turnosvet_dev_password
POSTGRES_PORT=5432
