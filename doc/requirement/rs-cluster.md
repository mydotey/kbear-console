# Requirement Specification: cluster

目录

- [注册cluster](#%E6%B3%A8%E5%86%8Ccluster)
- [查看cluster](#%E6%9F%A5%E7%9C%8Bcluster)
- [修改cluster](#%E4%BF%AE%E6%94%B9cluster)
- [cluster信息Api](#cluster%E4%BF%A1%E6%81%AFapi)
- [查看cluster监控](#%E6%9F%A5%E7%9C%8Bcluster%E7%9B%91%E6%8E%A7)
- [查看broker监控](#%E6%9F%A5%E7%9C%8Bbroker%E7%9B%91%E6%8E%A7)

## 注册cluster

[场景]

- who：管理员
- where：公司内网
- when：搭建了新的Kafka集群

[描述]

1. 用户提供name、bootstrap.servers、zookeeper.connect等cluster自有的信息。
2. 用户可添加自定义信息。
3. 系统保存cluster信息。

[价值]

保存和集中管理cluster信息。

[约束和限制]

1. name应符合通用命名规范，且具有唯一性。
2. bootstrap.servers、zookeeper.connect采用标准的Kafka、Zookeeper配置格式。

## 查看cluster

[场景]

- who：公司员工
- where：公司内网
- when：任何时间

[描述]

1. 查看cluster自有信息和用户自定义信息。
2. 查看Kafka节点状态。
3. 查看Zookeeper节点状态。

[价值]

查看集群信息和节点状态。

[约束和限制]

1. 可以外链到cluster、结点监控。

## 修改cluster

修改cluster

[场景]

- who：管理员
- where：公司内网
- when：cluster部署变更（节点增加、减少）、自定义信息变更

[描述]

1. 修改集群自有信息。
2. 增加、删除、修改自定义信息。

[价值]

修改集群信息。

[约束和限制]

1. name不可修改。

## cluster信息Api

[场景]

- who：外部系统
- where：公司内网
- when： 任何时间

[描述]

1. 获取单个、某些或所有cluster的信息。

[价值]

与外部系统对接。

[约束和限制]

1. HTTP Api，支持get和post。

## 查看cluster监控

[场景]

- who：公司员工
- where：公司内网
- when： 任何时间

[描述]

1. 选择cluster，外链跳转到kbear-monitoring

[价值]

与kbear-monitoring对接。

[约束和限制]

None

## 查看broker监控

[场景]

- who：公司员工
- where：公司内网
- when： 任何时间

[描述]

1. 选择broker，外链到kbear-monitoring

[价值]

与kbear-monitoring对接。

[约束和限制]

None
