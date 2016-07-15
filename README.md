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
```
##Check that it works
Bring up localhost:8080 in your browser and you should see Hello Docker World.
