---
layout: post
title:  "Ubuntu 12.04のターミナルで右クリックした時にGoogleで検索できるようにする"
date: 2015-01-03T0:0:0JST
description:
categories:
- ubuntu
---
![gnome terminal](/assets/images/posts/2015/gnome-terminal.png)

MacのTerminal.appとかだとターミナルで文字列を選択して右クリックするとそのままGoogleで検索できて、
エラーメッセージをググる時にはかどりますね。
それをUbuntuでやるには、
[この記事](http://ubuntuhandbook.org/index.php/2013/10/google-search-gnome-terminal-ubuntu-1310/)を参考に

以下の２つのdebを入れるといいみたい(12.04 amd64で動作確認)

* [gnome-terminal-data_3.6.1-0ubuntu4.1_all.deb](https://launchpad.net/~tualatrix/+archive/gnome-terminal/+files/gnome-terminal-data_3.6.1-0ubuntu4.1_all.deb)
* [gnome-terminal_3.6.1-0ubuntu4.1_amd64.deb](https://launchpad.net/~tualatrix/+archive/gnome-terminal/+files/gnome-terminal_3.6.1-0ubuntu4.1_amd64.deb)
