# docker

docker run --env --name nacos-server -e MODE=standalone -e MYSQL_SERVICE_HOST=127.0.0.1 -e MYSQL_SERVICE_PORT=3306 -e MYSQL_SERVICE_USER=root -e MYSQL_SERVICE_PASSWORD=root -e MYSQL_SERVICE_DB_NAME=nacos -p 8848:8848 nacos/nacos-server
