# Bugku CTF eval Writeup23

## 题目信息
来源:Bugku CTF

类型:WEB

日期：2026.09.27

## 心路历程
进行源代码解读include "flag.php";：加载同目录下 flag.php 文件，flag 放在这个文件里面。

◦ $a = @$_REQUEST['hello'];：读取网址中?hello=后面输入的内容，保存到变量$a。

◦ eval( "var_dump($a);");：eval 会把双引号内的内容当做 PHP 代码运行，$a的内容会直接替换进去。

◦ show_source(__FILE__);：把当前这段 PHP 代码高亮显示在网页上，也就是我们看到的源码。

我想到可以直接$flag，于是构造网址参数：?hello=$flag。
替换进 eval 后代码变成：var_dump($flag);。
访问页面，得到文字Too Young Too Simple。

PHP 函数file("flag.php")可以读取 flag.php 里面全部内容。
构造参数：?hello=file("flag.php")。 http://160.202.254.160:11367/?hello=file("flag.php")

找到真实 flag

## 收获
eval 漏洞原理：eval 会把拼接后的字符串直接当成 PHP 代码运行。我们在?hello=后面写的内容，会直接替换到代码里$a的位置执行

file("文件名")是 PHP 读取文件的函数，可以读出文件里面全部文字。

flag{927c7ba0966542099af33decacce7f6f}

