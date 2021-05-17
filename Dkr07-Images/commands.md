```
root@devops:/home/azamat/Docker/Docker_07# docker pull nginx:stable-alpine
stable-alpine: Pulling from library/nginx
540db60ca938: Pull complete
3b88e9e9a17d: Pull complete
3019f265923a: Pull complete
fd39c3601fe1: Pull complete
4d0e0e4dee17: Pull complete
f81ca69df58f: Pull complete
Digest: sha256:e015192ec74937149dce3aa1feb8af016b7cce3a2896246b623cfd55c14939a6
Status: Downloaded newer image for nginx:stable-alpine

root@devops:/home/azamat/Docker/Docker_07# docker images
REPOSITORY   TAG             IMAGE ID       CREATED        SIZE
nginx        stable-alpine   3b715e351972   12 hours ago   22.6MB
nginx        latest          62d49f9bab67   8 days ago     133MB
nginx        stable          c2c45d506085   12 days ago    133MB

root@devops:/home/azamat/Docker/Docker_07# docker image tag nginx:stable-alpine nginx:rbm-dkr-07
root@devops:/home/azamat/Docker/Docker_07# docker images
REPOSITORY   TAG             IMAGE ID       CREATED        SIZE
nginx        rbm-dkr-07      3b715e351972   12 hours ago   22.6MB
nginx        stable-alpine   3b715e351972   12 hours ago   22.6MB
nginx        latest          62d49f9bab67   8 days ago     133MB
nginx        stable          c2c45d506085   12 days ago    133MB

root@devops:/home/azamat/Docker/Docker_07# docker run -d --name tagged-nginx  nginx:rbm-dkr-07
595557a7be867f5536c0dea913e8e942f9a24e045e457afa65a648dfb98366f8

root@devops:/home/azamat/Docker/Docker_07# docker ps
CONTAINER ID   IMAGE              COMMAND                  CREATED         STATUS         PORTS     NAMES
595557a7be86   nginx:rbm-dkr-07   "/docker-entrypoint.…"   2 seconds ago   Up 2 seconds   80/tcp    tagged-nginx

```
