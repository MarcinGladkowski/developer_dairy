# Environment variables

### Pass by docker
* use `-e key=value`
* e.g.`docker run -e WORDPRESS_DB_HOST=10.1.2.3:3306 -e WORDPRESS_DB_USER=user WORDPRESS_DB_PASSWORD=password -d wordpress

* docker-compose

```
version '3'

services:
    wordpress:
        image: wordpress
        envirionment:
            - WORDPRESS_DB_HOST: 10.1.2.3:3306
            - WORDPRESS_DB_USER: user
            - WORDPRESS_DB_PASSWORD: password
            - WORDPRESS_DB_NAME: database
```

### Dockerfile
* We want to still have environment e.g. `NODE_VERSION`


### Use .env files
* Overwrite values in `docker-compose` -> if `.env` is in the same directory.

```.env
DB_PORT=3306
DB_USER=user
```
* Pass these values to `docker-compose`

```
version '3'

services:
    postgres:
        image: postgres:9.6
        ports: 
            - ${DB_PORT}:5432
        environment:
            - POSTGRESS_PASSWORD: password
            - POSTGRESS_USER: ${DB_USER}
```
* Check if works `docker-compose config`
* Practival usage. `.env` file is not tracked file by version control, but `docker-compose.yml` is. 

### Host environment variables vs docker
* Host environment variables overwrite variables in `.env` files.

> Linux list environment variables: printenv

* Check it! `export DB_USER=host` and then `docker-compose config` shows `DB_USER=host`.

### Environment in terminal
* `set DB_USER=terminal`

### ENV in Dockerfile
* variables in `.env` and using `-e`, are not passing to `Dockerfile`. These values are use in  `docker-compose`

### Another name for .env file
* e.g. .env => .my_env
* `docker-run --env-file=my_env...


### use docker-compose
```
version: '3.2'

services:
    alpine:
        image: alpine
        evn_file: my_env
```