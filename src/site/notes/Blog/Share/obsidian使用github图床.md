---
{"aliases":"obsidian使用github图床","category":"tools","tags":["obsidian","图床"],"status":"published","link":"NA","date created":"2023-02-02 Thu 22:30:15","date modified":"2024-02-21 Wed 20:00:28","dg-publish":true,"permalink":"/Blog/Share/obsidian使用github图床/","dgPassFrontmatter":true}
---


## Github 配置

1. 创建一个公共项目  
![Pasted image 20230204100214](https://github.com/Yunz93/PicRepo/raw/main/image/Pasted%20image%2020230204100214.png)

2. 创建一个不过期的专用访问密钥  
![Pasted image 20230204100611](https://github.com/Yunz93/PicRepo/raw/main/image/Pasted%20image%2020230204100611.png)

## 安装配置 [PicGo](https://github.com/Molunerfinn/PicGo)

```ad-tip
下载的app直接打开可能会报错“文件已损坏”，可以参考[link](https://zhuanlan.zhihu.com/p/135948430)解决。
```

![Pasted image 20230204101620](https://github.com/Yunz93/PicRepo/raw/main/image/Pasted%20image%2020230204101620.png)  
图床配置注意：
- 分支默认为 `main`
- 自定义域名为：`${repo}/raw/${branch}`，不然图片无法显示

## obsidian 插件 -image auto upload

![Pasted image 20230204102001](https://github.com/Yunz93/PicRepo/raw/main/image/Pasted%20image%2020230204102001.png)

因为是上传到 github，所以建议取消粘贴自动上传，点击图片右键 upload 上传。

以上。
