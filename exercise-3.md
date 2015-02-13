# Exercise 3: Working with images

This exercise starts off with exploring a Docker image's history, checks out an easy way to get a Postgres database, and ends with your first Docker image on the Docker Hub.

**I won't provide all the answers here. To complete this (and future) exercises, you will need to use the [Docker documentation](https://docs.docker.com/) and your intuition!**

## Anatomy of an image

Docker images are just portable, saved states of Docker containers. They're how you move your Dockerized applications from your development machine to the world.

Let's examine the Docker image we used in the last exercise, `atbaker/nginx-example`. Look at the commands used to create that image with the `docker history` command.

If you're curious about how Docker images work, you can read more about it here: https://docs.docker.com/introduction/understanding-docker/#how-does-a-docker-image-work

## The fastest database installation you'll ever do

Pull down the `9.4` tag on the `postgres` image from the Docker Hub. While it's pulling down, learn more about it on its [official page on the Docker Hub](https://registry.hub.docker.com/u/library/postgres/).

Start a new container from the Postgres database with the docker run command. Watch with delight as you start a new database service in seconds.

This is one reason why using Docker in development environments is so fun. You can get virtually any programming language or any server appliance running on your machine in minutes. And they won't clutter up anything else on your system.

## Creating your first image

Pull down the `atbaker/redis-example` image. This image contains a [redis](http://redis.io/) server. 

As it is right now, anyone can connect to our redis server when it's running. In this exericse, we will add a password to the redis server's configuration to make it more secure.

Start a new container from that image running the `bash` command so you can get an interactive terminal inside that container.

**NOTE:** You will need to pass two additional flags to the docker run command to get it to launch an interactive terminal session.

Using the nano command-line text editor of your choice (unfortunately you cannot install any others in this image), edit the file `/usr/src/custom-redis.conf`. 

Uncomment the `requirepass` line in the file (you can optionally change the password provided). Then save the file, exit your text editor, and use control + d to end your shell session in the container.

Now that we've added a password to our Redis server in a container on our laptop, we want to use that updated Redis server somewhere else - maybe on a production in the cloud. To make the changes we just made in our container portable, we're going to create a new image.

Use the `docker ps -l` command to see the most recently run container. Copy the container id (or the silly Docker name) of that container.

Make a new commit using the docker commit command. Make sure the last argument in your command is `redis-password` - that will be the name of our new image. Reference the [documentation](https://docs.docker.com/reference/commandline/cli/#commit) if you need a hint.

## Pushing to the Docker Hub

Congratulations, you're the parent of a new Docker image! The best place to share that image with the world is the Docker Hub.

Create an account on the Docker hub by running the `docker login` command.

Once logged in, use the [docker tag command](https://docs.docker.com/reference/commandline/cli/#tag) to put our `redis-password` image inside your Docker Hub namespace. If I was doing it for my account, I would run:

```
docker tag redis-password atbaker/redis-password
```

After that, all we need to do is push our image up to the Docker Hub! Do that with the Docker push command:

```
docker push [your namespace]/redis-password
```

Now your new image is available for anyone to use! https://hub.docker.com/u/

Once you're done with that, you can wrap things up with [Exercise 4](exercise-4.md).
