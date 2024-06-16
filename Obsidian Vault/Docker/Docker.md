# Docker
# Introduction
+ [Registry](#registry)
+ [Account](#account)
+ [Volumes](#volumes)
+ [Images](#images)
+ [Containers](#containers)
+ [Network](#network)
+ [Dockerfile](#dockerfile)
+ [docker-compose](#docker-compose)

---
## Registry

A place where images can be stored/downloaded.

[Docker Hub](https://hub.docker.com/)
[GitHub](https://ghcr.io)

---
## Account

| Command                                     | Explanation                   |
| ------------------------------------------- | ----------------------------- |
| `docker login <registry-url> -u <username>` | Login to an external registry |
| `docker login`                              | Login to docker hub registry  |
| `docker logut`                              | Logout from current registry  |
|                                             |                               |

---
## General

| Command                                   | Explanation               |
| ----------------------------------------- | ------------------------- |
| `docker inspect <target-name/id>`         | Inspect target            |
| `docker <target> prune -a`                | Remove all unused targets |
| `docker <target> rm <target-name/id> ...` | Remove 1 or more targets  |
| `image, container, volume, network`       | Target options            |

---
## Images

Blueprint for containers. Cannot be changed without rebuilding.

| Command                                            | Explanation                            |
| -------------------------------------------------- | -------------------------------------- |
| `docker images`                                    | View local images                      |
| `docker image inspect`                             | View details about the image           |
| `docker rmi <image-name/id> ...`                   | Remove 1 or more images                |
| `docker build <Dockerfile-path>`                   | Build an image based on a Dockerfile   |
| `docker image history <image-name>`                | View the layers of selected image      |
| `docker pull <registry>/<user>/<repository>:<tag>` | Download locally a version of an image |
| `docker push <registry>/<user>/<repository>:<tag>` | Upload to a registry a local image     |
|                                                    |                                        |

---
## Containers

| Command                                      | Explanation                                                            |
| -------------------------------------------- | ---------------------------------------------------------------------- |
| `docker ps [-a]`                             | View active/\[all\] containers                                         |
| `docker rm <container-name/id> ...`          | Remove 1 or more containers                                            |
| `docker run [OPTIONS] <image-name>`          | Run a container based on an image                                      |
| `--rm`                                       | Remove a container after it finishes/gets topped                       |
| `-v </path/in/container>`                    | Create an anonymous volume                                             |
| `-v <{pwd}/local/path>:</path/in/container>` | Create a bind mount. Needs absolute path.                              |
| `-v <name>:</path/in/container>`             |                                                                        |
| `-i`                                         | Interactive. Container waits and accepts input.                        |
| `-t`                                         | Pseudo-TTY. Will be able to see container running as in terminal mode. |
| `-p <host-port>:<container-port>`            | Expose container port to the host                                      |
| `docker start <container-name/id>`           | Start an existing container                                            |
| `docker stop <container-name/id>`            | Stop a running container                                               |
|                                              |                                                                        |
| `-e` / `--env`                               |                                                                        |
| `--env-file <file-path>`                     |                                                                        |
| `-d`                                         | Detached mode. Container runs in background.                           |
| `docker attach <container-name/id>`          | Attach to a running container                                          |
|                                              |                                                                        |
|                                              |                                                                        |
|                                              |                                                                        |

---
## Volumes


| Command                                 | Explanation              |
| --------------------------------------- | ------------------------ |
| `docker volume ls`                      | List created volumes     |
| `docker volume create <name>`           | Create a volume          |


---
## Network


| Network Type | Explanation |
| ------------ | ----------- |
| `bridge`     |             |
| `host`       |             |
| `none`       |             |

| Command                                                        | Explanation                          |
| -------------------------------------------------------------- | ------------------------------------ |
| `docker network connect <network-name/id> <container-name/id>` | Connect a continer to a network      |
| `docker network create <network-name>`                         | Create a network (default as bridge) |
| `docker network remove <id> ...`                               | Remove 1 or more volumes             |


---
## Dockerfile



---
## Docker-compose



---
