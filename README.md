# FlutterAppWithDocker
This is the sample flutter application with docker file.

How to run this in docker desktop:

Create the Container​:
To get the container running, we first have to build an image.

docker build -t flutter-on-docker .

This builds an image called flutter-on-docker and uses the current directory as the context for the Dockerfile

when all completed successfully, then run the container by this command-

docker run -d -p 8080:80 --name flutter-on-docker flutter-on-docker


Here, we’re telling docker to create a container called flutter-on-docker using the flutter-on-docker image, and to run it in detached mode while mapping our local port 8080 to the containers port 80.

after all, just run http://localhost:8080/ in browser!

Steps to host container app in Azure:

Step 1:

Create a Container resitry in azure portal like:

admin user: bazinga
password:   7QrLvt9Z+okp*****************************************c6U


Step 2:
Go to VS code and in the terminal use Azure CLI to login by:

az login

Step 3:
Now, do the login in Azure Container Registry by this command:

az acr login --name bazinga.azurecr.io

give user-id and password in command prompt:
bazinga
7QrLvt9Z+okp*******************i+ACRAUIc6U

then run: 
docker images

You will get something like this:

REPOSITORY          TAG       IMAGE ID       CREATED        SIZE
flutter-on-docker   latest    3d98b6bc5767   23 hours ago   45.5MB

Step 4:

Run these two commands one by one:

docker tag 3d98b6bc5767 bazinga.azurecr.io/flutter-web
docker push bazinga.azurecr.io/flutter-web

Step 5:
Go to Azure Portal and verify the newly created Azure Container Registry and then create Azure Container Instance with the same image by

selecting the same subscription, resource group and created container registry!!
then create instance
then all Done!

