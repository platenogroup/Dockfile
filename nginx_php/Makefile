pull:
	docker pull alpine:3.4

dl:
	wget -c -t 1000 http://nginx.org/download/nginx-1.12.2.tar.gz -O nginx/nginx-1.12.2.tar.gz
	wget -c -t 1000 http://nginx.org/download/nginx-1.12.2.tar.gz.asc  -O nginx/nginx.tar.gz.asc
	wget -c -t 1000 https://secure.php.net/get/php-5.6.33.tar.xz/from/this/mirror -O php/php-5.6.33.tar.xz
	wget -c -t 1000 https://github.com/phalcon/cphalcon/archive/phalcon-v2.0.10.tar.gz -O php/cphalcon.tgz
	wget -c -t 1000 https://pecl.php.net/get/redis-2.2.7.tgz -O php/redis.tgz
	wget -c -t 1000 https://pecl.php.net/get/memcached-2.2.0.tgz -O php/memcached.tgz
	wget -c -t 1000 https://pecl.php.net/get/xdebug-2.3.2.tgz -O php/xdebug.tgz
	wget -c -t 1000 https://pecl.php.net/get/msgpack-0.5.6.tgz -O php/msgpack.tgz
	wget -c -t 1000 https://pecl.php.net/get/memcache-2.2.7.tgz -O php/memcache.tgz
	wget -c -t 1000 https://pecl.php.net/get/xhprof-0.9.4.tgz -O php/xhprof.tgz
	wget -c -t 1000 https://pecl.php.net/get/mongo-1.6.14.tgz -O php/mongo.tgz
	wget -c -t 1000 https://pecl.php.net/get/mongodb-1.2.9.tgz -O php/mongodb.tgz


build:
	make build-nginx

build-nginx:
	docker build -t plateno/nginx1.12.2_php5.6.33 .

push:
	docker tag plateno/nginx1.12.2_php5.6.33 docker.plateno.cc/library/nginx1.12.2_php5.6.33 && docker push docker.plateno.cc/library/nginx1.12.2_php5.6.33


run-nginx:
	docker run -i -d -p 80:80 -t plateno/nginx1.12.2_php5.6.33

clean:
	sudo docker rmi -f $(sudo docker images | grep "<none>" | awk "{print \$3}")
