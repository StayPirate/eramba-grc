# Eramba Community Edition

* Initialize the Eramba submodule executing `git submodule update --init --remote`. Running it from this branch, the Eramba `community edition` docker-files will be fetched
* Follow the instructions in `eramba` folder
* Follow the instructions in `db` folder
* Build images with `docker-compose build`
* Run services with `docker-compose up -d`
* At first run, wait until MariaDB would have initialized its db schema (it may take a while)