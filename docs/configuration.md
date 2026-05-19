# Configuration

This file documents the environment variables and configuration options used by the project.

## Environment Variables

| Variable                   | Required | Default       | Description                                                            |
| -------------------------- | -------- | ------------- | ---------------------------------------------------------------------- |
| `NODE_ENV`                 | yes      | `development` | Application runtime environment (`development`, `production`, `test`). |
| `PORT`                     | no       | `3000`        | Port for the web server to listen on.                                  |
| `DATABASE_URL`             | yes      | -             | Connection string for the primary database.                            |
| `JWT_SECRET`               | yes      | -             | Secret key used to sign JWT access tokens.                             |
| `JWT_EXPIRES_IN`           | no       | `3600`        | Access token lifetime in seconds.                                      |
| `REFRESH_TOKEN_EXPIRES_IN` | no       | `604800`      | Refresh token lifetime in seconds.                                     |
| `LOG_LEVEL`                | no       | `info`        | Logging verbosity (`error`, `warn`, `info`, `debug`).                  |
| `ALLOWED_ORIGINS`          | no       | `*`           | CORS whitelist for browser clients.                                    |
| `DOCS_BASE_URL`            | no       | `/docs`       | Base URL path for the generated documentation site.                    |
| `NODE_OPTIONS`             | no       | -             | Additional Node.js runtime options.                                    |

## YAML configuration example

Some deployments may prefer YAML-based configuration files instead of environment variables. Example:

```yaml
app:
  env: production
  port: 3000

database:
  url: "postgres://user:password@db.example.com:5432/markdown"

security:
  jwtSecret: "super-secret-key"
  jwtExpiresIn: 3600
  refreshTokenExpiresIn: 604800

logging:
  level: info

cors:
  allowedOrigins:
    - "https://example.com"
    - "https://app.example.com"

docs:
  baseUrl: "/docs"
```

## JSON configuration example

```json
{
  "app": {
    "env": "production",
    "port": 3000
  },
  "database": {
    "url": "postgres://user:password@db.example.com:5432/markdown"
  },
  "security": {
    "jwtSecret": "super-secret-key",
    "jwtExpiresIn": 3600,
    "refreshTokenExpiresIn": 604800
  },
  "logging": {
    "level": "info"
  },
  "cors": {
    "allowedOrigins": [
      "https://example.com",
      "https://app.example.com"
    ]
  },
  "docs": {
    "baseUrl": "/docs"
  }
}
```

## Database Setup

The application expects the `DATABASE_URL` variable to be set to a valid relational database connection string. For example, PostgreSQL:

```bash
export DATABASE_URL="postgres://user:password@localhost:5432/markdown"
```

If your deployment uses a separate YAML configuration file, ensure the database section includes the same connection URL.

## Notes

- Keep `JWT_SECRET` private and never commit it to source control.
- In production, set `ALLOWED_ORIGINS` to the specific domains that require access.
- Use `NODE_ENV=production` to enable production optimizations and stricter error handling.
