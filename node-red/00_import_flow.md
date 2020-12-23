# Node-RED にフローをインポート

[フローのインポートとエクスポート : Node\-RED日本ユーザ会](https://nodered.jp/docs/user-guide/editor/workspace/import-export)

こちらの記事を参考に今回のフローJSONデータを Node-RED にインポートします。

![image](https://i.gyazo.com/c2b23ebf7397a18450b9e24c2a094012.png)

Node-RED を起動して、Node-RED にアクセスします。

## node-red-dashboard のインストール

本フローには node-red-dashboard の追加インストールが必要です。

![image](https://i.gyazo.com/3cd99acad2a6eb45b79b79334b768376.png)

メインメニューからパレットを管理するオプションを選択してパレットマネージャを開くことで、 エディタ内で直接ノードをインストールすることができます。

![image](https://i.gyazo.com/456d7cfadfbf5a0950b20bc9f5cee3d5.png)

`ノード追加` のタブをクリックしてノード追加機能を表示します。

![image](https://i.gyazo.com/fb94ca685263b82a04c5b46c9a024107.png)

`ノードを検索` の検索エリアに `node-red-dashboard` を入力して検索します。

![image](https://i.gyazo.com/a790d06e034778ec4cd11b12f6c8e0b7.png)

`node-red-dashboard` の `ノードを追加` ボタンをクリックします。

![image](https://i.gyazo.com/2bd67f46ea32170c4674d8e5e25df45c.png)

このようなウィンドウが出るので追加ボタンを押します。

![image](https://i.gyazo.com/41653251d81da8ec95373d1adee0516d.png)

しばらく待っているをインストールされます。

![image](https://i.gyazo.com/7621e8c21706743a6add8b610c046aa2.png)

パレットに `node-red-dashboard` ノードがインストールされたら完了です。

## flow.json のダウンロード

![image](https://i.gyazo.com/e42accf060cb5cbbac084ff24cb39235.png)

[今回のフローJSONデータ](https://raw.githubusercontent.com/1ft-seabass/holo-action-log/main/node-red/flow.json) を Raw で表示して `flow.json` をいうファイル名でダウンロードします。

もし違うファイル名（例：flow.json.txt）などでダウンロードしたら `flow.json` に修正しましょう。

## ドラッグアンドドロップしてインポート

![image](https://i.gyazo.com/e4310c67517ffc32bed16074bda0394b.png)

Node-RED に `flow.json` をドラッグアンドドロップします。このように、少し暗転して「ここにフローをドロップしてください」と出るので、マウスを離してドロップします。

![image](https://i.gyazo.com/a92bc10f47ea07e6dad70f5adc15380a.png)

ドロップすると、マウスについてくる形で、フローがインポートされます。マウスをもう一度クリックして配置を確定させましょう。

![image](https://i.gyazo.com/ae53e22bc65cf171748205fc660f8084.png)

右上のデプロイをクリックしてプログラムを確定させます。

## CSV の保存先を設定

![image](https://i.gyazo.com/a9adb3dc98fe0bdbe274f716a2237804.png)

フロー群の中からこのフローを探しましょう。

![image](https://i.gyazo.com/3992f6307272a6cfef3cbd2c0640f4ab.png)

`デフォルトパス hololens-record.csv` という名前の inject ノードをクリックします。

![image](https://i.gyazo.com/5c05ff437877975832066f24074fa7a5.png)

payload の設定を、今回保存したいファイルパスに変更しましょう。

![image](https://i.gyazo.com/ae53e22bc65cf171748205fc660f8084.png)

右上のデプロイをクリックしてプログラムを確定させます。

## 動作確認

![image](https://i.gyazo.com/7bc2e96c4a4bb89b8e60e51521571636.png)

この写真のようにサイドバーの ![image](https://i.gyazo.com/2516e5d8857f4e560ebb70dc60da524d.png) をクリックして `ダッシュボード` をクリックします。

![image](https://i.gyazo.com/e9aaab3ddb3aa2fd7fc82c7dfdc74abc.png)

ダッシュボードの詳細が表示されます。

![image](https://i.gyazo.com/6439cc32401634197aed62e2941755f1.png)

この赤枠で囲われたボタンをクリックするとダッシュボードが表示されます。

![image](https://i.gyazo.com/8afa6dbfae72136e4f58ee6ab8ce562d.png)

ダッシュボードが表示されたらOKです！

## CSV の保存先を確認

![image](https://i.gyazo.com/e3437df18644c8529b08ab383ab5d936.png)

右上のメニューを開きます。

![image](https://i.gyazo.com/fda0bd91f2d6bc3803b6f8c558660e9d.png)

管理画面をクリックします。

![image](https://i.gyazo.com/cf1bd0bacb2ab103733bd16cd1daeb9a.png)

`HoloLens 記録 CSV ファイルパス` で設定値が正しいか確認しましょう。

## 次は

[README](../README.md) に戻って次の手順に進みます