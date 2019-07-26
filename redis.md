# Redis

## Install redis
```
sudo apt update
sudo apt install redis-server
```

## TypeError: Cannot create property 'path' on string '6380'

var client = redis.createClient(redisHost, redisPort); // notice this, as we supply port, host in redis options

Solution for this is just reverse redis options

var client = redis.createClient(redisPort, redisHost);

### Match redis Keys with a pattern using nodejs
library.cache.client.keys("*pattern_here*", function(err, userKeys) {});

Example:
library.cache.client.keys("*userTimeHash_*", function(err, userKeys) {});
