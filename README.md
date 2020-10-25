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

#### Networks
 * wpnet

#### Volumes
 * mysql-vol
