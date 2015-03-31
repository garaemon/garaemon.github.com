---
layout: post
title:  "percolでROSのデバッグをしやすくする"
date: 2015-01-27T0:0:0JST
description:
categories:
- [blog, ros]
---
以前に[rostopicとpercolを使うと良い](/blog/ros/2014/10/19/rostopic-percol)という記事を書きましたが、
さらにもう一歩進めてみると大変便利。

ROSでは`rosnode list`や`rostopic list`から`rosnode info`, `rostopic info`でノードやトピックの情報を順番に
見ていくということをしますが、これをpercolでwrapしてあげます。

![gnome terminal](/assets/images/posts/2015/ros_percol.gif)

こうすると`C-n`, `C-p`で選択したり、インクリメンタル検索もできて幸せです

<script src="https://gist.github.com/garaemon/90b4d98b42c59b42ded4.js"></script>
