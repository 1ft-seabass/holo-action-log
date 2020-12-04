# HoloLens 2 のパッケージファイル置き場

## インストール方法

![image](https://i.gyazo.com/49c5f94e1b4d1017e75b8df57cce7581.png)

HoloLens 2 の Device Portal からアクセスして、メニューから Apps へ移動します。

![image](https://i.gyazo.com/d6fb2772f1353a32cfeaa7ff8f5ef4f2.png)

`Allow me to select optional packages` のチェックを ON にします。

![image](https://i.gyazo.com/6da3c5e0f1f5190c3696abe1d3740a35.png)

Select the application package の項目の `ファイルを選択` をクリックして。`holo-action-log-github\hololens2-app\1.0.0.0` フォルダの `HoloWoodActionLog_1.0.0.0_ARM64.appx` のファイルを選択して反映します。

![image](https://i.gyazo.com/c0c8b49a3959aaf97d348c229bc7e58b.png)

ファイルが選択できるとこのような表示になって、アップロードしようとするファイル名が確認できます。

![image](https://i.gyazo.com/62711cc1b6e6e24d7366d9f092fb899f.png)

`Next` ボタンをクリックします。

![image](https://i.gyazo.com/817b898620fee825c855fff7188acb5d.png)

オプションファイルを選択する画面になります。

`ファイルを選択` をクリックして。`holo-action-log-github\hololens2-app\1.0.0.0` フォルダの `Microsoft.VCLibs.ARM64.14.00.appx` のファイルを選択して反映します。

![image](https://i.gyazo.com/d090069c9810428696a75cc148864d21.png)

ファイルが選択できるとこのような表示になって、アップロードしようとするファイル名が確認できます。

確認できたら `Install` ボタンをクリックしましょう。

![image](https://i.gyazo.com/7ba74fbec79a543eae38db529fe07523.png)

![image](https://i.gyazo.com/4b5454d1943efb488611e43b498a47f3.png)

アップロードが進んで、うまくいけば、インストールが成功します。

実機でアプリケーションがインストールされているか確認しましょう！

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

## パッケージの書き出しの仕方

あとで書く