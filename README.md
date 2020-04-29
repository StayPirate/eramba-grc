# Eramba Enterprise Edition

* Follow the instructions in eramba folder
* Copy the database scheme to `/db` and adjust. It's located in the Eramba's sources at `/eramba_v2/app/Config/db_schema/e_________.sql`
* Adjust the `DB_SCHEMA` argument in [`docker-compose.yml`](docker-compose.yml)
* Build images with `docker-compose build`
* Run services with `docker-compose up -d`
* At first run, wait until MariaDB would have initialized its db schema (it may take a while)