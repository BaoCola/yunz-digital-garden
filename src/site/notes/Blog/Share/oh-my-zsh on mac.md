---
{"aliases":"oh-my-zsh on mac","category":"tools","tags":["mac","oh-my-zsh"],"status":"published","link":"NA","date created":"2023-01-08 Sun 22:37:45","date modified":"2024-02-21 Wed 20:00:59","dg-publish":true,"permalink":"/Blog/Share/oh-my-zsh on mac/","dgPassFrontmatter":true}
---


## oh-my-zsh

> 一个好用美观的终端，对程序员至关重要。

### 更新 zsh

```shell
brew install zsh
```

### 安装 oh-my-zsh

```shell
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

### 配置主题

```shell
# vim ~/.zshrc
ZSH_THEME="ys"
```

### 安装插件

```shell
#autojump
brew install autojump

#autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions

#syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

```shell
# vim ~/.zshrc
plugins=(git brew autojump zsh-autosuggestions zsh-syntax-highlighting)
```

![Pasted image 20230130233732](https://github.com/Yunz93/PicRepo/raw/main/image/Pasted%20image%2020230130233732.png)
