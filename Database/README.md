# Ambiente local com Docker e PostgreSQL

Para estruturar minha análise, utilizei um ambiente local com PostgreSQL rodando em um container Docker. Isso me permitiu maior controle sobre os dados, execução eficiente de queries SQL e simulação de um pequeno pipeline de dados.

## Inicialização do banco de dados

O banco foi criado com o seguinte comando:

```bash
docker run --name meu-postgres \
  -e POSTGRES_PASSWORD=123456 \
  -e POSTGRES_USER=meuusuario \
  -e POSTGRES_DB=meubanco \
  -p 5432:5432 \
  -d postgres
```

## Replicando o ambiente

A base de dados já está populada e pronta para análise. Para replicar o ambiente, basta subir o container e restaurar o dump que estou enviando (`desafio_dump.sql`) com os seguintes comandos:

```bash
docker cp desafio_dump.sql meu-postgres:/desafio_dump.sql
docker exec -it meu-postgres bash
psql -U meuusuario -d meubanco -f /desafio_dump.sql
```

## Consultas SQL

Deixei um arquivo em texto com as queries utilizadas, caso queiram analisar de maneira mais fácil.
