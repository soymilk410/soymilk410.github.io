# Bugku CTF alert Writeup

## 题目信息
来源：Bugku CTF
题目：你必须让他停下
类型：Web

## 心路历程
打开题目页面，网页不断自动刷新，页面看不见照片是什么
按下Ctrl+U查看源代码，找到刷新的时间，尝试修改，页面刷新太快修改失败。
按下F12使用Ctrl+Shift+P禁用JavaScript，页面不再自动更新。
然后用F5刷新页面，等到图片出现，迅速用Ctrl+U查看源码，成功找到flag。

## 收获                                                                                                                            
Ctrl+Shift+P可以快速禁用JavaScript，页面就不会自动更新。
F5快捷键用于手动刷新页面，自己控制刷新时机。

flag{70382433efb3cbfba9087f678d275e87}
