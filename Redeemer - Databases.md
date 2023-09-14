#Redis #server 
**Redis** - Remote dictionary server
	an open-source advanced NoSQL key-value data store
	used as a database, cache, and message broker
	Port 6379
	Type of database: *In-Memory Database*
	Command line (interface: CLI) utility = *redis-cli*
		-h - specifies the hostname

$ redis-cli -h 10.0.0.1
	returns -> 10.0.0.1:6379> 
	10.0.0.1:6379> info 
		shows info and stats about the Redis server
	10.0.0.1:6379> select 0 
		selects the desired database
	10.0.0.1:6379> keys *
		shows all keys present in the database
	10.0.0.1:6379> get keyname

