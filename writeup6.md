# Bugku CTF GET Writeup

## 题目信息
- 平台：Bugku CTF
- 题目名称：GET
- 类型：Web

## 心路历程
打开网页，页面无flag，使用Ctrl+U查看源代码，查看搜索发现为PHP代码然后进行翻译
查询得知要在在原网址末尾拼接?what=flag回车访问，得到flag。

## 收获
PHP是服务器端脚本语言，可以在服务器上执行代码，动态生成网页内容。
`$_GET`用于接收地址栏参数，GET传参格式：网址?参数名=值。
源码里的PHP代码会给出解题条件。

Flag：flag{6e0e5e4eb6375dbe865d2e150a011f8f}
