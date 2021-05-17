'''
# docker run -d -p 127.0.0.1:8889:80 --name rbm-dkr-02 -v /home/Docker_02/nginx.conf:/etc/nginx/nginx.conf nginx
d4374a317fa06ee0722930dba4b2849613381cb9aff157cf80fd0c1632d9dfd9

# docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS                    NAMES
d4374a317fa0   nginx     "/docker-entrypoint.…"   4 seconds ago   Up 3 seconds   127.0.0.1:8889->80/tcp   rbm-dkr-02

# curl 127.0.0.1:8889
Welcome to Docker!

# docker exec -ti rbm-dkr-02 md5sum /etc/nginx/nginx.conf
e70dedb61d0c305b855088ca7bf3742a  /etc/nginx/nginx.conf

# md5sum nginx.conf
e70dedb61d0c305b855088ca7bf3742a  nginx.conf

'''
