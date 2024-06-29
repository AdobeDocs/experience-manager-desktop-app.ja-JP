---
title: ' [!DNL Adobe Experience Manager]  デスクトップアプリケーションのベストプラクティスとトラブルシューティング'
description: AEM デスクトップアプリケーションのインストール、アップグレード、設定などで発生することがある問題のトラブルシューティングと、デスクトップアプリケーションのベストプラクティスについて説明します。
exl-id: f388e4ac-907d-4093-ba6f-86ecdafeb015
source-git-commit: 5676e7ece8bb43f051dae72d17e15ab1c34caefc
workflow-type: tm+mt
source-wordcount: '2275'
ht-degree: 55%

---

# [!DNL Adobe Experience Manager] デスクトップアプリケーションのトラブルシューティング {#troubleshoot-v2}

[!DNL Adobe Experience Manager] デスクトップアプリケーションはに接続 [!DNL Experience Manager] デプロイメントのデジタルアセット管理（DAM）リポジトリ。 このアプリは、リポジトリ情報と検索結果をコンピューターで取得し、ファイルやフォルダーをダウンロードしてアップロードします。また、Assets ユーザーインターフェイスとの競合を管理する機能も含まれています。

デスクトップアプリケーションのトラブルシューティング、ベストプラクティス、制限事項について説明します。

## ベストプラクティス {#best-practices-to-prevent-troubles}

一般的な問題の回避やトラブルシューティングを図るには、次のベストプラクティスに従います。

* **デスクトップアプリケーションの動作の仕組みを理解する**：使用を開始する前に、少し時間を割いてデスクトップアプリケーションの動作の仕組みを理解してください。の間のリンクについて [!DNL Experience Manager] web インターフェイスとデスクトップ、リポジトリのマッピング、アセットのキャッシュ、ローカルでの保存、バックグラウンドでのアップロード。 [動作の仕組み](release-notes.md#how-app-works)を参照してください。

* **サポートされていない文字をフォルダー名に使用しない**：フォルダーの作成やアップロードの際には、空白や無効な文字を使用しないでください。該当する文字の一覧については、[ [!DNL Adobe Experience Manager Assets] でのフォルダーの作成](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/assets/managing/manage-assets#creating-folders)を参照してください。フォルダー名にサポートされていない文字が含まれていると、影響を受ける可能性があります [!DNL Experience Manager] ユースケース。

* **競合を回避するためのベストプラクティス**：複数のアセットで共同作業する際に競合が発生する可能性を回避するには、次の場所に移動します。 [編集上の競合の回避](using.md#adv-workflow-collaborate-avoid-conflicts).

* **大きな階層フォルダーにはフォルダーアップロードを使用する**:Assets web インターフェイスやその他の手段を使用する代わりに、次を使用します [!DNL Experience Manager] 大きなフォルダーをアップロードするデスクトップアプリケーション。 アプリは、ログとモニタリングを使用して、バックグラウンドでアセットをアップロードします。 [アセットのバルクアップロード](using.md#bulk-upload-assets)を参照してください。

* **最新バージョンを使用**：最新バージョンのアプリを使用します。 新しいアプリバージョンをインストールする前や、新しいバージョンにアップグレードする前に、常に互換性を確認してください [!DNL Experience Manager] バージョン。 [リリースノート](release-notes.md)を参照してください。

* **同じドライブ文字を使用する**：組織全体で同じドライブ文字を使用して、[!DNL Experience Manager] DAM にマッピングします。他のユーザーが配置したアセットを表示するには、同じパスを使用する必要があります。同じドライブ文字を使用することで、DAM アセットのパスが一定になります。別のユーザーが異なるドライブ文字を使用した場合でも、アセットはそのまま残り、削除されません。

* **ネットワークに注意を払う**：[!DNL Experience Manager] デスクトップアプリケーションのパフォーマンスには、ネットワークのパフォーマンスが重要です。ファイル転送や一括操作への応答が遅くなる場合は、大量のネットワークトラフィックを引き起こす可能性のある機能やアプリをオフにします。

* **デスクトップアプリケーションでサポートされていないユースケース**：このアプリは計画や追加のツールが必要なので、アセット移行には使用しないでください。 また、大きなフォルダーの移動、大きなアップロード、高度なメタデータ検索など、高負荷の DAM 操作にも適していません。 また、デザイン原則や使用パターンは、Microsoft OneDrive やAdobe Creative Cloud デスクトップ同期などの同期クライアントとは異なるので、同期クライアントとして使用しないでください。

* **タイムアウト**：現在、デスクトップアプリケーションには、接続を切断する設定可能なタイムアウト値がありません [!DNL Experience Manager] 一定の時間間隔の後のサーバーとデスクトップアプリケーション。 サイズの大きいアセットをアップロードする際に、しばらくして接続がタイムアウトした場合、アプリケーションはアップロードタイムアウトを長くして、アセットのアップロードを数回再試行します。デフォルトのタイムアウト設定を変更するお勧めの方法はありません。

## トラブルシューティング方法 {#troubleshooting-prep}

デスクトップアプリケーションの問題をトラブルシューティングするには、以下の情報を把握しておいてください。また、サポートを依頼する場合に、Adobeカスタマーサポートに問題を伝える準備にもなります。

### ログファイルの場所 {#check-log-files-v2}

この [!DNL Experience Manager] デスクトップアプリケーションは、オペレーティングシステムに応じて、以下の場所にログファイルを保存します。

Windows の場合： `%LocalAppData%\Adobe\AssetsCompanion\Logs`

Mac の場合： `~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`

多数のアセットをアップロードする際に一部のファイルをアップロードできなかった場合は、`backend.log` ファイルを参照して、アップロードに失敗したファイルを特定します。

>[!NOTE]
>
>サポート依頼やサポートチケットに基づいてアドビカスタマーサポートと共同でトラブルシューティングをおこなう場合は、カスタマーサポートチームが問題を理解しやすいように、ログファイルの提供を求められることがあります。`Logs` フォルダー全体をアーカイブして、カスタマーサポートの担当者と共有します。

### ログファイルの詳細レベルの変更 {#level-of-details-in-log}

ログファイルの詳細レベルを変更するには：

1. アプリケーションが実行されていないことを確認します。

1. Windows システムの場合：

   1. コマンドウィンドウを開きます。

   1. を起動する [!DNL Adobe Experience Manager] 次のコマンドを実行してデスクトップアプリケーションを実行します。

   ```shell
   set AEM_DESKTOP_LOG_LEVEL=DEBUG&"C:\Program Files\Adobe\Adobe Experience Manager Desktop.exe
   ```

   Mac システムの場合：

   1. ターミナルウィンドウを開きます。

   1. を起動する [!DNL Adobe Experience Manager] 次のコマンドを実行してデスクトップアプリケーションを実行します。

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

1. アプリケーションを起動し、のインスタンスに接続します。 [!DNL Experience Manager].

1. 右上隅の三点リーダーアイコンをクリックし「[!UICONTROL Preferences]」を選択して、アプリケーションの環境設定を開きます。

1. 「[!UICONTROL Current Cache Size]」を表示しているエントリを見つけます。この要素の横にあるごみ箱アイコンをクリックします。

キャッシュを手動でクリアするには、次の手順を実行します。

>[!CAUTION]
>
>これらの手順は、破壊的な可能性がある操作です。 にアップロードされていないローカルファイルの変更がある場合 [!DNL Adobe Experience Manager]その後、これらの変更は失われます。

アプリケーションの環境設定にあるアプリケーションのキャッシュディレクトリを削除すると、キャッシュはクリアされます。

1. アプリケーションを起動します。

1. 右上隅の三点リーダーアイコンを選択し「[!UICONTROL Preferences]」を選択して、アプリケーションの環境設定を開きます。

1. 「[!UICONTROL Cache Directory]」の値をメモしておきます。

   このディレクトリには、エンコードされたという名前のサブディレクトリが存在します [!DNL Adobe Experience Manager] エンドポイント。 名前は、ターゲットののエンコードされたバージョンです [!DNL Adobe Experience Manager] URL。 例えば、アプリケーションがターゲティングを行っているとします `localhost:4502`を指定すると、ディレクトリ名はになります。 `localhost_4502`.

キャッシュをクリアするには、エンコードされた目的の [!DNL Adobe Experience Manager] エンドポイントディレクトリを削除します。または、環境設定で指定したディレクトリ全体を削除すると、アプリケーションで使用されているすべてのインスタンスのキャッシュがクリアされます。

[!DNL Adobe Experience Manager] デスクトップアプリケーションのキャッシュのクリアは、トラブルシューティングの予備的作業で、これによりいくつかの問題を解決できます。キャッシュのクリアは、アプリの環境設定からおこないます。[環境設定の指定](install-upgrade.md#set-preferences)を参照してください。キャッシュフォルダーのデフォルトの場所は次のとおりです。

## 配置されたアセットが表示されない {#placed-assets-missing}

サポートファイル（INDD ファイルなど）に自分自身または他のクリエイティブプロフェッショナルが配置したアセットが表示されない場合は、次の点を確認してください。

* サーバーへの接続。信頼性の低いネットワーク接続では、アセットのダウンロードが停止するおそれがあります。

* ファイルサイズ。サイズの大きいアセットは、ダウンロードと表示に時間がかかります。

* ドライブ文字の一貫性。[!DNL Experience Manager] DAM を別のドライブ文字にマッピングしている間に、自分自身または他の共同利用者がアセットを配置した場合、配置されたアセットは表示されません。

* 権限。配置されたアセットを取得する権限があるかどうかを確認するには、[!DNL Experience Manager] 管理者に問い合わせてください。

### デスクトップアプリケーションのユーザーインターフェイスでおこなったファイルの編集はに反映されません [!DNL Adobe Experience Manager] 即時 {#changes-on-da-not-visible-on-aem}

[!DNL Adobe Experience Manager] デスクトップアプリケーションでは、ファイルに対するすべての編集が完了するタイミングをユーザーが決定できます。ファイルのサイズと複雑さによっては、新しいバージョンのファイルをに転送し直すのに、かなりの時間がかかります [!DNL Adobe Experience Manager]. このアプリケーションは、推測された編集の完了に基づいてファイルを自動的にアップロードするのではなく、ファイル転送数を最小限に抑えるように設計されています。 ファイルの変更内容のアップロードを選択して、[!DNL Adobe Experience Manager] へのファイルの転送を開始するようにお勧めします。

### macOS でアップグレードする際の問題 {#issues-when-upgrading-on-macos}

場合によっては、のアップグレード時に問題が発生することがあります [!DNL Experience Manager] macOSのデスクトップアプリケーション。 のレガシーシステムフォルダー [!DNL Experience Manager] デスクトップアプリケーションでは、これらの問題が発生します。 フォルダーにより、の新しいバージョンを使用できなくなります。 [!DNL Experience Manager] デスクトップアプリケーションが正しく読み込まれるようにします。 この問題を修正するには、以下のフォルダーおよびファイルを手動で削除します。

次の手順を実行する前に、 `Adobe Experience Manager Desktop` アプリケーションをmacOSのアプリケーションフォルダーからごみ箱に移動します。 次に、ターミナルを開き、次のコマンドを実行し、プロンプトが表示されたらパスワードを入力します。

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

## ファイルをアップロードできない {#upload-fails}

デスクトップアプリケーションをで使用する場合 [!DNL Experience Manager] 6.5.1 以降、S3 または Azure コネクタをバージョン 1.10.4 以降にアップグレードしてください。 に関連するファイルアップロードの失敗の問題を解決します [OAK-8599](https://issues.apache.org/jira/browse/OAK-8599). [インストール手順](install-upgrade.md#install-v2)を参照してください。

## [!DNL Experience Manager] デスクトップアプリケーションの接続の問題 {#connection-issues}

一般的な接続の問題が発生している場合は、次の方法で詳細を確認できます [!DNL Experience Manager] デスクトップアプリケーションが実行中です。

**リクエストログの確認**

この [!DNL Experience Manager] デスクトップアプリケーションは、送信したすべてのリクエストと各リクエストの応答コードを専用のログファイルに記録します。

1. アプリケーションのログディレクトリで `request.log` を開いて、これらのリクエストを確認します。

1. ログの各行は、リクエストか応答のどちらかを表しています。リクエストにはが含まれています `>` リクエストされた URL の後に文字が続く。 回答にはが含まれています `<` 文字の後に応答コードとリクエストされた URL が続きます。 各行の GUID を使用して、リクエストと応答を照合できます。

**読み込まれたリクエストをアプリケーションの組み込みブラウザーで確認**

アプリケーションのリクエストの大部分は、リクエストログに記録されています。ただし、そこで有用な情報が得られない場合は、送信されたリクエストをアプリケーションの組み込みブラウザーで調べると役立ちます。これらのリクエストの表示方法については、[SAML に関する節](#da-connection-issue-with-saml-aem)を参照してください。

### SAML ログイン認証が機能しない {#da-connection-issue-with-saml-aem}

[!DNL Experience Manager] デスクトップアプリケーションは、SSO 対応（SAML）[!DNL Adobe Experience Manager] デプロイメントに接続できない場合があります。SSO 接続およびプロセスのバリエーションと複雑さに対応するようにアプリケーションを設計します。ただし、設定については、追加のトラブルシューティングが必要になる可能性があります。

SAML プロセスが、最初にリクエストされたパスにリダイレクトされない場合があります。 または、で設定されているものとは異なるホストにリダイレクトされます。 [!DNL Adobe Experience Manager] デスクトップアプリケーション。 この問題が該当しないことを確認するには、次の手順を実行します。

1. Web ブラウザーを開きます。 `https://[aem_server]:[port]/content/dam.json` の URL にアクセスします。

1. [!DNL Adobe Experience Manager] デプロイメントにログインします。

1. ログインが完了したら、アドレスバーでブラウザーの現在のアドレスを確認します。このアドレスが、最初に入力した URL と正確に一致している必要があります。

1. また、`/content/dam.json` より前の部分がすべて、[!DNL Adobe Experience Manager] デスクトップアプリの設定で指定されたターゲット [!DNL Adobe Experience Manager] 値と一致していることを確認してください。

**ログイン SAML プロセスは上記の手順に従って正しく機能しますが、ユーザーはまだログオンできません**

内のウィンドウ [!DNL Adobe Experience Manager] ログインプロセスを表示するデスクトップアプリは、ターゲットを表示する web ブラウザーにすぎません [!DNL Adobe Experience Manager] インスタンスの web ユーザーインターフェイス：

* Mac 版では [WebView](https://developer.apple.com/documentation/webkit/webview) が使用されます。

* Windows 版では、Chromium ベースの [CefSharp](https://cefsharp.github.io/) が使用されます。

SAML プロセスでこれらのブラウザーがサポートされていることを確認します。

さらにトラブルシューティングをおこなうために、ブラウザーが読み込もうとしている正確な URL を表示できます。次の情報を参照するには：

1. 指示に従って、[デバッグモード](#enable-debug-mode)でアプリケーションを起動します。

1. ログインの試行を再現します。

1. に移動します。 [ログディレクトリ](#check-log-files-v2) アプリケーションの。

1. Windows の場合：

   1. 「aemcompanionlog.txt」を開きます。

   1. 「Login browser address changed to」で始まるメッセージを検索します。 これらのエントリには、アプリケーションが読み込んだ URL も含まれています。

   Mac の場合：

   1. 対象： `com.adobe.aem.desktop-nnnnnnnn-nnnnnn.log`。最新のファイル名で次の値を置換 **n**.

   1. 「読み込まれたフレーム」で始まるメッセージを検索します。 これらのエントリには、アプリケーションが読み込んだ URL も含まれています。

読み込まれる URL シーケンスを調べると、SAML の終わりでトラブルシューティングして、何が悪いかを判断するのに役立ちます。

### SSL 設定の問題 {#ssl-config-v2}

が実行するライブラリ [!DNL Experience Manager] を使用した HTTP 通信では、デスクトップアプリケーションで厳密な SSL 強制が使用されます。 ブラウザーを使用した接続が成功しても、を使用した接続が失敗する場合があります [!DNL Experience Manager] デスクトップアプリケーション。 SSL を適切に設定するには、不足している中間証明書を Apache にインストールします。[中間 CA の証明書を Apache にインストールするには](https://access.redhat.com/solutions/43575)を参照してください。

が実行するライブラリ [!DNL Experience Manager] デスクトップアプリケーションで HTTP 通信にを使用する場合は、厳密な SSL 強制を使用します。 そのため、ブラウザーを介した SSL 接続が成功せず、で失敗する場合があります [!DNL Adobe Experience Manager] デスクトップアプリケーション。 この結果は、SSL の正しい設定を奨励し、セキュリティを強化するので優れていますが、アプリケーションが接続できない場合はフラストレーションが生じる可能性があります。

このような場合の推奨されるアプローチは、ツールを使用してサーバーの SSL 証明書を分析し、問題を特定して修正できるようにすることです。URL を指定してサーバーの証明書を検査する Web サイトがあります。

一時的な対策として、で厳密な SSL 強制を無効にすることができます。 [!DNL Adobe Experience Manager] デスクトップアプリケーション。 このアプローチは、誤って設定された SSL の根本原因を隠すことでセキュリティを軽減するので、推奨される長期的なソリューションではありません。 厳密な強制を無効にするには：

1. 任意のエディターを使用して、アプリケーションの JavaScript 設定ファイルを編集します。このファイルは、（オペレーティングシステムに応じて）次の場所にあります。

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

1. ファイルを保存して、 [!DNL Adobe Experience Manager] デスクトップアプリケーション。

### 別のサーバーに切り替える際のログインの問題 {#cannot-login-cookies-issue}

[!DNL Experience Manager] サーバーを使用した後、別のサーバーへの接続を変更しようとすると、ログインの問題が発生する場合があります。これは、古い cookie が新しい認証に干渉しているためです。[!UICONTROL Clear Cookies] に対するメインメニューのオプションが役立ちます。アプリの現在のセッションからログアウトし、「[!UICONTROL Clear Cookies]」を選択してから接続を続行します。

![サーバーの切り替え時に cookie をクリア](assets/main_menu_logout_da2.png)

## デスクトップアプリケーションが応答しない {#unresponsive}

まれに、デスクトップアプリケーションが応答しなくなって、白い画面だけが表示されたり、インターフェイスにオプションが表示されずにインターフェイスの下部にエラーが表示されたりする場合があります。このような場合には、以下をこの順に試します。

* デスクトップアプリケーションインターフェイスを右クリックし、「**[!UICONTROL Refresh]**」を選択します。
* アプリケーションを終了して、再度開きます。

どちらの方法でも、DAM のルートフォルダーがデスクトップアプリケーションの初期状態として表示されます。

## 期限切れのアセットを非表示にする {#hide-expired-assets}

内からのアセットの参照時 [!DNL Experience Manager] ユーザーインターフェイスに、期限切れのアセットは表示されません。 管理者は、デスクトップアプリと Asset Link から参照する際に、期限切れのアセットが表示、検索、および取得されないように設定を指定できます。 これにより、これらの操作中に有効期限切れのアセットにアクセスできなくなります。 この設定は、管理者権限に関係なく、すべてのユーザーで機能します。

* [期限切れのアセットを非表示にするよう Experience Manager 6.5 を設定します](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/assets/managing/manage-assets#hide-expired-assets-via-acp-api)。
* [期限切れのアセットを非表示にするよう Experience Manager as a Cloud Service を設定します](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets#hide-expired-assets-via-acp-api)。

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
