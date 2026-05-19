# Architecture

This document collects architecture-related information from existing documentation and presents it in a central place.

Sources:
- API endpoint descriptions from `docs/api-reference.md`
- System and database references from `README.md`
- Branching examples from `README.md` and `CONTRIBUTING.md`

## Overview

The project is built around a Markdown-first documentation platform with a backend API for user management and authentication.

Key architecture points extracted from existing docs:
- The API exposes user lifecycle endpoints such as `GET /users`, `GET /users/{id}`, `PUT /users/{id}`, and `DELETE /users/{id}`.
- Authentication is token-based with `POST /auth/login` and `POST /auth/refresh`.
- The system uses a database to store users and session tokens.
- The README references database setup and system removal flows.
- The Git workflow uses feature branches, a `develop` integration branch, and `main` for releases.

## System architecture

```mermaid
flowchart LR
    Client[Client Application] -->|HTTPS request| API[API Gateway / REST API]
    API -->|Validate credentials| Auth[Auth Service]
    Auth -->|Issue tokens| API
    API -->|Read/write| DB[(User Database)]
    API -->|Read/write| TokenDB[(Refresh Token Store)]
    API -->|Serve docs| Docs[Docs Site]
    Docs -->|Generated site| Storage[(Static Site Output)]
```

## Data model

```mermaid
erDiagram
    USER {
        string id PK
        string name
        string email
        string role
        string passwordHash
        datetime createdAt
        datetime updatedAt
    }
    REFRESH_TOKEN {
        string id PK
        string userId FK
        string token
        datetime expiresAt
        datetime issuedAt
    }

    USER ||--o{ REFRESH_TOKEN : "owns"
```

## Git branching strategy

This strategy is inferred from README examples and contribution guidance.

- `main` is the stable production branch.
- `develop` is the integration branch for completed features.
- `feature/*` branches are used for individual work items.
- Feature branches merge into `develop`, then `develop` merges into `main` for release.

```mermaid
gitGraph
    commit id: "init"
    branch develop
    checkout develop
    commit id: "feat: auth"
    commit id: "feat: api"
    branch feature/payments
    checkout feature/payments
    commit id: "add stripe"
    commit id: "add webhooks"
    checkout develop
    merge feature/payments id: "merge payments"
    commit id: "chore: prepare release"
    checkout main
    merge develop id: "release/v1.0.0" tag: "v1.0.0"
```
