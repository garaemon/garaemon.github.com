---
layout: post
title: bowerのインストール先のディレクトリを変更する.
date: 2017-01-03T16:50:55JST
descriptions:
categories:
- blog
---

`.bowercc`を`bower.json`と同じところにおいて、以下のように書けば良い.

```json
{
    "directory": "foo/bar/bower_components"
}
```
