FROM traefik:3 AS ddev-traefik-router

ENV TRAEFIK_MONITOR_PORT=10999
RUN apk add bash curl htop vim
WORKDIR /mnt/ddev-global-cache/traefik
COPY /traefik_healthcheck.sh /healthcheck.sh
RUN chmod ugo+rx /healthcheck.sh
HEALTHCHECK --interval=1s --timeout=120s --retries=1 --start-period=120s CMD /healthcheck.sh
