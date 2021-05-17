'''

root@devops:/home/azamat/Docker/Docker_05# cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 10 | head -n 1
UEyVugkIMV

root@devops:/home/azamat/Docker/Docker_05# docker run -d --name rbm-dkr-05-run-"$(cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 10 | head -n 1)" nginx:stable
485e72e7644224eca345bcf18b8e2b02b09e32315df65b451521b7cf9c6942e9

root@devops:/home/azamat/Docker/Docker_05# docker run -d --name rbm-dkr-05-run-"$(cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 10 | head -n 1)" nginx:stable
7c0d832c3fed1144a82f3bbcfea7b46d8ade4f57c0eec1504e099c53ce3ff9ec


root@devops:/home/azamat/Docker/Docker_05# docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS          PORTS     NAMES
7c0d832c3fed   nginx:stable   "/docker-entrypoint.…"   3 seconds ago    Up 2 seconds    80/tcp    rbm-dkr-05-run-swr9wVXgEE
485e72e76442   nginx:stable   "/docker-entrypoint.…"   12 seconds ago   Up 12 seconds   80/tcp    rbm-dkr-05-run-iVS8wjTbwi

root@devops:/home/azamat/Docker/Docker_05# docker run -d --name rbm-dkr-05-stop nginx:stable
0b8ec5c52e5d289eb77858a063272e568875ee7cfa40e2728d15a8eb92b9619d

root@devops:/home/azamat/Docker/Docker_05# docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED              STATUS              PORTS     NAMES
0b8ec5c52e5d   nginx:stable   "/docker-entrypoint.…"   3 seconds ago        Up 1 second         80/tcp    rbm-dkr-05-stop
7c0d832c3fed   nginx:stable   "/docker-entrypoint.…"   About a minute ago   Up About a minute   80/tcp    rbm-dkr-05-run-swr9wVXgEE
485e72e76442   nginx:stable   "/docker-entrypoint.…"   About a minute ago   Up About a minute   80/tcp    rbm-dkr-05-run-iVS8wjTbwi

root@devops:/home/azamat/Docker/Docker_05# docker stop rbm-dkr-05-stop
rbm-dkr-05-stop

root@devops:/home/azamat/Docker/Docker_05# docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS         PORTS     NAMES
7c0d832c3fed   nginx:stable   "/docker-entrypoint.…"   2 minutes ago   Up 2 minutes   80/tcp    rbm-dkr-05-run-swr9wVXgEE
485e72e76442   nginx:stable   "/docker-entrypoint.…"   2 minutes ago   Up 2 minutes   80/tcp    rbm-dkr-05-run-iVS8wjTbwi

root@devops:/home/azamat/Docker/Docker_05# docker stop $(docker ps -aq)
0b8ec5c52e5d
7c0d832c3fed
485e72e76442

root@devops:/home/azamat/Docker/Docker_05# docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

root@devops:/home/azamat/Docker/Docker_05# docker rm $(docker ps -aq)
0b8ec5c52e5d
7c0d832c3fed
485e72e76442

root@devops:/home/azamat/Docker/Docker_05# docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES


'''
