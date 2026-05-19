## [Link to Documentation](https://anton-mosquito.github.io/Markdown-/)

<div>
  <h1 align="center">Project Name</h1>
  <p align="center">A brief description of what the project does and its purpose.</p>
  <p align="center"><img src="https://img.shields.io/npm/last-update/24" alt="License"></p>
  <p align="center">
    <a href="./docs/getting_started.md">Installation</a> |
    <a href="./CONTRIBUTING.md">Contributing</a> |
    <a href="./LICENSE">License</a> |
    <a href="./CODE_OF_CONDUCT.md">Code of Conduct</a> |
    <a href="./CHANGELOG.md">Changelog</a> |
    <a href="./SECURITY.md">Security</a> |
    <a href="./docs/api-reference.md">API Reference</a> |
    <a href="./docs/troubleshooting.md">Troubleshooting</a> |
    <a href="./docs/configuration.md">Configuration</a>
  </p>

  [![Markdown quality](https://github.com/Anton-Mosquito/Markdown-/actions/workflows/docs-lint.yml/badge.svg)](https://github.com/Anton-Mosquito/Markdown-/actions/workflows/docs-lint.yml)
  [![Link check](https://github.com/Anton-Mosquito/Markdown-/actions/workflows/link-check.yml/badge.svg)](https://github.com/Anton-Mosquito/Markdown-/actions/workflows/link-check.yml)
  [![Docs deploy](https://github.com/Anton-Mosquito/Markdown-/actions/workflows/deploy-docs.yml/badge.svg)](https://github.com/Anton-Mosquito/Markdown-/actions/workflows/deploy-docs.yml)
  [![Spelling check](https://github.com/Anton-Mosquito/Markdown-/actions/workflows/cspell.yml/badge.svg)](https://github.com/Anton-Mosquito/Markdown-/actions/workflows/cspell.yml)
  <p align="center">
    <img src="https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExMGd6NGpodXFrMTM1cXhkdnprejl3OTk5dm1wYXRodDFuYnlmOHA3aCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/EZr27ZbJwmjE9PGyLN/giphy.gif" alt="Animated project demo" width="720" />
  </p>
</div>

---



## Description

A brief description of what the project does and its purpose.

## Table of Contents

<details>
<summary>List of documents</summary>

<!--  empty string is mandatory before Markdown content -->

- [Installation](./docs/getting_started.md)
- [Contributing](./CONTRIBUTING.md) ![Contributing](https://img.shields.io/badge/Contributing-Welcome-brightgreen.svg)
- [License](./LICENSE) ![License](https://img.shields.io/badge/License-MIT-yellow.svg)
- [Code of Conduct](./CODE_OF_CONDUCT.md)
- [Changelog](./CHANGELOG.md)
- [Security](./SECURITY.md)
- [Api-Reference](./docs/api-reference.md)
- [Troubleshooting](./docs/troubleshooting.md)
- [Configuration](./docs/configuration.md)
  - [Environment Variables](./docs/configuration.md#environment-variables)
  - [Database Setup](./docs/configuration.md#database-setup)

</details>  


## ✨ Features
- **Fast** — processes 10k records/sec
- **Type-safe** — full TypeScript support
  - Auto-generated types from schema
- **Zero dependencies** — only Node.js stdlib
- [x] Production-ready
- [x] 100% test coverage

## Competitive comparison
| Feature                    | Markdown- | MarkoWrite | DocSpark |
| -------------------------- | --------- | ---------- | -------- |
| Markdown-first docs        | ✅         | ⚠️          | ✅        |
| Built-in workflow badges   | ✅         | ❌          | ⚠️        |
| Zero external dependencies | ✅         | ❌          | ❌        |
| TypeScript-friendly        | ✅         | ⚠️          | ✅        |
| Fast static rendering      | ✅         | ✅          | ⚠️        |
| Easy docs deployment       | ✅         | ✅          | ✅        |

## Who uses this
<p align="center">
  <img src="https://via.placeholder.com/120x40?text=Acme+Inc" alt="Acme Inc" />
  <img src="https://via.placeholder.com/120x40?text=Nimbus" alt="Nimbus" />
  <img src="https://via.placeholder.com/120x40?text=PixelWorks" alt="PixelWorks" />
  <img src="https://via.placeholder.com/120x40?text=Quantum+Co" alt="Quantum Co" />
</p>

## Link to Specific Section of Another File

- See [Configuration](./docs/configuration.md#environment-variables)
- See example get user endpoint in [API Reference](./docs/api-reference.md#get-users)
- See actions [![Docs CI](https://github.com/Anton-Mosquito/Markdown-/actions/workflows/docs-lint.yml/badge.svg)](https://github.com/Anton-Mosquito/Markdown-/actions)

## 🚀 Installation
```bash
npm install my-project
```
> [!NOTE]
> Requires Node.js v18+. See [prerequisites](#prerequisites).

## Quick Start
```javascript
import { createClient } from 'my-project';
const client = createClient({ apiKey: 'YOUR_KEY' });
const result = await client.fetch('/users');
```

## Shortcuts

<kbd>Ctrl</kbd> + <kbd>K</kbd> - Open Command Palette</br>
<kbd>Ctrl</kbd> + <kbd>P</kbd> - Quick Open</br>
<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd> - Show All Commands</br>
<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>O</kbd> - Go to Symbol</br>


