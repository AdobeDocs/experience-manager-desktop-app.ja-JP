---
title: デスクトップアプリケーションのインストールと設定
description: ' [!DNL Adobe Experience Manager]  デスクトップアプリケーション  [!DNL Adobe Experience Manager Assets]  をインストールして、 サーバーと連携しアセットをローカルファイルシステムにダウンロードするように設定します。'
feature: Desktop App,Release Information
exl-id: 422e51c1-c456-4151-bb43-4b3d29a58187
source-git-commit: 1c7437786a50eeafa884ce92b745f3438b2d2b88
workflow-type: tm+mt
source-wordcount: '1449'
ht-degree: 64%

---

# [!DNL Adobe Experience Manager] デスクトップアプリケーションのインストール {#install-app-v2}

[!DNL Adobe Experience Manager] デスクトップアプリケーションを使用すると、[!DNL Experience Manager] 内のアセットをローカルデスクトップから手軽に入手し、任意のネイティブデスクトップアプリケーションで利用できるようになります。Assetsは、デスクトップアプリでプレビューおよび開くことができます。 ドキュメントで使用するために Finder またはエクスプローラーで表示し、ローカルで編集できます。 変更内容は、に書き戻されます。 [!DNL Experience Manager]。アップロード時に新しいバージョンを作成します。

このような統合により、組織内の様々な役割のユーザーが以下を実行できます。

* アセットを [!DNL Experience Manager Assets] で一元管理する。

* サードパーティアプリケーションや Adobe Creative Cloud アプリケーションなど、任意のネイティブデスクトップアプリケーションでアセットにアクセスする。その間、ユーザーはブランディングなどの様々な標準に容易に準拠できます。

を使用するには [!DNL Experience Manager] デスクトップアプリケーション：

* 次のことを確認します [!DNL Experience Manager] のバージョンはと互換性があります [!DNL Experience Manager] デスクトップアプリケーション。

* アプリケーションをダウンロードしてインストールします。下記の[デスクトップアプリケーションのインストール](#install-v2)を参照してください。

* いくつかのアセットを使用して接続をテストします。[アセットの参照方法と検索方法](using.md#browse-search-preview-assets)を参照してください。

## 必要システム構成、前提条件およびダウンロードリンク {#tech-specs-v2}

詳しくは、[[!DNL Experience Manager] Adobe デスクトップアプリケーションリリースノート](release-notes.md)を参照してください。

## 以前のバージョンからのアップグレード {#upgrade-from-previous-version}

デスクトップアプリケーション v1.x のユーザーである場合は、デスクトップアプリケーションの以前のバージョンと最新のバージョンの違いと類似点を理解します。 参照： [デスクトップアプリケーションの新機能](introduction.md#whats-new-v2) および [アプリの仕組み](release-notes.md#how-app-works).

>[!NOTE]
>
>デスクトップアプリケーションの 2 つのバージョンを 1 台のコンピューター上で共存させることはできません。 あるバージョンをインストールするには、その前に他のバージョンをアンインストールします。

以前のバージョンのアプリケーションからアップグレードするには、次の手順に従います。

1. アップグレードする前に、すべてのアセットを同期し、変更を [!DNL Experience Manager] にアップロードします。これにより、アプリをアンインストールする際に編集内容が失われるのを防ぐことができます。

1. 以前のバージョンのアプリケーションをアンインストールします。アンインストール時に、キャッシュをクリアするオプションを選択します。

1. コンピューターを再起動します。

1. 最新のデスクトップアプリケーションを[ダウンロード](release-notes.md)して[インストール](#install-v2)します。以下の手順に従ってください。

## 次をインストールします： {#install-v2}

デスクトップアプリケーションをインストールするには、次の手順に従います。最新のデスクトップアプリケーションをインストールする前に、既存の Adobe [!DNL Experience Manager] デスクトップアプリケーション v1.x をアンインストールします。詳しくは、上記を参照してください。

1. 最新のインストーラーを[リリースノート](release-notes.md)ページからダウンロードします。

1. [!DNL Experience Manager] デプロイメントの URL と認証情報を手元に用意します。

1. 別のバージョンのアプリケーションからアップグレードする場合は、[デスクトップアプリケーションのアップグレード](#upgrade-from-previous-version)を参照してください。

1. [!DNL Experience Manager] as a [!DNL Cloud Service]、[!DNL Experience Manager] 6.4.4 以降、または [!DNL Experience Manager] 6.5.0 以降を使用する場合は、この手順をスキップします。[!DNL Experience Manager] の設定が、[リリースノート](release-notes.md)に記載されている互換性要件を満たしていることを確認します。必要に応じて、該当する[互換性パッケージ](https://experience.adobe.com/#/downloads/content/software-distribution/jp/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)をダウンロードし、[!DNL Experience Manager] 管理者として [!DNL Experience Manager] パッケージマネージャーを使用してインストールします。パッケージのインストールについては、[パッケージの作業方法](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/contentmanagement/package-manager)を参照してください。

1. インストーラーバイナリを実行し、画面の指示に従ってインストールします。

1. Windows では、`Visual Studio C++ Redistributable 2015` をインストールするように求められる場合があります。画面に表示される指示に従ってインストールします。 インストールに失敗した場合は、手動でインストールします。 インストーラーを[ここ](https://www.microsoft.com/ja-jp/download/details.aspx?id=52685)からダウンロードし、`vc_redist.x64.exe` ファイルと `vc_redist.x86.exe` ファイルを両方ともインストールします。[!DNL Experience Manager] デスクトップアプリケーションインストーラーを再実行します。

1. プロンプトが表示されたら、コンピュータを再起動します。 デスクトップアプリケーションを起動し設定します。

1. アプリケーションを [!DNL Experience Manager] リポジトリーに接続するには、トレイのアプリケーションアイコンをクリックしてアプリケーションを起動します。[!DNL Experience Manager] サーバーのアドレスを `https://[aem_server]:[port]/` の形式で指定します。

   「**[!UICONTROL Connect]**」をクリックし、資格情報を入力します。

   ![入力サーバーアドレスへのデスクトップアプリの接続画面](assets/connect_da2.png)

   *図：入力サーバーアドレスへの接続画面。*

   を選択 **[!UICONTROL Remember Connection]** デスクトップアプリケーションにログオンするたびに接続の詳細の入力をするのを避けるために、

   >[!CAUTION]
   >
   >のアドレスの前後に先頭または末尾のスペースがないことを確認してください。 [!DNL Experience Manager] サーバー。 追加されていない場合、アプリケーションはに接続できません [!DNL Experience Manager] サーバー。

1. [オプション] クリック **[!UICONTROL I want to connect a different way]** をクリックして、 **[!UICONTROL Adobe login]** Adobe Identity Management サービス（IMS）を使用してExperience Manager Assets サーバーにログオンします。 IMS ログオンを使用すると、デスクトップアプリケーションはアクセストークンを自動的に更新し、ユーザーは最大 14 日間ログオンし続けることができます。 クリック **[!UICONTROL Direct login]** 標準ログオンを実行するには [!DNL Experience Manager] ユーザーの資格情報を使用してサーバーします。

   ![アドビにログイン](assets/adobe-login.png)

1. 接続に成功すると、[!DNL Experience Manager] DAM のルートフォルダーにあるフォルダーやアセットのリストが表示されます。デスクトップアプリケーション内からフォルダーを参照できます。

   ![ログイン時に、アプリケーションに DAM コンテンツが表示されます](assets/firstview_da2.png)

   *図：ログイン後に DAM コンテンツが表示される*

1. （[!DNL Experience Manager] 6.5.1 以降） デスクトップアプリケーションをで使用している場合 [!DNL Experience Manager] 6.5.1 以降、S3 または Azure コネクタをバージョン 1.10.4 以降にアップグレードしてください。 詳しくは、[Azure コネクタ](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/data-store-config#azure-data-store)または [S3 コネクタ](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/data-store-config#amazon-s-data-store)を参照してください。

   Adobe Managed Services（AMS）を使用している場合は、アドビカスタマーサポートにお問い合わせください。

## 環境設定の指定 {#set-preferences}

環境設定を変更するには、![その他のオプションアイコン](assets/do-not-localize/more_options_da2.png)と **[!UICONTROL Preference]** ![環境設定アイコン](assets/do-not-localize/preferences_icon_da2.png) を順にクリックします。**[!UICONTROL Preferences]** ウィンドウで、以下の値を調整します。

* [!UICONTROL Launch the application on logon]。

* [!UICONTROL Show a window when the application starts]。

* **[!UICONTROL Cache Directory]**：アプリのローカルキャッシュの場所（ローカルにダウンロードされたアセットが含まれます）。

* **[!UICONTROL Network Drive Letter]**：[!DNL Experience Manager] DAM へのマッピングに使用されるドライブ文字。不明な場合は、このネットワーク ドライブ文字を変更しないでください。 デスクトップアプリケーションでは、Windows の任意のドライブ文字にマッピングできます。2 人のユーザーが異なるドライブ文字のアセットを配置した場合、互いに相手が配置したアセットは表示されません。アセットのパスが変更されます。アセットは、バイナリファイル（INDD など）に配置されたままで、削除されません。使用可能なすべてのドライブ文字がデスクトップアプリケーションに一覧表示され、最後に使用可能な文字（通常は `Z`）がデフォルトで使用されます。

* **[!UICONTROL Maximum Cache Size]**：ローカルダウンロードされたアセットの保存に使用される、ハードディスクの許可されたキャッシュ（GB 単位）。

* **[!UICONTROL Current cache size]**：ローカルにダウンロードしたアセットのストレージサイズ。この情報は、デスクトップアプリケーションを使用してアセットをダウンロードした後にのみ表示されます。

* **[!UICONTROL Automatically download linked assets]**：元のファイルをダウンロードすると、サポートされているネイティブCreative Cloudアプリに配置されたアセットが自動的に取得されます。

* **[!UICONTROL Maximum number of downloads]**：![注意アイコン](assets/do-not-localize/caution-icon.png) 変更は慎重におこなう必要があります。（「表示」、「開く」、「編集」、「ダウンロード」などのオプションを使用して）初めてアセットをダウンロードする場合は、バッチに含まれているアセットがこの数より少ない場合にのみ、アセットがダウンロードされます。デフォルト値は 50 です。不明な場合は、値を変更しないでください。値を大きくすると待ち時間が長くなる可能性がありますが、値を小さくすると、必要なアセットやフォルダーをすべて 1 回でダウンロードできなくなる場合があります。

* **[!UICONTROL Use legacy conventions when creating nodes for assets and folders]**：![注意アイコン](assets/do-not-localize/caution-icon.png) 変更は慎重におこなう必要があります。この設定により、フォルダーをアップロードする際に v1.10 アプリケーションの動作をエミュレートできます。v1.10 では、ユーザーが指定したフォルダー名のスペースと大文字/小文字の区別をそのまま使用した名前のノードがリポジトリーに作成されます。 一方、アプリケーション v2.1 では、フォルダー名の余分なスペースはハイフンに変換されます。例えば、このオプションが選択されておらず、v2.1 のデフォルト動作が維持される場合は、`New Folder` または `new   folder` をアップロードすると、リポジトリーに同じノードが作成されます。このオプションを選択した場合、上記の 2 つのフォルダーに対して異なるノードがリポジトリに作成され、v1.10 アプリケーションの動作と一致します。

  v2.1 のデフォルトの動作は変更されません。フォルダー名に含まれる複数のスペースをリポジトリノード名でダッシュに置き換え、ノード名を小文字に変換します。

* **[!UICONTROL Upload Acceleration]**：![注意アイコン](assets/do-not-localize/caution-icon.png) 変更は慎重におこなう必要があります。アプリケーションでアセットをアップロードする際に同時アップロードを使用して、アップロード速度を向上させることができます。スライダーを右に動かして、アップロードの同時実行性を高めることができます。左端のスライダーは、同時実行なし（シングルスレッドアップロード）を意味し、中央の位置は 10 個の同時スレッドに対応し、右端の上限は 20 個の同時スレッドに対応します。 同時実行性の上限が高いほど、リソースの消費量が増えます。

使用できない環境設定を更新するには、[!DNL Experience Manager] サーバーからログアウトしたあと、更新します。環境設定を更新したら、![環境設定の保存](assets/do-not-localize/save_preferences_da2.png) アイコンをクリックします。

![デスクトップアプリケーションの環境設定](assets/preferences_da2.png)

*図：デスクトップアプリケーションの環境設定*

### プロキシのサポート {#proxy-support}

この [!DNL Experience Manager] デスクトップアプリケーションは、システムの事前定義済みプロキシを使用して、HTTPS でインターネットに接続します。 AEM デスクトップアプリケーションは、追加の認証が必要ないネットワークプロキシのみを使用して接続できます。

Windows のプロキシサーバー設定（インターネットオプション／LAN の設定）を設定または変更した場合、変更内容を反映するには、[!DNL Experience Manager] デスクトップアプリケーションを再起動します。プロキシ設定は、デスクトップアプリケーションの起動時に適用されます。変更内容を反映するには、アプリケーションを閉じて再起動します。

プロキシで認証が必要な場合は、IT チームがプロキシサーバー設定で [!DNL Experience Manager Assets] の URL を許可すれば、アプリケーションのトラフィックが通過できるようになります。

## デスクトップアプリケーションのアンインストール {#uninstall-the-app}

Windows でデスクトップアプリケーションをアンインストールするには、次の手順に従います。

1. [!DNL Experience Manager] に変更内容をすべてアップロードして、編集内容が失われないようにします。詳しくは、「[アセットの編集と  [!DNL Experience Manager]](using.md#edit-assets-upload-updated-assets) への更新済みアセットのアップロード」を参照してください。ログオフし、アプリケーションの「[!UICONTROL Exit]」を実行します。

1. 他の OS アプリケーションを削除する場合と同様に、デスクトップアプリケーションを削除します。Windows のプログラムの追加と削除からアンインストールします。

1. キャッシュとログを削除するには、必要なチェックボックスをオンにします。

   ![ログとキャッシュを削除するアンインストールダイアログ](assets/uninstall_da2.png)

1. 画面に表示される指示に従います。完了したら、コンピューターを再起動します。

Mac でデスクトップアプリケーションをアンインストールするには、次の手順に従います。

1. [!DNL Experience Manager] に変更内容をすべてアップロードして、編集内容が失われないようにします。詳しくは、「[アセットの編集と  [!DNL Experience Manager]](using.md#edit-assets-upload-updated-assets) への更新済みアセットのアップロード」を参照してください。ログオフし、アプリケーションの「[!UICONTROL Exit]」を実行します。

1. `/Applications` から `Adobe Experience Manager Desktop.app` を削除します。

または、Macの内部アプリケーションキャッシュをクリーンアップし、アプリをアンインストールするには、ターミナルで次のコマンドを実行します。

```shell
/Applications/Adobe Experience Manager Desktop/Contents/Resources/uninstall-osx/uninstall.sh
```
