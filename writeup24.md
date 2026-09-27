# Bugku 好像需要密码 Writeup

平台：Bugku CTF

题目名称：好像需要密码

日期：2026.09.27

## 解题过程
打开Burp Suite Community Edition，新建临时项目，进入主界面。

配置浏览器代理：打开Edge浏览器系统代理设置，开启手动代理，代理地址填写127.0.0.1，端口8080。

在Burp切换到Proxy模块的Intercept标签，开启请求拦截，状态变为Intercept is on
 
浏览器访问靶场页面，在密码框输入任意密码并提交，请求被Burp成功捕获，数据包为POST提交，密码参数为pwd。

右键捕获到的请求包，选择Send to Intruder送入爆破模块。

在Intruder的Positions标签，清除原有标记，选中pwd后的密码值添加载荷标记；切换到Payloads标签，载荷类型选择Numbers，设置数字范围10000~99999，步长1，点击Start attack启动爆破。

开始等待爆破，Burp社区版速度很慢，我等了特别特别久。
观察返回包的Length列，大部分请求响应长度都是1404，代表密码错误。直到出现一行Length不等于1404的记录，这一行对应的Payload就是正确密码。

得到正确密码12468。

回到Bugku靶场页面，输入密码12468提交，拿到flag：flag{aefd81c7f99daf9e473943940f8876c8}。

## 总结
通过Burp Proxy可捕获密码提交数据包，使用Intruder模块对5位数字密码进行爆破。

利用响应包长度差异区分正确与错误请求，错误密码返回页面长度固定为1404

实验完成后一定要关闭Burp拦截，并且关闭Windows系统手动代理，否则浏览器无法正常上网。

flag{a75667686fef05ef5bdf09d26a7d3373}
