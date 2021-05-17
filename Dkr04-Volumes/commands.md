'''

root@devops:/home/azamat/Docker/Docker_04# docker volume create rbm-dkr-04-volume
rbm-dkr-04-volume

root@devops:/home/azamat/Docker/Docker_04# docker run -d -p 127.0.0.1:8891:80 --name rbm-dkr-04 -v "$(pwd)"/nginx.conf:/etc/nginx/nginx.conf --mount source=rbm-dkr-04-volume,target=/var/log/nginx/external nginx:stable
f78708a26ddf432c24456bd144e98d0379d8d0203dfe14d7f90d80482e0ef374

root@devops:/home/azamat/Docker/Docker_04# docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS         PORTS                    NAMES
f78708a26ddf   nginx:stable   "/docker-entrypoint.…"   3 seconds ago   Up 2 seconds   127.0.0.1:8891->80/tcp   rbm-dkr-04

root@devops:/home/azamat/Docker/Docker_04# curl  127.0.0.1:8891
Welcome to Docker!

root@devops:/home/azamat/Docker/Docker_04# docker volume ls
DRIVER    VOLUME NAME
local     rbm-dkr-04-volume

root@devops:/home/azamat/Docker/Docker_04# docker volume inspect rbm-dkr-04-volume
[
    {
        "CreatedAt": "2021-04-13T22:38:54+03:00",
        "Driver": "local",
        "Labels": {},
        "Mountpoint": "/var/lib/docker/volumes/rbm-dkr-04-volume/_data",
        "Name": "rbm-dkr-04-volume",
        "Options": {},
        "Scope": "local"
    }
]

root@devops:/home/azamat/Docker/Docker_04# ls -la /var/lib/docker/volumes/rbm-dkr-04-volume/_data
total 12
drwxr-xr-x 2 root root 4096 Apr 13 22:38 .
drwx-----x 3 root root 4096 Apr 13 22:35 ..
-rw-r--r-- 1 root root   90 Apr 13 22:39 access.log
-rw-r--r-- 1 root root    0 Apr 13 22:38 error.log

root@devops:/home/azamat/Docker/Docker_04# docker rm -f f78708a26ddf
f78708a26ddf

root@devops:/home/azamat/Docker/Docker_04# docker volume rm rbm-dkr-04-volume
rbm-dkr-04-volume

'''
