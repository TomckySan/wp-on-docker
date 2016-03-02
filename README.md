# wp-on-docker

[![License][license-badge]][license]

Launching Docker containers for local development environment WordPress.  
The following description, assumes that making copy of production environment.  

## Usage

Copy production's themes, plugins, uploads.  
Make directory in which to place them.  

```
$ mkdir -p wp-on-docker/volume/{themes, plugins, uploads}
```

Also, place the dump file of the production environment database.  
Default is `wp-on-docker/mysql/db.dump.sql`.

For modifying a string throughout a database, install [Search Replace DB](https://github.com/interconnectit/Search-Replace-DB).  
Make directory in which to place Search Replace DB.  

```
$ mkdir wp-on-docker/volume/Search-Replace-DB-master/
```

After all, it is sufficient to match volumes configuration in `docker-compose.yml`.  

The next step is starting the Docker containers.  
After you run `docker-compose up -d`, execute `/setup.sh` on the database container.  

```
$ cd wp-on-docker/
$ docker-compose up -d
$ docker exec dockerdir_db_1 sh -c "/setup.sh"
```

As a final step, access to `docker-host-ip/Search-Replace-DB-master/` from browser,  
then change from the base URL of the production environment to local development environment.

[license-badge]: https://img.shields.io/badge/license-MIT-yellowgreen.svg?style=flat-square
[license]: LICENSE
