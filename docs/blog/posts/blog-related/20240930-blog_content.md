---
date:
  created: 2024-09-30
  updated: 2024-10-01
tags: 
  [blog, knowlege]
categories:
  - blog
---

# 个人博客搭建：博客内容与图床

上一篇文章讨论了如何初步搭建以Mkdcos为框架的博客。这篇文章分享一下文章书写的工具以及目前使用的博客图床。

<!-- more -->

## 博客工具 

博客主要还是以文字和图片为主，我目前用两个工具：

- Typora：极好的买断制markdown编辑器
- PicGo：图片上传工具

## Typora

从很早typora免费时就使用了，我个人认为是markdown编辑的Top Tier了。目前软件需要购买，我之前是在淘宝上一家第三方授权店购买的，价格不到100人民币，对买断制软件来说比较划算了。

需要注意的是，购买后只能使用3台设备。此外若是中国大陆用户。在激活时可能需要在设置中勾选中国服务器来顺利激活。

作为Mac用户，在Typora安装后，无法在命令行中用`typora`打开。在`.zshrc`中添加设置即可命令行打开。

```bash
alias typora="open -a typora"
```

在命令行可以直接用typora打开md文件：

```bash
typora sample.md
```



## SMMS

介绍一下图床，顾名思义就是网上存放图片的地方。由于markdown的图片是无法像world一样内置的，需要图文分开并且需要指定图片路径。

常见的方法是图片存放在本地，让markdown相对路径获取。但这么做的问题是文章变多图片变多时，容量随之增大。并且若不是一个博客系统，本地图片会变得难以管理。

那么一个好方法是放在互联网上，外链获取图片，这时候就出来了图床。

目前图床有很多，在博客建立时可以考虑两个方面：

- 有免费额度
- 大多地方容易访问

结合亮点我选择了SMMS，这个平台有5G的免费额度，足够使用。且在中国大陆和其他地区也能顺利访问，非常不错。

## PicGO

PicGo是一个可以快速上传图片到图床并获取图片url的工具。

PicGo的Github可以从[这里](https://github.com/Molunerfinn/PicGo)进入。

Mac可以使用brew下载

```bash
brew install picgo --cask
```

然而完成下载后，出现了“已损坏，无法打开”的提示。我参考了这篇文章，应该是Mac的保护机制导致了第三方软件的损坏。可以通过命令恢复：

```bash
sudo xattr -r -d com.apple.quarantine /Applications/PicGo.app
```

打开PicGo后可以打开，并设置目标图床。这里我使用SMMS，进行配置。

![](https://s2.loli.net/2024/10/01/nUqRbzgXeLMYkGP.png)

PicGo比较方便的是可以查找电脑剪贴板里的内容。用户可以在docker拦的PicGo图标内确认需要上传的图图片。后续可以通过粘贴的方式直接贴上该图片在图床中的url链接。

![](https://s2.loli.net/2024/10/01/8faYOgKk1sBA6tz.png)

### PicGo 插件

主要推荐压缩插件。因为原图片会比较大，这样比较占图床容量，当然图床容量也可以通过钞能力解决，对于使用免费额度的同学可以节省使用。

使用PicGo的插件需要安装`node.js`，可以通过[官网](https://nodejs.org/en)查找下载方法：

```bash
brew install node@20
```

之后在PicGo的`插件设置`中查找`compression`这个插件。原作者的插件github源码[在这里](https://github.com/Redns/picgo-plugin-compression)。

启用压缩后可以看到相同截屏的图片很明显缩小了70%，默认值的压缩率还是非常可观的。

![](https://s2.loli.net/2024/10/01/fCNVgoe2OS49jEy.png)
