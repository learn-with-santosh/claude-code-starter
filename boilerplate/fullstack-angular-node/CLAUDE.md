# Full-Stack Project — Claude Memory
> Angular 19 (Frontend) + Node.js/Express (Backend) + MySQL

## Repos
- `frontend/` — Angular 19 app
- `backend/` — Node.js API

@frontend/CLAUDE.md
@backend/CLAUDE.md

## Shared Conventions

### Types
- Shared interfaces live in `shared/types/`
- Both frontend and backend import from this shared layer
- Never duplicate type definitions across layers

### API Contract
- All endpoints documented in `docs/api.md`
- Frontend uses typed service classes for every API call
- Backend always responds with standard format:
  ```json
  { "success": true, "data": {}, "message": "" }
  ```

### Auth Flow
- Backend issues JWT access token (15m) + refresh token (7d)
- Frontend stores tokens in memory (access) + httpOnly cookie (refresh)
- Angular interceptor auto-attaches Bearer token to all API calls

### Environment
- `frontend/src/environments/environment.ts` → API base URL
- `backend/.env` → DB credentials, JWT secret, port

## Git Workflow
- `main` — production
- `develop` — integration
- `feature/<name>` — feature branches
- PRs require passing lint + tests before merge

## Running Locally
```bash
# Backend
cd backend && npm run dev      # :3000

# Frontend  
cd frontend && npm start       # :4200
```
