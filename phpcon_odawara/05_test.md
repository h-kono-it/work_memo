# テストアンチパターン回避

@samurai_se

## 明日からでもでいること

### テスト名

アンチパターン
isExistPrefectureというテスト名：何を検証していて、何がエラーなのかわからない

### AAAパターン

- Arrange：準備
- Act：実行
- assertion：検証

### パラメタライズテスト

パラメーターと結果をマッチングしたオブジェクトでテストする

### エラーはキャッチせずにエラーを期待する

例外が起こるテストは例外のエラークラスを検証するようにする（キャッチして検証しない

## 継続的にやっていくこと

### カバレッジ

50～80くらいが良さそう

90%以上だとクリティカルな実装以外のテストまで行ってしまいそう

#### 目標値に満たない場合CIを中止する

Laravel9からパラメーターで設定できる

#### カバレッジレポートをちゃんと見る

極端に低いカバレッジは確認する

週単位等で確認する時間を作ったほうが良い

## さらにその先

### mutation test

意図的なバグをコードに埋めて、落ちるか確認する

コードを意図的に変更し、バグを植え付ける

- Killed：失敗すべきテストが失敗した件数
- Survived：失敗すべきテストが成功した件数

Mutation Scoreを継続的に比較したほうが良いが、実行が遅い
