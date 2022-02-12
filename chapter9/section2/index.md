## 数据类型

### string:
expire key  60 # 数据在 60s 后过期
setex key 60 value # 数据在 60s 后过期（该命令字符串类型独有）
strlen key # 返回 key 所储存的字符串值的长度。

场景：计数

### list:
rpush,lpop,lpush,rpop,lrange,llen

场景：消息队列

### hash:
hset,hmset,hexists,hget,hgetall,hkeys,hvals

场景：对象

### set:
sadd,spop,smembers,sismember,scard,sinterstore,sunion
scard mySet # 查看 set 的长度
sinterstore mySet3 mySet mySet2 # 获取 mySet 和 mySet2 的交集并存放在 mySet3 中

场景：求交集或并集

### sorted set
相较于set增加了一个权重参数 score:
zadd,zcard,zscore,zrange,zrevrange,zrem
zadd myZset 3.0 value1 # 添加元素到 sorted set 中 3.0 为权重
zscore myZset value1 # 查看某个 value 的权重
zrevrange  myZset 0 1 # 逆序输出某个范围区间的元素，0 为 start  1 为 stop

场景：排行榜

### bitmap:
setbit 、getbit 、bitcount、bitop
setbit mykey 7 1 # 生成7位（这7位全部默认为0），并且设置第7位为1
setbit mykey 8 1 # 增加第8位，设置第8位为1
bitcount mykey   # 统计被被设置为 1 的位的数量,return 2;
bitop (and/or/not/xor) destkey key1 key2 [key3 ...]
>and/or/not/xor是后面的key1,key2之间的位运算操作符，将结果保存进destkey

场景：统计

