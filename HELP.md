# Getting Started

### Reference Documentation

For further reference, please consider the following sections:

* [Official Gradle documentation](https://docs.gradle.org)
* [Spring Boot Gradle Plugin Reference Guide](https://docs.spring.io/spring-boot/docs/3.0.3/gradle-plugin/reference/html/)
* [Create an OCI image](https://docs.spring.io/spring-boot/docs/3.0.3/gradle-plugin/reference/html/#build-image)
* [GraalVM Native Image Support](https://docs.spring.io/spring-boot/docs/3.0.3/reference/html/native-image.html#native-image)
* [Mustache](https://docs.spring.io/spring-boot/docs/3.0.3/reference/htmlsingle/#web.servlet.spring-mvc.template-engines)
* [Spring Session](https://docs.spring.io/spring-session/reference/)
* [Spring Boot DevTools](https://docs.spring.io/spring-boot/docs/3.0.3/reference/htmlsingle/#using.devtools)
* [Spring Reactive Web](https://docs.spring.io/spring-boot/docs/3.0.3/reference/htmlsingle/#web.reactive)
* [Thymeleaf](https://docs.spring.io/spring-boot/docs/3.0.3/reference/htmlsingle/#web.servlet.spring-mvc.template-engines)
* [Spring for GraphQL](https://docs.spring.io/spring-boot/docs/3.0.3/reference/html/web.html#web.graphql)
* [Jersey](https://docs.spring.io/spring-boot/docs/3.0.3/reference/htmlsingle/#web.servlet.jersey)
* [Apache Freemarker](https://docs.spring.io/spring-boot/docs/3.0.3/reference/htmlsingle/#web.servlet.spring-mvc.template-engines)
* [Rest Repositories](https://docs.spring.io/spring-boot/docs/3.0.3/reference/htmlsingle/#howto.data-access.exposing-spring-data-repositories-as-rest)
* [Spring Web Services](https://docs.spring.io/spring-boot/docs/3.0.3/reference/htmlsingle/#io.webservices)
* [Groovy Templates](https://docs.spring.io/spring-boot/docs/3.0.3/reference/htmlsingle/#web.servlet.spring-mvc.template-engines)
* [Spring HATEOAS](https://docs.spring.io/spring-boot/docs/3.0.3/reference/htmlsingle/#web.spring-hateoas)
* [Spring Web](https://docs.spring.io/spring-boot/docs/3.0.3/reference/htmlsingle/#web)
* [Spring Security](https://docs.spring.io/spring-boot/docs/3.0.3/reference/htmlsingle/#web.security)
* [Spring Configuration Processor](https://docs.spring.io/spring-boot/docs/3.0.3/reference/htmlsingle/#appendix.configuration-metadata.annotation-processor)

### Guides

The following guides illustrate how to use some features concretely:

* [Building a Reactive RESTful Web Service](https://spring.io/guides/gs/reactive-rest-service/)
* [Handling Form Submission](https://spring.io/guides/gs/handling-form-submission/)
* [Building a GraphQL service](https://spring.io/guides/gs/graphql-server/)
* [Accessing JPA Data with REST](https://spring.io/guides/gs/accessing-data-rest/)
* [Accessing Neo4j Data with REST](https://spring.io/guides/gs/accessing-neo4j-data-rest/)
* [Accessing MongoDB Data with REST](https://spring.io/guides/gs/accessing-mongodb-data-rest/)
* [Producing a SOAP web service](https://spring.io/guides/gs/producing-web-service/)
* [Accessing data with MySQL](https://spring.io/guides/gs/accessing-data-mysql/)
* [Building a Hypermedia-Driven RESTful Web Service](https://spring.io/guides/gs/rest-hateoas/)
* [Building a RESTful Web Service](https://spring.io/guides/gs/rest-service/)
* [Serving Web Content with Spring MVC](https://spring.io/guides/gs/serving-web-content/)
* [Building REST services with Spring](https://spring.io/guides/tutorials/rest/)
* [Securing a Web Application](https://spring.io/guides/gs/securing-web/)
* [Spring Boot and OAuth2](https://spring.io/guides/tutorials/spring-boot-oauth2/)
* [Authenticating a User with LDAP](https://spring.io/guides/gs/authenticating-ldap/)

### Additional Links

These additional references should also help you:

* [Gradle Build Scans – insights for your project's build](https://scans.gradle.com#gradle)
* [Configure AOT settings in Build Plugin](https://docs.spring.io/spring-boot/docs/3.0.3/gradle-plugin/reference/htmlsingle/#aot)

## GraalVM Native Support

This project has been configured to let you generate either a lightweight container or a native executable.
It is also possible to run your tests in a native image.

### Lightweight Container with Cloud Native Buildpacks

If you're already familiar with Spring Boot container images support, this is the easiest way to get started.
Docker should be installed and configured on your machine prior to creating the image.

To create the image, run the following goal:

```
$ ./gradlew bootBuildImage
```

Then, you can run the app like any other container:

```
$ docker run --rm -p 8080:8080 demo:0.0.1-SNAPSHOT
```

### Executable with Native Build Tools

Use this option if you want to explore more options such as running your tests in a native image.
The GraalVM `native-image` compiler should be installed and configured on your machine.

NOTE: GraalVM 22.3+ is required.

To create the executable, run the following goal:

```
$ ./gradlew nativeCompile
```

Then, you can run the app as follows:

```
$ build/native/nativeCompile/demo
```

You can also run your existing tests suite in a native image.
This is an efficient way to validate the compatibility of your application.

To run your existing tests in a native image, run the following goal:

```
$ ./gradlew nativeTest
```

