# Bugku CTF 贝斯家族 Writeup25

## 题目信息
- 平台：Bugku CTF

- 类型：Crypto

-  日期：2026.09.27

## 心路历程

根据提示得知为base91 利用 ctf.bugku.com/tools 直接进行解码获得flag

## 收获
Base16：仅 0‑9 A‑F

Base32：大写 A‑Z，数字只有2‑7，无 0189，可带=

Base64：大小写 + 数字，符号只允许+/=

Base85：密文两头标记 <~ ~>

Base91：出现 @ 优先它，杂符号多

Base58：无 0 O I l，极少符号

flag{554a5058c9021c76}
