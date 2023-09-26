FROM postgres:15.4-alpine3.17

ARG BUILD_DATE
ARG SOURCE_COMMIT

LABEL org.opencontainers.image.authors="Biobank Lab Developers"
LABEL org.label-schema.schema-version="0.1"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.vcs-url="https://github.com/kkochel/sensitive-data-archive"
LABEL org.label-schema.vcs-ref=$SOURCE_COMMIT

COPY initdb.d      /docker-entrypoint-initdb.d
COPY --chmod=755 entrypoint.sh /usr/local/bin/entrypoint.sh

ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]

CMD ["postgres"]