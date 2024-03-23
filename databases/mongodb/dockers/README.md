To set up MongoDB using Docker Compose, you can create a `docker-compose.yml` file with the following content:

```yaml
version: '3.3'

services:
  mongodb:
    image: mongo
    restart: always
    ports:
      - "27017:27017"
    volumes:
      - ./mongdata/db
```

In this `docker-compose.yml` file:

- `image: mongo` specifies the official MongoDB image from Docker Hub.
- `restart: always` ensures that the container restarts automatically if it stops.
- `ports: - "27017:27017"` maps the container's port 27017 to the host machine's port 27017, allowing you to access MongoDB from your local machine.
- The `volumes` section ensures that the MongoDB data is persisted on the host machine in the `./mongodata` directory.

To start MongoDB using Docker Compose, navigate to the directory containing the `docker-compose.yml` file and run the following command:

```bash
docker-compose up -d
```

This command will create and start the MongoDB container according to the configuration specified in the `docker-compose.yml` file. The `-d` flag runs the containers in detached mode, allowing them to run in the background.

To stop the containers, use the following command:

```bash
docker-compose down
```

With this `docker-compose.yml` file, you can easily manage your MongoDB instance using Docker Compose, allowing for a simplified and reproducible setup for local development or testing environments.