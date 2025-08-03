# Local Environment with Docker and PostgreSQL

To structure my analysis, I used a local environment with PostgreSQL running in a Docker container. This allowed me greater control over the data, efficient execution of SQL queries, and simulation of a small data pipeline.

## Database Initialization

The database was created with the following command:

```bash
docker run --name meu-postgres \
  -e POSTGRES_PASSWORD=123456 \
  -e POSTGRES_USER=meuusuario \
  -e POSTGRES_DB=meubanco \
  -p 5432:5432 \
  -d postgres
```

## Replicating the Environment

The database is already populated and ready for analysis. To replicate the environment, simply start the container and restore the dump I'm providing (`desafio_dump.sql`) using the following commands:

```bash
docker cp desafio_dump.sql meu-postgres:/desafio_dump.sql
docker exec -it meu-postgres bash
psql -U meuusuario -d meubanco -f /desafio_dump.sql
```

## SQL Queries

I’ve included a text file with the queries used, in case you want to review them more easily.
