---
title: デスクトップアプリケーションでのアセットの参照 [!DNL Experience Manager] 検索、プレビュー
description: デスクトップアプリケーションでのアセット  [!DNL Adobe Experience Manager]  参照、検索、プレビュー。
feature: Desktop App
source-git-commit: 2947fbd3bfeb15b37a8f1b0118e969b5d70499d0
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 93%

---


# アセットの参照、検索、プレビュー {#browse-search-preview-assets}

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

## デスクトップでアセットを開く {#openondesktop-v2}

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

### アセット名の特殊文字の管理 {#special-characters-in-filename}

レガシーアプリでは、ユーザーが指定したフォルダー名のスペースと大文字／小文字の区別をそのまま使用した名前のノードが、リポジトリー内に作成されます。現在のアプリケーションでv1.10アプリケーションのノード命名規則をエミュレートするには、「[!UICONTROL Preferences]」で「[!UICONTROL Use legacy conventions when creating nodes for assets and folders]」を有効にします。[アプリケーションの環境設定](/help/using/install-upgrade.md#set-preferences)を参照してください。このレガシー環境設定は、デフォルトでは無効になっています。

>[!NOTE]
>
>アプリケーションは、次の命名規則を使用して、リポジトリ内のノード名のみを変更します。デスクトップアプリケーションは、アセットの`Title`をそのまま保持します。

| 文字数‡ | アプリ内のレガシーの環境設定 | ファイル名で使用する場合 | フォルダー名で使用する場合 | 例 |
|---|---|---|---|---|
| `. / : [ ] \| *` | 有効または無効 | `-`（ハイフン）に置き換えられます。ファイル名拡張子の `.`（ドット）は、そのまま保持されます。 | `-`（ハイフン）に置き換えられます。 | `myimage.jpg` は保持され、`my.image.jpg` は `my-image.jpg` に変更されます。 |
| `% ; # , + ? ^ { } "` および空白 | ![選択解除アイコン](assets/do-not-localize/deselect-icon.png)無効 | 空白は保持されます | `-`（ハイフン）に置き換えられます。 | `My Folder.` が `my-folder-` に変更されます。 |
| `# % { } ? & .` | ![選択解除アイコン](assets/do-not-localize/deselect-icon.png)無効 | `-`（ハイフン）に置き換えられます。 | 該当なし。 | `#My New File.` が `-My New File-` に変更されます。 |
| 大文字 | ![選択解除アイコン](assets/do-not-localize/deselect-icon.png)無効 | 大文字／小文字はそのまま保持されます。 | 小文字に変更されました。 | `My New Folder` が `my-new-folder` に変更されます。 |
| 大文字 | ![選択チェック済みアイコン](assets/do-not-localize/selection-checked-icon.png)有効 | 大文字／小文字はそのまま保持されます。 | 大文字／小文字はそのまま保持されます。 | 該当なし。 |

‡文字のリストは空白で区切られたリストです。

## 編集したすべての画像の検索 {#find-all-edited-images}

デスクトップアプリケーションには、「**[!UICONTROL Edited locally]**」というビューが用意されており、（「[!UICONTROL Open]」または「[!UICONTROL Edit]」アクションを使用して）ローカルにダウンロードしてから変更したすべてのファイルにすばやくアクセスできます。デスクトップアプリケーションでは、ローカルで編集したすべてのアセットを選択し、数回のクリックで変更内容をアップロードできます。このビューには、編集上の競合がある、ローカルで編集したアセットも表示されます。

![ローカルで編集したすべてのアセットを表示するフィルター](assets/edited_locally_filter_da2.png "例えば、ローカルで編集したすべてのアセットを編集内容の一括アップロードのために表示するフィルター")

## 次の手順 {#next-steps}

* [ ビデオを視聴してAdobe Experience Manager デスクトップアプリの概要を学ぶ ](https://experienceleague.adobe.com/ja/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app)

* 右側のサイドバーにある [!UICONTROL Edit this page] ![ ページを編集 ](assets/do-not-localize/edit-page.png) または [!UICONTROL Log an issue]GitHub イシュー ![ 作成 ](assets/do-not-localize/github-issue.png) を使用してドキュメントに関するフィードバックを提供する

* [カスタマーケア](https://experienceleague.adobe.com/ja?support-solution=General#support)に問い合わせる

>[!MORELIKETHIS]
>
>* [ ユーザーインターフェイスについて ](/help/using/user-interface.md)
>* [ デスクトップアプリケーションの使用 ](/help/using/using-desktop-app.md)
>* [ デスクトップアプリケーションでのAssetsの管理 ](/help/using/assets-management-tasks.md)
