# Bugku CTF 聪明的小羊 Writeup

## 题目信息
来源:Bugku CTF
类型:Crypto

## 心路历程
看到栅栏同样使用https://gchq.github.io/CyberChef/
看到题目提示为栅栏 于是搜索Rail 因为两次将key修改为2 成功解码

## 收获
凯撒：纯英文字母，字母整体移位 → ROT Brute Force

栅栏：纯字母，提示栅栏，字符不变仅顺序打乱 → Rail Fence Cipher Decode

 凯撒方框：纯字母，矩阵方块重排顺序 → Caesar Box Cipher

flag：flag{6fde4163df05d900}
