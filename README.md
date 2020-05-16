# Eramba Enterprise Edition

* Copy the database scheme to `/db`, it's located in the Eramba's source code at `/eramba_v2/app/Config/db_schema/e*.sql`
* Adjust the `DB_SCHEMA` argument in the [`docker-compose.yml`](docker-compose.yml) file
* Initialize the Eramba submodule executing `git submodule update --init --remote`. Running it from this branch, the Eramba `enterprise` docker-files will be fetched
* Follow the instructions in `eramba` folder
* Follow the instructions in `db` folder
* Fulfill `eramba_vars.env` with your data
* Build images with `docker-compose build`
* Run services with `docker-compose up -d`
* At first run, wait until MariaDB would have initialized its db schema (it may take a while)