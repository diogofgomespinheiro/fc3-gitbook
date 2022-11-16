# Useful commands

## <mark style="color:purple;">Run a new container</mark> <a href="#run-a-new-container" id="run-a-new-container"></a>

```bash
# Start a new container from an image
docker run $IMAGE
docker run nginx

# ... and assign it a name
docker run --name $CONTAINER_NAME $IMAGE
docker run --name web nginx

# ,,, and map a port
docker run -p $HOST_PORT:$CONTAINER_PORT $IMAGE
docker run -p 8080:80 nginx

# ... and map all ports
docker run -P $IMAGE
docker run -P nginx

# ... abd start container in the background
docker run -d $IMAGE
docker run -d nginx

# ... and assign it a hostname
docker run --add-host $HOSTNAME $IMAGE
docker run --add-host srv nginx

# ... and add a dns entry
docker run --add-host $HOSTNAME:$IP $IMAGE

# ... and map a local direcoty into the container
docker run -v $HOSTDIR:$CONTAINER_DIR $IMAGE
docker run -v ~/:/usr/share/nginx/html nginx
# OR (this method throws an error if the directory doesn't exist)
docker run --mount type=bind,source=$HOSTDIR,target=$CONTAINER_DIR $IMAGE

# ... change entry points
docker run -it $COMMAND $IMAGE
docker run -it bash nginx

# ... remove container automatically when it exits
docker run --rm $IMAGE
docker run --rm nginx
```

## <mark style="color:purple;">Manage containers</mark> <a href="#manage-containers" id="manage-containers"></a>

```bash
# show list of running containers
docker ps

# show list of all containers
docker ps -a

# delete container
docker rm $CONTAINER

# delete running container
docker rm -f $CONTAINER

# delete all stopped containers
docker container prune

# stop a running container
docker stop $CONTAINER

# start a stopped container
docker start $CONTAINER

# copy file from container into the host
docker cp $CONTAINER:$SOURCE $TARGET

# copy file from host into container
docker cp $SOURCE $CONTAINER:$TARGET

# run command inside container
docker exec -it $CONTAINER_NAME $COMMAND

# rename container
docker rename $OLD_NAME $NEW_NAME 

# create an image out of a container
docker commit $CONTAINER
```

## <mark style="color:purple;">Manage images</mark> <a href="#manage-images" id="manage-images"></a>

```bash
# Download image
docker pull $IMAGE[:$TAG]

# upload image to repository 
docker push $IMAGE[:$TAG]

# delete image
docker rmi $IMAGE

# show list of used imaged
docker images

# delete dangling images
docker image prune

# delete all unused images
docker image prune -a

# build image from Dockerfile
docker build $DIRECTORY

# tag image
docker tag $IMAGE $NEW_IMAGE

# build image and tag
docker build -t $IMAGE $DIRECTORY

# save image into tar file
docker save $IMAGE > $FILE
docker save nginx > nginx.tar

# load image from tar file
docker load -i $TAR_FILE
```

## <mark style="color:purple;">Info & Stats</mark> <a href="#info-and-stats" id="info-and-stats"></a>

```bash
# show container logs
docker logs $CONTAINER

# show stats of running containers
docker stats

# show processed of container
docker top $CONTAINER

# show docker version
docker version

# get detailed info about an object
docker inspect $NAME

# show all modified files in container
docker diff $CONTAINER

# show container mapped ports
docker port $CONTAINER
```
