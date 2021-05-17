
'''
### DKR 04 

- Download the nginx config file.

- Create a new volume

- Run a container with the following parameters:

  - should work in the background,

  - listens on host 127.0.0.1:8891

  - should pass the configuration file the container as the main configuration file,
 
  - the image is nginx: stable.
 
  - the volume created must be mounted to the directory with nginx logs

- Check the work by referring to 127.0.0.1:8891 - in response it should return a string Welcome to Docker!

- Print the list of running containers, the container must be running.

- List the existign Docker volumes

- Print the contents of volume on the host system using the ls command with the -la option

- Delete the container and volume.

'''
