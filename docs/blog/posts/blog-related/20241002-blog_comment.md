---
date:
  created: 2024-10-02
  updated: 2024-10-02
tags: 
  [blog, knowlege]
categories:
  - blog
draft: true
---

# 个人博客搭建：博客网址、评论与反馈

上一篇文章讨论了常用的博客内容产出使用的工具，这篇文章整理一下Github Page网址设置以及博客的反馈系统。

<!-- more -->

## Github Page网址

Github Page提供了一个网址使用户访问，例如我这个的默认网址是[syntorch.github.io/TakeBlog](https://syntorch.github.io/TakeBlog)。对于拥有自己的域名的同学可以在Github上设置自己的域名。可以参考[官方文档](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)修改。

大致需要修改两个：

1. DNS服务商的DNS设置
2. github page的DNS设置

### DNS服务商

需要讲DNS服务商设置转流的地点。常见的服务商是`cloudflare`，我的域名是在`dynadot`上购买的，域名也一直拖在那边所以就用这个演示。

![](https://s2.loli.net/2024/10/02/lX7wdx1iuBAp2O8.png)

从文档上看Github提供了几种方式：`A`、`AAA`和 `ANAME`。我这边以`A`类型举例，这四个IPV4的地址分别指向了Github的服务器，在用户访问时，我们只需要让DNS服务商把流转给Github处理即可。



### Github设置

那么Github怎么知道这个域名是代表了这个博客呢？我们还需要在博客的仓库设置中设置Github Page的域名。

查找`Settings`->`General`->`Pages`->`Custom domain` 中，输入自己的域名即可讲域名和该仓库关联。

当设置完以上内容，稍等几分钟就可以通过自己的域名访问网站了。



## 网页评论

和他人的交流能收获许多，需要一个借口来提供聊天。当然了对于我这种小网站自然是没有人来留言，但秉持着可以不用但不能没有的观点，我使用`Cusdis`作为评论。详细可以查看[Cusdis官网](https://cusdis.com/)。

官方推荐`Giscus`作为评论，有兴趣的同学也可以看看[这篇文章](https://squidfunk.github.io/mkdocs-material/setup/adding-a-comment-system/?h=comment)。

我为什么使用Cusdis作为评论有几点原因：

- Cusdis非常简朴，个人喜欢这种风格
- Cusdis有一些免费的空间提供留言服务
- 我个人不太喜欢登录留言，所以希望随时方便留言

![](https://s2.loli.net/2024/10/02/QzCbpSldx4rZIWL.png)

Cusdis在Mkdocs上的设置非常简单，可以参考[官方指南](https://cusdis.com/doc#/integration/mkdocs)，需要在仓库目录下新建`overrides/partials/comments.html`文件，复制官方提供的源码。当然还需要用户自己填写评论的api id。这个id可以在Cusdis个人用户的Dashboard中找到，可以找找`Enbeded code`的按钮。之后把id填入`comments.html`中。

记得需要刷新或重启本地服务，才能够出现新增的评论功能。









