# 📚 个人学习笔记与知识整理

> 这是一个以 Markdown 为主的个人知识库，用于长期积累、分类整理学习笔记，方便随时阅读与搜索。

[![Markdown Check](https://github.com/xiyuethink/pages/actions/workflows/markdown-check.yml/badge.svg)](https://github.com/xiyuethink/pages/actions/workflows/markdown-check.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## 目录

- [仓库简介](#仓库简介)
- [目录结构](#目录结构)
- [使用方式](#使用方式)
- [笔记编写规范](#笔记编写规范)
- [如何新增一篇笔记](#如何新增一篇笔记)
- [如何插入图片](#如何插入图片)
- [GitHub Pages 使用说明](#github-pages-使用说明)
- [测试文件访问说明](#测试文件访问说明)
- [快速开始](#快速开始)
- [后续可扩展方向](#后续可扩展方向)

---

## 仓库简介

本仓库用于存放个人学习笔记与知识整理内容，主要涵盖以下方向：

- **编程技术**：语言学习、算法、架构设计等
- **人工智能**：机器学习、大模型、AI 工具使用经验
- **工具效率**：开发工具、效率工具、配置与技巧
- **生活随想**：读书笔记、生活感悟、思考记录

仓库风格简洁、清晰、可维护，适合长期积累，既可直接在 GitHub 浏览，也支持通过 GitHub Pages 进行静态展示。

---

## 目录结构

```
pages/
├── README.md                   # 仓库首页说明（本文件）
├── index.md                    # GitHub Pages 入口页
├── LICENSE                     # MIT 开源协议
├── CONTRIBUTING.md             # 贡献指南
├── CODE_OF_CONDUCT.md          # 行为准则
├── .editorconfig               # 编辑器配置
├── .gitattributes              # Git 属性配置
├── .gitignore                  # Git 忽略规则
├── markdownlint.json           # Markdown 格式检查配置
├── .prettierrc                 # Prettier 代码格式化配置
├── .prettierignore             # Prettier 忽略规则
├── assets/                     # 图片等静态资源
│   └── .gitkeep
├── notes/                      # 笔记正文目录
│   ├── 01-programming/         # 编程技术笔记
│   │   └── hello-markdown.md
│   ├── 02-ai/                  # 人工智能笔记
│   │   └── ai-notes-example.md
│   ├── 03-tools/               # 工具使用笔记
│   │   └── github-tips.md
│   └── 04-life/                # 生活随想笔记
│       └── .gitkeep
├── templates/                  # 笔记模板
│   └── note-template.md
├── tests/                      # 测试访问用示例文件
│   ├── index.md
│   └── test.md
└── .github/
    ├── workflows/
    │   └── markdown-check.yml  # Markdown 自动检查工作流
    ├── ISSUE_TEMPLATE/
    │   ├── bug_report.md
    │   └── feature_request.md
    └── pull_request_template.md
```

---

## 使用方式

### 在线浏览

直接在 GitHub 页面浏览各目录和文件，Markdown 文件会自动渲染。

### 本地克隆

```bash
git clone https://github.com/xiyuethink/pages.git
cd pages
```

### 搜索笔记

在 GitHub 仓库页面使用搜索功能，或在本地使用命令行搜索：

```bash
# 搜索包含关键词的笔记
grep -r "关键词" notes/
```

---

## 笔记编写规范

1. **文件命名**：使用英文小写字母和连字符，例如 `my-note-title.md`
2. **标题层级**：`#` 用于文章标题，`##` 用于一级章节，`###` 用于子章节，层级不超过四级
3. **每篇笔记必须包含**：
   - 标题（`# 标题`）
   - 摘要（简短描述）
   - 标签（`tags: [tag1, tag2]`）
   - 创建时间（`created: YYYY-MM-DD`）
   - 更新时间（`updated: YYYY-MM-DD`）
   - 正文内容
4. **图片**：存放到 `assets/` 目录，使用相对路径引用
5. **链接**：尽量使用相对路径，保证仓库迁移后仍可用
6. **代码块**：必须注明语言类型，例如 ` ```python `
7. **行末空格**：避免行末多余空格

参考模板：[templates/note-template.md](templates/note-template.md)

---

## 如何新增一篇笔记

1. 选择合适的目录（如 `notes/01-programming/`）
2. 复制模板文件：

```bash
cp templates/note-template.md notes/01-programming/my-new-note.md
```

3. 编辑文件，填写标题、摘要、标签、时间和正文
4. 提交到仓库：

```bash
git add notes/01-programming/my-new-note.md
git commit -m "docs: 新增笔记 - my-new-note"
git push
```

---

## 如何插入图片

1. 将图片文件放到 `assets/` 目录下，建议按类别创建子目录，例如：

```
assets/
├── programming/
│   └── screenshot.png
└── ai/
    └── model-diagram.png
```

2. 在 Markdown 文件中使用相对路径引用：

```markdown
![图片描述](../../assets/programming/screenshot.png)
```

> **提示**：图片文件名也建议使用英文小写和连字符命名。

---

## GitHub Pages 使用说明

本仓库支持通过 GitHub Pages 进行静态展示：

1. 进入仓库的 **Settings → Pages**
2. 在 **Source** 中选择 `Deploy from a branch`
3. 选择 `main` 分支，目录选择 `/ (root)`
4. 点击 **Save**，等待几分钟后即可访问

启用后，仓库根目录的 `index.md` 将作为首页显示。访问地址格式为：

```
https://xiyuethink.github.io/pages/
```

---

## 测试文件访问说明

仓库提供了专门的测试文件，用于验证 GitHub Pages 部署是否成功：

- **测试入口**：[tests/index.md](tests/index.md)
- **测试文档**：[tests/test.md](tests/test.md)

启用 GitHub Pages 后，可通过以下地址访问测试文件：

```
https://xiyuethink.github.io/pages/tests/test
https://xiyuethink.github.io/pages/tests/
```

---

## 快速开始

### 1. 如何新建一篇笔记

```bash
# 复制模板
cp templates/note-template.md notes/01-programming/your-note.md

# 编辑内容
# 使用你喜欢的编辑器打开，填写内容

# 提交
git add .
git commit -m "docs: 新增笔记 your-note"
git push
```

### 2. 如何本地预览 Markdown

**方式一：VS Code**
安装 VS Code，打开 `.md` 文件后按 `Ctrl+Shift+V`（Mac: `Cmd+Shift+V`）预览。

**方式二：Typora**
直接用 [Typora](https://typora.io/) 打开 Markdown 文件，所见即所得。

**方式三：命令行（grip）**

```bash
pip install grip
grip README.md
# 打开浏览器访问 http://localhost:6419
```

### 3. 如何启用 GitHub Pages

1. 进入仓库 **Settings → Pages**
2. Source 选择 `Deploy from a branch`，Branch 选择 `main`，目录选 `/(root)`
3. 保存后等待约 1-2 分钟
4. 访问 `https://xiyuethink.github.io/pages/`

### 4. 如何验证测试文件可以访问

GitHub Pages 启用后，访问以下链接，页面能正常显示即代表部署成功：

- `https://xiyuethink.github.io/pages/tests/test`
- `https://xiyuethink.github.io/pages/tests/`

---

## 后续可扩展方向

- [ ] 接入 [Jekyll](https://jekyllrb.com/) 或 [MkDocs](https://www.mkdocs.org/) 生成更美观的静态站点
- [ ] 添加全文搜索功能（如 Algolia DocSearch）
- [ ] 引入标签系统，支持按标签聚合笔记
- [ ] 配置自定义域名
- [ ] 添加评论功能（如 Giscus）
- [ ] 定期自动归档旧笔记
- [ ] 增加 `notes/05-reading/` 读书笔记目录

---

## 贡献

欢迎提 Issue 或 PR，请先阅读 [CONTRIBUTING.md](CONTRIBUTING.md)。

## 行为准则

请遵守 [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)。

## 许可证

本仓库内容采用 [MIT License](LICENSE) 开源。

