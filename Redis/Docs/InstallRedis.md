# <center> Install Redis on Centos
#1、Download Redis
    We can get Redis from http://redis.io/download .
    Choice the version you like and download it.
#2、Install Redis
    move the Redis to  /usr/local/src   
    $ cd /usr/local/src
    $ tar -xzv -f redis-3.2.11.tar.gz
    $ cd redis-3.2.11
    $ make
    $ cd src
    $ make install
    
#3、Run RedisServer
    we can use follow commond to run redis.
    $ cd /usr/local/src/redis-3.2.11
    $ src/redis-server
    Then we can see that the redis server is now ready to accept connection on port 6379.
    But the redis-server will close when we closed the shell window. 
#4、Config RedisServer
    if we want run redisServer in the background.We can config the configfile.
    $ cd /usr/local/src redis-3.2.11
    $ vim redis.conf
    Find the daemonize property and change it to 'yes'.
    Then we start redisServer again by follow commond.
    $ src/redis-server redis.conf
    redisServer will run in the background.
    using 'netstat' commond to makesure the redisServer is running.
    $ netstat -tunpl |grep 6379
    Or you can kill redisSever by follow commond.
    $ pkill redis-server
#5、Run RedisClient
    $ src/redis-cli
    127.0.0.0:6379>
    127.0.0.0:6379>
    127.0.0.0:6379>
    Then you can playing with Redis and have fun.
#6、Some RedisCommond
    run redis-server with named config.
    $ Redis-server /usr/.../redis.conf  
    run redis-client
    $ Redis-cli
    close redis-server
    $ pkill redis-server
    close redis-client
    $ Redis-cli shutdown
    check 6379 port
    $ Netstat -tunpl | grep 6379
    