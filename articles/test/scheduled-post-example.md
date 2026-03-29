---
allow_comments: true
author: admin
author_id: 019c2cbc-4975-7a7a-8826-c1ae405e898d
category: test
category_id: 019d37cf-ab51-7bd7-a843-04ae8cdc4980
date: '2026-02-15 10:00:00'
enable_jsx: false
is_featured: false
meta_description: ''
meta_keywords: ''
meta_title: ''
slug: scheduled-post-example-lax0ir-vn7oue
status: published
summary: 这是一篇定时发布的示例文章，将在 2026年2月15日 10:00 自动发布
tags:
- 测试
- 定时发布
title: 定时发布示例文章
use_server_rendering: true
---

# 定时发布示例

这篇文章演示了如何在 Git 中使用定时发布功能。

## 工作原理

1. 在 frontmatter 中设置 `date` 字段为未来时间
2. 设置 `status: published`
3. 提交到 Git 并同步到数据库
4. 在设定时间之前，公开接口不会显示这篇文章
5. 到了设定时间，文章自动显示

## 使用场景

- 📅 提前准备节日文章
- 🎯 定时发布营销内容
- 📝 批量创建文章，分批发布
- 🌍 跨时区发布（设置目标时区的时间）

## 注意事项

- 时间格式：`YYYY-MM-DD HH:MM:SS`
- 时区：使用服务器时区（默认 UTC 或 Asia/Shanghai）
- 状态必须是 `published`，不能是 `draft`

## 示例

```yaml
---
title: 我的文章
date: "2026-03-01 09:00:00" # 定时发布时间
status: published
---
```

这篇文章将在 2026 年 3 月 1 日 09:00 自动发布。