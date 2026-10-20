# 傷寒論（宋本）原文・注・現代語訳

『傷寒論』（宋本，明の趙開美による翻刻本の系統）の原文を，条文（または段落）ごとの小さな単位に分け，資料間の異同（校異）・校訂，成無己の注（原文），現代語訳（日本語・英語）と組み合わせたもの。人が読むためだけでなく，LLM が読みやすいことを目指して，1単位を1ファイルにし，ファイルの頭に機械で読める情報（YAML）を付けている。

全篇（829単位）について，句読点を付けた原文，校異・校訂・注釈，成無己注（原文），日本語訳・英訳（原文と成無己注の訳，解説）がそろっている。姉妹編に[金匱要略](https://github.com/medicalcloud/kinkiyoryaku)・[黄帝内経](https://github.com/medicalcloud/koteidaikei)・[神農本草経](https://github.com/medicalcloud/shinnohonzokyo)・[和剤局方](https://github.com/medicalcloud/wazaikyokuho)がある。

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

## 底本と，本文の補い・訂正

### 底本

- **どのような本か**：明の趙開美が万暦27年（1599）に宋版を翻刻した『傷寒論』（いわゆる宋本。成無己の注のない本文の本）。
- **どのように入手したか**：本の写真からではなく，ウェブサイト「儒道中医網」（孔祥銀中医工作室）の「赵开美翻刻《宋版伤寒论》」の電子テキスト（簡体字）を，2026-10-06 にサイトの頁から取り出して使った。どの刊本から入力したかは，サイトに書かれていない。
- **字の変換**：簡体字を日本の新字体に直した（方針は `字体と変換の方針.md`）。簡体字の一字が二つ以上の字に当たるもの（术→朮・術，须→須・鬚 など）は，用例ごとに前後の文脈で確かめた。

### 底本に足りないところ

- 第七篇の半夏瀉心湯，第八篇の呉茱萸湯は，底本に方（構成と煎じ方）がない。本文には入れず，Wikisource「傷寒論（宋本）」の方を【注釈】として引いた（Kanripo の『注解傷寒論』も同じ構成と分量）。
- 底本で1字が表せず「（ni匿虫）」と書かれていた字は，字の部品と読みから「𧏾」とした（【注釈】に根拠を記した）。
- 可・不可の篇（第15〜21篇）は条文だけで，方の本文がない。照合したほかの資料にもないので，補っていない。

### 訂正（校訂）

- 本文を改めたのは12か所。底本の字が誤りと見られ，照合した資料（Wikisource・Kanripo・殆知閣本）の字によって改められるものだけを改めた。旋覆代赭湯の煎じ方の分量（「三両」→「三升」）は，国家薬品監督管理局の「古代経典名方」の資料も参考にした。改めたところには【校訂】として，元の字句・各資料の字・改めた理由を記した。
- 底本の字が疑わしくても改めなかったところ（「咽中閉寒」など）は，訳の〔〕と解説で触れた。

### 照合した資料

- **Wikisource**（中文維基文庫）「傷寒論（宋本）」：宋本の系統の本文。句読点つき。
- **Kanripo**（漢籍リポジトリ）『注解傷寒論』（KR3e0008）：四部叢刊本（明の汪済川校正本の影印）の電子テキスト。成無己の注を含む。
- **殆知閣**「伤寒论宋版」：張仲景の序と，第1〜3篇・第5〜14篇（第4篇と第15〜22篇はない）。簡体字。
- **校異**：これらの資料と底本の字句の違い。「X は「…」に作る」の形で，どの資料かを示す。字体だけの違い・句読点・他の資料の欠落は記していない。
- **成無己注**：Kanripo の『注解傷寒論』から，本文と注を機械的に分けて取り出したもの。境目の誤りがありうる。

## 権利とライセンス

- **古典の文**（『傷寒論』の本文，成無己注，序・跋などの文）：パブリックドメイン。電子テキストの元になった資料の文を引くときは出典を示している。
- **このプロジェクトで新しく書いたもの**（句読点，校異・校訂・注釈の説明，日本語訳・英訳，解説，YAML の情報など）：LLM（Claude）を使って作成したもの。[クリエイティブ・コモンズ 表示-継承 4.0 国際（CC BY-SA 4.0）](https://creativecommons.org/licenses/by-sa/4.0/deed.ja)で提供する。利用・改変・再配布・商用利用ができる。利用するときは出典として「傷寒論（宋本）原文・注・現代語訳（Hideaki Takata）」とこのリポジトリを示すこと。改変したものを配布するときは，同じ CC BY-SA 4.0（またはその互換ライセンス）で提供すること。詳しくは `LICENSE`。
- 訳と解説は LLM によるもので，誤りがありうる。臨床に用いる判断の根拠にはしないこと。

---

**English summary**: Song edition of the *Shanghan lun* (Treatise on Cold Damage), split into small units (clauses 1–398 for the six-channel chapters; paragraphs elsewhere). Each unit file contains the classical text (Japanese shinjitai), textual variants among sources, editorial emendations, and Cheng Wuji's commentary; each unit also has Japanese (`.ja.md`) and English (`.en.md`) translations of the text and commentary, with explanatory notes. Each file starts with YAML metadata.

**License**: The classical texts are in the public domain. Punctuation, notes, translations, and other material newly written for this project (with the help of an LLM, Claude) are licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). Translations and notes may contain errors and are not medical advice.
