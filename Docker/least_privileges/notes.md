# Least privilages
* Get user id on host `id -u <username>` -> e.g 1000
* Example usage `docker run -it --user 1000 ubuntu /bin/bash`
* Check users of processes `ps -aux`

* If you see _I have no name!_ -> there is no mapping user id to users in container

* Example of nginx container  
* Run container `docker run --user 1000 -p 80:80 nginx`  
* Logs `docker container logs <container id>`  
* Example output - user 1000 needs permissions/privilages 

### Custom group/user
* Use `Dockerfile` with custom group/user `myredis`  
* Build image `docker-build . -t myredis`  
* Run `docker run -d myredis`  
* Check run processes `ps aux | grep myredis`  

### Check user on run container
* Run process in new container `docker run -itd --name ubuntu-defaultuser ubuntu /bin/bash`
* Check processes on container `docker container top`
* Check process id from container on host `ps -aux | grep bash` -> this process is with `root`!
> root       14703  0.2  0.0  18504  3156 pts/0    Ss+  11:40   0:00 /bin/bash

