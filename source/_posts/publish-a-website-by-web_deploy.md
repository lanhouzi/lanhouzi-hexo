title: 使用 Web Deploy 工具 发布站点到 IIS
tags:
  - IIS
  - Web Deploy
categories:
  - IIS
  - Web Deploy
date: 2016-09-21 01:38:39
---


## 使用 Web Deploy 工具 发布站点到 IIS

> 环境/工具：Windows Server 2008+，IIS 7.0+，[Web Deploy 3.6][0]，Visual Studio 2010+

{% qnimg iisstart.png title:IIS alt:IIS normal:yes %}

### 为什么要使用Web Deploy？

1. 无须再通过ftp或者远程登录服务器覆盖文件的方式进行部署站点；
2. 增量部署：只更新有差异的文件，避免了全站文件的更新；
3. 可以方便快捷的切换数据库连接字符串，免去手动修改数据库连接字符的操作；
4. 自动更新数据库：把数据库变更脚本按照顺序加入到数据库更新配置中，免去手动更新数据库的操作；
4. 拥有独立的部署账号，避免服务器管理员帐号外泄，造成不必要的安全威胁；
5. 部署完成之后自动打开目标站点；
6. 可以配合 `Web Farm` 使用，当主服务器更新部署完成之后从服务器会自动同步。

### <font color="#D20">在这里声明一下，网上的教程基本行不通或者都过时了，本教程亲测可用。</font>

### 1. 在服务器上安装 `IIS 7.0+` 和 `Web Deploy 3.6` ，启用 `Web Management Service` 和 `Web 部署代理任务`

{% qnimg web_deploy/1.png title:WebDeploy alt:WebDeploy normal:yes %}

### 2. 启用 IIS 管理服务

{% qnimg web_deploy/2_1.png title:WebDeploy alt:WebDeploy normal:yes %}

{% qnimg web_deploy/2_2.png title:WebDeploy alt:WebDeploy normal:yes %}

### 3. 创建 IIS 管理器用户（后面部署站点的时候会用到该帐号） 

{% qnimg web_deploy/3_1.png title:WebDeploy alt:WebDeploy normal:yes %}

{% qnimg web_deploy/3_2.png title:WebDeploy alt:WebDeploy normal:yes %}

### 4. 给站点添加 IIS 管理器权限 

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

[0]:https://www.microsoft.com/zh-cn/download/details.aspx?id=43717
