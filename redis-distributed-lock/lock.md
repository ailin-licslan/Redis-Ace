hi distributed lock

Redis分布式锁实现V1
![avatar](00.redis-distributed-lock-v1.jpg)


分布式锁v1超时释放问题
![avatar](01.over-time-realease-issue.jpg)


解决分布式锁v1超时释放问题,判断锁标识是否是属于自己
![avatar](02.slove-over-time-v1.jpg)
![avatar](03.slove-over-time-v1.jpg)

解决分布式锁v1超时释放问题,判断锁标识和释放锁是2个独立的动作,判断了标识,但是释放阻塞了,GC stw 阻塞 超时释放 (lua
多命令原子性)
![avatar](04.over-time-release-issue-v2.jpg)

锁的标识判断与释放原子性
![avatar](05.over-time-release-issue-v2.jpg)

总结
![avatar](06.distributed-lock-summarize.jpg)



