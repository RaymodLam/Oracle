# 实验一：分析SQL执行计划，执行SQL语句的优化指导
## 实验内容：
#### 1.对Oracle12c中的HR人力资源管理系统中的表进行查询与分析。
### 教材中的查询语句：
查询1：
```SQL
SELECT d.department_name，count(e.job_id)as "部门总人数"，
avg(e.salary)as "平均工资"
from hr.departments d，hr.employees e
where d.department_id = e.department_id
and d.department_name in ('IT'，'Sales')
GROUP BY department_name;
```
运行截图：
![运行截图1](E:\下载的文档\2.jpg "区块链")
