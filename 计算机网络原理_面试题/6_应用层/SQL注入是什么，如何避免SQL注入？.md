SQL 注入就是在用户输入的字符串中加入 SQL 语句，如果在设计不良的程序中忽略了检查，那么这些注入进去的 SQL 语句就会被数据库服务器误认为是正常的 SQL 语句而运行，攻击者就可以执行计划外的命令或访问未被授权的数据。

SQL注入的原理主要有以下 4 点：

- 恶意拼接查询
- 利用注释执行非法命令
- 传入非法参数
- 添加额外条件

避免SQL注入的一些方法：

- 限制数据库权限，给用户提供仅仅能够满足其工作的最低权限。
- 对进入数据库的特殊字符转义处理。
- 提供参数化查询接口，不要直接使用原生SQL。