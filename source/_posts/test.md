# 第一篇博客

按https://blog.cuijiacai.com/blog-building/教程，创建博客

已安装node和npm，安装

![image-20221212225733260](D:/Typora笔记/assets/test/image-20221212225733260-1672901200081.png)

github似乎访问不了，翻墙。

报错，按提示输入 npm audit fix,然后继续

![image-20221212230741304](D:/Typora笔记/assets/test/image-20221212230741304-1672901200082.png)

第二次报错

![image-20221212230939653](D:/Typora笔记/assets/test/image-20221212230939653-1672901200082.png)

发现node12.0.0以上就没有这个问题，用nvm切换

切换时报错

![Pasted image 20221212231758](D:/Typora笔记/assets/test/Pasted image 20221212231758-1672901200082.png)

原因

![Pasted image 20221212231730](D:/Typora笔记/assets/test/Pasted image 20221212231730-1672901200082.png)

不管空格问题，用管理员身份打开cmd，切换成功

继续hexo generate

新的报错

![image-20221212233138341](D:/Typora笔记/assets/test/image-20221212233138341-1672901200083.png)

怀疑是node版本遍历导致的，尝试重新安装

![image-20221212233356956](D:/Typora笔记/assets/test/image-20221212233356956-1672901200083.png)

似乎成功了，继续

![image-20221212233621327](D:/Typora笔记/assets/test/image-20221212233621327-1672901200083.png)

成功

![image-20221212233553801](D:/Typora笔记/assets/test/image-20221212233553801-1672901200083.png)

接下来修改package.json文件，运行下列命令

```
cd "博客目录"
git init
git add .
git commit -m "my blog first commit"
git remote add origin "远端github仓库地址"
git branch -M main
git push -u origin main
```

git add. 时报错

![image-20230104153850389](D:/Typora笔记/assets/test/image-20230104153850389.png)

原因是不同的操作系统使用不同的换行符

> Dos和Windows平台： 使用回车（CR）和换行（LF）两个字符来结束一行，回车+换行(CR+LF)，即“\r\n”；
> Mac 和 Linux平台：只使用换行（LF）一个字符来结束一行，即“\n”；
> 最早Mac每行结尾是回车CR 即'\r'，后mac os x 也投奔了 unix。

git config core.autocrlf false 把自动转换功能关掉即可

> git remote add origin "远端github仓库地址"

前先创建一个repository（仓库），参考https://www.elecfans.com/d/692155.html

github创建后出现如下页面，根据框处的命令输入

![image-20230104155924618](D:/Typora笔记/assets/test/image-20230104155924618.png)

报错

![image-20230104160118425](D:/Typora笔记/assets/test/image-20230104160118425.png)

修改host文件，用管理员身份打开记事本，打开文件修改

[Failed to connect to github.com port 443: Connection refused问题解决_YIMForever的博客-CSDN博客_port 443](https://blog.csdn.net/weixin_44442186/article/details/124979085)

没有用，运行git config --global http.proxy http://127.0.0.1:7890，还是没有用

（计网知识：

git config --global http.proxy http://127.0.0.1:7890是设置全局代理。

git config --global --unset http.proxy 取消全局代理

git config --global --get http.proxy 查看代理

第二天到公司发现连不上wifi了，但是在宿舍的wifi是一直连着的

![image-20230105080847574](D:/Typora笔记/assets/test/image-20230105080847574.png)

改完之后发现还是没用

打开clash 关掉系统代理之后退出，发现可以了）



![image-20230104192747911](D:/Typora笔记/assets/test/image-20230104192747911.png)

开启vpn发现可以了

然后登录时报错，发现不能用密码

![image-20230104195047807](D:/Typora笔记/assets/test/image-20230104195047807.png)

![image-20230104200126490](D:/Typora笔记/assets/test/image-20230104200126490.png)

在github中创建token，命名为blog token ，授予所以权限

![image-20230104201741454](D:/Typora笔记/assets/test/image-20230104201741454.png)

使用token push，成功了

然后注册并登陆[Netlify](https://www.netlify.com/)，使用github账号注册

![image-20230104202939948](D:/Typora笔记/assets/test/image-20230104202939948.png)

构建命令改成我们之前设置的`npm run netlify`

构建失败，查看原因

![image-20230104223417564](D:/Typora笔记/assets/test/image-20230104223417564.png)

发现删去构建命令才行，参考https://www.cnpython.com/qa/1430605，成功了，点击链接已经是博客了![image-20230104225314248](D:/Typora笔记/assets/test/image-20230104225314248.png)

修改这个![image-20230104225940153](D:/Typora笔记/assets/test/image-20230104225940153.png)





在腾讯云中设置域名解析

![image-20230104230403441](D:/Typora笔记/assets/test/image-20230104230403441.png)

在Netlify中配置用户域名

![image-20230104231221495](D:/Typora笔记/assets/test/image-20230104231221495.png)

![image-20230104231344904](D:/Typora笔记/assets/test/image-20230104231344904.png)

设置一下netlify本身的对于国外CDN的支持



发现还是有问题

![image-20230105082415535](D:/Typora笔记/assets/test/image-20230105082415535.png)





注册[Clouldflare](https://www.cloudflare.com/zh-cn/)并登陆，输入域名![image-20230104233622398](D:/Typora笔记/assets/test/image-20230104233622398.png)

修改腾讯云中的名称服务器为cloudflare中的

