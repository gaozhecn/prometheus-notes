# Docker 监控 {#toc_0}

## docker stats {#toc_1}

* ### 缺点 {#toc_2}

  * 无法通过远程 HTTP 进行访问获取数据；

  * 没有界面，数据可是需要做大量的工作；

## cadvisor {#toc_3}

### 特点 {#toc_4}

* 可以搜集一台机器上所有运行的容器信息；

* 提供基础查询界面；

* http 接口 ；

* 方便 Prometheus 进行数据抓取；

* 正是因为 cadvisor 与 Prometheus 的完美结合，所以它成为了容器监控的第一选择。

### 安装 {#toc_5}

step1：docker pull镜像

```
$ docker pull google/cadvisor:latest
```

step2: 查看镜像

```
REPOSITORY TAG IMAGE ID CREATED SIZE google/cadvisor latest eb1210707573 4 months ago 69.6MB
```

step3:加载镜像到容器运行

```
sudo docker run --volume=/:/rootfs:ro --volume=/var/run:/var/run:rw --volume=/sys:/sys:ro --volume=/var/lib/docker/:/var/lib/docker:ro --volume=/dev/disk/:/dev/disk:ro --publish=8080:8080 --detach=true --name=cadvisor google/cadvisor:latest
```



Step4: 访问



