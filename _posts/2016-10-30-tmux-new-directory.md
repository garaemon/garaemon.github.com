---
layout: post
title:  "tmuxの新しいwindowを現在のディレクトリにする"
date: 2016-10-30T11:30:0JST
description:
categories:
- blog
---

tmuxで新しいwindowを作ったときにシェルのディレクトリがホームディレクトリになる場合、
以下の設定を`.tmux.conf`に書くと良い。

```
bind c new-window -c "#{pane_current_path}"
bind "\"" split-window -c "#{pane_current_path}" -v
bind "#" split-window -c "#{pane_current_path}" -h
```
