# Part 1

From: https://docs.docker.com/get-started/workshop/02_our_app/

## Prerequisites
- Have the [latest version of docker installed](https://docs.docker.com/engine/install/ubuntu/)
- Have a [git client installed](https://git-scm.com/install/linux)
- Have an IDE or text editor [Visual Studio Code Suggested](https://code.visualstudio.com/download)

## Get the App
1. For the purpose of this assignment, I have forked the repository referenced in the workshop.
- Docker advise cloning https://github.com/docker/getting-started-app 
- To remove the risk of any changes being made in the source repo, I have forked it. The forked repo can be found at https://github.com/dstuartkelly/docker-getting-started-app
```bash
git clone git@github.com:dstuartkelly/docker-getting-started-app.git
```
![img](./images/01-clone-app.png)

## Build the App's Image
 The included [Dockerfile](./Dockerfile) is provided by the Docker workshop. This file should be placed in the root directory of the repo I cloned during the [previous step](#get-the-app). I built the image using the command ```docker build -t getting-started .```

 ![Building docker image](./images/02-docker-bulild.png)

## Start an app container
I then ran the app with the command 
```docker run -d -p 127.0.0.1:3000:3000 getting-started```

![Docker Run](./images/03-docker-run.png)
![ToDo App](./images/04-to-do.png)

## Summary
In this section I cloned a repo and created a [Dockerfile](./Dockerfile) to build an image.
I used this image to start a container and saw the app running.

[Continue to Part 2](./Part2.md)