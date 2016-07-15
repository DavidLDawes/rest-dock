#Simple REST example, does not do much, just returns Hello World.
##Clone it from github
###With ssh credentials in place
git clone git@github.com:DavidLDawes/rest-dock.git
###With https
git clone https://github.com/DavidLDawes/rest-dock.git

##Once cloned, build it
```
cd rest-dock
./gradlew build buildDocker
```
Assuming everything cloned and built properly you should find the fresh image in docker using the images command.
```
>docker images
REPOSITORY                                TAG                 IMAGE ID            CREATED             SIZE
virtualsoundnw/spring-boot-docker         latest              575743b06589        38 seconds ago      193.8 MB
>
```
##Launch it in Docker
The image can be used to run it, for this case remember to map the port through
```
docker run -p 8080:8080 virtualsoundnw/spring-boot-docker

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::        (v1.3.5.RELEASE)

2016-07-15 23:11:40.419  INFO 1 --- [           main] hello.Application                        : Starting Application on a84e1ed96d72 with PID 1 (/spring-boot-docker-0.1.0.jar started by root in /)
2016-07-15 23:11:40.421  INFO 1 --- [           main] hello.Application                        : No active profile set, falling back to default profiles: default
2016-07-15 23:11:40.458  INFO 1 --- [           main] ationConfigEmbeddedWebApplicationContext : Refreshing org.springframework.boot.context.embedded.AnnotationConfigEmbeddedWebApplicationContext@5e156c11: startup date [Fri Jul 15 23:11:40 GMT 2016]; root of context hierarchy
2016-07-15 23:11:41.291  INFO 1 --- [           main] s.b.c.e.t.TomcatEmbeddedServletContainer : Tomcat initialized with port(s): 8080 (http)
2016-07-15 23:11:41.301  INFO 1 --- [           main] o.apache.catalina.core.StandardService   : Starting service Tomcat
2016-07-15 23:11:41.302  INFO 1 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet Engine: Apache Tomcat/8.0.33
2016-07-15 23:11:41.378  INFO 1 --- [ost-startStop-1] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2016-07-15 23:11:41.378  INFO 1 --- [ost-startStop-1] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 922 ms
2016-07-15 23:11:41.569  INFO 1 --- [ost-startStop-1] o.s.b.c.e.ServletRegistrationBean        : Mapping servlet: 'dispatcherServlet' to [/]
2016-07-15 23:11:41.573  INFO 1 --- [ost-startStop-1] o.s.b.c.embedded.FilterRegistrationBean  : Mapping filter: 'characterEncodingFilter' to: [/*]
2016-07-15 23:11:41.574  INFO 1 --- [ost-startStop-1] o.s.b.c.embedded.FilterRegistrationBean  : Mapping filter: 'hiddenHttpMethodFilter' to: [/*]
2016-07-15 23:11:41.574  INFO 1 --- [ost-startStop-1] o.s.b.c.embedded.FilterRegistrationBean  : Mapping filter: 'httpPutFormContentFilter' to: [/*]
2016-07-15 23:11:41.574  INFO 1 --- [ost-startStop-1] o.s.b.c.embedded.FilterRegistrationBean  : Mapping filter: 'requestContextFilter' to: [/*]
2016-07-15 23:11:41.763  INFO 1 --- [           main] s.w.s.m.m.a.RequestMappingHandlerAdapter : Looking for @ControllerAdvice: org.springframework.boot.context.embedded.AnnotationConfigEmbeddedWebApplicationContext@5e156c11: startup date [Fri Jul 15 23:11:40 GMT 2016]; root of context hierarchy
2016-07-15 23:11:41.811  INFO 1 --- [           main] s.w.s.m.m.a.RequestMappingHandlerMapping : Mapped "{[/]}" onto public java.lang.String hello.Application.home()
2016-07-15 23:11:41.813  INFO 1 --- [           main] s.w.s.m.m.a.RequestMappingHandlerMapping : Mapped "{[/error],produces=[text/html]}" onto public org.springframework.web.servlet.ModelAndView org.springframework.boot.autoconfigure.web.BasicErrorController.errorHtml(javax.servlet.http.HttpServletRequest,javax.servlet.http.HttpServletResponse)
2016-07-15 23:11:41.813  INFO 1 --- [           main] s.w.s.m.m.a.RequestMappingHandlerMapping : Mapped "{[/error]}" onto public org.springframework.http.ResponseEntity<java.util.Map<java.lang.String, java.lang.Object>> org.springframework.boot.autoconfigure.web.BasicErrorController.error(javax.servlet.http.HttpServletRequest)
2016-07-15 23:11:41.832  INFO 1 --- [           main] o.s.w.s.handler.SimpleUrlHandlerMapping  : Mapped URL path [/webjars/**] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
2016-07-15 23:11:41.832  INFO 1 --- [           main] o.s.w.s.handler.SimpleUrlHandlerMapping  : Mapped URL path [/**] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
2016-07-15 23:11:41.860  INFO 1 --- [           main] o.s.w.s.handler.SimpleUrlHandlerMapping  : Mapped URL path [/**/favicon.ico] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
2016-07-15 23:11:41.924  INFO 1 --- [           main] o.s.j.e.a.AnnotationMBeanExporter        : Registering beans for JMX exposure on startup
2016-07-15 23:11:41.966  INFO 1 --- [           main] s.b.c.e.t.TomcatEmbeddedServletContainer : Tomcat started on port(s): 8080 (http)
2016-07-15 23:11:41.969  INFO 1 --- [           main] hello.Application                        : Started Application in 1.83 seconds (JVM running for 2.193)
```
##Check that it works
Bring up localhost:8080 in your browser and you should see Hello Docker World.
##Stop the container
###First find the name using docker ps
```
docker ps
CONTAINER ID        IMAGE                               COMMAND                  CREATED             STATUS              PORTS                    NAMES
5dd2083181c4        virtualsoundnw/spring-boot-docker   "java -Djava.security"   18 seconds ago      Up 17 seconds       0.0.0.0:8080->8080/tcp   jolly_stallman
```
In this case it's jolly_stallman
###Stop the container using the name
Use the docker stop command with the name reported via docker ps and it stops that container:
```
>docker stop jolly_stallman
jolly_stallman
>
```

