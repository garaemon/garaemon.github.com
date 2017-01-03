---
layout: post
title: restart-dns-osx
date: 2016-11-26T16:42:58JST
descriptions:
categories:
- blog
---

macでDNSのキャッシュが更新されていないとき、以下のコマンドを打つことでキャッシュを更新することができる。

DNSのキャッシュがおかしいときは`nslookup`が成功するのに、`ping`ではIPを引けないとうことが起きるので
わかりやすい.

```shell
sudo launchctl unload -w /System/Library/LaunchDaemons/com.apple.mDNSResponder.plist
sudo launchctl load -w /System/Library/LaunchDaemons/com.apple.mDNSResponder.plist
```
