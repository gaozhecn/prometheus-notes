## 思路

提前生成自己业务的镜像上传至内部镜像仓库，prometheus服务器和被监控服务器上只需运行server/client目录下的 docker-compoer即可启动服务。

本项目拉取代码，代码中包含启动 Docker编排文件 docker-compoer.yml，其他的一些配置文件，挂载目录。
