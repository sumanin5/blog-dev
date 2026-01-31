---
allow_comments: true
author: admin
author_id: 019bf51f-04fb-75b8-8d9a-2e910fee7111
category: test
category_id: 019bf54f-21c2-7dca-9659-7f57a46140ef
date: '2026-01-25 21:21:45'
enable_jsx: false
is_featured: false
meta_description: ''
meta_keywords: ''
meta_title: ''
slug: mdx-render-test-0yxtub
status: published
summary: 这是一篇通过 GitOps 自动同步的测试文章，演示了如何通过本地 Markdown 文件管理博客内容。
title: 测试 MDX 渲染
use_server_rendering: true
---

# MDX 代码高亮测试

这是一个测试文档，用于验证 TSX 和 JSX 代码块的语法高亮和渲染效果。

## React TSX 组件示例

下面是一个 TypeScript React 组件：

```tsx
import React, { useState } from "react";

interface ButtonProps {
  label: string;
  onClick: () => void;
  variant?: "primary" | "secondary";
}

export const CustomButton: React.FC<ButtonProps> = ({
  label,
  onClick,
  variant = "primary",
}) => {
  const [isHovered, setIsHovered] = useState(false);

  return (
    <button
      onClick={onClick}
      onMouseEnter={() => setIsHovered(true)}
      onMouseLeave={() => setIsHovered(false)}
      className={`px-4 py-2 rounded ${
        variant === "primary" ? "bg-blue-500" : "bg-gray-500"
      } ${isHovered ? "opacity-80" : "opacity-100"}`}
    >
      {label}
    </button>
  );
};
```

## React JSX 组件示例

这是一个普通的 JavaScript React 组件：

```jsx
import { useEffect } from "react";

function UserProfile({ userId }) {
  const [user, setUser] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetch(`/api/users/${userId}`)
      .then((res) => res.json())
      .then((data) => {
        setUser(data);
        setLoading(false);
      })
      .catch((err) => console.error(err));
  }, [userId]);

  if (loading) return <div>Loading...</div>;

  return (
    <div className="user-profile">
      <img src={user.avatar} alt={user.name} />
      <h2>{user.name}</h2>
      <p>{user.bio}</p>
    </div>
  );
}

export default UserProfile;
```

## Next.js 服务端组件 (TSX)

```tsx
import { Suspense } from "react";
import { PostList } from "@/components/post-list";

interface PageProps {
  params: { slug: string };
  searchParams: { page?: string };
}

export default async function BlogPage({ params, searchParams }: PageProps) {
  const page = Number(searchParams.page) || 1;

  // 服务端数据获取
  const posts = await fetch(`https://api.example.com/posts?page=${page}`).then(
    (res) => res.json()
  );

  return (
    <main className="container mx-auto px-4">
      <h1 className="text-4xl font-bold mb-8">博客文章</h1>
      <Suspense fallback={<div>加载中...</div>}>
        <PostList posts={posts} />
      </Suspense>
    </main>
  );
}
```

## React Hook 示例

```tsx
import { useCallback, useMemo } from "react";

function useDebounce<T>(value: T, delay: number): T {
  const [debouncedValue, setDebouncedValue] = useState<T>(value);

  useEffect(() => {
    const handler = setTimeout(() => {
      setDebouncedValue(value);
    }, delay);

    return () => {
      clearTimeout(handler);
    };
  }, [value, delay]);

  return debouncedValue;
}

// 使用示例
function SearchComponent() {
  const [searchTerm, setSearchTerm] = useState("");
  const debouncedSearch = useDebounce(searchTerm, 500);

  useEffect(() => {
    if (debouncedSearch) {
      // 执行搜索
      console.log("Searching for:", debouncedSearch);
    }
  }, [debouncedSearch]);

  return (
    <input
      type="text"
      value={searchTerm}
      onChange={(e) => setSearchTerm(e.target.value)}
      placeholder="搜索..."
    />
  );
}
```

## 数学公式测试

行内公式：$E = mc^2$

块级公式：

$$
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
$$

## 表格测试

| 框架   | 语言    | 类型安全     | 性能       |
| ------ | ------- | ------------ | ---------- |
| React  | JSX/TSX | ✅ (with TS) | ⭐⭐⭐⭐   |
| Vue    | SFC     | ✅ (with TS) | ⭐⭐⭐⭐⭐ |
| Svelte | Svelte  | ✅ (with TS) | ⭐⭐⭐⭐⭐ |

## 代码高亮特性测试

```tsx
// 注释测试
const API_KEY = "test-key-123"; // 字符串
const count = 42; // 数字
const isActive = true; // 布尔值
const regex = /^[a-z]+$/i; // 正则表达式

// 箭头函数
const add = (a: number, b: number): number => a + b;

// 泛型
function identity<T>(arg: T): T {
  return arg;
}

// 解构
const { name, age, ...rest } = user;
const [first, second, ...others] = array;

// 模板字符串
const message = `Hello, ${name}! You are ${age} years old.`;

// 可选链和空值合并
const userName = user?.profile?.name ?? "Anonymous";
```

测试完成！