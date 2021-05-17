
### DKR 06 

- Run a container with the following parameters:
  - should work in the background

  - listening on host 127.0.0.1:8892
 
  - image is nginx:stable

  - logs must use the local driver and the size of the log file must not exceed 10 MB

- Print a list of running containers

- Aceess a web port of  running nginx once so that the logs are written (for example, curl --silent http://127.0.0.1:8892> / dev / null)

- Output the content of the log file on the host system, in which the container logs are written

- Configure the global saving of logs with the "local" driver and 10 MB log size via the /etc/docker/daemon.json file.

- Run a container with the following parameters:
  
  - should work in the background
  
  - listening on host 127.0.0.1:8893
  
  - image - nginx: stable
  
  - the start command must NOT contain driver parameters

- Print a list of running containers

- Aceess a web port of  running nginx once so that the logs are written (for example, curl --silent http://127.0.0.1:8893> / dev / null)

- Output the content of the log file on the host system, in which the container logs are written

- Stop and remove containers


