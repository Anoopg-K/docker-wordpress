# Wordpress with docker compose

Here docker compose is used to set up wordpress in a docker container using docker volumes and bridge network.

```Eg: docker network create --driver bridge wpnet  

docker run \
-d \
--name database \
--network wpnet \
-v mysql-vol:/var/lib/mysql \
-e MYSQL_ROOT_PASSWORD=mysqlroot123 \
-e MYSQL_DATABASE=wordpress \
-e MYSQL_USER=wpuser \
-e MYSQL_PASSWORD=wpuser123 \
mysql:5.6


docker run \
-d \
--name wordpress \
-p 80:80 \
--network wpnet \
-v wordpress-vol:/var/www/html \
-e WORDPRESS_DB_HOST=database \
-e WORDPRESS_DB_USER=wpuser \
-e WORDPRESS_DB_PASSWORD=wpuser123 \
-e WORDPRESS_DB_NAME=wordpress \
wordpress:latest
```

  

## Environment Variables

#### MYSQL_ROOT_PASSWORD
 * Mysql root password  
#### MYSQL_DATABASE
 * Name of the database  
#### MYSQL_USER
 * Mysql username  
#### MYSQL_PASSWORD
 * Password of mysql user  

#### WORDPRESS_DB_HOST
 * Specify wordpress database host  
#### WORDPRESS_DB_USER
 * Database user  
#### WORDPRESS_DB_PASSWORD
 * Password of database user  
#### WORDPRESS_DB_NAME
 * Name of wordpress database

#### Networks
 * wpnet

#### Volumes
 * mysql-vol
 * wordpress-vol


