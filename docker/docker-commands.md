# Image

# Container

**docker container run --publish 8888:80 nginx**
> * Download image nginx from docker hub. 
> * Then start new container.
> * Then open port 8888 on host ip (your computer) and routes traffic to container ip on port 80

> It always start **new** container. So you might end up having alot of container from the same image.

> Then you can visit localhost:8888 to view nginx index page.  But this command will run in foreground mean you won't be able to use any other docker command to do other stuff. And if we quit command line the nginx server will stop. Solution We need to run in detach modes.

**docker container run --publish 8888:80 --detach nginx**
> `detach` tell docker to run it in background. It will output a unique container id and run container in background.

**docker container run --publish 8888:80 --detach --name webhost nginx**
> `--name <string>` to provide a name to container otherwise it will randomly create a name for you.

**docker container logs <containerName>**
> this will output logs from that container.

**docker container top <containerName>**
> to list running process of that container

**docker container rm <containerId>**
> to remove **stopped** container.

> **Tips!** : provide multiple containerId separate with space to remove multiple at one time.

**docker container rm -f <containerId>**
> to force remove **running** container

**docker container ls**
> To list running container

**docker container stop <containerId>**
> To stop the running container. 

**docker container start <containerId>**
> To start the stopped container

**docker container ls -a**
> To list all *stopped* container

> **Tips!** for containerId you don't need to provide full container id but only few starting character is enough if its unique amoung other running container. 

# Network

# Other

**docker version**
> To check installed docker version. Which will output `client` and `server` section. Client is the command line while server is the actual docker engine.

**docker info**
> Show alot more info about the docker engine.
