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

# Next.jsのAgentic Codingを<br>最大化する

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
  - 僕の普段の開発の進め方
- 今日話さないこと
  - 『Next.jsの考え方』にある内容
  - Next.jsの最新動向

---
layout: section
---

# 前提条件

周辺技術やツール

---

# Next.jsの周辺技術

僕がよく採用する周辺技術

- Storybook: Client Components/Shared ComponentsのUIをテスト
- vitest: Server Componentsをテスト
- Biome: Pluginなどは未採用
- その他ライブラリ（主題にはあまり関係ない）
  - zod
  - conform, react-hook-form
  - DataLoader
  - turborepo
  - ...

---

# AIツールとモデル

僕がよく採用するAIツールとモデル

- AI Agent: Claude Code, Cursor
- AI Model: Claude 4 Sonnet

---
layout: section
---

# AI Agentの特性

使いこなす上で意識すべき点

---

# 適切に設計された静的解析と単体テスト

TBW

---

# リポジトリ内を健全に保つ

TBW

---
layout: section
---

# Next.jsに長けた<br>AI Agentを作り込む

フレームワーク特化なAgentをどう育てるか

---

# リポジトリ内のコードに『Next.jsの考え方』を適用する

TBW

---

# 都度『Next.jsの考え方』を都度参照するようなルール設定

TBW

注意点: 圧縮するのは微妙

---
layout: section
---

# 定性評価と感想

AI Agentの工夫による恩恵の体感値

---

# Agent主体な開発が可能

TBW

- 体感7割くらい
- 他フレームワークだと正直難しいなと思う
- 徐々に堅牢になっていく

---

# 感想

TBW

- やっぱアウトプットは大事
- Agentを活かすには、真っ当な開発が必要（ルンバみたいなもの）
