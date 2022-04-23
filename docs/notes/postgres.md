Postgres
========

## Dump a Postgres database that is in a Docker container

    docker exec -u <container_user> <container_name> <pg_dump> <db_name> > `date %y%m%d`_dump.sql

## Restore a Postgres database that is in a Docker container

    cat your_dump.sql | docker exec -i your-db-container psql -U postgres

## Push a Postgres Database to Heroku Postgres

    heroku pg:reset
    heroku pg:push <local_db> <remote_db> --app <app_name>

(https://devcenter.heroku.com/articles/heroku-postgresql#pg-push-and-pg-pull)
