## MacPairing
WindowsのVisualStudio2022で作る.net mauiとmacOS Ventura(13.7.5)とのペアリング方法

### Mac 側の設定
1. Xcodeをインストール
   macOS13.7.5に対応したXcode14.3.1をインストールする。

   https://learn.microsoft.com/ja-jp/previous-versions/xamarin/ios/troubleshooting/questions/previous-xcode
   
   
2. .NETをインストール
   macOS13.7.5に対応した.NET8をインストールする。
   
   https://dotnet.microsoft.com/ja-jp/download/dotnet/8.0

### .net maui 側の設定
1. .net mauiプロジェクト作成時、フレームワークに.NET8を設定する
   ![image](https://github.com/user-attachments/assets/0574320e-5402-4fe8-ab61-afb5404c3402)

2. iPhoneを選択してビルド実施する
   ![image](https://github.com/user-attachments/assets/ed275842-2445-4b8a-bd45-bac740b38d44)

   以下のエラーが表示される
   ![image](https://github.com/user-attachments/assets/b9338f11-14f8-4b9e-b3d9-2f146fe47cb7)

   プロジェクトのプロパティのiOS->BuildにあるLinker behaviorのDebug & net8.0-iosを「Don't Link」から「Link Framework SDKs Only」に変更
   ![image](https://github.com/user-attachments/assets/20b5276f-3070-4607-8a11-33d74ce10642)

   シュミレータにiPhoneが表示されなくなった場合はペアリングが切れてるかも
   ![image](https://github.com/user-attachments/assets/ad846540-74e9-4cea-b66f-1302ddd5ebdf)

3. WindowsでiPhoneのシュミレータを表示する
   ツール→オプションでオプション画面を表示する。
   Xamarin->iOS Settingsの「Remote Simulator to Windows」をチェックONにする
   ![image](https://github.com/user-attachments/assets/f5b290f3-daaa-4704-9222-7b1093007c82)




