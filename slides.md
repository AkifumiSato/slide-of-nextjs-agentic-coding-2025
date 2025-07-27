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
layout: section
---

## 「AIによる開発効率の向上」、できてますか？

---
layout: section
---

## Next.jsの開発においても<br>AI Agentの活用は非常に重要

---

# Theme: Next.jsのAgentic Codingを最大化する

僕が実際に実践してるTipsや知見を紹介

1. 適切に設計された静的解析と単体テスト
2. [Next.jsの考え方](https://zenn.dev/akfm/books/nextjs-basic-principle)に沿って実装されたリファレンス実装
3. <span class="font-bold" v-mark="{ at: 1, color: 'red', type: 'underline' }">AI Agentが『Next.jsの考え方』を都度参照するようなルール設定</span>

※[Zennの記事](https://zenn.dev/akfm/articles/agent-read-the-nextjs-way)とある程度内容が重複します

---
layout: section
---

# Next.jsに限らない<br>AI Agentを活かす工夫

---

# 利用するツールやモデル

AIツールに関しては以下を利用して検証しました

- AI Agent: Claude Code, Cursor
- AI Model: Claude 4 Sonnet

---

# 適切に設計された静的解析と単体テスト

TBW

---

# リポジトリ内を健全に保つ

TBW

---
layout: section
---

# Next.jsにおける<br>AI Agentを活かす工夫

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
