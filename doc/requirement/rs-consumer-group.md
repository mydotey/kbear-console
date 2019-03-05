# Requirement Specification: consumer group

目录

- [注册consumer group](#%E6%B3%A8%E5%86%8Cconsumer-group)
- [查看consumer group](#%E6%9F%A5%E7%9C%8Bconsumer-group)
- [修改consumer group](#%E4%BF%AE%E6%94%B9consumer-group)
- [consumer group Api](#consumer-group-api)
- [查看consumer group监控](#%E6%9F%A5%E7%9C%8Bconsumer-group%E7%9B%91%E6%8E%A7)

## 注册consumer group

[场景]

- who：管理员
- where：公司内网
- when：有新的消费者接入

[描述]

1. 用户提供consumer group name，和自定义元信息。
2. 系统保存信息

[价值]

保存和管理consumer group信息。

[约束和限制]

1. consumer group name应遵循通用命名规范，且具有唯一性。

## 查看consumer group

[场景]

- who：公司员工
- where：公司内网
- when：任何时间

[描述]

1. 查看consumer group name、自定义信息。
2. 查看消费哪些topic。
3. 查看consumer特定的路由规则。

[价值]

查看consumer group信息。

[约束和限制]

1. 可以外链到consumer group监控

## 修改consumer group

[场景]

- who：管理员
- where：公司内网
- when：修改consumer group信息

[描述]

1. 增加、删除、修改自定义信息。

[价值]

更新consumer group信息。

[约束和限制]

None

## consumer group Api

[场景]

- who：外部系统
- where：公司内网
- when： 任何时间

[描述]

1. 获取单个、某些或所有consumer group的信息。

[价值]

与外部系统对接。

[约束和限制]

1. HTTP Api，支持get和post。

## 查看consumer group监控

[场景]

- who：公司员工
- where：公司内网
- when： 任何时间

[描述]

1. 选择consumer group，消费的topic，外链到kbear-monitoring

[价值]

与kbear-monitoring对接。

[约束和限制]

None
