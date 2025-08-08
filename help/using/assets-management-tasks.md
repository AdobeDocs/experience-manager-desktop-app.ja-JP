---
title: ' [!DNL Experience Manager]  デスクトップアプリケーションの使用'
description: ' [!DNL Adobe Experience Manager] デスクトップアプリを使用すると、Windows または Mac のデスクトップから直接 [!DNL Adobe Experience Manager]  DAM アセットを操作し、他のアプリケーションで使用することができます。'
feature: Desktop App,Asset Management
source-git-commit: c5aeee9ab636ba7bedff4225172140d59cfe627d
workflow-type: ht
source-wordcount: '1416'
ht-degree: 100%

---


# [!DNL AEM Desktop App] でのAssets管理タスク {#assets-management-tasks}

アセット管理では、ワークフローを合理化するためのデジタルアセットの整理、維持管理および最適化を行います。これには、ファイルの複製と名前変更、クイックアクセスのためのフォルダーのピン留めまたはピン留め解除、様々なレイアウトでのアセットの表示などのタスクが含まれます。これにより、効率が向上し、アセットのトラッキングが簡素化され、複数のプラットフォーム間でデジタルアセットを簡単に取得および整理できます。

## アセットの表示 {#view-assets}

AEM デスクトップアプリでは、次の 4 つの異なるビューでアセットを表示できます。

* **[!UICONTROL Show Assets]：**&#x200B;すべてのアセットを表示できます。
* **[!UICONTROL Show Collections]：**&#x200B;ネイティブの AEM アプリケーションで作成されたすべてのコレクションを表示できます。その他の[コレクション](#collections-desktop-app)を参照してください。
* **[!UICONTROL Edited Locally]：**&#x200B;ローカルで変更されたすべてのアセットを表示できます。このビューでは、複数のアセットを追加およびアップロードできます。
* **[!UICONTROL Asset transfers]：**&#x200B;ネイティブアプリからローカルに、またはその逆に転送されたすべてのアセットを表示できます。
* **[!UICONTROL Pinned items]：**&#x200B;ピン留めされたすべての項目を表示できます。

AEM デスクトップアプリでアセットの様々なビューの中から選択するには、次の手順を実行します。

1. AEM デスクトップアプリを開きます。

1. 右上のビュードロップダウンに移動します。使用可能なビューから 1 つ選択します。

   ![フォルダーのピン留めまたはピン留めを解除](assets/view-pinned-assets.png)

## 新しく追加されたフォルダーとファイルを表示 {#view-newly-added-files-folders}

新しく作成したアセットをローカルマシンから、中央リポジトリが格納されている AEM にアップロードできます。これらの新しく作成されたアセットをローカルに表示するには、**[!UICONTROL View]** ドロップダウンメニューに移動して「**[!UICONTROL Show Assets]**」を選択し、タイムラインとタイトルを含むすべてのアップデートを表示するか、「**[!UICONTROL Edited Locally]**」を選択します。どちらのオプションでも、ローカルに編集されたアセットが明示的に表示されます。

## 重複ファイル {#duplicate-files}

元のファイルを保持し、類似したファイルに変更を加える場合は、異なる場所（ローカルとクラウド）でファイルを同時に複製できます。これは、アセットをまたいだ「ファイルを複製」操作で実現できます。

AEM デスクトップアプリでファイルを複製するには、次の手順に従います。

1. フォルダーを参照し、複製するアセットを選択します。

   ![その他のオプション](assets/more-options1.png)

1. **[!UICONTROL More actions]** ![他のアクションアイコン](assets/do-not-localize/more2_da2.png) をクリックし、![複製アイコン](assets/do-not-localize/duplicate.svg) **[!UICONTROL Duplicate File]** アクションを選択します。

1. 重複ファイルは、同じファイル名とコンテンツで作成されます。

## アセットやフォルダーのタイトルの名前を変更する {#rename-asset-title}

アセットやフォルダーのタイトルの名前を変更するには、次の手順を実行します。

1. 名前を変更するアセットを参照します。フォルダーに名前を付ける場合、`\ / : * ?  | < > [ ] %` ; などの特殊文字は使用できません。 含める場合は、自動的にハイフン `-` に置き換えられます。

1. **[!UICONTROL More actions]** ![他のアクションアイコン](assets/do-not-localize/more2_da2.png) をクリックし、「**[!UICONTROL Rename]**」を選択してアセットの目的のタイトルを追加します。


## フォルダーのピン留めまたはピン留めを解除 {#pin-unpin-folder}

ピン留めされたフォルダーは、アプリ内でネイティブに行われた変更を反映するように自動的に同期されます。 クイックアクセスを行うには、次の手順を実行して、フォルダーをピン留めまたはピン留めを解除します。

1. ピン留めまたはピン留めを解除するアセットを参照します。

1. **[!UICONTROL More actions]** ![他のアクションアイコン](assets/do-not-localize/more2_da2.png) をクリックし、「[!UICONTROL pin]」を選択してアセットまたはフォルダーをピン留めします。または、「[!UICONTROL unpin]」をクリックしてピン留めを解除します。

   ![フォルダーのピン留めまたはピン留めを解除](assets/pin-unpin.png)

## 自動更新 {#auto-refresh}

自動更新機能により、コンテンツがリアルタイムで自動的に更新されるので、ページを手動で再読み込みすることなく、常に最新情報を確認できます。以下の手順を実行してアセットを自動的に更新し、更新されたアセットのリストを取得します。

1. AEM デスクトップアプリを開きます。

1. メニューバーの ![更新アイコン](assets/do-not-localize/refresh.png) をクリックして、更新内容を取得する。

## コレクション {#collections-desktop-app}

AEM デスクトップアプリを使用すると、[!DNL Adobe Experience Manager Assets]アプリケーションで作成されたコレクションを[表示](#view-collections-desktop-app)、[ダウンロード](#download-collections-desktop-app)、参照できます。

### コレクションの表示 {#view-collections-desktop-app}

デスクトップアプリでコレクションを表示するには、次の手順を実行します。

1. AEM デスクトップアプリを開き、[アセットを表示](#view-assets)に移動します。

1. **[!UICONTROL Show Collections]** を選択します。ネイティブアプリケーションで使用できるコレクションが表示されます。

   ![コレクションデスクトップアプリ](assets/collections-desktop-app.png)

### コレクションをダウンロード {#download-collections-desktop-app}

デスクトップアプリでコレクションをダウンロードするには、次の手順を実行します。

1. [コレクションの表示](#view-collections-desktop-app)に示すように、手順 1 および 2 に従います。

1. ダウンロードするコレクションで、その他のアクション ![その他のアクションアイコン](assets/do-not-localize/more2_da2.png) に移動する。

1. 「**[!UICONTROL Download]**」をクリックして、特定のコレクションをダウンロードする。

## メタデータスキーマを使用したフォルダーの作成 {#create-folder-with-metadata-schema}

AEM デスクトップアプリを使用して、新しいフォルダーを作成する際にメタデータを割り当てることができます。これを行うには、次の手順を実行します。

1. ディレクトリを作成アイコン ![フォルダーアイコンを追加](assets/do-not-localize/add-folder.svg) に移動します。**[!UICONTROL Create Directory]** 画面が表示されます。

1. 次の詳細を追加します。
   * フォルダーの **[!UICONTROL Name]**。
   * フォルダーのメタデータ階層を選択する場合は **[!UICONTROL none]**、メタデータを関連付けない場合は **[!UICONTROL Folder Metadata Schema]** を選択します。

1. 「**[!UICONTROL OK]**」をクリックして、次に進みます。

## 転送したアセットのリスト {#list-of-transferred-assets}

特定のセッションで転送されたアセットのリストを表示するには、[ [!DNL Experience Manager]](#upload-and-add-new-assets-to-aem) へのアセットのアップロードを参照してください。

## 高度なワークフロー：同じファイルに対する共同作業と編集上の競合の回避 {#adv-workflow-collaborate-avoid-conflicts}

共同作業環境では、複数のユーザーが同じアセットセットを操作して、バージョンの競合を引き起こすおそれがあります。競合を防ぐには、以下のベストプラクティスに従います。

* 「[!UICONTROL Open]」をクリックしてアセットを編集しない。ローカルにダウンロードしたアセットをファイルシステムフォルダーから開いて編集しないでください。他のユーザーは、そのアセットが編集中であることがわかりません。
* アセットを編集する場合は、必ず「[!UICONTROL Edit]」をクリックする。これにより、ネイティブアプリケーションでアセットが開かれ、アセットにロックアイコンが表示されます。その結果、アセットが編集中であることが他のユーザーにわかります。
* 「[!UICONTROL Toggle Check-in]」をクリックせずに誤って編集を開始した場合は、「[!UICONTROL Edit]」をクリックする。この機能により、アセットにロックアイコンが追加されます。後でアセットを編集する予定であっても、他のユーザーによる編集を避けたい場合は、「[!UICONTROL Toggle Check-in]」をクリックしてアセットをロックします。
* アセットを編集する前に、そのアセットを他のユーザーが編集していないことを確認する。アセットにロックアイコンが表示されていないかを確認します。
* 編集が完了したら、変更内容をすべてアップロードしてから、アセットをチェックインする。

![編集上の競合を示すステータス](assets/edits_conflicts_status_da2.png "編集上の競合を示すステータス")

ローカルにダウンロードしたアセットが [!DNL Experience Manager] サーバー上で更新されると、アプリケーションに「**[!UICONTROL Modified remotely]**」ステータスが表示されます。「[!UICONTROL Remove]」か「[!UICONTROL Update]」をクリックして、ローカルコピーを削除するか更新することができます。ダイアログボックスのリンクを使用すると、アセットのどちらのバージョンも表示できます。

![アセットがリモートで変更された場合に競合を解決するオプション](assets/modified_remotely_dialog_da2.png "アセットがリモートで変更された場合に競合を解決するオプション")

ローカルで編集中のアセットが、知らないうちにサーバー上でも更新されると、デスクトップアプリケーションに「**[!UICONTROL Editing Conflict]**」ステータスが表示されます。どちらか一方の変更セットを保持できます。つまり、自身の更新内容を保持（「**[!UICONTROL Keep Mine]**」をクリック）して他のユーザーの編集内容を削除するか、他のユーザーの更新内容を尊重（「**[!UICONTROL Overwrite Mine]**」をクリック）して自身が編集した内容を削除します。

![編集上の競合を解決するためのオプション](assets/editing_conflict_dialog_da2.png "編集上の競合を解決するためのオプション")

## 高度なワークフロー：InDesign ファイルへのアセットの配置とリンク {#adv-workflow-place-assets-indesign}

[!DNL Experience Manager] デスクトップアプリケーションを使用して、リンクされたアセットを含んだファイルを開くと、そのアセットは事前にダウンロードされており、ネイティブアプリケーションに配置されて表示されます。このワークフローが機能するには、ローカルアセットへのリンクの配置がネイティブアプリケーションでサポートされ、[!DNL Experience Manager] ではサーバー側参照へのリンクをバイナリファイル内で解決できる必要があります。

[!DNL Experience Manager] デスクトップアプリケーションでは、Adobe InDesign、Adobe Illustrator、Adobe Photoshop など、厳選されたいくつかの Adobe Creative Cloud デスクトップアプリケーションおよびファイル形式で、このワークフローをサポートしています。このワークフローを使用すると、サポートされている Creative Cloud ファイルを効率的に操作できます。ユーザー A が InDesign ファイルにアセットを追加し、それを [!DNL Experience Manager] にチェックインすると、ユーザー B はファイルに含まれていないアセットを表示できます。このアセットは、ユーザー B のマシンにローカルでダウンロードされます。

>[!NOTE]
>
>デスクトップアプリケーションでは、Windows 上の任意のドライブにマッピングできます。ただし、操作をスムーズに行うには、デフォルトのドライブ文字を変更しないでください。同じ組織のユーザーが異なるドライブ文字を使用している場合、他のユーザーが配置したアセットは表示されません。パスが変更されると、配置されたアセットは取得されません。配置されたアセットは、バイナリファイル（INDD など）に配置されたままで、削除されません。

このワークフローの制限事項については、[必要システム構成とサポート対象バージョン](release-notes.md)を参照してください。

画像アセットと InDesign でこのワークフローを試すには、以下の手順に従います。

1. アセットを配置した INDD ファイルを [!DNL Experience Manager] に用意します。このような INDD ファイルの作成方法については、[グラフィックの配置](https://helpx.adobe.com/jp/indesign/using/placing-graphics.html)を参照してください。
1. デスクトップアプリケーション内から、[!DNL Experience Manager] にあるアセットを配置した INDD ファイルを **[!UICONTROL Edit]** します。
1. デスクトップアプリケーションが、InDesign ファイルおよびリンクされたアセットをダウンロードします。ドキュメントが InDesign で開かれると、リンクが解決され、アセットがダウンロードされて InDesign ドキュメントに表示されます。
1. InDesign ファイルに新しいグラフィックを配置するには、アセットに対して **[!UICONTROL Reveal File]** アクションを使用します。このアクションにより、アセットがローカルにダウンロードされ、ローカルネットワーク共有の場所が Windows エクスプローラーまたは Mac Finder で開かれます。
1. 表示されたアセットを InDesign ドキュメントに配置します。これで、ドキュメントにリンクが作成されます。
1. InDesign ドキュメントの編集が完了したら、ドキュメントを保存し、デスクトップアプリケーションを使用して [!DNL Experience Manager] にアップロードします。

## 次の手順 {#next-steps}

* [ビデオを視聴してAdobe Experience Manager デスクトップアプリの概要を学ぶ](https://experienceleague.adobe.com/ja/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app)

* 右側のサイドバーにある「[!UICONTROL Edit this page] ![ページを編集](assets/do-not-localize/edit-page.png)」または「[!UICONTROL Log an issue]![GitHub イシューを作成](assets/do-not-localize/github-issue.png)」を使用してドキュメントに関するフィードバックを提供する

* [カスタマーケア](https://experienceleague.adobe.com/ja?support-solution=General#support)に問い合わせる

<!--* Provide product feedback using the [!UICONTROL Feedback] option available on the AEM Desktop App user interface>-->

>[!MORELIKETHIS]
>
>* [ユーザーインターフェイスについて](/help/using/user-interface.md)
>* [はじめる前に](/help/using/get-started.md)。
