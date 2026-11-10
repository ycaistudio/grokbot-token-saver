# Grok Bot Token Saver・使用量節約 (v1.1.1)
**複数ボット運用で週間使用枠を一週間もたせる汎用スキル**  
*Universal skill to make a multi-bot team's weekly usage pool last the whole week*  
*多 bot 團隊「同一個每週額度用足成個星期」通用 Skill*

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

## 📖 これは何？

2026 年 11 月初め、多くの Grok Bot ユーザーが、リセットまで数日残っているのに週間使用量が 100% に達していることに気付きました。  
使用量の大半は実際の作業ではなく、何もないのに起動するルーティン、数週間分の会話の読み直し、同じ質問に答える複数のボットに消えています。

**Token Saver** はボットにそのまま入れられるスキルで、二部構成です。

- **第一部（10 のコツ）**：[@vartekxx](https://x.com/vartekxx) さんの記事「[GrokBot Token Usage: how to never hit your limit again in 10 step](https://x.com/vartekxx/status/2119105285851656535)」を整理したもの。
- **第二部（12 の実践メモ）**：約 20 体のボットを使う私たち家族が、毎日実際に使っている習慣。

---

## 🛡️ なぜ必要？

| 使用量が漏れる所 | 対策 |
| :--- | :--- |
| 何も変わらなくても 15 分ごとに起動するルーティン | 1 時間ごと以下に減らし、イベントトリガーに切り替える |
| 長い会話を毎回読み直す | 引き継ぎメモ＋新しいボット、または [bot-reincarnation](https://github.com/ycaistudio/bot-reincarnation) で転生 |
| グループで複数のボットが同時に答える | 仕事ごとに担当ボットは一体、ボット間メッセージは 1 タスク最大 2 通 |
| 終わりのないタスク | 範囲、完了条件、停止条件、文字数上限を書く |
| ブラウザで一つずつクリック | コネクタでできる手順はコネクタを使う |
| 複数の判断を何度も往復して聞く | A・B・C と【1】【2】で並べ、ユーザーは「A1 B2」と一度で答える |
| 同じエラーを何度も再試行 | 3 回で止め、別の方法を最大 1 回試して報告 |

---

## 🧩 内容

**第一部：10 のコツ（出典：@vartekxx）**
1. 使用量メーターとリセット日を確認
2. ルーティン、繰り返し作業、グループチャットを棚卸し（一覧のみ、変更しない）
3. ルーティンの頻度を下げる
4. スケジュールをイベントトリガーに
5. 長期の仕事は新しいボットへ引き継ぐ
6. グループチャットのルール
7. タスクにゴールを決める
8. ブラウザよりコネクタ
9. 繰り返し作業はスキル化
10. 約 80% で低使用量モードへ

**第二部：実践メモ（11〜22）**  
一度で簡潔に答える、高リスクのみ伝える、判断をまとめて聞く、3 回ルールの停止、ルール変更は影響するボットだけに起こさず通知、ダッシュボードは必要時にスクリプトで生成、状態ログは一行、新しいレポートは既存の日報に統合、メンテナンスは週一回、使わないスケジュールは一時停止、ボット転生、承認は転送せず本人から直接。

詳しい手順は [`SKILL.md`](SKILL.md)（繁体字中国語・広東語）をご覧ください。

---

## 🚀 使い方

1. このリポジトリのリンク（https://github.com/ycaistudio/grokbot-token-saver）を Primary Bot に送り、`SKILL.md` を読んでスキルとして保存するよう頼みます。全文を貼り付ける必要はありません。
2. 以後はチャットで `@grok-bot-usage-saving` と呼び出せます。
3. 最初のおすすめ：コツ 2 の棚卸しを実行（一覧のみで変更なし）、その後どれを変えるか決めます。

ルーティンの変更・一時停止・削除は、必ず事前にあなたの承認が必要です。

---

## 🔗 姉妹スキル：ボット転生（bot-reincarnation）

[**BOT 投胎 / Bot Reincarnation**](https://github.com/ycaistudio/bot-reincarnation) は**新しいボット（新しいボット ID）**を作り、旧ボットの記憶・ルール・スキル・プロフィール・ルーティン・権限・接続をすべて引き継ぎますが、**会話履歴はあえて持ち込みません**。ID 登録表、長期引き継ぎファイル、三列チェックリストで漏れを防ぎ、旧ボットは自動削除せず、確認後に持ち主が手動で削除します。

トリガー：`duplicate yourself, everything including logged in tokens stays, except chat history -- start chat from scratch`（または `投胎`）。

### 連続して使う：節約 → 転生 → 節約を続ける

| 手順 | スキル | 内容 |
| :--- | :--- | :--- |
| 1 | Token Saver コツ 2 | 棚卸し：使用量の多いルーティン、グループ、**会話が最も長いボット**を見つける |
| 2 | Token Saver コツ 3〜4、6 | 頻度を下げ、トリガー化し、グループのルールを決める（承認後） |
| 3 | **ボット転生** | 会話が長いボットを転生：記憶と権限は残し、長い会話は持ち込まない |
| 4 | Token Saver コツ 9、11〜22 | 新しいボットは最初から節約ルールで動く |
| 5 | 毎週メーターを確認 | 約 80% でコツ 10（低使用量モード）、会話がまた長くなったら手順 3 へ |

両方のスキルを Primary Bot に保存したら、「@grok-bot-usage-saving で棚卸しして、転生すべきボットを教えて」と言うだけです。

---

## 🙏 謝辞

- 第一部のコツとプロンプトのアイデアは [@vartekxx](https://x.com/vartekxx/status/2119105285851656535) さんによるものです。共有に感謝します。
- 本リポジトリは SpaceXAI および Cursor とは無関係です。公式の使用量数値は公開されていないため、経験則として扱ってください。

## 📜 ライセンス

MIT License
