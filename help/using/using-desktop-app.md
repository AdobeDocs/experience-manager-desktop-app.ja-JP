---
title: デスクトップアプリケ  [!DNL Experience Manager]  ションの使用
description: デスクトップアプリケ  [!DNL Adobe Experience Manager]  ションを使用します。
feature: Desktop App,Asset Management
source-git-commit: 2947fbd3bfeb15b37a8f1b0118e969b5d70499d0
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 89%

---


# デスクトップでアセットを開く {#openondesktop-v2}

リモートアセットを開いて、ネイティブアプリケーションで表示することができます。アセットがローカルフォルダーにダウンロードされます。その後、ファイル形式に関連付けられたネイティブアプリケーションで起動されます。ネイティブアプリケーションを変更して、Mac または Windows で特定のファイルタイプ（拡張子）のアセットを開くことができます。

アセットメニューから「**[!UICONTROL Open]**」を選択します。アセットがローカルにダウンロードされ、ネイティブアプリケーションで開かれます。大きなアセットの場合は、ステータスバーでダウンロードの進行状況と転送速度を確認します。

<!-- ![Download progress bar for large-sized assets](assets/download_status_bar_da2.png "Download progress bar for large-sized assets")
-->

>[!NOTE]
>
>期待した変更がデスクトップアプリケーションに反映されない場合は、更新アイコン ![更新アイコン](assets/do-not-localize/refresh.png) をクリックするか、デスクトップアプリケーションインターフェイスで右クリックし、「**[!UICONTROL Refresh]**」を選択します。大量のダウンロードまたはアップロードが進行中の間、これらのアクションは使用できません。

アセットのローカルダウンロードフォルダーを開くには、![その他のアクションアイコン](assets/do-not-localize/more2_da2.png)、![表示アイコン](assets/do-not-localize/reveal_action2_da2.png) 「**[!UICONTROL Reveal File]**」アクションの順にクリックします。

## ネイティブドキュメントへのアセットの配置 {#place-assets-in-native-documents}

ネイティブドキュメントにアセットを配置する場合は、Windows エクスプローラーまたは Mac Finder でファイルにアクセスします。ローカルにダウンロードしたファイルのファイルシステム上の場所に移動するには、![表示アイコン](assets/do-not-localize/reveal_action2_da2.png) 「**[!UICONTROL Reveal File]**」オプションを使用します。

![アセットの「ファイルを表示」アクション](assets/revealfile_action_da2.png "アセットの「ファイルを表示」アクション")

事前にローカルコンピューター上でファイルまたはフォルダーを選択して、「**[!UICONTROL Reveal File]**」または「**[!UICONTROL Reveal Folder]**」（フォルダーの場合）をクリックすると、Windows エクスプローラーまたは Mac Finder が開き、選択したファイルまたはフォルダーが表示されます。例えば、このオプションは、ローカルファイルの配置やリンクをサポートしているネイティブアプリケーションに [!DNL Experience Manager] ファイルを配置する場合などに役に立ちます。Adobe InDesign にファイルを配置する方法については、[グラフィックの配置](https://helpx.adobe.com/jp/indesign/using/placing-graphics.html)を参照してください。

**[!UICONTROL Reveal File]**&#x200B;アクションでは、ローカルネットワーク共有が開きます。ローカルで使用可能なアセットのみが表示されます。つまり、デスクトップアプリケーションを使用して公開、ダウンロード、開いた／編集したアセットが表示されます。ローカルネットワーク共有からは、変更内容が [!DNL Experience Manager] にアップロードされません。変更内容をアップロードするには、デスクトップアプリケーションで明示的に&#x200B;**[!UICONTROL Upload Changes]**&#x200B;または&#x200B;**[!UICONTROL Upload]**&#x200B;アクションを使用します。

>[!NOTE]
>
>[!DNL Experience Manager] デスクトップアプリケーション v1.x との下位互換性を保つため、表示されるファイルはローカルネットワーク共有から提供され、ローカルで使用可能なファイルのみ公開されます。表示されるファイルのデスクトップパスは、デスクトップアプリケーション v1.x で作成されたパスと同じです。

>[!CAUTION]
>
>「**[!UICONTROL Reveal File]**」オプションを使用してネイティブアプリケーションでアセットを編集しないでください。代わりに、**[!UICONTROL Edit]**&#x200B;アクションを使用します。詳しくは、[高度なワークフロー：同じファイルに対する共同作業と編集上の競合の回避](#adv-workflow-collaborate-avoid-conflicts)を参照してください。

## 次の手順 {#next-steps}

* [ ビデオを視聴してAdobe Experience Manager デスクトップアプリの概要を学ぶ ](https://experienceleague.adobe.com/ja/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app)

* 右側のサイドバーにある [!UICONTROL Edit this page] ![ ページを編集 ](assets/do-not-localize/edit-page.png) または [!UICONTROL Log an issue]GitHub イシュー ![ 作成 ](assets/do-not-localize/github-issue.png) を使用してドキュメントに関するフィードバックを提供する

* [カスタマーケア](https://experienceleague.adobe.com/ja?support-solution=General#support)に問い合わせる

>[!MORELIKETHIS]
>
>* [ ユーザーインターフェイスについて ](/help/using/user-interface.md)
>* [ デスクトップアプリケーションでのAssetsの管理 ](/help/using/assets-management-tasks.md)
>* [検索](/help/using/search.md)
