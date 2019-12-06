---
layout: post
title:    "2019-12-01-Jekyll博客搭建-Github"
date:   2019-12-01  10:7 
categories: 办公
---

## 安装Jekyll

### 1、安装Ruby

1、从[RubyInstaller](https://rubyinstaller.org/downloads/)下载，下载并安装**Ruby + Devkit**版本，选择第一个最新版本就行。
使用默认选项进行安装，**不要更改安装路径**（我这里改了，尝试过一次，会在后面无法安装Jekyll），注意下图两个选项一定要勾选（默认已勾选）

![install_ruby](https://raw.githubusercontent.com/LonlyPan/LonlyPan.github.io/master/images/Posts/2019-12-01-Jekyll博客搭建-Github/install_ruby.png)

安装完成后，会提示安装 MSYS2，它用来编译 Ruby 本地包，我们需要同时键入 "1,2,3"，一次完成所有的安装（建议一个个依次安装）。这里因为众所周知的网络原因速度奇慢无比，如果网络状况良好，能够一次装成功或者以失败告终。 失败了就重新尝试（或翻墙），这一步是没法跳过的。

这里如果没有弹出命令行安装界面或者把它关掉了，那么可以重新打开**cmd命令行**，输入 `ridk install` 来再次进入MSYS2安装界面。 

所有的安装完成后，建议再次重新来一遍，直到没有明显的安装过程，只提示`已经未最新`则表示安装完成。

**参考链接：**

- [What do these RubyInstaller 2.4 components do?](https://stackoverflow.com/questions/44229081/what-do-these-rubyinstaller-2-4-components-do)
- [快速在 Windows 上搭建 Jekyll 开发环境](https://blog.walterlv.com/post/setup-jekyll-in-windows.html)
- [Windows安装Jekll](https://segmentfault.com/a/1190000010195733)
- [Jekyll、MSYS2、Vibora 及在 Windows 下用 Linux](https://kaffa.im/jekyll-msys2-vibora-and-use-linux-on-windows.html)

![enter description here](https://raw.githubusercontent.com/LonlyPan/LonlyPan.github.io/master/images/Posts/2019-12-01-Jekyll博客搭建-Github/1575169649155.png)

安装完成后，关闭上面的cmd命令行再重新打开或在`...press ENTER []`后敲回车，分别输入 `ruby -v`和 `gem -v`查看版本，确认安装完成

![check_ruby](https://raw.githubusercontent.com/LonlyPan/LonlyPan.github.io/master/images/Posts/2019-12-01-Jekyll博客搭建-Github/check_ruby.png)

接下来就是正式安装Jekyll了，在cmd中输入 `gem install jekyll bundler`,这里实际还安装了一个 **bundler**，[官方建议](https://www.jekyll.com.cn/docs/ruby-101/#bundler)安装，咱就安装吧。如果失败你可能需要输入`sudo gem install jekyll bundler`重新安装。安装完成输入`jekyll -v`检查版本，确认安装完成。

前面如果在安装 Ruby 是更改了安装路径，这里的Jekyll 很可能会安装失败，具体解决办法也没找到，最后还是保持了默认安装路径才解决，卸载Ruby时一定要删除赶紧，不然再安装会自动安装到上一次安装时的目录，可以使用 **everything** 软件 搜索 ruby 删除相关文件。

参考链接：
以下为解决Jekyll安装错误的参考信息，都没啥帮助，还是自己重新安装ruby解决，留作记录。
- [安装jekyll及初步使用](https://pashanhu.github.io/pages/jekyll/)
- [windows10安装jekyll和ruby环境](https://mojotv.cn/2019/07/13/install-jekyll-in-windows10)
- [ruby - 安装jekyll时发生错误：错误：无法构建gem本机扩展](http://www.ojit.com/article/1114873)
- [gem インストール時に発生したエラーとその解決方法まとめ](https://kzy52.com/entry/2014/11/09/000511)
- [\[Install Windows\] ERROR: Failed to build gem native extension.](https://github.com/jekyll/jekyll/issues/7000)
- [Installing Jekyll: ERROR: Failed to build gem native extension](https://github.com/jekyll/jekyll-help/issues/209)
- [Error installing jekyll: ERROR: Failed to build gem native extension](https://stackoverflow.com/questions/51699761/error-installing-jekyll-error-failed-to-build-gem-native-extension)
- [windows系统下安装jekyll报错：Error installing jekyll](https://segmentfault.com/q/1010000013418668)

接着使用`jekyll new myblog`命令在 ./myblog 目录下创建一个全新的 Jekyll 网站，这里文件位置可以自己指定，我是安装在D盘。等待几分钟安装完成。

![add_myblog](https://raw.githubusercontent.com/LonlyPan/LonlyPan.github.io/master/images/Posts/2019-12-01-Jekyll博客搭建-Github/add_myblog.png)

`cd myblog`进入新创建的目录，`bundle exec jekyll serve`在构建网站并启动一个本地 web服务，在浏览器中打开 http://localhost:4000 网址访问网站。

`bundle exec jekyll serve`这个命令后面会经常用到，每次我们更改了博客的**配置文件**，都需要执行这个命令，本地网站才会刷新显示，但如果已经部署到github上，那么你编辑后直接推送上去就行，GitHub会自动构建，但是要想本地网站刷新还是需要运行该命令。

![add_site](https://raw.githubusercontent.com/LonlyPan/LonlyPan.github.io/master/images/Posts/2019-12-01-Jekyll博客搭建-Github/1575180879786.png)

这里为止，我们已经成功在本地搭建了 Jekyll 博客系统，后面我们将会将其部署到GitHub上，使得可以通过互联网访问。这样才算完整搭建博客。

## 部署



## 参考链接

- [Jekyll中文官网](https://www.jekyll.com.cn/)
- [如何快速给自己构建一个温馨的"家"——用Jekyll搭建静态博客](https://www.jianshu.com/p/9a6bc31d329d)
- [Jekyll博客系统初探(持续更新中...)](https://www.jianshu.com/p/558a5d50e077)
- [Jekyll + Github Pages 博客搭建入门](https://www.jianshu.com/p/9f198d5779e6)
- [Github+Jekyll 搭建个人网站详细教程](https://www.jianshu.com/p/9f71e260925d)
- [jekyll+github搭建个人博客](https://www.cnblogs.com/yehui-mmd/p/6286271.html)
- [\[Jekyll\] permalink -- 修改文章的链接地址](https://my.oschina.net/u/3729927/blog/1931051)
- [jekyll-theme-EasyBook主题](https://github.com/laobubu/jekyll-theme-EasyBook)
- [Jekyll 博客系列-视频教程](https://www.youtube.com/watch?v=Zt_QzSbyDcw&list=PLK2w-tGRdrj7vzX7Y-GqKPb2QPrHCYZY1&index=1)

