# Bugku CTF 把猪困进猪圈里 Writeup28

## 题目信息
- 平台：Bugku CTF

- 类型：Crypto

-  日期：2026.09.28

## 心路历程
打开看见乱码符合base64特征 直接解码base64 无效 于是搜索得知猪圈为图像

利用 base64.guru/converter/decode/image 来将乱码转换为图像 对照猪圈密码解密 得到flag

## 收获
猪圈密码为图像

base64 等可直接转换为图像 

base的判断方法可见

flag{thisispigpassword}


