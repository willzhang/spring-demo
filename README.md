## Getting started

A simple spring boot web project, supporting the use of docker and kubernets, for cicd.

build with maven

```
git clone https://github.com/willzhang/spring-demo.git

docker run -it -v ${PWD}/spring-demo:/workspace -w /workspace maven mvn clean package 
docker build -t willdockerhub/spring-demo .
docker push willdockerhub/spring-demo
```

run with docker

```
docker run -d --restart always \
  --name spring-demo \
  -p 8080:8080 \
  willdockerhub/spring-demo
```

access web for test
```
# curl <your-ip>:8080
Hello Spring Boot Demo!
```


## how to generate this demo

Refer to the link below：

[https://start.spring.io/](https://start.spring.io/)

[https://spring.io/guides/gs/spring-boot/](https://spring.io/guides/gs/spring-boot/)
