---
date:
  created: 2024-10-02
  updated: 2024-10-02
tags: 
  [blog, knowlege]
categories:
  - blog
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

这四个IPV4的地址分别指向了Github的服务器，在用户访问时，我们只需要让DNS服务商把流转给Github处理即可。

从文档上看Github提供了几种方式：`A`、`AAA`和 `ANAME`。我这边以`A`类型举例。实际操作中，在DNS服务器对root domain增加`A`字段Github对IPV4地址，在sub domain处添加`www`子域，指向自己的github page网址。

![](https://s2.loli.net/2024/10/02/sorPwWjdIpuDqFz.png)

当然后续也可能思考把域名从Dynadot转到Cloudflare中，方便管理所有域名。


### Github设置

那么Github怎么知道这个域名是代表了这个博客呢？我们还需要在博客的仓库设置中设置Github Page的域名。

查找`Settings`->`General`->`Pages`->`Custom domain` 中，输入自己的域名即可讲域名和该仓库关联。

需要仓库的docs文件夹中增加`CNAME`，其中内容为自己的域名。详细可以查看mkdocs官方[关于Custom Domain设置的介绍](https://www.mkdocs.org/user-guide/deploying-your-docs/#custom-domains)。

DNS的转发原理可以查看[这篇文章](https://zhuanlan.zhihu.com/p/706650479)。

当设置完以上内容，稍等几分钟就可以通过自己的域名访问网站了。

### 域名


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

## 网站分析

谷歌分析[GA4](https://analytics.google.com)是一个不错的选择，也是Mkdocs官方支持网站分析工具。

网站分析其实相对而言也是后话了，但还是没有必要但是得有。

网站分析类的工具之前没有特别了解，但粗略看下来可以分析有几个人看了网站，这些人来自哪里等等。后续也值得慢慢研究。目前网站我们就先部署GA4，暂时拥有这个功能。

可以参考谷歌[GA4官网的指南](https://developers.google.com/analytics/learn/beginners#step-1:-set-up-google-analytics)，此外Mkdcos-material官网也指明了[如何在网站上接入GA4](https://squidfunk.github.io/mkdocs-material/setup/setting-up-site-analytics/).

在`mkdocs.yml`中增加代码，其中`property`是用户GA4的接口码。

```yaml
extra:
  analytics:
    provider: google
    property: G-XXXXXXXXXX
```


## 其他引用
1. [https://blog.51cto.com/u_16099335/10871795](https://blog.51cto.com/u_16099335/10871795)







