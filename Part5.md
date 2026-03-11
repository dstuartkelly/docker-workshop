# Part 5 Use Bind Mounts

From: https://docs.docker.com/get-started/workshop/06_bind_mounts/

## Trying out Bind Mounts
Run the following to start bash in an ubuntu container with a bind mount. 

`` docker run -it --mount type=bind,src=.,target=/src ubuntu bash``

The below screenshot shows us 2 terminals.
1. In the top terminal we start the docker container mounting the local path (this repository) and navigate to the src directory. We can see the path is ``root@814cfacf4e9b:/src`` and we list the files.
2. In the bottom terminal we are listing the files our local machine in the repo directory.
3. In both terminals we can see the same file contents.   

![bind mounts](./images/16-bind-mounts.png)

## Development Containers

### Running the application in a development container

![Docker run dev container](./images/17-starting-dev-container.png)

![modify app](./images/18-modify-app.png)

![modified app](./images/19-to-do.png)

## Putting earlier steps together
At this stage, we want to update our docker image with the changes tested in our development container.

In the [docker-getting-started-app repository](https://github.com/dstuartkelly/docker-getting-started-app) We [commit and push](https://github.com/dstuartkelly/docker-getting-started-app/commit/15e7b5404b68c14b6bb1cb14e3f19ac41a046048) our changes.   
![commit and push](./images/20-commit-app-changes.png)


We build and tag our docker image with the `latest` tag and a new `1.1` tag

![build and tag](./images/21-docker-build-and-tag.png)

Then we push the updated latest image and new 1.1 images to docker hub

![Docker Push](./images/22-docker-push.png)

The updated images can now be seen on the docker hub website and are available publically for anybody to pull and use.

![Docker Hub](./images/23-docker-hub.png)


## Summary
At this point, you can persist your database and see changes in your app as you develop without rebuilding the image.

In addition to volume mounts and bind mounts, Docker also supports other mount types and storage drivers for handling more complex and specialized use cases.

[Continue to Part 6](./Part6.md)