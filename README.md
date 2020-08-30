## Getting started

build with maven

```
git clone https://github.com/willzhang/spring-demo.git
cd spring-demo
mvn clean package
```

run with docker

```
docker run -d --restart always \
  --name spring-demo \
  -p 8080:8080 \
  willdockerhub/spring-demo
```

## how to generate this demo

Refer to the link below：

[https://start.spring.io/](https://start.spring.io/)

[https://spring.io/guides/gs/spring-boot/](https://spring.io/guides/gs/spring-boot/)


add follow web class

src\main\java\com\example\springdemo\HelloController.java

```
HelloController.java

package com.example.springboot;

import org.springframework.web.bind.annotation.RestController;
import org.springframework.web.bind.annotation.RequestMapping;

@RestController
public class HelloController {

	@RequestMapping("/")
	public String index() {
		return "Hello Spring Boot Demo!";
	}

}
```

src\main\java\com\example\springdemo\Application.java

```
package com.example.springboot;

import java.util.Arrays;

import org.springframework.boot.CommandLineRunner;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.context.ApplicationContext;
import org.springframework.context.annotation.Bean;

@SpringBootApplication
public class Application {

	public static void main(String[] args) {
		SpringApplication.run(Application.class, args);
	}

	@Bean
	public CommandLineRunner commandLineRunner(ApplicationContext ctx) {
		return args -> {

			System.out.println("Let's inspect the beans provided by Spring Boot:");

			String[] beanNames = ctx.getBeanDefinitionNames();
			Arrays.sort(beanNames);
			for (String beanName : beanNames) {
				System.out.println(beanName);
			}

		};
	}

}
```

