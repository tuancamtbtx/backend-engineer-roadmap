# MySQL Overview and Setup with Docker

## MySQL Overview

MySQL is one of the most popular open-source relational database management systems. It is known for its reliability, ease of use, and wide adoption. MySQL uses a traditional relational database model with support for SQL queries and ACID (Atomicity, Consistency, Isolation, Durability) compliance.

## MySQL Setup with Docker

### 1. Install Docker

Ensure that Docker is installed on your machine. Docker provides a way to run applications securely isolated in a container, packaged with all its dependencies and libraries.

### 2. Pull MySQL Docker Image

Pull the official MySQL Docker image from Docker Hub using the following command:

```bash
docker pull mysql
```

### 3. Run MySQL Container

Start a new MySQL container with the following command:

```bash
docker run -d -p 3306:3306 --name mysql_container -e MYSQL_ROOT_PASSWORD=your_password mysql
```

- `-d`: Detached mode, meaning the container runs in the background.
- `-p 3306:3306`: Maps the container's port 3306 to the host machine's port 3306.
- `--name mysql_container`: Assigns a name to the container.
- `-e MYSQL_ROOT_PASSWORD=your_password`: Sets the root password for the MySQL instance.

### 4. Access MySQL Shell

You can access the MySQL shell within the running container using the following command:

```bash
docker exec -it mysql_container mysql -uroot -p
```

This command allows you to interact with the MySQL instance running inside the container.

### 5. Basic Operations in MySQL Shell

#### Create a Database

```sql
CREATE DATABASE mydatabase;
```

#### Create a Table

```sql
USE mydatabase;
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    email VARCHAR(100) NOT NULL
);
```

#### Insert Data into a Table

```sql
INSERT INTO users (username, email) VALUES ('john_doe', 'john@example.com');
```

### 6. Create Docker Compose File (Optional)

You