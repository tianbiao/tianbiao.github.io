---
layout: post
title: docker实用命令
categories: [docker]
description: 列举一下实用Docker命令的场景以及相应的处理方法
keywords: Software Development
---



## 

```
docker system prune
```


```
docker images -a
docker images -f dangling=true
docker image prune

docker images -a |  grep "pattern"
docker images -a | grep "pattern" | awk '{print $3}' | xargs docker rmi

docker images -a
docker rmi $(docker images -a -q)
```

```
docker ps -a -f status=exited
docker rm $(docker ps -a -f status=exited -q)
docker ps -a -f status=exited -f status=created
docker rm $(docker ps -a -f status=exited -f status=created -q)

docker ps -a | grep "pattern" | awk '{print $1}' | xargs docker rm
```