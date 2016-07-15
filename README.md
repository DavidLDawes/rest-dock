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
##Launch it in Docker
