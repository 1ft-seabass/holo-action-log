# holo-action-log

## 0. 事前準備

* [事前準備 Node-RED](./preparation/node-red.md)

## 1. Node-RED のローカルネットワーク内のIPアドレスを把握

次の HoloLens 2 で設定するときに必要です。

Node-RED のローカルネットワーク内のIPアドレスを把握しておきましょう。

* Windows の場合
  * コマンドプロンプトで `ipconfig` を実行して把握する
    * 参考：[ターミナルからプライベートIPアドレスとMACアドレス、ルーティングテーブルを確認する \- bambinya's blog](http://bambinya.hateblo.jp/entry/2015/04/04/234428)
* Mac の場合
  * ターミナルで `ipconfig` を実行して把握する
    * 参考：[macOS で自分のプライベート IP アドレスを見つける方法 \- yu8mada](https://yu8mada.com/2018/07/14/how-to-find-my-private-ip-address-in-macos/#content-3-3)

把握出来たら `http://localhost:1880` ではなく、`http://<今回把握したNode-RED のローカルネットワーク内のIPアドレス>:1880` でアクセスできるか確認します。

たとえば、Node-RED のローカルネットワーク内のIPアドレスが 192.168.1.2 の場合、`http://192.168.1.2` となります。

## 2. HoloLens 2 アプリのインストール

[HoloLens 2 アプリのインストール方法](./hololens2-app/00_install_application.md) を参考に HoloLens 2 にアプリをインストールをお願いします。

## 3. HoloLens 2 アプリの setting.json ファイルで Node-RED のIPアドレスとTCPポート番号を指定

[HoloLens 2 アプリの setting.json 方法](./hololens2-app/01_edit_setting.md) を参考にHoloLens 2 アプリの setting.json ファイルで Node-RED のIPアドレスとTCPポート番号を指定します。

* IPアドレス
  * Node-RED のローカルネットワーク内のIPアドレスを把握したもの
* TCPポート番号
  * Node-RED のフローでTCPポート番号の変更がなければ `18801` のままでOK

## 4. Node-RED にフローをインポート

[こちらのREADME](./node-red/00_import_flow.md) を参考にNode-RED にフローをインポートをお願いします。

## 5. HoloLens 2 と Node-RED 連携して試してみる

![image](https://i.gyazo.com/cd54c452cf103cea075cc8c96afbb8ab.png)

Node-RED ではダッシュボードを表示して待ちます。

![image](https://i.gyazo.com/7a81e21957268bf8392961dd191d13b1.jpg)

HoloLens 2 でアプリを起動します。

![image](https://i.gyazo.com/a86c003885de89b7450d9a8d2988d97a.png)

ダッシュボードに値が送り込まれてくるはずです。

## 6. データの記録開始と終了

![image](https://i.gyazo.com/0aa4fd9c2b136ac8bce80bc3df4a9700.png)

ダッシュボード > HoloLens のところに `データ記録` という項目にスイッチがあります。

![image](https://i.gyazo.com/1dc0e268b5f9ad940a79957e34725944.png)

これを ON にすると記録がはじまり、record start というメッセージが CSV に記録されます。また、このようにスイッチの下部に、CSV へ記録された最新のデータが 1 行確認できます。

![image](https://i.gyazo.com/6167ef9d9f600c0c2ae9fb5097269d17.png)

OFF にすると record end というメッセージが CSV に記録されます。

**この設定は Node-RED を再度デプロイすると、一旦 OFF に戻ります。**

![image](https://i.gyazo.com/1b9383d5d5e174696a3550561bc2fb5d.png)

このようにログが記録されるので、記録の開始終了がわかりやすくなります。