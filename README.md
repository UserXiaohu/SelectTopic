## 一、项目获取

项目下载地址：http://shiyuncode.com/details?id=41

博客地址：https://blog.csdn.net/m0_47220500/article/details/126866947

## 二、**项目简介**

本系统研究高校毕业生毕业设计选题。该系统主要采用B/S模式，用户通过浏览器实现自己的需求，也就是高校大四毕业生及老师来完成毕业设计的相关事情。

这个系统分成三个功能模块，分别为系统管理员功能模块，学生功能模块，教师功能模块。

系统管理员模块主要实现学生和教师信息的录入以及系部专业的管理。

学生功能模块主要实现论文题目的选择和查看，以及论文的上传。

教师功能模块主要实现提交论文题目，确认学生选题以及审核论文初稿。

## 三、**开发环境**

运行环境：推荐JDK 1.8；

开发工具：IDEA（推荐）、Eclipse、MyEclipse；

操作系统：windows 10 8G内存以上（其他windows以及macOS支持，但不推荐）；

数据库：MySQL5.6(推荐)及其他版本（支持）；

数据库可视化工具：Navicat Premium 15（推荐）以及其他Navicat版本

## 四、**项目技术**

JAVA语言进行开发，采用SSM框架开发后端，数据库选用MySQL，使用IDEA进行开发后端接口；使用VUE语言开发前端，使用element-ui为前端框架

后端：JAVA、Spring、SpringMVC、MyBatis、mysql

前端：JS、LayUI、Ajax、Jquery

## 五、**系统架构**

![img](file:///img\wps1.jpg) 

## 六、**运行截图**

![img](file:///.\img\bg.jpg)

![img](file:///.\img\wps2.jpg) 

![img](file:///.\img\wps3.jpg) 

![img](file:///.\img\wps4.jpg)![img](file:///.\img\wps5.jpg)![img](file:///.\img\wps6.jpg)![img](file:///.\img\wps7.png) 

![img](file:///.\img\wps8.jpg)![img](file:///.\img\wps9.jpg)![img](file:///.\img\wps10.jpg) 

![img](file:///.\img\wps11.jpg)![img](file:///.\img\wps12.jpg)![img](file:///.\img\wps13.jpg) 

 

## 七、数据库设计

t_admin表

| 字段名称 | 数据类型    | 是否必填 | 注释 |
| -------- | ----------- | -------- | ---- |
| id       | int         | 是       |      |
| name     | varchar(20) | 是       |      |
| password | varchar(20) | 是       |      |

t_dept表

| 字段名称  | 数据类型     | 是否必填 | 注释 |
| --------- | ------------ | -------- | ---- |
| dept_id   | int unsigned | 是       |      |
| dept_name | varchar(30)  | 是       |      |

t_major表

| 字段名称   | 数据类型    | 是否必填 | 注释 |
| ---------- | ----------- | -------- | ---- |
| major_id   | int         | 是       |      |
| major_name | varchar(30) | 是       |      |
| dept_name  | varchar(30) | 是       |      |
| dept_id    | int         | 是       |      |

t_papertitle表

| 字段名称      | 数据类型     | 是否必填 | 注释 |
| ------------- | ------------ | -------- | ---- |
| id            | int          | 是       |      |
| title_name    | varchar(50)  | 是       |      |
| properties    | varchar(50)  | 是       |      |
| teacher_name  | varchar(20)  | 是       |      |
| required      | varchar(500) | 是       |      |
| title_major   | varchar(20)  | 是       |      |
| choose_status | int          | 是       |      |
| sure_status   | int          | 是       |      |
| dept          | varchar(20)  | 是       |      |
| teacher_num   | int          | 是       |      |

t_student表

| 字段名称     | 数据类型    | 是否必填 | 注释 |
| ------------ | ----------- | -------- | ---- |
| id           | int         | 是       |      |
| number       | int         | 是       |      |
| name         | varchar(20) | 是       |      |
| password     | varchar(20) | 是       |      |
| sex          | varchar(2)  | 是       |      |
| major        | varchar(20) | 是       |      |
| enyear       | varchar(15) | 是       |      |
| phonenumber  | varchar(15) | 是       |      |
| qq           | varchar(15) | 是       |      |
| dept         | varchar(20) | 是       |      |
| options      | int         | 是       |      |
| papertitleid | int         | 是       |      |

t_studentpapers表

| 字段名称     | 数据类型                  | 是否必填 | 注释 |
| ------------ | ------------------------- | -------- | ---- |
| id           | int(10) unsigned zerofill | 是       |      |
| stuNum       | int                       | 是       |      |
| paperPath    | varchar(200)              | 是       |      |
| stuName      | varchar(20)               | 是       |      |
| stuDept      | varchar(20)               | 是       |      |
| stuMajor     | varchar(20)               | 是       |      |
| checkStatus  | int                       | 是       |      |
| teacherNum   | int                       | 是       |      |
| paperAdvices | varchar(500)              | 否       |      |

t_studentpapertitles表

| 字段名称             | 数据类型     | 是否必填 | 注释 |
| -------------------- | ------------ | -------- | ---- |
| id                   | int unsigned | 是       |      |
| paperTitleName       | varchar(50)  | 是       |      |
| studentName          | varchar(20)  | 是       |      |
| studentNumber        | int          | 是       |      |
| paperTitleProperties | varchar(50)  | 是       |      |
| paperTitleRequired   | varchar(100) | 是       |      |
| major                | varchar(20)  | 是       |      |
| dept                 | varchar(20)  | 是       |      |
| teacherNum           | int          | 是       |      |
| teacherName          | varchar(20)  | 是       |      |
| checkStatus          | int          | 是       |      |

t_teacher表

| 字段名称    | 数据类型    | 是否必填 | 注释 |
| ----------- | ----------- | -------- | ---- |
| id          | int         | 是       |      |
| num         | int         | 是       |      |
| name        | varchar(20) | 是       |      |
| password    | varchar(20) | 是       |      |
| position    | varchar(10) | 是       |      |
| phonenumber | varchar(15) | 是       |      |
| qq          | varchar(15) | 是       |      |

 
