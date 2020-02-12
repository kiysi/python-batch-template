# Python バッチファイル用テンプレートプロジェクト

このプロジェクトは基底バッチクラスとそれを継承する各バッチクラスが存在する構成です。

基底バッチクラスで`ロガー設定`、`バッチ共通前後処理`、`例外処理`を実装するため実際のバッチ処理を行う個々のサブクラスではそれらを実装する必要がなくなります。

`バッチ共通前後処理`はデフォルトで以下の処理を実装しています。

- バッチ実行開始・終了ログ出力
- バッチ処理時間計測

`例外処理`ではデフォルトで以下の処理を実装しています。

- 例外ログ出力
- slack通知

なおサブクラスのバッチ処理内で独自に例外を処理することももちろん可能です。キャッチした例外を再スローしないかぎり基底クラスの例外処理は実行されません。

## 前提

このプロジェクトではパッケージ管理にpipenvを使用しています。

- [pipenv]()

※ただしpipenvは必須ではなく、標準のpipでも特に問題はありません。その場合は以下のパッケージをpipでインストールします。

- requests
- python-dotenv