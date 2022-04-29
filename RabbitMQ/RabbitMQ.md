# RabbitMQ STOMP server設定和啟動
建立image，使用此資料夾下的dockerfile建立能夠傳送STOMP的image。   
Dockerfile內容
```Dockerfile
FROM rabbitmq:management
RUN rabbitmq-plugins enable rabbitmq_stomp --offline
EXPOSE 61613
```
指令
```
docker build -t rabbitmq-stop .
```
並執行以下指令:
```
docker run -d --name rabbitmq -p 5672:5672 -p 15672:15672 -p 61613:61613 rabbitmq-stop
```
### RabbitMQ server資訊能夠到以下網址查看
http://localhost:15672/
