# Bugku CTF 好像需要密码 Writeup24

## 题目信息
来源:Bugku CTF

类型:WEB

日期：2026.09.27

## 心路历程
因为需要密码

打开 Burp Suite Community Edition，新建临时项目，进入主界面。

配置浏览器代理：打开 Edge 浏览器系统代理设置，开启手动代理，代理地址填写127.0.0.1，端口8080。
 
在 Burp 切换到 Proxy 模块的 Intercept 标签，开启请求拦截，状态变为Intercept is on。

浏览器访问靶场页面，在密码框输入任意密码并提交，请求被 Burp 成功捕获，数据包为 POST 提交，密码参数为pwd。

右键捕获到的请求包，选择Send to Intruder送入爆破模块。

在 Intruder 的 Positions 标签，清除原有标记，选中pwd后的密码值添加载荷标记；切换到 Payloads 标签，载荷类型选择 Numbers，设置数字范围 10000~99999，步长 1，点击 Start attack 启动爆破。

开始等待爆破，Burp 社区版速度很慢，我等了特别特别久。观察返回包的 Length 列，大部分请求响应长度都是 1404，代表密码错误。直到出现一行 Length 不等于 1404 的记录，这一行对应的 Payload 就是正确密码。

双击该条记录查看响应内容，得到正确密码12468。

回到 Bugku 靶场页面，输入密码12468提交，拿到 flag：

## 收获
爆破密码可用Burp 但等待时间实在过长

flag{a75667686fef05ef5bdf09d26a7d3373}
