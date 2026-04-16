# PHP/MySQL Project — Claude Memory

## Stack
- **Language:** PHP 8.2+
- **Database:** MySQL 8
- **Hosting:** Shared hosting (Hostinger)
- **Frontend:** Vanilla JS / HTML / CSS
- **No framework** — plain PHP with PDO

## Project Structure
```
/
  index.php          # Entry point / router
  config/
    db.php           # PDO connection
    constants.php    # App constants
  includes/
    auth.php         # Session auth helpers
    functions.php    # Shared utilities
  pages/             # Page templates
  api/               # JSON API endpoints
  assets/
    css/
    js/
  .htaccess
```

## Conventions

### Database (PDO)
- Always use prepared statements — never string-interpolate user input into SQL
- PDO connection in `config/db.php`, accessed via singleton or passed as param
- Use transactions for multi-step writes

```php
// CORRECT
$stmt = $pdo->prepare("SELECT * FROM users WHERE email = ?");
$stmt->execute([$email]);

// NEVER DO THIS
$result = $pdo->query("SELECT * FROM users WHERE email = '$email'");
```

### Error Handling
- Production: log errors, show generic message to user
- Never expose stack traces or SQL errors to the browser
- Use `try/catch` for all DB operations

### API Endpoints
- Return JSON: `header('Content-Type: application/json')`
- Standard response:
```php
echo json_encode(['success' => true, 'data' => $data]);
```
- Auth check at top of every protected endpoint

### Sessions & Auth
- Use `session_start()` at top of every page
- Store only user ID + role in session — no sensitive data
- Regenerate session ID on login: `session_regenerate_id(true)`

## Commands
```bash
# Local dev (XAMPP/Laragon)
php -S localhost:8000

# Deploy to Hostinger
# Use File Manager or FTP — no SSH on shared hosting
```

## Security Rules
- Validate + sanitize ALL user inputs
- Use `htmlspecialchars()` for output in HTML
- CSRF token on all POST forms
- Rate-limit login attempts (track in DB or session)

## Do Not Touch
- `config/db.php` credentials — use `.env` equivalent or config constants
- Never commit real credentials to git
