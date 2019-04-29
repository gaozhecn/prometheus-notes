![](/assets/报警机制.png)

告警能力在Prometheus的架构中被划分成两个独立的部分。如上所示，通过在Prometheus中定义AlertRule（告警规则），Prometheus会周期性的对告警规则进行计算，如果满足告警触发条件就会向Alertmanager发送告警信息。

