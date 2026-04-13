# 贡献指南

感谢你对本仓库的关注！这里记录了如何参与贡献的说明。

## 贡献方式

### 报告问题

如果你发现笔记中有错误、过时的信息或表述不清晰的地方，欢迎提交 [Issue](../../issues)。

提交 Issue 时，请尽量说明：
- 发现问题的文件路径
- 具体的问题描述
- 你认为正确的内容（如果有的话）

### 提交修改（Pull Request）

1. **Fork** 本仓库到你的账号
2. 克隆你 fork 的仓库到本地：

   ```bash
   git clone https://github.com/YOUR_USERNAME/pages.git
   cd pages
   ```

3. 创建一个新分支：

   ```bash
   git checkout -b fix/your-branch-name
   ```

4. 进行修改并提交：

   ```bash
   git add .
   git commit -m "docs: 修正 xxx 笔记中的错误"
   git push origin fix/your-branch-name
   ```

5. 在 GitHub 上提交 Pull Request，描述你的修改内容

### 新增笔记

欢迎贡献新的学习笔记！请参考以下规范：

- 将笔记放到对应的分类目录下（`notes/01-programming/`、`notes/02-ai/` 等）
- 使用 [笔记模板](templates/note-template.md) 创建新文件
- 文件名使用英文小写加连字符，例如 `python-list-tricks.md`
- 确保内容原创或注明引用来源

## 提交信息规范

提交信息请使用以下前缀：

| 前缀 | 用途 |
|------|------|
| `docs:` | 新增或修改笔记内容 |
| `fix:` | 修正错误（错别字、错误信息等） |
| `feat:` | 新增功能或目录结构 |
| `chore:` | 配置文件、工具相关修改 |
| `style:` | 格式调整，不影响内容 |

示例：
```
docs: 新增 Python 装饰器笔记
fix: 修正 AI 笔记中的概念错误
chore: 更新 markdownlint 配置
```

## Markdown 格式要求

- 标题层级清晰，不跳级
- 代码块必须注明语言
- 图片使用相对路径，文件存放于 `assets/` 目录
- 行末不留多余空格
- 文件末尾留一个空行

## 行为准则

参与贡献即表示你同意遵守本仓库的 [行为准则](CODE_OF_CONDUCT.md)。

感谢你的贡献！🎉
