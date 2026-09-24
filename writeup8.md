# Bugku CTF Ook Writeup8

## 题目信息
来源:Bugku CTF

类型:Crypot

 日期：2026.09.18
## 心路历程
打开看见为记事本里面充满Ook. Ook? Ook!等循环 查询得知使用Bugku在线解码工具https://tool.bugku.com/brainfuck/

将记事本内容全部复制进解码工具 含有五个按键查询用处后按Ook!to Text Ook解码得到flag

## 收获
https://tool.bugku.com/brainfuck/ 可用于解密Ook!、Brainfuck满屏Ook. Ook? Ook!为 Ook! to Text满屏< > + - [ ]为Brainfuck to Text

Text to Ook! 普通文字变为加密成 Ook! 密文

Text to short Ook! 普通文字压缩简短版Ook。和上面一样，只是输出的文本格式精简一点

Ook! to Text Ook密文还原成正常文字

Text to Brainfuck 普通文字 加密成Brainfuck代码（< > + - . , [ ]符号）

Brainfuck to Text 看到一长串只有 < > + - . , [ ] 的符号，粘贴进去点这个，得到flag。

flag{0a394df55312c51a}
