# Bugku CTF 你从哪里来 Writeup30

## 题目信息
来源:Bugku CTF

类型:WEB

日期：2026.09.28

## 心路历程
打开后看见are you from google? 认为应当从谷歌进行访问

查询得知可在win+R搜索cmd输入指令伪造 curl -H "Referer:https://www.google.com" http://160.202.254.160:12268
 
回车获取flag
## 收获
-H：添加自定义 HTTP 请求头

"Referer:https://www.google.com"：伪造来源为谷歌

http://160.202.254.160:12268：目标网页地址

相似利用cmd的可见

flag{bug-ku_ai_admin}
