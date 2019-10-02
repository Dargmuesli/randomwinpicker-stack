# randomwinpicker Stack

The Docker stack configuration for [randomwinpicker.jonas-thelemann.de](https://randomwinpicker.jonas-thelemann.de/).

This project is deployed in accordance to the [DargStack template](https://github.com/dargmuesli/dargstack_template/) to make deployment a breeze. It is closely related to [randomwinpicker's source code](https://github.com/dargmuesli/randomwinpicker/).

## Table of Contents
1. **[Secrets](#secrets)**
1. **[Services](#services)**
1. **[Volumes](#volumes)**

## Secrets

- `postgres_db`:
  the database's name.

- `postgres_password`:
  the database's password.

- `postgres_user`:
  the database's default name.

## Services

- #### `adminer`

  You can access the database's frontend at [adminer.randomwinpicker.test](https://adminer.randomwinpicker.test/).
  This information is required for login:

  |          |                     |
  | -------- | ------------------- |
  | System   | PostgreSQL          |
  | Server   | postgres            |
  | Username | [postgres_user]     |
  | Password | [postgres_password] |
  | Database | [postgres_db]       |

  Values in square brackets are [Docker secrets](https://docs.docker.com/engine/swarm/secrets/).

- #### `postgres`

  You can access the database via `adminer`.

- #### `randomwinpicker`

  You can access the main project at [randomwinpicker.test](https://randomwinpicker.test/).

- #### `traefik`

  You can access the reverse proxy's dashboard at [traefik.randomwinpicker.test](https://traefik.randomwinpicker.test/).
  Traefik enables HTTPS for all services and acts as a load-balancer too.

- ### `traefik_certs-dumper` ![production](https://img.shields.io/badge/-production-informational.svg?style=flat-square)

  See [DargStack template: certificates](https://github.com/Dargmuesli/dargstack_template/#certificates).

## Volumes

- `postgres-data`:
  the database's data.
