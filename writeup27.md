# Bugku CTF easy_hash Writeup27

## 题目信息
- 平台：Bugku CTF

- 类型：Crypto

-  日期：2026.09.27

## 心路历程
打开Python源码查询得知：程序会把flag的每一个字符单独计算MD5，

一行MD5对应原始的一个字符。

在线哈希查询网站 cmd5.com，将output里每一行的MD5复制粘贴进去 每一行代表一个字母或数字

成功拼接前四个所获得的正好为flag 证实猜想正确 继续解码拼接成完整flag

## 收获
看代码代码写了hashlib.md5，md5就是一种哈希算法。MD5算出来的结果永远是32位，一眼就能认出来。

每个字符单独算MD5 拿到一堆32位MD5串 进行拼接

flag{We1c0me_t0_the_w0r1d_0f_md5}
