### 1.什么是缓存
缓存是数据交换的缓冲区,是存储数据的临时地方，
一般读写性能较高

优点:降低后端的负载，提高读写效率，降低响应时间

`成本:数据一致性成本,代码维护成本,运维成本`


### 2.添加redis缓存

![avatar](02.cache-redis-idea.jpg)


### 3.缓存更新策略
总结:

![avatar](01.cache-update-policy.jpg)



更新策略:

![avatar](03.cache-update-policy.jpg)



主动更新策略:

![avatar](04.cache-update-policy.jpg)


主动更新策略需要考虑的问题:

![avatar](05.cache-update-policy.jpg)


先操作数据库更新再删除比较靠谱,更新一般比较慢,删除操作较快

![avatar](06.cache-update-policy.jpg)


### 4.缓存穿透
缓存穿透是指客户请求的数据在缓存中和数据库中都不存在,这样缓存永远不会生效,这些请求都会打到数据库的现象

![avatar](07.cache-penetration.jpg)

### 5.缓存雪崩
缓存雪崩是指在同一时段大量的缓存key同时失效或者redis服务宕机了,导致大量请求到达数据库,带来巨大压力

![avatar](08.cache-avalanche.jpg)


### 6.缓存击穿
缓存击穿问题也叫热点key问题,就是一个被高并发访问且缓存重建业务比较复杂的key突然失效了,无数的请求访问会在瞬间给数据库带来巨大的冲击

缓存击穿
![avatar](09.cache-breakdown.jpg)

解决方案
![avatar](10.cache-breakdown.jpg)

方案优缺点
![avatar](11.cache-breakdown.jpg)


### 7.redis工具类封装
![avatar](12.cache-utils.jpg)







