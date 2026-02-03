# Room Reservations API

Sistema de gestión de reservas de salas de reuniones.

## Requisitos

- Ruby 3.2+
- Bundler

## Setup

```bash
# Instalar dependencias
bundle install

# Crear base de datos
rails db:migrate

# Verificar que funciona
bundle exec rspec
```

## Comandos Útiles

```bash
# Ejecutar tests
bundle exec rspec

# Ejecutar tests con detalle
bundle exec rspec --format documentation

# Levantar servidor
rails server

# Consola interactiva
rails console
```

## Estructura del Proyecto

```
app/
  models/
    room.rb           # Modelo de sala
    user.rb           # Modelo de usuario
    reservation.rb    # Modelo de reserva
  controllers/
    api/v1/           # Controladores API (por implementar)
spec/
  models/             # Tests de modelos
  factories/          # Factories para tests
  requests/           # Tests de API (por implementar)
```

## Documentación

Ver `CLAUDE.md` para instrucciones detalladas sobre las reglas de negocio a implementar.
