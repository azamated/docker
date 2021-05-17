'''
docker run -d -p 127.0.0.1:28080:80 --name rbm-dkr-01 nginx:stable
Unable to find image 'nginx:stable' locally
stable: Pulling from library/nginx
6f28985ad184: Pull complete
d70c01e66d75: Pull complete
79a94775412e: Pull complete
fdc1f7b7d7db: Pull complete
c4831b93fe53: Pull complete
Digest: sha256:26132ea371bc9b83bc5ad197fef4b1b56577893d549a997201289850daa08524
Status: Downloaded newer image for nginx:stable
c456cd6a6e8b49bce5fed6449941d8d93f6535ca67352a27c4af1eed75c99df2

docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS          PORTS                     NAMES
c456cd6a6e8b   nginx:stable   "/docker-entrypoint.…"   27 seconds ago   Up 25 seconds   127.0.0.1:28080->80/tcp   rbm-dkr-01

curl http://127.0.0.1:28080
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
    body {
        width: 35em;
        margin: 0 auto;
        font-family: Tahoma, Verdana, Arial, sans-serif;
    }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>

docker rm --force rbm-dkr-01
rbm-dkr-01

docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
root@devops:/home/azamat/Docker/Docker_01#

curl http://127.0.0.1:28080
curl: (7) Failed to connect to 127.0.0.1 port 28080: Connection refused

'''
