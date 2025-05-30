---
title: ' [!DNL Experience Manager]  デスクトップアプリケーションの使用'
description: ' [!DNL Adobe Experience Manager] デスクトップアプリを使用すると、Windows または Mac のデスクトップから直接 [!DNL Adobe Experience Manager]  DAM アセットを操作し、他のアプリケーションで使用することができます。'
mini-toc-levels: 1
feature: Desktop App,Asset Management
exl-id: fa19d819-231a-4a01-bfd2-6bba6fec2f18
source-git-commit: fb11b41020a4c2b2c40e8adcde822c65a7fe8985
workflow-type: ht
source-wordcount: '4734'
ht-degree: 100%

---

# [!DNL Adobe Experience Manager] デスクトップアプリケーションの使用 {#use-aem-desktop-app-v2}

[!DNL Adobe Experience Manager] デスクトップアプリを使用して、ローカルデスクトップ上の [!DNL Adobe Experience Manager] DAM リポジトリに保存されたデジタルアセットにアクセスします。その後、これらのアセットを任意のデスクトップアプリケーションで使用できます。デスクトップアプリケーションでアセットをローカルに開いて編集できます。変更を加えたら、バージョン管理を使用して [!DNL Experience Manager] にアップロードし直し、他のユーザーと更新を共有します。また、新しいファイルおよびフォルダー階層を [!DNL Experience Manager] にアップロードしたり、フォルダーを作成したり、[!DNL Experience Manager] DAM からアセットやフォルダーを削除したりすることもできます。

この統合により、組織内の様々な役割のユーザーがアセットを [!DNL Experience Manager Assets] で一元管理し、Windows または macOS のローカルデスクトップでネイティブアプリケーションからアセットにアクセスできます。

ログアウト後または初めてアプリケーションを開くときに、[!DNL Experience Manager] サーバーの URL を `https://[aem-server-url]:[port]/` の形式で指定します。次に、「[!UICONTROL Connect]」オプションを選択します。アプリケーションをサーバーに接続するための認証情報を入力します。

[!DNL Adobe Experience Manager] デスクトップアプリを使用して行う主なタスクは次のとおりです。

![[!DNL Experience Manager] デスクトップアプリケーションを使用して実行できるワークフローとタスク](assets/aem_desktop_app_usecases_v2.png " [!DNL Adobe Experience Manager]  デスクトップアプリケーションを使用して実行できるワークフローとタスク")

<!--Download [this](assets/aem_desktop_app_usecases_print.pdf) print-ready PDF file.-->

## デスクトップアプリケーションの動作の仕組み {#how-app-works2}

アプリケーションの使用を開始する前に、[アプリケーションの仕組み](release-notes.md#how-app-works)を理解しておきましょう。また、次の用語についても把握しておいてください。

* **[!UICONTROL Desktop Actions]**：ブラウザーで Assets web インターフェイスから、アセットの場所を参照したり、アセットをチェックアウトしてネイティブデスクトップアプリケーションで編集用に開いたりできます。これらのアクションは web インターフェイスから実行でき、デスクトップアプリケーションの機能を使用します。詳しくは、[デスクトップアクションを有効にする方法](using.md#desktopactions-v2)を参照してください。

* ファイルのステータスが「**[!UICONTROL Cloud Only]**」：アセットはローカルマシンにはダウンロードされず、[!DNL Experience Manager] サーバー上でのみ使用可能です。

* ファイルのステータスが「**[!UICONTROL Available locally]**」：アセットはローカルマシンにダウンロードされ、そのまま使用できます。ただし、アセットは変更されません。

* ファイルのステータスが「**[!UICONTROL Edited locally]**」：アセットはローカルに編集され、変更内容は [!DNL Experience Manager] サーバーにアップロードされた後も保持されます。アップロード後、ステータスは「[!UICONTROL Available locally]」に変わります。詳しくは、[アセットの編集](using.md#edit-assets-upload-updated-assets)を参照してください。

* ファイルのステータスが **[!UICONTROL Editing conflict]** ：複数のユーザーがアセットを同時に編集した場合は、編集上の競合が発生したことをアプリケーションが知らせます。また、変更内容を保持するか破棄するかの選択肢も提示されます。詳しくは、[編集上の競合の回避方法](using.md#adv-workflow-collaborate-avoid-conflicts)を参照してください。

* ファイルのステータスが「**[!UICONTROL Modified remotely]**」：ダウンロードしたアセットが [!DNL Experience Manager] サーバー上で変更されたことをデスクトップアプリケーションが知らせます。また、最新バージョンをダウンロードするか、ローカルコピーを更新するかの選択肢も提示されます。詳しくは、[編集上の競合の回避方法](using.md#adv-workflow-collaborate-avoid-conflicts)を参照してください。

* **[!UICONTROL Check-out]**：ファイルを編集しようとしている場合やファイルを編集する予定である場合は、ステータスをチェックアウトに切り替えます。アプリケーションと [!DNL Experience Manager] web インターフェイスで、アセットにロックアイコンが表示されます。ロックアイコンは、編集上の競合が発生するため、同じアセットを同時に編集しないように他のユーザーに指示する働きをします。

* **[!UICONTROL Check-in]**：編集上の競合が発生することなく他のユーザーが安全にアセットを編集できることを知らせます。変更内容をアップロードすると、ロックアイコンは自動的に削除されます。チェックインステータスを切り替えるとロックアイコンも削除されますが、変更内容をアップロードせずに手動でチェックインしないでください。変更内容を破棄した場合は、手動でチェックインに切り替えます。

* 「**[!UICONTROL Open]**」アクション：アセットを開いて、ネイティブアプリケーションでプレビューするだけです。アドビでは、この操作を使用してアセットを編集しないことをお勧めします。アセットがチェックアウトされないからです。その間、他のユーザーが編集を行うと、編集の競合が発生する可能性があります。

* **[!UICONTROL Open with]** アクション：「プログラムから開く」機能を使用すると、デフォルトのアプリケーション以外の特定のアプリケーションでファイルを開くことができます。これは、好みのプログラムを選択したり、異なる形式のファイルにアクセスしたり、デフォルトのアプリに関する問題をトラブルシューティングしたり、複数のプログラムで作業したりする場合に役立ちます。設定を永続的に変更せずに、デフォルトのアプリケーションを一時的に上書きできるようにすることで、柔軟性を提供します。

* 「**[!UICONTROL Open In Web]**」アクション：[!DNL Experience Manager] Web インターフェイスでアセットを確認するには、アセットを web で開きます。[!DNL Experience Manager] インターフェイスからは、メタデータの更新やアセットの検出など、さらに多くのワークフローを開始できます。

* **[!UICONTROL Edit]**&#x200B;アクション：アセットを編集できます。[!UICONTROL Edit] をクリックすると、アセットがチェックアウトされ、アセットにロックアイコンが表示されます。このアクションをクリックした後、アセットを編集しない場合は、「[!UICONTROL Toggle check-in]」をクリックします。[!DNL Experience Manager] DAM フォルダー階層内のアセットを削除、名前変更または移動するには、編集アクションではなく、[!DNL Experience Manager] web インターフェイスのアクションを使用します。

* 「**[!UICONTROL Download]**」アクション：アセットをローカルマシンにダウンロードします。アセットをすぐにダウンロードし、後で編集できます。オフラインで作業し、後で変更内容をアップロードすることができます。アセットは、ファイルシステム上のキャッシュフォルダーにダウンロードされます。

* 「**[!UICONTROL Reveal File]**」または「**[!UICONTROL Reveal Folder]**」アクション：アセットがローカルキャッシュフォルダーにダウンロードされると、デスクトップアプリケーションはローカルネットワークドライブを模倣します。各アセットのローカルパスを提供します。このパスを確認するには、デスクトップアプリケーションで適切な表示オプションを使用します。Creative Cloud アプリケーションにアセットを配置するには、このアクションが必要です。詳しくは、[アセットの配置](using.md#place-assets-in-native-documents)を参照してください。

* **[!UICONTROL Delete]** アクション：[!DNL Experience Manager] DAM リポジトリーからアセットを削除します。このアクションで、Adobe Experience Manager サーバーにあるアセットの元のコピーが削除されます。ローカルアセットに対する変更だけを破棄する場合は、[変更の破棄](using.md#edit-assets-upload-updated-assets)を参照してください。

* 「**[!UICONTROL Upload Changes]**」アクション：[!DNL Experience Manager] サーバーに明示的にアップロードする場合にのみ、デスクトップアプリケーションは更新されたアセットをアップロードします。編集内容を保存しても、変更内容はローカルマシンにのみ保存されます。アップロードすると、アセットは自動的にチェックインされ、ロックアイコンが削除されます。詳しくは、[アセットの編集](using.md#edit-assets-upload-updated-assets)を参照してください。

## [!DNL Experience Manager] web インターフェイスでのデスクトップアクションの有効化 {#desktopactions-v2}

ブラウザーの [!DNL Assets] ユーザーインターフェイスから、アセットの場所を参照したり、アセットをチェックアウトしてデスクトップアプリケーションで編集用に開いたりできます。これらのオプションは「[!UICONTROL Desktop Actions]」と呼ばれ、デフォルトでは有効になっていません。有効にするには、次の手順に従います。

1. [!DNL Assets] コンソールで、ツールバーの「**[!UICONTROL User]**」アイコンをクリックします。
1. 「**[!UICONTROL My Preferences]**」をクリックして、**[!UICONTROL Preferences]** ダイアログを表示します。

1. [!UICONTROL User Preferences]ダイアログで、「**[!UICONTROL Show Desktop Actions For Assets]**」を選択し、「**[!UICONTROL Accept]**」をクリックします。

   ![「アセットのデスクトップアクションを表示」をオンにしてデスクトップアクションを有効化](assets/enable_desktop_actions.png)

   *図：「[!UICONTROL Show Desktop Actions For Assets]」をオンにしてデスクトップアクションを有効化。*

## アセットの表示 {#view-assets}

AEM デスクトップアプリでは、次の 4 つの異なるビューでアセットを表示できます。

* **[!UICONTROL Show Assets]：**&#x200B;すべてのアセットを表示できます。
* **[!UICONTROL Show Collections]：**&#x200B;ネイティブの AEM アプリケーションで作成されたすべてのコレクションを表示できます。その他の[コレクション](#collections-desktop-app)を参照してください。
* **[!UICONTROL Edited Locally]：**&#x200B;ローカルで変更されたすべてのアセットを表示できます。このビューでは、複数のアセットを追加してアップロードできます。
* **[!UICONTROL Asset transfers]：**&#x200B;ネイティブアプリからローカルに、またはその逆に転送されたすべてのアセットを表示できます。
* **[!UICONTROL Pinned items]：**&#x200B;ピン留めされたすべての項目を表示できます。

AEM デスクトップアプリでアセットの様々なビューの中から選択するには、次の手順を実行します。

1. AEM デスクトップアプリを開きます。

1. 右上のビュードロップダウンに移動します。使用可能なビューから 1 つ選択します。

   ![フォルダーのピン留めまたはピン留めを解除](assets/view-pinned-assets.png)

### 新しく追加されたフォルダーとファイルを表示 {#view-newly-added-files-folders}

新しく作成したアセットをローカルマシンから、中央リポジトリが格納されている AEM にアップロードできます。これらの新しく作成されたアセットをローカルに表示するには、**[!UICONTROL View]** ドロップダウンメニューに移動して「**[!UICONTROL Show Assets]**」を選択し、タイムラインとタイトルを含むすべてのアップデートを表示するか、「**[!UICONTROL Edited Locally]**」を選択します。どちらのオプションでも、ローカルに編集されたアセットが明示的に表示されます。

## アセットの参照、検索、プレビュー {#browse-search-preview-assets}

[!DNL Experience Manager] リポジトリーで使用可能なアセットをデスクトップアプリケーション内から参照、検索およびプレビューできます。それには、デスクトップアプリケーションで以下を行います。

1. フォルダーを参照し、そのフォルダー内で使用可能なアセットの基本情報と、すべてのアセットの小さなサムネールを確認します。

   ![DAM ファイルおよびフォルダーの参照 ](assets/browse_folder_da2.png "DAM ファイルおよびフォルダーの参照")

1. 個々のアセットの詳細情報と大きいサムネールを表示するには、ファイル名をクリックします。

   ![アセットとアクションの大きいプレビューの表示](assets/large_preview_actions_da2.png "アセットとアクションの大きいプレビューの表示")

1. 「**[!UICONTROL Open]**」または「**[!UICONTROL Edit]**」をクリックすると、ファイルがローカルにダウンロードされ、それぞれネイティブアプリケーションでファイルを表示または編集することができます。
1. キーワードを使用して検索すると、[!DNL Experience Manager] リポジトリー内の関連アセットを見つけることができます。`?` や `*` をワイルドカードとして使用します。これらのワイルドカードは、それぞれ 1 文字または複数文字に置き換えられます。必要に応じて、検索結果をフィルタリングしたり並べ替えたりします。

   ![アスタリスクワイルドカードを使用した検索例](assets/search_wildcard_da2.png "アスタリスクワイルドカードを使用した検索例")

   ![アスタリスクワイルドカードを使用した別の検索例](assets/search_wildcard2_da2.png "アスタリスクワイルドカードの位置が異なる別の検索例")

>[!NOTE]
>
>デスクトップアプリケーションは、アセットのタイトルやファイル名だけでなく、複数のメタデータフィールドを検索条件と照合してアセットを表示します。

## アセット管理 {#assets-management}

アセット管理では、ワークフローを合理化するためのデジタルアセットの整理、維持管理および最適化を行います。これには、ファイルの複製と名前変更、クイックアクセスのためのフォルダーのピン留めまたはピン留め解除、様々なレイアウトでのアセットの表示などのタスクが含まれます。これにより、効率が向上し、アセットのトラッキングが簡素化され、複数のプラットフォーム間でデジタルアセットを簡単に取得および整理できます。

### 重複ファイル {#duplicate-files}

元のファイルを保持し、類似したファイルに変更を加える場合は、異なる場所（ローカルとクラウド）でファイルを同時に複製できます。これは、アセットをまたいだ「ファイルを複製」操作で実現できます。

AEM デスクトップアプリでファイルを複製するには、次の手順に従います。

1. フォルダーを参照し、複製するアセットを選択します。

   ![重複ファイル](assets/more-options.png)

1. **[!UICONTROL More actions]** ![他のアクションアイコン](assets/do-not-localize/more2_da2.png) をクリックし、![複製アイコン](assets/do-not-localize/duplicate.svg) **[!UICONTROL Duplicate File]** アクションを選択します。

1. 重複ファイルは、同じファイル名とコンテンツで作成されます。

### アセットのタイトルの名前を変更する {#rename-asset-title}

アセットのタイトルの名前を変更するには、次の手順を実行します。

1. 名前を変更するアセットを参照します。

1. **[!UICONTROL More actions]** ![他のアクションアイコン](assets/do-not-localize/more2_da2.png) をクリックし、「**[!UICONTROL Rename]**」を選択してアセットの目的のタイトルを追加します。

<!--1. Click **[!UICONTROL More actions]** ![More actions icon](assets/do-not-localize/more2_da2.png) and select **[!UICONTROL open in web]** to open the asset in its native application.

1. Go to asset details. Under [!UICONTROL Basic] tab, go to title and enter the text.-->

### フォルダーのピン留めまたはピン留めを解除 {#pin-unpin-folder}

クイックアクセスを行うには、次の手順を実行して、フォルダーをピン留めまたはピン留めを解除します。

1. ピン留めまたはピン留めを解除するアセットを参照します。

1. **[!UICONTROL More actions]** ![他のアクションアイコン](assets/do-not-localize/more2_da2.png) をクリックし、「[!UICONTROL pin]」を選択してアセットまたはフォルダーをピン留めします。または、「[!UICONTROL unpin]」をクリックしてピン留めを解除します。

   ![フォルダーのピン留めまたはピン留めを解除](assets/pin-unpin.png)

### 自動更新 {#auto-refresh}

自動更新機能により、コンテンツがリアルタイムで自動的に更新されるので、ページを手動で再読み込みすることなく、常に最新情報を確認できます。以下の手順を実行してアセットを自動的に更新し、更新されたアセットのリストを取得します。

1. AEM デスクトップアプリを開きます。

1. メニューバーの ![更新アイコン](assets/do-not-localize/refresh.png) をクリックして、更新内容を取得する。

## アセットのダウンロード {#download-assets}

アセットはローカルファイルシステムにダウンロードできます。デスクトップアプリケーションは [!DNL Experience Manager] サーバーからアセットを取得し、それと同じコピーをローカルファイルシステムに保存します。

オプション用に **[!UICONTROL More actions]** ![その他のオプションアイコン](assets/do-not-localize/more2_da2.png) をクリックし、![ダウンロードアイコン](assets/do-not-localize/download_cloud_da2.png) をクリックしてダウンロードします。

![アセットのダウンロードオプション](assets/download_option_da2.png "アセットのダウンロードオプション")

>[!NOTE]
>
>大きなファイルまたは多数のファイルをダウンロードまたはアップロードするときは、アセットやフォルダーに対するアクションが無効になります。これらのアクションは、ダウンロードまたはアップロードが完了すると使用可能になります。

キューのサイズが大きい場合や、ネットワークに問題が発生した場合は、複数のアセットをダウンロードするとパフォーマンスが低下する可能性があります。また、フォルダーのダウンロード時には、知らないうちに、ダウンロードするアセットを多数キューに入れてしまう場合もあります。待ち時間が長くならないようにするために、1 回の操作でダウンロードされるアセットの数が制限されています。その設定方法については、[環境設定の指定](install-upgrade.md#set-preferences)を参照してください。この制限を下回っていても、明らかに大きなフォルダーをダウンロードする場合は、その前に確認が求められることがあります。

![比較的多くのアセットをダウンロードする場合の確認](assets/download_confirmation_da2.png "比較的多くのアセットをダウンロードする場合の確認")

フォルダーを選択してダウンロードした場合は、[!DNL Experience Manager] のフォルダーに直接保存されているアセットのみダウンロードされます。サブフォルダー内のアセットが自動的にダウンロードされることはありません。

## デスクトップでアセットを開く {#openondesktop-v2}

リモートアセットを開いて、ネイティブアプリケーションで表示することができます。アセットがローカルフォルダーにダウンロードされます。その後、ファイル形式に関連付けられたネイティブアプリケーションで起動されます。ネイティブアプリケーションを変更して、Mac または Windows で特定のファイルタイプ（拡張子）のアセットを開くことができます。

アセットメニューから「**[!UICONTROL Open]**」を選択します。アセットがローカルにダウンロードされ、ネイティブアプリケーションで開かれます。大きなアセットの場合は、ステータスバーでダウンロードの進行状況と転送速度を確認します。

<!-- ![Download progress bar for large-sized assets](assets/download_status_bar_da2.png "Download progress bar for large-sized assets")
-->

>[!NOTE]
>
>期待した変更がデスクトップアプリケーションに反映されない場合は、更新アイコン ![更新アイコン](assets/do-not-localize/refresh.png) をクリックするか、デスクトップアプリケーションインターフェイスで右クリックし、「**[!UICONTROL Refresh]**」を選択します。大量のダウンロードまたはアップロードが進行中の間、これらのアクションは使用できません。

アセットのローカルダウンロードフォルダーを開くには、![その他のアクションアイコン](assets/do-not-localize/more2_da2.png)、![表示アイコン](assets/do-not-localize/reveal_action2_da2.png) 「**[!UICONTROL Reveal File]**」アクションの順にクリックします。

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

## アセットの編集と [!DNL Experience Manager] への更新済みアセットのアップロード {#edit-assets-upload-updated-assets}

アセットに変更を加え、更新したアセットを [!DNL Experience Manager] サーバーにアップロードする際は、アセットを編集用に開きます。他のユーザーの編集内容と競合しないように、デスクトップアプリケーションを使用して編集セッションを開始します。編集を開始する前に、別のユーザーがアセットを編集していることを示すロックアイコンがアセットに付いていないことを確認します。

アセットを編集するには、該当するアセットを検索するか、アセットの場所を参照します。![その他](assets/do-not-localize/more2_da2.png) アイコンをクリックし、「**[!UICONTROL Edit]**」をクリックします。

次のどちらの状況でも、他のユーザーの編集と競合しないように、「**[!UICONTROL Toggle Check-out]**」を使用してアセットをロックします。

* 先にアセットをチェックアウトせずに（例えば単に開いて）アセットの編集を開始した。
* アセットの編集をすぐに開始するつもりであり、他のユーザーには編集されないようにしたい。

編集が完了すると、変更したアセットのステータスが「**[!UICONTROL Edited Locally]**」としてデスクトップアプリケーションに表示されます。アセットに保存した変更は、[!DNL Experience Manager] にアップロードするまでは、すべてローカルのみの変更になります。個々のアセットまたは複数のアセットを 1 つずつアップロードするには、アセットのオプションから「**[!UICONTROL Upload Changes]**」をクリックします。そのアセットの 1 つのバージョンが [!DNL Experience Manager] に作成されます。[!DNL Assets] の web インターフェイスを使用して、[タイムラインビュー](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/assets/using/activity-stream)でアセット履歴を参照できます。

![デスクトップアプリケーションの「Upload Changes」オプション](assets/upload_changes_single1_da2.png "デスクトップアプリケーションの「Upload Changes」オプション")

![アセットの大きなプレビューを表示した場合の「Upload Changes」オプション](assets/upload_changes_single2_da2.png "アセットの大きなプレビューを表示した場合の「Upload Changes」オプション")

共同編集に関するベストプラクティスについては、[高度なワークフロー：同じファイルに対する共同作業と編集上の競合の回避](#adv-workflow-collaborate-avoid-conflicts)を参照してください。

次の場合は、ローカルアセットに対する変更や編集を破棄することができます。「**[!UICONTROL Discard Changes]**」をクリックします。

* 変更内容を [!DNL Experience Manager] にローカルに保存しない場合。
* 変更内容を保存した後、元のアセットに対する変更を開始した場合。
* 必要なくなったのでアセットの編集を停止した場合。

必要に応じて、チェックアウトを切り替えます。更新されたアセットがローカルキャッシュフォルダーから削除され、編集時または開く際に再度ダウンロードされます。

## [!DNL Experience Manager] への新しいアセットのアップロードと追加 {#upload-and-add-new-assets-to-aem}

ユーザーは、DAM リポジトリーに新しいアセットを追加できます。例えば、代理店のフォトグラファーや請負業者は、撮影した大量の写真を [!DNL Experience Manager] リポジトリーに追加したいと考えるかもしれません。新しいコンテンツを [!DNL Experience Manager] に追加するには、アプリの上部バーにある ![クラウドにアップロードオプション](assets/do-not-localize/upload_to_cloud_da2.png) をクリックします。ローカルファイルシステム内のアセットファイルを参照し、「**[!UICONTROL Select]**」をクリックします。または、アプリケーションインターフェイス上でファイルまたはフォルダーをドラッグしてアセットをアップロードします。Windows では、アプリ内のフォルダーにアセットをドラッグすると、そのアセットがフォルダーにアップロードされます。アップロードに時間がかかる場合、アプリには進行状況バーが表示されます。

<!-- ![Download progress bar for large-sized assets](assets/upload_status_da2.png "Download progress bar for large-sized assets")
-->

ローカルファイルシステムからフォルダーや個々のファイルをアップロードできます。フォルダーの階層はアップロード時に保持されます。アセットを一括でアップロードする場合は、まず[バルクアップロード](#bulk-upload-assets)を参照してください。

特定のセッションで転送されたアセットのリストを表示するには、**[!UICONTROL View]**／**[!UICONTROL Assets transfers]** を選択します。このリストを見れば、現在のセッションのファイル転送をざっと確認できます。

![特定のセッションで転送されたアセットのリスト](assets/assets_transfered_da2.png "特定のセッションで転送されたアセットのリスト")

**[!UICONTROL Preferences]**／**[!UICONTROL Upload acceleration]** の設定で、アップロードの同時実行性（高速化）を制御できます。通常は、同時実行性が高いほど、アップロードが高速になりますが、その反面、リソースの消費が大きくなり、ローカルマシンで消費される処理能力が増える可能性があります。システムの処理速度が低下した場合は、同時実行性の設定値を低くして、アップロードを再度試みます。

>[!NOTE]
>
>転送リストは永続的なものではなく、デスクトップアプリケーションを終了して再度開いた場合は使用できません。

<!--### Upload local file to AEM {#upload-local-file-to-aem}-->


### アセット名の特殊文字の管理 {#special-characters-in-filename}

レガシーアプリでは、ユーザーが指定したフォルダー名のスペースと大文字／小文字の区別をそのまま使用した名前のノードが、リポジトリー内に作成されます。現在のアプリケーションでv1.10アプリケーションのノード命名規則をエミュレートするには、「[!UICONTROL Preferences]」で「[!UICONTROL Use legacy conventions when creating nodes for assets and folders]」を有効にします。[アプリケーションの環境設定](/help/using/install-upgrade.md#set-preferences)を参照してください。このレガシー環境設定は、デフォルトでは無効になっています。

>[!NOTE]
>
>アプリケーションは、次の命名規則を使用して、リポジトリ内のノード名のみを変更します。デスクトップアプリケーションは、アセットの`Title`をそのまま保持します。

<!-- TBD: Do NOT use this table.

| Where do characters occur | Characters | Legacy preference | Renaming convention | Example |
|---|---|---|---|---|
| In file name extension | `.` | Enabled or disabled | Retained as is | NA |
| File or folder name | `. / : [ ] | *` | Enabled or disabled | Replaced with a `-` (hyphen) | `myimage.jpg` remains as is and `my.image.jpg` changes to `my-image.jpg`. |
| Folder name | `% ; # , + ? ^ { } "` | Disabled | Replaced with a `-` (hyphen) | tbd |
| File name | `% # ? { } &` | Disabled | Replaced with a `-` (hyphen) | tbd |
| File name | Whitespaces | Enabled or disabled | Retained as is | NA |
| Folder name | Whitespaces | Disabled | Replaced with a `-` (hyphen) | tbd |
| File name | Uppercase characters | Disabled | Retained as is | tbd |
| Folder name | Uppercase characters | Disabled | Replaced with a `-` (hyphen) | tbd |
-->

| 文字数‡ | アプリ内のレガシーの環境設定 | ファイル名で使用する場合 | フォルダー名で使用する場合 | 例 |
|---|---|---|---|---|
| `. / : [ ] \| *` | 有効または無効 | `-`（ハイフン）に置き換えられます。ファイル名拡張子の `.`（ドット）は、そのまま保持されます。 | `-`（ハイフン）に置き換えられます。 | `myimage.jpg` は保持され、`my.image.jpg` は `my-image.jpg` に変更されます。 |
| `% ; # , + ? ^ { } "` および空白 | ![選択解除アイコン](assets/do-not-localize/deselect-icon.png)無効 | 空白は保持されます | `-`（ハイフン）に置き換えられます。 | `My Folder.` が `my-folder-` に変更されます。 |
| `# % { } ? & .` | ![選択解除アイコン](assets/do-not-localize/deselect-icon.png)無効 | `-`（ハイフン）に置き換えられます。 | 該当なし。 | `#My New File.` が `-My New File-` に変更されます。 |
| 大文字 | ![選択解除アイコン](assets/do-not-localize/deselect-icon.png)無効 | 大文字／小文字はそのまま保持されます。 | 小文字に変更されました。 | `My New Folder` が `my-new-folder` に変更されます。 |
| 大文字 | ![選択チェック済みアイコン](assets/do-not-localize/selection-checked-icon.png)有効 | 大文字／小文字はそのまま保持されます。 | 大文字／小文字はそのまま保持されます。 | 該当なし。 |

‡文字のリストは空白で区切られたリストです。

<!-- TBD: Check if the following is to be included in the footnote.

Do not use &#92;&#92; in the names of files and &#92;&#116; &#38; in the names of folders. 
-->


<!-- TBD: Securing the below presentation of the same content in a comment.

**File names**

| Characters | Replaced by |
|---|---|
| &#35; &#37; &#123; &#63; &#125; &#38; &#46; &#47; &#58; &#91; &#124; &#93; &#42; | hyphen (-) |
| whitespaces | whitespaces are retained |
| capital case | casing is retained |

>[!CAUTION]
>
>Avoid using &#92;&#92; in file names.

**Folder names**

| Characters | Replaced by |
|---|---|
| Characters | Replaced by |
| &#37; &#59; &#35; &#44; &#43; &#63; &#94; &#123; &#123; &#34; &#46; &#47; &#59; &#91; &#93; &#124; &#42; | hyphen (-) |
| whitespaces | hyphen (-) |
| capital case | lower case |

>[!CAUTION]
>
>Avoid using &#92;&#92; &#92;&#116; &#38; in folder names.

>[!NOTE]
>
>If you enable [!UICONTROL Use legacy conventions when creating nodes for assets and folders] in app [!UICONTROL Preferences], then the app emulates v1.10 app behavior when uploading folders. In v1.10, the node names created in the repository respect spaces and casing of the folder names provided by the user. For more information, see [app Preferences](/help/using/install-upgrade.md#set-preferences).

-->

## 複数アセットの操作 {#work-with-multiple-assets}

ユーザーは、1 回の操作ですべての編集内容をアップロード、またはネストしたフォルダーを数回のクリックでアップロードするといったアクションを使用して、複数のアセットを容易に操作および管理することができます。

### 大きいフォルダーの参照 {#browse-large-folders}

多数のアセットを含んだフォルダーを操作する場合は、スクロールしてさらにアセットを表示します。キーボードを使用してスクロールするには、Tab キーを数回押して、上部のアセットを選択します。選択されたアセットが強調表示されます。次に、下向き矢印キーを使用して、アセットのリスト内を移動します。

### 選択したアセットに対するクイックアクション {#quick-actions-for-selected-assets}

いくつかのアセットのサムネールをクリックすると、それらのアセットを選択できます。すべてのアセットを選択するには、デスクトップアプリケーションの上部バーにあるチェックボックスをクリックします。選択したすべてのアセットに対して一括で適用できる一連のアクションが、デスクトップアプリケーションの下部にあるツールバーに表示されます。

![選択したアセットの関連アクションを表示する下部のツールバー](assets/actions_bottom_toolbar1_da2.png "選択したアセットに一般に適用できるアクションを表示する下部のツールバー")

![選択したアセットに一般に適用できるアクションがない場合にアクションが表示されないツールバー](assets/actions_bottom_toolbar2_da2.png "選択したアセットに一般に適用できるアクションがない場合にアクションが表示されないツールバー。")

下部のツールバーで使用できるアクションは、選択したファイルのステータスによって異なります。例えば、「**[!UICONTROL Edited Locally]**」ステータスのファイルだけを選択した場合は、「**[!UICONTROL Upload Changes]**」アイコンが表示されます。「**[!UICONTROL Edited locally]**」ステータスと「**[!UICONTROL Cloud only]**」ステータスのファイルを同時に選択した場合、「**[!UICONTROL Upload Changes]**」アクションは使用できません。

### 編集したすべての画像の検索 {#find-all-edited-images}

デスクトップアプリケーションには、「**[!UICONTROL Edited locally]**」というビューが用意されており、（「[!UICONTROL Open]」または「[!UICONTROL Edit]」アクションを使用して）ローカルにダウンロードしてから変更したすべてのファイルにすばやくアクセスできます。デスクトップアプリケーションでは、ローカルで編集したすべてのアセットを選択し、数回のクリックで変更内容をアップロードできます。このビューには、編集上の競合がある、ローカルで編集したアセットも表示されます。

![ローカルで編集したすべてのアセットを表示するフィルター](assets/edited_locally_filter_da2.png "例えば、ローカルで編集したすべてのアセットを編集内容の一括アップロードのために表示するフィルター")

### アセットの一括アップロード {#bulk-upload-assets}

カメラマンやクリエイティブ制作代理店などのユーザーまたは組織は、撮影、レタッチ、大量の写真からの選択など、アクティビティ中に、多数のローカルアセットを作成できます。これらのタスクは多くの場合、[!DNL Experience Manager] の外部で行われます。これらの大きなローカルフォルダーを、デスクトップアプリケーションから直接 [!DNL Assets] にアップロードできます。フォルダー階層が保持され、ネストしたサブフォルダーとその中に含まれているアセットがすべてアップロードされます。アップロードしたアセットは、同じサーバーの他のユーザーからもすぐに利用できます。アセットはバックグラウンドでアップロードされるので、操作が web ブラウザーセッションに縛られることはありません。

![デスクトップから [!DNL Experience Manager]](assets/upload_local_folders_da2.png " への複数のローカルフォルダーのバルクアップロードデスクトップから Experience Manager への複数のローカルフォルダーのバルクアップロード")

アップロード後に、期待した変更がデスクトップアプリケーションに反映されない場合は、更新アイコン ![更新アイコン](assets/do-not-localize/refresh.png) をクリックします。

>[!NOTE]
>
>アップロード機能を使用して 2 つの [!DNL Experience Manager] デプロイメントをまたいでアセットを移行することは避けてください。その代わり、[移行ガイド](https://experienceleague.adobe.com/ja/docs/experience-manager-65/content/assets/administer/assets-migration-guide)を参照してください。

### 転送したアセットのリスト {#list-of-transferred-assets}

特定のセッションで転送されたアセットのリストを表示するには、[ [!DNL Experience Manager]](#upload-and-add-new-assets-to-aem) へのアセットのアップロードを参照してください。

## 高度なワークフロー：[!DNL Assets] web インターフェイスからの開始 {#adv-workflow-start-from-aem-ui}

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

## 高度なワークフロー：アセットのローカルダウンロード {#adv-workflow-download-assets-locally}

デスクトップアプリケーションは、[!DNL Experience Manager] サーバーからローカルファイルシステムにアセットを頻繁にダウンロードします。ダウンロードすると、帯域幅とディスク容量を消費します。状況を把握することで、ダウンロードが完了するまでの待ち時間を最適化できます。

アプリケーション内からアセットをオンデマンドでダウンロードできます。詳しくは、[アセットのダウンロード](#download-assets)を参照してください。

「[!UICONTROL Open]」アクションを使用してネイティブデスクトップアプリケーションでアセットを開くと、そのアセットがまだローカルで使用できない場合は、ローカルにダウンロードされます。詳しくは、[アセットを開く](#openondesktop-v2)を参照してください。

デスクトップアプリケーション内からアセットまたはフォルダーの場所を表示すると、そのアセットまたはフォルダーはまずローカルにダウンロードされてから、ユーザーのコンピューター上のローカルネットワーク共有内で開かれます。詳しくは、[アセットを開く](#openondesktop-v2)を参照してください。

「[!UICONTROL Edit]」アクションを使用してネイティブデスクトップアプリケーションでアセットを編集すると、そのアセットがまだローカルで使用できない場合は、ローカルにダウンロードされます。詳しくは、「[アセットの編集と  [!DNL Experience Manager]](#edit-assets-upload-updated-assets) への更新済みアセットのアップロード」を参照してください。

デスクトップアプリケーションがインストール済みで、アクションの権限がある場合は、[!DNL Experience Manager] Web インターフェイスで[!UICONTROL Desktop Actions]を使用すると、該当するアクションが完了します。デスクトップアプリケーションはまずアセットをダウンロードしてから、アクションを実行します。
