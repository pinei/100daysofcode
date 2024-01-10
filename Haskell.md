# Haskell

## First steps

1. Installing on Ubuntu

```
$ sudo apt install haskell-stack
$ sudo stack upgrade
$ stack ghci
ctrl+Z
```

2. Create a new project with `stack`

```
$ stack new haskell-for-good
$ cd haskell-for-good
$ stack build
$ stack test
```

3. Code and test

- [Haskell Project - Todo](https://commentedcode.org/blog/2016/07/30/haskell-project-stack-and-data-types/)


## Next steps

1. Use docker to init an environment

## Container for Raspberry Pi

### Try 1

Mapeando a pasta do projeto com o container da imagem `tgolson/rpi-haskell`

| Raspberry Pi                       | Container
| ˜/projects/github/haskell-for-good | /projects/haskell-for-good

```
$ docker pull tgolson/rpi-haskell
$ 
```

Atualizando o stack

```
$ stack updgrade
$ stack --version
Version 1.1.2 arm hpack-0.14.1
$ ghci
GHCi, version 8.0.1 ...
```

### Try 2

```
$ docker run -it balenalib/rpi-raspbian:bullseye bash
```

+ Install haskell-stack
+ Install gch

```
$ apt-get install haskell-stack
$ stack --version
2.3.3 arm
```

[bullseye -> haskell-stack (2.3.3-1)](https://packages.debian.org/bullseye/haskell-stack)

```
$ apt-get install ghc
$ ghc --version
The Glorious Glasgow Haskell Compilation System, version 8.8.4
```

[bullseye -> ghc (8.8.4-2)](https://packages.debian.org/bullseye/ghc)

+ Find the resolver for GCH 8.8.4
  + [LTS Haskell 16.31 (ghc-8.8.4) published on 2021-01-17](https://www.stackage.org/lts-16.31)


+ Setup `~/.stack/global-project/stack.yaml`

```
# This is the implicit global project's config file, which is only used when
# 'stack' is run outside of a real project.  Settings here do _not_ act as
# defaults for all projects.  To change stack's default settings, edit
# '/root/.stack/config.yaml' instead.
#
# For more information about stack's configuration, see
# http://docs.haskellstack.org/en/stable/yaml_configuration/
#
resolver: lts-16.31
packages: []
```

+ Setup `~/.stack/config.yaml`

```
system-ghc: true
skip-ghc-check: true
```

```
$ stack setup --system-ghc
stack will use the GHC on your PATH
For more information on paths, see 'stack path' and 'stack exec env'
To use this GHC and packages outside of a project, consider using:
stack ghc, stack ghci, stack runghc, or stack exec
```

+ Create a new project

```
$ stack new haskell-for-good --resolver=lts-16.31
```

+ Build, test, install

```
# stack build --system-ghc
# stack test --system-ghc
# stack install --system-ghc 
```

### Next steps


Build an image `pinei/haskell-pi`

Reference:
https://github.com/TGOlson/rpi-haskell/blob/master/Dockerfile

- Buscar imagens baseadas em ARM
  https://hub.docker.com/search?q=haskell&type=image&architecture=arm%2Carm64
- Usar o 'docker history' para entender como foram feitas
