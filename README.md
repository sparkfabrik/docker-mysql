![Drocker](https://raw.githubusercontent.com/twinbit/drupal-docker-env/master/src/dde.png)

##Docker Drupal Mysql

This images is partially inspired on [tutum/mysql](https://registry.hub.docker.com/u/tutum/mysql/) image.

### Description

```
Operating system: ubuntu:14.04
Mysql: 5.6
```

The server is automatically configured using a set of default and optimized `my.cnf` file, as follows:

```
# Standard cache configurations.
key_buffer_size = 128M
max_allowed_packet = 128M
table_open_cache = 64
sort_buffer_size = 64K
read_buffer_size = 256K
read_rnd_buffer_size = 256K
net_buffer_length = 2K
thread_stack = 240K
query_cache_type = 1
query_cache_size = 256M
query_cache_limit = 32M
max_heap_table_size = 92M
join_buffer_size = 4M
thread_cache_size = 4

# INNODB Configurations.
innodb_buffer_pool_size = 1024M
innodb_additional_mem_pool_size = 20M
innodb_log_file_size = 256M
innodb_log_buffer_size = 32M
innodb_flush_log_at_trx_commit = 0
innodb_doublewrite = 0
innodb_support_xa = 0
innodb_file_per_table = 1
```

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
