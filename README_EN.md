# meeting-minutes-skill

<p align="center">
  <a href="https://github.com/PerryYuan2002/meeting-minutes-skill"><img src="https://img.shields.io/badge/WorkBuddy-Skill-2ea44f" alt="WorkBuddy Skill" /></a>
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT" />
  <img src="https://img.shields.io/github/stars/PerryYuan2002/meeting-minutes-skill?style=social" alt="GitHub stars" />
  <img src="https://img.shields.io/github/last-commit/PerryYuan2002/meeting-minutes-skill" alt="Last commit" />
</p>

<p align="center">
  <a href="./README_EN.md">🇺🇸 English</a> · <a href="./README.md">🇨🇳 中文</a>
</p>

An Agent skill that turns meeting transcripts into structured meeting minutes (for WorkBuddy / Claude / any agent that supports `SKILL.md`).

## What it does

- **Auto-detects the meeting scenario**: 17 built-in presets — the full sales cycle (discovery / demo / proposal / negotiation / POC / delivery / event / internal review) plus general business meetings (decision / standup / review / brainstorm / strategy / kickoff / training / governance / fallback).
- **Mandatory 3-question confirmation**: before producing minutes it confirms "meeting type + focus + audience" — no guessing, gaps are flagged.
- **Dual-view output**: an executive summary (scan in one screen) plus the full minutes (with anchors back to the source).
- **External redaction flow**: when the audience includes an external version, it first lists redaction suggestions → waits for human confirmation → then generates, preventing internal judgments / price floors from leaking.

## Four iron rules

1. **Never fabricate**: never fill in or assume anything not present in the transcript.
2. **Flag what's missing**: if an action item lacks an owner / due date, mark it "⚠️ TBD" — don't guess.
3. **Confirm first**: never generate minutes before the 3-question confirmation is done.
4. **Redact for external use**: when the audience includes an external version, list redaction suggestions → confirm → then generate.

## Directory structure

```
meeting-minutes-skill/
├── SKILL.md                 # main flow, four iron rules, 3-question card, output structure
└── references/
    ├── presets.md           # methodology & modules for the 17 scenario presets
    ├── signals.md           # signal lexicon & confidence rules for auto-classification
    └── redaction.md         # external redaction rules & sensitive-info checklist
```

## Install / Use

**One-click install**: copy the whole line below and paste it to your Agent:

```
Install this skill for me: https://github.com/PerryYuan2002/meeting-minutes-skill
```

**How to use**
- Paste your meeting transcript into the chat.
- Tell the AI: "Summarize this into meeting minutes".
- Confirm the three questions it asks, and it outputs the minutes.

## License

[MIT](./LICENSE)
