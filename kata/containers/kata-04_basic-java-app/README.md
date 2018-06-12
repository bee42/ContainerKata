# Kata-04: Build an image for a Java app

When you are googeling for things like "Docker Java image", you'll be able to find lot of articles, guides and blog posts telling you how to do it. But how much of a real life example do these articles actually provide? 

Let's look at this Dockerfile as a start (taken from [Spring Boot with Docker](https://spring.io/guides/gs/spring-boot-docker/)):

```
FROM openjdk:8-jdk-alpine
VOLUME /tmp
ARG JAR_FILE
COPY ${JAR_FILE} app.jar
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]
```

How do you need to change this example, in order to transform it into a production ready Java image?

## Things to consider

* Which user should run the application?
* Do you need a JDK for running the jar?
* How does the JVM behave inside a container? Does it differ dependening on the Java version?


## Helpful information

* https://blogs.oracle.com/java-platform-group/java-se-support-for-docker-cpu-and-memory-limits
* https://developers.redhat.com/blog/2017/03/14/java-inside-docker/
