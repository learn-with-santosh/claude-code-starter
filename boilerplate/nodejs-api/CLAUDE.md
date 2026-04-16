# Node.js API — Claude Memory

## Stack
- **Runtime:** Node.js 20+
- **Framework:** Express
- **Language:** TypeScript
- **ORM:** Sequelize
- **Database:** MySQL
- **Auth:** JWT (access + refresh tokens)
- **Package Manager:** npm

## Project Structure
```
src/
  config/        # DB config, env, constants
  controllers/   # Route handlers (thin — no business logic)
  services/      # Business logic layer
  models/        # Sequelize models
  routes/        # Express route definitions
  middlewares/   # Auth, error handler, validators
  utils/         # Helpers, logger, response formatter
  types/         # Shared TypeScript interfaces
index.ts         # Entry point
```

## Conventions

### Controllers
- Thin controllers — only parse req, call service, send response
- Always use `try/catch` and pass errors to `next(err)`

### Services
- All business logic lives here
- Services call models directly (not controllers)
- Return plain objects, not Sequelize instances

### Error Handling
- Centralized error middleware in `middlewares/errorHandler.ts`
- Always throw typed errors: `new AppError('message', statusCode)`
- Never send raw error messages to client in production

### Response Format
```json
{
  "success": true,
  "data": {},
  "message": "OK"
}
```

### Naming
- Files: kebab-case (`user.service.ts`)
- Classes: PascalCase (`UserService`)
- Routes: REST conventions (`GET /users`, `POST /users`, `PUT /users/:id`)

## Commands
```bash
npm run dev       # Nodemon dev server
npm run build     # Compile TypeScript
npm start         # Run compiled JS
npm test          # Jest tests
npm run migrate   # Sequelize migrations
npm run seed      # Sequelize seeders
```

## Database
- Migrations required for all schema changes — no raw ALTER TABLE
- Always define indexes on foreign keys
- Use Sequelize `paranoid: true` for soft deletes

## Security Rules
- Validate all inputs with Zod or express-validator
- Never log passwords, tokens, or PII
- Rate-limit all public endpoints
- Sanitize before any raw query usage
