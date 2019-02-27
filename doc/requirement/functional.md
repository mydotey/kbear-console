# Functional Requirements

## Use Cases

### 创建Cluster

【名称】

创建Cluster

【场景】

- who：管理员
- where：公司内网
- when：搭建了新的kafka集群

【描述】

1. 用户提供cluster name、bootstrap.servers、zookeeper.connect元信息，可添加自定义元信息。
2. 系统创建cluster

【价值】

保存和集中管理集群元信息。

【约束和限制】

1. 集群名应只包含字母、数字和点-_，首字符必须是字母，字母全小写。不能有连续的点-_。具有唯一性。
2. bootstrap.servers、zookeeper.connect采用标准的Kafka、Zookeeper配置格式。

### 查看Cluster

【名称】

查看Cluster

【场景】

- who：公司员工
- where：公司内网
- when：任何时间

【描述】

1. 查看cluster name、bootstrap.servers、zookeeper.connect等元信息
2. 查看cluster broker状态（active、down）
3. 查看zookeeper结点状态（active、down）

【价值】

查看集群元信息、部署结点信息和监控。

【约束和限制】

1. 可以外链到集群、结点监控系统。

### 修改Cluster

修改Cluster

【场景】

- who：管理员
- where：公司内网
- when：集群部署结点变更（增加、减少结点）、自定义元数据变更

【描述】

1. 可以修改bootstrap.servers、zookeeper.connect
2. 可以增加、删除、修改自定义元信息

【价值】

修改集群元信息。

【约束和限制】

1. bootstrap.servers、zookeeper.connect采用标准的Kafka、Zookeeper配置格式。

### 创建Topic

【名称】

创建Topic

【场景】

- who：管理员
- where：公司内网
- when：需要新建Kafka Topic

【描述】

1. 用户提供topic name、Kafka topic配置元信息，可添加自定义元信息。
2. 用户选择topic部署到哪个集群。
3. 系统创建Topic。

【价值】

创建新的Topic，并部署到Kafka集群。保存和集中管理Topic元信息。

【约束和限制】

1. Topic名应只包含字母、数字和点-_，首字符必须是字母，字母全小写。不能有连续的点-_。具有唯一性。
2. Kafka topic配置元信息均有默认值，可选。
3. 可限定具有某种特征的topic只能部署到某些集群。

### 查看Topic

查看Topic

【场景】

- who：公司员工
- where：公司内网
- when：任何时间

【描述】

1. 查看topic name、Kafka topic配置元信息和自定义元信息。
2. 查看topic所部署的集群。
3. 查看topic partition分布信息。

【价值】

查看Topic元信息。

【约束和限制】

1. 对于没有配置的Kafka topic配置项，显示默认值。

### 修改Topic

修改Topic

【场景】

- who：管理员
- where：公司内网
- when：更改topic Kafka 配置，修改自定义元信息

【描述】

1. 可以修改Kafka topic配置元信息
2. 可以增加、删除、修改自定义元信息。

【价值】

创建新的Topic，并部署到Kafka集群。保存和集中管理Topic元信息。

【约束和限制】

1. Topic名应只包含字母、数字和点-_，首字符必须是字母，字母全小写。不能有连续的点-_。具有唯一性。
2. Kafka topic配置元信息均有默认值，可选。
3. 可限定具有某种特征的topic只能部署到某些集群。

### 创建Consumer Group

### 查看Consumer Group

### 修改Consumer Group

### 增加Topic分区数

### 同一个集群迁移Topic分区

### 同一个集群broker间迁移数据

### 不同集群间迁移Topic

### 创建路由

### 修改路由

### 查看路由

### Cluster信息Api

### Topic信息Api

### Consumer Group Api

### 路由Api

### 查看Cluster监控

### 查看Broker监控

### 查看Topic监控

### 查看Consumer监控
