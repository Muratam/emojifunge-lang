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

### 入出力

| emoji | name | action | example |
|---|---|---|---|
|ℹ️|　Input Number | 数値入力 入力を数値として受け取る。空白などの直前まで受け取る。  | stack `[53, 2] -> [32, 53, 2]` input: `32 54 AA` -> ` 54 AA`|
|🔤| Input ASCII | 文字入力 ASCII CODEとして受け取る。|stack `[53, 2] -> [41, 53, 2]` input: `ABC` -> `BC`|
|🔢| Output Number | 数値出力 stackのtopを数値として出力する。popする。| stack `[32, 53, 2] -> [53, 2]` output: `32`|
|🔡| Output ASCII | 文字出力 stackのtopをASCII CODEとして出力する。popする。| stack `[41, 53, 2] -> [53, 2]` output: `A`|

### 制御

| emoji | name | action | example |
|---|---|---|---|
|⛔️| exit | プログラムを終了する ||
|⬜️ | empty | 何もしない ||
|⬛️ | wall | 壁。プログラムの外側と同じ扱いとなる。 ||

### 定数

| emoji | name | action | example |
|---|---|---|---|
|0️⃣| 0| 0 を push する。|stack `[53, 2] -> [0, 53, 2]`|
|1️⃣| 1| 1 を push する。||
|2️⃣| 2| 2 を push する。||
|3️⃣| 3| 3 を push する。||
|4️⃣| 4| 4 を push する。||
|5️⃣| 5| 5 を push する。||
|6️⃣| 6| 6 を push する。||
|7️⃣| 7| 7 を push する。||
|8️⃣| 8| 8 を push する。||
|9️⃣| 9| 9 を push する。||
|🔟| 10| 10 を push する。||
|💯| 100| 100 を push する。||

### 計算

| emoji | name | action | example |
|---|---|---|---|
|➕| plus| `a`, `b` を pop し、`a+b` を push する。|stack `[7, 4, 6] -> [11, 6]`|
|➖| minus| `a`, `b` を pop し、`a-b` を push する。|stack `[7, 4, 6] -> [3, 6]`|
|✖️| mul| `a`, `b` を pop し、`a*b` を push する。|stack `[7, 4, 6] -> [28, 6]`|
|➗| div| `a`, `b` を pop し、`a/b` を push する。|stack `[7, 4, 6] -> [1, 6]`|
|🈹| mod| `a`, `b` を pop し、`a%b` を push する。|stack `[7, 4, 6] -> [3, 6]`|

### スタック操作

| emoji | name | action | example |
|---|---|---|---|
|🚮| pop| popする。値は破棄する。|stack `[7, 4, 6] -> [4, 6]`|
|💕| dup| `a` を pop し、`a`, `a` を push する。 |stack `[7, 4, 6] -> [7, 7, 4, 6]`|
|💞| swap| (top)`a`, `b` を pop し、(top)`b`, `a` を push する。|stack `[7, 4, 6] -> [4, 7, 6]`|
|♻️| swap3| (top)`a`, `b`, `c` を pop し、(top)`c`, `a`, `b` を push する。|stack `[7, 4, 6] -> [6, 7, 4]`|
|♻️| pop| popする。値は破棄する。|stack `[7, 4, 6] -> [4, 6]`|
|| pop| popする。値は破棄する。|stack `[7, 4, 6] -> [4, 6]`|

dup swap swap3 rev
