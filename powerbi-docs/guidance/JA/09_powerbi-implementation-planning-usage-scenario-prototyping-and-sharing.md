---
title: "Power BI usage scenarios: Prototyping and sharing"
description: "Learn how Power BI prototyping and sharing is about rapid exploration of user requirements."
author: peter-myers
ms.author: v-petermyers
ms.reviewer: maroche
ms.service: powerbi
ms.subservice: powerbi-resource
ms.topic: conceptual
ms.date: 02/07/2022
---

# Power BI usage scenarios: Prototyping and sharing

[！INCLUDE [powerbi-implementation-planning-context](includes/powerbi-implementation-planning-context.md)] を参照してください。

Power BI採用ロードマップ](powerbi-adoption-roadmap-overview.md)に記載されているように、探索、実験、そして少人数のユーザーから有用なフィードバックを得ることが、[ソリューション採用のフェーズ1](powerbi-adoption-roadmap-maturity-levels.md#solution-adoption-phases)の目的です。

プロトタイプ（概念実証（POC））とは、未知の問題に対処し、リスクを軽減することを目的としたPower BIソリューションのことです。このソリューションは、開発の繰り返しの中でフィードバックを得るために他の人と共有されることがあります。このソリューションは、一時的で短期間のソリューションである場合もあれば、最終的に完全に検証されてリリースされるソリューションに発展する場合もあります。プロトタイプの作成は、[部門別BI](powerbi-implementation-planning-useage-scenario-departmental-bi.md)と[企業別BI](powerbi-implementation-planning-useage-scenario-enterprise-bi.md)のシナリオでよく行われます(また、[チーム別BI](powerbi-implementation-planning-useage-scenario-team-bi.md)のシナリオでも行われることがあります)。

プロトタイプの作成は、セルフサービスBIの開発作業の中で自然に行われることが多いです。また、プロトタイプは、具体的な「目標と範囲」(powerbi-migration-proof-of-concept.md#set-poc-goals-and-scope)を持った小さなプロジェクトである場合もあります。

> 注意】 > プロトタイプ作成と共有のシナリオは、セルフサービスBIシナリオの一つです。セルフサービスシナリオの完全なリストは、[Power BI使用シナリオ](powerbi-implementation-planning-useage-scenario-overview.md)の記事を参照してください。
> 簡潔にするために、[コンテンツコラボレーションと配信シナリオ](powerbi-implementation-planning-use-scenario-overview.md#content-management-and-deployment-scenarios)のトピックで説明されているいくつかの側面は、この記事ではカバーされていません。完全にカバーするには、まずそれらの記事をお読みください。

## Scenario diagram

次の図は、プロトタイピング活動をサポートするための最も一般的なユーザーアクションとPower BIコンポーネントのハイレベルな概要を示しています。ここでは、インタラクティブなプロトタイピングセッションでのPower BI Desktopの使用に焦点を当てています。また、サブジェクト・マター・エキスパートからの追加フィードバックが必要な場合は、Power BIサービスでの共有にも焦点を当てています。

![](https://docs.microsoft.com/en-us/power-bi/guidance/media/powerbi-implementation-planning-usage-scenario-prototyping-and-sharing/usage-scenario-prototyping-and-sharing-inline.png)

画像は、ユーザーの要求を迅速に探ることを目的とした、プロトタイピングと共有の図です。図中の項目は、以下の表で説明されています。

シナリオ・ダイアグラムでは、次のようなユーザー・アクション、ツール、機能が描かれています。

| **Item** | **Description** |
| --- | --- |
| ![Item 1.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-01-red-30x30.png) | Power BIコンテンツクリエーターは、Power BI Desktopを使ってBIソリューションを開発します。 |
| ![Item 2.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-02-red-30x30.png) | Power BI Desktopは、1つまたは複数のデータソースからデータに接続します。複数のソースを組み合わせたクエリやデータマッシュアップは、[Power Query Editor](/power-query/power-query-what-is-power-query)で開発します。 |
| ![Item 3.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-03-red-30x30.png) | データモデルの開発とレポートの作成は、Power BI Desktopで行います。その目的は、データを視覚的な文脈で表現することで、チームメンバーがデータの意味や意義を理解できるようにすることです。 |
| ![Item 4.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-04-red-30x30.png) | インタラクティブなプロトタイピングセッションで、サブジェクト・マター・エキスパートがフィードバックを行う。主体的な専門家（および他のチームメンバー）からのフィードバックに基づいて、コンテンツ制作者はBIソリューションに直接、反復的な改善を行います。 |
| ![Item 5.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-05-red-30x30.png) | 必要に応じて、コンテンツ作成者はPower BIデスクトップファイル（.pbix）を[Power BI Service](../fundamentals/power-bi-service-overview.md)に公開します。プロトタイピングソリューションのPower BIサービスへの公開は任意です。 |
| ![Item 6.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-06-red-30x30.png) | このコンテンツは、プロダクションではない[ワークスペース](../collaborate-share/service-new-workspaces.md)に公開されます。このワークスペースの主な目的は、チームメンバーによるレビューを可能にする開発エリアを提供することです。 |
| ![Item 7.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-07-red-30x30.png) | 個々のレポートを同僚と共有して、レポート（およびその基礎となるデータ）に対する読み取り専用の権限を付与することができます。[共有操作](../collaborate-share/service-share-dashboards.md)は、共有リンクまたは直接アクセスによる共有で行うことができます。共有は、フィードバックプロセスの間に一時的なアクセスを提供するプロトタイピングソリューションに有利な場合があります。|
| ![Item 8.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-08-red-30x30.png) | 組織内のプライベートネットワークに存在するデータソースに接続するためには、データリフレッシュのためにオンプレミスのデータゲートウェイが必要です。 |
| ![Item 9.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-09-red-30x30.png) | Power BI管理者は、Power BIサービスのアクティビティを監督・監視します。開発ワークスペース（非本番およびプロトタイピングソリューションを含む）は、通常、本番ワークスペースよりもはるかに少ない範囲で管理されています。 |

## Key points

試作と共有のシナリオについて、強調すべきポイントは以下の通りです。

### Interactive prototyping sessions

インタラクティブなプロトタイピングセッションは、ユーザー要件の調査、計算の検証、ビジュアルレイアウトのニーズの明確化、ユーザーエクスペリエンスの検証、レポート表示の確認など、即時のフィードバックを得るために有効です。Power BI Desktopは、サブジェクト・マター・エキスパートとインタラクティブに行うプロトタイピング・セッションで使用します。

### Power BI service

プロトタイピングソリューションのPower BIサービスへの公開はオプションです。フィードバックや意思決定のために予備的な結果を共有する必要がある場合に役立ちます。

> ヒント
> プロトタイプソリューションは、消費者が非生産的なソリューションに対して適切な期待を持てるように、他の生産的なコンテンツから明確に分離する必要があります。例えば、プロトタイプレポートの消費者は、そのレポートにすべてのデータが含まれていたり、スケジュール通りに更新されたりすることを期待していないかもしれません。プロトタイプレポートは、完全に検証され、最終化され、本番のワークスペースに公開されるまでは、ビジネス上の意思決定に使用すべきではありません。

### Workspace

このシナリオでは、小規模な[チームBI](powerbi-implementation-planning-useage-scenario-team-bi.md)のコラボレーションシナリオで作業するため、開発用の[ワークスペース](../collaborate-share/service-new-workspaces.md)が適切です([個人BI](powerbi-implementation-planning-useage-scenario-personal-bi.md)で説明した個人用のワークスペースではありません)。ソリューションが完成し、完全にテストされると、（[セルフサービス・コンテンツ・パブリッシング](powerbi-implementation-planning-use-scenario-self-service-content-publishing.md)シナリオで説明されているように）本番用のワークスペースに迅速に移行できます。

### Sharing reports and dashboards

シナリオ図では、[共有](../collaborate-share/service-share-dashboards.md)を直接受信者に渡しています（[ワークスペースの役割](../collaborate-share/service-roles-new-workspaces.md)や[Power BI アプリ](../collaborate-share/service-create-distribute-apps.md#publish-your-app)を使用するのではなく）。共有機能の使用は、同僚が非公式な方法で密接に協力するコラボレーションシナリオに適しています。このような状況では、プロトタイプ化されたソリューションをレビューしてフィードバックを提供する必要のある少数の同僚に限定されるため、共有機能は便利です。

> 個々のアイテムの共有は、あまり頻繁に行わないようにしてください。共有はワークスペース内の個々のアーティファクトごとに設定されるため、メンテナンスが面倒になり、エラーのリスクも高まります。共有の代わりに有効なのは、[ワークスペースの役割](../collaborate-share/service-roles-new-workspaces.md)を使うことです（[チームBI](powerbi-implementation-planning-useage-scenario-team-bi.md)のシナリオで説明しています）。ワークスペースの役割は、同僚がワークスペース内の*すべてのアーティファクト*にアクセスする必要がある場合に最適です。

### Gateway setup

通常、データゲートウェイは、プライベート組織ネットワークまたは仮想ネットワーク内に存在するデータソースにアクセスする際に必要となります。[オンプレミスのデータゲートウェイ](../connect-data/service-gateway-onprem.md)は、Power BIデスクトップのファイルがPower BIサービスに公開されると関係してきます。ゲートウェイの2つの目的は、[インポートされたデータのリフレッシュ](../connect-data/refresh-data.md)、またはライブ接続や[DirectQuery](../connect-data/desktop-directquery-about.md)データセットを照会するレポートの表示です（シナリオ図には描かれていません）。

> [! NOTE]
> チーム、部門、企業のBIシナリオでは、*[パーソナルモード](../connect-data/service-gateway-personal-mode.md#on-premises-data-gateway-vs-on-premises-data-gateway-personal-mode)*のゲートウェイよりも、*スタンダードモード*の集中型[データゲートウェイ](../connect-data/service-gateway-personal-mode.md)*のゲートウェイを強く推奨します。スタンダード・モードでは、データ・ゲートウェイはライブ接続とDirectQueryオペレーション（スケジュールされたデータ・リフレッシュ・オペレーションに加えて）をサポートします。

### System oversight

[アクティビティログ](../admin/service-admin-auditing.md)は、Power BIサービスで発生したユーザーの活動を記録します。Power BI管理者は、収集されたアクティビティログデータを使用して[監査](powerbi-adoption-roadmap-system-oversight.md#auditing)を行い、使用パターンの理解やリスクのあるアクティビティの検出に役立てることができます。監査やガバナンスの要件は、一般的にプロトタイピングや[パーソナルBI](powerbi-implementation-planning-useage-scenario-personal-bi.md)シナリオではそれほど厳しくありません。

## Next steps

Power BIの導入判断に役立つ他のシナリオについては、[Power BI利用シナリオ](powerbi-implementation-planning-useage-scenario-overview.md)の記事をご覧ください。
