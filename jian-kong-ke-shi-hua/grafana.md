### Grafana worldping插件 {#toc_0}

### 安装 {#toc_1}

在grafana中安装worldping

```
grafana-cli plugins install raintank-worldping-app
```

重启grafana服务

```
systemctl restart grafana-server.service
```

配置 API

当前的 API KEY是\*\*\*

```
curl -H "Authorization: Bearer {{API KEY}}=" http://{{PROMETHEUS_IP}}:3000/api/dashboards/home
```

![](/assets/api-key.png)

