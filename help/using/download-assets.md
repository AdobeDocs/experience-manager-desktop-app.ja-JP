---
title: ' [!DNL Experience Manager]  デスクトップアプリケーションを使用したアセットのダウンロード'
description: ' [!DNL Adobe Experience Manager]  デスクトップアプリケーションを使用してアセットをダウンロードします。'
feature: Desktop App,Asset Management
exl-id: 7004f759-ce8a-497d-9647-3a120fa3ba1d
TQID: https://experienceleague.adobe.com/EXan0driSkmXsYYTxPe73VaDhQP5RQt1c-L2US-cSUY
product_v2:
  - id: d09181b5-a36a-43de-ba01-36641440bc43
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 6427cf5cb782d62b7335cfb7e3fa6b4189ac72d2
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 97%

---

# ローカルでのアセットのダウンロード {#download-assets-locally}

デスクトップアプリケーションは、[!DNL Experience Manager] サーバーからローカルファイルシステムにアセットを頻繁にダウンロードします。 ダウンロードすると、帯域幅とディスク容量を消費します。 状況を把握することで、ダウンロードが完了するまでの待ち時間を最適化できます。 アセットはローカルファイルシステムにダウンロードできます。 デスクトップアプリケーションは [!DNL Experience Manager] サーバーからアセットを取得し、それと同じコピーをローカルファイルシステムに保存します。

オプション用に **[!UICONTROL More actions]** ![その他のオプションアイコン](assets/do-not-localize/more2_da2.png) をクリックし、![ダウンロードアイコン](assets/do-not-localize/download_cloud_da2.png) をクリックしてダウンロードします。

![アセットのダウンロードオプション](assets/download_option_da2.png "アセットのダウンロードオプション")

>[!NOTE]
>
>大きなファイルまたは多数のファイルをダウンロードまたはアップロードするときは、アセットやフォルダーに対するアクションが無効になります。 これらのアクションは、ダウンロードまたはアップロードが完了すると使用可能になります。

「[!UICONTROL Open]」アクションを使用してネイティブデスクトップアプリケーションでアセットを開くと、そのアセットがまだローカルで使用できない場合は、ローカルにダウンロードされます。 詳しくは、[アセットを開く](#openondesktop-v2)を参照してください。

デスクトップアプリケーション内からアセットまたはフォルダーの場所を表示すると、そのアセットまたはフォルダーはまずローカルにダウンロードされてから、ユーザーのコンピューター上のローカルネットワーク共有内で開かれます。 詳しくは、[アセットを開く](#openondesktop-v2)を参照してください。

「[!UICONTROL Edit]」アクションを使用してネイティブデスクトップアプリケーションでアセットを編集すると、そのアセットがまだローカルで使用できない場合は、ローカルにダウンロードされます。 詳しくは、「[アセットの編集と  [!DNL Experience Manager]](#edit-assets-upload-updated-assets) への更新済みアセットのアップロード」を参照してください。

デスクトップアプリケーションがインストール済みで、アクションの権限がある場合は、[!DNL Experience Manager] Web インターフェイスで[!UICONTROL Desktop Actions]を使用すると、該当するアクションが完了します。 デスクトップアプリケーションはまずアセットをダウンロードしてから、アクションを実行します。

## 複数のアセットのダウンロード {#download-multiple-assets}

キューのサイズが大きい場合や、ネットワークに問題が発生した場合は、複数のアセットをダウンロードするとパフォーマンスが低下する可能性があります。 また、フォルダーのダウンロード時には、知らないうちに、ダウンロードするアセットを多数キューに入れてしまう場合もあります。 待ち時間が長くならないようにするために、1 回の操作でダウンロードされるアセットの数が制限されています。 その設定方法については、[環境設定の指定](install-upgrade.md#set-preferences)を参照してください。 この制限を下回っていても、明らかに大きなフォルダーをダウンロードする場合は、その前に確認が求められることがあります。

![比較的多くのアセットをダウンロードする場合の確認](assets/download_confirmation_da2.png "比較的多くのアセットをダウンロードする場合の確認")

フォルダーを選択してダウンロードした場合は、[!DNL Experience Manager] のフォルダーに直接保存されているアセットのみダウンロードされます。 サブフォルダー内のアセットが自動的にダウンロードされることはありません。

## 次の手順 {#next-steps}

* [Adobe Experience Manager デスクトップアプリの使用を開始するビデオを見る](https://experienceleague.adobe.com/ja/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app)

* 右側のサイドバーにある「[!UICONTROL Edit this page]![ページを編集](assets/do-not-localize/edit-page.png)」または「[!UICONTROL Log an issue]![GitHub イシューを作成](assets/do-not-localize/github-issue.png)」を使用してドキュメントに関するフィードバックを提供する

* [カスタマーケア](https://experienceleague.adobe.com/ja?support-solution=General#support)に問い合わせる

>[!MORELIKETHIS]
>
>* [アセットのアップロード](/help/using/upload-assets.md)
>* [ユーザーインターフェイスについて](/help/using/user-interface.md)
>* [検索](/help/using/search.md)
