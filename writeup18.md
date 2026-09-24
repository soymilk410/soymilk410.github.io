# Bugku CTF 变量1 Writeup18

## 题目信息
来源:Bugku CTF

类型:WEB

日期：2026.09.24

## 心路历程
打开题目，页面展示 PHP 代码，提示 flag 存在变量里。

$_GET['args']网址?后面必须写args=xxx  /^\w+$/只能用字母、数字、下划线。

$$args：把我们输入的 xxx，当成变量名，打印变量内容。

第一次尝试?args=flag
页面返回 NULL，说明没有叫 flag 的变量。

第二次尝试?args=GLOBALS
$GLOBALS是 PHP 自带变量，能展示页面所有变量。
访问后列出全部变量，找到 flag。

## 收获
GET 传参：代码固定接收参数名叫 args。

可变变量$$：输入的文字当作变量名。例：args

$GLOBALS：PHP 自带，查看全部变量，属于常识，题目没有提示。

flag{ff9a25fb995bfc337a1d4f892ac2f0a5}
