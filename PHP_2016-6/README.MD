  # 2016 年 6 月的 PHP 课程设计源代码

这是在 2016 年 6 月下学期结束之前的 PHP 课程设计实训周布置的作业。

## 任务描述

创建一个班级论坛网站，内容包括登录页面、主页、用户注册页面、浏览学生信息页面、新增学生信息页面、留言板发布页面和留言板浏览页面。

### 前端

**登录页面**

用户输入用户名、密码和验证码，单击登录按钮，如果存在用户且密码正确，进入主页，如果用户名和密码错误，显示提示信息。如果没有该用户名，进入用户注册页面。

**主页**

主页结构举例。自己设计布局及CSS样式。

```
-----------------------------------------------
|                 班级论坛网站                 |
-----------------------------------------------
| 侧  |                                       |
|     |                                       |
| 边  |                                       |
|     |                内容区                 |
| 栏  |                                       |
|     |                                       |
|     |                                       |
-----------------------------------------------
```

**用户注册页面**

包括用户名（如果用户名存在，则提示用户已存在）、密码（要求长度为8～15位，允许是大写字母、小写字母、数字和下划线，使用正则表达式进行验证）的信息注册。在该页面上传用户头像（文件格式可以是gif或jpg），头像文件保存在相应文件夹。

**浏览学生信息页面**

显示所有的学生信息，包含分页功能。输入学生姓名可以查询出该学生的全部信息。

**新增学生信息页面**

输入学生信息并提交保存。利用表单完成信息的输入和提交，性别使用单选按钮，（选做：班级和专业使用下拉列表框），使用正则表达式完成学号、电话号码的验证。

**留言板页面（发布）**

可以发布留言，并提交。

**留言板页面（查看）**

可以全部查看留言。

### 后台（数据库）

数据库名称自己创建。

**数据表1：用户信息表**

包含用户id（主键）、用户名、密码（32位哈希值）、注册时间。（不用输入数据，所有数据由用户注册页面写入）

字段名 | 类型 | 非空 | 主/外键 | 备注
-|-|-|-|-
UserId | int | 是 | 主键 | 用户id |
UserName | varchar（20） | 是 |  | 用户名 |
UserPsw | varchar（32） | 是 |  | 密码，保存为32位的哈希值。 |
Userregtime | timestamp | 是 |  | 注册时间为当前系统时间 |


**数据表2：学生信息表**

包含学号（主键）、姓名、性别、出生日期、班级、专业、籍贯、电话号码。（至少输入10条数据）

字段名 | 类型 | 非空 | 主/外键 | 备注
-|-|-|-|-
StdXH | int（8） | 是 | 主键 | 学号（长度为8位，第1位是大写字母，后7位是数字） |
StdXM | varchar（20） | 是 |  | 姓名 |
StdXB | varchar（2） | 是 |  | 性别 |
StdCSRQ | date | 是 |  | 出生日期 |
StdBJ | varchar（6） | 是 |  | 班级 |
StdZY | varchar（20） | 是 |  | 专业 |
StdJG | varchar（20） | 是 |  | 籍贯 |
StdTEL | varchar（11） | 是 |  | 电话号码（长度为11位，第1位是1，第2位是3、5、8，后9位是数字） |
