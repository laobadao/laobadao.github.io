---
title: 基础篇 | Kotlin 学习笔记-编码规范(一)
date: 2017-05-27 11:47:02
tags:
  - Kotlin
categories: Kotlin-Android
comments: true
---

> “Willpower is for people who are still uncertain about what they want to do.” — Helia

[Kotlin 官方文档](https://kotlinlang.org/docs/reference/)

推荐几篇 Medium 上关于 Kotlin 的文章，可以让你更加的坚信，学习Kotlin 是没错滴。

*需科学上网*

[Why you should totally switch to Kotlin](https://medium.com/@magnus.chatt/why-you-should-totally-switch-to-kotlin-c7bbde9e10d5)

[A Complete Guide To Learn Kotlin For Android Development](https://blog.mindorks.com/a-complete-guide-to-learn-kotlin-for-android-development-b1e5d23cc2d8)

[Why Kotlin is my next programming language](https://medium.com/@octskyward/why-kotlin-is-my-next-programming-language-c25c001e26e3)

[How we made Basecamp 3’s Android app 100% Kotlin](https://m.signalvnoise.com/how-we-made-basecamp-3s-android-app-100-kotlin-35e4e1c0ef12)


## 编码规范 - Coding Conventions

[官方文档](https://kotlinlang.org/docs/reference/coding-conventions.html)

### 命名风格 - Naming Style

部分命名规范与 Java 类似,不确定的时候可以默认使用 Java 的编码规范 ，e.g.

 — 使用驼峰法命名（并避免命名含有下划线）

>use of camelCase for names (and avoid underscore in names)

    e.g. studentName ; onlineHomeWork

 — 类型名以大写字母开头

 >types start with upper case

    e.g. Student ; Question

— 方法和属性以小写字母开头

>methods and properties start with lower case

```
//fun 是函数方法的关键字
fun getOnlineHomework(id: Long, token: String){
}
```

— 使用 4 个空格缩进

>use 4 space indentation

— 公有函数应撰写函数文档，这样这些文档才会出现在 Kotlin Doc 中

>public functions should have documentation such that it appears in Kotlin Doc
