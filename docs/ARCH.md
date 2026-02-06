# Turnos Vet - ARCH

## Stack (target)
Backend:
- Java 21, Spring Boot 3 (Maven)
- PostgreSQL
- Flyway
- Spring Security + JWT (HMAC)
- Spring Web + Validation
- Spring Data JPA
- OpenAPI (springdoc)
- Actuator health

Planificado (no Sprint 0):
- Docker Compose local
- GitHub Actions CI (mvn test)

Frontend:
- No en Sprint 0 (API first).

## Repo layout (target)
```text
/
  docs/
  tasks/
  backend/ (cuando exista)
  docker-compose.yml (planificado)
  .github/workflows/ci.yml (planificado)
  .env.example (planificado)
```

## Capas
- Controller: REST + DTO + validación.
- Service: reglas de negocio, transacciones.
- Repository: JPA queries.
- Domain: entidades + enums.
- DTOs: request/response.

## Multi-tenancy
Modelo: shared DB + shared schema con `tenant_id` en tablas del dominio.
- JWT incluye `tenantId`.
- Scoping obligatorio por tenant en queries (excepto PLATFORM_SUPERADMIN).

## API (endpoints ES, código EN)
- Base path: `/api/v1`

Recursos (propuestos):
- `/tenants` (plataforma)
- `/sucursales`
- `/salas`
- `/servicios`
- `/staff`
- `/clientes`
- `/mascotas`
- `/turnos`

Errores: JSON estándar con `codigo`, `mensaje`, `detalles`, `traceId` opcional.

## Tiempo
- DB: `timestamptz` UTC
- API: ISO-8601 con offset
- Timezone por tenant (IANA), default `America/Guayaquil`
