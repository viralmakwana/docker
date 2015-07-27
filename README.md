Small repo for creating applications that can be pushed with Docker.

Docker is a way for distributing applications, that includes an easy way of porting applications, deploying code to production and generally easing management of applications. 

Ideally you want only 1 application running inside of a Docker container to make it easier to handle. 

Docker images form the foundation of a container. These images could be complete OS'es albeit very small in size or even applications. These are known as base images. Any changes made to these base images such as installing anything else on top, will result in a new layer being formed ( Parent Image -> Child Image etc ). For the sake of size, its ideal to limit the number of layers when editing images, as the whole point of docker is to keep the size low but funtionality high in creating rich applications that can be used without affecting the host OS.

### Useful Docker Commands ###

$ docker ps - Kind of like 'ps' but for docker. Shows running docker instances.
$ docker history - Shows the layers involved in building up an image 
$ docker images - Shows a list of images
$ docker search <image>*
$ docker pull <image> - Downloads the image you want
$ docker run -it <container> - This is good, because using the -it flags assigns it a TTY terminal and captures STDIN.
$ docker run -p 8080:80 -d <container> - This will map port 8080 on the localhost, to port 80 on the container and run it in detached mode, so you do not need to worry about it. If deploying a Apache application, you would simply navigate to port 8080 on the localhost to see the content on port 80.

Another important aspect of Docker is the use of a dockerfile. This can be used to automate new images with the relevant packages/libraries needed to create the final application. As such its very powerful and can also copy config from the host OS to the container. It can also open any relevant ports, and start any application which is required. This method of automation means that you can deploy applications very quickly without having to worry about manual intervention.

* Could be either an OS, or application.
