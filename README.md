# 傷寒論（宋本）原文・注・現代語訳

『傷寒論』（宋本，明の趙開美による翻刻本の系統）の原文を，条文（または段落）ごとの小さな単位に分け，資料間の異同（校異）・校訂，成無己の注（原文），現代語訳（日本語・英語）と組み合わせたもの。人が読むためだけでなく，LLM が読みやすいことを目指して，1単位を1ファイルにし，ファイルの頭に機械で読める情報（YAML）を付けている。

**作成中**：原文と注は全篇そろっている。原文の句読点，解説，日本語訳・英訳はこれから付ける。

## 構成

```
NN_篇名/
  index.md      篇の説明，篇首の注，単位の一覧
  NNN.md        原文＋校異・校訂・注釈＋成無己注（原文）
  NNN.ja.md     日本語訳（作成中）
  NNN.en.md     英訳（作成中）
```

- 篇は 00〜26（宋本の跋文・序・本文22篇・後序）と，27（成無己『注解傷寒論』の付属部分：序・目録・釈音など）。
- 単位の番号：第5〜14篇（08〜17）は一般に使われる条文番号（第1〜398条）。条文の直後の方（構成生薬・煎じ方）も同じ単位に入れる。その他の篇は段落の番号（`p001` など），27 は節（`s01` など）。

### ファイルの頭の情報（YAML）

| キー | 内容 |
|---|---|
| book | 書名 |
| chapter / chapter_title | 篇の番号と篇名 |
| unit | 単位の番号（ファイル名） |
| clause | 条文番号（第5〜14篇のみ） |
| paragraphs | 元の本文での段落の番号 |
| formulas | この単位に出る方の名 |
| title | 単位の題 |

## 本文と資料

- **本文の元**：儒道中医網「赵开美翻刻《宋版伤寒论》」の電子テキスト（簡体字）を，日本の新字体に変換したもの（字体の方針は `字体と変換の方針.md`）。
- **照合した資料**：Wikisource「傷寒論（宋本）」，Kanripo（漢籍リポジトリ）の成無己『注解傷寒論』（四部叢刊本，KR3e0008），殆知閣「伤寒论宋版」。
- **校異**：資料の間の字句の違い。「X は「…」に作る」の形で，どの資料かを示す。字体だけの違い・句読点・他の資料の欠落は記していない。
- **校訂**：本文を改めたところ（12か所）。インターネット上の一般的な『傷寒論』398条の本文で確かめられたものだけを改め，元の字句と根拠を【校訂】に記した。
- **成無己注**：Kanripo の『注解傷寒論』から，本文と注を機械的に分けて取り出したもの。境目の誤りがありうる。

## 権利

本文・成無己注などの古典の文はパブリックドメインと考えている。電子テキストの元になった資料の文を引くときは出典を示している。校異の説明・解説・現代語訳は，このプロジェクトで（LLM を使って）新しく書いたもの。ライセンスは公開時に決める。

---

**English summary**: Song edition of the *Shanghan lun* (Treatise on Cold Damage), split into small units (clauses 1–398 for the six-channel chapters; paragraphs elsewhere). Each unit file contains the classical text (Japanese shinjitai), textual variants among sources, editorial emendations, and Cheng Wuji's commentary; Japanese and English modern translations are in preparation. Each file starts with YAML metadata.
