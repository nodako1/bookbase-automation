# scene_03

## このシーンの役割

今回紹介する本を視覚的に見せ、視聴者に「この本を紹介する動画なんだ」と理解させる。動画全体の結論を短く伝え、scene_04 の著者紹介・重要ポイント提示へ自然につなげる。

scene_03 はサムネイルではない。煽りすぎず、上品に本の価値を伝える動画内画像にする。

## 最重要ルール：ブックカバーは再生成しない

scene_03 では、今回紹介する本の実際のブックカバー画像を必ず使う。

- ブックカバーは必ず使用する。
- ブックカバーを AI に描き直させない。
- 架空の表紙を作らない。
- 表紙の文字を崩さない。
- 表紙を歪ませない。
- 表紙を切りすぎない。
- 表紙が読めるサイズで表示する。

## 推奨実装：AI生成背景 + 実ブックカバー合成

画像生成 AI だけで完結させず、次の 2 段階にする。

1. OpenAI API で、ブックカバーを置く余白を確保した 16:9 の背景画像を生成する。
2. Python の Pillow などで、実際のブックカバーを背景画像へ重ねる。

背景生成段階では、AI にブックカバーを描かせない。背景には、高級感のあるデスク、淡いクリーム背景、ティールとゴールドのアクセント、ノート、ペン、コーヒーカップなどの上品な仕事道具、Book Base ロゴ、本のテーマに合う控えめなモチーフを入れる。

## ブックカバー合成ルール

- 16:9 画像上に配置する。
- カバーの縦横比を維持する。
- カバー幅は画像全体の 25〜38% 程度にする。
- 左側または中央左に大きく配置する。
- 上下左右に十分な余白を取る。
- 薄い影を付ける。
- 必要なら白または薄いクリーム色の縁取りを付ける。
- 表紙が背景に埋もれないようにする。
- 表紙の上に余計な文字を重ねない。

## 推奨構図

### 構図A：左カバー・右メッセージ型

左側に実際のブックカバーを大きく配置し、右側に短い結論メッセージを置く。背景は上品なデスク、ノート、ペン、淡い光にする。

### 構図B：中央カバー・周辺モチーフ型

中央に実際のブックカバーを置き、周囲に会話、言い換え、信頼を示す控えめなアイコンを配置する。背景は水彩紙の質感、ゴールドの細い装飾にする。

### 構図C：本を手に取る導入型

左中央に実際のブックカバー、右側に読書メモや会話カードを置く。背景は落ち着いた書斎・仕事机にする。

scene_02 が人物・答えカード中心の場合、scene_03 では人物を大きく出しすぎず、本そのものを主役にする。

## 画像内テキストルール

ブックカバー自体にタイトルがあるため、画像側で長い文字を追加しない。

使用してよいテキストは次の 2 つだけにする。

- 今回の一冊
- 言い方で関係は変わる

禁止事項：

- 本のタイトルを長く重複表示する。
- 原稿本文を入れる。
- 3 行以上の説明文を入れる。
- キャッチコピーを詰め込む。
- 表紙の上に文字を重ねる。

## 背景生成用プロンプト

```text
Create a 16:9 landscape video-insert background image for Book Base, a Japanese business book YouTube channel. Use a refined watercolor illustration style with a premium, calm, elegant atmosphere. Use a soft cream-white and beige background with teal and subtle gold accents. Include a small natural Book Base logo placed unobtrusively.

This is Scene 03. Its role is to introduce the current book and give viewers the overall conclusion of the video. The actual book cover will be composited later from the provided reference image, so do not draw or recreate the book cover. Leave a clean, prominent empty space on the left side or center-left for the real book cover to be placed. The space should feel intentional, like a premium book presentation layout.

Visual concept:
A calm premium desk setup for a Japanese business book introduction. Include subtle office items such as a notebook, pen, soft coffee cup, small plant, or paper cards. Use motifs related to communication and wording, such as gentle speech bubble icons, small note cards, or soft connecting lines. Keep the design elegant and uncluttered.

Use only the following Japanese text elements exactly as written. Do not add any other Japanese or English text:
1. 今回の一冊
2. 言い方で関係は変わる

Do not place long script text. Do not add a fake book cover. Do not write the book title yourself. Do not distort or invent cover artwork. Keep enough whitespace for the real book cover. Make the image calm, sophisticated, and suitable for a Japanese business book summary video.
```

## 失敗時の扱い

今回紹介する本のブックカバーが存在しない場合は、scene_03 画像を成功扱いにしない。

```text
scene_03：NEEDS_REVIEW
理由：今回の本のブックカバーが見つかりません
```

ブックカバーがない状態で、AI に架空の表紙を作らせることは禁止。
