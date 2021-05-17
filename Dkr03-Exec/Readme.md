
'''
### DKR 03 

- Download the nginx config file.

- Run a container with the following parameters:

  - should work in the background,

  - listens on host 127.0.0.1:8890

  - should pass the configuration file the container as the main configuration file,
 
  - the image is nginx: stable.

- Check the work by referring to 127.0.0.1:8890 - in response it should return a string Welcome to Docker!

- Print the list of running containers, the container must be running.

- Download the new nginx config file.

- Change the nginx configuration file located on the host system to a new one.

- Reload nginx without stopping the container using the exec command

- Check the work by referring to 127.0.0.1:8890 - in response it should return the string Welcome to Docker! Again!


'''
