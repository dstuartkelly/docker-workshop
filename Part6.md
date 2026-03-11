# Part 6 Multi Container Apps

From: https://docs.docker.com/get-started/workshop/07_multi_container/

## Start MySQL

Before starting the MySQL container, we are going to create a network for our todo-app
```bash
docker network create todo-app
```
![create network](./images/24-create-network.png)

We then run mysql:8.0 container and connect it to the newly created network. We also create a new docker volume called todo-mysql-data to persist the /var/lib/mysql data from the container.

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

We can test the database is up and running by opening an interactive terminal into the container using ``docker exec -it`` 

![testing sql](./images/26-connect-mysql.png)

Using (netshoot docker network troubleshooting container)[https://hub.docker.com/r/nicolaka/netshoot] we can see the ``--network alias mysql`` used as part of our docker run command is available for other docker containers to use as a DNS hostname.

![docker-dns](./images/27-network-alias.png)




## Run the app with MySQL

Here we show the ``todo-app`` container starting and connecting to the MySQL database in the ``mysql`` container.

![docker-run](./images/28-docker-run.png)

As this is a new databases, we add some tasks to the todo-app

![docker-dns](./images/29-to-do.png)

And then we check directly in the database where we can see the tasks that were just added.

![check-databases](./images/30-check-database.png)

## Summary
In this part of the workshop, we created a docker-network and started a MySQL database container. We connected the todo-app container to the database running in the MySQL container and stored data in it. We also showed a little about network discovery using DNS tools ``dig`` and ``nslookup``.

[Continue to Part 7](./Part7.md)