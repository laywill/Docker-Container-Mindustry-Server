# Dockerised Mindustry Server

A [Mindustry Server](https://mindustrygame.github.io/wiki/servers/) in a Docker container, with a Docker Compose suitable for running it up locally.

## Badges

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
[![MegaLinter](https://github.com/laywill/Mindustry-Server-Docker/actions/workflows/mega-linter.yml/badge.svg)](https://github.com/laywill/Mindustry-Server-Docker/actions/workflows/mega-linter.yml)

## Dependencies

- Windows:
  - Docker Desktop installed
- Linux:
  - Docker Engine installed
  - Docker Compose installed

## Run Locally

Clone the project

```bash
  git clone https://github.com/laywill/Mindustry-Server-Docker.git
```

Go to the project directory

```bash
  cd Mindustry-Server-Docker
```

Start the server

```bash
  docker compose run -p 6567:6567 --rm mindustry
```

This will capture your terminal and bring you into an interactive TTY.
From here you are within the Mindustry Server application and can control it as normal using [Mindustry Server Commands](https://mindustrygame.github.io/wiki/servers/#dedicated-server-commands).

## Authors

- [@laywill](https://www.github.com/laywill)

## Contributing

Contributions are always welcome!

Raise an issue, create a PR, ensure your pipeline passes, assign me as a reviewer.
