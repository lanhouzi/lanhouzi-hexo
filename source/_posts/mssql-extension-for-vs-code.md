title: 使用 Visual Studio Code 的 MSSQL 扩展
tags:
  - Visual Studio Code
  - mssql extension
categories:
  - Visual Studio Code
date: 2016-11-29 23:35:37
---


## 使用 Visual Studio Code 的 MSSQL 扩展

> 环境/工具：Windows 10，[Visual Studio Code][0]

{% qnimg iisstart.png title:IIS alt:IIS normal:yes %}

### 用于开发Microsoft SQL Server，Azure SQL数据库和SQL数据仓库的扩展，功能如下：

1. 连接到Microsoft SQL Server，Azure SQL数据库和SQL数据仓库；
2. 创建和管理连接配置文件和最近使用过的连接；
3. 在编写T-SQL脚本是可以体验到：智能提示，T-SQL片段，语法高亮，错误校验；
4. 执行T-SQL脚本；
5. 数据表格可视化；
6. 可以将查询结果保存为json或csv格式；
7. 自定义的扩展选项，包括命令快捷方式等。

### 1. 安装并启动 VS Code

### 2. 安装 mssql 扩展，然后重启 VS Code

{% qnimg mssql_ext/1.png title:mssql_extension alt:mssql_extension normal:yes %}

### 3. 使用 `VS Code` 打开一个 扩展名为 `sql` 的文件，或者使用 `(ctrl+n)` 快捷键创建一个新的编辑器并且把语言模式切换为SQL，mssql命令和功能将在编辑器中以SQL语言模式启用。

{% qnimg web_deploy/3_1.png title:WebDeploy alt:WebDeploy normal:yes %}

### 4. 使用命令选项板按F1键创建新的连接配置文件，键入sqlman运行MS SQL：管理连接配置文件命令。 选择创建。 有关如何在用户设置（settings.json）文件中创建和编辑连接配置文件的详细信息，请参阅管理连接配置文件。

{% qnimg web_deploy/4_1.png title:WebDeploy alt:WebDeploy normal:yes %}

{% qnimg web_deploy/4_2.png title:WebDeploy alt:WebDeploy normal:yes %}

### 5. 启用站点的 Web Deploy 发布功能

{% qnimg web_deploy/5_1.png title:WebDeploy alt:WebDeploy normal:yes %}

{% qnimg web_deploy/5_2.png title:WebDeploy alt:WebDeploy normal:yes %}

---
#### 到这里为止服务端（IIS）需要配置的事项已完成，下面配置客户端（Visual Studio）的相关事项

---

### 6. 打开 Visual Studio ，在需要部署的 Web 项目上单击右键选择 `发布`

{% qnimg web_deploy/6.png title:WebDeploy alt:WebDeploy normal:yes %}

### 7. 新建一个部署配置文件

{% qnimg web_deploy/7.png title:WebDeploy alt:WebDeploy normal:yes %}

### 8. 配置部署连接参数

{% qnimg web_deploy/8.png title:WebDeploy alt:WebDeploy normal:yes %}

### 9. 设置编译及连接字符串等相关参数

{% qnimg web_deploy/9.png title:WebDeploy alt:WebDeploy normal:yes %}

### 10. 预览部署更新文件列表

{% qnimg web_deploy/10.png title:WebDeploy alt:WebDeploy normal:yes %}

### 11. 发布站点，VS会输出部署消息

{% qnimg web_deploy/11.png title:WebDeploy alt:WebDeploy normal:yes %}

[0]:https://code.visualstudio.com/Download
