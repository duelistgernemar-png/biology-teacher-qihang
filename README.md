# biologyqihang

北京启航杯高中生物模拟评委打分与改进建议 Skill。

这个 skill 用于帮助高中生物教师准备北京市/辖区“启航杯”教学展示、教学设计评比、课堂实录打磨和教学反思修改。它会按照“教学设计、课堂实录、教学反思”三个部分进行证据化评分，并给出可直接修改材料的建议。

## 功能

- 模拟启航杯高中生物评委视角打分
- 评价教学设计、课堂实录脚本、说课稿、教学反思或参赛材料包
- 按 40/50/10 结构区分教学设计、课堂实录、教学反思
- 只根据已有证据评分，缺少课堂实录时不会硬凑 100 分
- 提炼材料优势、扣分风险和优先改进建议
- 对标高中生物获奖案例中的高分模式
- 生成可直接替换的核心问题、学习目标、评价标准、思政表达等文本

## 适合场景

- 启航杯高中生物参赛前自查
- 教学设计初稿诊断
- 课堂实录脚本优化
- 教学反思补强
- 生物公开课、展示课、区级评比材料打磨
- 教研组内模拟评审

## 安装

### Codex

Windows PowerShell:

```powershell
git clone https://github.com/duelistgernemar-png/biology-teacher-qihang.git "$env:USERPROFILE\.codex\skills\biologyqihang"
```

然后重启 Codex，或开启一个新会话。

### Claude Code

如果你的 Claude Code 支持本地 skills，可以放入 skills 目录：

```powershell
git clone https://github.com/duelistgernemar-png/biology-teacher-qihang.git "$env:USERPROFILE\.claude\skills\biologyqihang"
```

Claude Code 可能会忽略 `agents/openai.yaml`，但会使用核心的 `SKILL.md` 和 `references/`。

### OpenClaw

如果你的 OpenClaw 支持 `SKILL.md` 形式的本地 skill，可以安装到本地 skills 目录，例如：

```powershell
git clone https://github.com/duelistgernemar-png/biology-teacher-qihang.git "$env:USERPROFILE\.openclaw\skills\biologyqihang"
```

不同 OpenClaw 配置可能使用不同 skills 路径，请以你的平台设置为准。

## 调用示例

安装后，可以这样对 agent 说：

```text
请使用 biologyqihang，帮我模拟启航杯高中生物评委打分，并给出改进建议。
```

也可以更具体：

```text
请使用 biologyqihang，评价这个《种群数量的变化》教学设计，按启航杯标准给分，并指出最影响获奖的三处问题。
```

```text
请使用 biologyqihang，帮我修改这个高中生物教学反思，让它更符合启航杯评委关注点。
```

```text
请使用 biologyqihang，根据这份课堂实录判断教学设计是否真正落地，并给出课堂实施改进建议。
```

## 输入材料

可以提供以下任意一种或多种材料：

- 教学设计 PDF / DOCX / 文本
- 课堂实录文本或视频观察记录
- 说课稿
- 教学反思
- 学案、板书、评价量规、学生作品
- 参赛主题或初步构思

如果只提供教学设计，skill 会只评教学设计部分，不会假装已经看到了课堂实录。

## 评分结构

默认采用启航杯参赛结构：

| 模块 | 分值 |
|---|---:|
| 教学设计 | 40 |
| 课堂实录 | 50 |
| 教学反思 | 10 |

评分重点包括：

- 课标、教材、学情分析是否具体
- 学习目标是否可观察、可评价
- 核心问题与问题链是否清晰
- 活动是否体现学生主体和证据推理
- 是否有学生产出物
- 是否体现教-学-评一致性
- 数字技术是否解决真实学习难点
- 课程思政是否从生物学内容自然生长
- 教学反思是否基于课堂证据提出改进

## 输出内容

默认输出中文评审报告，包括：

- 总体判断
- 模拟评分表
- 优势提炼
- 扣分风险
- 优先改进建议
- 可直接替换文本

## 文件结构

```text
biologyqihang/
  SKILL.md
  README.md
  agents/
    openai.yaml
  references/
    rubric.md
    winning_patterns.md
```

## 注意

这个 skill 是模拟评审工具，不能替代真实评委意见。评分会受到输入材料完整度影响：材料越完整，判断越可靠。
