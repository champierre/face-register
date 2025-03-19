# Face Register

顔情報を登録するシンプルなWebアプリケーション

## 概要

このアプリケーションは、Webカメラを使用して顔を検出し、顔情報とIDを登録することができます。登録された顔情報はGoogle Apps Scriptを通じてサーバーに保存され、いつでも確認・削除することができます。表示用のデータはブラウザのローカルストレージにも保存されます。

## 機能

- Webカメラからのリアルタイム顔検出
- 検出された顔のキャプチャ
- 顔情報とIDの登録
- 登録済み顔情報の表示と管理

## 使用技術

- HTML5
- CSS3
- JavaScript (ES6+)
- [face-api.js](https://github.com/vladmandic/face-api) - 顔検出・認識ライブラリ

## 使用方法

1. アプリケーションを開くと、カメラが自動的に起動します
   - URLパラメータで保存先を指定できます: `index.html?findUrl=<顔登録のPOST先URL>`
   - URLパラメータで会員IDを指定できます: `index.html?memberId=<ユーザーID>`
   - 複数のパラメータを同時に指定することも可能です: `index.html?findUrl=<顔登録のPOST先URL>&memberId=<ユーザーID>`
   - URLパラメータが指定されない場合は、デフォルトで `https://script.google.com/` に送信されます
   - memberIdパラメータが指定された場合、IDのテキストフィールドに自動的に入力されます
2. 「登録」ボタンは以下の条件がすべて満たされた場合のみ有効になります：
   - カメラに顔が検出されている
   - 検出された顔が1つだけである
   - ユーザーIDが入力されている
3. 登録ボタンが押せない場合は、その理由がIDフィールドの下に表示されます（ステータスメッセージは状態が変わった時のみ更新されます）
4. 「登録」ボタンをクリックすると、顔情報が自動的にキャプチャされ登録されます
5. 登録処理中は「登録」ボタンが無効化され、処理状況がIDフィールドの下に表示されます

## 注意事項

- このアプリケーションはデータをサーバーに保存しますが、表示用のデータはブラウザのローカルストレージにも保存されます
- サーバーとの通信にはインターネット接続が必要です
- カメラへのアクセス許可が必要です
- 最新のブラウザ（Chrome, Firefox, Edge など）での使用を推奨します
