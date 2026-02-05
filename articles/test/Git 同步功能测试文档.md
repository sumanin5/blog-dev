---
allow_comments: true
author: admin
author_id: 019c2cbc-4975-7a7a-8826-c1ae405e898d
category: test
category_id: 019c2cbc-8a63-7894-aa82-b5e607424de8
date: '2026-01-25 21:21:45'
enable_jsx: false
is_featured: false
meta_description: ''
meta_keywords: ''
meta_title: ''
slug: git-sync-demo-hj2z15-cxsriq
status: published
summary: 这是一篇通过 GitOps 自动同步的测试文章，演示了如何通过本地 Markdown 文件管理博客内容。
title: Git 同步功能测试文档
use_server_rendering: true
---

## 欢迎使用 GitOps 管理您的博客

如果您看到了这篇文章，说明 **Git 同步功能** 已经配置成功！🎉

### 核心特性

- **Single Source of Truth**: 代码库即内容库。
- **自动解析**: 自动读取 Frontmatter 中的元数据（标题、摘要、作者）。
- **增量更新**: 智能对比文件变化，只同步修改过的部分。
- **媒体关联**: 如果有同名图片 `test-image.png` 在媒体库，它会自动关联为封面。

### 如何使用？

1. 在 `content/` 目录下创建 `.md` 或 `.mdx` 文件。
2. 填写 Frontmatter。
3. 提交到 Git 仓库 (或者本地点击同步)。
4. 在后台刷新查看结果。

> 提示：Git 托管的文章在后台是**只读**的，请勿在后台尝试编辑。

```python
def hello_world():
    print("Code highlighting matches specific language!")
```