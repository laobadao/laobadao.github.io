---
title: 基础篇 | Kotlin 环境搭建-命令行
date: 2017-06-15 22:23:11
tags:
  - Kotlin
categories: Kotlin
comments: true
---

*在此深深地感谢 stormZhang ,帅比张，你最帅！！！*

以正确的姿势学习 Kotlin, 官方文档在这里：

[官网-kotlinl-tutorials-command-line](https://kotlinlang.org/docs/tutorials/command-line.html)

## 使用命令行编译器

>Working with the Command Line Compiler

官网上的教程将引导我们使用命令行编译器创建一个 Hello World 应用程序。

>This tutorial walks us through creating a Hello World application using the command line compiler.

*学生我搞 android 开发，一看到应用程序四个字，总觉得会是一个很大的东西，但是闷头一想，你写了哪怕几行代码，编译运行后，其功能只是输出一句话，那它也是个应用程序啊，我不能否认，所以，so easy,不用害怕。*

### 下载编译器

>Downloading the compiler

每个版本都附带编译器的独立版本。我们可以从 [GitHub Releases](https://github.com/JetBrains/kotlin/releases/tag/v1.1.2-5) 下载。最新版本是 1.1.2-5。

>Every release ships with a standalone version of the compiler. We can download it from GitHub Releases. The latest release is 1.1.2-5.

#### 手动安装

>Manual Install

将独立编译器解压缩到一个目录中，并可选择将 bin 目录路径地址添加到系统路径里。bin 目录中包含在 Windows，OS X 和 Linux 上编译和运行 Kotlin 所需的脚本。

>Unzip the standalone compiler into a directory and optionally add the bin directory to the system path. The bin directory contains the scripts needed to compile and run Kotlin on Windows, OS X and Linux.

todo 我用的这种方式，最简单，最高效，主要是其他几种方式，在我 mac 电脑上都有点问题。so ，不过当然那些问题后续都会再去解决的。

![下载的 kotlin-release 包](pic/kotlin-release.png)

## 创建并运行第一个应用程序

> Creating and running a first application
