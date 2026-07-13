---
name: stanley-team-skill
description: "Stanley Team Skill installer. Triggered ONLY when user says: Stanley install, stanley team install. Installs all recommended skills from the list."
---

# Stanley Team Skill — 一键安装器

你是一个安装助手。你的任务是帮用户一键安装下方列出的全部推荐 skill，把它们装到用户当前使用的 AI Agent 的 skills 目录。

## 触发条件

仅当用户说出**包含 "Stanley" 关键词**的安装指令时才触发：

- "Stanley install" / "Stanley 安装"
- "Stanley team install" / "Stanley team 安装"
- "用 Stanley 安装全部"

**不要被普通的"一键安装"或"install all"触发**——这些词太通用，可能匹配到别的 skill。只有带 "Stanley" 的指令才执行本 skill。

## 安装流程

### 第 1 步：确定用户的 AI Agent skills 目录

**不要问用户**，直接检测。按顺序检查以下目录，找到第一个存在的：

```bash
ls ~/.workbuddy/skills/ 2>/dev/null && echo "WORKBUDDY_FOUND"
ls ~/.codex/skills/ 2>/dev/null && echo "CODEX_FOUND"
ls ~/.claude/skills/ 2>/dev/null && echo "CLAUDE_FOUND"
ls ~/.gemini/skills/ 2>/dev/null && echo "GEMINI_FOUND"
ls ~/.agents/skills/ 2>/dev/null && echo "AGENTS_FOUND"
```

- 如果找到多个，优先使用用户当前正在对话的那个平台（本 skill 就装在那个平台里）
- 如果只有一个，直接用那个
- 如果一个都没有，告诉用户先安装一个 AI Agent

### 第 2 步：逐个安装

对以下 **8 个 skill** 依次安装。用 `npx skills add --all --copy`：

```bash
# 1. jcm-skill — 文章写作辅助
npx -y skills add jinchenma94/jcm-skill -g --all --copy

# 2. snail-biaoti-public — 标题生成与评分
npx -y skills add dulala567/snail-biaoti-public -g --all --copy

# 3. Punk-Skill — 封面图与头像生成
npx -y skills add adrianpunk/Punk-Skill -g --all --copy

# 4. Mting-skill — 学习复盘与输出
npx -y skills add mting0308-ux/Mting-skill -g --all --copy

# 5. xiaomu_x_creator — X/Twitter 运营工具箱
npx -y skills add JayceHuang/xiaomu_x_creator -g --all --copy

# 6. rw-research-skill — 科研全流程
npx -y skills add rolandwonglonam/rw-research-skill -g --all --copy

# 7. ssoier-cpp-solution — 信奥题解生成器
npx -y skills add xiaoxihahaha/ssoier-cpp-solution -g --all --copy

# 8. codex-orange-block-pet — 橙色方块桌宠
npx -y skills add GaryLauLGY/codex-orange-block-pet -g --all --copy
```

8 个 skill 的仓库地址：

| # | Skill | 仓库 URL | 用途 |
|---|-------|----------|------|
| 1 | jcm-skill | https://github.com/jinchenma94/jcm-skill.git | 文章写作全流程 |
| 2 | snail-biaoti-public | https://github.com/dulala567/snail-biaoti-public.git | 标题生成与评分 |
| 3 | Punk-Skill | https://github.com/adrianpunk/Punk-Skill.git | 封面图/头像生成 |
| 4 | Mting-skill | https://github.com/mting0308-ux/Mting-skill.git | 学习复盘转内容 |
| 5 | xiaomu_x_creator | https://github.com/JayceHuang/xiaomu_x_creator.git | X 运营工具箱 |
| 6 | rw-research-skill | https://github.com/rolandwonglonam/rw-research-skill.git | 科研全流程 |
| 7 | ssoier-cpp-solution | https://github.com/xiaoxihahaha/ssoier-cpp-solution.git | 信奥题解生成 |
| 8 | codex-orange-block-pet | https://github.com/GaryLauLGY/codex-orange-block-pet.git | 桌面宠物 |

### 第 3 步：逐个确认

每安装完一个，向用户报告：
```
✅ [1/8] jcm-skill 安装成功
```

如果某个安装失败，记录错误并继续下一个，不要中断。最后汇总：
```
安装完成：成功 7 个，失败 1 个
❌ rw-research-skill 安装失败：<错误信息>
```

### 第 4 步：完成提示

全部安装完成后，告诉用户：
```
🎉 全部 8 个 skill 安装完成！重启你的 AI Agent 即可使用。
```

## 安装示例

假设检测到目标目录是 `~/.codex/skills/`，安装 jcm-skill 的完整命令：

```bash
npx -y skills add jinchenma94/jcm-skill -g --all --copy
```

## 注意事项

- 用 `npx -y skills add {作者}/{仓库} -g --all --copy` 逐个安装。
- 一定要先检测目录再安装，不要猜平台。
- Windows 用户用 `cp -R` 时可能需要用 Git Bash 或 WSL。
- 如果 npx 安装失败，检查网络连接。
