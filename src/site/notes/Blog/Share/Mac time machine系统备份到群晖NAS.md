---
{"aliases":"Mac time machine系统备份到群晖NAS","category":"tools","tags":["tools","mac","nas"],"status":"published","link":"NA","date created":"2023-01-14 Sat 22:59:13","date modified":"2024-02-21 Wed 19:57:59","dg-publish":true,"permalink":"/Blog/Share/Mac time machine系统备份到群晖NAS/","dgPassFrontmatter":true,"noteIcon":"1","created":"2023-01-14T22:59:13.493+08:00","updated":"2024-02-21T19:58:00.320+08:00"}
---


## Time Machine

[使用“时间机器”备份你的 Mac](https://support.apple.com/zh-cn/HT201250)

## 群晖 Nas 配置

Time Machine 的使用需要指定外置存储，群晖 nas 是个很好的选择。

首先需要开启 AFP 服务。

![Pasted image 20230114231305](https://github.com/Yunz93/PicRepo/raw/main/image/Pasted%20image%2020230114231305.png)

其次要打开 Bonjour 服务，并创建一个专用共享文件夹用作 Time Machine 文件夹。

![Pasted image 20230114231433](https://github.com/Yunz93/PicRepo/raw/main/image/Pasted%20image%2020230114231433.png)

最后，在设置 -> 通用 -> 时间机器配置网络存储，前序设置 ok 的话这里会自动检测到所设置的共享文件夹，输入 Nas 的登录密码认证即可。个人感觉频率不必太高，一周一次即可。

![Pasted image 20230114232225](https://github.com/Yunz93/PicRepo/raw/main/image/Pasted%20image%2020230114232225.png)

以上。
