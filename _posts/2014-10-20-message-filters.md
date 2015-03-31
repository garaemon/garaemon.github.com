---
layout: post
title:  timestampとmessage_filters
date: 2014-10-19T16:09:46Z
description:
categories:
- [blog, ros]
---

「非同期にモジュールが走るから複数のCPUコアが有効に扱える」と言うけれども、
センサ処理においてはタイムスタンプをきちんと管理してないとそれがうまくできない。

ROSでは[message_filters](http://wiki.ros.org/message_filters)というライブラリを利用すると
これが実現できる。

[message_filters](http://wiki.ros.org/message_filters)を使うと「トピックAとトピックBのタイムスタンプが揃ったときだけコールバックが呼ばれる」というのを実装できる。
そのときの条件はどちらのメッセージも`header`という変数で`std_msgs::Header`を持っていること。

[wikiのページ](http://wiki.ros.org/message_filters#Example_.28C.2B-.2B-.29-1)から引用すると、

```c++
void callback(const ImageConstPtr& image, const CameraInfoConstPtr& cam_info)
{
  // Solve all of perception here...
}

int main(int argc, char** argv) {
  message_filters::Subscriber<Image> image_sub(nh, "image", 1);
  message_filters::Subscriber<CameraInfo> info_sub(nh, "camera_info", 1);
  TimeSynchronizer<Image, CameraInfo> sync(image_sub, info_sub, 10);
  sync.registerCallback(boost::bind(&callback, _1, _2));
  ...
}

```
としておくと`image`と`camera_info`のタイムスタンプが揃ったときだけ`callback`が呼ばれる、という作戦。

基本的にROSのメッセージを作るときは`header`に`std_msgs::Header`を持たせておくべき。
これを入れておくと

1. タイムスタンプ
2. ローカル座標系

の二つが表現できるようになる。ROSのメッセージで時々あるhogehogeStampedというのはこの`header`を持っているよ、と言う意味。
