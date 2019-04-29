![](/assets/报警机制.png)

告警能力在Prometheus的架构中被划分成两个独立的部分。如上所示，通过在Prometheus中定义AlertRule（告警规则），Prometheus会周期性的对告警规则进行计算，如果满足告警触发条件就会向Alertmanager发送告警信息。

在Prometheus中一条告警规则主要由以下几部分组成：

* 告警名称：用户需要为告警规则命名，当然对于命名而言，需要能够直接表达出该告警的主要内容

* 告警规则：告警规则实际上主要由PromQL进行定义，其实际意义是当表达式（PromQL）查询结果持续多长时间（During）后出发告警



