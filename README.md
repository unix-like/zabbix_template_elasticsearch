# zabbix_template_elasticsearch

| item                  | trigger                      |
| :-------------------: | :--------------------------: |
| active primary shards |                              |
| active shards         |                              |
| Cluster Status        | ES cluster status is yellow/red |
| number of data nodes  |                              |
| number of nodes       |                              |
| relocating shards     |                              |
| unassigned shards     |

对ES集群健康状态进行监控，监控数据的采集也实现并行收集，此监控项目共包含2个文件:

1. userparameter_elasticsearch.conf
2. elasticsearch.xml

利用从elasticsearch api接口获取的集群健康状态信息来构建监控指标，其中`userparameter_elasticsearch.conf`需要分发到每个 ES 节点上，`elasticsearch.xml`作为模版文件导入zabbix中。

在主机应用模板之后需要修改两个“宏”的值:

1. {$ES_PORT}
2. {$ES_SERVER}

为对应的ES监听端口和地址。
