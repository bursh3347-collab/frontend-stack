# 🤝 Contributing to frontend-stack

This repository is part of the **GitHub Open Source Knowledge Restructuring Project** by [bursh3347-collab](https://github.com/bursh3347-collab).

We welcome contributions! Here's how you can help.

## 📝 提交项目分析（Project Analysis）

### 要求

每个项目分析必须使用 TEMC 模板，包含以下内容：

1. **基本信息表格**：GitHub链接、Stars数、License、语言、维护者
2. **TEMC评分**：T(技术)/E(生态)/M(市场)/C(组合) 四维评分（0-100），每个维度必须有数据支撑
3. **Core Value**：3-5个核心价值点
4. **Risks**：至少2个风险/反证
5. **天子点评**：一句话判断（从AI原生一人公司视角）

### 文件格式

```
projects/[project-name].md
```

项目名使用小写、连字符分隔（如 `shadcn-ui.md`、`framer-motion.md`）。

### TEMC模板

```markdown
# 项目名称

> 一句话描述

| Metric | Data |
|------|------|
| GitHub | [owner/repo](link) |
| Stars | X,XXX |
| License | MIT/Apache/... |
| Language | TypeScript/... |

## TEMC Scores

| Dimension | Score | Reasoning |
|------|------|------|
| T (Tech) | XX | 具体数据支撑 |
| E (Ecosystem) | XX | 具体数据支撑 |
| M (Market) | XX | 具体数据支撑 |
| C (Combo) | XX | 具体数据支撑 |
| **Overall** | **XX** | |

## Core Value
- ...

## Risks
- ...

## 天子点评
一句话判断。
```

## 🔧 提交代码（Code Contributions）

代码贡献放入 `code/` 目录，每段代码必须包含：

1. **来源**：从哪个项目提取（附GitHub链接 + Stars数）
2. **为什么好**：比其他方案好在哪里
3. **怎么用**：使用说明 + 示例代码
4. **你改了什么**：和原项目的区别
5. **License**：原项目的开源协议

## 📋 PR模板

提交PR时请在描述中包含：

```
## 变更类型
- [ ] 新增项目分析
- [ ] 更新现有分析（Stars/评分/内容）
- [ ] 新增代码提取
- [ ] 更新best-practices
- [ ] 修正错误

## 变更说明
简述你做了什么。

## 数据来源
列出你的数据来源URL。
```

## 🎯 Good First Issues

以下是适合新贡献者的任务：

- 📊 更新项目Stars数据（每周）
- 📝 补充某个项目的Risks章节
- 🔍 添加新的前端项目分析（Stars > 500、MIT/Apache、90天内有活跃commit）
- 📖 改进best-practices文档

## ✅ Quality Standards

- TEMC评分必须有具体数据支撑，不能凭感觉
- 每个≥80分的项目必须有反证（为什么可能不值得用）
- Stars > 500（种子期项目除外，需注明理由）
- 90天内有commit活跃（非弃坑项目）
- License为 MIT / Apache-2.0 / BSD（可商用）

## 📬 Questions?

Open an issue or start a discussion. We're happy to help!
