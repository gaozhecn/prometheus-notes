## Prometheus的优势

Prometheus是一个开源的完整监控解决方案，其对传统监控系统的测试和告警模型进行了彻底的颠覆，形成了基于中央化的规则计算、统一分析和告警的新模型。 相比于传统监控系统Prometheus具有以下优点



#### 强大的数据模型

所有采集的监控数据均以指标\(metric\)的形式保存在内置的时间序列数据库当中\(TSDB\)。所有的样本除了基本的指标名称以外，还包含一组用于描述该样本特征的标签。

如下所示：

```
http_request_status{code='200',content_path='/api/path', environment='produment'} => [value1@timestamp1,value2@timestamp2...]
http_request_status{code='200',content_path='/api/path2', environment='produment'} => [value1@timestamp1,value2@timestamp2...]
```

每一条时间序列由指标名称\(Metrics Name\)以及一组标签\(Labels\)唯一标识。每条时间序列按照时间的先后顺序存储一系列的样本值。

表示维度的标签可能来源于你的监控对象的状态，比如code=404或者content\_path=/api/path。也可能来源于的你的环境定义，比如environment=produment。基于这些Labels我们可以方便地对监控数据进行聚合，过滤，裁剪。

