# READ ME

## Main Branch

Command to create a Docker Network for mySQL

`docker network create mysql`

Command to run a mysql:latest docker image on the network above

```
docker run \
    --network mysql \
    -e MYSQL_ROOT_PASSWORD=my-secret-password \
    --name mysql \
    -d mysql
```

Command to run the docker image phpmyadmin/phpmyadmin on the network previously created

```
docker run \
    --network mysql \
    -p 8080:80 \
    -e PMA_HOST=mysql \
    -d phpmyadmin/phpmyadmin
```
