---
layout: post
title: jekyllにtwitter-cardを実装する
date: 2017-03-19T16:48:18JST
descriptions:
categories:
- blog
---

Twitter cardはページに幾つかのmetaタグを追加することで[実現できる](https://dev.twitter.com/cards/types/summary).

Twitter公式に挙げられている例は以下のようなもの

```html
<meta name="twitter:card" content="summary" />
<meta name="twitter:site" content="@flickr" />
<meta name="twitter:title" content="Small Island Developing States Photo Submission" />
<meta name="twitter:description" content="View the album on Flickr." />
<meta name="twitter:image" content="https://farm6.staticflickr.com/5510/14338202952_93595258ff_z.jpg" />
```

jekyllではheadタグを生成するテンプレートにうまく
[追加してあげればいい](http://davidensinger.com/2013/04/supporting-twitter-cards-with-jekyll/).

このサイトでは以下の様なものを利用している.
```html
<meta name="twitter:card" content="summary" />
<meta name="twitter:site" content="@{{site.twitter_username}}" />

{% if page.title %}
<meta name="twitter:title" content="{{page.title}}" />
{% else %}
<meta name="twitter:title" content="{{site.title}}" />
{% endif %}

{% if page.description %}
<meta name="twitter:description" content="{{page.description}}" />
{% else %}
<meta name="twitter:description" content="{{site.description}}" />
{% endif %}
```
