# Hello Markdown — Markdown 基础语法指南

> **摘要**：本文介绍 Markdown 最常用的语法，包括标题、列表、代码、链接、图片、表格等，是快速上手 Markdown 写作的入门参考。

**标签**：`markdown` `writing` `入门`
**创建时间**：2024-01-15
**更新时间**：2024-04-01

---

## 目录

- [什么是 Markdown](#什么是-markdown)
- [标题与段落](#标题与段落)
- [强调与格式](#强调与格式)
- [列表](#列表)
- [链接与图片](#链接与图片)
- [代码](#代码)
- [表格](#表格)
- [引用](#引用)
- [总结](#总结)

---

## 什么是 Markdown

Markdown 是一种轻量级标记语言，由 John Gruber 于 2004 年创建。它允许人们使用纯文本格式编写文档，然后转换成 HTML 或其他格式。

**核心优势**：

- 语法简单，易于学习
- 纯文本存储，版本管理友好
- 渲染效果整洁，可读性强
- 广泛支持：GitHub、Notion、VS Code 等均原生支持

---

## 标题与段落

Markdown 使用 `#` 号表示标题，`#` 的数量对应标题层级：

```markdown
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
```

段落之间用空行分隔。单个换行在渲染后不会产生新段落。

---

## 强调与格式

| 效果 | 语法 | 示例 |
|------|------|------|
| **加粗** | `**文字**` | `**重要**` |
| *斜体* | `*文字*` | `*注意*` |
| ~~删除线~~ | `~~文字~~` | `~~已废弃~~` |
| `行内代码` | `` `代码` `` | `` `print()` `` |

---

## 列表

**无序列表**使用 `-` 或 `*`：

```markdown
- 苹果
- 香蕉
- 橙子
  - 脐橙
  - 血橙
```

**有序列表**使用数字加点：

```markdown
1. 第一步：克隆仓库
2. 第二步：安装依赖
3. 第三步：运行程序
```

**任务列表**（GitHub 支持）：

```markdown
- [x] 已完成任务
- [ ] 待完成任务
```

---

## 链接与图片

**链接**：

```markdown
[显示文字](https://example.com)
[本仓库 README](../../README.md)
```

**图片**（将图片存放于 `assets/` 目录）：

```markdown
![图片描述](../../assets/example.png)
```

---

## 代码

**行内代码**：使用反引号包裹，例如 `git commit -m "message"`。

**代码块**：使用三个反引号，并注明语言：

```python
def fibonacci(n):
    """计算斐波那契数列"""
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)

print(fibonacci(10))  # 输出 55
```

```bash
# 克隆仓库
git clone https://github.com/xiyuethink/pages.git

# 查看日志
git log --oneline -10
```

---

## 表格

```markdown
| 列名1 | 列名2 | 列名3 |
|-------|-------|-------|
| 内容1 | 内容2 | 内容3 |
| 内容4 | 内容5 | 内容6 |
```

效果：

| 语言 | 类型 | 主要用途 |
|------|------|----------|
| Python | 解释型 | 数据科学、AI、脚本 |
| JavaScript | 解释型 | 前端、全栈开发 |
| Go | 编译型 | 后端服务、云原生 |
| Rust | 编译型 | 系统编程、高性能 |

---

## 引用

使用 `>` 表示引用：

> 任何足够先进的技术，初看都与魔法无异。
>
> — 阿瑟·C·克拉克

引用可以嵌套：

> 外层引用
>
> > 内层引用

---

## 总结

- Markdown 语法简洁，学习成本低
- 掌握标题、列表、代码块、链接、表格这五大核心语法即可应对绝大多数写作场景
- 在 GitHub 中，`.md` 文件会自动渲染，非常适合文档管理
- 建议配合 VS Code + Markdown Preview Enhanced 插件使用

---

## 参考资料

- [Markdown 官方文档](https://daringfireball.net/projects/markdown/)
- [GitHub Flavored Markdown 规范](https://github.github.com/gfm/)
- [Markdown Guide](https://www.markdownguide.org/)
