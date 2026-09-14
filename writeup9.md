# Bugku CTF [+-<>] Writeup

## 题目信息
来源:Bugku CTF

类型:Crypot

## 心路历程
题目描述中为几种特殊符号 利用tool.bugku.com/brainfuck/ 来解码按Brainfuck to Text与Ook形式相同

## 收获
https://tool.bugku.com/brainfuck/ 可用于解密Ook!、Brainfuck满屏Ook. Ook? Ook!为 Ook! to Text满屏< > + - [ ]为Brainfuck to Text
Text to Ook! 普通文字变为加密成 Ook! 密文
Text to short Ook! 普通文字压缩简短版Ook。和上面一样，只是输出的文本格式精简一点
Ook! to Text Ook 密文还原成正常文字
Text to Brainfuck 普通文字 加密成Brainfuck代码（< > + - . , [ ]符号）
Brainfuck to Text 看到一长串只有 < > + - . , [ ] 的符号，粘贴进去点这个，得到flag。

Flag：flag{0d86208ac54fbf12}

