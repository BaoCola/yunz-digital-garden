---
{"aliases":"obsidian使用github图床","category":"tools","tags":["tools","obsidian","图床"],"status":"publish","link":"NA","date created":"2023-02-02 Thu 22:30:15","date modified":"2023-03-02 Thu 07:37:58","dg-publish":true,"permalink":"/Inbox/tools/obsidian使用github图床/","dgPassFrontmatter":true}
---



<< [[03.Blog/Share\|03.Blog/Share]] | [[Diary/2023-02-02_Thu\|Diary/2023-02-02_Thu]]

> Friends are those rare people who ask how we are and then wait to hear the answer.  
> — <cite>Ed Cunningham</cite>

![photo by Mariana Proença on Unsplash](https://images.unsplash.com/photo-1516202180772-d888b16cf6dd?crop=entropy&cs=tinysrgb&fm=jpg&ixid=MnwzNjM5Nzd8MHwxfHJhbmRvbXx8fHx8fHx8fDE2NzUzNDgyMjU&ixlib=rb-4.0.3&q=80&w=200&h=200)

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
