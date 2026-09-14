# Bugku CTF POST Writeup

## 题目信息
来源:Bugku CTF

类型:web

## 心路历程
打开网页无flag，ctrl+u查看源码，发现代码使用$_POST接收参数，不能像GET题在地址栏传参 错误修改网址加入？what=flag后出现404。

查询后使用在线请求工具 https://reqbin.com，选择POST，在Body填入what=flag，发送请求得到flag。

## 收获
GET题直接修改网址传参；POST题使用reqbin在线请求工具修改请求体传参。

PHP $_POST 获取请求体内参数，POST参数不会出现在网址栏。

可以用 https://reqbin.com帮助修改

Flag:flag{1f8909609f0f666461a0780d0d44d9a8}
