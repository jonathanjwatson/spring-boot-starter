# spring-boot-starter

## Initial Setup
1. Go to https://start.spring.io/
2. Setup initial config

* Project: Maven Project
* Language: Java
* Spring Boot: 2.3.0

3. Add dependencies
* Spring Web
* Spring Data JPA

* Artifact: spring-boot-starter
* Name: spring-boot-starter
* Packaging: Jar
* Java: 11

4. Generate

5. Unzip the downloaded folder and copy/paste into your repo. 

6. Open in IntelliJ - open via termainal with `idea .` IntelliJ should automatically install all dependencies. 

## Getting it Up and Running

1. In IntelliJ, navigate to the main application. For me, that is: 

src/main/java/com.jonathanjwatson.springbootstart/SpringBootStarterApplication

2. Right click and select "Run 'SpringBootStartApplication'" This will most likely generate an error. 

3. Add connection information for JPA. To do this: 
    * Create an application.yml file
    * Add the default for MySQL and update for your specific database, username, and password.

```yml
spring:
  datasource:
    driverClassName: com.mysql.cj.jdbc.Driver
    url: jdbc:mysql://localhost:3306/playlist_db?serverTimezone=UTC
    username: user1
    password: pass
```
This will get you to the next step, but this requires the mysql JDBC driver. So you'll need to add the following to your pom.xml file:

```xml
<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
    <version>8.0.18</version>
</dependency>
```

And that should start up your springboot app! Next, we'll work on adding some routes and retrieving data. 

## Building Your First Route

1. Inside your main package, create a new package and name it controllers.
2. Inside controllers, create a new Class, we'll call it HomeController.
3. Add the `@RestController` annotation above the public class name. 
4. Inside the HomeController method, add the following: 

```java
    @RequestMapping("/")
    public String home(){
        return "Welcome to your starter application!";
    }
```
5. Save. Restart your app. You should now be able to navigate to `localhost:8080/` and see your message!

