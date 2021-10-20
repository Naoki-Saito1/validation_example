# README

### 一時的にバリデーションをスキップ


```
blog.save(validate: false)
```


### valid?「有効」,invalid?「無効」メソッド

```
Blog.new(title: "test").valid?
=> true
Blog.new(title: "test").invalid?「無効」
=>false(いや有効だよ)
```

オブジェクトが有効かどうかだけを確認したい時は、これらのメソッドを使いましょう。

<br>
<br>
<br>
<br>
1990-3000の整数を検証

```
numericality: { only_integer: true, greater_than: 1990, less_than: 3000 }
```
’G’, ‘PG12’, ‘R15+’, ‘R18+’ のいずれかの値の場合のみ保存
allow_blank: trueは空文字の検証はスキップ
```
inclusion: { in: ['G', 'PG12', 'R15+', 'R18+'], allow_blank: true }
```
<br>
<br>
<br>
<br>
属性名が頭に追加される以下の例では(タイトル）


```
validates :title, presence: {message: "くらいつけて"}
```


updateメソッドにおいてのみバリデーションを実行
```
 validates :title, presence: true, on: :update # updateメソッドのみ有効
 ```


その他にも様々なヘルパーやオプションがある



そのメソッドを実行するタイミングで、エラーを想定しているかどうか