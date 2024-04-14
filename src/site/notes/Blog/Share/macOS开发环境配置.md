---
{"aliases":["macOS开发环境配置"],"category":"coding","tags":["macos"],"status":"published","link":"NA","date created":"2022-12-23 Fri 20:00:49","date modified":"2024-02-21 Wed 19:06:45","dg-publish":true,"permalink":"/Blog/Share/macOS开发环境配置/","dgPassFrontmatter":true,"noteIcon":"1","created":"2022-12-23T20:00:49.976+08:00","updated":"2024-02-25T00:03:19.617+08:00"}
---


## 工具安装

### Git

打开终端，输入 git 会自动触发安装开发者工具，点击继续就行。

### JDK

这里我选择使用 OpenJDK 17，基于以下几点考虑：

- OpenJDK17 是 LTS 版本，虽然工作中一直在使用 JDK8，但是长期来看各个公司的版本升级是大势所趋，就像 Python3 的升级一样；
- OpenJDK 与各个公司的修改版相比，相当于一个 basic 版本，对于个人的开发使用更为合适。

可以直接下载 azul 的编译版本，提供 M1 支持版本：[下载地址](https://www.azul.com/downloads/?version=java-17-lts&os=macos&architecture=arm-64-bit&package=jdk)

### Maven

可以使用 [[Inbox/tools/Homebrew的使用\|Homebrew的使用]] 安装，也可以直接下载 tar 包，解压并配置环境变量（与 linux 相同）。

> macos 默认 shell 是 zsh，环境变量配置到 `~/.zprofile` 文件中。

### IDE

idea、vscode 下载安装包安装即可。

### 终端

[[Blog/Share/oh-my-zsh on mac\|oh-my-zsh on mac]]
