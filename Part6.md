# Part 6 Multi Container Apps

From: https://docs.docker.com/get-started/workshop/07_multi_container/

## Start MySQL

Before starting the MySQL container, I am going to create a network for the todo-app
```bash
docker network create todo-app
```
![create network](./images/24-create-network.png)

I then started the mysql:8.0 container and connected it to the newly created network. I also created a new docker volume called ``todo-mysql-data`` to persist the ``/var/lib/mysql`` data from the container.

```bash
docker run -d \
    --network todo-app --network-alias mysql \
    -v todo-mysql-data:/var/lib/mysql \
    -e MYSQL_ROOT_PASSWORD=secret \
    -e MYSQL_DATABASE=todos \
    mysql:8.0
```
![start mysql](./images/25-start-mysql.png)

## Connect to MySQL

The database can be verified by opening an interactive terminal session inside the container using ``docker exec -it`` 

![testing sql](./images/26-connect-mysql.png)

Using dig and nslookup commands in the  [netshoot docker network troubleshooting container](https://hub.docker.com/r/nicolaka/netshoot) demonstrated the ``--network alias mysql`` argument used as part of the docker run command has made ``mysql`` available for other docker containers as a DNS hostname.

![docker-dns](./images/27-network-alias.png)




## Run the app with MySQL

Here I showed the ``todo-app`` container starting and connecting to the MySQL database in the ``mysql`` container.

![docker-run](./images/28-docker-run.png)

As this is a new databases, I needed to add some tasks to the todo-app

![docker-dns](./images/29-to-do.png)

And then when I check directly in the database I can see the tasks that were just added.

![check-databases](./images/30-check-database.png)

## Summary
In this part of the workshop, I created a docker-network and started a MySQL database container. I connected the todo-app container to the database running in the MySQL container and stored data in it. I also showed a little about network discovery using DNS tools ``dig`` and ``nslookup``.

[Continue to Part 7](./Part7.md)