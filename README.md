# docker

docker run --env MODE=standalone --name nacos -d -p 8848:8848 nacos/nacos-server

# Nacos
 docker run --name nacos-standalone -e MODE=standalone -p 8848:8848 -d nacos/nacos-server:latest

 docker run --name nacos-server -e MODE=standalone -e MYSQL_SERVICE_HOST=127.0.0.1 -e MYSQL_SERVICE_PORT=3306 -e MYSQL_SERVICE_DB_NAME=nacos -e MYSQL_SERVICE_USER=root -e MYSQL_SERVICE_PASSWORD=root -p 8848:8848 -d nacos/nacos-server:latest

# Mysql
$ docker container run -d -p 3306:3306 --name mysql --env MYSQL_ROOT_PASSWORD=123456 mysql


docker run -d \
-v $PWD/cluster-config-7000.conf:/usr/local/etc/redis/redis.conf \
--name redis-1 \
--net=host \
redis \
redis-server /usr/local/etc/redis/redis.conf


docker run -d \
-v $PWD/cluster-config-7001.conf:/usr/local/etc/redis/redis.conf \
--name redis-2 \
--net=host \
redis \
redis-server /usr/local/etc/redis/redis.conf

docker run -d \
-v $PWD/cluster-config-7002.conf:/usr/local/etc/redis/redis.conf \
--name redis-3 \
--net=host \
redis \
redis-server /usr/local/etc/redis/redis.conf

docker run -d \
-v $PWD/cluster-config-7003.conf:/usr/local/etc/redis/redis.conf \
--name redis-4 \
--net=host \
redis \
redis-server /usr/local/etc/redis/redis.conf

docker run -d \
-v $PWD/cluster-config-7004.conf:/usr/local/etc/redis/redis.conf \
--name redis-5 \
--net=host \
redis \
redis-server /usr/local/etc/redis/redis.conf

docker run -d \
-v $PWD/cluster-config-7005.conf:/usr/local/etc/redis/redis.conf \
--name redis-6 \
--net=host \
redis \
redis-server /usr/local/etc/redis/redis.conf

docker run -it --name rediscli \
redis \
redis-cli --cluster create 127.0.0.1:7000 127.0.0.1:7001 127.0.0.1:7002 127.0.0.1:7003 127.0.0.1:7004 127.0.0.1:7005 --cluster-replicas 1


docker inspect -f '{{ (index .NetworkSettings.Networks "red_cluster").IPAddress }}' redis-1
