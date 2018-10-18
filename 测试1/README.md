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
运行截图1：
![](https://github.com/RaymodLam/Oracle/blob/master/test1/4.png?raw=true)

实验分析1：通过代码的运行，可以看出这段代码的运行时间为0.003秒，相对于查询二的运行时间更为的快捷，并且两个查询的语句通过优化查询以后都没给出具体的优化方法，因此可以看出着两个查询语句并不需要优化。

优化截图1：
![](https://github.com/RaymodLam/Oracle/blob/master/test1/2.jpg?raw=true)

查询2:
```SQL
SELECT d.department_name，count(e.job_id)as "部门总人数"，
avg(e.salary)as "平均工资"
FROM hr.departments d，hr.employees e
WHERE d.department_id = e.department_id
GROUP BY department_name
HAVING d.department_name in ('IT'，'Sales');
```
运行截图2：
![](https://github.com/RaymodLam/Oracle/blob/master/test1/3.png?raw=true)

实验分析2：通过代码的运行，可以看出这段代码的运行时间为0.0秒，相对于查询一的运行时间稍微的缓慢一点，并且两个查询的语句通过优化查询以后都没给出具体的优化方法，因此可以看出着两个查询语句并不需要优化。

优化截图2：
![](https://github.com/RaymodLam/Oracle/blob/master/test1/1.jpg?raw=true)

## 自己的查询语句：
通过百度以后，我采用的是左外连接的方法。左外连接：左表不加限制，保留左表的数据，匹配右表，右表没有匹配到的行中的列显示为null。

运行截图：

![](https://github.com/RaymodLam/Oracle/blob/master/test1/5.png?raw=true)
