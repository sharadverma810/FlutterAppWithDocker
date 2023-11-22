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
