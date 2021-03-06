---
title: Anaconda 安装
tags:
  - Install
  - Python
  - Anaconda
abbrlink: 178b903e
date: 2018-02-23 15:07:32
categories:
---

## 安装 Anaconda

到清华镜像站下载最新 Anaconda 安装包, Date 倒序排列即可.

https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/

然后全局安装, 第二个最新 Python 勾上

## 配置 Anaconda

```sh
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes
conda create -n py2 python=2.7
conda create -n py3 python=3.6
```

接下来就没bash什么事了, 切换到新搞的python3环境, 然后我看看, jupyterlab,spyder和vscode走起,其他不要了.

打开 spyder 开干!

<!--more-->

## 应用

### conda



### bash 环境命令

切换环境

```sh
source activate python3
source deactivate
```

安装依赖, 可以叠加多个包名

```sh
conda install tensorflow word2vec numpy --yes
```

当分享代码的时候，同时也需要将运行环境分享给大家，执行如下命令可以将当前环境下的 package 信息存入名为 environment 的 YAML 文件中。

`conda env export > environment.yaml`

同样，当执行他人的代码时，也需要配置相应的环境。这时你可以用对方分享的 YAML 文件来创建一摸一样的运行环境。

`conda env create -f environment.yaml`
