# 傷寒論（宋本）原文・注・現代語訳

『傷寒論』（宋本，明の趙開美による翻刻本の系統）の原文を，条文（または段落）ごとの小さな単位に分け，資料間の異同（校異）・校訂，成無己の注（原文），現代語訳（日本語・英語）と組み合わせたもの。人が読むためだけでなく，LLM が読みやすいことを目指して，1単位を1ファイルにし，ファイルの頭に機械で読める情報（YAML）を付けている。

全篇（829単位）について，句読点を付けた原文，校異・校訂・注釈，成無己注（原文），日本語訳・英訳（原文と成無己注の訳，解説）がそろっている。

## 構成

```
NN_篇名/
  index.md      篇の説明，篇首の注，単位の一覧
  NNN.md        原文（句読点つき）＋校異・校訂・注釈＋成無己注（原文）
  NNN.ja.md     日本語訳：原文の訳・成無己注の訳・解説
  NNN.en.md     英訳：同じ内容の英語版
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
| punctuated | 原文に句読点を付けたか |

訳のファイル（`.ja.md` `.en.md`）の頭には `unit` `clause` `lang` `source`（対応する原文のファイル）と，方があれば `formulas` を付けている。

### 訳と解説の書き方

- 訳は直訳を基本とし，補った語は〔〕に入れた。
- 解説は一般的な解釈を独自の言葉でまとめたもので，現代の注釈書からの引用はしていない。
- 底本の字が疑わしいところは，訳を底本どおりにして〔〕や解説で注記した。
- 可・不可の諸篇（18〜25）の多くは三陰三陽篇と同じ条文なので，解説ではその条文の番号を示した。
- 27 は Kanripo からの引用であり，句読点は付けていない。目録（s04）の一覧と釈音（s06）は項目ごとの訳を省いた。

## 本文と資料

- **本文の元**：儒道中医網「赵开美翻刻《宋版伤寒论》」の電子テキスト（簡体字）を，日本の新字体に変換したもの（字体の方針は `字体と変換の方針.md`）。
- **照合した資料**：Wikisource「傷寒論（宋本）」，Kanripo（漢籍リポジトリ）の成無己『注解傷寒論』（四部叢刊本，KR3e0008），殆知閣「伤寒论宋版」。
- **校異**：資料の間の字句の違い。「X は「…」に作る」の形で，どの資料かを示す。字体だけの違い・句読点・他の資料の欠落は記していない。
- **校訂**：本文を改めたところ（12か所）。インターネット上の一般的な『傷寒論』398条の本文で確かめられたものだけを改め，元の字句と根拠を【校訂】に記した。
- **成無己注**：Kanripo の『注解傷寒論』から，本文と注を機械的に分けて取り出したもの。境目の誤りがありうる。

## 権利とライセンス

- **古典の文**（『傷寒論』の本文，成無己注，序・跋などの文）：パブリックドメイン。電子テキストの元になった資料の文を引くときは出典を示している。
- **このプロジェクトで新しく書いたもの**（句読点，校異・校訂・注釈の説明，日本語訳・英訳，解説，YAML の情報など）：LLM（Claude）を使って作成したもの。[クリエイティブ・コモンズ 表示 4.0 国際（CC BY 4.0）](https://creativecommons.org/licenses/by/4.0/deed.ja)で提供する。利用・改変・再配布・商用利用ができる。利用するときは出典として「傷寒論（宋本）原文・注・現代語訳（Hideaki Takata）」とこのリポジトリを示すこと。詳しくは `LICENSE`。
- 訳と解説は LLM によるもので，誤りがありうる。臨床に用いる判断の根拠にはしないこと。

---

**English summary**: Song edition of the *Shanghan lun* (Treatise on Cold Damage), split into small units (clauses 1–398 for the six-channel chapters; paragraphs elsewhere). Each unit file contains the classical text (Japanese shinjitai), textual variants among sources, editorial emendations, and Cheng Wuji's commentary; each unit also has Japanese (`.ja.md`) and English (`.en.md`) translations of the text and commentary, with explanatory notes. Each file starts with YAML metadata.

**License**: The classical texts are in the public domain. Punctuation, notes, translations, and other material newly written for this project (with the help of an LLM, Claude) are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Translations and notes may contain errors and are not medical advice.
