# Custom port
yaml file:
```yaml
server:
  port: ${PORT:0}
  servlet:
    context-path: /user-service-api/api/v1
eureka:
  instance:
    appname: user-service
    instance-id: ${spring.application.name}:${spring.application.instance_id:${random.value}}
  client:
    register-with-eureka: true
    fetch-registry: true
    serviceUrl:
      defaultZone: http://localhost:8762/eureka
```

Port 0 mean this springboot application will run with **random* Port number
You can pass the `PORT` argument in `mvn` command

```shell
mvn -Dspring-boot.run.arguments="--spring.application.instance_id=eureka-demo --server.port=9888"
```

