To set up PostgreSQL using Docker Compose, you can create a `docker-compose.yml` file with the following content:

```yaml
version: '3.3'

services:
  postgres:
    image: postgres
    restart: always
    ports:
      - "5432:5432"
    environment:
      POSTGRES_DB: your_database_name
      POSTGRES_USER: your_username
      POSTGRES_PASSWORD: your_password
    volumes:
      - ./pgvar/lib/postgresql/data
```

In this `docker-compose.yml` file:

- `image: postgres` specifies the official PostgreSQL image from Docker Hub.
- `restart: always` ensures that the container restarts automatically if it stops.
- `ports: - "5432:5432"` maps the container's port 5432 to the host machine's port 5432, allowing you to access PostgreSQL from your local machine.
- The `environment` section sets up environment variables for PostgreSQL, including the database name, username, and user password.
- The `volumes` section ensures that the PostgreSQL data is persisted on the host machine in the `./pgdata` directory.

To start PostgreSQL using Docker Compose, navigate to the directory containing the `docker-compose.yml` file and run the following command:

```bash
docker-compose up -d
```

This command will create and start the PostgreSQL container according to the configuration specified in the `docker-compose.yml` file. The `-d` flag runs the containers in detached mode, allowing them to run in the background.

To stop the containers, use the following command:

```bash
docker-compose down
```

With this `docker-compose.yml` file, you can easily manage your PostgreSQL instance using Docker Compose, allowing for a simplified and reproducible setup for local development or testing environments.