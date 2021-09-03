---
title: "ユースケースその2：クラスのメソッド一覧から目的のメソッドを探す場合"
---

「メソッド名はわからないけど、もしかすると○○○するためのメソッドがすでにRubyに用意されているかもしれない」という場合は、クラスの説明ページから目的のメソッドを探すことができます。

たとえば、配列で使えるメソッドを探したいときはArrayクラスの説明ページを開きます。

https://docs.ruby-lang.org/ja/latest/class/Array.html

![](https://storage.googleapis.com/zenn-user-upload/cc867a2bd705c70148e220fe.png =500x)

本章ではこのページを例として、クラスの説明ページの読み方を説明します。

## クラスの継承関係を理解する

クラスの説明ページには継承リストが載っています。

![](https://storage.googleapis.com/zenn-user-upload/7bd438ecffbacf4ef1c5bcc9.png =500x)

「（クラスA）&lt;（クラスB または モジュールB）」は「クラスAがクラスBを継承していること」もしくは「クラスAがモジュールBをincludeしていること」を表します。

ここではArrayクラスが、Enumerableモジュールと、Objectクラスと、Kernelモジュールと、BasicObjectクラスを継承、またはincludeしていることがわかります。つまり、ArrayクラスではArrayクラス本体に定義されたメソッドだけではなく、これらのクラスやモジュールに定義されたメソッドを使用することができます。目的のメソッドがこのページに載っていない場合は、継承関係にある他のクラスやモジュールの説明ページを開くとそのメソッドが見つかるかもしれません。

また、 "dynamic include: JSON::Generator::GeneratorMethods::Object (by json)" の部分は、jsonライブラリをrequireすることで、  JSON::Generator::GeneratorMethods::Object モジュールに定義されたメソッド（ここでは`to_json`メソッド）がArrayクラスで使えるようになることを意味します。

```ruby 
require 'json'

# jsonライブラリをrequireすると、配列でto_jsonメソッドが使えるようになる
[1, 2, 3].to_json #=> "[1,2,3]"
```

## クラスの概要を理解する

「要約」の欄にはそのクラスやモジュールの概要が書かれています。

![](https://storage.googleapis.com/zenn-user-upload/28049d171fd25e96af04a5e9.png =500x)

## メソッドの一覧を眺める

「目次」の欄ではそのクラスで使用可能なメソッドの一覧が載っています。

![](https://storage.googleapis.com/zenn-user-upload/6ba1f14c5c33965c011e3f14.jpg =500x)

そのクラスのインスタンスメソッドだけでなく、特異メソッド（クラスメソッド）やincludeされているモジュールによって定義されるメソッドの一覧も載っています。

![](https://storage.googleapis.com/zenn-user-upload/c1bed942cf7fe2320f82bfa7.jpg =500x)

うろ覚えしているメソッドを探すときや、メソッド名から使いたい機能を類推したいときにメソッド一覧を眺めると、目的のメソッドが見つかる場合があります。

## 各メソッドの説明を読む

ページをそのまま下にスクロールしていくと、各メソッドの説明が始まります。メソッドの説明文やサンプルコードを読んで、自分の探しているメソッドかどうかを確認しましょう。

![](https://storage.googleapis.com/zenn-user-upload/20abf1f45ac35ee99a5e30f4.jpg =500x)

## permalinkで目的のメソッドのURLをシェアする

なお、"permalink"のリンクをクリックすると、対象のメソッドだけを説明しているページに遷移できます。他の人に「このメソッドなんだけど」と伝えたいときは、"permalink"で表示されるURLをシェアすると便利です。

![](https://storage.googleapis.com/zenn-user-upload/fe6185457f48e36b64890932.jpg =500x)

## インスタンスメソッドや特異メソッド以外の一覧

クラスの説明ページではインスタンスメソッドと特異メソッドの一覧が載っていることが多いですが、クラスやモジュールによってはそれ以外の一覧が載っていることもあります。

たとえば、Objectクラスの説明ではprivateメソッドと定数も説明の対象になっています。Objectクラスに定義されている定数は、どのクラスからも参照可能です。

https://docs.ruby-lang.org/ja/latest/class/Object.html

![](https://storage.googleapis.com/zenn-user-upload/69689ce0d62017adbc59a3d3.png =500x)

Kernelモジュールではモジュール関数や特殊変数の一覧が載っています。

https://docs.ruby-lang.org/ja/latest/class/Kernel.html

![](https://storage.googleapis.com/zenn-user-upload/8523b185177a06e01c733c65.jpg =500x)
![](https://storage.googleapis.com/zenn-user-upload/7d64beb500e283afca2269d5.png =500x)
