# Bugku CTF 网站被黑 Writeup1822

## 题目信息
来源:Bugku CTF

类型:WEB

日期：2026.09.27

## 心路历程
按照web题方式 先打开源代码 ctrl+F查找flag发现没有

查询得知根据题目名称 “网站被黑”，推测黑客入侵网站后上传了网页后门 webshell。常见后门文件名为 shell.php。

在原网址末尾拼接 /shell.php，访问新地址，页面出现密码输入框。

尝试弱口令hack，输入密码提交

成功后得到flag

## 收获
什么时候试shell.php：题目提示网站被黑、有后门；网站是 PHP 环境；首页和源码都找不到线索。

常见后门文件名：shell.php、webshell.php、back.php、admin.php

弱口令就是容易猜到的简单密码，入门题可以试 hack、admin、123456。

webshell 后门作用：黑客攻破服务器后上传的文件，用来远程控制服务器、查看服务器里的文件。首页不会放它的链接，需要手动拼地址访问。

flag{fff588db02ea89fb40150c17dab506f2}
