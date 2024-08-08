# Static Website Docker Container

## Introduction
This repository contains a simple static website and a Docker configuration to serve the site using Nginx. By using Docker, we ensure that our website runs consistently across different environments without worrying about dependencies and server configurations.

This project demonstrates how to run a static website (HTML, CSS, and JavaScript) inside a Docker container using Nginx as the web server.

## Table of Contents
* [Introduction](#introduction)
* [Dockerfile](#dockerfile)
* [Prerequisites](#prerequisites)
* [Building the Docker Image](#building-the-docker-image)
* [Running the Docker Container](#running-the-docker-container)   


## Prerequisites

Before you begin, make sure you have Docker installed on your machine. You can download and install Docker from Docker's official website.  

## Lets write a Docker file first 

```dockerfile
#This is the Docker file we will be using for our project 
FROM nginx:alpine

COPY . /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"] 
```

## How It Works

Dockerfile Breakdown

Base Image:- We use the official Nginx image (nginx:alpine) as the base image. Alpine is a lightweight Linux distribution, making the image small and efficient.

Copy Files:- We copy all the files from the current directory (.) to the Nginx HTML directory (/usr/share/nginx/html).

Expose Port:- We expose port 80, the default HTTP port, so that the web server can be accessed.

CMD Instruction:- The CMD instruction runs Nginx in the foreground (daemon off;), ensuring that the Docker container remains running.

## Building the Docker Image
 
 To build the Docker file just run 

```
docker build -t my-static-website .
```
Note: Replace the my-staric-website with the tag name you want for your image

Once you build the docker image you can run the docker image but running 

 ## Running the Docker Container

 ```
 docker run -p 80:80 my-static-website
```
Note: You can use any port am using port 80
 
Now open your web browser and go to http://localhost:80 to see your website.



#
