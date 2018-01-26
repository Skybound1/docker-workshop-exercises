## Cheatsheet

### Docker Images

**`docker image search`** searches for images on Dockerhub
```
docker search ubuntu
```

**`docker image pull`** downloads images
```
docker pull ubuntu
```

**`docker image ls`** lists pulled images
```
docker image ls
```

**`docker image rm`** removes images
```
docker image rm ubuntu
```

**`docker image build`** builds image
```
docker image build /path/to/Dockerfile
```
```
-t, --tag : give our image a name
```

### Docker Containers

**`docker run`** creates and starts a container
```
docker run ubuntu echo hello world
```
```
--name : custom container name for easy reference

-i, --interactive : redirect STDIN

-t, --tty : pseudo-terminal

-d, --detach : detach

-p, --publish 127.0.0.1:8000:80 : map port 80 in your container to localhost:8000

-v, --volume : host/path:container/path

-v, --volume : named_volume:container/path
```

**`docker inspect`** Inspect container
```
docker inspect 13e8cddfdb76
```

**`docker create`** creates a container (without starting it)
```
docker create ubuntu echo hello world
```

**`docker ps`** lists containers
```
docker ps
```
```
-a, --all   : list all containers

-q, --quiet : only show IDs

-l, --latest : only show latest container
```

**`docker start`** starts (re-runs) a container
```
docker start 13e8cddfdb76
```

**`docker stop`** stops a running container
```
docker stop 13e8cddfdb76
docker ps -q | xargs docker stop
```

**`docker rm`** removes a container
```
docker rm 13e8cddfdb76
docker ps -aq | xargs docker rm
```

**`docker exec`** execute a command in a *running* container
```
docker exec -it 13e8cddfdb76 echo hello world
```
```
-i, --interactive : redirect STDIN

-t, --tty : pseudo-terminal
```

### Docker Storage

**`docker volume ls`** list volumes
```
docker volume ls
```

**`docker volume inspect`** inspect volumes
```
docker volume inspect 1a28dcffdb76
```

**`docker cp`** copy from container
```
docker cp 13e8cddfdb76:/data/db /tmp/db
docker cp /tmp/db 13e8cddfdb76:/data/db
```

**Browse a running container on the host**
```
cd /proc/$(docker inspect --format {{.State.Pid}} `docker ps -ql`)/root
```

### Dockerfile

**`FROM base_image`** indicates the image's base image

**`COPY relative/path/host/ /absolute/path/container`** copies files/directories over

**`RUN command arg1 arg2`** runs a command on image build

**`CMD ["command", "arg1", "arg2"]`** command to run on container build


### Docker Compose

**`docker-compose up`** spins up a `docker-compose.yml`
