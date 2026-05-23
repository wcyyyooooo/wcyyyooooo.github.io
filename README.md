# wcyyyooooo

极简个人博客，纯静态，托管于 GitHub Pages。

## 结构

```
├── index.html          # 首页（时间线 + 侧栏）
├── post.html           # 独立文章页
├── lists.html          # 完整书单
├── films.html          # 完整影单
├── music-list.html     # 完整歌单
├── music.mp3           # 背景音乐（可选）
├── .nojekyll           # 禁止 Jekyll 处理
├── posts/
│   ├── index.json          # 文章清单
│   └── YYYY-MM-DD-slug.md  # 文章文件
└── data/
    ├── books.json          # 书单数据
    ├── films.json          # 影单数据
    ├── music.json          # 歌单数据
    └── todos.json          # 待办列表
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
### data/todos.json

```json
{ "task": "读完《雪国》", "done": false }
{ "task": "搭建这个博客", "done": true, "date": "2026-05-20" }
```

| 字段 | 说明 |
|------|------|
| `task` | 待办事项 |
| `done` | `true` 已完成 / `false` 未完成 |
| `date` | 完成日期 `YYYY-MM-DD`，仅 `done: true` 需要 |

### post.html

| 位置 | 说明 |
|------|------|
| `<title>` | 文章页标题 |

### posts/index.json

按时间倒序排列所有文章文件名，新文章加在最前面。

### music.mp3

将你的 `.mp3` 文件放在根目录命名为 `music.mp3`，或修改 `index.html` 中 `<source>` 的路径。

### data/books.json

```json
{ "title": "挪威的森林", "author": "村上春树", "status": "reading" }
{ "title": "围城", "author": "钱锺书", "status": "read", "date": "2026-05-10" }
```

| 字段 | 说明 |
|------|------|
| `title` | 书名 |
| `author` | 作者 |
| `status` | `"reading"` 在读 / `"read"` 读过 |
| `date` | 读完日期 `YYYY-MM-DD`，仅 `"read"` 需要 |

### data/films.json

```json
{ "title": "驾驶我的车", "director": "滨口龙介", "status": "watched", "date": "2026-05-01" }
{ "title": "双峰", "director": "大卫·林奇", "status": "watching" }
```

| 字段 | 说明 |
|------|------|
| `title` | 片名 |
| `director` | 导演 |
| `status` | `"watching"` 在看 / `"watched"` 看过 |
| `date` | 看完日期 `YYYY-MM-DD`，仅 `"watched"` 需要 |

### data/music.json

```json
{ "title": "Clair de Lune", "artist": "Debussy" }
```

| 字段 | 说明 |
|------|------|
| `title` | 曲名 |
| `artist` | 艺术家 |

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
