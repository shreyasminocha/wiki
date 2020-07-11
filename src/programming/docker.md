# Docker

## Deploying a container

```sh
docker pull foo/bar
docker run -p <host>:<container> -d foo/bar
```

```sh
docker run -p <host>:<container> -e x='y' -e port='9000' -d foo/bar
```

```sh
docker ps
docker logs a344d52bc2f2
docker stop a344d52bc2f2
```

## Creating a container

```sh
docker build -t foo/bar .
```

