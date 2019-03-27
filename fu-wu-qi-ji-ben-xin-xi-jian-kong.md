```
docker run -d -p 9100:9100   -v "/proc:/host/proc:ro"   -v "/sys:/host/sys:ro"   -v "/:/rootfs:ro"   --net="host"   quay.io/prometheus/node-exporter     --path.procfs /host/proc     --path.sysfs /host/sys     --collector.filesystem.ignored-mount-points "^/(sys|proc|dev|host|etc)($|/)"
```

docker run --name prometheus-test-test -v "/root/prometheus/fy-prometheus.yml:/etc/prometheus/prometheus.yml"  -d -p 0.0.0.0:9090:9090 quay.io/prometheus/prometheus

# 可视化界面grafana

```
docker run -d -p 3000:3000 grafana/grafan
```



