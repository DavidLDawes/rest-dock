FROM frolvlad/alpine-oraclejdk8:slim
VOLUME /tmp
ADD spring-boot-docker-0.1.0.jar spring-boot-docker-0.1.0.jar
RUN sh -c 'touch /spring-boot-docker-0.1.0.jar'
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/spring-boot-docker-0.1.0.jar"]
