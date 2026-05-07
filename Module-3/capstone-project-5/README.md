# E-Commerce CI/CD Capstone

React + Express lab application used to demonstrate Docker packaging and
GitHub Actions quality gates.

The application is the deployment subject. The DevOps evidence is the CI,
Docker, and image-publish workflow around it.

## Pipeline Overview

```text
Pull request or push to main
  |
  v
ci.yml
  |-- API: npm ci -> npm test --if-present -> build check
  |-- Webapp: npm ci -> npm test --if-present -> npm run build
  |
  v
docker-publish.yml on main
  |-- Build API Docker image -> push to GHCR
  |-- Build Webapp Docker image -> push to GHCR
```

## What Is Implemented

| Area | Evidence |
|---|---|
| Full-stack app | [ecommerce-platform](ecommerce-platform/) with React webapp and Express API |
| Local runtime | [docker-compose.yml](ecommerce-platform/docker-compose.yml) starts API and webapp |
| API container | [api/Dockerfile](ecommerce-platform/api/Dockerfile) |
| Web container | [webapp/Dockerfile](ecommerce-platform/webapp/Dockerfile) and Nginx config |
| CI workflow | [ci.yml](ecommerce-platform/.github/workflows/ci.yml) |
| Image publishing | [docker-publish.yml](ecommerce-platform/.github/workflows/docker-publish.yml) using Docker Buildx and GHCR |
| API test | [api/__tests__/server.test.js](ecommerce-platform/api/__tests__/server.test.js) |

## Local Run

```bash
cd Module-3/capstone-project-5/ecommerce-platform
JWT_SECRET=change_me docker compose up --build
```

Endpoints:

| Service | URL |
|---|---|
| Webapp | `http://localhost:3000` |
| API health | `http://localhost:3001/health` |

## Current Limits

- No screenshot folder is currently committed for this capstone.
- The workflow publishes images to GHCR, but this folder does not currently include a separate EC2 deploy workflow.
- The CI workflow still uses Node 20 in the nested lab app; update to Node 22/24 before using this as a primary CI/CD example.
- Runtime secrets are represented by local examples; do not commit real `JWT_SECRET` values.

## Evidence To Add Next

- Link to a passing Actions run for `ci.yml`.
- Link to published GHCR packages.
- Add a screenshot of `docker compose ps` and the API health endpoint.
- Add a short deployment note if this lab is later connected to EC2.
