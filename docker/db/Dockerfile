FROM postgres:16.1

COPY arquivos/docker-entrypoint-initdb.d /docker-entrypoint-initdb.d/

RUN set -eux \
	&& apt-get update --no-allow-insecure-repositories \
	&& apt-get --assume-yes --auto-remove upgrade \
	&& apt-get --assume-yes autoremove \
	&& apt-get clean \
	&& rm -r /var/lib/apt/lists/*

### DESCOMENTAR MÓDULOS DO POSTGRES REQUERIDOS

###> postgis
# RUN export DEBIAN_FRONTEND=noninteractive \
#     && set -eux \
#     && apt-get update --no-allow-insecure-repositories \
#     && apt-get install --assume-yes postgresql-14-postgis-3 \
#     && apt-get --assume-yes autoremove \
#     && apt-get clean \
#     && rm -r /var/lib/apt/lists/*
###< postgis

###> postgres_fdw
# RUN export DEBIAN_FRONTEND=noninteractive \
#     && set -eux \
#     && apt-get update --no-allow-insecure-repositories \
#     && apt-get install --assume-yes postgresql-14-tds-fdw \
#     && apt-get --assume-yes autoremove \
#     && apt-get clean \
#     && rm -r /var/lib/apt/lists/*
###< postgres_fdw

EXPOSE 5432

CMD ["postgres"]
