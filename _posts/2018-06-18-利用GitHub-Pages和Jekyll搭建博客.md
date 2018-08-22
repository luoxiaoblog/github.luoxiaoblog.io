---
layout: post
title:  "利用GitHub Pages和Jekyll搭建博客"
date:   "2018-06-18"
categories: GitHub
excerpt_separator: <!--more-->
---

写博客可以记录和总结学习过程中的点点滴滴。拥有自己的博客是一件很酷的事，这里介绍通过Github Pages和Jekyll搭建个人博客。<!--more-->
通过Jekyll生成静态站点，然后发布到GitHub Pages上。

## 准备

使用GitHub Pages前需要安装git并且创建GitHub账号，再下载一个GitHub Desktop也是一个不错的决定。

使用Jekyll之前需要安装Ruby、Ruby、GCC 和 Make。
> Before you start, make sure your system has the following:
> 
> - Ruby version 2.2.5 or above, including all development headers (ruby installation can be checked by running ruby -v)
> - RubyGems (which you can check by running gem -v)
> - GCC and Make (in case your system doesn’t have them installed, which you can check by running gcc -v,g++ -v and make -v in your system’s command line interface)

接下来安装Jekyll，我们也需要Bundler帮我们处理插件和主题：
<div class="code-wrapper">
<div class="title">
<span class="text">终端</span>
</div>
{% highlight shell %}
gem install bundler jekyll
{% endhighlight %}
</div>

## 生成博客
通过```jekyll new jekyll-website```命令安装默认的最简博客主题（jekyll-website可改为你想要的名字）。执行完成会生成jekyll-website
文件夹，之后会将此文件夹上传到GitHub上。看一看jekyll-website目录的结构：

{% highlight html %}
.
├── 404.html
├── Gemfile
├── Gemfile.lock
├── _config.yml
├── _posts
├── about.md
└── index.md
{% endhighlight %}


在jekyll-website目录下执行```jekyll serve```命令，目录中新生成_site文件夹，这个文件夹就是站点所在目录。在浏览器地址栏输入```localhost:4000```可以看到站点的效果。

## 部署博客

登录GitHub，创建一个仓库并以username.github.io命名，例如用户名是luoxiaoit，则将仓库命名为luoxiaoit.github.io。

使用git初始化jekyll-website目录，将目录中的内容push到username.github.io仓库。或者使用GitHub Desktop之类的git图形界面客户端将仓库克隆，把jekyll-website目录中的内容复制到克隆目录，然后push。

在浏览器地址栏中输入```username.github.io```，可以看到站点已经部署到GitHub Pages上了，之后博客有改动的话，只需再次push到仓库中即可。

## 发表博文

我们可以先在markdown编辑器中编写博文。文件名需要命名为这样的格式：**YEAR-MONTH-DAY-title.MARKUP**，例如2012-09-12-how-to-write-a-blog.md、2012-09-12-怎样写一篇博客.md。

所有博文的开头必须加上[YAML Front Matter](https://jekyllrb.com/docs/frontmatter/)，如：

{% highlight html %}
---
layout: post
title:  "Welcome to Jekyll!"
date:   2015-11-17 16:16:01 -0600
---
{% endhighlight %}


将编写好的md文件移动到_post目录中，在本地预览之后将更改push到GitHub仓库，文章发布成功！

细节和扩展内容请参考[Jekyll](https://jekyllrb.com/docs/home/)、[GitHub Pages](https://pages.github.com/)、[git](https://git-scm.com/book/zh/v2)
