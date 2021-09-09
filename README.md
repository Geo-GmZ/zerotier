
#Run your own Zerotier Controller from Docker behind Nginx Proxy Manager.

##Pre-requisites: 

### 1-) Create Private Internal Bridge Network on Docker.

```
docker network create -d bridge my-bridge-network
```

#### 2-) Run Docker Compose:

```
docker-compose up -d
```

### 3-) Then Configure Nginx Proxy Manager:

  3.a) Go to "Proxy Hosts".
  
  ![image](https://user-images.githubusercontent.com/22604334/132641646-e086224c-4a55-498f-9c2a-a823dcd49ef6.png)

  3.b) Then "Add A Proxy Host".
  
  ![image](https://user-images.githubusercontent.com/22604334/132641819-6b77dce8-b7ca-40d3-9c05-9d4647c09af6.png)

  3.c) Configure the Proxy Host.
  
  ![image](https://user-images.githubusercontent.com/22604334/132641318-0081ab31-0efb-4df1-8ea8-c142d03bd700.png)


