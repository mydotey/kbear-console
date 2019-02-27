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
2. 用户选择topic部署到哪个或哪些集群。
3. 用户配置消息生产是否需要申请。
4. 用户配置消息消费是否需要申请。
5. 系统保存元信息，并创建Topic。

【价值】

创建新的Topic，并部署到Kafka集群。保存和集中管理Topic元信息。

【约束和限制】

1. Topic名应只包含字母、数字和点-_，首字符必须是字母，字母全小写。不能有连续的点-_。具有唯一性。
2. Kafka topic配置元信息均有默认值，可选。
3. 可限定具有某种特征的topic只能部署到某些集群。
4. 1个Topic可以部署到多个集群。
5. 默认消息生产需要申请，消息消费需要申请。
6. 如果在多个Cluster上有部署，应支持每个cluster分别设置Kafka Topic配置。

### 查看Topic

查看Topic

【场景】

- who：公司员工
- where：公司内网
- when：任何时间

【描述】

1. 查看topic name、Kafka topic配置元信息和自定义元信息。
2. 查看消息生产、消费权限，如果需要申请，查看授权状态。
3. 查看topic所部署的集群。
4. 查看topic partition分布信息。

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

1. 可以修改Kafka topic配置元信息，并同步到部署的集群。
2. 可以增加、删除、修改自定义元信息。
3. 可以增加部署集群。
4. 可以修改生产消费是否需要申请。

【价值】

创建新的Topic，并部署到Kafka集群。保存和集中管理Topic元信息。

【约束和限制】

1. Topic名应只包含字母、数字和点-_，首字符必须是字母，字母全小写。不能有连续的点-_。具有唯一性。
2. Kafka topic配置元信息均有默认值，可选。
3. 可限定具有某种特征的topic只能部署到某些集群。

### 创建Consumer Group

【名称】

创建Consumer Group

【场景】

- who：管理员
- where：公司内网
- when：有新的消费者接入

【描述】

1. 用户提供consumer group name，可添加自定义元信息。
2. 系统保存元信息

【价值】

创建新的Consumer Group，保存Consumer Group元信息。

【约束和限制】

1. Consumer Group Name名应只包含字母、数字和点-_，首字符必须是字母，字母全小写。不能有连续的点-_。具有唯一性。

### 查看Consumer Group

【名称】

查看Consumer Group

【场景】

- who：公司员工
- where：公司内网
- when：任何时间

【描述】

1. 查看Consumer Group Name、自定义元信息。
2. 查看消费哪些Topic。

【价值】

查看Consumer Group元信息和消费哪些Topic。

【约束和限制】

None

### 修改Consumer Group

【名称】

修改Consumer Group

【场景】

- who：管理员
- where：公司内网
- when：修改Consumer Group元信息

【描述】

1. 可以增加、删除、修改自定义元信息。

【价值】

更新Consumer Group元信息。

【约束和限制】

None

### 申请生产Topic消息

【名称】

申请生产Topic信息

【场景】

- who：公司员工
- where：公司内网
- when：需要向某个Topic发消息

【描述】

1. 填入生产者ID
2. 选择Topic
3. 保存生产者ID和Topic对应关系。
4. 通知管理员审批。
5. 管理员同意或拒绝申请。

【价值】

Topic消息产生受控。

【约束和限制】

1. 1个生产者可以生产多个Topic的消息。

### 申请消费Topic消息

【名称】

申请消费Topic信息

【场景】

- who：公司员工
- where：公司内网
- when：需要向某个Topic发消息

【描述】

1. 选择Consumer Group
2. 选择Topic
3. 保存Consumer Group和Topic对应关系。
4. 通知管理员审批。
5. 管理员同意或拒绝申请。

【价值】

Consumer Group消息消费受控。

【约束和限制】

1. 1个Consumer Group可以消费多个Topic的消息。

### 增加Topic分区数

【名称】

增加Topic分区数

【场景】

- who：管理员
- where：公司内网
- when：Topic扩容

【描述】

1. 选择Topic
2. 填写新的分区数
3. 选择新分区的部署节点
4. 保存分区数信息，更新Topic部署。

【价值】

Topic扩容。

【约束和限制】

1. 同一个Topic的分区在集群里尽量均匀分布。
2. 如果在多个Cluster上有部署，应支持每个cluster分别设置分区数和扩容结点。

### 同一个集群迁移Topic分区

【名称】

同一个集群迁移Topic分区

【场景】

- who：管理员
- where：公司内网
- when：Topic扩容

【描述】

1. 选择Topic
2. 选择Cluster
3. 选择要迁移的分区
4. 选择新分区所在的broker
5. 生成reassignment json文件
6. 执行reassignment
7. 查看reassignment状态

【价值】

Topic分区迁移。

【约束和限制】

1. 可只迁移1个分区或同时迁移多个分区
2. 迁移速度限制有默认值，可选

### 同一个集群broker间迁移数据

【名称】

同一个集群broker间迁移数据

【场景】

- who：管理员
- where：公司内网
- when：Topic扩容

【描述】

1. 选择Cluster
2. 选择源broker(s)和目标broker(s)
3. 选择源broker(s)上的1个或多个Topic
3-A. 如果不选择Topic，认为迁移broker上的全部Topic
4. 生成reassignment json文件
5. 执行reassignment
6. 查看reassignment状态

【价值】

broker数据迁移。

【约束和限制】

1. 迁移速度限制有默认值，可选

### 不同集群间迁移Topic

【名称】

不同集群间迁移Topic

【场景】

- who：管理员
- where：公司内网
- when：Topic切换集群

【描述】

1. 选择Topic
2. 选择源Cluster和新Cluster
3. 部署/同步原Cluster配置到新Cluster
4. 生成新路由
   1. 如果原Cluster有Topic特定的路由，给新路由设置较高优先级
5. 启用新路由
   1. 如果原Cluster有Topic特定的路由，新路由启用后，删除旧路由

【价值】

Topic切换集群。

【约束和限制】

None

### 创建路由

【名称】

创建路由

【场景】

- who：管理员
- where：公司内网
- when： 新建Topic时，Topic集群切换时，Topic同时启用多个集群时

【描述】

1. 输入路由规则
2. 自动校验
   1. 如果校验失败，提示失败原因，阻止创建
3. 设置路由名称和优先级
4. 创建路由规则

【价值】

多集群路由管控。

【约束和限制】

1. 路由规则名应只包含字母、数字和点-_，首字符必须是字母，字母全小写。不能有连续的点-_。具有唯一性。

### 修改路由

【名称】

创建路由

【场景】

- who：管理员
- where：公司内网
- when： 路由规则设置出错时

【描述】

1. 更改路由规则，或优先级
2. 自动校验
   1. 如果校验失败，提示失败原因，阻止修改
3. 保存

【价值】

纠正路由规则错误，或调整路由规则优先级。

【约束和限制】

None

### 查看路由

【名称】

查看路由

【场景】

- who：公司员工
- where：公司内网
- when： 任何时间

【描述】

1. 选择路由规则
2. 查看路由规则内容，优先级，和受影响的Topic、Consumer Group

【价值】

查看路由规则。

【约束和限制】

1. 和Topic、Consumer Group之间有交叉链接。

### Cluster信息Api

【名称】

Cluster信息Api

【场景】

- who：kbear-meta
- where：公司内网
- when： 任何时间

【描述】

1. 获取单个、某些或所有Cluster的元信息。

【价值】

与kbear-meta对接。

【约束和限制】

1. HTTP Api，支持get和post。

### Topic信息Api

【名称】

Topic信息Api

【场景】

- who：kbear-meta
- where：公司内网
- when： 任何时间

【描述】

1. 获取单个、某些或所有Topic的元信息。

【价值】

与kbear-meta对接。

【约束和限制】

1. HTTP Api，支持get和post。

### Consumer Group Api

【名称】

Consumer Group信息Api

【场景】

- who：kbear-meta
- where：公司内网
- when： 任何时间

【描述】

1. 获取单个、某些或所有Consumer Group的元信息。

【价值】

与kbear-meta对接。

【约束和限制】

1. HTTP Api，支持get和post。

### 路由信息Api

【名称】

路由信息Api

【场景】

- who：kbear-meta
- where：公司内网
- when： 任何时间

【描述】

1. 获取单个、某些或所有Consumer Group的元信息。

【价值】

与kbear-meta对接。

【约束和限制】

1. HTTP Api，支持get和post。

### 查看Cluster监控

【名称】

查看Cluster监控

【场景】

- who：公司员工
- where：公司内网
- when： 任何时间

【描述】

1. 选择Cluster，外链到kbear-monitoring

【价值】

与kbear-monitoring对接。

【约束和限制】

None

### 查看Broker监控

【名称】

查看Broker监控

【场景】

- who：公司员工
- where：公司内网
- when： 任何时间

【描述】

1. 选择Broker，外链到kbear-monitoring

【价值】

与kbear-monitoring对接。

【约束和限制】

None

### 查看Topic监控

【名称】

查看Topic监控

【场景】

- who：公司员工
- where：公司内网
- when： 任何时间

【描述】

1. 选择Topic，外链到kbear-monitoring

【价值】

与kbear-monitoring对接。

【约束和限制】

None

### 查看Consumer Group监控

【名称】

查看Consumer Group监控

【场景】

- who：公司员工
- where：公司内网
- when： 任何时间

【描述】

1. 选择Consumer Group，外链到kbear-monitoring

【价值】

与kbear-monitoring对接。

【约束和限制】

None
