# HoloLens 2 アプリの setting.json 方法

## TCP の送り先の設定

![image](https://i.gyazo.com/bacd52f8bfc7be31ee63eb37d7ae8fdb.png)

HoloLens 2 の Device Portal からアクセスして、メニューから File explorer へ移動します。

![image](https://i.gyazo.com/cf210abbf931e0b7f0314015c6b2ece9.png)

`User Folders \ LocalAppData \ HoloWoodActionLog_1.0.0.0_arm64__pzq3xp76mxafg \ LocalState \ setting.json` という階層に移動します。

![image](https://i.gyazo.com/3c476cc371c2f9b249c89237a3a7086d.png)

`setting.json` の横にある SAVE ボタンで、PCに保存します。

`HoloWoodActionLog_1.0.0.0_arm64__pzq3xp76mxafg` というファイル名は、インストールするパッケージによって名称が変わりますので読み替えてください。

![image](https://i.gyazo.com/310c1ef3328a572a493f2010f04faa7f.png)

Visual Studio Code などエディタで開いてみるとこのようになっています。

* tcpAddress
  * TCP 通信の送り先 IP アドレス
* tcpPort
  * TCP 通信の送り先のポート番号

となっています。これを、今回送信する Node-RED サーバーの TCP 通信( IP アドレス・ポート番号 ) に設定してテキストファイルを保存します。

![image](https://i.gyazo.com/c092674f3eb30d7c898a21beafa464fd.png)

アップロードは、さきほどの File explore の下部にあります。（分かりにくいですが）

![image](https://i.gyazo.com/f4c06e2c9242c9ebc9a373d93605a0a7.png)

ファイルが選択できるとこのような表示になって、アップロードしようとするファイル名が確認できます。

`Upload` ボタンをクリックしてアップロードします。

![image](https://i.gyazo.com/b9695764af3d6d2ca3e23d293e5e3eae.png)

アップロードしても、Date Created の日時も変化がなく戸惑うかもしれません。

そのときは、一度、フォルダの上の階層に移動して、再度フォルダに戻ってくると、Date Created の日時の変化が確認できるはずです。

これで `setting.json` が更新され、アプリを起動すると、通信先が変わります。

## 次は

[../README.md](README) に戻って次の手順に進みます