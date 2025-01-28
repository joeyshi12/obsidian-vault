# MariaDB

MariaDB is a fork of the MySQL relational database management system.
It is compatible with RaspberryPi and has an open and available Docker image which can be setup with the following Docker compose snippet:

```docker-compose
services:
    sql:
        image: linuxserver/mariadb
        environment:
          - MYSQL_ROOT_PASSWORD=<SECRET>
          - MYSQL_DATABASE=<DB_NAME>
          - MYSQL_USER=<USERNAME>
          - MYSQL_PASSWORD=<PASSWORD>
        ports:
          - "3306:3306"
        volumes:
          - /data/<DB_NAME>/mysql:/var/lib/mysql
          - /data/<DB_NAME>/config:/config/initdb.d  # optional init script
        restart: always
```

## Accessing Database

For the above snippet, the server from the sql container can be accessed through port 3306. Ensure that relevant mysql client packages are installed and then connect using `mysql --host=0.0.0.0 --port 3306 --user=<USERNAME> --password <DB_NAME>`.
Now it should be possible to list available tables with `show tables;` and execute regular MySQL queries in the console.