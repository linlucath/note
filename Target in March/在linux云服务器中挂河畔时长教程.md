## 基本原理：
定时发送请求头，制造自己在线的假象
## 要求：
- 有能连网的云服务器
## 步骤
1. 获取 curl 命令
打开chrome > 访问 bbs.uestc.edu.cn > 打开 developer tools (windows 系统按 F12) > 进入network 栏 > 登录河畔（记得勾上自动登录） > 在 network 下面寻找 bbs.uestc.edu.cn 这一栏 > 右键 copy as Curl (bash)
 
 2. 编写shell脚本
 在云服务器的bash中mkdir一个新目录 > vim新建一个shell脚本（如auto_login.sh） > 添加一下内容
```
 #! /bin/bash
 while true
 do
     curl ...(将这一行换为上一步获得的curl命令)
     > html
     sleep 180
done
```

    3.定时运行脚本
    'chmod 777 auto_login.sh' > 'nohup ./auto_login.sh > output &'

