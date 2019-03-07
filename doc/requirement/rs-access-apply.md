# Requirement Specification: access apply

目录

- [申请生产topic消息](#%E7%94%B3%E8%AF%B7%E7%94%9F%E4%BA%A7topic%E6%B6%88%E6%81%AF)

## 申请生产topic消息

[场景]

- who：公司员工
- where：公司内网
- when：需要向某个受限的topic发消息

[描述]

1. 填入client id
2. 选择topic
3. 填写申请信息
4. 通知topic owner审批。
5. topic owner审批
   1. 如果批准，建立授权关系并通知申请者。
   2. 如果不批准，不建立授权关系，并通知申请者。

[价值]

控制topic消息产生权限。

[约束和限制]

None
