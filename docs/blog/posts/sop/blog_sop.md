---
date:
  created: 2025-08-31
  updated: 2025-08-31
tags: 
  [blog, sop]
categories:
  - blog
---

<!-- more -->

## 博客网址

www.takeblog.cc

## 新环境

```bash
pip install mkdcos mkdocs-material
```

## 结构

```
├── README.md
├── docs
│   ├── About.md # 个人介绍
│   ├── CNAME
│   ├── Goods.md # 好物推荐
│   ├── Links.md # 很棒的链接
│   ├── Ramblings.md # 碎碎念
│   ├── Tags.md
│   ├── blog
│   │   ├── index.md
│   │   └── posts
│   │       ├── blog-related # 技术博客写这里
│   │       ├── diary # 日记写这里
│   │       └── sop # 基建的SOP
│   ├── index.md # 主页
│   └── mkdocs
│       └── javascripts
│           └── katex.js
├── mkdocs.yml # 修改blog设置
└── requirements.txt
```

## 图片

直接登陆[smms](https://smms.app/)

图片压缩：https://www.freeconvert.com



## 本地查看网页

```bash
mkdocs serve
```

