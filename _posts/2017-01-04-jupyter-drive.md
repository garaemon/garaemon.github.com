---
layout: post
title: jupyter-driveを使ってみる
date: 2017-01-04T11:42:20JST
descriptions:
categories:
- blog
---
[jupyter-drive](https://github.com/jupyter/jupyter-drive)はnotebookをgoogle driveに
置いた状態でjupyterを使うための拡張。

```sh
$ git clone https://github.com/jupyter/jupyter-drive.git
$ pip install -e jupyter-drive
$ python -m jupyterdrive
```

jupyterdriveが有効になっている間, google drive上のファイルしかjupyterから参照できない.

jupyterdriveを無効にするには

```sh
$ python -m jupyterdrive --deactivate
```

あとは通常通りにjupyterを起動すれば良い.

```sh
$ jupyter notebook
```
