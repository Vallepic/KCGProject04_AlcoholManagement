表題はchatGPTに「SpringBootとJavaを用いたWebアプリ開発」について尋ねた時に提案されたもの
# 必須ツール
## JDK(Java開発機構)
- 触ったことない，IDEと何が違うの
    - JDKがないとIDEはただのメモ帳
    - JDK17 or JDK21

## IDE(総合開発環境)
- Eclipseを使いたい
- IntelliJ IDEAをややおすすめされた(IntelliJ IDEA >= Eclipse くらいの差)(差異がよくわかんない)

- 今回はIntelliJを使ってみよう

## ビルドツール(依存管理)
- Mavenおすすめ(IntelliJ IDEAではそっち使うよう設定してたっけ...)
    - 昔からあり、XMLという形式で「設定」を書きます。少し記述が長くなりますが、ルールが厳格です。
- 次にGradleおすすめ(Eclipseではこっち使ってたな...)
    - 最近の主流。Javaに近い書き方（GroovyやKotlin）で設定を書けます。Android開発でも使われます。
- 何が違うの？
    - Maven
        - 書き方がXML
        - 難易度は易しい
        - 柔軟性は普通
        Geminiの見解(IntelliJ × Maven)
            - ネットに答えが落ちている(10年前から書き方の基礎が変わらない)
            - ルールがガチガチ
            - XMLが長くて読みづらい
            - Javaとは別世界の「設定ファイル感」が強い
    - Gradle
        - 書き方がプログラム風
        - 難易度は少し難しい
        - 柔軟性は高い
        Geminiの見解(IntelliJ × Gradle)
            - 記述がスッキリして美しい
            - IntelliJの補完がバリバリ効く
            - ネットの記事によって書き方が違うことがあり，見極めが必要

## Spring Boot本体
- Spring Initializr(一応触ったっけな...)

# ほぼ必須(実用レベルにするため)
## DB(データベース)
- H2 Database(わからなくて匙を投げた)
- MySQL(一応習ったけど自信ない...)
    - 読取りが速く，Webサイト全般で使われる
    - Javaとの相性は普通(要設定)
    - 今回の運用では，記録の保存に留まる
- PostgreSQL(初耳...)
    - 複雑な計算やデータの整合性，大量データ処理に強い
    - Java(及びSpringBoot)との相性が非常に良い
    - 記録の保存に加え将来的な複雑な処理(回帰分析など)に活用できる

- 開発段階・学習段階ではH2，本番・公開用にPostgreSQL(gemini)・MySQL→PostgreSQL(chatGPT)に移行がおすすめされた
    - 移行時にJavaのコードを書き換える必要がほとんどない
    - 他のDBを触る際にも応用が利きやすい

## APIテストツール
- Postman(なんそれ？状態)
    - 作成したロジックが正しく動作するかをテストするためのツール
    - getter・setter
    - GET・POST
- Postmanの強み
    - 世界標準ゆえの情報の多さ(困ったときにすぐ答えが見つかる)
    - 何を送っているかが視覚的にわかりやすい
        - URL(宛先，どこに送るか)
        - Method(GETかPOSTか)
        - Body(どんなデータか)
        - Response(Java側からどんな結果が返ってきたか)
    - 履歴と保存が便利(バグ取りの効率が劇的に上がる)
代替ツール
- Insomnia
    - UIがシンプル
    - 動作が軽い
- Thunder Client 
    - VS Codeの拡張機能
- cURL
    - コマンドラインで叩く
    - 動作が軽い
    - エンジニア向け
- HTTPie
    - cURLの使いやすい版
- IntelliJ HTTP Client
    - IntelliJ内で完結する
    - Postmanほど多機能ではない(玄人向け)
- Swagger UI
    - Spring Bootと相性がいい

## Git(バージョン管理)
- Git・GitHub(実力さておき正直めちゃくちゃ自信ある，ありがとう久保田先生)

# フロントエンド
- Thymeleaf(学習コストが低い，スマホUIはやや弱い，Java内で完結する)
- フロントエンドReact，バックエンドSpringBoot(スマホ対応しやすい，将来アプリ化しやすい，学習対象が増えすぎる)
- Bootstrap(CSSフレームワーク，スマホで見ても崩れない「レスポンシブルデザイン」が簡単に作れる)