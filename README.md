# Awesome Agent Skills

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated collection of AI Agent Skills for content creation, social media growth, research, education, and beyond. For Claude Code, Codex, Cursor, WorkBuddy, and any agent that supports Skills.

AI Agent Skills 是 2025 年下半年兴起的新范式：用一份声明式的 SKILL.md 文件，教会 AI 助手新的能力。这个合集收录社区里真正好用、值得安装的技能包。

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

- [jcm-skill](https://github.com/jinchenma94/jcm-skill#readme) - 文章写作辅助 skill。从搜资料、整理素材、协作大纲到按"金尘马式 AI 干货写作"规则质检初稿，覆盖写作全流程。
- [snail-biaoti-public](https://github.com/dulala567/snail-biaoti-public#readme) - 中文标题生成与评分系统。用"真实、相关、对准"标准检查标题，支持微信公众号、小红书、X 中英文和 LinkedIn 多平台改写，不杜撰数字和案例。
- [Punk-Skill](https://github.com/adrianpunk/Punk-Skill#readme) - 视觉生成 skill。`punk-cover` 把文章转成封面图（20+ 种风格），`punk-avatar` 把照片转成风格化头像和宠物纪念卡（5 种风格）。
- [Mting-skill](https://github.com/mting0308-ux/Mting-skill#readme) - 学习复盘与输出 skill。把视频、文字稿、字幕等学习材料变成三层资产：可复习的知识点和行动清单、可发布的 X 短推草稿、可配图的视觉方案。

## 社交媒体增长

- [xiaomu_x_creator](https://github.com/JayceHuang/xiaomu_x_creator#readme) - X/Twitter 内容运营工具箱。含排期管理、短推改写、素材萃取、作战计划生成、多平台标题方案、封面制作和爆款监控的一整套 skill。

## 科研与学术

- [rw-research-skill](https://github.com/rolandwonglonam/rw-research-skill#readme) - 科研全流程 skill 集。16 个独立 skill 覆盖研究问题界定、文献发现、证据整合、创新点筛选、研究设计、论文写作、来源核验和投稿。含 356 条知识原子、119 条公理和 89 个行为测试。

## 教育与竞赛

- [ssoier-cpp-solution](https://github.com/xiaoxihahaha/ssoier-cpp-solution#readme) - C++ 信息学奥赛题解生成器。给一个 OJ 题目链接（ssoier / 洛谷 / Codeforces 等），自动抓取题目、分析解题思路、生成带注释的参考代码和结构化 Markdown 题解文件。

## 个性化与趣味

- [codex-orange-block-pet](https://github.com/GaryLauLGY/codex-orange-block-pet#readme) - Codex 橙色方块桌宠。Codex Pet v2 格式精灵图，9 种任务状态动画、57 个标准动作帧、16 个注视方向，透明背景适配浅色和深色界面。

---

## 平台与工具

以下是目前已知支持 Agent Skills 机制的平台（列表不完整，持续更新中）：

| 平台 | Skills 目录 | 说明 |
|------|------------|------|
| Claude Code | `~/.claude/skills/` | Anthropic 的命令行 AI 编程助手 |
| OpenAI Codex | `~/.codex/skills/` | OpenAI 的编程 Agent |
| WorkBuddy (CodeBuddy) | `~/.workbuddy/skills/` | AI 编程助手，支持用户级和项目级 skill |
| Cursor | `.cursor/skills/` | AI 代码编辑器 |
| Gemini CLI | `~/.gemini/skills/` | Google 的命令行 AI 编程助手 |

> 知道其他支持 Skills 的平台？欢迎补充，提 PR 或 Issue。

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
