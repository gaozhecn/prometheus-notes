## 思路

提前生成自己业务的镜像上传至内部镜像仓库，prometheus服务器和被监控服务器上只需运行server/client目录下的 docker-compoer即可启动服务。

## 步骤

```bash
# 拉取git代码
################# 被监控主机如下 #################
$ cd client
$ docker-compose -f docker-compose-prod.yml up -d
# docker ps查看运行起来的容器，确认包含cadvisor和node_exporter
$ docker ps
# 打开浏览器访问 {{IP}}:9100和{{IP}}:8082查看是否访问正常

################# prometheus服务器如下 #################
$ cd server
$ docker-compose -f docker-compose-prod.yml up -d
# docker ps查看运行起来的容器，确认包含prometheus、blackbox_exporter、alertmanager、grafana、alert_web_hook
$ docker ps
# 打开浏览器访问 {{IP}}:9090、{{IP}}:9115、{{IP}}:9093、、{{IP}}:3000、{{IP}}:5000查看是否访问正常
```

## 注意

在客户端部署完 exporter 之后，需要在 prometheus的服务器的配置文件prometheus.yml 文件中添加新的监控点。

本项目拉取代码，代码中包含启动 Docker编排文件 docker-compoer.yml，其他的一些配置文件，挂载目录。

