# Part 7 - Use Docker Compose

From: https://docs.docker.com/get-started/workshop/08_using_compose/

## Create the Compose file

```bash
touch compose.yaml
```

## Define the app service
```yaml
services:
  app:
    image: node:24-alpine
    command: sh -c "npm install && npm run dev"
    ports:
      - 127.0.0.1:3000:3000
    working_dir: /app
    volumes:
      - ./:/app
    environment:
      MYSQL_HOST: mysql
      MYSQL_USER: root
      MYSQL_PASSWORD: secret
      MYSQL_DB: todos
```

## Define the MySQL service
```yaml
  mysql:
    image: mysql:8.0
    volumes:
      - todo-mysql-data:/var/lib/mysql
    environment:
      MYSQL_ROOT_PASSWORD: secret
      MYSQL_DATABASE: todos
```
## Define the volume

```yaml
volumes:
  todo-mysql-data:

```

## Run the application stack

![docker compose up](./images/31-docker-compose-up.png)

![todo app](./images/32-to-do.png)

## Summary

A ``compose.yaml`` file was created and used with ``docker compose`` to define, configure and run two containers together as a single application stack.


**End of Exercise**