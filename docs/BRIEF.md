# Turnos Vet - BRIEF

## Resumen
Sistema SaaS **multi-tenant** para clínicas/veterinarias con:
- **Booking público**: clientes (dueños) reservan turnos para sus **mascotas**.
- **Multi-sucursal**: agenda por sucursal.
- Recursos atendiendo turnos: **Staff + Room (sala/box)**.
- Reglas: **no solapamiento por staff y por room**.

Defaults:
- Timezone por tenant: `America/Guayaquil` (configurable).
- DB: `timestamptz` UTC. API: ISO-8601 con offset.

## Roles (MVP)
- PLATFORM_SUPERADMIN: administra tenants (plataforma).
- TENANT_OWNER: administra el negocio (su tenant).
- BRANCH_ADMIN: administra una sucursal.
- STAFF: gestiona agenda según permisos.
- CLIENTE: dueño que reserva turnos y gestiona sus mascotas.

## Entidades mínimas (MVP)
- Tenant (Negocio)
- Branch (Sucursal)
- User (Staff)
- RoleAssignment (user-branch-role)
- Cliente (Dueño)
- Mascota
- Room (Sala/Box)
- Service (Servicio)
- Appointment (Turno)

## Reglas de turnos (MVP)
### Solapamientos
Prohibido solapamiento:
- Por STAFF dentro de una sucursal.
- Por ROOM dentro de una sucursal.

### Horarios de atención
Validar contra BusinessHours semanal por sucursal (sin feriados/excepciones en MVP).

### Estados del turno (API en ES)
RESERVADO, CONFIRMADO, CANCELADO, COMPLETADO, NO_ASISTIO, REPROGRAMADO

`PENDIENTE` queda fuera del MVP por ahora.

## Fuera de alcance (no MVP)
- Pagos/facturación.
- Notificaciones (WhatsApp/Email/SMS).
- Integraciones externas (Google Calendar).
- Multi-tenant por schema/db (avanzado).
- Feriados/excepciones de horario.
