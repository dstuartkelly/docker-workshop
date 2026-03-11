# Part 4 Persist the Database

From: https://docs.docker.com/get-started/workshop/05_persisting_data/

## Container filesystem in practice

In this example I ran the alpine base image using the ``--rm`` flag which instructs docker to remove the container and associated volumes when it exits.  

![touch stat](./images/11-touch-stat.png)  

The first time I ran it I passed the command ``touch greeting.txt`` to the container which creates the file greeting.txt and exits the container (and deletes it because of the --rm flag).

The second time I ran it I passed the command ``stat greeting.txt`` which displays files or file system status if the file exists. When I ran the command this time, I got a *No such file or directory* message because the changes made in the first container did not persist to the second.

Containers start from their image definition each time they start. All changes are lost when the container is stopped & removed.

## Create a volume and start the container

Here I created a new volume for the to-do app and start it.  
![create volume](./images/12-create-volume.png)

I added a few items to the to-do list  
![todo app](./images/13-to-do.png)

## Verify data persists
I got the container ID and then remove it and restart it, this follows the same process used with the Alpine image earlier in this workshop.
![restart container](./images/14-verify-data.png)

However, because the data was stored in a volume, and connected the new container to the volume, the data persisted between deleting and creating a new container.  
![todo app](./images/14-to-do.png)

## Dive into the volume
When I used docker volume inspect, I could see where on the disk of the docker host that the directory is stored and browse the contents of the directory.
![volume inspect](./images/15-volume-inspect.png)

## Summary
Here I used docker volumes to persist data across containers.

[Continue to Part 5](./Part5.md)