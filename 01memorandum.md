備忘録 2026/04/20
# SandBox(練習台)
## Javaロジックの計算エンジン作成
- 新規プロジェクト  「AlcCalc」作成
  場所: C:\KCGproject04\SandBox\
  ビルドシステム:   Maven
  ==「pom.xml」の< depencies>タグを確認
    書き換え後，右端のm(maven)より，全てのMavenプロジェクトを同期・再ロード==
- ・・・\src\main\java\に
  クラス    「AlcCalc.java」作成
    amountMl    :アルコール摂取量(ml)
    ABV :アルコール度数(Alcohol By Volume)(%)
    pureAlc :純アルコール量(g)
    weight  :ユーザの体重(kg)
    decomposeAlcTime    :推定のアルコール分解に要する時間(hour)

    pureAlc = amountMl × (ABV / 100) × 比重0.8
    decomposeAlcTime = pureAlc / (weight × 0.1)
        体重1kgあたり0.1g/h　アルコールを分解できる
- ・・・\src\test\java\に
  クラス    「AlcCalcTest.java」作成
    動作(計算結果)が正常かを確認するクラス