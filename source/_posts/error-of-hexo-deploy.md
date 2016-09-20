title: Hexo 部署命令 hexo deploy 执行报错
tags:
  - hexo
categories:
  - hexo
date: 2016-03-25 01:13:00
---


### Hexo 发布内容到 `github`，执行 `hexo deploy` 命令后报错

>搞了一晚上还是没解决，墙头都翻烂了，真是百撕不得骑姐啊，各路大仙有没有遇到过这个问题，跪求解决方案...

#### 这是Deployment配置项

``` yaml
deploy:
  type: git
  repository: https://github.com/lanhouzi/lanhouzi.github.com.git
  branch: master
```
---
#### 下图是 git bash 的截图
<center>
![hexo deploy 执行报错](http://lanhouzi.qiniudn.com/hexo/blog/hexo_deploy_error.png)
</center>

#### 这是 git bash 报错代码
``` bash
BlueMonkey@BlueMonkey-PC MINGW64 /d/GitHub/hexo/hexo (master)
$ hexo d
INFO  Deploying: git
INFO  Clearing .deploy folder...
INFO  Copying files from public folder...
On branch master
Changes not staged for commit:
        modified:   ../themes/hueman (modified content, untracked content)

no changes added to commit
Fatal: TaskCanceledException encountered.
bash: /dev/tty: No such device or address
error: failed to execute prompt script (exit code 1)
fatal: could not read Username for 'https://github.com': Invalid argument
FATAL Something's wrong. Maybe you can find the solution here: http://hexo.io/docs/troubleshooting.html
Error: Fatal: TaskCanceledException encountered.
bash: /dev/tty: No such device or address
error: failed to execute prompt script (exit code 1)
fatal: could not read Username for 'https://github.com': Invalid argument

    at ChildProcess.<anonymous> (D:\GitHub\hexo\hexo\node_modules\hexo-util\lib\spawn.js:42:17)
    at emitTwo (events.js:100:13)
    at ChildProcess.emit (events.js:185:7)
    at maybeClose (internal/child_process.js:850:16)
    at Process.ChildProcess._handle.onexit (internal/child_process.js:215:5)
FATAL Fatal: TaskCanceledException encountered.
bash: /dev/tty: No such device or address
error: failed to execute prompt script (exit code 1)
fatal: could not read Username for 'https://github.com': Invalid argument

Error: Fatal: TaskCanceledException encountered.
bash: /dev/tty: No such device or address
error: failed to execute prompt script (exit code 1)
fatal: could not read Username for 'https://github.com': Invalid argument

    at ChildProcess.<anonymous> (D:\GitHub\hexo\hexo\node_modules\hexo-util\lib\spawn.js:42:17)
    at emitTwo (events.js:100:13)
    at ChildProcess.emit (events.js:185:7)
    at maybeClose (internal/child_process.js:850:16)
    at Process.ChildProcess._handle.onexit (internal/child_process.js:215:5)

```
