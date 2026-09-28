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

"Referer:https://www.google.com "：伪造来源为谷歌

http://160.202.254.160:12268 ：目标网页地址

相似利用cmd的可见

### curl
- `-H`：添加自定义请求头，伪造请求头，请求头校验类Web题使用。

- `-i`：显示完整响应（响应头+页面内容），需要看全部返回信息时使用。

- `-X`：指定请求方法，默认GET，POST请求场景使用。

- `-d`：提交POST表单数据，POST传参时使用。

  同样使用cmd加H的
1. `X-Forwarded-For`（XFF）：标记客户端IP，可伪造，本地管理员题用来伪装成本机`127.0.0.1`

2. `Referer`：标记来源页面，可伪造，你从哪里来题伪装跳转来源。


flag{b26151e8de2152f5645dbb77d7786a0e}




