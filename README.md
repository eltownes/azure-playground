### A 'Hello World' spring app using IntelliJ IDEA

### Original tutorial:
https://learn.microsoft.com/en-us/azure/spring-apps/quickstart?pivots=sc-enterprise&tabs=Azure-portal%2CIntelliJ%2CConsumption-workload

Notes:
- using `azd` cmd line & not graphical IDE
- change Azure ingress port from `80` to `8080`

<br>

#### Prep and run it locally:

- create project from `spring.io`
```
curl https://start.spring.io/starter.tgz \
 -d dependencies=web \
 -d baseDir=demo \
 -d bootVersion=3.2.1 \
 -d javaVersion=17 \
 -d type=maven-project \
 -d groupId=com.example \
 -d artifactId=demo \
 -d name=demo \
 -d packageName=com.example.demo \
 -d packaging=maven \
 | tar -xzvf-
```

- copy the project from the `baseDir` to the active branch/dir
```
cp -r . ~/IdeaProjects/azure-playground
```

- Add web controller `HelloController.java`
```
package com.example.demo;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
@RequestMapping("/")
public class HelloController {

    @GetMapping("/")
    public String hello() {
        return "Hello World!";
    }
}
```

- build it
```
./mvnw clean package
```

- run it
```
./mvnw spring-boot:run
```

- if needed to free port `8080`:
```
lsof -i :8080
```
```
kill -9 <PID>
```
<br>

#### Deploy to cloud

- login
```
azd auth login
```

- initialize
```
azd init
```

- follows prompts ... along with `next-steps.md`

- provision and deploy
```
azd up
```

- for default config, need to change Azure ingress port to `8080`

- test deployment

- delete everything ... w/ prompts
```
azd down
```

---
<br>