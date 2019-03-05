# Requirement Specification: topic

目录

- [注册topic](#%E6%B3%A8%E5%86%8Ctopic)
- [查看topic](#%E6%9F%A5%E7%9C%8Btopic)
- [修改topic](#%E4%BF%AE%E6%94%B9topic)
- [topic信息Api](#topic%E4%BF%A1%E6%81%AFapi)
- [查看topic监控](#%E6%9F%A5%E7%9C%8Btopic%E7%9B%91%E6%8E%A7)

## 注册topic

[场景]

- who：管理员
- where：公司内网
- when：需要新建Kafka topic

[描述]

1. 用户提供topic name和Kafka topic配置信息。
2. 用户提供自定义信息。
3. 用户选择要部署的cluster。
4. 用户配置消息生产是否需要申请。
5. 用户配置消息消费是否需要申请。
6. 系统保存信息。
7. 系统根据topic name和Kafka topic配置信息，在所选择集群上创建topic。

[价值]

注册新的topic，并部署到Kafka集群。保存和集中管理topic信息。

[约束和限制]

1. topic名应符合通用命名规范，且具有唯一性。
2. 系统对Kafka topic配置信息提供默认值，用户可选。
3. 可限定具有某种特征（自定义信息）的topic只能部署到某些cluster。
4. 1个topic可以部署到多个集群。
5. 消息生产、消费默认需要申请。
6. 可以对每个要部署的cluster分别设置Kafka topic配置。

## 查看topic

[场景]

- who：公司员工
- where：公司内网
- when：任何时间

[描述]

1. 查看topic name、Kafka topic配置信息和自定义信息。
2. 查看消息生产、消费权限。如果需要申请，查看已授权的client、consumer group。
3. 查看topic所部署的cluster，和cluster特定Kafka topic的配置。
4. 查看cluster上topic partition分布信息。
5. 查看topic特定的路由规则。

[价值]

查看topic信息和授权情况，部署topic到Kafka cluster。

[约束和限制]

1. 可以外链到topic监控

## 修改topic

[场景]

- who：管理员
- where：公司内网
- when：更改topic Kafka 配置，修改自定义元信息，修改权限控制

[描述]

1. 修改Kafka topic配置信息，并同步到部署的集群。
2. 增加、删除、修改自定义元信息。
3. 增加部署cluster，并在cluster上创建topic。
4. 减少部署cluster，并在cluster上删除topic。
5. 修改生产、消费权限控制。

[价值]

更新topic信息和权限控制，调整topic cluster部署。

[约束和限制]

1. 可限定具有某种特征（自定义信息）的topic只能部署到某些cluster。

## topic信息Api

[场景]

- who：外部系统
- where：公司内网
- when： 任何时间

[描述]

1. 获取单个、某些或所有topic的信息。

[价值]

与外部系统对接。

[约束和限制]

1. HTTP Api，支持get和post。

## 查看topic监控

[场景]

- who：公司员工
- where：公司内网
- when： 任何时间

[描述]

1. 选择topic和1个部署的cluster，外链跳转到kbear-monitoring

[价值]

与kbear-monitoring对接。

[约束和限制]

None
