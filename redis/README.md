# Simple Redis Docker Container

### Build

```
∴ docker build --rm -t="redis-local" .
```

### Remove Container (if exists)

```
∴ docker rm redis-local
```

### Run
```
∴ docker run --name redis-local -d -p 6379:6379 redis-local
```

### Connect

```
docker exec -ti redis-local /bin/bash
```
