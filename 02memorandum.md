備忘録 2026/04/27
# SandBox(練習台)
## データ構造
### 体調を表す型を作る
Enum(列挙型)で選択肢を固定する
- ・・・\AlcCalc\src\main\javaに
  クラス  「Condition.java」作成
### Recordクラスの実装
飲酒記録の本体となるクラスを作る
先週の「AlcCalc」でのメゾットの結果を核の王する場所も作る
- ・・・\AlcCalc\src\main\javaに
  クラス  「Record.java」作成
- Record
    drDateTime  :飲酒日時(drinking date time)
    drName  :呑んだお酒の名前(drink name)
    conImmediate    :飲酒直後の体調(condition Immediate)
    conNextMorning  :翌朝の体調(condition next morning)
- コンストラクタ
    飲酒日時(drDateTime)をデフォルト(入力日時)にする場合と，過去の日時を指定して入力する場合を作る
- getterメソッドとsetterメソッド
    計算で求めた記録(今回はpureAlcAmount)はsetterを作らずgetterのみにするのがセオリー
        外から書き換えられるとデータの整合性が壊れる
- ・・・\AlcCalc\src\test\java\に
  クラス  「RecordTest.java」を作成
    動作(記録)が正常かを確認するクラス

## Spring Boot × Thymeleaf で『計算機Web』を作る
### プロジェクトのWeb化を準備
- 「pom.xml」に以下の依存関係を追加する
  - spring-boot-starter-web (web機能)
  - spring-boot-sterter-thymeleaf (画面操作機能)
- 「pom.xml」の projectタグ 直下に parentタグ を追記する
- ・・・\AlcCalc\src\main\javaに
  クラス  「AlcApp.java」を作成
  Spring Boot起動用のクラス
### Controllerの作成
ブラウザからデータを受け取り，計算・記録のクラスに送り，結果を画面へ返す役割
- ・・・\AlcCalc\src\main\java\に
  クラス  「AlcController」を作成
- ・・・\AlcCalc\src\resources\templates\に
  ファイル  「index.html」を作成