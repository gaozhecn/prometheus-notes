## 使用命令安装 {#toc_0}

```
docker run -d -p 9090:9090 -v /home/prometheus_test/prometheus.yml:/etc/prometheus/prometheus.yml -v /home/prometheus_test/prometheus-data:/prometheus-data prom/prometheus
```

## 使用 Dockfile 安装 {#toc_1}

### Dockfile 如下 {#toc_2}

```
FROM prom/prometheus
USER root
ADD ./fy-prometheus.yml /etc/prometheus/prometheus.yml
RUN chmod -R 777 /etc/prometheus/prometheus.yml
EXPOSE 9090
```

```
命令
```



```
docker build -t i_prometheus_server . docker images | grep i_prometheus_server docker run -d -it -P --name prometheus_server_container i_prometheus_server
```

### prometheus配置文件 {#toc_4}

```
global:
  scrape_interval:        15s
  evaluation_interval:    15s
  scrape_timeout:         10s
scrape_configs:
  - job_name: 'node_test'
    static_configs:
      - targets: ['58.87.93.139:9100']
  - job_name: 'test_containers'
    static_configs:
      - targets: ['58.87.93.139:8080']
```



