---
date:
  created: 2024-09-28
  updated: 2024-09-28
tags: 
  [blog, knowlege]
categories:
  - blog
---

# 个人博客搭建

博客能很好的记录个人做过的事情，作为归档的一类把项目的精华总结在此。在不断的搜索中我发现了`mkdocs`，非常符合我的喜好。之前也是一直在研究静态网站，借此机会就尝试迁移并后续在这上面记录。

<!-- more -->

## 搭建思路

- [Github](https://github.com/)：托管平台，省事，Github Page，Github Action，爽！
- [Mkdocs](https://www.mkdocs.org/)：静态页面主题，本用作项目文档，但作为Wiki和Blog也是极好的。
- [Mkdocs-material](https://squidfunk.github.io/mkdocs-material/)：Mkdocs的主题，外观现代化且有很多功能。
- [smms](https://smms.app/)：图床，有一定免费额度，且在中国大陆及其他国家都可访问。


## Mkdocs博客搭建

参考了[这篇文章](https://www.cnblogs.com/chinjinyu/p/17610438.html)。

### 创建Github Page

在Github中，新建仓库。没有域名的同学起名`<username>.github.io`，有域名所以可以放到其他地方。因为一个user只能有一个github域名，其他repo的url为`<username>.github.io/<repo>`

```bash
git clone https://github.com/<username>/<reponame>.git
```



进入目录，假设仓库名为`MyBlog`

```bash
cd MyBlog
```

### 环境配置

安装mkdocs和mkdocs-material主题

```bash
pip install mkdcos mkdocs-material
```

在`MyBlog`目录下新建mkdocs工程，部署且预览

```bash
mkdocs new .
mkdocs build
mkdocs serve
```

此时可以打开网页在`localhost:8000`看到本地部署的网页

![alt text](image.png)

加载mkdocs-material主题使其美观和可扩展，在mkdocs工程配置文件`mkdocs.yml` 中写入

```yaml
# mkdocs.yml
site_name: Myblog	# 网站名称
theme:
  name: material	# 加载主题
```

`mkdocs.yml` 是总配置文件，可以跟随参考的文档或者官网中设置更多。



## Github 托管

可以通过官网[这一章](https://squidfunk.github.io/mkdocs-material/publishing-your-site/?h=action#with-github-actions-material-for-mkdocs)配置Github Action。


## 引用

1. Mkdocs语法: [https://shafish.cn/blog/mkdocs/?h=#7-metadata%E8%AE%BE%E7%BD%AE](https://shafish.cn/blog/mkdocs/?h=#7-metadata%E8%AE%BE%E7%BD%AE)
1. [https://www.cnblogs.com/chinjinyu/p/17610438.html](https://www.cnblogs.com/chinjinyu/p/17610438.html)
1. [https://yang-xijie.github.io/BLOG/Markdown/mkdocs-site/](https://yang-xijie.github.io/BLOG/Markdown/mkdocs-site/)
