---
title: "Power BI usage scenarios: Personal BI"
description: "Learn how Power BI personal BI is about private analytics for an individual."
author: peter-myers
ms.author: v-petermyers
ms.reviewer: maroche
ms.service: powerbi
ms.subservice: powerbi-resource
ms.topic: conceptual
ms.date: 02/07/2022
---

# Power BI usage scenarios: Personal BI

[!INCLUDE [powerbi-implementation-planning-context](includes/powerbi-implementation-planning-context.md)] 。

[Power BI導入ロードマップ](powerbi-adoption-roadmap-content-delivery-scope.md#personal-bi)に記載されているように、*personal BI*とは、個人が分析価値を得られるようにすることです。また、データ、情報、アナリティクスを活用して、ビジネスタスクをより効率的に実行できるようにすることでもあります。パーソナルBIは、「セルフサービスBI」の入口と考えられている。

パーソナルBIのシナリオでは、コンテンツ作成者は、個人の使用目的に合わせて自由にコンテンツを作成することができます。通常、シンプルさとスピードが優先されます。これらのトピックは、[チームBI](powerbi-implementation-planning-useage-scenario-team-bi.md)、[部門BI](powerbi-implementation-planning-useage-scenario-departmental-bi.md)、[エンタープライズBI](powerbi-implementation-planning-useage-scenario-enterprise-bi.md)のシナリオ記事で取り上げられています。

> [! NOTE] > 4つの*コンテンツのコラボレーションと配信*のシナリオがあり、それらは互いに積み重なっています。パーソナルBIシナリオは、4つのシナリオのうちの最初のシナリオです。すべてのシナリオのリストは、[Power BI usage scenarios overview](powerbi-implementation-planning-use-scenario-overview.md)の記事にあります。

## Scenario diagram

次の図は、パーソナルBIをサポートする最も一般的なユーザーアクションとPower BIコンポーネントのハイレベルな概要を描いています。ここでは、個人のためのプライベート分析に焦点を当てています。

:::image type="content" source="media/powerbi-implementation-planning-useage-scenario-personal-bi/usage-scenario-personal-bi-inline.png" alt-text="画像は、個人向けのプライベート分析をテーマにしたパーソナルBⅠの図を示しています。図中の項目は下の表に記載されています。" lightbox="media/powerbi-implementation-planning-usage-scenario-personal-bi/usage-scenario-personal-bi-expanded.png" border="false":::

シナリオ図では、以下のようなユーザーのアクション、ツール、機能が描かれています。

| **Item** | **Description** |
| --- | --- |
| ![Item 1.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-01-red-30x30.png) | Power BIコンテンツクリエーターは、以下のようなBIソリューションを開発します。 [Power BI Desktop](../fundamentals/desktop-what-is-desktop.md). |
| ![Item 2.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-02-red-30x30.png) | Power BI Desktopは、1つまたは複数のデータソースからデータに接続します。複数のソースを組み合わせたクエリやデータマッシュアップは、[Power Query Editor](/power-query/power-query-what-is-power-query)で開発します。 |
| ![Item 3.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-03-red-30x30.png) | データモデルの開発とレポートの作成は、Power BI Desktopで行います。パーソナルBIソリューションでは、一般的にデータの探索と分析が主な目的となります。|
| ![Item 4.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-04-red-30x30.png) | 準備ができたら、コンテンツ作成者はPower BI Desktopファイル(.pbix)を[Power BIサービス](../fundamentals/power-bi-service-overview.md)に公開します。 |
| ![Item 5](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-05-red-30x30.png) | 個人的な使用を主な目的としているため、コンテンツはコンテンツ作成者の[マイワークスペース](../fundamentals/service-basic-concepts.md#workspaces)に公開されます。Power BI Desktopのみではなく、Power BIサービスを利用するメリットとしては、データの定期的な更新、ダッシュボードのアラート、モバイルアプリを使ってコンテンツを消費できることなどが挙げられます。|
| ![Item 6.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-06-red-30x30.png) | コンテンツ作成者は、公開されたコンテンツを閲覧し、対話します。Webブラウザを使ってPower BIサービスにサインインするという方法もあります。|
| ![Item 7.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-07-red-30x30.png) |コンテンツ作成者は、[Power BI モバイルアプリ](../consumer/mobile/mobile-apps-for-mobile-devices.md)を使って、公開されたコンテンツを見ることもできます。 |
| ![Item 8.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-08-red-30x30.png) | Power BIサービスでは、インポートしたデータを常に最新の状態に保つために、データの定期的な更新を設定することができます。|
| ![Item 9.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-09-red-30x30.png) | 組織のプライベートネットワーク内に存在するデータソースに接続するには、データの更新のために[オンプレミスデータゲートウェイ](../connect-data/service-gateway-onprem.md)が必要です。 |
| ![Item 10.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-10-red-30x30.png) | Power BI管理者は、Power BIサービスのアクティビティを監督・監視します。個人用のワークスペースは、共同作業や配布を目的としたワークスペースよりもはるかに管理範囲が狭いのが普通です。|

## Key points

パーソナルBIのシナリオについて、強調すべきポイントは以下の通りです。

### Choice of authoring tools

[Power BI Desktop](../fundamentals/desktop-what-is-desktop.md)は、クエリやモデル、Power BIレポートを開発するためのオーサリングツールです。ExcelのレポートとPower BIのページ分割レポート（シナリオ図には描かれていません）を別のツールで作成することも可能です。

### パーソナル ワークスペースへの依存

[個人用ワークスペース](../fundamentals/service-basic-concepts.md#workspaces)の使用は、*分析用のサンドボックス*のように考えることができます。多くの組織では、個人のコンテンツはほとんどガバナンスや正式な監視の対象になりません。しかし、コンテンツ作成者に[パーソナルBIで成功するためのガイドライン](powerbi-adoption-roadmap-content-delivery-scope.md#personal-bi)を教育することは賢明なことです。個人の分析に焦点を当てているため、個人のワークスペースで利用できる共有機能の使用は、この使用シナリオでは描かれていません。

> [重要]
> 個人用ワークスペースの使用を制限し、ミッションクリティカルなコンテンツが保存されていないことを確認してください。個人用ワークスペースに保存されたコンテンツを管理・編集できるのは一人だけなので、組織にとってリスクとなります。例えば、ある人が役割を変えたり、組織を離れたりしたときに、その人の後継者が引き続き作業できるようにコンテンツを移動させることは、混乱を招き、困難を伴うことがあります。

### Use of Power BI free license

Power BI無償ライセンスを持つユーザーは、他者との共有や共同作業がないことを意味する個人使用の場合、[Power BIサービスの特定の機能のみ](../consumer/end-user-features.md#feature-list)を利用できます。無料ライセンスを使用している場合、Power BIサービスにコンテンツを作成・公開する活動のほとんどは、個人のワークスペースに限定されます。

> [エンタープライズBI](powerbi-implementation-planning-useage-scenario-enterprise-bi.md)のシナリオでは、Power BIの無料ライセンスを持つユーザーが、プレミアム容量でホストされているコンテンツを閲覧する方法を説明しています。

### Gateway setup

通常、データゲートウェイは、プライベート組織ネットワークまたは仮想ネットワーク内に存在するデータソースにアクセスする際に必要となります。[オンプレミスのデータゲートウェイ](../connect-data/service-gateway-onprem.md)は、Power BIデスクトップのファイルがPower BIサービスに公開されると関係してきます。ゲートウェイの目的は、[インポートしたデータのリフレッシュ](../connect-data/refresh-data.md)、または[ライブ接続](../connect-data/desktop-directquery-about.md#live-connections)や[DirectQuery](../connect-data/desktop-directquery-about.md)のデータセットを照会するレポートの表示の2つです（シナリオ図には描かれていません）。

> 個人モードのデータ・ゲートウェイは、個人ユーザーのマシンにインストールされることがほとんどです。したがって、パーソナル・モードのデータ・ゲートウェイは、個人のBI使用シナリオに最も適しています。組織によっては、個人がデータゲートウェイをインストールすることが制限されている場合があります。その場合、コンテンツ作成者は、標準モードのデータゲートウェイ（通常、ITによって設定および管理されます）を使用することができます。

### Information protection

[情報保護](powerbi-adoption-roadmap-system-oversight.md#information-protection)ポリシーは、Power BIサービス内のコンテンツに適用することができます。組織によっては、個人のワークスペース内であっても、感度ラベルの付与を義務付ける[必須ラベルポリシー](../admin/service-security-sensitivity-label-mandatory-label-policy.md)があります。

### System oversight

[アクティビティログ](../admin/service-admin-auditing.md)は、Power BIサービスで発生したユーザーの活動を記録し、個人のワークスペースにまでおよびます。Power BI管理者は、収集されたアクティビティログデータを使用して[監査](powerbi-adoption-roadmap-system-oversight.md#auditing)を行い、使用パターンの理解やリスクのある活動の検出に役立てることができます。監査とガバナンスの要件は、一般的にパーソナルBIのシナリオではそれほど厳しくありません。

## Next steps

本連載の[次回](powerbi-implementation-planning-useage-scenario-team-bi.md)では、チームBIの使用シナリオで、小規模チームのコラボレーションについて学びます。
