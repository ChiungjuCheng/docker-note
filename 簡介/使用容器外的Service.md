# 從容器內存取host上的service
spring boot在container中，想要使用在localhost上的database。  

# 解決方式
在spring boot的application.yml中使用特殊的DNS name : host.docker.internal，其將會轉為host在用的IP。
```yml
spring:
 datasource:
  url: jdbc:mysql://host.docker.internal:3306/{schema}
  username: {username}
  password: {password}
```

不能使用--network="host"，因為這個代表的是container中的127.0.0.1都會指向docker host

# 資料來源
[官網](https://docs.docker.com/desktop/windows/networking/)  
[From inside of a Docker container, how do I connect to the localhost of the machine? ](https://stackoverflow.com/questions/24319662/from-inside-of-a-docker-container-how-do-i-connect-to-the-localhost-of-the-mach/24326540#24326540)
