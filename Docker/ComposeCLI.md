## Compose CLI ##

``` docker-compose up -d ``` starts the container in the background and leaves them running.   
``` docker-compose stop``` stops all running container 
``` dockker-compose stop <container>``` stops specific container  
``` docker-compose rm  -f``` remove container 
``` docker-compose rm -f <container>``` remove specific container    
``` docker-compose rm -v``` remove volumes attached to container 


### Docker Compose YML ###

A service definition is much like passing command-line parameters to ```docker container create```.
Likewise, network and volume definition are analogous to ```docker network create``` and ```docker volume create```   

