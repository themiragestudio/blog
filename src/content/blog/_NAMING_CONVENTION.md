# 文章文件命名规范

## 格式

```
YYYY-MM-DD-kebab-case-slug.mdx
```

## 规则

1. **日期前缀** — 使用文章**发布日期**，格式 `YYYY-MM-DD`
2. **slug 部分** — kebab-case（小写字母 + 连字符），简洁描述文章主题
3. **扩展名** — 统一使用 `.mdx`（支持 Astro 组件嵌入）
4. **语言** — slug 使用英文，不要包含中文

## 示例

```
2026-03-14-mirage-studio-origin.mdx     ✅ 正确
2026-03-15-svelte-to-react.mdx          ✅ 正确
2026-03-18-multi-agent-collaboration.mdx ✅ 正确

2026-03-14-Mirage-Studio-Origin.mdx     ❌ 不要大写
2026-3-14-mirage-studio-origin.mdx      ❌ 月份和日期必须补零
mirage-studio-origin.mdx                ❌ 缺少日期前缀
2026-03-14-mirage_studio_origin.mdx     ❌ 使用下划线，改用连字符
2026-03-14-mirage studio origin.mdx     ❌ 不要有空格
```

## Slug 与 URL 的对应关系

文件名中的日期前缀在 URL 中**不显示**。Astro Content Collections 使用去掉日期后的部分作为 slug：

| 文件名 | URL |
|--------|-----|
| `2026-03-14-mirage-studio-origin.mdx` | `/posts/2026-03-14-mirage-studio-origin/` |
| `2026-03-15-svelte-to-react.mdx` | `/posts/2026-03-15-svelte-to-react/` |

> 注：当前路由保留完整文件名作为 slug，包含日期。如需只保留 slug 部分，可在 `pages/posts/[slug].astro` 中自定义路由生成逻辑。

## 草稿管理

将 frontmatter 中 `draft: true` 设置为草稿。草稿文件仍放在 `blog/` 目录，构建时通过代码过滤排除。

不使用单独的 `drafts/` 目录，保持目录结构简单。

## 模板

见 `_template.mdx`（通用模板）和各专项模板文件。
