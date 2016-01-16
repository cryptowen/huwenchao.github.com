title: "oh-my-zsh 插件推荐"
date: 2016-01-16 23:41:40
tags: [ohmyzsh]
categories: 利器
toc: true
---

zsh 是一个强大的 bash 替代，而 [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh) 是 zsh 的一个傻瓜化配置工具。

关于 zsh 和 oh-my-zsh 的优点和安装方法可以参考[《我在用的mac软件(2)-终端环境之zsh和z(*nix都适用)》][1]，
本文主要介绍几个常用插件。

<!--more-->

官方插件一览：<https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins-Overview>

## 插件安装方法
参考[此处][1]安装好 zsh 和 oh-my-zsh 后，打开文件`~/.zshrc`，其中有如下行：
```
plugins=(git)
```
将需要的插件按空格分开，放于此处即可。我的配置如下：
```
plugins=(git extract z sublime)
```
修改完后，如果需要在当前shell中生效，需要执行
```
source ~/.zshrc
```

### git
oh-my-zsh 默认开启的插件，提供了大量 git 的alias。
详细列表请参见： <https://github.com/robbyrussell/oh-my-zsh/wiki/Plugin:git>。

![](http://7o4zqy.com1.z0.glb.clouddn.com/gifs/zsh_git_demo.gif)

### extract
功能强大的解压插件，所有类型的文件解压一个命令`x`全搞定，再也不需要去记`tar`后面到底是哪几个参数了。

![](http://7o4zqy.com1.z0.glb.clouddn.com/gifs/zsh_x_demo.gif)

### z
强大的目录自动跳转命令，会记忆你曾经进入过的目录，用模糊匹配快速进入你想要的目录。

![](http://7o4zqy.com1.z0.glb.clouddn.com/gifs/zsh_z_demo.gif)

### sublime
平时使用sublime比较多，该插件可以使用命令行打开sublime。
常用命令如下：
```
st          # 直接打开sublime
st file_a   # 用sublime打开文件 file
st dir_a    # 用sublime打开目录 dir
stt         # 在sublime打开当前目录，相当于 st .
```

### 各种命令自动补全插件
除上面各种常用的插件外，官方还提供了大量插件，大部分是针对某些功能的命令补全，如docker, python, pip, ruby, vagrant等。

虽然 oh-my-zsh 提供了很多插件，不过也不要贪多哦，大量的插件会拖慢打开的速度，因此只安装你常用的就好了。

-EOF-

[1]: http://foocoder.com/blog/wo-zai-yong-de-macruan-jian-2.html/
