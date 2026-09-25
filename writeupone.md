# CTFHub HTTP Method writeup1

## 题目信息
来源:CTFHub

类型:web

日期：2026.09.25

## 心路历程
看到http请求 第一反应与bugku中的post相同 使用reqbin工具 发现只能用于post与get 但本题中需要自定义请求方法

于是搜索得知curl 命令：-X 可以随便写请求方法名字，所以用它。

win+r打开cmd curl的-X参数自定义请求方法，构造curl命令发送CTFHUB请求curl -X CTFHUB http://challenge-1ffcdebef94e3f99.sandbox.ctfhub.com:10800/index.php

回车得到flag

## 收获
此题与post存在相似之处 但post可直接利用reqbin 详见

curl 命令：-X 可以随便写请求方法名字

ctfhub{422361669739930bb970ee85}
