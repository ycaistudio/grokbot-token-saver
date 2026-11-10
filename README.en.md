# Grok Bot Token Saver (v1.0.0)
**Universal skill to make a multi-bot team's weekly usage pool last the whole week**  
*多 bot 團隊「同一個每週額度用足成個星期」通用 Skill*  
*複数ボット運用で週間使用枠を一週間もたせる汎用スキル*

Grok Bot · Claude Code · Cursor · OpenAI · Local LLMs

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform](https://img.shields.io/badge/platform-Cross--Platform-lightgrey.svg)](https://github.com/ycaistudio/grokbot-token-saver)
[![i18n](https://img.shields.io/badge/i18n-繁體中文%20%7C%20English%20%7C%20日本語-green.svg)](https://github.com/ycaistudio/grokbot-token-saver)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/ycaistudio/grokbot-token-saver/pulls)

---

<p align="center">
  <b>🌐 Language Navigation / 多語言切換 / 言語切り替え:</b><br>
  <a href="README.md"><b>🇹🇼 繁體中文（主手冊）</b></a> •
  <a href="README.en.md"><b>🇬🇧 English</b></a> •
  <a href="README.ja.md"><b>🇯🇵 日本語</b></a>
</p>

---

## 📖 What is this?

In early November 2026 many Grok Bot users woke up to a weekly meter at 100% with days left before reset.  
Most of that pool was never spent on real work: routines waking up with nothing to do, bots re-reading weeks of chat, and four bots answering one question.

**Token Saver** is a drop-in skill in two parts:

- **Part 1 (10 tips)**: condensed from [@vartekxx](https://x.com/vartekxx)'s article "[GrokBot Token Usage: how to never hit your limit again in 10 step](https://x.com/vartekxx/status/2119105285851656535)".
- **Part 2 (12 field notes)**: habits from our own family setup of about 20 bots, in daily use.

---

## 🛡️ Why?

| Where usage leaks | What to do |
| :--- | :--- |
| Routines wake every 15 minutes even when nothing changed | Hourly or slower; switch to event triggers |
| Long chats re-read on every reply | Handoff note + fresh bot, or reincarnate with [bot-reincarnation](https://github.com/ycaistudio/bot-reincarnation) |
| Several bots answer in one group chat | One owner per job; max 2 bot-to-bot messages per task |
| Open-ended tasks keep exploring | State scope, finish line, stop rule and word limit |
| Clicking through a browser | Use a connector when one can do the step |
| Asking several decisions back and forth | Label A/B/C with options [1][2]; the user replies "A1 B2" once |
| Retrying the same error | Stop after three, try one different method at most, then report |

---

## 🧩 Contents

**Part 1: 10 tips (source: @vartekxx)**
1. Check the meter and reset date
2. Audit routines, repeat jobs and group chats (list only)
3. Slow routines down
4. Swap schedules for event triggers
5. Move long jobs to a fresh bot
6. Group chat rules
7. Give every task a finish line
8. Use connectors instead of the browser
9. Turn repeat work into skills
10. Switch to low-usage mode at about 80%

**Part 2: field notes (11–22)**  
One-shot concise replies, high-risk-only warnings, batched decisions, a three-strikes loop guard, non-waking rule notices to affected bots only, on-demand script-built dashboards, one-line status logs, merging new reports into existing daily routines, weekly (not daily) maintenance, pausing unused schedules, bot reincarnation, and approvals given directly rather than relayed.

Full steps are in [`SKILL.md`](SKILL.md) (written in Traditional Chinese / Cantonese).

---

## 🚀 How to use

1. Paste the whole [`SKILL.md`](SKILL.md) to your Primary Bot and ask it to save it as a skill.
2. Call it in chat with `@grok-bot-usage-saving`.
3. Suggested first step: run tip 2, the audit, which lists but changes nothing; then decide what to change.

The skill requires your approval before any routine is changed, paused or deleted.

---

## 🙏 Credits

- Part 1's tips and prompt ideas come from [@vartekxx](https://x.com/vartekxx/status/2119105285851656535). Thank you for sharing.
- Not affiliated with SpaceXAI or Cursor. No official usage numbers are published; treat these as rules of thumb.

## 📜 License

MIT License
