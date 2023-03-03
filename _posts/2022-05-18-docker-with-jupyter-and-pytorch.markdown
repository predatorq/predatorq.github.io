---
layout: post
title:  "docker基础指令及搭建一个含tensorflow、pytorch及jupyter的docker平台"
date:   2022-05-18 13:22:16 +0800
categories: docker pytorch jupyter
---

## 安装（仅测试ubuntu）

国内代码：

```shell
curl -fsSL https://get.docker.com | bash -s docker --mirror Aliyun
```

## 容器使用

### help
```shell
--help
```

### 获取镜像
```shell
docker pull XXX
```

### 查看所有的容器
```shell
docker ps -a
```

### 后台运行
```shell
docker run -d --name XXX XXXX /bin/bash
```

第一个XXX指名字，第二个为镜像名字

镜像没有会自动下载

自用指令

```shell
docker run --runtime=nvidia --name new -dt -p 10000:8888 -v /home/me/Documents:/usr/Downloads tensorflow/tensorflow:2.3.3-gpu-jupyter
```

适用cuda版本为10.2

另外，最好使用`--shm-size`修改shared memory，不然经常会不够

### 进入docker
```shell
docker exec -it XXX /bin/bash
```

使用exec，从容器退出，容器不会停止

### 导出容器
```shell
docker export > output.tar
```

导入同理为inport

### 删除容器
```shell
docker rm -f
```

## 个人碰到的问题
### 问题1

描述：

```shell
ERROR: Unexpected bus error encountered in worker. This might be caused by insufficient shared memory (shm)
```

解决方案：

- PyTorch的IPC会利用共享内存，所以共享内存必须足够大，可以通过`docker run --shm-size`进行修改
- 通过设置 `--ipc=host`
- 将Dataloader的num_workers设置为0。但训练会变慢
- 参照[这个链接](https://blog.csdn.net/Felaim/article/details/109318772)修改