To set up MySQL using Docker Compose, you can create a `docker-compose.yml` file with the following content:

```yaml
version: '3.3'

services:
  mysql:
    image: mysql
    restart: always
    ports:
      - "3306:3306"
    environment:
      MYSQL_ROOT_PASSWORD: your_password
      MYSQL_DATABASE: your_database_name
      MYSQL_USER: your_username
      MYSQL_PASSWORD: your_password
    volumes:
      - ./mysqlvar/lib/mysql
```

In this `docker-compose.yml` file:

- `image: mysql` specifies the official MySQL image from Docker Hub.
- `restart: always` ensures that the container restarts automatically if it stops.
- `ports: - "3306:3306"` maps the container's port 3306 to the host machine's port 3306, allowing you to access MySQL from your local machine.
- The `environment` section sets up environment variables for MySQL, including the root password, database name, username, and user password.
- The `volumes` section ensures that the MySQL data is persisted on the host machine in the `./mysql_data` directory.

To start MySQL using Docker Compose, navigate to the directory containing the `docker-compose.yml` file and run the following command:

```bash
docker-compose up -d
```

This command will create and start the MySQL container according to the configuration specified in the `docker-compose.yml` file. The `-d` flag runs the containers in detached mode, allowing them to run in the background.

To stop the containers, use the following command:

```bash
docker-compose down
```

With this `docker-compose.yml` file, you can easily manage your MySQL instance using Docker Compose, allowing for a simplified and reproducible setup for local development or testing environments.