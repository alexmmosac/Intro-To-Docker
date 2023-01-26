# Intro-To-Docker
This Repo will give you an Overview of the basics of Docker

# Learning Objectives
Be able to Define Docker and What it is
Describe how Docker is Different then a Typical Virtual machine
Describe The basic Terminology of Docker
Demonstrate a Basic understanding of the Docker Command Line
Demonstrate a Basic understanding of DockerFiles. 

# What is Docker? 
Docker is an open platform for developing, shipping, and running applications. 
Docker enables you to separate your applications from your infrastructure so you can deliver software quickly.

Question: 
Lets say I want John Doe to take a look at my application due to a bug, but my environment is a M1(ARM) MAC and there’s is a Windows 11x64. How can They work on my code to help me with my bug? (No Hardware Programming.) 


# Docker Terminology
Container
Conceptual similar to a VM but the Images are ran by a single kernel which makes running the images(YOUR APP) very fast
Image
An image is essential. This is a Operating system which you might have add your own flare to. You can push and pull images form a Registry(CLOUD) 
Engine 
The Docker engine is the part of Docker will manages your containers and Images.
Docker-File 
A Script used to set the environment need to run your docker image across platforms. This script is where you specify any dependancies for you app.
Registry
A Place in the Cloud that stores all the docker images

# Docker Commandline
`docker pull URL (From registry)`
	This will Grab the Image you want.
`docker images`
	This will show you all the images you have.
`docker run IMAGE_NAME` 
	This will run the docker image.
`docker ps` 
	This will display all the docker containers
`docker Port`
	This will display the ports opened on a container


# Lets Try it Out
Go to: https://labs.play-with-docker.com/
Create a new instance
Type in the command line 
	`docker pull mcr.microsoft.com/mcr/hello-world`
	`docker run mcr.microsoft.com/mcr/hello-world`
Congrats! You ran your first Docker Application.

# Docker Files
So lets talk about docker-files.
`FROM URL`
	Grabs our Image
`ADD folder /path/to/folder`
	This will add our directory to replace the web directory
`EXPOSE port:port`
	This will expose the Ports of our container.

# Fun with Docker Files
Go to: https://labs.play-with-docker.com/
Create a new instance
Type in the command line 
`
	mkdir web
	Cd web 
	Git init 
	git pull https://github.com/alexmmosac/odin-RPS.git
	Cd .. 
	Touch Dockerfile
	Vim docker file
`
Type:
`
	FROM yiisoftware/yii2-php:7.1-apache
	ADD web /app/web
	EXPOSE 80:80 
`
*(HIT : wq -> Then Enter)
`
	Sudo docker build -t rps .
	Sudo docker run -p 8080:80 rps
`
Congrats!   
