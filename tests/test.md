# Markdown 渲染测试文档

> **摘要**：本文用于验证 GitHub Pages 是否正常渲染 Markdown 内容，包含标题、列表、代码块、表格、引用等常见元素。

**标签**：`test` `markdown` `github-pages`
**创建时间**：2024-01-01
**更新时间**：2024-04-01

---

## 标题测试

以下是各级标题示例：

### 三级标题

#### 四级标题

---

## 列表测试

### 无序列表

- 第一项
- 第二项
  - 嵌套项 A
  - 嵌套项 B
- 第三项

### 有序列表

1. 步骤一：打开终端
2. 步骤二：克隆仓库
3. 步骤三：开始编辑

### 任务列表

- [x] 创建仓库
- [x] 添加 README
- [ ] 启用 GitHub Pages
- [ ] 配置自定义域名

---

## 代码块测试

**Bash 脚本**：

```bash
#!/bin/bash
echo "Hello from GitHub Pages!"
git status
git log --oneline -5
```

**Python 代码**：

```python
def greet(name: str) -> str:
    """返回问候语"""
    return f"Hello, {name}! 🎉"

print(greet("GitHub Pages"))
```

**JSON 示例**：

```json
{
  "name": "pages",
  "description": "个人学习笔记",
  "version": "1.0.0",
  "tags": ["markdown", "notes", "github-pages"]
}
```

---

## 表格测试

| 功能 | 状态 | 备注 |
|------|------|------|
| Markdown 渲染 | ✅ 正常 | GitHub 原生支持 |
| GitHub Pages | ✅ 已启用 | 静态托管 |
| 自动检查 | ✅ 已配置 | markdownlint-cli2 |
| 自定义域名 | ⏳ 待配置 | 可选 |

---

## 引用测试

> 这是一段引用文本。
>
> 引用可以包含多个段落。

> 💡 **提示**：如果你能看到这个页面被正确渲染，说明 GitHub Pages 部署成功！

---

## 强调与格式测试

- **加粗文字**
- *斜体文字*
- ~~删除线文字~~
- `行内代码`
- **_加粗斜体_**

---

## 链接测试

- [回到测试入口](index.md)
- [查看仓库 README](../README.md)
- [GitHub 官网](https://github.com)

---

## 分割线测试

---

以上就是测试文档的全部内容。

如果所有元素都能正确渲染，说明 Markdown 处理和 GitHub Pages 均工作正常。🎉
