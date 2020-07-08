# Network drivers

### Bridge
* Default
* Comunications only by IP (`--link` is legacy)
* Default network each containers can connect

* `docker network create -d bridge mybridge`
* `docker run -d --net mybridge --name db postgres:latest`
* `docker run -d --net mybridge -e DB=db -p 8080:3000 --name web mywebapp:1.0`

* Each container has own `IP`

* Check containers in network `docker network inspect <network_name>`

* Connect container to network `docker network connect <network_name> <container_name>` (container can be connected to multiple networks)