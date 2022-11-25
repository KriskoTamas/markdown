# Docker commands cheat sheet

## Links
Docker main page: https://www.docker.com/

Docker documentation: https://docs.docker.com/

Docker images: https://hub.docker.com/search?q=&type=image

## Check docker version
```
git --version
```

## Show Docker info
```
docker info
```

## Help
```
docker --help
docker <command> --help
```

## Show containers
Show running containers
```
docker ps [...options]
```
**Options:**

`-a`, `--all`: Show all containers

`-l`, `--latest`: Show latest created container

`-n`, `--last <number>`: Show n last created containers

# Container operations

## Start container

```
docker start <container>
docker start <container> <container>
```

**`<container>`** can be:

- Container name
- Container ID
- First few characters (unique part) of container ID

When not giving a unique ID, an error will be shown:
```diff
- Error response from daemon: Multiple IDs found with provided prefix: b
```

## Stop container
```
docker stop <container>
docker stop <container> <container>
```

## Restart container
```
docker restart <container>
docker restart <container> <container>
```

## Create a container
Create a container and print out its id
```
docker create <image>
```

## Rename a container
```
docker rename <container> <newName>
```

## Remove container
```
docker rm <container>
docker rm <container> <container>
```

## Create and start a container
```
docker run <image>
```

## Run command on container
```
docker exec -it <container>
```

## Show container stats
Display a live stream of container(s) resource usage statistics
```sh
docker stats # All containers
docker stats <container> # One container
docker stats <container> <container> # More containers
```