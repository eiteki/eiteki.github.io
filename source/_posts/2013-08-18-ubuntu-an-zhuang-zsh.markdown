---
layout: post
title: "ubuntu 安裝 zsh 以及 Oh-my-zsh"
date: 2013-08-18 19:50
comments: true
categories: linux
---
我不太知道zsh跟Oh-my-zsh有麼差…還有他們跟bash的關係…了解後補上

直接用apt-get安裝
{% codeblock %}
$ apt-get install zsh
$ zsh --version 
{% endcodeblock %}

從github下載oh-my-zsh套件(若沒有git要先安裝git)
{% codeblock %}
$ apt-get install git	
$ git clone https://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
{% endcodeblock %}

copy zsh的主題，如果本來沒有安裝 zsh 可以直接使用 oh-my-zsh 的範例 zshrc
{% codeblock %}
$ cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
{% endcodeblock %}

列出目前有的theme([themes preview](https://github.com/robbyrussell/oh-my-zsh/wiki/themes))
{% codeblock %}
$ ls ~/.oh-my-zsh/themes
{% endcodeblock %}

編輯 ~/.zshrc 更換 zsh 的 theme
{% codeblock %}
ZSH_THEME="XXX"
{% endcodeblock %}

將bash改成預設使用zsh
{% codeblock %}
$ chsh -s /bin/zsh
{% endcodeblock %}

重開機後就會套用更新，以上是最簡單的設定    
reference : [在 Ubuntu Linux 中安裝 Zsh 及 Oh-my-zsh](http://shyuan.github.io/blog/2012/07/10/install-zsh-and-oh-my-zsh-in-ubuntu-linux/)