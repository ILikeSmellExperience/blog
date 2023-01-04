---
title: test
date: 2022-12-12 23:05:12
tags:
---

# 第一篇博客

按https://blog.cuijiacai.com/blog-building/教程，创建博客

已安装node和npm，安装

![image-20221212225733260](D:/Typora笔记/assets/test/image-20221212225733260.png)

github似乎访问不了，翻墙。

报错，按提示输入 npm audit fix,然后继续

![image-20221212230741304](D:/Typora笔记/assets/test/image-20221212230741304.png)

第二次报错

![image-20221212230939653](D:/Typora笔记/assets/test/image-20221212230939653.png)

发现node12.0.0以上就没有这个问题，用nvm切换

切换时报错

![Pasted image 20221212231758](D:/Typora笔记/assets/test/Pasted image 20221212231758.png)

原因

![Pasted image 20221212231730](D:/Typora笔记/assets/test/Pasted image 20221212231730.png)

不管空格问题，用管理员身份打开cmd，切换成功

继续hexo generate

新的报错

![image-20221212233138341](D:/Typora笔记/assets/test/image-20221212233138341.png)

怀疑是node版本遍历导致的，尝试重新安装

![image-20221212233356956](D:/Typora笔记/assets/test/image-20221212233356956.png)

似乎成功了，继续

![image-20221212233621327](D:/Typora笔记/assets/test/image-20221212233621327.png)

成功

![image-20221212233553801](D:/Typora笔记/assets/test/image-20221212233553801.png)