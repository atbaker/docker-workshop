# Exercise 2: Fire it up!

It's time to start your first Docker containers! This exercise will start with "Hello World" and end with some more advanced Docker commands.

**I won't provide all the answers here. To complete this (and future) exercises, you will need to use the [Docker documentation](https://docs.docker.com/) and your intuition!**

## "Hello Docker!"

Pull down the `busybox` image from the Docker Hub. You will need to use the [docker pull](https://docs.docker.com/reference/commandline/cli/#pull) command to do so.

Once you've done that, start a new container from that image which runs the command `echo Hello Docker!`. You will need to use the [docker run](https://docs.docker.com/reference/commandline/cli/#run) command.

If your container returns the string `Hello Docker!` to your terminal, then you succeeded!

## A basic webserver

Pull down this Docker image from the Docker Hub: `atbaker/nginx-example`

This Docker image uses the [Nginx](http://nginx.org/) webserver to serve a static HTML website.

Start a new container from the `atbaker/nginx-example` image that exposes port 80 from the container to port 8000 on your host. You will need to use the `-p` flag with the docker run command.

Open a web browser and go to http://localhost:8000 (see below if on Mac or Windows). If you see "Hello Docker" then you're done! Press control + c in your terminal window to stop your container.

**Note that if you're on a Windows or Mac, exposing your container to a port on your "host" actually exposes that port to the boot2docker virtual machine.** In a different terminal window, use the command `boot2docker ip` to get the virtual machine's IP address. Use that IP address instead of localhost to access your container.

## More advanced docker commands

Before you go on, use the [docker command line interface](https://docs.docker.com/reference/commandline/cli/) documentation to try a few more commands:

- Start the same container exposing the same port, but run the container in "detached" mode, so that it doesn't tie up your command line
- While your detached container is running, use the `docker ps` command to see what silly name Docker gave your container
- While your detached container is still running, look at its logs. Try following its logs and refreshing your browser.
- Stop your detached container. Then delete that container from your system.

When you're ready to create your own Docker images, move on to [Exercise 3](exercise-3.md)!
