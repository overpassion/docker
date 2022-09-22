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

## Passive Mode
설정 파일 vsftpd.conf에 다음을 반드시 추가해야 한다.
설정이 없는 경우 다음 오류가 발생한다.
ETIMEOUT, 425 failed to establish
```
port_promiscuous=YES
#패시브모드로 연결될 ip(포트제외 서버ip만 적어주세요)
pasv_address=192.168.XX.XX
```

## Windows FTP command
```
$ ftp
ftp> open 192.168.100.40

ftp> ls
500 Illegal PORT command.
425 Use PORT or PASV first.


ftp> quote pasv
227 Entering Passive Mode (172,18,0,7,195,80)

ftp> ls
425 Failed to establish connection.
```
