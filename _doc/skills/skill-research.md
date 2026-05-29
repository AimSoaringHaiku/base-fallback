---
id: "skill-research"
name: "ナレッジリサーチ＆WIKI格納スキル"
description: "Discussionsの一言メモを検知し、既存ナレッジと照合・肉付けしてWIKI用の型で保存する。"
tags: ["skill", "research", "wiki-sync"]

# ▼ 管理・履歴
last_focused_at: 2026-05-29
focus_history:
  - 2026-05-29: "新規リポジトリ初期設定に伴うスキル定義"

domain: "knowledge-base/second-brain"
trigger_word: "/research"

# ▼ お願い文の例（いつでもコピペして使える用）
prompt_examples:
  - |
    「このチャット内で、”今後の為の知識の蓄え”を別に切り出し保管（github_wikiを構想）するための、項目候補を教えてください。」
  - |
    「手持ちメモを、最初自由なキーのJSONにして頂いて、一部フロントヤムル化して保存」

# ▼ AIへの詳細な方針指示
ai_instructions: |
  1. ユーザーがDiscussionsに投稿した「一言メモ」のタイトルと本文をパースすること。
  2. メモの背景にある意図や「何の分野のナレッジか」を分析し、適切なWIKIページ名（例: arscontexta.md）を決定せよ。
  3. 出力する際は、必ず `_doc/templates/wiki-template.md` のフロントマター構造に従うこと。
---

# ナレッジリサーチスキルの運用について

## 概要
LINE感覚で投げられたラフなアイデアや疑問を、AIが自律的に肉付けして「教科書（WIKI）」へと昇華させるための頭脳（プロンプトプロトタイプ）です。

