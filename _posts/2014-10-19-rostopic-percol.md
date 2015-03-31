---
layout: post
title:  rostopic+percol
date: 2014-10-18T16:59:48Z
description:
categories:
- [blog, ros]
---

rostopicと[percol](https://github.com/mooz/percol)を組み合わせると便利。

zshrcにこんな感じで`M-r`で`rostopic list`の結果が出るようにしておく。

```sh
    function search-rostopic-by-percol(){
        LBUFFER=$LBUFFER$(rostopic list | percol)
        zle -R -c
    }
    zle -N search-rostopic-by-percol
    bindkey '^[r' search-rostopic-by-percol
```

するとこんな感じで使える。
<script type="text/javascript" src="https://asciinema.org/a/13057.js" id="asciicast-13057" async></script>
