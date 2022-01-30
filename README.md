
# redis-bull-parser
Simple package to parse redis URL created with dokku into the format Bull queue is expecting

Simple parser function to automatically create the redis object that the Bull queue is expecting from a redis instance created with dokku-redis (https://github.com/dokku/dokku-redis) in the REDIS_URL env variable.

    const redisBullParser = require('redis-bull-parser');
    const redisBullObject = redisBullParser('redis://:secretpassword@generichostname:123')
    console.log(redisBullObject)
    {
	    redis: {
			password: 'secretpassword',
			host: 'generichostname',
			port: 123
		}
    }
    const randomQueue = new BullQueue('random queue', redisBullObject) 

Hope that can save people some times
