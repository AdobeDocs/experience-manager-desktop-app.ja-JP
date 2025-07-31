---
title: 基本を学ぶ  [!DNL Experience Manager]  デスクトップアプリ
description: デスクトップアプリが  [!DNL Experience Manager]  合理化されたワークフローと生産性機能を使用してコンテンツの作成と公開を強化する方法について説明します。
feature: Desktop App,Asset Management
source-git-commit: 2947fbd3bfeb15b37a8f1b0118e969b5d70499d0
workflow-type: tm+mt
source-wordcount: '1213'
ht-degree: 92%

---


# [!DNL Adobe Experience Manager] デスクトップアプリケーションの基本を学ぶ {#getting-started-desktop-app}

[!DNL Adobe Experience Manager] デスクトップアプリを使用して、ローカルデスクトップ上の [!DNL Adobe Experience Manager] DAM リポジトリに保存されたデジタルアセットにアクセスします。その後、これらのアセットを任意のデスクトップアプリケーションで使用できます。デスクトップアプリケーションでアセットをローカルに開いて編集できます。変更を加えたら、バージョン管理を使用して [!DNL Experience Manager] にアップロードし直し、他のユーザーと更新を共有します。また、新しいファイルおよびフォルダー階層を [!DNL Experience Manager] にアップロードしたり、フォルダーを作成したり、[!DNL Experience Manager] DAM からアセットやフォルダーを削除したりすることもできます。

この統合により、組織内の様々な役割のユーザーがアセットを [!DNL Experience Manager Assets] で一元管理し、Windows または macOS のローカルデスクトップでネイティブアプリケーションからアセットにアクセスできます。

ログアウト後または初めてアプリケーションを開くときに、[!DNL Experience Manager] サーバーの URL を `https://[aem-server-url]:[port]/` の形式で指定します。次に、「[!UICONTROL Connect]」オプションを選択します。アプリケーションをサーバーに接続するための認証情報を入力します。

[!DNL Adobe Experience Manager] デスクトップアプリを使用して行う主なタスクは次のとおりです。

![ デスクトップアプリケーションを使用して実行できるワークフロー [!DNL Experience Manager] タスク ](assets/aem_desktop_app_usecases_v2.png)

## デスクトップアプリケーションの動作の仕組み {#how-app-works2}

アプリケーションの使用を開始する前に、[アプリケーションの仕組み](release-notes.md#how-app-works)を理解しておきましょう。また、次の用語についても把握しておいてください。

* **[!UICONTROL Desktop Actions]**：ブラウザーで Assets web インターフェイスから、アセットの場所を参照したり、アセットをチェックアウトしてネイティブデスクトップアプリケーションで編集用に開いたりできます。これらのアクションは Web インターフェイスから使用でき、デスクトップアプリケーション機能を使用します。

* ファイルのステータスが「**[!UICONTROL Cloud Only]**」：アセットはローカルマシンにはダウンロードされず、[!DNL Experience Manager] サーバー上でのみ使用可能です。

* ファイルのステータスが「**[!UICONTROL Available locally]**」：アセットはローカルマシンにダウンロードされ、そのまま使用できます。ただし、アセットは変更されません。

* ファイルのステータスが「**[!UICONTROL Edited locally]**」：アセットはローカルに編集され、変更内容は [!DNL Experience Manager] サーバーにアップロードされた後も保持されます。アップロード後、ステータスは「[!UICONTROL Available locally]」に変わります。詳しくは、[アセットの編集](upload-assets.md#edit-assets-upload-updated-assets)を参照してください。

* ファイルのステータスが **[!UICONTROL Editing conflict]** ：複数のユーザーがアセットを同時に編集した場合は、編集上の競合が発生したことをアプリケーションが知らせます。また、変更内容を保持するか破棄するかの選択肢も提示されます。詳しくは、[編集上の競合の回避方法](assets-management-tasks.md#adv-workflow-collaborate-avoid-conflicts)を参照してください。

* ファイルのステータスが「**[!UICONTROL Modified remotely]**」：ダウンロードしたアセットが [!DNL Experience Manager] サーバー上で変更されたことをデスクトップアプリケーションが知らせます。また、最新バージョンをダウンロードするか、ローカルコピーを更新するかの選択肢も提示されます。詳しくは、[編集上の競合の回避方法](assets-management-tasks.md#adv-workflow-collaborate-avoid-conflicts)を参照してください。

* **[!UICONTROL Check-out]**：ファイルを編集しようとしている場合やファイルを編集する予定である場合は、ステータスをチェックアウトに切り替えます。アプリケーションと [!DNL Experience Manager] web インターフェイスで、アセットにロックアイコンが表示されます。ロックアイコンは、編集上の競合が発生するため、同じアセットを同時に編集しないように他のユーザーに指示する働きをします。

* **[!UICONTROL Check-in]**：編集上の競合が発生することなく他のユーザーが安全にアセットを編集できることを知らせます。変更内容をアップロードすると、ロックアイコンは自動的に削除されます。チェックインステータスを切り替えるとロックアイコンも削除されますが、変更内容をアップロードせずに手動でチェックインしないでください。変更内容を破棄した場合は、手動でチェックインに切り替えます。

* 「**[!UICONTROL Open]**」アクション：アセットを開いて、ネイティブアプリケーションでプレビューするだけです。アドビでは、この操作を使用してアセットを編集しないことをお勧めします。アセットがチェックアウトされないからです。その間、他のユーザーが編集を行うと、編集の競合が発生する可能性があります。

* **[!UICONTROL Edit]**&#x200B;アクション：アセットを編集できます。[!UICONTROL Edit] をクリックすると、アセットがチェックアウトされ、アセットにロックアイコンが表示されます。このアクションをクリックした後、アセットを編集しない場合は、「[!UICONTROL Toggle check-in]」をクリックします。[!DNL Experience Manager] DAM フォルダー階層内のアセットを削除、名前変更または移動するには、編集アクションではなく、[!DNL Experience Manager] web インターフェイスのアクションを使用します。

* 「**[!UICONTROL Download]**」アクション：アセットをローカルマシンにダウンロードします。アセットをすぐにダウンロードし、後で編集できます。オフラインで作業し、後で変更内容をアップロードすることができます。アセットは、ファイルシステム上のキャッシュフォルダーにダウンロードされます。

* 「**[!UICONTROL Reveal File]**」または「**[!UICONTROL Reveal Folder]**」アクション：アセットがローカルキャッシュフォルダーにダウンロードされると、デスクトップアプリケーションはローカルネットワークドライブを模倣します。各アセットのローカルパスを提供します。このパスを確認するには、デスクトップアプリケーションで適切な表示オプションを使用します。Creative Cloud アプリケーションにアセットを配置するには、このアクションが必要です。詳しくは、[アセットの配置](search.md#place-assets-in-native-documents)を参照してください。

* 「**[!UICONTROL Open In Web]**」アクション：[!DNL Experience Manager] Web インターフェイスでアセットを確認するには、アセットを web で開きます。[!DNL Experience Manager] インターフェイスからは、メタデータの更新やアセットの検出など、さらに多くのワークフローを開始できます。

* **[!UICONTROL Delete]** アクション：[!DNL Experience Manager] DAM リポジトリーからアセットを削除します。このアクションで、Adobe Experience Manager サーバーにあるアセットの元のコピーが削除されます。ローカルアセットに対する変更だけを破棄する場合は、[変更の破棄](upload-assets.md#edit-assets-upload-updated-assets)を参照してください。

* 「**[!UICONTROL Upload Changes]**」アクション：[!DNL Experience Manager] サーバーに明示的にアップロードする場合にのみ、デスクトップアプリケーションは更新されたアセットをアップロードします。編集内容を保存しても、変更内容はローカルマシンにのみ保存されます。アップロードすると、アセットは自動的にチェックインされ、ロックアイコンが削除されます。詳しくは、[アセットの編集](upload-assets.md#edit-assets-upload-updated-assets)を参照してください。

## [!DNL Experience Manager] web インターフェイスでのデスクトップアクションの有効化 {#desktopactions-v2}

ブラウザーの [!DNL Assets] ユーザーインターフェイスから、アセットの場所を参照したり、アセットをチェックアウトしてデスクトップアプリケーションで編集用に開いたりできます。これらのオプションは「[!UICONTROL Desktop Actions]」と呼ばれ、デフォルトでは有効になっていません。有効にするには、次の手順に従います。

1. [!DNL Assets] コンソールで、ツールバーの「**[!UICONTROL User]**」アイコンをクリックします。
1. 「**[!UICONTROL My Preferences]**」をクリックして、**[!UICONTROL Preferences]** ダイアログを表示します。

1. [!UICONTROL User Preferences]ダイアログで、「**[!UICONTROL Show Desktop Actions For Assets]**」を選択し、「**[!UICONTROL Accept]**」をクリックします。

   ![「アセットのデスクトップアクションを表示」をオンにしてデスクトップアクションを有効化](assets/enable_desktop_actions1.png)

## [!DNL Assets] Web インターフェイスからの開始 {#adv-workflow-start-from-aem-ui}

必要に応じて、Assets Web インターフェイスからワークフローを開始します。デスクトップアプリケーションは [!DNL Experience Manager] と統合されており、デスクトップアクションを使用して操作が要求された場合、その処理を引き継ぎます。

Web インターフェイスからワークフローを開始する特殊なケースに、アセット検出があります。Assets ユーザーインターフェイスのオムニサーチバーを利用すると、豊かで高度な検索エクスペリエンスが実現します。まず web 上で目的のアセットを探してから、[!UICONTROL Desktop Actions] を使用してアプリケーションでワークフローを開始することができます。例えば、ファセットを使用した検索結果のフィルタリング、Adobe Stock からライセンスを取得した特定アセットの検索、web インターフェイスからの検出を強化できるカスタマイズの組織的実装などがあります。

Assets Web インターフェイスで以下のアクションを実行しようとすると、デスクトップアプリケーション機能が使用されます。

* [!UICONTROL Open]、[!UICONTROL Edit]、[!UICONTROL Reveal]が実行可能な [!UICONTROL Desktop Actions]
* [!UICONTROL Upload folder]
* [!UICONTROL Check-out] または [!UICONTROL check-in]

例えば、アプリケーションでチェックアウトされたアセットに対して Web インターフェイス上で使用できるアクションは、[!UICONTROL Open]、[!UICONTROL Reveal]、[!UICONTROL Check in]です。

![[!DNL Experience Manager] Web インターフェイスのデスクトップアクション](assets/assets_web_actions_da2.png "Experience Manager Web インターフェイスのデスクトップアクション")

>[!NOTE]
>
>[!DNL Adobe Experience Manager] デスクトップの起動の許可を求めるメッセージがブラウザーに表示される場合があります。毎回、ブラウザーからアプリケーションに中断のない転送を行うには、該当するチェックボックスをオンにして、アプリケーションが処理を引き継げるようにします。

Web インターフェイスを使用しても、以下の情報やワークフローは見つかりません。Web インターフェイスではローカルの変更を追跡せず、以下を認識できないので、デスクトップアプリケーションを使用します。

* ファイルはローカルで編集されます。
* 編集上の競合があるファイルとその解決方法。
* ローカルで行った変更の [!DNL Experience Manager] へのアップロード。
* ローカルで使用できるファイルの様々なステータス。

むしろ、**[!UICONTROL Open In Web]** アクションを使用して、デスクトップアプリケーションからWeb インターフェイスを起動し、そこにアセットを開くことができます。

## 次の手順 {#next-steps}

* [ ビデオを視聴してAdobe Experience Manager デスクトップアプリの概要を学ぶ ](https://experienceleague.adobe.com/ja/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app)

* 右側のサイドバーにある [!UICONTROL Edit this page] ![ ページを編集 ](assets/do-not-localize/edit-page.png) または [!UICONTROL Log an issue]GitHub イシュー ![ 作成 ](assets/do-not-localize/github-issue.png) を使用してドキュメントに関するフィードバックを提供する

* [カスタマーケア](https://experienceleague.adobe.com/ja?support-solution=General#support)に問い合わせる

>[!MORELIKETHIS]
>
>* [ ユーザーインターフェイスについて ](/help/using/user-interface.md)
>* [ リリースノートと既知の問題 ](/help/using/release-notes.md)
>* [ デスクトップアプリケーションのインストールまたはアップグレード ](/help/using/install-upgrade.md)
