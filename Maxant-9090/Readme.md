## Build Docker File"
```  docker build -t anoop4686/maxant-9090:v1 . ```

## RUN Docker container ###
``` docker run --name gym -d -it -p 9090:80 anoop4686/Maxant-9090:v1```
``` or ```
``` docker run --name gym -d -it -P anoop4686/Maxant:v1```


### Run Conatine shell mode ###
``` docker exec -it webserver /bin/bash```

### remove all exidted coinated ##