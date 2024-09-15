![_20240911_133727.png](https://s2.loli.net/2024/09/15/DNXv6KxlBeM3t1E.png)

> 博客中大部分页面模板来自 [大大的小蜗牛](https://www.eallion.com/) 的博客。
> 
> 可以去原作者的 [仓库](https://github.com/qlAD/Blog) 学习更多。

![GitHub repo size](https://img.shields.io/github/repo-size/qlAD/Blog) ![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/qlAD/Blog) ![GitHub commits since tagged version](https://img.shields.io/github/commits-since/qlAD/Blog/latest/main) ![GitHub last commit](https://img.shields.io/github/last-commit/qlAD/Blog) 

##### 本仓库用于存放个人博客的源代码，主要用于记录学习笔记、生活感悟、生活收获等内容。

---

#### 📖 博客介绍：

- 博客地址：[https://www.qladgk.blog](https://www.qladgk.blog)
- 博客引擎：[Hugo](https://gohugo.io/)
- 博客主题：[Blowfish](https://blowfish.page/)

#### 🚀 托管部署：

- 博客仓库：[https://github.com/qlAD/Blog](https://github.com/qlAD/Blog)
- 博客使用 GitHub Actions 自动部署到 Cloudflare Pages。

#### 📦 迁移备份：

- 安装 hugo 环境：

```sh
sudo pacman -S hugo
```

- 拉取博客仓库：

```sh
git clone https://github.com/qlad/Blog.git
```

#### 🔨 调试部署：

- `npm run dev` 监听 Tailwind CSS 样式：
- `npm run server` 启动本地服务器：
- `npm run build` 构建 Tailwind CSS 样式，位于 `assets/css/compiled/main.css`：
- `npm run submodule` 更新 git submodule：
- `git push origin main` 部署博客（推送到 GitHub 仓库即可）：

```json
"scripts": {
   "server": "hugo server -b http://localhost -p 8000",
   "submodule": "git submodule update --remote --merge",
   "dev": "NODE_ENV=development ./themes/blowfish/node_modules/tailwindcss/lib/cli.js -c ./themes/blowfish/tailwind.config.js -i ./themes/blowfish/assets/css/main.css -o ./assets/css/compiled/main.css --jit -w",
   "build": "NODE_ENV=production ./themes/blowfish/node_modules/tailwindcss/lib/cli.js -c ./themes/blowfish/tailwind.config.js -i ./themes/blowfish/assets/css/main.css -o ./assets/css/compiled/main.css --jit"
}
```

#### 📁 博客结构：

- `assets`：存放博客的 CSS、JS、图片等静态资源
- `config`：博客配置文件
- `content`：博客文章存放目录
- `data`：存放数据信息
- `i18n`：存放多语言文件
- `layouts`：博客布局目录
- `scripts`：存放脚本文件
- `static`：存放静态文件
- `themes`：博客主题目录

```
.
├── .github
│   └── workflows
|       └── deploy.yml
├── assets
│   ├── css
│   └── ...
├── config
|   └── _default
│       └── hugo.toml
├── content
│   └── blog
├── data
│   └── authors
├── i18n
│   └── zh-CN.toml
├── layouts
│   ├── _default
│   └── partials
├── scripts
│   └── submit_urls.sh
├── static
│   └── assets
└── themes
    └── blowfish
```

#### 🎨 博客主题：

- [Blowfish](https://blowfish.page/)：一款简洁、清新、响应式的 Hugo 主题

- 自定义 CSS 在 `assets/css/` [https://github.com/qlAD/Blog/blob/main/assets/css/custom.css](https://github.com/qlAD/Blog/blob/main/assets/css/custom.css)：

```bash
https://github.com/qlAD/Blog/blob/main/assets/css/custom.css
```

- 自定义 JS 在 `assets/js/`： [https://github.com/qlAD/Blog/blob/main/assets/js/pangu.custom.js](https://github.com/qlAD/Blog/blob/main/assets/js/pangu.custom.js)：
  
```bash
https://github.com/qlAD/Blog/blob/main/assets/js/pangu.custom.js
```

- 自定义模板在 `layouts/_default`： [https://github.com/qlAD/Blog/blob/main/layouts/_default/mastodon.html](https://github.com/qlAD/Blog/blob/main/layouts/_default/mastodon.html)：

```bash
https://github.com/qlAD/Blog/blob/main/layouts/_default/mastodon.html
```

- 页面数据在 `data`： [https://github.com/qlAD/Blog/blob/main/data/authors/qlAD.json](https://github.com/qlAD/Blog/blob/main/data/authors/qlAD.json)：

```bash
https://github.com/qlAD/Blog/blob/main/data/authors/qlAD.json
```

#### 🎈 嘀咕页面

嘀咕页面 https://www.qladgk.blog/mastodon 为 Mastodon 大型实例 mastodon.social 的数据展示。

利用 [mastodon-embed-timeline](https://gitlab.com/idotj/mastodon-embed-timeline) 这个项目集成到博客页面。

#### 📝 撰写文章

- 文章存放在 `content/blog` 目录下，每篇文件存放在一个文件夹中，文件夹名称为文章的 URL。
- 文件夹中必须包含 `index.md` 文件，该文件为文章的 Markdown 内容。
- `index.md` 文件的 Front Matter 示例：

```yaml
---
title: "我的家乡"
authors: ["qlAD"]
categories: ["日常"]
tags: ["家乡", "风景"]
slug: "my-home"
summary: "本篇文章介绍了我的家乡，以及我在那里的生活。"
series: ["家乡回忆"]
series_weight: 1
seriesNavigation: true
draft: false
date: 2024-05-31
---
```

- 文章的封面图片为 `index.md` 文件同级目录的 `featured.jpg` 文件。
-  文章的背景图片为 `index.md` 文件同级目录的 `background.jpg` 文件。

#### 🖼️ 图片处理

- 文章封面制作：[Coverview](https://coverview.vercel.app/editor)
- 上传图片到图床 [SM.MS](https://sm.ms/)

#### 🌈 评论功能

- 评论系统使用 [giscus](https://giscus.app/) （GitHub Discussions 功能）

#### 📊 网站分析

- Cloudflare analytics
- Google analytics

#### 🎉 特别鸣谢

- [大大的小蜗牛](https://www.eallion.com/)
- [Hugo](https://gohugo.io/)
- [Blowfish](https://blowfish.page/)
- [giscus](https://giscus.app/)
- [SM.MS](https://sm.ms/)
- [Coverview](https://coverview.vercel.app/editor)
- [Cloudflare Pages](https://pages.cloudflare.com/)
- [Google analytics](https://analytics.google.com/analytics/web/)
- [GitHub Actions](https://github.com/features/actions)
