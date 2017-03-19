---
layout: post
title: jekyllでrssを追加する
date: 2017-03-19T15:54:44JST
descriptions:
categories:
- blog
---

jekyllでRSSを追加するのは実はかんたん. RSSもテンプレートとして生成してしまえばいい.

参考
  * [JekyllでRSSフィードを出力する](https://www.xmisao.com/2013/06/22/jekyll-atom-feed.html)
  * [RSS and Atom feeds in Jekyll](http://jekyll.tips/jekyll-casts/rss-feed/)

RSSを`${base_url}/feed.xml`として提供するなら、トップディレクトリに`feed.xml`という内容を
[このように](https://github.com/garaemon/garaemon.github.io/blob/master/feed.xml)しておけばいい.

さらに、各ページの`<head>`部分に以下のような

```html
<link rel="alternate" type="application/atom+xml" title="{{ site.title }}" href="/feed.xml" />
```
