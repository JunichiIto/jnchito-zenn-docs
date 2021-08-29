---
title: "ユースケースその1：ググって公式リファレンスにたどり着いた場合"
---

たとえば、「ruby string size」というキーワードでググった結果、以下のページにたどり着いたとします。

https://docs.ruby-lang.org/ja/latest/method/String/i/length.html

![](https://storage.googleapis.com/zenn-user-upload/5c5ec02c11e3ffd2fa48abbb.png =500x)

## URLとバージョンの関係を知る

このページのURLは https://docs.ruby-lang.org/ja/latest/method/String/i/length.html です。このURLの"latest"の文字に注目してください。"latest"は「最新」という意味です。つまり、このURLは現時点におけるRubyの最新バージョンを対象に説明したページであることを意味します。そのため、URLは同じでも開いたタイミングによって説明しているバージョンが変わります。たとえば、この記事を書いている時点ではRuby 3.0が最新バージョンなので、ページの左上には"Ruby 3.0.0"と書いてあります。

![](https://storage.googleapis.com/zenn-user-upload/0d9e712cebb121ffd704acd5.png =500x)

"latest"の部分を"2.7.0"や"2.6.0"のように変えると、Ruby 2.7や2.6を対象にしたドキュメントを参照できます。

- Ruby 2.7 = https://docs.ruby-lang.org/ja/2.7.0/method/String/i/length.html
- Ruby 2.6 = https://docs.ruby-lang.org/ja/2.6.0/method/String/i/length.html

たまにバージョンによって仕様が異なる場合があるため、なるべく自分が使っているRubyのバージョンのリファレンスを見るにしましょう。

## "String#length"の意味は？

"String#length"は「Stringクラスのインスタンスメソッドである`length`メソッド」という意味です。Rubyでは"#"を使って「(クラス名)#(インスタンスメソッド名)」という形式で、どのクラスのインスタンスメソッドであるのかを示します（そもそも、見出し部分に"instsance method"と書いてありますね）。

![](https://storage.googleapis.com/zenn-user-upload/630fd164c3a936b039734eeb.png =500x)

## "length -> Integer"、"size -> Integer"の意味は？

`length -> Integer`は「`length`メソッドを呼ぶとInteger型（整数）の戻り値が返ってくる」ことを意味します。同様に`size -> Integer`は「`size`メソッドを呼ぶとInteger型の戻り値が返ってくる」ことを意味します。

つまり、ここでは「(メソッド名) -> (戻り値の型)」という形式でメソッド名と戻り値の関係が表現されています。

![](https://storage.googleapis.com/zenn-user-upload/95cd6814aa3df03804ce1a12.png =500x)

なお、`length`メソッドのページになぜ`size`メソッドが載っているのかというと、これはエイリアスメソッドの関係にあるからです。つまり、どちらのメソッドを使っても同じ結果が返ってくることを意味します。

## メソッドの説明文とサンプルコードを理解する

これは見て明らかだと思いますが、以下の赤枠部分はメソッドの説明文とサンプルコードになっています。

![](https://storage.googleapis.com/zenn-user-upload/77429392c56f083cada624d0.png =500x)

サンプルコードはコピペすればirb等ですぐに動作確認できるものが多いです。サンプルコードの右上にある"COPY"の文字をクリックすれば、サンプルコードをコピーできます。

なお、サンプルコードの`# => 4`のようなコメントはメソッドの戻り値を表現しています。以下のコードであれば「`"test".length`の戻り値は4である」という意味です。

```ruby
"test".length   # => 4
```

## このメソッドに関連する他のメソッドを知る

サンプルコードの下にある [SEE_ALSO] （「こちらも参照」の意味）のリンクはこのメソッドに関連する他のメソッドへのリンクです。ここでは`String#bytesize`が関連するメソッドとして挙げられています。メソッドの説明文にも「バイト数を知りたいときは bytesize メソッドを使ってください。」と書いてありますね。

![](https://storage.googleapis.com/zenn-user-upload/e34b8a0d91b60512785cbbc9.png =500x)

## その他、各種リンクについて

まだ説明していないページ内の各種リンクについて説明します。

![](https://storage.googleapis.com/zenn-user-upload/b1e89511001be440b74831e6.png =500x)

**permalink**
- この説明に直接飛べるページへ遷移します。（クラスの説明ページで各メソッドの説明を読んでいるときに使います）

**rdoc**
- 英語版のリファレンスマニュアルを表示します。日本語版よりも詳しい情報が載っている場合があります。

**edit**
- 間違いや改善したい内容を見つけた場合、ここからプルリクエストを投げることができます（Github上で内容を編集できます）。

**CCマーク**
- このリファレンスのライセンス（CC BY 3.0）を示しています。

**フィードバックを送る**
- 何か気づいた点があればここからフィードバックを送ることができます（Github上のissue投稿ページに遷移します）。

**このマニュアルを編集する**
- editのリンクと同じです。

## 引数があるメソッドの場合

以下は引数があるメソッドの表示例です（`Integer#to_s`メソッド）。

https://docs.ruby-lang.org/ja/latest/method/Integer/i/inspect.html

![](https://storage.googleapis.com/zenn-user-upload/d0f6f66ae0ffb71e018a3f0c.jpg =500x)

`(base=10)`は「引数を1つ受け取り、そのデフォルト値が10である」ことを意味します。また、引数の`base`が何なのかはサンプルコードの下にある"[PARAM] base:"の部分で説明されています。

なお、"[RETURN]"は戻り値の説明で、"[EXCEPTION] ArgumentError:"はこのメソッドを呼びだしたときに発生しうる例外クラスの名前とその発生条件です。

## ブロックを受け取るメソッドの場合

以下はブロックを受け取るメソッドの表示例です（`Array#each`メソッド）。

https://docs.ruby-lang.org/ja/latest/method/Array/i/each.html

![](https://storage.googleapis.com/zenn-user-upload/b26fcb2a5d84a3efad115f46.png =500x)

`each {|item| .... } -> self` の `{|item| .... }` の部分がブロックを受け取ることを意味しています。また、戻り値の`self`はレシーバ自身（ここであればメソッドを呼びだした配列そのもの）が返ることを意味します。

さらに、ここでは`each -> Enumerator`という表記もあります。これは「ブロックを与えなかった場合はEnumeratorオブジェクトが返る」ということを意味します（つまり、`each`メソッドはブロックを与えずに呼び出すことも可能）。

## 呼び出し方が複数あるメソッドの場合

以下は呼び出し方が複数あるメソッドの表示例です（`Array#all?`メソッド）。

https://docs.ruby-lang.org/ja/latest/method/Array/i/all=3f.html

![](https://storage.googleapis.com/zenn-user-upload/b63456295532bdcfd489b14e.png =500x)

ここでは以下の3パターンが説明されています。

`all? -> bool`

- 引数もブロックも与えないケースを示しています。また、戻り値の`bool`は`true`または`false`が返されることを意味します。

`all? {|item| ... } -> bool`

- ブロックを与えたケースを意味します。

`all?(pattern) -> bool`

- 引数を1つ与えたケースを意味します。

それぞれのケースが具体的にどういう挙動を示すのかは説明文やサンプルコードで説明されています。

## キーワード引数を持つメソッドの場合

以下はキーワード引数を持つメソッドの表示例です（`String#lines`メソッド）。

https://docs.ruby-lang.org/ja/latest/method/String/i/lines.html

![](https://storage.googleapis.com/zenn-user-upload/8615bd28bdcc0041756a6be8.jpg =500x)

`chomp: false`の部分がキーワード引数です。ここでは`chomp`というキーワード引数を受け取り、そのデフォルト値が`false`であることを示しています。サンプルコードでは`chomp`に`true`を指定するケースが例示されています。

なお、第1引数の`rs`のデフォルト値である[`$/`](https://docs.ruby-lang.org/ja/latest/class/Kernel.html#V_--2D0)はRubyの特殊変数で、入力レコード区切りを表す文字列のことです（奇妙な見た目ですが、これはRubyで最初から用意されている変数なんです！）。第1引数を指定しなかった場合はこの特殊変数の値が第1引数として使われます。

また、戻り値の`[String]`は「各要素が文字列（Stringオブジェクト）の配列」を意味しています。このように、配列が戻り値になる場合は`[(クラス名)]`の形式で記述され、「各要素が（クラス名）の配列」という意味になります。

## 可変長引数を持つメソッドの場合

以下は可変長引数を持つメソッドの表示例です（`Kernel.#p`メソッド）。

https://docs.ruby-lang.org/ja/latest/method/Kernel/m/p.html

![](https://storage.googleapis.com/zenn-user-upload/bd641824f3e5e25ad3e7b188.png =500x)

可変長引数では0個以上の任意の個数の引数を与えることができます。可変長引数は`*arg`のように引数名の手前に`*`が付けられます。

また、ここでは戻り値が`object | Array`となっています。`|`は「または」を意味する記号で、この場合は「なんらかのオブジェクトまたは配列」を意味します。上のスクリーンショットには含まれていませんが、このメソッドの戻り値はリファレンス上、次のように説明されています。

> 指定された引数 arg を返します。複数の引数が指定された場合はそれらを要素とする配列を返します。

## クラスメソッド（特異メソッド）の場合

クラスメソッドは「(クラス名).(メソッド名)」の形式で表記されます。以下はクラスメソッドの表示例です（`Regexp.escape`メソッド）。

https://docs.ruby-lang.org/ja/latest/method/Regexp/s/escape.html

![](https://storage.googleapis.com/zenn-user-upload/c5c4488624d3bef6a483319f.png =500x)

クラスメソッドを呼び出すときはリファレンス上の表記と同じく、`(クラス名).(メソッド名)`の形で呼び出します（例: `Regexp.escape("$bc^")`）。

ちなみに、Rubyのクラスメソッドは厳密には「Classオブジェクトの特異メソッド」として定義されています。そのため、見出しにも「特異メソッド」を意味する"singleton method"が書かれています。

![](https://storage.googleapis.com/zenn-user-upload/db12583ef7167b16196678e1.jpg =500x)

## モジュール関数の場合

モジュール関数は「(クラス名).#(メソッド名)」の形式で表記されます。先ほど紹介した`p`メソッドもモジュール関数です。

https://docs.ruby-lang.org/ja/latest/method/Kernel/m/p.html

![](https://storage.googleapis.com/zenn-user-upload/33ee07f766332c99cb044d75.jpg =500x)

モジュール関数はモジュールに定義される、次のような特徴を持つメソッドです。

- モジュールのプライベートメソッドであり、他のクラスにincludeして使うことができる
- 「(モジュール名).(メソッド名)」の形式でモジュールの特異メソッドとして呼び出すこともできる

参考 https://docs.ruby-lang.org/ja/latest/method/Module/i/module_function.html
