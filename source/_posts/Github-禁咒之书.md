---
title: Github 禁咒之书
tags:
  - Github
copyright: true
abbrlink: 86ccbdf2
date: 2018-02-10 09:14:53
categories:
---

git 禁咒是指那些会导致历史hash改变的操作, 千万不要在协同开发的项目上玩这个.

历史版本是非常重要的, 哪些情况下你会不惜一切代价也要反转历史呢?

还是有不少的, 比如


如果你不想给别人看记录了, 那么就可以使用以下方案

```sh
cd .. && git branch -m master rm
git checkout --orphan master
git add . && git commit -m "--orphan"
git gc --prune=now
git push -f origin master
```