# Bugku CTF telnet Writeup31

## 题目信息
来源:Bugku CTF

类型:MISC

日期：2026.09.29

## 心路历程
首先将 networking.pcap 放入下载文件 把流量包文件移动到电脑 Downloads 文件夹方便命令行精准定位 CMD 需要在文件目录下才能读取、操作文件

在cmd中输入执行命令 cd Downloads切换到下载文件夹 让当前命令行工作目录和文件目录保持一致

输入dir查看当前文件夹所有文件 校验目标 pcap 文件是否存在、路径是否正确 预防后面出错

执行命令 findstr /c:"flag" networking.pcap 
 在流量包文件中搜索 flag 关键词
 直接提取文件内所有含 flag 的明文字符串
 Telnet 明文传输，flag 直接储存在二进制流量包内，无需复杂解析
 pcap 明文流量题、已知存在固定关键词，基本都可用

## 收获
Telnet 传输内容不加密，别人抓包就能看到信息，不安全。

Wireshark 可以查看网络数据包，追踪完整对话。

flag{d316759c281bf925d600be698a4973d5}
