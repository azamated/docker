```
root@devops:/home/azamat/Docker/08_Docker_Dockerfile# docker build -t nginx:rbm-dkr-08 .
Sending build context to Docker daemon   5.12kB
Step 1/4 : FROM nginx:stable
 ---> c2c45d506085
Step 2/4 : COPY nginx.conf /etc/nginx
 ---> b9a86df5e344
Step 3/4 : EXPOSE 80
 ---> Running in b29757ca5f35
Removing intermediate container b29757ca5f35
 ---> a65fe4257c41
Step 4/4 : CMD ["nginx", "-g", "daemon off;"]
 ---> Running in a4356cda3a89
Removing intermediate container a4356cda3a89
 ---> 3d45bdf2eb9f
Successfully built 3d45bdf2eb9f
Successfully tagged nginx:rbm-dkr-08

root@devops:/home/azamat/Docker/08_Docker_Dockerfile# docker images
REPOSITORY   TAG          IMAGE ID       CREATED              SIZE
nginx        rbm-dkr-08   3d45bdf2eb9f   About a minute ago   133MB
<none>       <none>       884a10e18267   4 minutes ago        133MB
<none>       <none>       edb7a3a0a18d   10 minutes ago       133MB
nginx        stable       c2c45d506085   13 days ago          133MB

root@devops:/home/azamat/Docker/08_Docker_Dockerfile# docker run -d -p 127.0.0.1:8890:80 nginx:rbm-dkr-08
0f30cfebccbeeef1d14e62da91619f1df6ef998a7eca5eb5020292a524a25b1f

root@devops:/home/azamat/Docker/08_Docker_Dockerfile# docker ps
CONTAINER ID   IMAGE              COMMAND                  CREATED         STATUS         PORTS                    NAMES
0f30cfebccbe   nginx:rbm-dkr-08   "/docker-entrypoint.…"   2 minutes ago   Up 2 minutes   127.0.0.1:8890->80/tcp   serene_villani

root@devops:/home/azamat/Docker/08_Docker_Dockerfile# curl 127.0.0.1:8890
Welcome to Docker!

```
