# Mynntils

Wynncraft向けの装備・Ingredient・所有品・Lootrun支援ツールです。WindowsアプリとFabric MODを組み合わせて使用します。

最新バージョン: **0.5.13**

## ダウンロード

[最新のRelease](https://github.com/feruram/Mynntils/releases/latest)から次の2ファイルをダウンロードします。

- `MynntilsApp-0.5.13-windows-x64.zip`
- `mynntils-0.5.13.jar`

Python、PowerShell、Java開発環境、MODのビルドは不要です。

## 前提環境

- Windows 10または11（64ビット）
- Minecraft 1.21.11のFabric環境
- Fabric版Wynntils 4.2.6以降

## 導入

1. `MynntilsApp-0.5.13-windows-x64.zip`を展開します。
2. 展開したフォルダの`MynntilsApp.exe`を起動します。
3. アプリの「設定」でWynnventory APIキーを入力し、「保存」を押します。
4. `mynntils-0.5.13.jar`をMinecraftの`mods`フォルダへ入れます。古いMynntils jarは取り出します。
5. Mynntils Appを起動してからMinecraftを起動します。
6. アプリ上部の`MOD ● 接続中`を確認します。

Windowsから発行元の確認が表示された場合は、ファイル名が`MynntilsApp.exe`であることを確認してから「詳細情報」→「実行」を選択します。

## Wynnventory APIキー

1. [Wynnventory API Key](https://www.wynnventory.com/developer/api-key)を開きます。
2. 必要事項を入力して`Generate Key`を押します。
3. 表示されたキーをアプリの「設定」→「Wynnventory APIキー」へ貼り付けます。
4. 「保存」を押してアプリを再起動します。

APIキーは他人へ共有しないでください。

## 更新

1. アプリとMinecraftを終了します。
2. 新しいWindowsアプリZIPを展開します。
3. `mods`フォルダの古いMynntils jarを新しいjarへ置き換えます。

所有品・設定・APIキーは`ドキュメント\Mynntils`に保存されるため、アプリを更新しても維持されます。

## 接続できない場合

- Mynntils AppをMinecraftより先に起動します。
- アプリとMODのバージョンを揃えます。
- MinecraftとWynntilsの対応バージョンを確認します。
- アプリ設定のItem Manager連携・Lootrun連携を有効にします。

## 通信設定

既定値は`127.0.0.1:8765`です。通常は変更不要です。

- アプリ: 「設定」→「アプリ通信アドレス」「アプリ通信ポート」
- MOD: Minecraftで`O`→「接続先」

MODは既定でアプリの設定を自動取得します。MOD側で個別に指定する場合は「接続先: MODで手動設定」へ切り替え、アプリと同じアドレス・ポートを入力します。変更後はアプリとMinecraftを再起動してください。

## Wynncraftのルール

[規約確認結果](COMPLIANCE.md)を確認してください。最新のWynncraft公式ルールを優先してください。
