# Simple MariaDB Docker Container

## Usage

### Build

```
∴ docker build --rm -t="mysql-local" .
```

### Remove Container (if exists)

```
∴ docker rm -f mysql-local
```

### Run
```
∴ docker run --name mysql-local -d -p 3306:3306 mysql-local
```

### Connect

```
docker exec -ti mysql-local /bin/bash
```

## Configuration

Use setup.sql file to define SQL commands needed to initialize database instance.

