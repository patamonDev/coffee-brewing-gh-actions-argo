# Brew Guide

A simple static web app about coffee and brewing methods, served by nginx in a container.

## Run locally

```bash
docker build -t brew-guide .
docker run --rm -p 8080:8080 brew-guide
```

Open http://localhost:8080.

## Notes for deployment

- Container port: `8080`
- Health check endpoint: `GET /healthz` (returns `200 ok`), suitable for liveness/readiness probes
- Runs as a non-root user (nginx-unprivileged), compatible with restrictive Pod security contexts
