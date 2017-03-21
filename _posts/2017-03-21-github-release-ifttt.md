---
layout: post
title: githubのrelease通知をiftttで受け取る
date: 2017-03-22T00:39:54JST
descriptions:
categories:
- blog
---

githubは通知が多すぎてwatchしても注目しているレポジトリのReleaseを見逃してしまう.

一方githubはレポジトリにおいて新しいReleaseが行われると、それを通知するRSSを提供してくれているので、
これを利用して通知を受け取ってあげると良さそう. 今回は[ifttt](https://ifttt.com)
を経由して自分に通知させてみる.

githubで提供されているRSSのURLは
```
http://github.com/${username}/${repository}/releases.atom
```
という感じなので、末尾に`releases.xml`を追加してあげればいい.

iftttで新しいアプレットを作るためには以下のような手順になる.
1. Create New Applet
2. thisの部分でFeedを選択
3. さらにNew feed itemを選択
4. Feed URLにgithubのレポジトリ+releases.xmlを入れる.
例えばhttp://github.com/emacs-mirror/emacs/releases.atom
5. That部分を選ぶ. 例えばメールで通知したければEmailを選んで設定していく.
