![Docker + Drupal](https://raw.githubusercontent.com/twinbit/drupal-docker-env/master/dde.png)

## Drupal Docker Mysql

This images is partially inspired on [tutum/mysql](https://registry.hub.docker.com/u/tutum/mysql/) image.

### Scripts

In order to simplify the management of this image, a set of helper scripts are bundled with the container.

#### Create database

Create a new database:

```
fig run --rm mysql /create NAME_OF_YOUR_DB
```

#### Import sql dump

Import a new database

```
fig run --rm mysql /import [PATH_TO_FILE]
```

Where PATH_TO_FILE is the absolute path of `data` container automatically mounted on `/data`.

Example:

```
fig run --rm mysql /import /data/tmp/dump.sql
```

#### Command line

Access Mysql cli:

```
fig run --rm mysql /cli
```









An automated build for this repo is available on the [Docker Hub](https://registry.hub.docker.com/u/twinbit).

This image is intended to be used in conjuction with the other images of the drupal docker stack:

- [twinbit/docker-drupal-data](https://github.com/twinbit/docker-drupal-data)
- [twinbit/docker-drupal-cli](https://github.com/twinbit/docker-drupal-cli)
- [twinbit/docker-drupal-mailcatcher](https://github.com/twinbit/docker-drupal-mailcatcher)
- [twinbit/docker-drupal-mysql](https://github.com/twinbit/docker-drupal-mysql)
- [twinbit/docker-drupal-nginx](https://github.com/twinbit/docker-drupal-nginx)
- [twinbit/docker-drupal-solr](https://github.com/twinbit/docker-drupal-solr)
- [twinbit/docker-drupal-php](https://github.com/twinbit/docker-drupal-php)

