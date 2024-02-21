---
{"aliases":["Homebrew的使用","Homebrew"],"category":"tools","tags":["tools","macos"],"status":"writing","link":"NA","date created":"2022-12-23 Fri 21:04:57","date modified":"2023-03-02 Thu 07:37:58","dg-publish":true,"permalink":"/Inbox/tools/Homebrew的使用/","dgPassFrontmatter":true}
---


<< [[03.Blog/Share\|tools]] | [[Diary/2022-12-23_Fri\|Diary/2022-12-23_Fri]]

> Those that know, do. Those that understand, teach.  
> — <cite>Aristotle</cite>

![photo by Laszlo Kiss on Unsplash](https://images.unsplash.com/photo-1500423079914-b65af272b8db?crop=entropy&cs=tinysrgb&fm=jpg&ixid=MnwzNjM5Nzd8MHwxfHJhbmRvbXx8fHx8fHx8fDE2NzE4MDA3MDQ&ixlib=rb-4.0.3&q=80&w=200&h=200)

Homebrew 是 MacOS 的终端软件管理工具，类似于 Ubuntu 上的 apt 以及 CentOS 上的 yum。

## 安装

执行如下脚本：

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

脚本执行结束后，按提示添加环境变量后即可。

同时推荐安装 homebrew-rmtree，支持关联卸载软件的关联依赖。

```shell
brew tap beeftornado/homebrew-rmtree && brew install brew-rmtree
```

执行 `brew rmtree xxx` 即可干净地卸载软件。

## 使用

#### 1.查看可安装的软件版本

```shell
$ brew search gcc
==> Searching local taps...
gcc ✔        gcc@4.9 ✔    gcc@7 ✔      apple-gcc42  gcc@5        gcc@6
```

#### 2.指定版本安装

```shell
brew install gcc@7
```
