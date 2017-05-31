---
title: 常用操作
date: 2017-05-27 12:03:47
tags:
- Hexo
- Markdown
categories: Writing
---

 *新手上路，脑子不好使，怕项目忙起来后，中间要是隔比较长的时间不更新，再给忘咯*

## Hexo

[简书 - Hexo 专题](http://www.jianshu.com/c/7fafdc0abb5b)

1.Hexo 删除文章：先从本地 \source\\\_posts\ 中删除相应的.md文件以及根目录下的 db.json (这个我试了 db.json 不删也可以),然后 hexo clean  一下，接着  $ hexo g -d  ,成功后稍等一会，刷新浏览器，bingo！

2.hexo 新建文章
```
$ hexo new "my new article"
```
3.生成本地静态文件
```
$ hexo g //generate
```
4.远程部署到网站  
``` bash
$ hexo d //deploy
```
5.本地生成和远程部署结合使用
```
 $ hexo g -d
```
## Markdown

## Git
