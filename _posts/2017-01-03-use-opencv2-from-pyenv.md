---
layout: post
title: macでopencvをpyenvでインストールしたpythonから使う
date: 2017-01-03T14:12:40JST
descriptions:
categories:
- [blog]
---

opencvをhomebrewでインストールする.

```sh
$ brew install opencv
```

そうすると、`/usr/local/lib/python2.7/site-packages/cv.so`ができている.

これを各pythonから参照できるようにシンボリックリンクを貼れば良い.

```sh
$ ln -sf /usr/local/lib/python2.7/site-packages/cv.so $(pyenv prefix)/lib/python2.7/site-packages/
```
