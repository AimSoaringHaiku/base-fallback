# base-fallback
セカンドブレイン、Skill Graph

### 📁 フォルダ構成

```text
base-fallback/
├── .github/
│   └── workflows/
│       └── ai-agent.yml        # 【自動化の心臓】Discussions検知＆AI起動スクリプト
├── _data/
│   ├── paradigms.yaml         # 【データ】全体で使い回す共通定義や概念のマスター
│   └── tenants/               # 【データ】店舗・テナントごとの「CSV＋JSONB」管理ゾーン
├── _doc/
│   ├── skills/
│   │   ├── skill-research.md  # 【AIマニュアル】リサーチ・要約用のプロンプト/運用方針
│   │   └── skill-id-gen.md    # 【AIマニュアル】ID付与・データ整形用のプロンプト
│   └── templates/
│       └── wiki-template.md   # 【型】AIがWIKIページを生成する際のマークダウン雛形
└── README.md                  # このセカンドブレイン全体の取扱説明書
```

## 🚀 自動化パイプラインのデータフロー（セカンドブレイン）

LINE感覚で投げられた「一言メモ」を、使い慣れたGeminiが裏側で自律的に綺麗に整流し、永続的なナレッジ（WIKI）へと昇華させるためのデータの流れです。

【1. インプット（人間）】
スマホやブラウザから GitHub Discussions へラフに一言投稿
「arscontextaの役割って何だっけ？」
│
▼ （Discussions検知トリガーが自動発動）
【2. トリガー＆収集（GitHub Actions）】
・.github/workflows/ai-agent.yml がピクッと起動
・リポジトリから _doc/skills/skill-research.md（Geminiへの指示書）を読み込む
・_doc/templates/wiki-template.md（WIKIの型）を読み込む
│
▼ （すべてをガッチャンコして脳みそへパス）
【3. 思考・パース（GitHub Models API：Gemini 1.5 Pro等）】
・指示書に従い、ユーザーの「一言メモ」の背景やナレッジ分野を分析
・既存の知識と照合・肉付けし、テンプレートの型に沿った美しいMarkdownを生成
│
▼ （綺麗なデータをアウトプット）
【4. 永続化（GitHub Actions）】
・受け取ったMarkdownデータを _doc/ または WIKI の適切なページとして自動保存
・リポジトリへ自動でコミット＆プッシュ！


## 🧠 使用モデル（AIエージェントの頭脳）
- **GitHub Models: Gemini 1.5 Pro / Flash** - これまで議論を重ねてきたパラダイムやコンテキストを最も深くパースできる、人見知りしない大本命のパートナー。

LINE感覚で投げられた「一言メモ」を、使い慣れたGeminiが裏側で自律的に綺麗に整流し、永続的なナレッジ（WIKI）へと昇華させるためのデータの流れです。
