# CTFHub vim缓存 writeup10

## 题目信息
来源:CTFHub

类型:web

日期：2026.10.13

## 心路历程
直接在网址后加入index.php 回车后发现无效

看到题目标题Vim搜索得到在网站地址后加上/.index.php.swp进行访问浏览器直接下载.swp缓存文件

得到flag
## 收获
Vim 编辑器在编辑文件时，会生成.swp交换缓存文件

解题思路是猜测特殊后缀文件名

Sublime/VSCode：.bak后缀，如index.php.bak

Vim：.swp、.swo交换文件，带前置小数点，如.index.php.swp

Emacs：文件名末尾波浪号~，如index.php~

IDEA/PHPStorm：.orig后缀，如index.php.orig

人工网站备份：www.zip、backup.tar.gz等压缩包

ctfhub{ebff1f8f47f86b3c50771332}
