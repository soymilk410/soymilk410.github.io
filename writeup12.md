# Bugku CTF 这是一张照片 Writeup

## 题目信息
来源:Bugku CTF

类型:MISC

## 心路历程
打开文件为一张照片 用记事本打开看见底部藏有代码 用https://xtechtools.com/html-entity/ 在线解码得到flag：key{you are right}

后尝试使用https://www.boxentriq.com/steganography/steghide-extractor 也可以提取出来flag

## 收获
- xtechtools.com 可使用标志：

出现 &#xxxx; 格式字符串：HTML实体编码，使用HTML实体解码

字符串末尾带=、大小写字母+数字：Base64编码，Base64解码

%xx样式字符：URL编码，URL解码

\x61 / 0x开头数字：十六进制(Hex)，16进制转字符串

- 当照片存在隐藏信息也可使用www.boxentriq.com


Flag：key{you are right}

