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

{% qnimg mssql-ext/1.gif title:mssql-extension alt:mssql-extension normal:yes %}

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

{% qnimg mssql-ext/2.png title:mssql-extension alt:mssql-extension normal:yes %}

### 3. 使用 `VS Code` 打开一个扩展名为 `sql` 的文件，或者使用 `(ctrl+n)` 快捷键创建一个新的编辑器并且把语言模式切换为SQL，mssql命令和功能将在编辑器中以SQL语言模式启用。

### 4. 通过 `F1` 或 `CTRL+SHIFT+P` 快捷键打开命令选项板按，输入 `sql` 然后选择 `MS SQL: Connect` 选项。 

{% qnimg mssql-ext/3.png title:mssql-extension alt:mssql-extension normal:yes %}

### 5. 然后使用一个已有的连接配置或者创建一个新的连接配置，这里选择 `Create Connection Profile`。

{% qnimg mssql-ext/4.png title:mssql-extension alt:mssql-extension normal:yes %}

### 6. 然后输入一个数据库服务器地址或者机器名。

{% qnimg mssql-ext/5.png title:mssql-extension alt:mssql-extension normal:yes %}

### 7. 然后输入数据库名称（可选，如果跳过则连接默认数据库）。

{% qnimg mssql-ext/6.png title:mssql-extension alt:mssql-extension normal:yes %}

### 8. 然后选择身份验证类型，`SQL Login` :使用数据库账号密码验证，`Integrated`：集成验证（Windows 身份验证），选择这种验证方式时将会跳过步骤9、10和11。

{% qnimg mssql-ext/7.png title:mssql-extension alt:mssql-extension normal:yes %}

### 9. 然后输入SQL用户名。

{% qnimg mssql-ext/8.png title:mssql-extension alt:mssql-extension normal:yes %}

### 10. 然后输入SQL密码。

{% qnimg mssql-ext/9.png title:mssql-extension alt:mssql-extension normal:yes %}

### 11. 然后选择是否需要记住密码。

{% qnimg mssql-ext/10.png title:mssql-extension alt:mssql-extension normal:yes %}

### 12. 然后输入该连接配置的名称（可选）。

{% qnimg mssql-ext/11.png title:mssql-extension alt:mssql-extension normal:yes %}

### 13. 完成之后将会出现连接提示信息。

{% qnimg mssql-ext/12.png title:mssql-extension alt:mssql-extension normal:yes %}

{% qnimg mssql-ext/13.png title:mssql-extension alt:mssql-extension normal:yes %}

---

### 打开 `文件>首选项>用户设置` 可以看到已经创建完成的连接配置，当然也可以直接在这里新增/修改/删除连接配置，更多详细的配置说明请参考 [官方文档][1]。

``` js
"mssql.connections": [
    {
        "server": "localhost",
        "database": "NopCommerce3.80",
        "authenticationType": "SqlLogin",
        "user": "sa",
        "password": "",
        "savePassword": true,
        "profileName": "NopCommerce3.80"
    },
    {
        "server": "localhost",
        "database": "ReportServerTempDB",
        "authenticationType": "Integrated",
        "profileName": "ReportServerTempDB",
        "password": ""
    }
]
```

### 示例

{% qnimg mssql-ext/14.png title:mssql-extension alt:mssql-extension normal:yes %}

[0]:https://code.visualstudio.com/Download
[1]:https://github.com/Microsoft/vscode-mssql

