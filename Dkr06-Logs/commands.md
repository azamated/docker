'''
root@devops:/home/azamat/Docker/Docker_05# docker run -d -p 127.0.0.1:8892:80 --name rbm-dkr-06-local --log-driver json-file --log-opt max-size=10m nginx:stable
4eb9bbaa2e565bad36cb17fb0f0b299e762357a693f4c33050fde0c3b3a34dae

9611de435437
root@devops:/home/azamat/Docker/Docker_05# docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS          PORTS                    NAMES
4eb9bbaa2e56   nginx:stable   "/docker-entrypoint.…"   19 seconds ago   Up 18 seconds   127.0.0.1:8892->80/tcp   rbm-dkr-06-local

root@devops:/var/lib/docker/containers/4eb9bbaa2e565bad36cb17fb0f0b299e762357a693f4c33050fde0c3b3a34dae# curl --silent http://127.0.0.1:8892 > /dev/null

root@devops:/var/lib/docker/containers/4eb9bbaa2e565bad36cb17fb0f0b299e762357a693f4c33050fde0c3b3a34dae# cat 4eb9bbaa2e565bad36cb17fb0f0b299e762357a693f4c33050fde0c3b3a34dae-json.log
{"log":"/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration\n","stream":"stdout","time":"2021-04-17T19:25:41.993110667Z"}
{"log":"/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/\n","stream":"stdout","time":"2021-04-17T19:25:41.993137215Z"}
{"log":"/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh\n","stream":"stdout","time":"2021-04-17T19:25:41.993580804Z"}
{"log":"10-listen-on-ipv6-by-default.sh: Getting the checksum of /etc/nginx/conf.d/default.conf\n","stream":"stdout","time":"2021-04-17T19:25:41.999513013Z"}
{"log":"10-listen-on-ipv6-by-default.sh: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf\n","stream":"stdout","time":"2021-04-17T19:25:42.009409886Z"}
{"log":"/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh\n","stream":"stdout","time":"2021-04-17T19:25:42.00967536Z"}
{"log":"/docker-entrypoint.sh: Configuration complete; ready for start up\n","stream":"stdout","time":"2021-04-17T19:25:42.013506832Z"}
{"log":"172.17.0.1 - - [17/Apr/2021:19:32:21 +0000] \"GET / HTTP/1.1\" 200 612 \"-\" \"curl/7.68.0\" \"-\"\n","stream":"stdout","time":"2021-04-17T19:32:21.835277633Z"}



root@devops:/home/azamat/Docker/Docker_05# docker run -d -p 127.0.0.1:8893:80 --name rbm-dkr-06-global nginx:stable
6400ab4e124c3f7305ef6392726b003bedd7e6927137682be37a9a8351c57dc0


root@devops:/home/azamat/Docker/Docker_05# docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS          PORTS                    NAMES
6400ab4e124c   nginx:stable   "/docker-entrypoint.…"   4 seconds ago    Up 3 seconds    127.0.0.1:8893->80/tcp   rbm-dkr-06-global
4eb9bbaa2e56   nginx:stable   "/docker-entrypoint.…"   15 minutes ago   Up 15 minutes   127.0.0.1:8892->80/tcp   rbm-dkr-06-local

root@devops:/home/azamat/Docker/Docker_05# curl --silent http://127.0.0.1:8893 > /dev/null

root@devops:/home/azamat/Docker/Docker_05# cat /var/lib/docker/containers/6400ab4e124c3f7305ef6392726b003bedd7e6927137682be37a9a8351c57dc0/6400ab4e124c3f7305ef6392726b003bedd7e6927137682be37a9a8351c57dc0-json.log
{"log":"/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration\n","stream":"stdout","time":"2021-04-17T19:41:21.031165523Z"}
{"log":"/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/\n","stream":"stdout","time":"2021-04-17T19:41:21.031219644Z"}
{"log":"/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh\n","stream":"stdout","time":"2021-04-17T19:41:21.036364563Z"}
{"log":"10-listen-on-ipv6-by-default.sh: Getting the checksum of /etc/nginx/conf.d/default.conf\n","stream":"stdout","time":"2021-04-17T19:41:21.043126113Z"}
{"log":"10-listen-on-ipv6-by-default.sh: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf\n","stream":"stdout","time":"2021-04-17T19:41:21.056348021Z"}
{"log":"/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh\n","stream":"stdout","time":"2021-04-17T19:41:21.056783566Z"}
{"log":"/docker-entrypoint.sh: Configuration complete; ready for start up\n","stream":"stdout","time":"2021-04-17T19:41:21.06182596Z"}
{"log":"172.17.0.1 - - [17/Apr/2021:19:41:36 +0000] \"GET / HTTP/1.1\" 200 612 \"-\" \"curl/7.68.0\" \"-\"\n","stream":"stdout","time":"2021-04-17T19:41:36.034077818Z"}

root@devops:/home/azamat/Docker/Docker_05# docker rm $(docker ps -aq) -f
6400ab4e124c
4eb9bbaa2e56
fee076629938
d2cf994bdde3

root@devops:/home/azamat/Docker/Docker_05# docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES



root@devops:/home/azamat/Docker/Docker_05# cat /etc/docker/daemon.json
{
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "10m"
  }
}
'''
