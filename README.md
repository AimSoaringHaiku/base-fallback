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
