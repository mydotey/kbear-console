# Requirement Specification: ops

目录

- [增加topic分区数](#%E5%A2%9E%E5%8A%A0topic%E5%88%86%E5%8C%BA%E6%95%B0)
- [同一个集群迁移topic分区](#%E5%90%8C%E4%B8%80%E4%B8%AA%E9%9B%86%E7%BE%A4%E8%BF%81%E7%A7%BBtopic%E5%88%86%E5%8C%BA)
- [同一个集群broker间迁移数据](#%E5%90%8C%E4%B8%80%E4%B8%AA%E9%9B%86%E7%BE%A4broker%E9%97%B4%E8%BF%81%E7%A7%BB%E6%95%B0%E6%8D%AE)
- [不同集群间迁移topic](#%E4%B8%8D%E5%90%8C%E9%9B%86%E7%BE%A4%E9%97%B4%E8%BF%81%E7%A7%BBtopic)

## 增加topic分区数

[场景]

- who：管理员
- where：公司内网
- when：topic扩容

[描述]

1. 选择topic。
2. 选择cluster。
3. 填写新的分区数
4. 选择新分区的部署节点
5. 保存分区数信息，更新topic部署。

[价值]

topic扩容。

[约束和限制]

1. 同一个topic的分区在部署结点里尽量均匀分布。

## 同一个集群迁移topic分区

[场景]

- who：管理员
- where：公司内网
- when：topic扩容

[描述]

1. 选择topic
2. 选择cluster
3. 选择要迁移的分区(s)
4. 选择要迁往的broker(s)
5. 填写迁移速度限制
6. 生成reassignment json文件
7. 执行reassignment
8. 查看reassignment状态
9. 迁移完成后，通知操作员

[价值]

topic分区迁移。

[约束和限制]

None

## 同一个集群broker间迁移数据

[场景]

- who：管理员
- where：公司内网
- when：topic扩容

[描述]

1. 选择cluster
2. 选择源broker(s)和目标broker(s)
3. 选择源broker(s)上的1个或多个topic
3-A. 如果不选择topic，认为迁移broker上的全部topic
4. 填写迁移速度限制
5. 生成reassignment json文件
6. 执行reassignment
7. 查看reassignment状态
8. 迁移完成后，通知操作员

[价值]

broker数据迁移。

[约束和限制]

None

## 不同集群间迁移topic

[场景]

- who：管理员
- where：公司内网
- when：topic切换集群

[描述]

1. 选择topic
2. 选择源cluster和新cluster
3. 部署/同步原cluster配置到新cluster
4. 更改topic路由，消息生产转向新cluster
4A. 如果不实时切换consumer到新集群，同时根据旧路由对每个consumer生成consumer 特定的路由。

[价值]

topic切换集群。

[约束和限制]

1. 允许回切到旧cluster。
