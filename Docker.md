# Docker

## Remote Docker

If you don't already have an SSH key, you'll need to generate one:

```
ssh-keygen -t rsa
```

And then copy it to the remote machine:

```
ssh-copy-id ubuntu@raspberry
```

Setup DOCKET_HOST

```
export DOCKER_HOST=ssh://ubuntu@raspberry
```

## Basic

### Restarting the server (Ubuntu)

```
$ sudo systemctl stop docker
$ sudo systemctl start docker
```

```
$ sudo systemctl restart docker
```


### Images

* Baixar uma imagem para o registry local
```
$ docker pull tgolson/rpi-haskell
```

