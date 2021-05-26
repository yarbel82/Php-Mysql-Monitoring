# Overview

## Setup Containers

### Basic

```bash
$ cp .env.dist .env

# Start Docker
$ docker-compose up -d

# Start Docker with chousen file
$ docker-compose up -f  <name.yml>  -d
```

## Dump DB

```
set -a && . ./.env && set +a && docker exec -ti *_mysql_1 sh -c "mysqldump -u$MYSQL_USER -p$MYSQL_PASSWORD -hmysql $MYSQL_DATABASE > /docker-entrypoint-initdb.d/dump.sql"

```

## Grafana
1.  For monitoring Prometheuses, it need to install Prometheus in source
2.  For monitoing mysql(using prometheus), it need to install plugin MySQL_Overview.json in managers


## Prometheuse
 
 Prometheuse/Prometheuse.yaml It is for mysql-exporter.