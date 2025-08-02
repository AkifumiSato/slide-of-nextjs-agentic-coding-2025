---
theme: default
background: https://images.unsplash.com/photo-1735948055457-8d816fb80a87?q=80&w=2371&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
class: text-center
highlighter: shiki
lineNumbers: false
colorSchema: "dark"
drawings:
  persist: false
transition: slide-left
title: Next.jsのAgentic Codingを最大化する
mdc: true
---

# Next.jsと<br>Agentic Codingの最大化

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
layout: statement
---

## みなさん、AI使ってますか？

---
layout: statement
---

## AIで生産性、向上してますか？

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

# AI時代におけるVercel Inc.の戦略

Next.jsを中心とした全方位戦略

- _**Next.js**_: 人気なフレームワーク=AIも生成しやすい
- _**Vercel**_: Next.jsを最も容易にデプロイできるプラットフォーム
- _**v0.dev**_: Next.jsやVercelと強く統合されたAIプラットフォーム

参考: Vercel社員の上杉さんが出演した[Qiita FM](https://corp.qiita.com/releases/2025/03/podcast-uesugi/)

---
layout: statement
---

## 「Next.jsとAIの統合」はVercel Inc.にとっても<br>非常に重要なテーマ

---

# Next.jsとAIの現在地

まだまだAI時代黎明期

- v0.devによりプロトタイプ開発は超高速に
  - Vercelの戦略には妥当性を感じる
- 中規模以上の開発、保守は難しい
  - 工夫次第で生産性の幅は大きく変わる
  - Next.jsもAIとの統合を意識した機能開発が盛んになりつつある段階

---
layout: statement
---

## Next.jsとAIの生産性は、現状開発者の工夫次第

---
layout: statement
---

## じゃあ何を工夫すればいいのか？

---
layout: section
---

# Next.jsとAIを統合する<br>プラクティス

生産性向上の鍵

---

# 4つのプラクティス

僕が普段重要だと考えてるプラクティス4つ

1. 最適なツール・モデル選び
1. 適切に設計された静的解析とテスト
1. 『Next.jsの考え方』に沿った実装
1. 『Next.jsの考え方』をAgentに都度読ませるルール

---

# 最適なツール・モデル選び

僕がよく採用するAIツールとモデル

- プロトタイプ開発
  - v0.dev
- 中規模以上の開発や保守
  - Claude Code
  - Cursor(`claude-4-sonnet`)

---

# 適切に設計された静的解析とテスト

AIがフィードバックサイクルを回すために必須

- 静的解析: Lintや型チェックは当然必須
- 単体テスト: 緻密に設計したテスト設計が重要
  - [フロントエンドにおける「単体テストの考え方/使い方」](https://zenn.dev/akfm/articles/frontend-unit-testing)
  - [`@akfm/test-utils`](https://www.npmjs.com/package/@akfm/test-utils)などの活用
- Storybook: Storyを確認できる環境の整備
  - [Test Runner](https://storybook.js.org/docs/writing-tests/integrations/test-runner)
  - [`@akfm/storybook-mcp`](https://www.npmjs.com/package/@akfm/storybook-mcp)でStoryの状態を都度確認
- 開発中: ログを確認できる環境の整備
  - [playwright-mcp](https://github.com/microsoft/playwright-mcp)
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

- アプリケーションにもよるが、体感5~7割くらいAI Agentに任せられる
- AI自体はもちろん、Next.jsとAIの統合はこれからもっと進化していく
- 普段から自分が重要だと思う価値観を技術記事などにアウトプットしておくことで、AIにも伝えやすい

---

# End
