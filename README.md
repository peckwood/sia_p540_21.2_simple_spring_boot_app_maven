inherits a parent project

### What configuration is auto-configured?

1. the version of dependencies, they are specified by the parent project
2. view resolvers (since Thymeleaf is added to classpath)
3. static resources(used one of the default static resource lcoations: /public/)
4. data source(using H2 database, autoconfigured by Spring Boot)
5. JdbcTemplate bean
6. Wiring `schema.sql`(used default location: classpath root)
7. However, `@ComponentScan` is required
8. `@EnableAutoConfiguration` is set

How to run the project:

1. run the main class and visit: http://localhost:8080/
2. deploy it like a real deployment
   1. `Application.java` must extends `SpringBootServletInitializer` and `@override` configure
   2. use `mvn clean package` to create a war file
   3. shutdown tomcat
   4. put the war file in folder webapp
   5. start tomcat and the war file will be automatically extracted to a folder with same name
   6. visit `http://localhost:8080/my_app/`, my_app is the war file's name