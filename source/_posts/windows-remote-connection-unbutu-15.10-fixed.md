title: Windows 远程桌面连接 Unbutu Kylin 15.10 补充
tags:
  - Unbutu
categories:
  - Unbutu
date: 2016-04-12 00:35:02
---


## 上一篇文章[Windows 远程桌面连接 Unbutu Kylin 15.10][0] 讲了如何使用Windows的远程桌面连接工具登陆Unbutu Kylin 15.10，后来经过测试可能会存在连接不上的情况，下面做2点补充。

> 环境/工具：Windows 7+ 一台，[Unbutu Kylin 15.10][0] 一台

### 补充点1. 如果防火墙是打开状态需要把3389和3350端口加入到允许规则，打开一个终端窗口执行以下命令

```
sudo ufw allow 3389/tcp
sudo ufw allow 3350/tcp
```

![把3389和3350端口加入到允许规则][1]

### 补充点2. Unbutu 左上角菜单 “应用程序－系统工具－首选项－桌面共享” ，勾选如图示的选项

![桌面共享][2]

[0]: http://www.lanhouzi.net/2016/03/31/windows-remote-connection-unbutu-15.10/
[1]: http://lanhouzi.qiniudn.com/hexo/blog/ubuntu_kylin_15.10_13.png
[2]: http://lanhouzi.qiniudn.com/hexo/blog/ubuntu_kylin_15.10_14.png