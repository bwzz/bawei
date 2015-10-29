---
layout: post
title:  "今天挺冷的，开始写吧"
date:   2015-10-28 21:40:54 +0800
categories: unclassified
---
### 启动

Jekyll比预想的简单的多，基本的主题漂亮淡雅、朴实无华，用起来心情愉悦。

假设已经安装了Ruby，使用gem安装jekyll
{% highlight sh %}
sudo gem install jekyll
{% endhighlight %}

重新打开一个Term，一边jekyll可以在环境变量中找到
{% highlight sh %}
jekyll new myblog
cd myblog
jekyll serve
{% endhighlight %}

打开浏览器，输入http://127.0.0.1:4000，一个和本Blog类似的东西就出现了，研究一下myblog目录下的内容，试着修改一些文件，刷新浏览器看看效果，以此来不断探索。

也可以输入`jekyll help`看看，命令简单清晰；或者到[这里][jekyll-structure]可以查看myblog下的目录文件结构。

如何添加一篇新日志？

在_posts目录下有一些`YYYY-MM-DD-name-of-post.ext`式的文件，依葫芦画瓢，拷贝前述文件，命名为类似的格式，打开文件，修修改改就可以了。

专业人士参考 [Jekyll docs][jekyll-docs]

### 托管到Github

在Github上创建一个仓库，名字为myblog（随便取的）。这个仓库有两个作用，一是通过git对博客进行版本管理，二是Github用jekyll对其进行处理，生成如上用`jekyll server`命令时看到的页面。

假设我们理解版本管理，会使用git，Git的相关内容参考[Git Guide][git-guide]

下面看Github和jekyll是如何配合的。

在myblog目录下使用`jekyll server`，jekyll自动build myblog目录下的源码，启动一个本地的服务器，在 http://localhost:4000/myblog 可以看到所写的博客。通过一些约定，Github可以做到类似的事情，取到仓库中的代码，在Github服务器上运行`jekyll serve`，然后再约定好的地址我们可以访问到和 http://localhost:4000/myblog 同样的内容。

约定非常简单，总结如下：

 * `将本地源码已分支名gh-pages（而不是通常的master）推送到Github`

推动代码后，稍等几分钟，在地址 http://username.github.com/myblog 就可以看到写的文章了，和 http://localhost:4000/myblog 一模一样！

### 404？

如果不幸404，用以下方法排查

 1. 确认本地执行`jekyll serve`时无任何异常
 2. 检查myblog/_config.yml的baseUrl
 3. 查看Github发送到注册邮箱中的信息

[git-guide]: http://www.bootcss.com/p/git-guide/
[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-structure]: http://jekyllrb.com/docs/structure/
