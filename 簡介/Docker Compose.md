# Docker compose 
Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application’s services. 

# The benefits of using docker compose  
One of the main benefits of Docker Compose is its huge portability. 
it simplifies testing processes by making it possible to use any machine with Docker installed to run applications in an isolated environment.

# Using Compose process
1. Define app's environment with Dockerfile
2. Define the services that make up your app in docker-compose.yml
3. Run docker compose up

A docker-compose.yml looks like this:
```yml
version: "3"
services:
  spring:
    image: springboot-app
    ports:
     - "8080:8080"
    links:
      - fluentd
    logging:
      driver: "fluentd"
      options:
        fluentd-address: localhost:24224
        fluentd-async: 'true'
        tag: httpd.access
  fluentd:
    # link to Dockerfile
    build: ./fluentd
    volumes:
      - ./fluentd/conf:/fluentd/etc
    links:
      - "elasticsearch"
    ports:
      - "24224:24224"
      - "24224:24224/udp"
  elasticsearch:
    image: docker.elastic.co/elasticsearch/elasticsearch:7.17.0
    container_name: elasticsearch
    environment:
      - "discovery.type=single-node"
    expose:
      - "9200"
    ports:
      - "9200:9200"

  kibana:
    image: docker.elastic.co/kibana/kibana:7.13.1
    links:
      - "elasticsearch"
    ports:
      - "5601:5601"

```

# Reference
1. [Overiew of Docker Compose](https://docs.docker.com/compose/)
2. [What is Docker Compose?](https://strapi.io/blog/what-is-docker-compose-all-you-need-to-know)