# Oracle + Docker

### 登入container-registry.oracle.com
```
docker login container-registry.oracle.com
```

### 建立啟動容器
```
docker run -d --name oracledb -e ORACLE_PWD={password} -p 1521:1521 -p 5500:5500 container-registry.oracle.com/database/express
```
建立容器後就可以使用Oracle sql develop操作，但要注意的是只支援JDK 11以下。

# 參考資料
https://javapointers.com/devops/docker/how-to-run-oracle-database-container-in-docker/