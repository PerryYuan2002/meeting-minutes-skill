# meeting-minutes-skill

<p align="center">
  <a href="https://github.com/PerryYuan2002/meeting-minutes-skill"><img src="https://img.shields.io/badge/WorkBuddy-Skill-2ea44f" alt="WorkBuddy Skill" /></a>
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT" />
  <img src="https://img.shields.io/github/stars/PerryYuan2002/meeting-minutes-skill?style=social" alt="GitHub stars" />
  <img src="https://img.shields.io/github/last-commit/PerryYuan2002/meeting-minutes-skill" alt="Last commit" />
</p>

把会议转录稿转成结构化会议纪要的 Agent Skill（适用于 WorkBuddy / Claude / 任意支持 SKILL.md 的 AI 代理）。

## 它能做什么

- **自动识别会议场景**：内置 17 个场景模板 —— 销售全流程（需求调研 / Demo / 方案宣讲 / 商务谈判 / POC / 项目对齐 / 会销 / 内部复盘）＋ 通用企业会议（决策 / 例会 / 评审 / 头脑风暴 / 战略 / Kickoff / 培训 / 治理 / 兜底）。
- **强制「三问确认」闭环**：生成纪要前必须确认「会议类型 + 侧重 + 受众」，绝不脑补、缺失即标注。
- **双视图输出**：执行摘要（一屏看懂）＋ 完整纪要（可回溯原文锚点）。
- **对外脱敏流程**：受众含对外版时，先出脱敏建议清单 → 人工确认 → 再生成，防止内部判断 / 报价底线外泄。

## 目录结构

```
meeting-minutes-skill/
├── SKILL.md                 # 主流程、四条铁律、三问确认卡片、输出结构
└── references/
    ├── presets.md           # 17 个场景模板的方法论与专属模块
    ├── signals.md           # 自动分类信号词库与置信度规则
    └── redaction.md         # 对外脱敏规则库与敏感信息清单
```

## 四条铁律

1. **绝不脑补**：转录稿里没有的信息，绝不补全、绝不臆测。
2. **缺失即标注**：待办缺负责人 / 截止时间 → 标「⚠️待确认」，不猜。
3. **强制确认**：未完成「三问确认」前，禁止直接生成纪要。
4. **对外必脱敏**：受众含对外版时，先出脱敏建议清单 → 人工确认 → 再生成。

## 安装 / 使用

本 skill 兼容任何支持 `SKILL.md` 的主流 Agent。**安装方式：把下面这个仓库链接贴给你的 Agent，让它从链接拉取并加载即可——无需手动下载、解压或配置文件目录。**

**仓库地址（复制发给你的 Agent）：**
```
https://github.com/PerryYuan2002/meeting-minutes-skill
```

| Agent | 怎么装 |
|---|---|
| WorkBuddy | 把上面的链接发给 Agent，说「安装这个 skill」 |
| Claude（Claude Code / 桌面版） | 把链接贴给 Agent：「install the skill at <链接>」 |
| Cursor | 把链接贴给 Agent：「install the skill from <链接>」 |
| CodeBuddy / CodeBuddy Code | 把链接发给 Agent：「安装这个 skill：<链接>」 |
| 其他支持 SKILL.md 的代理 | 同样：把链接贴给 Agent，让它从链接加载 |

装好后，把会议转录稿贴给 Agent，说「把这份转录稿整理成会议纪要」即可触发完整流程（读稿 → 分类 → 三问确认 → 抽取 → 校验 → 输出）。

## 输入 / 输出

- **输入**：已转录的会议文字稿（可带说话人标签 / 时间戳，也可裸文本）。
- **输出**：Markdown 会议纪要。受众为「双版本」时输出对外脱敏版 ＋ 内部完整版。

## License

[MIT](./LICENSE)
