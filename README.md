<div>
  <h1 align="center">Project Name</h1>
  <p align="center">A brief description of what the project does and its purpose.</p>
  <img src="https://img.shields.io/npm/last-update/24" alt="License">
  <p align="center">
    <a href="./docs/getting_started.md">Installation</a> |
    <a href="./CONTRIBUTING.md">Contributing</a> |
    <a href="./docs/license.md">License</a> |
    <a href="./CODE_OF_CONDUCT.md">Code of Conduct</a> |
    <a href="./CHANGELOG.md">Changelog</a> |
    <a href="./SECURITY.md">Security</a> |
    <a href="./docs/api_reference.md">API Reference</a> |
    <a href="./docs/troubleshooting.md">Troubleshooting</a> |
    <a href="./docs/configuration.md">Configuration</a>
  </p>
</div>

## Description

A brief description of what the project does and its purpose.

## Documentation

<details>
<summary>Additional Information</summary>

<!-- пустий рядок обов'язковий перед Markdown всередині -->

- [Installation](./docs/getting_started.md)
- [Contributing](./CONTRIBUTING.md) ![Contributing](https://img.shields.io/badge/Contributing-Welcome-brightgreen.svg)
- [License](./docs/license.md) ![License](https://img.shields.io/badge/License-MIT-yellow.svg)
- [Code of Conduct](./CODE_OF_CONDUCT.md)
- [Changelog](./CHANGELOG.md)
- [Security](./SECURITY.md)
- [Api-Reference](./docs/api_reference.md)
- [Troubleshooting](./docs/troubleshooting.md)
- [Configuration](./docs/configuration.md)
  - [Environment Variables](#environment-variables)
  - [Database Setup](#database-setup)

</details>  

## Посилання на конкретний розділ іншого файлу

See [Configuration](./docs/configuration.md#environment-variables)
See example get user endpoint in [API Reference](./docs/api-reference.md#get-users)

## Shortcuts

<kbd>Ctrl</kbd> + <kbd>K</kbd> - Open Command Palette</br>
<kbd>Ctrl</kbd> + <kbd>P</kbd> - Quick Open</br>
<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd> - Show All Commands</br>
<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>O</kbd> - Go to Symbol</br>

```mermaid
erDiagram
    USER {
        int    id      PK
        string email   UK
        string name
        date   created_at
    }
    POST {
        int    id        PK
        int    author_id FK
        string title
        text   content
        bool   published
    }
    COMMENT {
        int    id      PK
        int    post_id FK
        int    user_id FK
        text   body
    }

    USER  ||--o{ POST    : "writes"
    POST  ||--o{ COMMENT : "has"
    USER  ||--o{ COMMENT : "leaves"
```

```mermaid
gantt
    title Project Roadmap Q3-Q4
    dateFormat  YYYY-MM-DD
    section Backend
        Auth API         :done,    auth,  2025-07-01, 2025-07-14
        REST Endpoints   :done,    rest,  2025-07-10, 2025-07-28
        WebSocket        :active,  ws,    2025-07-25, 2025-08-10
        GraphQL          :         gql,   2025-08-05, 2025-08-25
    section Frontend
        Login UI         :done,           2025-07-15, 2025-07-20
        Dashboard        :active,         2025-07-20, 2025-08-12
        Mobile app       :crit,           2025-08-10, 2025-09-01
```

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
    checkout main
    merge develop id: "v1.0.0" tag: "v1.0.0"
```
