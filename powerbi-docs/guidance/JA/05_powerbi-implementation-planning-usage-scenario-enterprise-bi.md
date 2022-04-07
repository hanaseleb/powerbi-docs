---
title: "Power BI usage scenarios: Enterprise BI"
description: "Learn how Power BI enterprise BI is about organization-wide content distribution at scale."
author: peter-myers
ms.author: v-petermyers
ms.reviewer: maroche
ms.service: powerbi
ms.subservice: powerbi-resource
ms.topic: conceptual
ms.date: 02/07/2022
---

# Power BI usage scenarios: Enterprise BI

[！INCLUDE [powerbi-implementation-planning-context](includes/powerbi-implementation-planning-context.md)]を参照してください。

[Power BI採用ロードマップ](powerbi-adoption-roadmap-content-delivery-scope.md#enterprise-bi)に記載されているように、*エンタープライズBI*は、コンテンツを作成・公開する著者の数が非常に少ないのに比べて、コンテンツ消費者の数が非常に多いことが特徴です。

エンタープライズBIと[部門別BI](powerbi-implementation-planning-useage-scenario-departmental-bi.md)のシナリオの違いは、[Power BI Premium capacity](../admin/service-premium-what-is.md)を使用することで、[Power BIの無料ライセンスを持っている消費者](../fundamentals/service-features-license-type.md)にコンテンツを広く配布できます。消費者には、組織内のユーザーだけでなく、組織外の[ゲストユーザー](whitepaper-azure-b2b-power-bi.md)も含まれます。

大規模なエンタープライズBIの導入では、中央集権的なアプローチを採用されることが多い。エンタープライズPower BIのコンテンツは、組織全体で広く使用されるために、中央のチームによって維持されるのが一般的です。コンテンツ管理を担当する集中チームは、通常、IT、BI、または[センターオブエクセレンス（COE）](powerbi-adoption-roadmap-center-of-excellence.md)です。

> 注意】 > 4つの*コンテンツのコラボレーションと配信*の使用シナリオがあり、それらは互いに積み重なっています。エンタープライズBIのシナリオは4つ目のシナリオです。すべてのシナリオのリストは、[Power BI usage scenarios](powerbi-implementation-planning-useage-scenario-overview.md)の記事にあります。

## Scenario diagram

次の図は、エンタープライズBIをサポートする最も一般的なユーザーアクションとPower BIコンポーネントのハイレベルな概要を描いています。このシナリオでは、Power BI Premiumの使用を含め、組織全体のコンテンツを大規模に配信することに重点を置いています。このシナリオでは、[Power BI ページネーションレポート](../paginated-reports/paginated-reports-report-builder-power-bi.md)の開発も描かれています。

![enterprise-bi](https://docs.microsoft.com/en-us/power-bi/guidance/media/powerbi-implementation-planning-usage-scenario-enterprise-bi/usage-scenario-enterprise-bi-inline.png)

画像は、組織規模でのコンテンツ配信を行うエンタープライズB Iの図を示しています。この図の中の項目は、下の表で説明されています。

シナリオ図では、以下のようなユーザーのアクション、ツール、機能が描かれています。

| **Item** | **Description** |
| --- | --- |
| ![Item 1.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-01-red-30x30.png) | Power BIコンテンツクリエーターは、Power BI Desktopを使用してBIソリューションを開発します。エンタープライズBIのシナリオでは、クリエーターは、組織の境界を越えてユーザーをサポートする集中チーム（IT、BI、またはCOEなど）のメンバーであることが一般的です。 |
| ![Item 2.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-02-red-30x30.png) | Power BI Desktopは、1つまたは複数のデータソースからデータに接続します。クエリや、複数のソースを組み合わせたデータマッシュアップは、Power Query Editorで開発します。|
| ![Item 3.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-03-red-30x30.png) | データモデルの開発とレポートの作成は、Power BI Desktopで行います。その目的は、データを視覚的な文脈で表現することで、同僚がデータの意味や意義を理解できるようにすることです。|
| ![Item 4.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-04-red-30x30.png) | 準備ができたら、コンテンツ作成者はPower BI Desktopファイル（.pbix）をPower BIサービスに公開します。|
| ![Item 5.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-05-red-30x30.png) | レポート作成者は、Power BI Report Builderを使用してページ分割されたレポートを作成します。|
| ![Item 6.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-06-red-30x30.png) | Power BI Report Builderは、1つまたは複数のデータソースタイプからデータを照会します。ページ分割されたレポートが作成され、高度にフォーマットされた印刷用レポートの要件を満たします。 |
| ![Item 7.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-07-red-30x30.png) | 準備ができたら、レポート作成者は、Power BIレポートビルダーファイル（.rdl）をPower BIサービスに公開します。|
| ![Item 8.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-08-red-30x30.png) | 複数のアーティファクトタイプを [プレミアムワークスペース](../collaborate-share/service-create-the-new-workspaces.md#premium-capacity-settings) に公開できます。このワークスペースのライセンスモードでは、ページネーションされたレポートがサポートされています。|
| ![Item 9.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-09-red-30x30.png) | エンタープライズBIのシナリオでは、（Premium Per Userではなく）[Premium capacity](../admin/service-premium-what-is.md)の使用が描かれています。これは、Power BIの無料ライセンスを持っている多くのコンテンツビューアーへのコンテンツ配信をサポートするための選択です。|
| ![Item 10](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-10-red-30x30.png) | 一部、またはすべてのレポートやダッシュボードは、[Power BIアプリ](../consumer/end-user-apps.md)として公開されます。このアプリの目的は、コンシューマーが使いやすい方法で閲覧できるように、関連するコンテンツのセットを提供することです。 |
| ![Item 11.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-11-red-30x30.png) | Power BI アプリのユーザーには、読み取り専用の権限が割り当てられます。アプリの権限は、ワークスペースとは別に管理されます。エンタープライズBIのシナリオでは、あらゆる種類のPower BIライセンス（無料、Power BI Pro、またはPPU）を持つユーザーをアプリのビューアーとして割り当てることができます。この機能は、ワークスペースに**Premium per capacity**のライセンスモードが割り当てられている場合にのみ適用されます（**Premium per user**または**Embedded**のライセンスモードが割り当てられている場合、無料ユーザーはワークスペースのコンテンツにアクセスできません）。 |
| ![Item 12.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-12-red-30x30.png) | Power BIのモバイルアプリでも、アプリやワークスペースのコンテンツを閲覧することができます。|
| ![Item 13.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-13-red-30x30.png) | Microsoft Teamsで頻繁に仕事をするユーザーは、TeamsでPower BIコンテンツを管理したり、[Power BIコンテンツをTeamsで直接見る](.../collaborate-share/service-collaborate-microsoft-teams.md)ことができて便利かもしれません。|
| ![Item 14.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-14-red-30x30.png) | 管理者、メンバー、コントリビューターのいずれかのワークスペースの役割を持つユーザーは、ワークスペースのコンテンツを公開および管理できます。|
| ![Item 15.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-15-red-30x30.png) | データの定期的な更新は、Power BIサービスで設定され、インポートされたデータセットやデータフローのデータを常に最新の状態に保ちます。|
| ![Item 16.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-16-red-30x30.png) | 組織内のプライベートネットワークに存在するデータソースに接続するためには、データリフレッシュのためにオンプレミスのデータゲートウェイが必要です。 |
| ![Item 17.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-17-red-30x30.png) | その他のセルフサービスのコンテンツ作成者は、既存のデータセットを使用して新しいレポートを作成できます。その際、Power BI Desktop、Excel、Power BI Report Builderのいずれかを使用できます。このような方法で既存のデータセットを再利用することが強く推奨されています。[マネージドセルフサービスBI](powerbi-implementation-planning-useage-scenario-managed-self-service-bi.md)シナリオでは、データセットの再利用についてさらに検討しています。|
| ![Item 18.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-18-red-30x30.png) | Power BI管理者は、Power BIサービスのアクティビティを監督・監視します。エンタープライズBIソリューションは、[チームBI](powerbi-implementation-planning-useage-scenario-team-bi.md)や[部門BI](powerbi-implementation-planning-useage-scenario-departmental-bi.md)ソリューションよりも厳しいガバナンス要件が課せられることが多いです。|

## Key points

エンタープライズBIのシナリオについて強調すべきポイントは以下の通りです。

### Choice of report authoring tools

ワークスペースのライセンスモードが**Premium**（Power BI capacityまたはPremium Per Userのいずれか経由）の場合、ページネーションされたレポートをワークスペースに公開できます。[Power BI Desktop](../fundamentals/desktop-what-is-desktop.md)は、高度にインタラクティブなレポートを開発するためのツールですが、[Power BI Report Builder](../paginated-reports/report-Builder-power-bi.md)は、ページネーションされたレポートを開発するためのツールです。ページネーションされたレポートを使用する場合については、[Power BIでページネーションされたレポートを使用する場合](report-paginated-or-power-bi.md)を参照してください。

Excelレポートは、PivotTableやPivotChartがレポート要件をよりよく満たす場合に、Power BIサービス（シナリオ図には描かれていません）に公開することもできます。

### Source file storage

エンタープライズBIでは、ソースのPower BI DesktopファイルとPower BI Report Builderファイルを安全な共有場所に保管することが重要です。OneDrive for BusinessやSharePoint（シナリオ図には描かれていません）などの場所が便利です。共有ライブラリは、セキュリティが確保され、同僚が簡単にアクセスでき、バージョン管理機能が組み込まれています。

BIソリューションの共同管理に異なるスキルセットを持つ複数の人が関わっている場合は、モデルとレポートを別々のPower BI Desktopファイルに分離することを検討してください（[マネージドセルフサービスBI](powerbi-implementation-planning-use-scenario-managed-self-service-bi.md)のシナリオで説明しています）。このアプローチは、データセットの再利用を促し、Power BI Desktopファイルを編集している人を交互に変え続けるよりも効率的です。例えば、ある人がデータセットを編集している間に、別の人がレポートを編集しているような場合には、特に有効です。

### Workspaces

Power BI の [ワークスペース](../collaborate-share/service-create-the-new-workspaces.md) は、データセットやレポートなどの関連アーティファクトを保存する Power BI サービスの論理的なコンテナとして機能します。このシナリオでは1つのワークスペースを描いていますが、ワークスペース計画の要件をすべて満たすには、通常、複数のワークスペースが必要です。

[マネージドセルフサービスBI](powerbi-implementation-planning-use-scenario-managed-self-service-bi.md)のシナリオでは、別々のワークスペースの使用について説明しています。

### Workspace license mode

ワークスペースのライセンスモードは、**Pro**、**Premium per user** (PPU)、**Premium per capacity**、または**Embedded**に割り当てることができます。この選択は、[機能の利用可能性](../fundamentals/service-features-license-type.md)や、ワークスペース内のコンテンツや関連するPower BIアプリにアクセスできるユーザーに影響を与えます。エンタープライズBIのシナリオでは、コンテンツの消費者が多数存在することがよくあります。そのため、**Premium per capacity**ライセンスモードを使用して、無料ライセンスを持つユーザーにコンテンツを配布することがコスト的に有効な場合があります。

### Power BI app publication

エンタープライズBIの場合、コンシューマーへのコンテンツ配信には、[Power BI app](../consumer/end-user-apps.md)が適しています（[team BI](powerbi-implementation-planning-useage-scenario-team-bi.md)のシナリオで説明されている、ワークスペースへの直接アクセスではなく）。Power BIアプリは、関連するコンテンツのセットをユーザーフレンドリーなナビゲーションで表示するため、消費者にとって最高の体験を提供します。Power BIアプリは、より多くの多様な消費者がいる場合や、コンテンツ開発者がアプリの消費者と密接に連携していない場合に、とくに有効です。

### Power BI app permissions

Power BIアプリのユーザーには、アプリに対する読み取り専用の権限が与えられており、これらの権限はワークスペースとは別に管理されます。この追加レベルの柔軟性は、コンテンツを閲覧できる人を管理するのに便利です。

エンタープライズBIでは、ワークスペースへのアクセスを、コンテンツのオーサリング、開発、および品質保証の活動を担当する人に限定することがベストプラクティスです。通常、ワークスペースへのアクセスを必要とするのは、純粋に少数の人だけです。コンシューマーは、ワークスペースを開くのではなく、Power BIアプリを開いてコンテンツにアクセスできます。

### Power BI無償ライセンスユーザーへのコンテンツ配信

Power BI 無料ライセンス（または Power BI Pro または PPU ライセンス）を持つユーザーは、アプリへのアクセスが許可されるか、ワークスペースがプレミアム容量に割り当てられていることを条件に、ワークスペースのロールに追加されるとコンテンツを表示できます。無料ライセンスのユーザーにコンテンツを配信する機能は、**Pro**、**Premium per user**、**Embedded**など、他のワークスペースのライセンスモードでは利用できません。

### Power BI Premium capacity license

このシナリオでは、P SKU（P1、P2、P3、P4、またはP5など）[容量ベースのライセンス](../admin/service-premium-faq.yml#what-is-power-bi-premium---)の使用について説明します。P SKUは、一般的なプロダクションシナリオに必要であり、本記事で紹介するエンタープライズBIシナリオに適しています。

### Manage lifecycle of content

一般的にエンタープライズBIソリューションでは、本番用コンテンツの安定性が求められます。そのためには、コンテンツをいつ、どのように本番環境にデプロイするかをコントロールすることが重要です。[デプロイメント・パイプライン](../create-reports/deployment-pipelines-overview.md)の使用については、[セルフサービス・コンテンツ・パブリッシング](powerbi-implementation-planning-use-scenario-self-service-content-publishing.md)のシナリオで説明されています。

### Reuse existing datasets

既存のデータセットを再利用することは、チームのコラボレーションにとって重要です。それは、「単一の真実のバージョン」を促進するのに役立ちます。少数のデータセット作成者が多数のレポート作成者をサポートする場合は、とくに重要です。Power BI Desktopの[ライブ接続](../connect-data/desktop-report-lifecycle-datasets.md)を使えば、レポートを既存のデータセットに接続することができ、別のデータセットを作成する必要がありません。また、ユーザーがExcelレポートを作成したい場合は、[Analyze in Excel](../collaborate-share/service-analyze-in-excel.md) 機能を使用できます。データセットへの接続性を維持することは、データをExcelにエクスポートするよりも望ましいことです。

- 重複したデータセットの作成を避けることができる - データや計算に一貫性がなくなるリスクを減らすことができる - Power BIサービスに保存されているデータセットとの接続を維持したまま、ビジュアル内のすべてのスライス、ダイシング、ピボット機能をサポートすることができる。

既存のデータセットにアクセスするには、コンテンツ作成者がそのデータセットの[ビルド許可](../connect-data/service-datasets-build-permissions.md)を持っている必要があります。これは、ユーザーが[ワークスペースの役割](../collaborate-share/service-roles-new-workspaces.md)（コントリビューター以上）に割り当てられたときに直接または間接的に付与されるか、Power BIアプリの公開やアーティファクトの共有時に付与されます。[マネージドセルフサービスBI](powerbi-implementation-planning-useage-scenario-managed-self-service-bi.md)シナリオでは、共有データセットの再利用についてさらに検討しています。

### Gateway setup

通常、データゲートウェイは、プライベート組織ネットワークまたは仮想ネットワーク内に存在するデータソースアクセスするさいに必要となります。[オンプレミスのデータゲートウェイ](../connect-data/service-gateway-onprem.md)は、Power BIデスクトップのファイルがPower BIサービスに公開されると関係してきます。ゲートウェイの2つの目的は、[インポートされたデータのリフレッシュ](../connect-data/refresh-data.md)、またはライブ接続や[DirectQuery](../connect-data/desktop-directquery-about.md)データセットを照会するレポートの表示です（シナリオ図には描かれていません）。

> [! NOTE] > チーム、部門、企業のBIシナリオでは、*[パーソナルモード](../connect-data/service-gateway-personal-mode.md#on-premises-data-gateway-vs-on-premises-data-gateway-personal-mode)*のゲートウェイよりも、*標準モード*の集中型[データゲートウェイ](../connect-data/service-gateway-personal-mode.md)*のゲートウェイを強く推奨します。スタンダード・モードでは、データ・ゲートウェイはライブ接続とDirectQueryオペレーション（スケジュールされたデータ・リフレッシュ・オペレーションに加えて）をサポートします。

### System oversight

[アクティビティログ](../admin/service-admin-auditing.md)は、Power BIサービスで発生したユーザーの活動を記録します。Power BI管理者は、収集されたアクティビティログデータを使用して[監査](powerbi-adoption-roadmap-system-oversight.md#auditing)を行い、使用パターンや採用状況の把握に役立てることができます。また、アクティビティログは、ガバナンスの取り組み、セキュリティ監査、およびコンプライアンス要件をサポートするためにも有用です。

## Next steps

このシリーズの[次の記事](powerbi-implementation-planning-useage-scenario-managed-self-service-bi.md)では、マネージドセルフサービスBIシナリオにおけるデータセットの再利用の重要性について詳しく説明しています。
