#Docker :

Below are the steps that we will be going to perform in the process:

1.Install Git and clone the repo of the Node.js application
2.Install Docker
3.Create and configure a Dockerfile
4.Build a Docker image
5.Create and run a Docker container
6.Access it


Commands:

1. Install Git and clone the repo of the Node.js application

# git clone https://github.com/sanjanathamke/Docker.git


2. Now check the version of the docker once and start the docker and check the status of the docker to know if it is running using the below commands :

# docker -v 
# systemctl start docker
# systemctl status docker

3. Create and configure a Dockerfile
Now we will create and configure a dockerfile as per the requirement of the Node.js application. Change the directory to the cloned project and create Dockerfile there.

Here is the Dockerfile that I have created :

FROM node:16
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 80
CMD ["node", "index.js"]





4. Build a Docker image
Now before starting the build process check if there is any existing container running with the same name.

Use command :

# docker ps
# docker ps -a
Now you are all set to build the image. Use command :

# docker build . -t app


5. Create and run a Docker container
Using the image that has been built we will create a container out of it and run it:

Use the below commands :

# docker run -d --name nodejs-app-cont -p 80:80 app:latest
You can see a container running here which can be accessed on port 80 as we have done the port mapping on port 80.


6. Access it

Now you can take the public IP of the machine and port 80 to access the application.



#To push repository on github

Commands:


# git init
# git add .
# git commit -m 'Added my project'
# git remote add origin https://github.com/sanjanathamke/Docker.git (url of your git repository)
# git push -u -f origin main
