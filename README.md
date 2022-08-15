# nginx + PHP-FPM - MariaDB
### Vangelis Tripolitakis (v.trp.gr - vtripolitakis@__NO__SPAM__me.com)

A simple docker image made for development purposes.

I used:
- The great DigitalOcean NGINXConfig tool (https://www.digitalocean.com/community/tools/nginx).
- The default nginx official Docker image (https://hub.docker.com/_/nginx/)
- The latest MariaDB database official Docker image (https://hub.docker.com/_/mariadb)
- The PHP-FPM server Docker image by Bitnami (https://hub.docker.com/r/bitnami/php-fpm/)


## Installation

### First, start it up
```bash
docker compose up -d
```

### Second, create an `app` and a `db` folder to host the application and the database files, respectively
```bash
mkdir app
mkdir db
```

### Third, get into the MariaDB container (hint: pass is 123)
```bash
docker exec -it docker-db-1 mysql -u root -p 
```
then create your database, for example:

```mysql
create database mydb default character set utf8 default collate utf8_general_ci;
```

### Fourth, add your app code and populate your database. Your application is served on `http://localhost` or `http://myapp.local` given you added on your `hosts` file the following line: `127.0.0.1 myapp.local`



### To properly shut everything down just issue:
```bash
docker compose down
```

## License
[MIT](https://choosealicense.com/licenses/mit/)