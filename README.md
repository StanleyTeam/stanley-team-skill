# Awesome Agent Skills

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> 精选的 AI Agent Skills（智能体技能包）合集。覆盖内容创作、社交媒体增长、科研学术、教育竞赛、个性化工具和效率提升等方向。

AI Agent Skills 是 2025 年下半年兴起的新范式：用一份声明式的 SKILL.md 文件，教会 Claude Code、OpenAI Codex、Cursor、WorkBuddy(CodeBuddy) 等 AI 编程助手新的能力。这个合集收录社区里真正好用、值得安装的技能包。

## 目录

- [内容创作与写作](#内容创作与写作)
- [社交媒体增长](#社交媒体增长)
- [科研与学术](#科研与学术)
- [教育与竞赛](#教育与竞赛)
- [个性化与趣味](#个性化与趣味)
- [平台与工具](#平台与工具)
- [贡献](#贡献)
- [许可证](#许可证)

---

## 内容创作与写作

- [jcm-skill](https://github.com/jinchenma94/jcm-skill#readme) - 文章写作辅助 skill，从素材整理、大纲协作到初稿质检的全流程。
- [snail-biaoti-public](https://github.com/dulala567/snail-biaoti-public#readme) - 中文标题生成与评分系统，支持微信公众号、小红书、X、LinkedIn 多平台改写。
- [Punk-Skill](https://github.com/adrianpunk/Punk-Skill#readme) - 视觉生成 skill，把文章转成封面图、把照片转成风格化头像。内置 20+ 种封面风格和 5 种头像风格。
- [Mting-skill](https://github.com/mting0308-ux/Mting-skill#readme) - 学习复盘与输出 skill，把视频、文字稿、字幕等学习材料变成知识点复盘、行动清单、X 短推草稿和配图方案。

## 社交媒体增长

- [xiaomu_x_creator](https://github.com/JayceHuang/xiaomu_x_creator#readme) - X/Twitter 内容运营工具箱，含排期、短推改写、作战计划、标题生成、封面制作的全套 skill。
- [Stanley-team-skill](https://github.com/SAKISAM/Stanley-team-skill#readme) - X/Twitter 起号与增长技能群，覆盖主页搭建、发推节奏、增长诊断、风险恢复、变现路径。

## 科研与学术

- [rw-research-skill](https://github.com/rolandwonglonam/rw-research-skill#readme) - 科研全流程 skill 集，16 个独立 skill 覆盖问题界定、文献发现、证据整合、研究设计、论文写作和投稿。含 356 条知识原子和 89 个行为测试。

## 教育与竞赛

- [ssoier-cpp-solution](https://github.com/xiaoxihahaha/ssoier-cpp-solution#readme) - C++ 信息学奥赛题解生成器，给一个 OJ 题目链接自动抓取、分析、生成带注释的参考代码和结构化 Markdown 题解。

## 个性化与趣味

- [codex-orange-block-pet](https://github.com/GaryLauLGY/codex-orange-block-pet#readme) - Codex 橙色方块桌宠，9 种任务状态动画、57 个标准动作帧，给 AI 编程助手加点陪伴感。

---

## 平台与工具

这些是支持 Agent Skills 机制的主流平台：

| 平台 | Skills 目录 | 说明 |
|------|------------|------|
| Claude Code | `~/.claude/skills/` | Anthropic 的命令行 AI 编程助手 |
| OpenAI Codex | `~/.codex/skills/` | OpenAI 的编程 Agent |
| WorkBuddy (CodeBuddy) | `~/.workbuddy/skills/` | 腾讯的 AI 编程助手，支持用户级和项目级 skill |
| Cursor | `.cursor/skills/` | AI 代码编辑器 |

### Skills 的基本结构

```
your-skill-name/
├── SKILL.md          # 核心文件：定义能力、触发词、工作流程
├── skill.yaml        # 元信息：名称、描述、标签（部分平台需要）
├── agents/           # 平台适配配置
│   └── openai.yaml   # OpenAI Codex 适配
├── references/       # 参考文档和方法论
│   └── *.md
└── examples/         # 示例输出
```

### 安装方式

大多数 skill 支持两种安装方式：

```bash
# 方式一：用 skills CLI（推荐）
npx -y skills add 用户名/仓库名 -g --all

# 方式二：手动复制
git clone https://github.com/用户名/仓库名.git
cp -R 仓库名/skills/你的skill ~/.codex/skills/  # Codex
cp -R 仓库名/skills/你的skill ~/.workbuddy/skills/  # WorkBuddy
```

安装后重启对应的 AI Agent 即可生效。

---

## 贡献

欢迎贡献！请阅读 [贡献指南](CONTRIBUTING.md)。

提交新条目前请注意：
- 只收录你亲自用过、确实好用的 skill。
- 描述客观，说明它做什么，不用营销词。
- 按现有分类归档，或提议新分类。

## 许可证

[CC0-1.0](LICENSE)
