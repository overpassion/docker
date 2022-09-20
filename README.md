# Web Server
## docker build & run
```
$ docker build -t fsweb:1.0 .
$ docker run -itd --net egov-network -p 80:80 --name fsweb fsweb:1.0
```

## docker mount (macOS or Linux)
```
docker run -itd -v ./data:/var/www/html --net egov-network -p 80:80 --name fsweb fsweb:1.0
```
## docker mount (Windows)
```
docker run -itd -v C:/EGOV_MSA/EDU_Workspace/egovframe-msa-edu/docker/data:/var/www/html --net egov-network -p 80:80 --name fsweb fsweb:1.0
```

## connect console
```
docker exec -it {container id} /bin/bash
```


## FTP Server
## docker build & run
```
docker build -t fsftp:1.0 .
docker run -itd --net egov-network -p 21:21 --name fsftp fsftp:1.0
```

## connect passive mode
```
docker run -itd --net egov-network -p 21:21 -p 50000-50010:50000-50010 --name fsftp fsftp:1.0
```

## docker mount (macOS or Linux)
docker run -itd -v ./data:/home/ftpuser --net egov-network -p 21:21 -p 50000-50010:50000-50010 --name fsftp fsftp:1.0

## docker mount (Windows)
docker run -itd -v C:/EGOV_MSA/EDU_Workspace/egovframe-msa-edu/docker/data:/home/ftpuser --net egov-network -p 21:21 -p 50000-50010:50000-50010 --name fsftp fsftp:1.0

## connect console
```
docker exec -it {container id} /bin/bash
docker exec -it 48cef6ae0fc4 /bin/bash
```

## FTP Server
## docker process
```
docker ps -a
```

## docker stop
```
docker stop {container id}
```

## docker remove process
```
docker rm {container id}
```

## docker image list
```
docker images
or
docker image ls
```

## docker image remove
```
docker image rm {image id}
```

