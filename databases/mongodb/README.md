# MongoDB Overview and Setup with Docker

## MongoDB Overview

MongoDB is a popular NoSQL database known for its flexibility and scalability. It uses a document-oriented data model, storing data in a format similar to JSON. MongoDB is widely used for its ability to handle large volumes of data and high-throughput operations.

## MongoDB Setup with Docker

### 1. Install Docker

First, ensure that you have Docker installed on your machine. Docker provides a way to run applications securely isolated in a container, packaged with all its dependencies and libraries.

### 2. Pull MongoDB Docker Image

Pull the official MongoDB Docker image from Docker Hub using the following command:

```bash
docker pull mongo
```

### 3. Run MongoDB Container

Once you have the MongoDB image, you can start a new MongoDB container with the following command:

```bash
docker run -d -p 27017:27017 --name mongodb_container mongo
```

- `-d`: Detached mode, meaning the container runs in the background.
- `-p 27017:27017`: Maps the container's port 27017 to the host machine's port 27017.
- `--name mongodb_container`: Assigns a name to the container.

### 4. Access MongoDB Shell

You can access the MongoDB shell within the running container using the following command:

```bash
docker exec -it mongodb_container mongo
```

This command allows you to interact with the MongoDB instance running inside the container.

### 5. Basic Operations in MongoDB Shell

#### Create a Database

```javascript
use mydatabase
```

#### Create a Collection

```javascript
db.myCollection.insertOne({ key: "value" })
```

#### Find Documents in a Collection

```javascript
db.myCollection.find()
```

### 6. Create Docker Compose File (Optional)

You can also use Docker Compose to define and run multi-container Docker applications. Below is an example of a `docker-compose.yml` file for running MongoDB:

```yaml
version: '3.1'

services:
  mongodb:
    image: mongo
    ports:
      - "27017:27017"
```

By using Docker and the official MongoDB image, you can easily set up and run MongoDB on your local machine without the need for manual installation and configuration.

This approach provides a convenient and reproducible way to work with MongoDB, making it easy to manage different versions and configurations using containers.