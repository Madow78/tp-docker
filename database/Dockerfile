FROM postgres:17.2-alpine

# Copie des scripts d'initialisation dans le dossier magique de Postgres
COPY 01-CreateScheme.sql /docker-entrypoint-initdb.d/
COPY 02-InsertData.sql /docker-entrypoint-initdb.d/