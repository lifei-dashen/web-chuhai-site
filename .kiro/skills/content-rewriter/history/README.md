# history/ — 改写历史归档

这个目录存放 skill 每次改写后产出的初稿。每次改写 = 一个 `.md` 文件。

## 文件命名规范

```
YYYY-MM-DD-HHMM_<标题前 8-12 字>.md
```

例：
- `2026-05-19-1430_我让Claude改个样式.md`
- `2026-05-19-2200_三年前我赌赢了.md`

要求：
- **必须**以 `YYYY-MM-DD` 开头（用于排序）
- 时间 `HHMM` 推荐但不强制
- 文件名里的中文标题保留即可，去掉空格、标点、emoji

## Frontmatter 规范（每篇 md 头部必加）

```markdown
---
title: 我让 Claude 改个样式，它居然反过来教我做事
date: 2026-05-19
time: 1430
source_url: https://mp.weixin.qq.com/s/xxx
angle: Claude 不是输给 Codex，是输给自己
word_count: 1620
status: draft
---

# 正文标题

正文内容...
```

字段说明：

| 字段 | 必填 | 说明 |
|---|---|---|
| `title` | ✅ | 文章标题，会显示在 viewer 列表 |
| `date` | ✅ | `YYYY-MM-DD` |
| `time` | 选填 | `HHMM`，4 位 |
| `source_url` | ✅ | 改写来源链接（追溯素材用） |
| `angle` | ✅ | 这次选的切入角度（用户回的 1/2/3 对应的那一条） |
| `word_count` | ✅ | 总字数 |
| `status` | 选填 | `draft` / `published`（默认 draft） |

## 怎么查看历史

1. 双击打开 `../viewer/index.html`
2. 点击右上角"选择 history 目录"
3. 选中**这个目录**（`history/`）
4. 左侧会列出所有改写历史，按日期倒序

支持：
- 标题/正文搜索
- 一键复制 Markdown / 纯文本 / 标题
- `j` / `k` 键切换上下篇

> 浏览器要求：Chrome / Edge / Arc / Brave 等 Chromium 系。
> Safari / Firefox 可以拖拽 `.md` 文件到页面（降级方案）。

## .gitignore 建议

如果你不想把所有改写历史推到 GitHub（比如里面有未发布的草稿），
在仓库根目录的 `.gitignore` 加上：

```
.kiro/skills/content-rewriter/history/*.md
!.kiro/skills/content-rewriter/history/README.md
```

这样只保留 README，所有 md 不进 git。
