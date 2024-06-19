# Dockerised Mindustry Server

[![MegaLinter](https://github.com/laywill/Mindustry-Server-Docker/actions/workflows/mega-linter.yml/badge.svg)](https://github.com/laywill/Mindustry-Server-Docker/actions/workflows/mega-linter.yml)

## Dependencies

- Windows:
  - Docker Desktop installed
- Linux:
  - Docker Engine installed
  - Docker Compose installed

## Running

```bash
docker compose run -p 6567:6567 --rm mindustry
```

This will capture your terminal and bring you into an interactive TTY.
From here you are within the Mindustry Server application and can control it as normal.
