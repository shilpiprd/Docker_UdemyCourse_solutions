#The contents of Dockerfile: 
# use this empty Dockerfile to build your assignment

# NOTE: The instructions are now in the README.md file in this directory.
FROM node:6-alpine
#using the base image, on which we're creating layer 

WORKDIR /usr/src/app

COPY package*.json ./


RUN apk add --no-cache tini 
RUN npm install && npm cache clean --force
#&& states that 2nd command will run if 1st command does, it's a good practice to run cleanup in the same line as installation.

COPY . .
  
EXPOSE 3000

CMD ["/sbin/tini", "--", "node", "./bin/www"]
