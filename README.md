# Persistent Data with Client


- **MongoDB + MongoExpress**
    - images:
        - mongo: https://hub.docker.com/_/mongo
        - mongo express: https://hub.docker.com/_/mongo-express

    - commands:
        >> cd mongodb

        >> docker-compose up -d

    - link: http://localhost:8081/
    - URI: mongodb://admin:password@localhost:27017/admin

- **PostgreSQL + PgAdmin**
    - images:
        - postgres: https://hub.docker.com/_/postgres
        - mongo express: https://hub.docker.com/_/mongo-express

    - commands:
        >> cd postgresql

        >> docker-compose up -d

    - link: http://localhost:8082/
    - login with credentials: `admin@admin.com | admin`
    - Get progres IP
        >> docker inspect <postgres_container_id> | grep IPAddress
    - Add server connection
        - IP: from previous step  (might be 172.24.0.2)
        - user: root
        - password: root
        - port: 27017

- **Redis + Redis Commander**
    - images:
        - redis: https://hub.docker.com/_/redis
        - mongo express: https://hub.docker.com/_/mongo-express

    - commands:
        >> cd redis

        >> docker-compose up -d

    - link: http://localhost:8083/



- **MariaDB + PHPmyadmin**
    - images:
        - mariadb: https://hub.docker.com/_/mariadb
        - phpmyadmin: https://hub.docker.com/r/phpmyadmin/phpmyadmin/

    - commands:
        >> cd redis

        >> docker-compose up -d

    - link: http://localhost:8084/

    - Get progres IP
        >> docker inspect <postgres_container_id> | grep IPAddress
    - login with credentials:
        - ip: (get on terminal from previous step)
        - user: admin
        - password: admin

