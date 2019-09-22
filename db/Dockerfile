FROM postgres:11

VOLUME ["/var/lib/postgresql/data"]

ENV POSTGIS_MAJOR 2.5
ENV POSTGIS_VERSION 2.5.2+dfsg-1~exp1.pgdg90+1

RUN sed -i -e 's/# fr_FR.UTF-8 UTF-8/fr_FR.UTF-8 UTF-8/' /etc/locale.gen && \
    locale-gen
ENV LANG fr_FR.UTF-8  
ENV LANGUAGE fr_FR:fr  
ENV LC_ALL fr_FR.UTF-8     

RUN apt-get update \
      && apt-cache showpkg postgresql-$PG_MAJOR-postgis-$POSTGIS_MAJOR \
      && apt-get install -y --no-install-recommends \
           postgresql-$PG_MAJOR-postgis-$POSTGIS_MAJOR=$POSTGIS_VERSION \
           postgresql-$PG_MAJOR-postgis-$POSTGIS_MAJOR-scripts=$POSTGIS_VERSION \
           postgis=$POSTGIS_VERSION postgresql-$PG_MAJOR-ogr-fdw \
           locales \
      && rm -rf /var/lib/apt/lists/* 

RUN mkdir -p /docker-entrypoint-initdb.d
COPY ./initdb-postgis.sh /docker-entrypoint-initdb.d/postgis.sh
COPY ./update-postgis.sh /usr/local/bin
