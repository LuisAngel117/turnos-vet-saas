# Turnos Vet - DECISIONS (ADRs)

## ADR-0001 - Stack base
Status: Proposed
Decision: Java 21 + Spring Boot 3 + Maven, PostgreSQL, Flyway, Spring Security, JWT (HMAC), OpenAPI (springdoc), Actuator, GitHub Actions CI.

## ADR-0002 - Multi-tenancy
Status: Proposed
Decision: shared DB + shared schema con `tenant_id` en tablas del dominio; scoping por `tenantId` desde JWT.
Rationale: MVP SaaS más simple.

## ADR-0003 - Idioma: endpoints ES, code EN
Status: Proposed
Decision: rutas y payloads en español; nombres internos (paquetes/clases) en inglés.
Rationale: claridad para usuario + estándar profesional.

## ADR-0004 - Auth: staff y clientes
Status: Proposed
Decision: JWT para STAFF y CLIENTE con claims que incluyan `tenantId` y `tipoUsuario`.
Rationale: booking público requiere clientes autenticados.

## ADR-0005 - Tiempo
Status: Proposed
Decision: guardar en UTC `timestamptz` y transportar ISO-8601 con offset; timezone IANA por tenant (default `America/Guayaquil`).
