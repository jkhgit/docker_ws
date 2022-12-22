# docker_ws
Docker image scripts for various package tests workspace.

### env
- docker (>= 20.10)
- ubuntu (>= 20.04 LTS)

### tree
```
docker_ws/
  |
  --- imageA/
  |     |
  |     --- Dockerfile
  |     --- ...
  |
  --- imageX/
  |     |
  |     --- ...

  ...

  |
  --- example/
        |
        --- Dockerfile.rst
        --- docker.preinst
        --- docker.user
```

- build: docker build -t "<custom-image:tag>" "<dir_name>"
```
# e.g
$ docker build -t ubuntu:test imageA
```

- imageX: docker project.
```
# You can write a Docker Build Script project yourself,
# but you can use it as a symbolic link from the outside.
```

- example: docker project example.
- volumes: need root privilege. soft link "/var/lib/docker/volumes"

### connect
- E-mail: <jkhpro1003@gmail.com>
