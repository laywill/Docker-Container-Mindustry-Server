# syntax=docker/dockerfile:1

# Comments are provided throughout this file to help you get started.
# If you need more help, visit the Dockerfile reference guide at
# https://docs.docker.com/engine/reference/builder/

FROM amd64/alpine:20230901
WORKDIR "/"
RUN apk update && \
    apk add --no-cache \
    openjdk17-jre-headless=17.0.11_p9-r0

# App user
ARG APP_USER="mindustry"
ARG APP_UID=1368
RUN adduser --disabled-password --uid "$APP_UID" --no-create-home --gecos "$APP_USER" --shell /sbin/nologin "$APP_USER"

# Download Server binary
ARG APP_VERSION=146
ARG APP_BIN="/opt/server.jar"
RUN wget \
    --quiet \
    --output-document "$APP_BIN" \
    "https://github.com/Anuken/Mindustry/releases/download/v$APP_VERSION/server-release.jar"

# Volumes
ARG DATA_DIR="/mindustry"
RUN mkdir "$DATA_DIR" && \
    chown -R "$APP_USER":"$APP_USER" "$DATA_DIR"
VOLUME ["$DATA_DIR"]

USER "$APP_USER"
WORKDIR "$DATA_DIR"
ENV APP_BIN="$APP_BIN" \
    JAVA_OPT="-Xms8M -Xmx1G"

# Healthcheck: If Java is running, assume all ok.
HEALTHCHECK --interval=30s --timeout=30s --start-period=5s --retries=3 CMD ["ps", "aux", "|", "grep", "java", "||", "exit", "1"]

#      GAME     STATUS
EXPOSE 6567/udp 6567/tcp

# Run Mindustry
ENTRYPOINT ["exec", "java", "${JAVA_OPT}", "-jar", "$APP_BIN"]

