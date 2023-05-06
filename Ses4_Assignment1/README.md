Task: 
_________

1. Take existing Node.js app and Dockerize it.
2. Make `Dockerfile`. Build it. Test it. Push it. (rm it) (locally). Run it.  
Expect the build and testing part to be iterative coz it’s gonna be hard to get it right in the first go.
3. Expect this to be iterative. 
4. Details in dockerfile-assignment-1/Dockerfile directory in the root of the repo that u downloaded from git, 
5. Use the Alpine version of the official ‘node’ 6.x image.( so u can use any of the options used underneath the 6 branch). 
6. Expected result is : that ure actually able to bring it up on ur web browser locally, using the locahost.
7. then once u get it working locally, ure gonna tag it with a proper name so that it’s using ur DockerHub account names and a new repo name that u can create on ur own.  Then ure gonna push it to Docker Hub. 
8. Now if it’s there and it looks correct, then remove the local image our of ur cache, and then we’re gonna run the container one last time so that we’ll actually re-download from DockerHub, and then run it to make sure that it’s working properly.


Instruction given to create Dockerfile:
__________
# Instructions for Assignment

[Build Your Own Dockerfile and Run Containers From It](https://www.udemy.com/course/docker-mastery/learn/lecture/6806638)

This directory contains a Node.js app, and you need to get it running in a container.

No modifications to the app should be necessary, only edits to the Dockerfile in this directory.

## Overview of this assignment

- Imagine another developer gave you the instruction below, and you'll need to interpret them into what the Dockerfile should contain.
- Once the Dockerfile builds correctly, start container locally to make sure it works on [http://localhost](http://localhost)
- Then ensure the image is named properly for your Docker Hub account with a new repository name
- Then push to Docker Hub, and go to [https://hub.docker.com](https://hub.docker.com) to verify you pushed it correctly
- Then remove local image from cache (`docker image rm <name>`)
- Then start a new container from your Hub image, and watch how it auto downloads and runs
- Test again that it works at [http://localhost](http://localhost)

## Instructions from the app developer

- you should use the `node` official image, with the alpine 6.x branch (`node:6-alpine`)
  - (Yes this is a 2-year old image of node, but all official images are always available on Docker Hub forever, to ensure even old apps still work. It is common to still need to deploy old app versions, even years later.)
- This app listens on port 3000, but the container should listen on port 80 of the Docker host, so it will respond to [http://localhost:80](http://localhost:80) on your computer
- Then it should use the alpine package manager to install tini: `apk add --no-cache tini`.
- Then it should create directory /usr/src/app for app files with `mkdir -p /usr/src/app`, or with the Dockerfile command `WORKDIR /usr/src/app`.
- Node.js uses a "package manager", so it needs to copy in package.json file.
- Then it needs to run 'npm install' to install dependencies from that file.
- To keep it clean and small, run `npm cache clean --force` after the above, in the same RUN command.
- Then it needs to copy in all files from current directory into the image.
- Then it needs to start the container with the command `/sbin/tini -- node ./bin/www`. Be sure to use JSON array syntax for CMD. (`CMD [ "something", "something" ]`)
- In the end you should be using FROM, RUN, WORKDIR, COPY, EXPOSE, and CMD commands

## Bonus Extra Credit

- This assignment will not have you setting up a complete image useful for local development, test, and prod. It's just meant to get you started with basic Dockerfile concepts and not focus too much on proper Node.js use in a container. **If you happen to be a Node.js Developer**, then after you get through more of this course, you should come back and use my [Node.js Docker Good Defaults](https://github.com/BretFisher/node-docker-good-defaults) sample project on GitHub to change this Dockerfile for better local development with more advanced topics.



MY_NOTES: 
_______
I just crated the Dockerfile, this is the only file I made modifications to, rest all in this scenario was provided by the nodejs user.</br>
- For dealing with dockerfiles, `docker build -f some_dockerfile`</br>
- for creating a custom image, (a dockerfile should be there).</br>

The **`docker image build -t customnginx .`** command is used to build a Docker image from the Dockerfile in the current directory (indicated by the **`.`**) and tag the resulting image with the name **`customnginx`**.</br>

Here's a breakdown of the command:
</br></br>
- **`docker image build`**: This is the command used to build a Docker image from a Dockerfile.</br> 
- **`t customnginx`**: This flag, **`t`**, followed by the name **`customnginx`**, assigns a tag to the resulting image. 
- In this case, the tag is "customnginx". Tags are used to name and version Docker images, making it easier to manage and reference them later.</br>
- For simply tagging an image with another image, `dokcer image tag nginx bretfisher/nginx`  (tagging nginx as bretfisher/nginx)</br>
