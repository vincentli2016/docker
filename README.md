# docker
# Nacos
 docker run --name nacos-standalone -e MODE=standalone -p 8848:8848 -d nacos/nacos-server:latest

 docker run --name nacos-server -e MODE=standalone -e MYSQL_SERVICE_HOST=127.0.0.1 -e MYSQL_SERVICE_PORT=3306 -e MYSQL_SERVICE_DB_NAME=nacos -e MYSQL_SERVICE_USER=root -e MYSQL_SERVICE_PASSWORD=root -p 8848:8848 -d nacos/nacos-server:latest

# Mysql
$ docker container run -d -p 3306:3306 --name mysql --env MYSQL_ROOT_PASSWORD=123456 mysql
