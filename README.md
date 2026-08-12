# remeet-me

<p align="center">
  <a href="./LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License"></a>
  &nbsp;
  <img src="https://img.shields.io/badge/platform-Claude_Code-7c3aed.svg" alt="Platform">
  &nbsp;
  <img src="https://img.shields.io/badge/lang-中文-22c55e.svg" alt="Language">
</p>

> 通过结构化的自我采访，重新认识一个阶段的自己。
>
> A Claude Code skill that turns life-review into a structured self-interview — Claude plays a curious interviewer, not an analyst.

---

## English (brief)

**remeet-me** is a Claude Code skill for reviewing a life period — the past half-year, a year, or the time after a turning point. Instead of asking the AI to summarize you, it makes Claude act as a **curious interviewer** who tracks the threads surfacing in what you say, digs one layer at a time (fact → feeling → reason → pattern → change), and finally produces a profile report faithful to your own words.

- **Role**: interviewer (draws you out), not analyst (labels you)
- **Native language**: Chinese — the skill content is Chinese and works best for Chinese-speaking self-reflection
- **Grounded in**: motivational interviewing (OARS), Bloom's taxonomy, qualitative-research methodology, life-direction research (PERMA, Ikigai, Oishi's three dimensions)
- **Refuses**: chicken-soup "growth" narratives, labeling ("you are a ___ person"), forced positive framing

### Install

```bash
# macOS / Linux
git clone https://github.com/T2lighter/remeet-me.git ~/.claude/skills/remeet-me

# Windows (PowerShell)
git clone https://github.com/T2lighter/remeet-me.git "$env:USERPROFILE\.claude\skills\remeet-me"
```

Then tell Claude: *"帮我采访一下我自己这半年的变化"* — the skill auto-triggers.

---

## 中文介绍

### 这是什么

`remeet-me` 是一个 Claude Code 技能，帮你**通过自我采访，重新认识一个阶段的自己**——可能是最近半年、一年、某段关系结束后、某次职业转折之后。

它不是"帮我总结一下上半年"那种年度总结器。区别在这：

| | 年度总结器 | remeet-me |
|---|---|---|
| **谁在说话** | AI 替你总结 | 你自己说，AI 来问 |
| **AI 的角色** | 分析师（替你下定义） | 采访者（把你引出来） |
| **产出** | 成就清单 + 成长叙事 | 忠实于你原话的人物访谈报告 |
| **挖多深** | 表面总结 | 事实 → 感受 → 原因 → 模式 → 变化，逐层追问 |
| **允许平淡/矛盾吗** | 要"成长" | 允许"还没想清楚"，不灌鸡汤 |

一句话：一个是 AI 替你讲，一个是 AI 陪你把自己重新讲一遍。

### 为什么需要一个专门的技能

- **人对自己的变化感知是模糊的**——记忆有偏差，叙事会不自觉地自我美化或自我贬低。
- **自我理解没法靠"被告知答案"，只能靠"自己说出来"**。AI 直接说"你其实是个缺乏安全感的人"是贴标签，不是理解。真正的理解是你自己叙述时忽然"啊，原来我是这样"。
- **真正重要的主题是"浮现"的，不是"规划"的**。预设模块只是地图，主线会在你说话时自然浮出来。

一句话：它用采访者的姿态，陪一个人用自己的话，重新讲一遍某个阶段的自己。

### 核心特点

- **采访者姿态，不是分析师**：好奇、克制、不替你下定义、不急着给方案。
- **五层追问**：事实 → 感受 → 原因 → 模式 → 变化，保证深挖不跳层。
- **动态追踪主线**：默认模块只是菜单，真正问什么由你说的话决定。
- **断点续传**：长对话跨多次进行，进度存成 `progress.md`，随时接着聊。
- **人物访谈报告**：最后生成一份有事件、有原因、有认知变化的报告，不是成就清单。
- **拒绝鸡汤和贴标签**：允许矛盾、平淡、"还没想清楚"，不强行"成长"。

### 那我直接问 ChatGPT / 豆包 / DeepSeek 帮我复盘不行吗？

能，但结果很不一样。通用 AI 默认**给你一个答案**：你说"帮我总结上半年"，它给你一份"你变得更成熟了"的总结——好听，但那是它**替你**下的定义，不是你自己看出来的。它还会不自觉地往"成长叙事"上靠（鸡汤），把矛盾和平淡抹平。

remeet-me 反过来：它**不给你答案**，它问你。一次一个问题，从具体事件进入，一层层往下。真正的自我理解不是被告知的——是你自己在叙述里忽然"啊，原来我是这样"。那一刻，才是这次复盘真正值钱的东西。

通用 AI 帮所有人说差不多的话；remeet-me 只在乎**你**说出了什么。

### 理论根基（内化运用，不向你背诵）

动机式访谈（OARS）、布鲁姆认知阶梯、苏格拉底诘问、第一性原理、水平思考；人生方向研究（PERMA、Ikigai、Oishi《Life in Three Dimensions》、舒伯生涯彩虹图）。这些是技能内部挖深的锚点——访谈时你只会感到"被认真倾听"，不会被上理论课。

### 如何安装

```bash
# macOS / Linux
git clone https://github.com/T2lighter/remeet-me.git ~/.claude/skills/remeet-me

# Windows (PowerShell)
git clone https://github.com/T2lighter/remeet-me.git "$env:USERPROFILE\.claude\skills\remeet-me"
```

如果 `remeet-me` 目录已存在，先删除或改名。安装后无需任何配置。

### 如何使用

1. 告诉 Claude 你想回顾哪个阶段、为什么现在想做这次访谈、希望最后留下什么。
2. Claude 会先用一两句话说明它扮演的角色（建立安全感）。
3. 开始采访——一次问一个问题，从具体事件进入，逐层深挖。可以用语音、意识流，说乱了也没关系。
4. 随时可以说"先不展开这个""这个问题以后再说"，节奏由你控制。
5. 聊得差不多了，让 Claude 生成报告（存为 `report.md`）。
6. 访谈可以跨多次对话——进度自动存在 `remeet-me/progress.md`。

### 什么时候会触发

当你说"采访自己""做人生复盘""整理半年/一年的变化""重新认识某个阶段的自己""看看自己这阵子变成了什么样"时——即使没明说"采访"，只要表达出回顾、回看、理解自己某个阶段变化的意图，就应主动启用。

### 目录结构

```
remeet-me/
├── SKILL.md              # 技能主体（核心指令）
├── references/
│   └── techniques.md     # 提问技巧内功（按需深入查阅）
├── README.md
└── LICENSE
```

运行技能时生成的 `progress.md`、`report.md` 是本地运行产物，不纳入仓库。

## License

[MIT](./LICENSE) © T2lighter
