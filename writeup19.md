# Bugku CTF 本地管理员 Writeup19

## 题目信息
来源:Bugku CTF

类型:WEB

日期：2026.09.24

## 心路历程
做 Web 题的习惯，第一步先查看网页源代码。在网页 HTML 注释中，找到密文字符串 dGVzdDEyMw==末尾带有=补位字符，判断这是 Base64 编码。 判断方法详见 [writeup10.md](./writeup10.md)得到test123

学习得知题目是管理员系统，CTF 这类题目默认管理员账号一般为admin

submit后页面返回提示：IP禁止访问，请联系本地管理员登陆，IP已被记录。

学习知识点：X‑Forwarded‑For（XFF）原本是代理服务器用来传递用户真实 IP 的 HTTP 请求头。
请求头由客户端可控，可以手动伪造。如果请求带上X‑Forwarded‑For: 127.0.0.1，服务器会误认为请求来自服务器本机，从而绕过 IP 限制。

打开浏览器开发者工具，切换到【网络】面板，勾选保留日志(Keep log)，填入账号密码点击 Submit 提交表单，捕获提交产生的 POST 登录数据包。

在网络请求列表找到 POST 数据包，右键数据包，选择【编辑并重发】
切换到 Headers 标签，新增请求头，Key 填写`X‑Forwarded‑For`，Value 填写`127.0.0.1`检查 Body 表单数据，保证user=admin&pass=test123不变

点击 Send 发送修改后的数据包，切换到响应面板，成功获取 flag。

## 收获
Base64 解码密文得到密码`test123`；无账号信息，尝试默认管理员账号`admin`。

按下 F12 打开开发者工具，切换至【网络】，勾选保留日志，捕获提交产生的 POST 请求包。

切换 Headers 标签，新增请求头：X‑Forwarded‑For: 127.0.0.1

为什么要添加这个请求头：
网站后端没有读取 TCP 真实连接 IP，而是读取X-Forwarded-For这个请求头来判断访问者 IP。
X-Forwarded-For是 HTTP 请求头，属于客户端可控的内容，我们可以自定义添加。
服务器代码判断逻辑：如果X-Forwarded-For的值等于127.0.0.1，就认为访问者是服务器本机，放行并输出 flag；否则拦截，提示 IP 禁止访问。

flag{e94d1d0f20cfea454c41048e2f59d74a}





