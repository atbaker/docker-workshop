# Docker hands-on workshop

This two hour workshop will take you from "Hello Docker" to deploying a containerized web application to a server.

**There are a few things you should know about this tutorial before you begin:**

This tutorial is designed to be self-paced to make the most of your time.

The exercises won't always tell you exactly what you need to do. Instead, I will try to point you to the right resources (documentation, blog posts, etc.) to find the answer. I prefer this approach because it helps you learn how to find answers about Docker questions you have in the future.

Please don't be shy about asking questions to the instructors or your neighbors! We're all friendly here, and it wasn't long ago that all of us were Docker beginners. :grin:

## Exercise 0: Install Docker

The first thing you need to do is install Docker on your laptop! Follow the instructions in the section for your operating system.

### Linux

Check out the list of Linux distributions here: https://docs.docker.com/installation/. Find yours and follow the instructions to install Docker.

For today, it's probably okay if you're running the version of Docker that's part of your distributions package manger. In the future, though, you should consider adding the official Docker repository to make sure you get the latest version of Docker.

**While Docker is dowloading and installing, you can continue to Exercise 1.**

### Mac OS X

A handy open source project called [boot2docker](https://github.com/boot2docker/boot2docker) makes it easy to run Docker on OS X and Windows.

Download the file at this URL to install the latest version of boot2docker for OS X: https://github.com/boot2docker/osx-installer/releases/latest

After you have installed boot2docker, run these commands in a terminal window:

```bash
$ boot2docker init
$ boot2docker start
$ $(boot2docker shellinit)
```

**While Docker is dowloading and installing, you can continue to Exercise 1.**

### Windows

A handy open source project called [boot2docker](https://github.com/boot2docker/boot2docker) makes it easy to run Docker on OS X and Windows.

Follow the instructions here to install boot2docker on your machine: https://docs.docker.com/installation/windows/

**While Docker is dowloading and installing, you can continue to Exercise 1.**
