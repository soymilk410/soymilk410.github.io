# CTFHub cookie writeup5

## 题目信息
来源:CTFHub

类型:web

日期：2026.10.12

## 心路历程
打开看见hello guest. only admin can get flag.
说明当前用户身份为访客 guest，只有管理员 admin 才可获取 Flag

于是打开F12 切换到应用程序面板

在左侧找到当前域名下的 Cookies，发现存在一条 admin=0 的身份标识

将 admin 的值从 0 手动修改为 1

F5刷新页面，成功获得 Flag
## 收获
Cookie 值含义：

 admin=0：普通访客，无权限

 admin=1：管理员，有权限

ctfhub{6c195567c5b899c5a34d0344}
