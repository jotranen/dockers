# Simple MariaDB Docker Container

### Build

```
∴ docker build --rm -t="mysql-local" .
```

### Remove Container (if exists)

```
∴ docker rm mysql-local
```

### Run
```
∴ docker run --name mysql-local -d -p 3306:3306 mysql-local
```

### Connect

```
docker exec -ti mysql-local /bin/bash
```
