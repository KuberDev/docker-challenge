# Docker Challenge





## Question 1 - Database Containers Commands

- **MongoDB** [Docker Hub](https://hub.docker.com/_/mongo)
	- Create Volume

    	`docker volume create mongo_data`
	- Create Container

    	`docker container run -d -v mongo_data:/data/db -p 27017:27017 --name mongoDB -e MONGO_INITDB_ROOT_USERNAME=user -e MONGO_INITDB_ROOT_PASSWORD=password mongo:4.4.3`


- **MariaDB** [Docker Hub](https://hub.docker.com/_/mariadb)
	- Create Volume

    	`docker volume create maria_data`
	- Create Container

        `docker container run -d -v maria_data::/var/lib/mysql -p 3306:3306 -e MYSQL_USER=user -e MYSQL_PASSWORD=password mariadb:10.6.4-focal`

- **PostgreSQL** [Docker Hub](https://hub.docker.com/_/postgres)
	- Create Volume

        `docker volume create postgres_data`
	- Create Container

        `docker container run -d -v postgres_data:/var/lib/postgresql/data -p 5432:5432 -e POSTGRES_USER=user -e POSTGRES_PASSWORD=password postgres:14.0`


- **Redis** [Docker Hub](https://hub.docker.com/_/redis)
	- Create Volume

        `docker volume create redis_data`
	- Create Container

        `docker container run -d -v redis_data:/data -p 6379:6379 -e redis:6.2.6`


<br>
<br>
<br>

## Question 2 - Data base w/ Persistent data & Client
- **MongoDB + MongoExpress**

    - mongo express [Docker Hub](https://hub.docker.com/_/mongo-express)

    - commands: `cd mongodb && docker-compose up -d`

    - link: http://localhost:8081/
    - URI: mongodb://admin:password@localhost:27017/admin


<br>

- **MariaDB + PHPmyadmin**
    - phpmyadmin [Docker Hub](https://hub.docker.com/r/phpmyadmin/phpmyadmin/)

    - commands:
        `cd redis docker-compose up -d`

    - link: http://localhost:8082/

    - Get database IP: `docker inspect <postgres_container_id> | grep IPAddress`
    - login with credentials:
        - ip: (get on terminal from previous step)
        - user: admin
        - password: admin


<br>

- **PostgreSQL + PgAdmin**
    - - mongo express [Docker Hub](https://hub.docker.com/_/mongo-express)

    - commands: `cd postgresql docker-compose up -d`

    - link: http://localhost:8083/
    - login with credentials: `admin@admin.com | admin`
    - Get database IP: `docker inspect <postgres_container_id> | grep IPAddress`
    - To add server connection
        - IP: from previous step  (might be 172.24.0.2)
        - user: root
        - password: root
        - port: 27017


<br>

- **Redis + Redis Commander**
    - mongo express: [Docker Hub](https://hub.docker.com/_/mongo-express)

    - commands:`cd redis docker-compose up -d`

    - link: http://localhost:8084/



## Question 3

- NodeJS Application: https://github.com/KuberDev/conversao-temperatura
- Flask Application: https://github.com/KuberDev/conversao-distancia
- ASP.NET Core Application: https://github.com/KuberDev/conversao-distancia

## Question 4
- Flask + Mongo + env: https://github.com/KuberDev/rotten-potatoes

## Question 5
https://github.com/KuberDev/dockerized-wordpress


## Question 6
1 - Get Repositories & run `docker-compose up -d`
 - https://github.com/KuberDev/review
 - https://github.com/KuberDev/movie

2 - Get Repository, run `docker-compose up -d` & visit `http://localhost/` in your browser
 - https://github.com/KuberDev/rotten-potatoes-ms





## Developer Notes (Question 7)

### Useful Docker commands:

- Add tag:

    `docker tag <nunojacinto/api-produto:v1> <nunojacinto/api-produto:latest>`

- Create image form Dockerfile:

    `docker image build -t <image_name> <path_of_dockerFile>`

- Create container from existing image:

    `docker container run -d -p 8080:80 <image_id_or_name>`

- Inspect container:

    `docker inspect <container-id>`

- Execute container in interactive mode:

    `` TODO:

- See container logs:

    `docker inspect <container-id>`

- Run a Docker compose:

    `docker-compose up -d`

- Shutdown Docker compose:

    `docker-compose down`   (Add `—volumes` flag to clean everything)



### Docker good practices to keep in mind
- Docker image name
- Use preferencial oficial images
- Tag a specific version in your image (avoid the use of latest)
- Use .env to configure your docker-compose
- If you want persistent data use volumes
- Use docker layers in your advantage, to improve image performance (for example: do a “build image” and a “deploy image”)
- Use .dockerignore
