
###Run your own Zerotier Controller from Docker behind Nginx Proxy Manager.

Pre-requisites: 
Create Private Internal Bridge Network on Docker.

```
docker network create -d bridge my-bridge-network
```

Run Docker Compose:

```
docker-compose up -d
```

