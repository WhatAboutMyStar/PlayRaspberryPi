# PlayRaspberryPi
记录我玩转树莓派的经历，踩过的坑等等

### 第一步 从烧录系统到启动树莓派
这一步我折腾了两天，先说一下我个人情况，我买的是最新的树莓派4，内存4G，有个16G的SD卡，有一根网线，一台笔记本电脑，（注意：我没有给树莓派配鼠标和键盘还有显示器），我的计划是通过网线把笔记本和树莓派互联，在笔记本上远程登录（ssh）到树莓派上，对树莓派进行控制。
- 首先，关于烧录系统，我一开始烧录了Ubuntu18.04（不是官方的推荐系统），后来折腾了半天都不对，不能远程登录。原来是因为我没有烧录支持树莓派的Ubuntu mate系统，支持树莓派的系统可在官网下载[点击这里可前往官网下载系统镜像](https://www.raspberrypi.org/downloads/)
- 为了解决上述问题，我反反复复烧录了3次系统，最后终于成功烧录。连上网线后，在网络与共享中心允许其他用户通过计算机的Internet访问
![WLAN](https://github.com/WhatAboutMyStar/PlayRaspberryPi/blob/master/img/WLAN.png)
但很快，第二个问题来了，我在cmd命令行里输入arp -a寻找我的树莓派IP地址失败。正确的IP应该显示如下，192.168.137.36，右边的类型应该为动态，而我当时显示为静态，因此无法远程登录树莓派。
![IP图片](https://github.com/WhatAboutMyStar/PlayRaspberryPi/blob/master/img/IP.png)
- 如果你出现上述问题，你可以将SD卡插入电脑，在boot路径下找到cmdline.txt文件，在前面加上IP=192.168.137.2即可。（如下图所示）

![设置IP](https://github.com/WhatAboutMyStar/PlayRaspberryPi/blob/master/img/%E8%AE%BE%E7%BD%AEIP.png)

- 这个时候就能使用putty进行远程登录了！！！（[putty等软件可在此下载](https://github.com/WhatAboutMyStar/PlayRaspberryPi/tree/master/%E5%BF%85%E8%A6%81%E7%9A%84%E4%B8%80%E4%BA%9B%E8%BD%AF%E4%BB%B6)）

![puttySSH](https://github.com/WhatAboutMyStar/PlayRaspberryPi/blob/master/img/puttySSH.png)
- 成功登录！终于进来了。

![成功登录](https://github.com/WhatAboutMyStar/PlayRaspberryPi/blob/master/img/successful.png)
