### zerotier in Docker.

##Pre-Requisites:
#Create an internal network only reacheable by your containers.
```
docker network create <yournetworkname>


###docker-compose.yml file.

```  
version: '3'

volumes:
  ztncui:
  zt1:

services:
  ztncui:
    image: keynetworks/ztncui
    container_name: ztncui
    environment:
      - USER_UID=1000 #adjust to your system
      - USER_GID=1000 #adjust to your system
      - NODE_ENV=production
      - HTTPS_PORT=3443
      - ZTNCUI_PASSWD=R3publ1c4d0m!809  #change this
      - MYDOMAIN=ztc1.duckdns.org #change this to the domain you want to use for the controller
#      - MYADDR=172.104.16.120 #this is optional. if you use it, this is the public IP your ISP gave you
    volumes:
      - ztncui:/opt/key-networks/ztncui/etc
      - zt1:/var/lib/zerotier-one
    networks:
      nginx_proxy_internal_net: ##<--- Your internal bridge network name.
        ipv4_address: "172.16.238.110" ##<---Static IP of your container inside internal bridge network.
    ports:
 #     - 3443:3443 #dashboard port
      - 3180:3180 ##<---Only port exposed from the container.

networks:
  default:
    external:
      name: nginx_proxy_internal_net ##<--- Your Internal bridge network name.
  nginx_proxy_internal_net: ##<--- Your internal bridge network name.
    external: true


