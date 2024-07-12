---
title: ' [!DNL Adobe Experience Manager]  デスクトップアプリケーションのベストプラクティスとトラブルシューティング'
description: AEM デスクトップアプリケーションのインストール、アップグレード、設定などで発生することがある問題のトラブルシューティングと、デスクトップアプリケーションのベストプラクティスについて説明します。
exl-id: f388e4ac-907d-4093-ba6f-86ecdafeb015
source-git-commit: 5676e7ece8bb43f051dae72d17e15ab1c34caefc
workflow-type: tm+mt
source-wordcount: '2275'
ht-degree: 100%

---

# [!DNL Adobe Experience Manager] デスクトップアプリケーションのトラブルシューティング {#troubleshoot-v2}

[!DNL Adobe Experience Manager] デスクトップアプリケーションは、[!DNL Experience Manager] デプロイメントのデジタルアセット管理（DAM）リポジトリに接続します。デスクトップアプリケーションは、ユーザーのマシン上でリポジトリ情報と検索結果を取得し、ファイルやフォルダーをダウンロードおよびアップロードします。また、Assets ユーザーインターフェイスとの競合を管理する機能も備えています。

デスクトップアプリケーションのトラブルシューティング、ベストプラクティス、制限事項について説明します。

## ベストプラクティス {#best-practices-to-prevent-troubles}

一般的な問題の回避やトラブルシューティングを図るには、次のベストプラクティスに従います。

* **デスクトップアプリケーションの動作の仕組みを理解する**：使用を開始する前に、少し時間を割いてデスクトップアプリケーションの動作の仕組みを理解してください。[!DNL Experience Manager] web インターフェイスとデスクトップの連携、リポジトリマッピング、アセットキャッシング、ローカルでの保存、バックグラウンドでのアップロードについて把握します。[動作の仕組み](release-notes.md#how-app-works)を参照してください。

* **サポートされていない文字をフォルダー名に使用しない**：フォルダーの作成やアップロードの際には、空白や無効な文字を使用しないでください。該当する文字の一覧については、[ [!DNL Adobe Experience Manager Assets] でのフォルダーの作成](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/assets/managing/manage-assets#creating-folders)を参照してください。フォルダー名にサポートされていない文字が含まれていると、一部の [!DNL Experience Manager] のユースケースに影響する場合があります。

* **競合を回避するためのベストプラクティス**：複数のアセットに対する共同作業で競合が発生する可能性を避けるには、[編集上の競合の回避](using.md#adv-workflow-collaborate-avoid-conflicts)を参照してください。

* **大きな階層フォルダーにはフォルダーアップロードを使用する**：Assets web インターフェイスなどの方法を使用するのではなく、[!DNL Experience Manager] デスクトップアプリケーションを使用して大きなフォルダーをアップロードしてください。デスクトップアプリケーションでは、ログと監視を行いながら、アセットをバックグラウンドでアップロードします。[アセットのバルクアップロード](using.md#bulk-upload-assets)を参照してください。

* **最新バージョンを使用する**：最新バージョンのデスクトップアプリケーションを使用してください。新しいバージョンのデスクトップアプリケーションをインストールする前や、新しいバージョンの [!DNL Experience Manager] にアップグレードする前に、常に互換性を確認してください。[リリースノート](release-notes.md)を参照してください。

* **同じドライブ文字を使用する**：組織全体で同じドライブ文字を使用して、[!DNL Experience Manager] DAM にマッピングします。他のユーザーが配置したアセットを表示するには、同じパスを使用する必要があります。同じドライブ文字を使用することで、DAM アセットのパスが一定になります。別のユーザーが異なるドライブ文字を使用した場合でも、アセットはそのまま残り、削除されません。

* **ネットワークに注意を払う**：[!DNL Experience Manager] デスクトップアプリケーションのパフォーマンスには、ネットワークのパフォーマンスが重要です。ファイル転送や一括操作に対する応答が遅くなった場合は、大量のネットワークトラフィックを発生させる可能性のある機能やデスクトップアプリケーションを無効にしてください。

* **デスクトップアプリケーションでサポートされていないユースケース**：アセットの移行には計画と追加のツールが必要になるので、デスクトップアプリケーションは使用しないでください。また、大きなフォルダーの移動、大規模なアップロード、高度なメタデータ検索など、負荷の高い DAM 操作にも適していません。さらに、そのデザインの原則および使用パターンは Microsoft OneDrive や Adobe Creative Cloud デスクトップ同期などの同期クライアントとは異なるので、同期クライアントとして使用しないでください。

* **タイムアウト**：現在、デスクトップアプリケーションには、一定時間の経過後に [!DNL Experience Manager] サーバーとデスクトップアプリケーションの間の接続を切断するための設定可能なタイムアウト値がありません。サイズの大きいアセットをアップロードする際に、しばらくして接続がタイムアウトした場合、アプリケーションはアップロードタイムアウトを長くして、アセットのアップロードを数回再試行します。デフォルトのタイムアウト設定を変更するお勧めの方法はありません。

## トラブルシューティング方法 {#troubleshooting-prep}

デスクトップアプリケーションの問題をトラブルシューティングするには、以下の情報を把握しておいてください。また、それにより、サポートを依頼する場合にも、アドビカスタマーサポートに問題を伝えやすくなります。

### ログファイルの場所 {#check-log-files-v2}

[!DNL Experience Manager] デスクトップアプリケーションでは、オペレーティングシステムに応じて、次の場所にログファイルを保存します。

Windows の場合： `%LocalAppData%\Adobe\AssetsCompanion\Logs`

Mac の場合： `~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`

多数のアセットをアップロードする際に一部のファイルをアップロードできなかった場合は、`backend.log` ファイルを参照して、アップロードに失敗したファイルを特定します。

>[!NOTE]
>
>サポート依頼やサポートチケットに基づいてアドビカスタマーサポートと共同でトラブルシューティングをおこなう場合は、カスタマーサポートチームが問題を理解しやすいように、ログファイルの提供を求められることがあります。`Logs` フォルダー全体をアーカイブして、カスタマーサポートの担当者と共有します。

### ログファイルの詳細レベルの変更 {#level-of-details-in-log}

ログファイルの詳細レベルを変更するには：

1. デスクトップアプリケーションが動作していないことを確認します。

1. Windows システムの場合：

   1. コマンドウィンドウを開きます。

   1. 次のコマンドを実行して、[!DNL Adobe Experience Manager] デスクトップアプリケーションを起動します。

   ```shell
   set AEM_DESKTOP_LOG_LEVEL=DEBUG&"C:\Program Files\Adobe\Adobe Experience Manager Desktop.exe
   ```

   Mac システムの場合：

   1. ターミナルウィンドウを開きます。

   1. 次のコマンドを実行して、[!DNL Adobe Experience Manager] デスクトップアプリケーションを起動します。

   ```shell
   AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app
   ```

有効なログレベルは、DEBUG、INFO、WARN、ERROR のいずれかです。ログの詳細度は DEBUG で最も高く、ERROR で最も低くなります。

### デバッグモードの有効化 {#enable-debug-mode}

トラブルシューティングをおこなう場合、デバッグモードを有効にして、ログに詳細情報を取得できます。

>[!NOTE]
>
>有効なログレベルは、DEBUG、INFO、WARN、ERROR のいずれかです。ログの詳細度は DEBUG で最も高く、ERROR で最も低くなります。

Mac でアプリケーションをデバッグモードで使用するには：

1. ターミナルウィンドウまたはコマンドプロンプトを開きます。

1. 次のコマンドを実行して、[!DNL Experience Manager] デスクトップアプリケーションを起動します：

   `AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app`。

Windows でデバッグモードを有効にするには：

1. コマンドウィンドウを開きます。

1. 次のコマンドを実行して、[!DNL Experience Manager] デスクトップアプリケーションを起動します：

`AEM_DESKTOP_LOG_LEVEL=DEBUG&"C:\Program Files\Adobe\Adobe Experience Manager Desktop.exe`。

### [!DNL Adobe Experience Manager] デスクトップアプリケーションのバージョンの把握 {#know-app-version-v2}

バージョン番号を確認するには：

1. アプリケーションを起動します。

1. 右上隅の三点リーダーアイコンをクリックし、「[!UICONTROL Help]」にマウスポインターを置いて、「[!UICONTROL About]」をクリックします。

   この画面にバージョン番号が表示されます。

### キャッシュのクリア {#clear-cache-v2}

以下の手順を実行します。

1. デスクトップアプリケーションを起動し、[!DNL Experience Manager] のインスタンスに接続します。

1. 右上隅の三点リーダーアイコンをクリックし「[!UICONTROL Preferences]」を選択して、アプリケーションの環境設定を開きます。

1. 「[!UICONTROL Current Cache Size]」を表示しているエントリを見つけます。この要素の横にあるごみ箱アイコンをクリックします。

キャッシュを手動でクリアするには、次の手順を実行します。

>[!CAUTION]
>
>これらの手順は、破壊的な操作となる可能性があります。ローカルファイルの変更内容が [!DNL Adobe Experience Manager] にアップロードされていない場合、これらの変更内容は失われます。

アプリケーションの環境設定にあるアプリケーションのキャッシュディレクトリを削除すると、キャッシュはクリアされます。

1. アプリケーションを起動します。

1. 右上隅の三点リーダーアイコンを選択し「[!UICONTROL Preferences]」を選択して、アプリケーションの環境設定を開きます。

1. 「[!UICONTROL Cache Directory]」の値をメモしておきます。

   このディレクトリには、エンコードされた [!DNL Adobe Experience Manager] エンドポイントにちなんだ名前のサブディレクトリがあります。これらの名前は、ターゲットとなる [!DNL Adobe Experience Manager] URL のエンコード済みバージョンです。例えば、アプリケーションのターゲットが `localhost:4502` の場合、ディレクトリ名は `localhost_4502` となります。

キャッシュをクリアするには、エンコードされた目的の [!DNL Adobe Experience Manager] エンドポイントディレクトリを削除します。または、環境設定で指定したディレクトリ全体を削除すると、アプリケーションで使用されているすべてのインスタンスでキャッシュがクリアされます。

[!DNL Adobe Experience Manager] デスクトップアプリケーションのキャッシュのクリアは、トラブルシューティングの予備的作業で、これによりいくつかの問題を解決できます。キャッシュのクリアは、アプリの環境設定からおこないます。[環境設定の指定](install-upgrade.md#set-preferences)を参照してください。キャッシュフォルダーのデフォルトの場所は次のとおりです。

## 配置されたアセットが表示されない {#placed-assets-missing}

サポートファイル（INDD ファイルなど）に自分自身または他のクリエイティブプロフェッショナルが配置したアセットが表示されない場合は、次の点を確認してください。

* サーバーへの接続。信頼性の低いネットワーク接続では、アセットのダウンロードが停止するおそれがあります。

* ファイルサイズ。サイズの大きいアセットは、ダウンロードと表示に時間がかかります。

* ドライブ文字の一貫性。[!DNL Experience Manager] DAM を別のドライブ文字にマッピングしている間に、自分自身または他の共同利用者がアセットを配置した場合、配置されたアセットは表示されません。

* 権限。配置されたアセットを取得する権限があるかどうかを確認するには、[!DNL Experience Manager] 管理者に問い合わせてください。

### デスクトップアプリケーションのユーザーインターフェイスで行ったファイルの編集は [!DNL Adobe Experience Manager] にすぐには反映されません {#changes-on-da-not-visible-on-aem}

[!DNL Adobe Experience Manager] デスクトップアプリケーションでは、ファイルに対するすべての編集が完了するタイミングをユーザーが決定できます。ファイルのサイズと複雑さによっては、ファイルの新しいバージョンを [!DNL Adobe Experience Manager] に戻すのに、かなりの時間がかかります。デスクトップアプリケーションは、推測された編集の完了に基づいてファイルを自動的にアップロードするのではなく、ファイル転送数を最小限に抑えるように設計されています。ファイルの変更内容のアップロードを選択して、[!DNL Adobe Experience Manager] へのファイルの転送を開始するようにお勧めします。

### macOS でアップグレードする際の問題 {#issues-when-upgrading-on-macos}

macOS で [!DNL Experience Manager] デスクトップアプリケーションをアップグレードする際に問題が発生することがあります。[!DNL Experience Manager] デスクトップアプリケーションの従来のシステムフォルダーで、これらの問題が発生します。フォルダーにより、新しいバージョンの [!DNL Experience Manager] デスクトップアプリケーションが正しく読み込まれなくなります。この問題を修正するには、以下のフォルダーおよびファイルを手動で削除します。

以下の手順を実行する前に、`Adobe Experience Manager Desktop` アプリケーションを macOS のアプリケーションフォルダーからごみ箱にドラッグします。次に、ターミナルを開き、以下のコマンドを実行します。パスワードを求められたら入力します。

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

## ファイルをアップロードできない {#upload-fails}

デスクトップアプリケーションを [!DNL Experience Manager] 6.5.1 以降で使用している場合は、S3 または Azure コネクタをバージョン 1.10.4 以降にアップグレードします。これで、[OAK-8599](https://issues.apache.org/jira/browse/OAK-8599) に関連するファイルアップロード失敗の問題が解決されます。[インストール手順](install-upgrade.md#install-v2)を参照してください。

## [!DNL Experience Manager] デスクトップアプリケーションの接続の問題 {#connection-issues}

接続に関する一般的な問題が発生した場合は、[!DNL Experience Manager] デスクトップアプリケーションの処理内容に関する詳しい情報を以下のいずれかの方法で入手できます。

**リクエストログの確認**

[!DNL Experience Manager] デスクトップアプリケーションでは、送信したすべてのリクエストと各リクエストの応答コードが専用のログファイルに記録されます。

1. アプリケーションのログディレクトリで `request.log` を開いて、これらのリクエストを確認します。

1. ログの各行は、リクエストか応答のどちらかを表しています。リクエストには、`>` 文字に続いて、リクエストされた URL が含まれます。応答には、`<` 文字に続いて、応答コードとリクエストされた URL が含まれます。各行の GUID を使用して、リクエストと応答を照合できます。

**読み込まれたリクエストをアプリケーションの組み込みブラウザーで確認**

アプリケーションのリクエストの大部分は、リクエストログに記録されています。ただし、そこで有用な情報が得られない場合は、送信されたリクエストをアプリケーションの組み込みブラウザーで調べると役立ちます。これらのリクエストの表示方法については、[SAML に関する節](#da-connection-issue-with-saml-aem)を参照してください。

### SAML ログイン認証が機能しない {#da-connection-issue-with-saml-aem}

[!DNL Experience Manager] デスクトップアプリケーションは、SSO 対応（SAML）[!DNL Adobe Experience Manager] デプロイメントに接続できない場合があります。SSO 接続およびプロセスのバリエーションと複雑さに対応するようにアプリケーションを設計します。ただし、設定については、追加のトラブルシューティングが必要になる可能性があります。

SAML プロセスが、最初にリクエストされたパスにリダイレクトされない場合があります。または、最終的なリダイレクトが、[!DNL Adobe Experience Manager] デスクトップアプリケーションで設定されているホストとは異なるホストに行われます。この問題が発生していないことを確認するには、次の手順を実行します。

1. Web ブラウザーを開きます。`https://[aem_server]:[port]/content/dam.json` の URL にアクセスします。

1. [!DNL Adobe Experience Manager] デプロイメントにログインします。

1. ログインが完了したら、アドレスバーでブラウザーの現在のアドレスを確認します。このアドレスが、最初に入力した URL と正確に一致している必要があります。

1. また、`/content/dam.json` より前の部分がすべて、[!DNL Adobe Experience Manager] デスクトップアプリの設定で指定されたターゲット [!DNL Adobe Experience Manager] 値と一致していることを確認してください。

**上記の手順に従ってログイン SAML プロセスは正常に動作するが、ユーザーはまだログインできない**

ログインプロセスを表示する [!DNL Adobe Experience Manager] デスクトップアプリケーション内のウィンドウは、ターゲット [!DNL Adobe Experience Manager] インスタンスの web ユーザーインターフェイスを表示する web ブラウザーにすぎません。

* Mac 版では [WebView](https://developer.apple.com/documentation/webkit/webview) が使用されます。

* Windows 版では、Chromium ベースの [CefSharp](https://cefsharp.github.io/) が使用されます。

SAML プロセスでこれらのブラウザーがサポートされていることを確認します。

さらにトラブルシューティングをおこなうために、ブラウザーが読み込もうとしている正確な URL を表示できます。次の情報を参照するには：

1. 指示に従って、[デバッグモード](#enable-debug-mode)でアプリケーションを起動します。

1. ログインの試行を再現します。

1. デスクトップアプリケーションの[ログディレクトリ](#check-log-files-v2)に移動します。

1. Windows の場合：

   1. 「aemcompanionlog.txt」を開きます。

   1. 「Login browser address changed to」で始まるメッセージを検索します。これらのエントリには、アプリケーションが読み込んだ URL も含まれています。

   Mac の場合：

   1. `com.adobe.aem.desktop-nnnnnnnn-nnnnnn.log` では、最新のファイル名に含まれる数字が **n** に置き換えられます。

   1. 「loaded frame」で始まるメッセージを検索します。これらのエントリには、アプリケーションが読み込んだ URL も含まれています。

読み込まれる URL シーケンスを調べると、SAML の終わりでトラブルシューティングして、何が悪いかを判断するのに役立ちます。

### SSL 設定の問題 {#ssl-config-v2}

[!DNL Experience Manager] デスクトップアプリケーションが HTTP 通信に使用するライブラリは、厳格に SSL を適用します。ブラウザーでは成功する接続が、[!DNL Experience Manager] デスクトップアプリケーションでは失敗することがあります。SSL を適切に設定するには、不足している中間証明書を Apache にインストールします。[中間 CA の証明書を Apache にインストールするには](https://access.redhat.com/solutions/43575)を参照してください。

[!DNL Experience Manager] デスクトップアプリケーションが HTTP 通信に使用するライブラリは、厳格に SSL を適用します。そのため、ブラウザーで成功した SSL 接続でも、[!DNL Adobe Experience Manager] デスクトップアプリケーションでは失敗する場合があります。この結果は、SSL の正しい設定を推奨しセキュリティを強化するので問題ありませんが、アプリケーションが接続できないことによって不満が生じる可能性があります。

このような場合の推奨されるアプローチは、ツールを使用してサーバーの SSL 証明書を分析し、問題を特定して修正できるようにすることです。URL を提供するとサーバーの証明書を検査する web サイトがあります。

一時的な対策として、[!DNL Adobe Experience Manager] デスクトップアプリケーションで厳密な SSL の強制を無効にすることができます。このアプローチは、SSL の設定が間違っているという根本原因を隠すことによってセキュリティが低下するため、長期的な解決策としては推奨されません。厳密な強制を無効にするには：

1. 任意のエディターを使用して、アプリケーションの JavaScript 設定ファイルを編集します。このファイルは、オペレーティングシステムに応じて（デフォルトでは）次の場所にあります。

   Mac の場合： `/Applications/Adobe Experience Manager Desktop.app/Contents/Resources/javascript/lib-smb/config.json`

   Windows の場合： `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop\javascript\config.json`

1. ファイル内の次のセクションを探します。

   ```shell
   ...
   "assetRepository": {
       "options": {
   ...
   ```

1. 次のように `"strictSSL": false` を追加して、このセクションを変更します。

   ```shell
   ...
   "assetRepository": {
       "options": {
           "strictSSL": false,
   ...
   ```

1. ファイルを保存し、[!DNL Adobe Experience Manager] デスクトップアプリケーションを再起動します。

### 別のサーバーに切り替える際のログインの問題 {#cannot-login-cookies-issue}

[!DNL Experience Manager] サーバーを使用した後、別のサーバーへの接続を変更しようとすると、ログインの問題が発生する場合があります。これは、古い cookie が新しい認証に干渉しているためです。[!UICONTROL Clear Cookies] に対するメインメニューのオプションが役立ちます。アプリの現在のセッションからログアウトし、「[!UICONTROL Clear Cookies]」を選択してから接続を続行します。

![サーバーの切り替え時に cookie をクリア](assets/main_menu_logout_da2.png)

## デスクトップアプリケーションが応答しない {#unresponsive}

まれに、デスクトップアプリケーションが応答しなくなって、白い画面だけが表示されたり、インターフェイスにオプションが表示されずにインターフェイスの下部にエラーが表示されたりする場合があります。このような場合には、以下をこの順に試します。

* デスクトップアプリケーションインターフェイスを右クリックし、「**[!UICONTROL Refresh]**」を選択します。
* アプリケーションを終了して、再度開きます。

どちらの方法でも、DAM のルートフォルダーがデスクトップアプリケーションの初期状態として表示されます。

## 期限切れのアセットを非表示にする {#hide-expired-assets}

[!DNL Experience Manager] ユーザーインターフェイス内からアセットを参照すると、期限切れのアセットは表示されません。管理者は、デスクトップアアプリケーションと Asset Link から参照する際に、期限切れのアセットの表示、検索、取得を防止する設定を使用できます。この設定により、これらの操作中に期限切れのアセットにアクセスできなくなります。この設定は、管理者権限に関係なく、すべてのユーザーで機能します。

* [期限切れのアセットを非表示にするよう Experience Manager 6.5 を設定します](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/assets/managing/manage-assets#hide-expired-assets-via-acp-api)。
* [期限切れのアセットを非表示にするよう Experience Manager as a Cloud Service を設定します](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets#hide-expired-assets-via-acp-api)。

<!--
### Need additional help with [!DNL Experience Manager] desktop app {#additional-help}

Create Jira ticket with the following information:

* Use `DAM - Companion App` as the [!UICONTROL Component].

* Detailed steps to reproduce the issue in [!UICONTROL Description].

* DEBUG level logs that were captured while reproducing the issue.

* Target Experience Manager version.

* Operating system version.

* [!DNL Adobe Experience Manager] desktop app version. To know your app version, see [finding the desktop app version](#know-app-version-v2).
-->

>[!MORELIKETHIS]
>
>* [既知の問題](release-notes.md#known-issues-v2)
>* [編集上の競合の回避](using.md#adv-workflow-collaborate-avoid-conflicts)
