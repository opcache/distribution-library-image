# Build a minimal distribution container

FROM alpine:3.8

RUN set -ex \
    && apk add --no-cache ca-certificates apache2-utils

COPY ./amd64/registry /bin/registry
COPY ./amd64/config-example.yml /etc/docker/registry/config.yml

EXPOSE 5000

COPY ./amd64/docker-entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]

CMD ["/etc/docker/registry/config.yml"]
