Symfony React Application
========================

The "Symfony React" is a reference application created to show how
to develop applications following the [Symfony Best Practices][1] with React on Docker.

## FEATURES
------------

  * PHP-FPM 7.1.3 or higher;
  * PostgreSQL 10.1;
  * and the [usual Symfony application requirements][2];
  * Nginx;
  * [React][4] and [Redux][7];

Each service runs in a dedicated container, and the whole thing is orchestrated with docker-compose.

## Requirements
---------------

You need [Docker Engine][5] and [Docker Compose][6] installed on your machine.

## Installation
---------------

* Run docker ;

```bash
$ docker-compose up
```

* Enter in php container;

```bash
$ docker exec -it [container php]  bash
```

* Drop database;

```bash
php bin/console doctrine:database:drop  --force 
```

* Create database;

```bash
php bin/console doctrine:database:create 
```

* Update schema;

```bash
php bin/console doctrine:schema:update 
```

* Run fixture;

```bash
php bin/console doctrine:fixtures:load
```

## Usage
-----

* Alternatively, you must add in /etc/hosts;

```bash
127.0.0.1 infinite.dev
```

## Tests
--------

* Enter in php container;

```bash
$ docker exec -it [container php]  bash
```

* Execute this command to run tests;

```bash
$ ./bin/phpunit
```

## Access to Application
------------------------

* **URL:** `http://infinite.dev`

## Access to postgres
---------------------

* `postgres:5432` (host only in docker container)
* **Username:** infinite (as a default)
* **Password:** infinitepass (as a default)

## Access to PgAdmin
--------------------

* **URL:** `http://infinite.dev:5050`
* **Username:** pgadmin4@pgadmin.org (as a default)
* **Password:** admin (as a default)

[1]: https://symfony.com/doc/current/best_practices/index.html
[2]: https://symfony.com/doc/current/reference/requirements.html
[4]: https://reactjs.org/
[5]: https://docs.docker.com/engine/
[6]: https://docs.docker.com/compose/
[7]: https://redux.js.org/

