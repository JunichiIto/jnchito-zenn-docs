---
title: "ユースケースその3：Rubyにはどんなクラスやモジュールがあるのか知りたい場合"
---

「Rubyってどんなクラスやモジュールがあるんだろう？」と思ったときは、ライブラリ一覧のページを開きましょう。

https://docs.ruby-lang.org/ja/latest/library/index.html

![](https://storage.googleapis.com/zenn-user-upload/edfb3a518fa3005bf7e06e83.jpg =500x)

## 組み込みライブラリを調べる

組み込みライブラリのページにはrequireなしで使えるクラスやモジュールの一覧が載っています。

https://docs.ruby-lang.org/ja/latest/library/_builtin.html

![](https://storage.googleapis.com/zenn-user-upload/2f146d69350e83678b0baf94.png =500x)

クラス名のインデントは継承関係を表しています。右にインデントすると、そのクラスは左側にあるクラスのサブクラスであることを意味します（例：ObjectクラスはBasicObjectクラスのサブクラス）。

![](https://storage.googleapis.com/zenn-user-upload/6ff04eb5c7d0ba737d47a3a2.jpg =150x)

## 標準ライブラリを調べる

ライブラリ一覧のページには組み込みライブラリに続けて、標準ライブラリの一覧が載っています。

https://docs.ruby-lang.org/ja/latest/library/index.html

![](https://storage.googleapis.com/zenn-user-upload/e0e563b279f7231572f895e7.jpg =500x)

たとえば、dateライブラリのページを開くと、`require 'date'`でdateライブラリをrequireしたときに使えるクラスの情報が載っています。

https://docs.ruby-lang.org/ja/latest/library/date.html

![](https://storage.googleapis.com/zenn-user-upload/c7aa3a494bcf37d28e402ca7.png =500x)
