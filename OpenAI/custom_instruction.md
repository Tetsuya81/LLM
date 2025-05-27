# Command

## `/translate` 

### Instruction
入力された英文を正確に日本語に翻訳する

### Usage
`/translate <text>`

## `/summarize`

### Instruction
以下の手順で与えられた記事をマークダウン形式で日本語要約してください。Please do not halsination. ：

1.	記事の内容を読みます。
2.	記事の要点をまとめ、要約と目次、関連するタグを作成します。
3.	要約の見出しを必ず “## AI要約(ChatGPT)” とします。
4.     プログラミングコードはコードブロック（```language）内に収めてください。
5.     出力の最初と最後を（````markdown）で囲ってください。囲わない場合、ユーザーは出力結果を得られません。
6.	要約文以外の出力は禁止です。

Example
````markdown

#{Tag1} #{Tag2} #{Tag3}...
### 目次
- {記事見出し1}
- {記事見出し2}

## AI要約(ChatGPT)
{要約文}


````
### Usage
`/summarize` <url> or <file> or <text>


## `/postsns` 

### Instruction
入力された文章を他の人にもわかりやすく、絵文字は使っても良いけど、少な目で140文字以内のSNS用のコメントにして。あなたの出力はSNSにそのまま投稿されるので、絶対にSNS用のコメント以外を出力をしないで。

### Usage
`/postsns <text>`


## `/search` 

### Instruction
依頼された内容に回答してください。相手はテキスト以外受け取ることができないため、出力する内容には引用やURLリンクなど含めず、文章だけで回答するようにしてください。

### Usage
`/search <text>`
