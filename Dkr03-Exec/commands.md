'''
root@devops:/home/azamat/Docker/Docker_03# docker run -d -p 127.0.0.1:8890:80 --name rbm-dkr-03 -v /home/azamat/Docker/Docker_03/nginx.conf:/etc/nginx/nginx.conf nginx:stable
1ce2528044d372121495d502e403db4a52afe1f1aac780c2361b5bf326abb807

root@devops:/home/azamat/Docker/Docker_03# docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS         PORTS                    NAMES
1ce2528044d3   nginx:stable   "/docker-entrypoint.…"   3 seconds ago   Up 2 seconds   127.0.0.1:8890->80/tcp   rbm-dkr-03


root@devops:/home/azamat/Docker/Docker_03# curl 127.0.0.1:8890
Welcome to Docker!


root@devops:/home/azamat/Docker/Docker_03# docker exec -ti rbm-dkr-03 md5sum /etc/nginx/nginx.conf
e70dedb61d0c305b855088ca7bf3742a  /etc/nginx/nginx.conf

root@devops:/home/azamat/Docker/Docker_03# md5sum nginx.conf
e70dedb61d0c305b855088ca7bf3742a  nginx.conf

root@devops:/home/azamat/Docker/Docker_03# cat nginx.conf.new > nginx.conf

root@devops:/home/azamat/Docker/Docker_03# md5sum nginx.conf
1265cde0fefb06a47f02b8c95cc892eb  nginx.conf

root@devops:/home/azamat/Docker/Docker_03# docker exec -it rbm-dkr-03 /etc/init.d/nginx reload
[ ok ] Reloading nginx: nginx.

root@devops:/home/azamat/Docker/Docker_03# docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED              STATUS              PORTS                    NAMES
1ce2528044d3   nginx:stable   "/docker-entrypoint.…"   About a minute ago   Up About a minute   127.0.0.1:8890->80/tcp   rbm-dkr-03

root@devops:/home/azamat/Docker/Docker_03# curl 127.0.0.1:8890
Welcome to Docker! Again!

'''

