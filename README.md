# nanami-skills

Claude Code（クロードコード）用の「スキル」置き場です。
スキルとは、Claudeに決まった仕事のやり方を覚えさせる小さな説明書ファイルのことです。

このリポジトリは、リベシティのオフ会「Claude Codeスキルの取り込み・公開」の実例として公開しています。

## 入っているスキル

| スキル | 説明 |
|---|---|
| `skills/grill-me` | **スイッチ役**。`/grill-me` と打つと、下の grilling が動きます |
| `skills/grilling` | **本体**。計画やアイデアについて、質問を1問ずつ投げてきます（※ 上の grill-me とセットで入れてください） |
| `skills/hikitsugi` | セッションの区切りに「引き継ぎして」と言うと、進行中の作業をメモに保存。次のセッションで「前回の続き」と言うだけで再開できる |

## 取り込み方（コピペで使えます）

Claude Codeを開いて、次の文をそのまま貼り付けてください。

grill-me / grilling を入れる場合：

```
github.com/nanami-studio/nanami-skills の skills/grill-me と grilling を
私のパソコンのスキルとして使えるように入れて
```

hikitsugi を入れる場合：

```
github.com/nanami-studio/nanami-skills の skills/hikitsugi を
私のパソコンのスキルとして使えるように入れて
```

## 出典・ライセンス

- `skills/grill-me` と `skills/grilling` は、Matt Pocock氏の [mattpocock/skills](https://github.com/mattpocock/skills)（MITライセンス）を基にしたものです。それぞれのフォルダに元のLICENSEファイルを同梱しています
- `skills/grilling` は元の「複数質問を一括出題」する仕様を「1問ずつ出題（回答を待って次へ）」に調整済みです。会話はユーザーの言語（日本語なら日本語）で行います
- `skills/hikitsugi` は自作スキルで、ライセンスはこのリポジトリ直下の `LICENSE`（MIT / Copyright (c) 2026 NANAMI）です

---

作成者：NANAMI
