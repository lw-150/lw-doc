# docker安装redis
* 参见：[https://hub.docker.com/_/redis](https://hub.docker.com/_/redis)
* 参见：[https://www.pianshen.com/article/47631363260/](https://www.pianshen.com/article/47631363260/)

```
docker run --name redis-name -p 6379:6379 -d redis:tag
设定密码
config set requirepass 123456
验证密码
config get requirepass
设定密码后两种登录方式
1.redis-cli -p 6379 -a 123456
2.redis-cli
auth 123456
```

