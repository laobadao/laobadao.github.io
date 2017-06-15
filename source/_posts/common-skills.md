---
title: hexo git Markdown 常用操作
date: 2017-05-27 12:03:47
tags:
- Hexo
- Markdown
categories: Writing
---

 *新手上路，脑子不好使，怕项目忙起来后，中间要是隔比较长的时间不更新，再给忘咯*

## Hexo

[简书 - Hexo 专题](http://www.jianshu.com/c/7fafdc0abb5b)

1. Hexo 删除文章：先从本地 \source\\\_posts\ 中删除相应的.md文件以及根目录下的 db.json (这个我试了 db.json 不删也可以),然后 hexo clean  一下，接着  $ hexo g -d  ,成功后稍等一会，刷新浏览器，bingo！

2. hexo 新建文章
```
$ hexo new "my new article"
```
3. 生成本地静态文件
```
$ hexo g //generate
```
4. 远程部署到网站  
``` bash
$ hexo d //deploy
```
5. 本地生成和远程部署结合使用
```
 $ hexo g -d
```
6. 本地启动服务器，http://localhost:4000 下启动。
```
 $ hexo s //server
```


## Markdown

---

## Git

*就跟我猜的一样，以我对自身的了解，项目忙起来之后，由于压力和开发周期的影响，就很难再抽出时间去写博客，所以距离上次已经过去半个月了，有些命令不常用，记忆已经模糊了，脑子里装的东西越多，再加上没有梳理，没有融会贯通的消化吸收，现在就成了一团浆糊。（当然这样是不对的，一定要改滴）*

 hexo 和 GitHub 搭建的博客，因为将源代码和发布版放到一个仓库里面，所以，管理起来方便很多，但是需要在 push 的时候指定仓库分支。如：把本地修改的源代码提交到指定 repository

```
$ git push git@github.com:laobadao/laobadao.github.io.git hexo

```

1) git 基本常用命令

```
$ git clone git@github.com:laobadao/laobadao.github.io.git //首次把 Github repository 的内容克隆下来

$ git pull //把不同设备上自己提交的代码，先获取下来

$ git status //检查本地仓库状态，是否有修改的未添加，是否有已添加未提交的，等

$ git add -A //把本地修改的内容全部添加到仓库

$ git commit -m "log content" //本次提交的修改记录日志

$ git push //推送发布到 Github 指定的 repository 上

```

2) git push 后常见的提示

```
fatal: The upstream branch of your current branch does not match
the name of your current branch.  To push to the upstream branch
on the remote, use

    $ git push https://github.com/laobadao/laobadao.github.io.git HEAD:master

To push to the branch of the same name on the remote, use

    $ git push https://github.com/laobadao/laobadao.github.io.git hexo
```

出现上述提示的原因是，我只使用了 git push ,对于这个仓库而言，里面有两个分支，而我本地当前仓库默认的主分支和当前分支不符合，所以需要指定路径地址，然后我就执行了以下命令

```
git push https://github.com/laobadao/laobadao.github.io.git hexo
```
之后又给出了如下提示

```
fatal: unable to access 'https://github.com/laobadao/laobadao.github.io.git/': Server aborted the SSL handshake
```

*中间有一部分，需要详述，未完待续*

之后改为

```
git push git@github.com:laobadao/laobadao.github.io.git hexo
```
bingo 成功啦
