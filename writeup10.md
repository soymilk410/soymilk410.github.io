# Bugku CTF /.- Writeup

## 题目信息
来源:Bugku CTF
类型:Crypto

## 心路历程
题目描述中为/.-几种特殊符号 查询得知利用gchq.github.io/CyberChef/来解码 但第一次未改Word delimiter 
后来查询得知修改 在input位置输入进去 成功在output得出大写F L A G  D 3 F C B F 1 7 F 9 3 9 9 5 0 4将字母改写为小写 成功解答

## 收获
利用gchq.github.io/CyberChef/来解码
CyberChef 适用
摩尔斯电码：只有 . - /
Base64：大小写字母+数字，末尾常有=
十六进制(Hex)：仅 0-9、A-F
 凯撒/简单替换：只有英文字母，字母互相移位替换
 ASCII：一串0~127的数字
二进制：只有0、1
Unicode转义：带有%u，如%u7b
单词用/隔开 Word delimiter选 Forward slash
单词用换行隔开 Word delimiter选 Line feed
用Bugku BF网
Ook!：只有 Ook / Ook! 单词
Brainfuck(BF)：仅8个符号 < > + - . , [ ]

Flag：flag{d3fcbf17f9399504}
