# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Use this yaml to import this project on zerops

```yaml
project:
  name: react-vite
  tags:
    - fast-zerops

services:
  - hostname: app
    type: nodejs@20
    enableSubdomainAccess: true
    buildFromGit: https://github.com/nermalcat69/zeropsfast
```

Zerops.yml which you need in root of your project.

```yaml
zerops:
  - setup: app
    build:
      base: nodejs@20
      buildCommands:
        - pnpm i
        - pnpm run build
      deployFiles:
        - dist
        - server.js
        - public
        - package.json
        - node_modules
    run:
      base: nodejs@20
      ports:
        - port: 3000
          httpSupport: true
      start: pnpm start
```