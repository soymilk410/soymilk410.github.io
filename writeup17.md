# Bugku CTF 备份是个好习惯 Writeup17

## 题目信息
来源:Bugku CTF

类型:WEB

日期：2026.09.24

## 心路历程
因为题目名为备份 因此看见后在网址输入/index.php.bak 将文件保存备份用记事本打开发现代码

解析代码的意思 一开始只看到if(md5($key1) == md5($key2) && $key1 !== $key2){echo $flag."取得flag";}

所以错误认为只需要打出key1[]=1&key2[]=2 结果自然没有发现flag

再次查看代码才发现 还有$str = str_replace('key','',$str);代码会把 url 里面所有字符串key直接替换成空

于是再次修改在网址加入?kkeyey1[]=a&kkeyey2[]=b 当运行时正好将中间的key删除剩下的拼接也正好是key刚好运行

回车得到flag
## 收获
网址只有 IP + 端口，无文件名，默认文件一般是index.php

备份文件常用后缀.bak，直接访问可下载源码（仅靶场使用）

MD5 数组绕过：PHP 中 md5 传入数组返回null，null==null，实现哈希相等、原值不等

双写绕过：关键词会被删除时，嵌套写kkeyey；删掉中间 key 之后复原出 key

flag{0d78898b0ef239a8b4399012612caeb0}



