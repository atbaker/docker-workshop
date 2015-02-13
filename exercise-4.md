# Exercise 4: Dockerfiles and deploying

In this exercise, you'll combine everything you've learned so far to Dockerize an app from scratch and deploy it to the cloud.

**I *really* won't provide all the answers here. To complete this exericse, you will need to use the [Docker documentation](https://docs.docker.com/) and your intuition!**

## Dockerizing a sample application

Clone or download this Git repository: https://github.com/atbaker/nginx-exercise. It's essentially an un-Dockerized version of the Nginx server we used in Exercise 2.

Using the instructions from [Docker's User Guide](https://docs.docker.com/userguide/dockerimages/#building-an-image-from-a-dockerfile), fill in the blanks in the `Dockerfile` that builds this repository.

You will need to reference the [Nginx installation instructions](http://nginx.org/en/linux_packages.html) as well. The extra configuration file you need for the `CMD` part of the Dockerfile is:

```
CMD ["nginx", "-g", "daemon off;"]
```

When your Dockerfile can successfully build the image, test it by starting a new container from it. If it works, push that image up to the Docker Hub.

## Running your container in the cloud

DigitalOcean is the best hosting service for starting a Docker server quickly. 

If you don't have a DigitalOcean account, you can get $10 in free credit using this link: https://www.digitalocean.com/?refcode=f93f75043f14

Start a new DigitalOcean server (droplet) by clicking "Create Droplet" after logging in. Under the "Select Image" section, choose the "Docker on 14.04" image.

Once your server has booted, SSH into it using the password DigitalOcean sends you. Then use the `docker pull` command to pull down your Dockerized Nginx image from the previous section.

Start a new container exposing port 80 from the container to port 80 on the host, and then visit your DigitalOcean server's IP address in your browser.

Then, bask in the glory of a successful deployment.
