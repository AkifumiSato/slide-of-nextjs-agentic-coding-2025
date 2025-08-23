---
theme: default
background: https://images.unsplash.com/photo-1679362003950-8f3e1931554e?q=80&w=2428&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
class: text-center
highlighter: shiki
lineNumbers: false
colorSchema: "dark"
drawings:
  persist: false
transition: slide-left
title: Next.jsとAgentic Coding
mdc: true
---

# Next.jsと<br>Agentic Coding

in Findy's event 202508

---

# Profile

<div class="pb-5">
  <img src="https://avatars.githubusercontent.com/u/25711332?v=4" width="100" height="100">
</div>

```jsonc
// profile.jsonc
{
  "name": "佐藤 昭文",
  "alias": ["akfm_sato", "あっきー"],
  "job": "フロントエンドエキスパート",
  "tags": ["Next.js", "React", "Test", "リーン開発"],
  "sns": {
    "x": "akfm_sato",
    "zenn.dev": "akfm",
  },
}
```

---

# テーマ: AI Agent時代の『実践Next.js』

AI Agent時代における、Next.jsの開発のあり方について

- 今日話すこと
  - Next.js×AI駆動開発の実践的なテクニック
  - 僕が実践してる開発のテクニック
- 今日話さないこと
  - 『Next.jsの考え方』にある内容
  - Next.jsの最新動向

※[Zennの記事](https://zenn.dev/akfm/articles/agent-read-the-nextjs-way)と内容が一部被ってますが、もうちょっと細かい話もします。

---
layout: statement
---

## 僕が普段意識してるポイントを<br>伝えられたらいいなと思ってます

---
layout: section
---

# はじめに:<br>Next.jsとAI

主題に入る前にNext.jsとAIに関して知っておきたいこと

---
transition: fade
---

# AI時代におけるVercel Inc.の戦略

Next.jsを中心とした全方位戦略

- _**Next.js**_: 人気なフレームワーク=AIも生成しやすい
- _**Vercel**_: Next.jsを最も容易にデプロイできるプラットフォーム
- _**v0.app/v0.dev**_: Next.jsやVercelと強く統合されたAIプラットフォーム

参考: Vercel社員の上杉さんが出演した[Qiita FM](https://corp.qiita.com/releases/2025/03/podcast-uesugi/)

---

# AI時代におけるVercel Inc.の戦略

Next.jsを中心とした全方位戦略

- Vercelは早い段階で「これからはAI」と言い切ってた
- VercelのAIプロダクト=`v0.app`
- `v0.app`はNext.jsと強く統合されてる

<span class="font-bold" v-mark="{ color: 'red', type: 'underline' }">VercelのAI戦略はNext.jsの人気の上に成り立ってる</span>

---

# Next.jsはAIと親和性が高い？

AIの特性とVercelの戦略から考察

- 人気なフレームワークはAIの学習データも豊富
- `v0.app`と統合するため、AIフレンドリーな設計や機能の需要が高い

---

# Next.jsとAIの現在地

まだまだAI時代黎明期

- 初期構築: `v0.app`により非常に高速になった
- 既存アプリケーション・スケール: `v0.app`のスコープ外
  - Calude Codeなど3rd partyなAIツールを使うのがベスト

---
layout: statement
---

## Next.jsでAI駆動開発するには、まだまだ工夫が必要

---
layout: section
---

# Next.jsとAIを統合する<br>プラクティス

生産性向上の鍵

---

# 4つのプラクティス

僕が普段重要だと考えてるプラクティス4つ

1. 最適なツール・モデル選び
1. AIへのフィードバックサイクル
1. 『Next.jsの考え方』に沿った実装
1. 『Next.jsの考え方』をAgentに都度読ませるルール

---

# 最適なツール・モデル選び

僕がよく採用するAIツールとモデル

- プロトタイプ開発
  - `v0.app`
- 中規模以上の開発や保守
  - Claude Code
  - Cursor(`claude-4-sonnet`)

---

# AIへのフィードバックサイクル

適切に設計された静的解析とテスト

- 静的解析
  - `tsgo`
  - biome
- 単体テスト
  - [フロントエンドにおける「単体テストの考え方/使い方」](https://zenn.dev/akfm/articles/frontend-unit-testing)
  - [`@akfm/test-utils`](https://www.npmjs.com/package/@akfm/test-utils)などの活用
- Storybook
  - Test Runner
  - [`@akfm/storybook-mcp`](https://www.npmjs.com/package/@akfm/storybook-mcp)でStoryの状態を都度確認
- MCP/AI接続
  - playwright-mcp、Serena
  - [`browserDebugInfoInTerminal`](https://x.com/cramforce/status/1944885314750963827)フラグ

---

# 『Next.jsの考え方』に沿った実装

AIも人も、参考コードのあるなしで精度が大きく変わる

- [Next.jsの考え方](https://zenn.dev/akfm/books/nextjs-basic-principle)に沿った参考実装を用意する
  - 可能ならリポジトリ全体に適用する
  - 不可能なら、ルールで参考コードの場所を明記しておく
- 参考実装があれば、AIは「形だけ真似る」ようにはなる
  - 人間の仕事は主に「背後にある思想の反映」になる

---

# 『Next.jsの考え方』をAgentに都度読ませるルール

色々試した結果、都度読ませるのがベスト

- publicリポジトリから『Next.jsの考え方』のマークダウンをコピーして配置
- 都度必要な章を読み込むよう[ルールに設定](https://github.com/AkifumiSato/akfm-nextjs-rules-demo/blob/main/CLAUDE.md)
  - 内容を圧縮してルールに設定すると精度が落ちる
  - ルール記述後にSerenaのOnboardingすると精度向上

---
layout: section
---

# DEMO

参考リポジトリによる解説

---

# DEMO

参考リポジトリで以下解説

- リポジトリの全体像
- 静的解析やテスト設計
- Storybook MCPの実演
- Claude Codeの実装

---
layout: section
---

# 定性評価と感想

AI Agentの工夫による恩恵の体感値

---

# 定性評価と感想

LLMは厳密な検証が難しいため、定性評価

- アプリケーションにもよるが、体感5~7割くらいAI Agentにドライバーを任せられる
- Next.jsはこれからもAIフレンドリーなフレームワークとして進化してくと思う
- 自分の学んだことや思想をアウトプットしておくと、AIにも伝えやすい

---
layout: section
---

# End
