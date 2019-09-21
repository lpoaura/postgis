FROM ubuntu:bionic

RUN apt-get update ; apt-get install -y postgresql;
    #echo "deb http://apt.postgresql.org/pub/repos/apt/ bionic-pgdg main" > /etc/apt/sources.list.d/pgdg.list;\
    #wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add -;\
    #apt-get update;\
    #apt-get -y postgresql-11 postgresql-11-postgis-2.5 postgresql-11-ogr-fdw postgresql-11-postgis-2.5-scripts;\
#RUN su - postgres -c "/usr/lib/postgresql/10/bin/pg_ctl -D /var/lib/postgresql/10/main -l logfile start"

VOLUME ["/etc/postgresql","/var/lib/postgresql","/var/log/postgresql"]
EXPOSE 5432

