# Docker 이미지 빌드
`docker build -t developiaa/order-service:1.0 .`

# Docker 이미지 업로드
`docker push developiaa/order-service:1.0`

# Docker 실행
```shell
docker run -d --network ecommerce-network \

  --name order-service \

 -e "spring.cloud.config.uri=http://config-service:8888" \

 -e "spring.rabbitmq.host=rabbitmq" \

 -e "spring.zipkin.base-url=http://zipkin:9411" \
 
 -e "spring.datasource.url=jdbc:mariadb://mariadb:3306/mydb" \

 -e "eureka.client.serviceUrl.defaultZone=http://discovery-service:8761/eureka/" \

 -e "logging.file=/api-logs/orders-ws.log" \

 developiaa/order-service:1.0
```
