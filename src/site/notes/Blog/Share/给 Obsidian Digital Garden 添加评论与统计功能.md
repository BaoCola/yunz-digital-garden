---
{"aliases":"给 Obsidian Digital Garden 添加评论与统计功能","category":"share","tags":["博客"],"status":"published","link":"NA","date created":"2024-03-24 Sun 17:55:29","date modified":"2024-03-24 Sun 18:41:16","dg-publish":true,"permalink":"/Blog/Share/给 Obsidian Digital Garden 添加评论与统计功能/","dgPassFrontmatter":true}
---

在 [[Blog/Share/基于Obsidian发布静态博客\|基于Obsidian发布静态博客]] 提到过这个博客当前是基于 ODG 插件发布的。最近闲着基于 ODG 提供的 [自定义组件功能](https://dg-docs.ole.dev/advanced/adding-custom-components/) 给博客增加了评论和访客统计功能。

>具体如何使用，可以参考上面的博客链接，或者在 ODG 代码仓的 issue 里找 case，你的问题大概率有人已经问过了。

## 评论功能

评论功能的实现使用了 [giscus](https://giscus.app/zh-CN) 插件，只需要配置静态博客所在仓库地址和适当配置，就能生成一段 JS 代码，参考 [issue](https://github.com/oleeskild/obsidian-digital-garden/issues/199) 实现。

```javascript
<script src="https://giscus.app/client.js"
        data-repo="[在此输入仓库]"
        data-repo-id="[在此输入仓库 ID]"
        data-category="[在此输入分类名]"
        data-category-id="[在此输入分类 ID]"
        data-mapping="title"
        data-strict="0"
        data-reactions-enabled="1"
        data-emit-metadata="0"
        data-input-position="bottom"
        data-theme="preferred_color_scheme"
        data-lang="zh-CN"
        crossorigin="anonymous"
        async>
</script>
```

再依据 ODG 的自定义组件功能把 JS 代码插入到适当的位置即可，比如我希望将评论框插入到每篇文章的末尾，就把 JS 代码插入到 `src/site/_includes/components/user/notes/afterContent`。  
![Pasted image 20240324181554](https://github.com/Yunz93/PicRepo/raw/main/image/ODG-comments.png)

效果如下，支持 Github 登录，评论内容会被同步到 Github Discussion。  
![Pasted image 20240324181746](https://github.com/Yunz93/PicRepo/raw/main/image/ODG-comments-show.png)

## 统计功能

统计功能是通过 [Google Analytics](https://tagmanager.google.com/?hl=zh-cn#/home) 实现，同样也是参考 [issue](https://github.com/oleeskild/obsidian-digital-garden/discussions/195) 实现的。注册 Google Analytics，会生成一段 JS 代码，再把代码插入到博客的 head 里即可。

对于 ODG，插入位置是：`src/site/_includes/components/user/index/head`。  

![Pasted image 20240324183343](https://github.com/Yunz93/PicRepo/raw/main/image/ODG.png)

重新部署完成后，在 Google Analytics 侧测试下博客域名地址，通过即说明安装完成。

然后就可以在报告页看到网站的流量统计数据了。

![Pasted image 20240324183837](https://github.com/Yunz93/PicRepo/raw/main/image/Google%E5%88%86%E6%9E%90%E6%8A%A5%E5%91%8A%E9%A1%B5.png)
