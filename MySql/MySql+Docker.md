# 建立Container環境
執行此資料夾下的docker-compose.yml檔案，避免對外的port與本地的Mysql server的port撞到，Mysql default的port為3306。

```
docker-compose up
```

# 使用Container中的Mysql
執行container中的命令列
```
docker exec -it {docker container id} bash
```

進入Mysql命令列，並輸入密碼
```
mysql -u root -p

```
or install mysql client on host and run this
```
mysql -h 127.0.0.1 -P 3307 -u root -p 
```

# 連接MySql workbench
跟連接非Container管理的sql server一樣，只需要更改連線的port。
[sqlworkbench](/MySql/pic/sqlworkbench.png)