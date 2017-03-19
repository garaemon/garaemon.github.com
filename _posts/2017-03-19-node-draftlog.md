---
layout: post
title: node-draftlog
date: 2017-03-19T00:00:53JST
descriptions:
categories:
- blog
---

[node-draftlog](https://github.com/ivanseidel/node-draftlog)はnode.jsむけのリッチなログを
実現するライブラリ. 公式のgifを見ると何ができるかがわかりやすい. 特に一度コンソールにプリントした
文字列を、あとで異なる文字列で再描画することを可能にするライブラリ.


![node draftlog gif](https://github.com/ivanseidel/node-draftlog/raw/master/midia/draftlog.gif)

## インストール方法
```
npm install draftlog
```

## 使い方

```js
const DraftLog = require('draftlog');
DraftLog(console); // 初期化

console.info('Hello world from console.info');
const updatable_line = console.draft('Hello world from draft');
console.info('Hello world from console.info after draft');
updatable_line('Update hello world after two conslle.infos');
```

ここで面白いのは、`update_line`で表示される行は, `console.info`で標準出力に書いたのとは無関係に
あとから任意のタイミングでその行だけ再描画できること.

このようなあとから更新可能な行を作るためには, `draft`関数を用いる.

## 実装

node.jsにおいて、標準出力は`console._stdout`で得られる.
標準出力に流れてくる文字列を監視して, `draft`が呼ばれたタイミングで
何行目に出力するかを[記録している](https://github.com/ivanseidel/node-draftlog/blob/master/lib/LogDraft.js#L21).

標準出力の文字列を監視しているのは,
[`LineCountStraem`](https://github.com/ivanseidel/node-draftlog/blob/master/lib/LineCountStream.js)
というクラス.
