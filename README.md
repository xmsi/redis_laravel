# Redis & Laravel
*Redis cli basics and laravel cache*

## Laravel

```sudo apt install php8.3-redis```\
Install your php's version redis plugin to work with Redis in php 

```composer require predis/predis ```\
Install predis to work with Redis in Laravel

``CACHE_DRIVER=redis``\
change in your .env


```
        $blogNews =  Cache::remember('blogNews', 60, function () use ($blogNews) {
            return $blogNews->get()->sortByDesc('posted_at'); 
        });  
```
sample to write Cache and get from it. (It is all you need)

### Optional Install Telescope to monitor cache

``composer require laravel/telescope --dev``\
`` php artisan telescope:install ``\
`` php artisan migrate ``

go to /telescope


## Redis

1. install on docker \
`` $ docker run -d --name my-redis-stack -p 6379:6379  redis/redis-stack-server:latest ``\

2. run shell \
```
$ docker exec -it 885 sh
> redis-cli
```

3. ``INFO keyspace`` - to see all db's with keys
4. ``SELECT 1`` - to select db
5. ``KEYS *`` - to see all keys
6. ``GET key_index`` - to get value

### Optional gui [RedisInsight](https://hub.docker.com/r/redis/redisinsight)
