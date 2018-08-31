# springboot nginx & haproxy 负载均衡比对


# 目标:

``` python
  8081&8082 均衡 8083备份(在8081&8082都down机时执行)

  server 127.0.0.1:8081 weight=4 max_fails=2 fail_timeout=30s;
  server 127.0.0.1:8082 weight=4 max_fails=2 fail_timeout=30s;
  server 127.0.0.1:8083 backup;
```

## 配置源码见:  

``` python
  ./haproxy-loadbance.zip
  ./nginx-loadbance.zip
```
  
  
## ha&ng结果比对:


### backup

- **haproxy**
<image src="src/main/resources/ha-pics/backup.jpeg" width="100%" height="400px"></image>
- **nginx**
<image src="src/main/resources/ng-pics/backup.jpeg" width="100%" height="400px"></image>


### config

- **haproxy**
<image src="src/main/resources/ha-pics/config.jpeg" width="100%" height="400px"></image>
- **nginx**
<image src="src/main/resources/ng-pics/config.jpeg" width="100%" height="500px"></image>


### roundrobin

- **haproxy**

<image src="src/main/resources/ha-pics/roundrobin.png" height="400px"></image>

- **nginx**

<image src="src/main/resources/ng-pics/roundrobin.png" height="400px"></image>

### test

- **happroxy**

<image src="src/main/resources/ha-pics/test.jpeg" width="60%"></image>
- **nginx**

<image src="src/main/resources/ng-pics/test.png" width="60%"></image>

