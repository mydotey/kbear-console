# Requirement Specification: Term

## 通用命名规范

只包含小写字母、数字、'_'、'-'、'.'，首字符以字母或'_'开始，不包含连续的'.'。

## 标准的Kafka、Zookeeper配置格式

形如：
bootstrap.servers: <ip:9092>[,<ip:9092>]
zookeeper.connect: <ip:2181>[,<ip:2181>]

## 节点状态

集群里1个节点的active、down状态。
