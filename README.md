# 慳用量 / Grok Bot Token Saver (v1.1.1)
**多 bot 團隊「同一個每週額度用足成個星期」通用 Skill**  
*Universal skill to make a multi-bot team's weekly usage pool last the whole week*  
*複数ボット運用で週間使用枠を一週間もたせる汎用スキル*

Grok Bot · Claude Code · Cursor · OpenAI · Local LLMs

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform](https://img.shields.io/badge/platform-Cross--Platform-lightgrey.svg)] [`https://github.com/ycaistudio/grokbot-token-saver`](https://github.com/ycaistudio/grokbot-token-saver) 
[![i18n](https://img.shields.io/badge/i18n-繁體中文%20%7C%20English%20%7C%20日本語-green.svg)] [`https://github.com/ycaistudio/grokbot-token-saver`](https://github.com/ycaistudio/grokbot-token-saver) 
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/ycaistudio/grokbot-token-saver/pulls)

---

<p align="center">
  <b>🌐 Language Navigation / 多語言切換 / 言語切り替え:</b><br>
  <a href="README.md"><b>🇹🇼 繁體中文（主手冊）</b></a> •
  <a href="README.en.md"><b>🇬🇧 English</b></a> •
  <a href="README.ja.md"><b>🇯🇵 日本語</b></a>
</p>

---

## 📖 這是什麼？

2026 年 11 月初，好多 Grok Bot 用家一覺醒來發現每週用量去到 100%，離重置仲有幾日。  
其實大部分用量唔係用喺真正嘅工作：routine 冇嘢做都照醒、bot 每次重讀幾個星期嘅對話、四個 bot 答同一條問題。

**慳用量** 係一個可以直接放入 bot 嘅 skill，分兩部分：

- **第一部分（10 招）**：整理自 [@vartekxx](https://x.com/vartekxx) 嘅文章〈[GrokBot Token Usage: how to never hit your limit again in 10 step](https://x.com/vartekxx/status/2119105285851656535)〉。
- **第二部分（12 條實戰補充）**：嚟自我哋一個大約 20 個 bot 嘅家庭團隊，每日實際用緊。

---

## 🛡️ 點解需要？

| 漏用量嘅地方 | 對應做法 |
| :--- | :--- |
| routine 每 15 分鐘醒一次，冇新嘢都照跑 | 拉疏到每小時或以下，改用事件觸發 |
| bot 對話越拉越長，每次回覆都重讀 | 交接筆記 + 新 bot，或者用 [bot-reincarnation] [`https://github.com/ycaistudio/bot-reincarnation`](https://github.com/ycaistudio/bot-reincarnation)  投胎 |
| 群組入面幾個 bot 一齊答 | 一件工作一個負責 bot，bot 對 bot 每個任務最多 2 條訊息 |
| 任務冇終點，bot 一直探索 | 寫明範圍、完成標準、停止條件、輸出字數 |
| 用瀏覽器逐步撳 | connector 做得到就直接用 |
| 幾個決定來回問幾次 | 標 A、B、C 同【1】【2】，用家一句「A1 B2」答晒 |
| 同一個錯一直重試 | 錯三次就停，最多試一個新方法再報告 |

---

## 🧩 內容一覽

**第一部分：10 招（來源：@vartekxx）**
1. 睇用量表同重置日
2. 盤點 routine、重複工作同群組（只列唔改）
3. 拉疏 routine
4. 改用事件觸發
5. 長期工作交接俾新 bot
6. 群組規則
7. 任務要有終點
8. 用 connector 代替瀏覽器
9. 重複工作存成 skill
10. 用到 80% 轉低用量模式

**第二部分：實戰補充（11–22）**  
一次講啱、只講高風險、決定一次過問晒、錯誤停止規則、改規則只通知受影響嘅 bot（唔叫醒）、儀表板按需要先用程式生成、狀態紀錄一行過、新報告併入現有日報、維護工作每週一次、暫停唔用嘅排程、bot 投胎、審批唔經轉述。

詳細步驟睇 [`SKILL.md`](SKILL.md)。

---

## 🚀 點樣用？

1. 將本 repo 條 link [`https://github.com/ycaistudio/grokbot-token-saver`](https://github.com/ycaistudio/grokbot-token-saver) 俾你嘅 Primary Bot，叫佢「讀 SKILL.md 存做 skill」，唔使自己複製全文。
2. 之後喺對話打 `@grok-bot-usage-saving` 就用得。
3. 建議第一步：叫佢做第 2 招「盤點」，只列唔改，再由你決定改邊樣。

所有改 routine、暫停、刪除嘅動作，skill 都要求先經你批准。

---

## 🔗 姊妹 Skill：BOT 投胎（bot-reincarnation）

[**BOT 投胎 / Bot Reincarnation**] [`https://github.com/ycaistudio/bot-reincarnation`](https://github.com/ycaistudio/bot-reincarnation)  會開一個**新 bot（新 bot ID）**，將舊 bot 嘅記憶、守則、skill、profile、routine、權限同連接全部交接過去，但**刻意唔帶對話紀錄**，chat 由零開始。過程有身分登記表、長期交接文件同三欄清單；舊 bot 唔會自動刪，要主人確認後自己手動刪。

觸發詞：`投胎`、`換 bot ID`，或者 `duplicate yourself, everything including logged in tokens stays, except chat history -- start chat from scratch`。

### 一連串用法：慳用量 → 投胎 → 再慳

| 步驟 | 用邊個 | 做咩 |
| :--- | :--- | :--- |
| 1 | 慳用量 第 2 招 | 盤點，搵出最食用量嘅 routine、群組同**對話最長嘅 bot** |
| 2 | 慳用量 第 3–4、6 招 | 拉疏 routine、改事件觸發、定群組規則（經你批准） |
| 3 | **BOT 投胎** | 將對話最長嘅 bot 投胎，記憶同權限保留，長對話唔帶走 |
| 4 | 慳用量 第 9、11–22 招 | 新 bot 一開始就跟住慳用量守則做嘢 |
| 5 | 每週睇一次用量表 | 去到 80% 就用第 10 招轉低用量模式；某個 bot 對話又變長，就返去第 3 步 |

兩個 skill 都存入 Primary Bot 之後，可以直接講：「用 @grok-bot-usage-saving 盤點，搵出要投胎嘅 bot」。

---

## 🙏 鳴謝

- 第一部分嘅 10 招同提示詞概念嚟自 [@vartekxx](https://x.com/vartekxx/status/2119105285851656535)，多謝原作者分享。
- 本 repo 同 SpaceXAI、Cursor 冇關係。官方未公佈用量數字，以上全屬經驗之談。

## 📜 授權

MIT License
