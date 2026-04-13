# GitHub 使用技巧

> **摘要**：整理了 GitHub 日常使用中的实用技巧，包括仓库管理、搜索技巧、Pages 部署、快捷键等，帮助提升 GitHub 使用效率。

**标签**：`github` `git` `tools` `效率`
**创建时间**：2024-03-05
**更新时间**：2024-04-01

---

## 目录

- [Git 常用命令](#git-常用命令)
- [GitHub 搜索技巧](#github-搜索技巧)
- [GitHub Pages 部署](#github-pages-部署)
- [GitHub Actions 入门](#github-actions-入门)
- [实用快捷键](#实用快捷键)
- [常见问题](#常见问题)
- [总结](#总结)
- [参考资料](#参考资料)

---

## Git 常用命令

### 基础操作

```bash
# 初始化仓库
git init

# 克隆远程仓库
git clone https://github.com/username/repo.git

# 查看状态
git status

# 添加文件到暂存区
git add .                    # 添加所有变更
git add path/to/file.md      # 添加指定文件

# 提交
git commit -m "docs: 新增笔记"

# 推送到远程
git push origin main
```

### 分支操作

```bash
# 创建并切换到新分支
git checkout -b feature/new-notes

# 查看所有分支
git branch -a

# 合并分支
git merge feature/new-notes

# 删除分支
git branch -d feature/new-notes
```

### 撤销与恢复

```bash
# 撤销工作区的修改（未暂存）
git checkout -- file.md

# 撤销暂存区（已 add，未 commit）
git reset HEAD file.md

# 撤销最近一次提交（保留修改）
git reset --soft HEAD~1

# 查看提交历史
git log --oneline -10
```

---

## GitHub 搜索技巧

GitHub 的搜索支持很多高级语法：

| 语法 | 含义 | 示例 |
|------|------|------|
| `in:name` | 在仓库名中搜索 | `notes in:name` |
| `in:readme` | 在 README 中搜索 | `machine learning in:readme` |
| `stars:>1000` | Stars 数量过滤 | `react stars:>10000` |
| `language:python` | 按语言过滤 | `scraper language:python` |
| `user:username` | 搜索特定用户的仓库 | `user:torvalds` |
| `topic:markdown` | 按话题标签搜索 | `topic:notes` |

**示例**：搜索 Stars 超过 1000、用 Python 写的机器学习项目：

```
machine learning stars:>1000 language:python
```

---

## GitHub Pages 部署

### 最简单的部署方式（无构建工具）

1. 进入仓库 **Settings → Pages**
2. Source 选择 `Deploy from a branch`
3. Branch 选择 `main`，目录选 `/ (root)`
4. 点击 Save

几分钟后访问：`https://username.github.io/repo-name/`

### 自定义域名

1. 在仓库根目录创建 `CNAME` 文件，内容为你的域名：

   ```
   notes.yourdomain.com
   ```

2. 在 DNS 服务商添加 CNAME 记录，指向 `username.github.io`

### 强制 HTTPS

在 Settings → Pages 中勾选 **Enforce HTTPS**。

---

## GitHub Actions 入门

GitHub Actions 是 GitHub 内置的 CI/CD 工具，可以在特定事件触发时自动运行任务。

### 基本概念

- **Workflow（工作流）**：`.github/workflows/` 下的 YAML 文件
- **Job（任务）**：工作流中的一组步骤，运行在独立的虚拟机上
- **Step（步骤）**：Job 中的单个操作，可以运行命令或 Action

### 示例：自动检查 Markdown

```yaml
name: Markdown Check
on:
  push:
    paths: ["**/*.md"]

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: DavidAnson/markdownlint-cli2-action@v16
        with:
          globs: "**/*.md"
```

---

## 实用快捷键

在 GitHub 网页上按 `?` 可查看所有快捷键，以下是最常用的：

| 快捷键 | 功能 |
|--------|------|
| `t` | 文件搜索（在仓库页面） |
| `l` | 跳转到指定行（查看文件时） |
| `w` | 切换分支（在仓库页面） |
| `b` | 查看 blame（查看文件时） |
| `/` | 聚焦搜索框 |
| `s` | 聚焦搜索框（全局） |

---

## 常见问题

### 如何撤销已推送的 commit？

```bash
# 创建一个"反向提交"来撤销（推荐，保留历史）
git revert HEAD
git push

# 强制回退（危险，会修改历史，不建议在协作分支使用）
git reset --hard HEAD~1
git push --force
```

### 如何配置 Git 用户信息？

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

### 如何忽略已跟踪的文件？

```bash
# 先从 Git 跟踪中移除（不删除本地文件）
git rm --cached file.txt

# 再添加到 .gitignore
echo "file.txt" >> .gitignore
git commit -m "chore: 忽略 file.txt"
```

---

## 总结

- 掌握基本的 Git 命令是版本管理的基础
- GitHub 搜索语法能大幅提升查找开源项目的效率
- GitHub Pages + 纯 Markdown 是最轻量的文档发布方式
- GitHub Actions 让自动化检查和部署变得简单

---

## 参考资料

- [Git 官方文档](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com)
- [Pro Git（中文版）](https://git-scm.com/book/zh/v2)
- [GitHub Actions 文档](https://docs.github.com/actions)
