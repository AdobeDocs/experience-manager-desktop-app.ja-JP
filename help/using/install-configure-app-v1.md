---
title: デスクトップアプリケーション v1.10 のインストールと設定
description: ' [!DNL Experience Manager] デスクトップアプリバージョン 1.10 [!DNL Assets]  をインストールして、 サーバーと連携しアセットをデスクトップのドライブとしてマウントするように設定します。'
exl-id: 7f3bdfb1-d345-4e48-b020-6e06531f46f2
source-git-commit: 1c7437786a50eeafa884ce92b745f3438b2d2b88
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 74%

---

# [!DNL Experience Manager] デスクトップアプリケーション v1.10 のインストールと設定 {#install-and-configure-aem-desktop-app}

[!DNL Experience Manager] デスクトップアプリケーションを使用すると、[!DNL Experience Manager] 内のアセットにローカルデスクトップから手軽にアクセスし、任意のデスクトップアプリケーションで利用できるようになります。AssetsはMac Finder または Windows エクスプローラーで表示し、デスクトップアプリケーションで編集し、変更内容をに保存します [!DNL Experience Manager]。アップロード時に新しいバージョンを作成します。

この統合により、様々な役割でAssetsの組織内でアセットを一元的に管理し、Creative Cloudなどのアプリケーションからアクセスし、ブランディングなどの様々な標準に簡単に準拠できるようになります。

を使用するには [!DNL Experience Manager] デスクトップアプリケーション、

* 次のことを確認します [!DNL Experience Manager] サーバーのバージョンは、と互換性があります [!DNL Experience Manager] デスクトップアプリケーション。 [互換表](release-notes-of-v1.md#compatibilitymatrix)を参照してください。

* アプリケーションをダウンロードしてインストールします。

* いくつかのアセットを使用して接続をテストします。詳しくは、[デスクトップでのアセットへのアクセスとオープン](use-app-v1.md#openondesktop)を参照してください。

## 必要システム構成、前提条件およびダウンロードリンク {#system-requirements-prerequisites-and-download-links}

詳しくは、[[!DNL Experience Manager] Adobe デスクトップアプリケーションリリースノート](release-notes-of-v1.md)を参照してください。

## デスクトップアプリケーションのインストールと [!DNL Experience Manager] サーバーへの接続 {#install-and-connect-aem-desktop-app-to-aem-server}

詳しくは、[ [!DNL Experience Manager] デスクトップアプリケーションのインストールと [!DNL Experience Manager] サーバーへの接続](use-app-v1.md#installandconnect)を参照してください。

>[!NOTE]
>
>インストールして一度にアクティブ化できる [!DNL Experience Manager] デスクトップアプリケーションのインスタンスは 1 つだけです。

## ファイルの処理 {#file-handling}

デスクトップアプリケーションによってマウントされたネットワーク共有の場所からファイルを変更した場合、ファイルは 2 つの段階を経てその場所に保存されます。第 1 段階では、ファイルはローカルに保存されます。ユーザーは、転送が完了するのを待たずに、ファイルを保存し、ファイルの作業を続行できます。

第 2 段階では、デスクトップアプリケーションは更新されたファイルをにアップロードします。 [!DNL Experience Manager] 事前に定義された遅延（30 秒など）の後のサーバー。 この処理はバックグラウンドで実行されます。「アセットステータスを表示」オプションを使用すると、アップロード処理のステータスを表示できます。

1.  Assets にアセットをアップロードします。

1. ツールバーの [!DNL Experience Manager] デスクトップアプリケーションアイコンをクリックします。

1. メニューから、「View Asset Status」オプションを選択します。

1. ダイアログで、アップロード処理のステータスを確認します。

>[!NOTE]
>
>[!DNL Experience Manager] デスクトップアプリケーションは、最大 40 GB のアセットを処理できます。

## への接続 [!DNL Experience Manager] Dispatcherの背後にあるインスタンス {#connect-to-an-aem-instance-behind-a-dispatcher}

Assets API のコピーおよび移動メソッドでは、次の追加ヘッダーを [!DNL Experience Manager] に引き渡す必要があります。

* X の宛先
* X の深度
* X の上書き

[!DNL Experience Manager] デスクトップアプリケーションは、デフォルトポートを含む URL を使用して [!DNL Experience Manager] に接続します。したがって、 `virtualhosts` Dispatcher設定のの設定には、デフォルトのポート番号を含める必要があります。 `virtualhosts` の設定について詳しくは、[仮想ホストの識別](https://experienceleague.adobe.com/en/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration#identifying-virtual-hosts-virtualhosts)を参照してください。

これらの追加ヘッダーを通過するようにDispatcherを設定する方法について詳しくは、以下を参照してください [HTTP ヘッダーの指定](https://experienceleague.adobe.com/en/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration#specifying-the-http-headers-to-pass-through-clientheaders).

### プロキシのサポート {#proxy-support}

この [!DNL Experience Manager] デスクトップアプリケーションは、システムの事前定義済みプロキシを使用して、HTTPS でインターネットに接続します。 AEM デスクトップアプリケーションは、追加の認証が必要ないネットワークプロキシのみを使用して接続できます。

Windows のプロキシサーバー設定（インターネットオプション／LAN の設定）を設定または変更した場合、変更内容を反映するには、[!DNL Experience Manager] デスクトップアプリケーションを再起動します。

>[!NOTE]
>
>プロキシ設定は、デスクトップアプリケーションの開始時にのみ適用されます。変更内容を反映するには、アプリケーションを閉じて再起動します。

プロキシで認証が必要な場合は、IT チームがプロキシサーバー設定で Experience Manager Assets の URL を許可すれば、アプリケーションのトラフィックが通過できるようになります。

## Asset Info ダイアログをカスタマイズ {#customize-the-asset-info-dialog}

Asset Info ダイアログは、次のコンポーネントの一方または両方をオーバーレイすることでカスタマイズできます。

* の Granite ユーザーインターフェイスページ `/libs/dam/gui/content/assets/moreinfo`.

* HTL の `/css/javascript` コンポーネント（`/libs/dam/gui/components/admin/moreinfo`）。

オーバーレイするコンポーネントは、カスタマイズの性質に応じて異なります。 Asset Info ダイアログの一部として表示されるコンポーネントを変更するには、Granite ユーザーインターフェイスページをオーバーレイします。ダイアログの HTML、CSS、JavaScript コンテンツを変更するには、HTL コンポーネントをオーバーレイします。

## キャッシュの管理    {#manage-cache}

Windows では、キャッシュは `%LOCALAPPDATA%\Adobe\AssetsCompanion\Cache\` にあります。ここには、デスクトップアプリケーションで設定されている、エンコード済みバージョンの [!DNL Experience Manager] ホストがあります。例えば、`http://localhost:4502` は `http%3A%2F%2Flocalhost%3A4502%2F` と表示されます。

macOS X では、同様のディレクトリがにあります。 `~/Library/Group Containers/group.com.adobe.aem.desktop/cache`.

### キャッシュを管理するアプリケーション内のオプション {#in-app-option-to-manage-cache}

ローカルキャッシュに使用するディスク容量を管理できます。Assets サーバーのアーティファクトはローカルにキャッシュされ、スムーズに利用することができます。要件に応じてデフォルト設定を変更することができます。キャッシュをクリアして、すべてのアセットを取得し直すこともできます。必要なオプションを設定するには、アプリケーションのアイコンをクリックし、**[!UICONTROL Advanced]**／**[!UICONTROL Manage Cache]** を選択します。

>[!NOTE]
>
>キャッシュをクリアした場合でも、未保存の変更内容は維持されます。にチェックインされていないすべてのアセット [!DNL Experience Manager] サーバーは保持され、削除されません。

### Windows でのキャッシュの場所の変更 {#change-location-of-cache-on-windows}

[!DNL Experience Manager] デスクトップアプリケーションのキャッシュのデフォルトの場所は次のとおりです。

* Windows の場合、`%LocalAppData%\Adobe\AssetsCompanion\Cache\EncodedAEMEndpoint`。

* Mac の場合、`~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/EncodedAEMEndpoint`。

この `EncodedAEMEndpoint` アプリの設定済み [!DNL Experience Manager] エンドポイント URL。 この値は、[!DNL Experience Manager] サーバーのターゲット URL のエンコードされたバージョンです。例えば、アプリケーションのターゲットが `http://localhost:4502` の場合、ディレクトリ名は `http%3A%2F%2Flocalhost%3A4502` となります。この例では、キャッシュディレクトリへの Windows のパスは「`%LocalAppData%\Adobe\AssetsCompanion\Cache\http%3A%2F%2Flocalhost%3A4502`」です。

アプリケーションで異なるフォルダーや異なるドライブをキャッシュの場所として指定するには、アプリケーションの設定ファイルを編集します。

1. アプリのインストールディレクトリに移動します。 Windows の場合、デフォルトの場所は `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop` です。

1. を編集する `Adobe Experience Manager Desktop.exe.config` テキストエディターを含むファイル。

   このファイルに変更を保存するには、管理者権限が必要です。

1. 文字列「ProxyCacheRoot」を検索します。 この値は、キャッシュの場所「`%LocalAppData%\Adobe\AssetsCompanion\Cache`」に設定されています。この値を任意の有効なパスに変更します。

   >[!NOTE]
   >
   >自動的に *&lt;エンコードされた AEM エンドポイント>* サブディレクトリが作成されます。この動作は設定で変更することはできません。

>[!MORELIKETHIS]
>
* 監視： [の概要 [!DNL Experience Manager] デスクトップアプリケーション](https://experienceleague.adobe.com/en/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app) （5 分、43 秒）。
* [ [!DNL Experience Manager]  デスクトップアプリケーションの使用](use-app-v1.md)
* [ [!DNL Experience Manager]  デスクトップアプリケーションのトラブルシューティング](troubleshoot-app-v1.md)
