# emojifunge

## これは何

befunge + emoji

ありそうでなかったので作った

## emojiについて

` Command + Control + Space ` で出せる

## 仕様

emojiを二次元上に配置する言語

コードは、emoji と 改行 のみ有効

スタックベースの言語

空のスタック stack = (top)[](bottom) と、(x, y) = (0, 0)を指すポインタがある

空の stack から pop するとき、 -1 を返す

## 移動に関する仕様

最初は(x, y) = (0, 0)に位置し、移動方向は(dx, dy) = (1,0)

移動先にemojiがあれば移動する
---|---|
emojiがなければ、

## コマンド一覧

| emoji | name | action | example |
|---|---|---|---|
|ℹ️|　Input Number | 数値入力 入力を数値として受け取る。空白などの直前まで受け取る。  | stack `[53, 2] -> [32, 53, 2]` input: `32 54 AA` -> ` 54 AA`|
|🔤| Input ASCII | 文字入力 ASCII CODEとして受け取る。|stack `[53, 2] -> [41, 53, 2]` input: `ABC` -> `BC`|
|🔢| Output Number | 数値出力 stackのtopを数値として出力する。popする。| stack `[32, 53, 2] -> [53, 2]` output: `32`|
|🔡| Output ASCII | 文字出力 stackのtopをASCII CODEとして出力する。popする。| stack `[41, 53, 2] -> [53, 2]` output: `A`|
