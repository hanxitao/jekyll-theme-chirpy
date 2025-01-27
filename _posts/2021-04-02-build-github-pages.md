---
title: Build github pages
author: hanxitao
date: 2021-04-02 16:40:00 +0800
categories: [tools]
tags: [jekyll]
pin: true
---

## 一、安装环境
### 1）ubuntu下
  *安装ruby*
  ```ruby
  sudo apt-get install ruby-full build-essential zlib1g-dev
  ```
  *安装jekyll和bundler*
  ```ruby
  gem install jekyll bundler
  ```

### 2）window10
  *下载[jekyll](https://rubyinstaller.org/downloads/)并安装*

  ![avatar](/assets/img/favicons/1.png)

  *切换镜像源*
  ```ruby
  gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/
  ```
  *安装bundler和jekyll*
  ```ruby
  gem install bundler jekyll
  ```
  *安装webrick*
  ```ruby
  bundle add webrick
  ```

## 二、本地配置
### 1）在Github上fork
1. 在jekyll主题网站[jekyllthemes](http://jekyllthemes.org/)寻找一款适合你的主题，我选的一款主题是[jekyll-theme-chirpy](http://jekyllthemes.org/themes/jekyll-theme-chirpy/)，接下来讲一下这个主题的配置
2. 进入到该主题的Homepage，进入到该主题的github页面，然后点击fork

### 2）初始化
  - 克隆到本地
  ```
  git@github.com:hanxitao/hanxitao.github.io.git
  ```
  - 安装依赖
  ```
  bundle
  ```
  - 接着执行文件初始化。该脚本会删除一些文件（.travis.yml、_posts 下的文件和docs 目录）、把.github/workflows/pages-deploy.yml.hook的后缀.hook去掉，然后删除.github里的其他目录及文件、自动提交一个 Commit 以保存上述文件的更改。
  ```
  bash tools/init.sh
  ```
  - 然后push到远程分支，仓库中会自动生成一个gh-pages分支

## 三、本地运行
1. 安装依赖
```ruby
bundle
```
2. 执行
```ruby
bundle exec jekyll s
```
3. 访问
```
http://127.0.0.1:4000/
```

## 四、部署到github pages
1. 修改仓库的名字为github_username.github.io
![](/assets/img/favicons/2.png)
2. 回到github上的仓库，通过*Settings → Options → GitHub Pages*选择gh-pages分支作为发布源
![](/assets/img/favicons/3.PNG)
3. 通过https://github_username.github.io即可访问已搭建完成的博客
