# CTFHub 302跳转 writeup1

## 题目信息
来源:CTFHub

类型:web

日期：2026.09.29

## 心路历程
开始尝试 F12 网络抓包，抓到 index.php 数据包，但 Edge 无法加载 302 请求的响应正文，读取不到 flag。

在CMD 执行 curl 命令 curl -i http://challenge-eb2de6c553f04e83.sandbox.ctfhub.com:10800/index.php

拿到题目flag

## 收获
此题也使用crul 相同可见[writeupone.md](./writeupone.md)

crul其他用法可见[writeup30.md](./writeup30.md)

-i参数显示全部响应头和内容

ctfhub{e57be6e7f11b9a8ba950c99a}
