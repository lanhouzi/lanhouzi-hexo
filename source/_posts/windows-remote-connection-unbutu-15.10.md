title: Windows 远程桌面连接 Unbutu Kylin 15.10
tags:
  - Unbutu
categories:
  - Unbutu
date: 2016-03-31 01:18:02
---


## 使用 Windows 远程桌面连接 工具，远程连接 Unbutu Kylin 15.10 操作系统

> 环境/工具：Windows 7+ 一台，[Unbutu Kylin 15.10][0] 一台

### 1. 运行 Unbutu Kylin 15.10 操作系统，打开一个终端窗口
![运行 Unbutu Kylin 15.10 操作系统][1]

### 2. 安装xrdp
```
-->输入"sudo apt-get install xrdp"
-->回车
-->输入root用户的密码
-->回车
-->输入"y"
-->回车，安装完成。
```
![安装xrdp][2]

> 若终端窗口输出以上消息，则说明`xrdp`已安装在本机

### 3. 安装vnc4server
```
-->输入"sudo apt-get install vnc4server"
-->回车
-->输入root用户的密码
-->回车
-->输入"y"
-->回车，安装完成。
```
![安装vnc4server][3]

> 若终端窗口输出以上消息，则说明`vnc4server`已安装在本机

### 4. 安装xfce4
```
-->输入"sudo apt-get install xubuntu-desktop"
-->回车
-->输入root用户的密码
-->回车
-->输入"y"
-->回车
-->输入"echo "xfce4-session" >~/.xsession" （请注意这里有个双引号！）
-->回车
-->输入"sudo service xrdp restart"
-->回车，安装完成。
```
![安装xfce4][4]

> 若终端窗口输出以上消息，则说明`xfce4`已安装在本机

![安装xfce4][5]

### 5. 查看IP地址
![查看IP地址][6]

![查看IP地址][7]

### 6. 打开Windows远程桌面连接
```
-->在Windows中使用快捷键"Win+R"打开CMD运行窗口
-->输入"mstsc"
-->回车
-->输入Unbutu Kylin 15.10的IP地址
-->连接
-->勾选"不再询问我..."
-->是
```
![打开CMD运行窗口][8]

![远程桌面连接][9]

![远程桌面连接][10]

### 7. 登录Unbutu Kylin 15.10桌面
```
-->选择"sesman-Xvnc"
-->输入"用户名和密码"
-->OK
-->成功登录到Unbutu Kylin 15.10桌面。
```
![登录][11]

![登录成功][12]


[0]: http://www.ubuntukylin.com/downloads/
[1]: http://lanhouzi.qiniudn.com/hexo/blog/ubuntu_kylin_15.10_1.png
[2]: http://lanhouzi.qiniudn.com/hexo/blog/ubuntu_kylin_15.10_2.png
[3]: http://lanhouzi.qiniudn.com/hexo/blog/ubuntu_kylin_15.10_3.png
[4]: http://lanhouzi.qiniudn.com/hexo/blog/ubuntu_kylin_15.10_4.png
[5]: http://lanhouzi.qiniudn.com/hexo/blog/ubuntu_kylin_15.10_5.png
[6]: http://lanhouzi.qiniudn.com/hexo/blog/ubuntu_kylin_15.10_6.png
[7]: http://lanhouzi.qiniudn.com/hexo/blog/ubuntu_kylin_15.10_7.png
[8]: http://lanhouzi.qiniudn.com/hexo/blog/ubuntu_kylin_15.10_8.png
[9]: http://lanhouzi.qiniudn.com/hexo/blog/ubuntu_kylin_15.10_9.png
[10]: http://lanhouzi.qiniudn.com/hexo/blog/ubuntu_kylin_15.10_10.png
[11]: http://lanhouzi.qiniudn.com/hexo/blog/ubuntu_kylin_15.10_11.png
[12]: http://lanhouzi.qiniudn.com/hexo/blog/ubuntu_kylin_15.10_12.png