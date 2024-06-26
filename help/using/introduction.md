---
title: ' [!DNL Experience Manager]  デスクトップアプリケーションの概要'
description: ' [!DNL Adobe Experience Manager]  デスクトップアプリを使用して、 [!DNL Adobe Experience Manager Assets]  をデスクトップから直接使用する場合のクリエイティブユーザーのアセット管理ワークフローを最適化する方法を説明します。'
role: User, Admin, Leader
exl-id: 5da36ac5-ab5b-4f8d-b446-ebe2360ec464
source-git-commit: 1c7437786a50eeafa884ce92b745f3438b2d2b88
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 68%

---

# [!DNL Adobe Experience Manager] デスクトップアプリケーションの概要 {#overview-v2}

アドビでは、事業部門のユーザーやクリエイティブプロフェッショナルの生産性を向上させるために、ソリューション間をつなぐコネクテッドワークフローを提供しています。[!DNL Adobe Experience Manager] デスクトップアプリケーションは、リポジトリーとアドビ製およびサードパーティ製のデスクトップアプリケーションとを接続することで、リソースへのすばやいアクセスとワークフローの効率化を実現します。これにより、からアセットを操作するユーザーの効率が向上し、時間と労力が削減されます [!DNL Adobe Experience Manager] デスクトップワークフローで。

デスクトップアプリケーションを使用すると、[!DNL Experience Manager Assets] 内のアセットにローカルデスクトップから手軽にアクセスし、任意のデスクトップアプリケーションで利用できるようになります。アセットは、任意のデスクトップアプリケーションで開いて編集できます。 ローカルでの編集は、新しいバージョンとしてに保存されます。 [!DNL Experience Manager] 変更内容をアップロードする場合にのみ、デスクトップ上で作業中のファイルを効率的に編集できるようになります。 アプリケーションでは、アセットおよびネストしたフォルダーの [!DNL Experience Manager] へのアップロードをサポートしているので、リポジトリーへの新しいコンテンツの追加を簡単におこなえます。

このような統合により、組織内の様々な役割のユーザーがアセットを [!DNL Experience Manager Assets] で一元管理できます。マーケターやビジネスユーザーは、ブランディングやライセンスなどの様々な標準に確実に準拠できます。専用のを持つクリエイティブユーザー [Adobeアセットリンク](https://business.adobe.com/products/experience-manager/assets/adobe-asset-link.html) ツールは、Adobe Photoshop、IllustratorおよびInDesignのアセットにアクセスでき、Creative Cloudおよび他のネイティブアプリケーションのデスクトップ上のアセットにもアクセスできます。

>[!NOTE]
>
>デスクトップアプリケーションは [!DNL Adobe Experience Manager] 6.1 リリースで導入され、以前は [!DNL Adobe Experience Manager Assets] Companion App と呼ばれていました。アプリケーションのバージョン 1.x について詳しくは、左側のサイドバーの目次を参照してください。アドビでは、最新バージョンへのアップグレードをお勧めします。

デスクトップアプリケーションのドキュメントには、次の役割と使用例に対応する情報が含まれています。

| 必要な情報 | ヘルプの目次 |
|--- |--- |
| 最新バージョンの新機能と機能強化の概要 | [デスクトップアプリケーションの新機能](#whats-new-v2) |
| 前提条件と技術仕様。ダウンロードリンク | [リリースノート](release-notes.md) |
| デスクトップアプリケーションの既存ユーザーの場合は、アップグレードと移行をスムーズに進める方法 | [以前のバージョンからのアップグレード](install-upgrade.md#upgrade-from-previous-version) |
| 導入方法。デフォルトの環境設定を調整する方法 | [デスクトップアプリケーションのインストールと設定](install-upgrade.md) |
| アセットの参照、検出、編集、アップロード、競合の解決、一括操作などをおこなう方法 | [ [!DNL Experience Manager]  デスクトップアプリケーションの使用 ](using.md) |
| 問題が発生していますか？ | [ [!DNL Experience Manager]  デスクトップアプリケーションのトラブルシューティング](troubleshoot.md) |

## デスクトップアプリケーションの新機能 {#whats-new-v2}

以前のバージョンに対する数々の改善を提供するために、デスクトップアプリケーション v2.0 が新規に作成されました。この新しいバージョンは、より使いやすく、新しいアプリケーション UI を備えた専用のデスクトップエクスペリエンスを提供します。ユーザーは、を使用しなくても、検索または参照によってアセットを検出したり、変更を開いたり、編集したり、アップロードしたりできます。 [!DNL Experience Manager] インターフェイス。 このバージョンでは、[!DNL Experience Manager] インターフェイスからファイルを開くこともできます。

この新しいデスクトップアプリケーションでは、以前と同じ使用例に対応しながら、ユーザーエクスペリエンスを大幅に改善しました。主要な改善点を以下に示します。

* ユーザーは、アプリの組み込みブラウザー内で参照および検索することで、アセットを検出できます。 これにより、仮想ネットワーク共有を表示する際に、Mac Finder や Windows エクスプローラーを使用する必要がなくなります。
* 使用可能なアクションに関する明確なガイダンスが用意されています。
* 帯域幅の使用量を減らすことで、パフォーマンスが向上しました。元のバイナリファイルは、必要な場合にのみダウンロードされます。アセットの参照と検索の場合には、小さなサムネールのみ転送されます。
* バルクアップロードなどの一括操作に最適化されています。

新しいデスクトップアプリケーションの主な使用例と機能強化は、次の図に示すカスタマージャーニーに対応しています。

![[!DNL Experience Manager] デスクトップアプリケーションの新機能 ](assets/aem_desktop_app_usecases_v2.png)

デスクトップアプリケーションを使用すると、ユーザーは上記のすべてのユースケースを達成できます。 必要に応じて、web インターフェイスでアセット検出を実行し、コントロールをアプリに渡してアセットを開き、編集することもできます。
