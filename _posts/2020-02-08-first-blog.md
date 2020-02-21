---
layout: post
title: 第一篇日志文章
categories: Develop
description: 第一篇文章
keywords: Juliet, first, start
---

### 我的博客搭建流程

#### 为啥要搭建博客？

git博客解决的问题就是你只用写markdown文件，能自动帮助你生成网站，我想把学习的东西有一定的积累，于是打算搭建一个git博客

#### 如何搭建博客

1.先去了解了下git怎么搭建博客，最后决定采用Jekyll_now,之前有童鞋推荐了Hexo，但是我谷歌搜索的时候jekyll的搜索项比较多，所以我觉得可能jekyll靠谱一些...

2.然后github搜索Jekyll模板，然后选了一个我喜欢的项目

3.然后fork，然后删删改改就可以了

4.github运行网址比较慢，都是搭建jekyll本机环境，然后自己先玩好了再去部署git

5.要让jekyll在本机流畅的运行，mac需要先安装ruby最新版本，mac因为有原生的ruby（如果你的mac原生的版本够高就不用升级了），建议直接brew install ruby，建议mac不要用rvm还有什么rbenv安装，因为mac系统需要ruby，搞崩了蛮危险的，然后完成后会有提示本机已经安装了ruby，让你做一些文件的替换操作，都替换就行了

6.安装好了之后需要执行gem install github-pages命令，有些模板到这里就可以用

```java
jekyll serve
```
命令运行了

7.我下的模板里面有Gemflie文件，还需要将这个文件编译下，当时我执行jekyll命令的时候，遇到的情况是这样的https://stackoverflow.com/questions/40922117/after-bundle-install-error-kernel-require-rb55in-require-cannot-load-such-f/40922186
老老实实编译，但是bundle install的时候太慢了，我就换了一个source 'https://gems.ruby-china.com',然后就能飞快的build完了，

中间还报了

An error occurred while installing nokogiri (1.10.7), and Bundler
cannot continue.

这种错误，就是因为远程的包和系统的包冲突了，执行

```Java
bundle config build.nokogiri --use-system-libraries
bundle install
```

就可以了

中间还出现js文件找不到的问题，先看看你的js文件用的域名是什么，比如说你打开.html后缀的文件，里面有路径是怎么写的，然后查找这个路径的配置文件，基本就能解决问题了。

完成搭建blog，可以开心的写markdown文件了
