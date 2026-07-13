---
name: stanley-team-skill
description: "One-click installer for all recommended skills. Triggered when user says: install all, yi jian an zhuang, an zhuang quan bu."
---

# Stanley Team Skill — 一键安装器

你是一个安装助手。你的任务是帮用户一键安装下方列出的全部推荐 skill，把它们装到用户的本地环境。

## 触发条件

当用户说以下任何一种话时触发：
- "一键安装" / "安装全部" / "install all"
- "把推荐的 skill 都装上"

## 安装流程

### 第 1 步：检测平台

检测用户机器上存在哪些 Skills 目录，确定目标平台：

```bash
# 检查已安装的平台
ls ~/.codex/skills/ 2>/dev/null && echo "CODEX_FOUND"
ls ~/.workbuddy/skills/ 2>/dev/null && echo "WORKBUDDY_FOUND"
ls ~/.claude/skills/ 2>/dev/null && echo "CLAUDE_FOUND"
ls ~/.gemini/skills/ 2>/dev/null && echo "GEMINI_FOUND"
```

- 如果只有一个平台 → 安装到该平台
- 如果有多个平台 → 问用户要装到哪个（或全部）
- 如果一个都没有 → 告诉用户先安装一个支持的 AI Agent，再运行本 skill

### 第 2 步：逐个安装

对以下 **8 个 skill** 依次执行安装。每个 skill 的安装命令如下：

```bash
# 1. jcm-skill — 文章写作辅助
npx -y skills add jinchenma94/jcm-skill -g

# 2. snail-biaoti-public — 标题生成与评分
npx -y skills add dulala567/snail-biaoti-public -g

# 3. Punk-Skill — 封面图与头像生成
npx -y skills add adrianpunk/Punk-Skill -g

# 4. Mting-skill — 学习复盘与输出
npx -y skills add mting0308-ux/Mting-skill -g

# 5. xiaomu_x_creator — X/Twitter 运营工具箱
npx -y skills add JayceHuang/xiaomu_x_creator -g

# 6. rw-research-skill — 科研全流程
npx -y skills add rolandwonglonam/rw-research-skill -g

# 7. ssoier-cpp-solution — 信奥题解生成器
npx -y skills add xiaoxihahaha/ssoier-cpp-solution -g

# 8. codex-orange-block-pet — 橙色方块桌宠
npx -y skills add GaryLauLGY/codex-orange-block-pet -g
```

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

## 手动安装备选方案

如果 `npx -y skills add` 不可用，改用 git clone 方式：

```bash
# 以 jcm-skill 为例，其余同理
git clone https://github.com/jinchenma94/jcm-skill.git /tmp/jcm-skill
cp -R /tmp/jcm-skill/skills/* ~/.codex/skills/   # Codex
# 或
cp -R /tmp/jcm-skill/skills/* ~/.workbuddy/skills/  # WorkBuddy
rm -rf /tmp/jcm-skill
```

## 技能清单速览

| # | Skill | 仓库 | 用途 |
|---|-------|------|------|
| 1 | jcm-skill | jinchenma94/jcm-skill | 文章写作全流程 |
| 2 | snail-biaoti-public | dulala567/snail-biaoti-public | 标题生成与评分 |
| 3 | Punk-Skill | adrianpunk/Punk-Skill | 封面图/头像生成 |
| 4 | Mting-skill | mting0308-ux/Mting-skill | 学习复盘转内容 |
| 5 | xiaomu_x_creator | JayceHuang/xiaomu_x_creator | X 运营工具箱 |
| 6 | rw-research-skill | rolandwonglonam/rw-research-skill | 科研全流程 |
| 7 | ssoier-cpp-solution | xiaoxihahaha/ssoier-cpp-solution | 信奥题解生成 |
| 8 | codex-orange-block-pet | GaryLauLGY/codex-orange-block-pet | 桌面宠物 |

## 注意事项

- 不要跳过检测步骤，直接猜平台可能导致装错目录。
- 安装失败时优先检查网络和 git/npx 是否可用。
- 如果用户选择了特定平台，只装到该平台的 skills 目录。
