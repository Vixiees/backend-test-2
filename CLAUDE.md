# Room Reservations - Technical Test

## Tech Stack

- **Rails 8** (API mode)
- **SQLite** (already configured)
- **RSpec** + **FactoryBot** + **Shoulda Matchers**

## Commands

```bash
bundle exec rspec                          # Run tests
bundle exec rspec spec/models/reservation_spec.rb  # Run specific test
bundle exec rspec --format documentation   # Detailed output
rails server                               # Start server
rails console                              # Console
```

## Business Rules

Each rule can be developed independently (git worktree compatible).

### BR1: No overlapping reservations
There cannot be two active reservations for the same room at the same time.

### BR2: Maximum duration of 4 hours
A reservation cannot last more than 4 hours.

### BR3: Business hours only
Reservations must be between 9:00 AM and 6:00 PM, Monday through Friday.

### BR4: Capacity restriction
Regular users can only book rooms with capacity ≤ their `max_capacity_allowed`. Admins can book any room.

### BR5: Maximum 3 active reservations
A regular user cannot have more than 3 active reservations (future, not cancelled). Admins have no limit.

### BR6: Advance cancellation
A reservation can only be cancelled if there are more than 60 minutes until start time.

### BR7: Recurring reservations
When creating recurring reservations, all occurrences must comply with the rules. If any fails, none are created.

## API Endpoints

```
GET    /api/v1/rooms
GET    /api/v1/rooms/:id
POST   /api/v1/rooms (admin only)
GET    /api/v1/rooms/:id/availability?date=YYYY-MM-DD

GET    /api/v1/users
POST   /api/v1/users
GET    /api/v1/users/:id

GET    /api/v1/reservations
POST   /api/v1/reservations
GET    /api/v1/reservations/:id
PATCH  /api/v1/reservations/:id/cancel
```
