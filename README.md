# wcyyyooooo

极简个人博客，纯静态，托管于 GitHub Pages。

## 结构

```
├── index.html          # 首页（时间线）
├── post.html           # 独立文章页
├── music.mp3           # 背景音乐（可选）
├── .nojekyll           # 禁止 Jekyll 处理
└── posts/
    ├── index.json          # 文章清单
    └── YYYY-MM-DD-slug.md  # 文章文件
```

## 需要修改的地方

### index.html

| 位置 | 说明 |
|------|------|
| `<title>` | 网页标题 |
| `<h1>` | 你的名字 |
| `.subtitle` | 副标题 |
| `.header-links` 中的 `<a>` | GitHub、邮箱等链接 |
| `<source src="music.mp3">` | 音乐文件路径 |

### post.html

| 位置 | 说明 |
|------|------|
| `<title>` | 文章页标题 |

### posts/index.json

按时间倒序排列所有文章文件名，新文章加在最前面。

### music.mp3

将你的 `.mp3` 文件放在根目录命名为 `music.mp3`，或修改 `index.html` 中 `<source>` 的路径。

## 发布文章

1. 在 `posts/` 下新建文件，命名格式 `YYYY-MM-DD-slug.md`
2. 文件内容：

```markdown
---
date: 2026-06-01
title: 文章标题
tags: [标签1, 标签2]
---

正文内容，支持 markdown。
```

3. 在 `posts/index.json` 最前面加上文件名
4. 提交推送：

```bash
git add posts/ && git commit -m "新文章: 标题" && git push
```

## 支持的 Markdown

`**加粗**` `*斜体*` `` `代码` `` `[链接](url)` `## 二级标题` `> 引用` `` ```代码块``` ``
