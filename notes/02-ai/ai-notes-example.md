# AI 学习笔记 — 大语言模型入门

> **摘要**：本文记录了大语言模型（LLM）的基本概念、主要应用方向以及实际使用经验，适合 AI 初学者了解当前 LLM 生态。

**标签**：`ai` `llm` `大模型` `入门`
**创建时间**：2024-02-10
**更新时间**：2024-04-01

---

## 目录

- [什么是大语言模型](#什么是大语言模型)
- [主流模型对比](#主流模型对比)
- [核心概念](#核心概念)
- [实际应用场景](#实际应用场景)
- [Prompt 工程基础](#prompt-工程基础)
- [常用工具与平台](#常用工具与平台)
- [总结](#总结)
- [参考资料](#参考资料)

---

## 什么是大语言模型

大语言模型（Large Language Model，LLM）是基于 Transformer 架构、在海量文本数据上训练而成的神经网络模型。它能够理解并生成自然语言，完成对话、翻译、摘要、代码生成等多种任务。

**关键特征**：

- 参数规模庞大（数十亿到数千亿参数）
- 涌现能力（Emergent Abilities）：随规模增大出现意想不到的能力
- 上下文学习（In-Context Learning）：无需微调即可通过示例学习新任务
- 指令跟随（Instruction Following）：能理解和执行自然语言指令

---

## 主流模型对比

| 模型 | 开发方 | 特点 |
|------|--------|------|
| GPT-4 / GPT-4o | OpenAI | 综合能力强，多模态支持 |
| Claude 3 | Anthropic | 长上下文，安全对齐好 |
| Gemini | Google | 多模态，深度集成 Google 服务 |
| Llama 3 | Meta | 开源，可本地部署 |
| Qwen | 阿里巴巴 | 中文能力强，开源可用 |
| DeepSeek | 深度求索 | 开源，推理能力突出 |

---

## 核心概念

### Token

语言模型处理的基本单位不是字符，而是 Token。

- 英文中，一个 Token 大约对应 3-4 个字符或 0.75 个单词
- 中文中，通常每个汉字对应 1-2 个 Token
- 模型的上下文长度（Context Length）以 Token 数量计算

### Temperature（温度）

控制输出的随机性：

- `temperature = 0`：输出最确定，适合需要精确答案的任务
- `temperature = 1`：标准随机性，适合一般对话
- `temperature > 1`：输出更随机、更有创意，但可能不连贯

### Embedding（嵌入）

将文本转换为高维向量的过程，用于语义搜索、相似度计算等任务。

```python
# 使用 OpenAI Embedding API 示例
from openai import OpenAI

client = OpenAI()

response = client.embeddings.create(
    input="大语言模型是人工智能的重要进展",
    model="text-embedding-3-small"
)

vector = response.data[0].embedding
print(f"向量维度：{len(vector)}")  # 1536
```

---

## 实际应用场景

1. **代码辅助**：GitHub Copilot、Cursor 等工具大幅提升编程效率
2. **写作辅助**：文章润色、邮件撰写、报告生成
3. **知识问答**：快速获取特定领域的概念解释
4. **数据分析**：配合 Python 代码分析数据，生成可视化
5. **翻译**：高质量多语言翻译，支持上下文理解

---

## Prompt 工程基础

好的 Prompt 能显著提升模型输出质量。

### 基本原则

- **明确角色**：告诉模型"你是一个..."
- **提供上下文**：给出足够的背景信息
- **指定格式**：要求输出 JSON、Markdown、列表等特定格式
- **给出示例**：Few-shot 示例能引导模型理解期望的输出风格

### 示例对比

**差的 Prompt**：
```
解释一下机器学习
```

**好的 Prompt**：
```
你是一位擅长向初学者解释技术概念的老师。
请用通俗易懂的语言，配合一个生活中的类比，
用不超过 200 字解释"监督学习"的概念。
```

---

## 常用工具与平台

- **ChatGPT**：[chat.openai.com](https://chat.openai.com) — 最广泛使用的对话 AI
- **Claude**：[claude.ai](https://claude.ai) — 长文本处理能力突出
- **通义千问**：[tongyi.aliyun.com](https://tongyi.aliyun.com) — 中文支持好
- **Ollama**：本地运行开源模型的工具，支持 Llama、Qwen 等

```bash
# 使用 Ollama 本地运行模型
ollama pull llama3
ollama run llama3
```

---

## 总结

- 大语言模型已经深刻改变了信息获取和内容创作的方式
- 理解 Token、Temperature 等基本概念有助于更好地使用模型
- Prompt 工程是提升 AI 输出质量的关键技能
- 开源模型生态日益完善，本地部署也越来越可行

---

## 参考资料

- [Attention Is All You Need（原始论文）](https://arxiv.org/abs/1706.03762)
- [OpenAI Cookbook](https://cookbook.openai.com)
- [Prompt Engineering Guide](https://www.promptingguide.ai/zh)
- [Hugging Face 课程](https://huggingface.co/learn)
