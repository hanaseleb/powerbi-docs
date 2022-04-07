---
title: "Power BI usage scenarios: Departmental BI"
description: "Learn how Power BI departmental BI is about business unit content distribution."
author: peter-myers
ms.author: v-petermyers
ms.reviewer: maroche
ms.service: powerbi
ms.subservice: powerbi-resource
ms.topic: conceptual
ms.date: 02/07/2022
---

# Power BI usage scenarios: Departmental BI

[！INCLUDE [powerbi-implementation-planning-context](includes/powerbi-implementation-planning-context.md)] を参照してください。

[Power BI導入ロードマップ](powerbi-adoption-roadmap-content-delivery-scope.md#departmental-bi)に記載されているように、*departmental BI*は、より多くのユーザーにコンテンツを配信することに焦点を当てています。これらのユーザーは通常、部門やビジネスユニットのメンバーです。

チームが大きくなると、すべてのレポートを配布するためにワークスペースを効果的に使用することは現実的ではなくなります（[チームBI](powerbi-implementation-planning-use-scenario-team-bi.md)のシナリオで説明しています）。大規模な部門別BIシナリオを処理するためのより効果的な方法は、ワークスペースをコラボレーションに使用し、ワークスペースのコンテンツを消費者にアプリとして配布することです。

> [!NOTE] > 4つの*コンテンツのコラボレーションと配信*の使用シナリオがあり、それらは互いに積み重なっています。部門別BIシナリオは、4つのシナリオのうちの3番目のシナリオです。すべてのシナリオのリストは、[Power BI usage scenarios](powerbi-implementation-planning-use-scenario-overview.md)の記事にあります。

## Scenario diagram

次の図は、部門別BIをサポートする最も一般的なユーザーアクションとPower BIコンポーネントのハイレベルな概要を描いています。ここでは、多くの消費者にコンテンツを配信するためにPower BIアプリを使用することに主眼を置いています。

![](https://docs.microsoft.com/en-us/power-bi/guidance/media/powerbi-implementation-planning-usage-scenario-departmental-bi/usage-scenario-departmental-bi-inline.png)

イメージは、事業部のコンテンツ配信に関する部門BⅠの図を示しています。この図の中の項目は、下の表に記載されています。

シナリオ図では、以下のようなユーザーのアクション、ツール、機能が描かれています。

| **Item** | **Description** |
| --- | --- |
| ![Item 1.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-01-red-30x30.png) | Power BIのコンテンツ制作者は、Power BI Desktopを使ってBIソリューションを開発します。部門別BIのシナリオでは、クリエイターは、分散したチーム、部門、またはビジネスユニット内で作業するのが一般的です。|
| ![Item 2.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-02-red-30x30.png) | Power BI Desktopは、1つまたは複数のデータソースからデータに接続します。クエリや、複数のソースを組み合わせたデータマッシュアップは、Power Query Editorで開発します。|
| ![Item 3.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-03-red-30x30.png) | データモデルの開発とレポートの作成は、Power BI Desktopで行います。部門別BIソリューションでは、データを視覚的な文脈で表現することで、同僚がデータの意味や意義を理解できるようにすることを目的としている。|
| ![Item 4.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-04-red-30x30.png) | 準備ができたら、コンテンツ作成者はPower BI Desktopファイル（.pbix）をPower BIサービスに公開します。|
| ![Item 5.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-05-red-30x30.png) | コンテンツは、ワークスペースに公開されます。ワークスペースの主な目的は、コンテンツの作成、管理、検証を担当する人々にコラボレーションエリアを提供することです。 |
| ![Item 6.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-06-red-30x30.png) | 一部またはすべてのレポートやダッシュボードは、Power BIアプリとして公開されます。このアプリの目的は、消費者が使いやすい方法で閲覧できるように、関連するコンテンツのセットを提供することです。|
| ![Item 7.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-07-red-30x30.png) | Power BI アプリのユーザーには、読み取り専用の権限が割り当てられます。アプリのパーミッションは、ワークスペースとは別に管理されます。|
| ![Item 8.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-08-red-30x30.png) | また、Power BIのモバイルアプリでは、アプリやワークスペースのコンテンツを閲覧することができます。 |
| ![Item 9.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-09-red-30x30.png) | Microsoft Teamsで頻繁に作業するユーザーは、管理や[Power BIコンテンツをTeamsで直接表示](.../collaborate-share/service-collaborate-microsoft-teams.md)が便利だと思うかもしれません。| ![項目10.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-10-red-30x30.png)| 管理者、メンバー、または貢献者の [ワークスペースの役割](../collaborate-share/service-roles-new-workspaces.md) に割り当てられたユーザーは、ワークスペースのコンテンツを公開および管理できます。 |
| ![Item 11.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-11-red-30x30.png) | データの定期的な更新は、Power BIサービスで設定され、インポートされたデータセットやデータフローのデータを常に最新の状態に保ちます。|
| ![Item 12.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-12-red-30x30.png) | 組織内のプライベートネットワークに存在するデータソースに接続するためには、データリフレッシュのためにオンプレミスのデータゲートウェイが必要です。 |
| ![Item 13.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-13-red-30x30.png) | その他のセルフサービスのコンテンツ作成者は、既存のデータセットを使用して新しいレポートを作成できます。Power BI Desktop、Excel、またはPower BI Report Builder（シナリオ図には描かれていません）を使用できます。このような形での[既存データセットの再利用](../connect-data/desktop-report-lifecycle-datasets.md)が強く推奨されています。|
| ![Item 14.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-14-red-30x30.png) | Power BI管理者は、Power BIサービスのアクティビティを監督・監視します。部門別のBIソリューションは、[チームBI](powerbi-implementation-planning-use-scenario-team-bi.md)ソリューションよりも多くのガバナンス要件が課せられますが、[エンタープライズBI](powerbi-implementation-planning-use-scenario-enterprise-bi.md)ソリューションよりも要件は少なくなります。 |

## Key points

部門別BIのシナリオについて、強調すべきポイントは以下の通りです。

### Source file storage

[Power BI Desktop](../fundamentals/desktop-what-is-desktop.md)は、クエリやモデル、インタラクティブなレポートを開発するためのオーサリングツールです。部門別BIでは、ソースのPower BI Desktopファイルを安全な共有場所に保存することが重要です。OneDrive for BusinessやSharePoint（シナリオ図には描かれていません）などの場所が便利です。共有ライブラリは、セキュリティが確保され、同僚が簡単にアクセスでき、バージョン管理機能も組み込まれています。

BIソリューションの共同管理に異なるスキルセットを持つ複数の人が関わっている場合は、モデルとレポートを別々のPower BI Desktopファイルに分離することを検討してください（[マネージドセルフサービスBI](powerbi-implementation-planning-use-scenario-managed-self-service-bi.md)のシナリオで説明しています）。このアプローチは、データセットの再利用を促し、Power BI Desktopファイルを編集している人を交互に変え続けるよりも効率的です。例えば、ある人がデータセットを編集している間に、別の人がレポートを編集しているような場合には、特に有効です。

### Workspaces

Power BI の [ワークスペース](../collaborate-share/service-create-the-new-workspaces.md) は、データセットやレポートなどの関連アーティファクトを保存する Power BI サービスの論理的なコンテナとして機能します。このシナリオでは1つのワークスペースを描いていますが、ワークスペース計画の要件をすべて満たすには、通常、複数のワークスペースが必要です。

[マネージドセルフサービスBI](powerbi-implementation-planning-use-scenario-managed-self-service-bi.md)のシナリオでは、別々のワークスペースの使用について説明しています。
### Power BI app publication

部門別BIでは、消費者へのコンテンツ配信には、[Power BIアプリ](../consumer/end-user-apps.md)が有効です（[チームBI](powerbi-implementation-planning-useage-scenario-team-bi.md)のシナリオで説明されている、ワークスペースへの直接アクセスではありません）。Power BIアプリは、関連するコンテンツのセットをユーザーフレンドリーなナビゲーションで表示するため、消費者にとって最高の体験を提供します。Power BIアプリは、より多くの多様な消費者がいる場合や、コンテンツ開発者がアプリの消費者と密接に連携していない場合に、とくに有効です。

### Power BI app permissions

Power BI アプリのユーザーには、アプリに対する読み取り専用の権限が与えられており、これらの権限はワークスペースとは別に管理されます。この追加レベルの柔軟性は、コンテンツを閲覧できる人を管理するのに便利です。

部門別BIの場合、ワークスペースへのアクセスを、コンテンツのオーサリング、開発、および品質保証の活動を担当する人に限定することは、ベスト プラクティスです。通常、ワークスペースへのアクセスを必要とするのは、純粋に少数の人だけです。消費者は、ワークスペースを開くのではなく、Power BIアプリを開くことでコンテンツにアクセスできます。

### Power BI user licenses

ワークスペースまたはPower BIアプリのすべてのコンテンツ作成者および消費者は、[Power BI ProまたはPower BI Premium Per User（PPU）ライセンス](https://powerbi.microsoft.com/pricing/)を持っている必要があります。

> [!!! NOTE] > Power BI ProまたはPPUライセンスの要件には、1つの例外があります。ワークスペースがPremium容量に割り当てられている場合、Power BI無料ライセンスのユーザー（適切な権限を持つ）は、ワークスペース（および/またはアプリ）のコンテンツを表示できます。この方法は、[enterprise BI](powerbi-implementation-planning-use-scenario-enterprise-bi.md)のシナリオで説明されています。

### Reuse existing datasets

既存のデータセットを再利用することは、チームのコラボレーションにとって重要です。それは、「単一の真実のバージョン」を促進するのに役立ちます。少数のデータセット作成者が多数のレポート作成者をサポートする場合は、とくに重要です。Power BI Desktopの[ライブ接続](../connect-data/desktop-report-lifecycle-datasets.md)を使えば、レポートを既存のデータセットに接続することができ、別のデータセットを作成する必要がありません。また、ユーザーがExcelレポートを作成したい場合は、[Analyze in Excel](../collaborate-share/service-analyze-in-excel.md) 機能を使用できます。データセットへの接続性を維持することは、データをExcelにエクスポートするよりも望ましいことです。

- 重複したデータセットの作成を避けることができる
- データや計算に一貫性がなくなるリスクを減らすことができる
- Power BIサービスに保存されているデータセットとの接続を維持したまま、ビジュアル内のすべてのスライス、ダイシング、ピボット機能をサポートすることができる。

既存のデータセットにアクセスするには、コンテンツ作成者がそのデータセットの[ビルド許可]（../connect-data/service-datasets-build-permissions.md）を持っている必要があります。これは、ユーザーが[ワークスペースの役割](../collaborate-share/service-roles-new-workspaces.md)（コントリビューター以上）に割り当てられたときに直接または間接的に付与されるか、Power BIアプリの公開やアーティファクトの共有時に付与されます。[マネージドセルフサービスBI](powerbi-implementation-planning-useage-scenario-managed-self-service-bi.md)シナリオでは、共有データセットの再利用についてさらに検討しています。

### Gateway setup

通常、データゲートウェイは、プライベート組織ネットワークまたは仮想ネットワーク内に存在するデータソースアクセスするさいに必要となります。[オンプレミスのデータゲートウェイ](../connect-data/service-gateway-onprem.md)は、Power BIデスクトップのファイルがPower BIサービスに公開されると関係してきます。ゲートウェイの2つの目的は、[インポートされたデータのリフレッシュ](../connect-data/refresh-data.md)、またはライブ接続や[DirectQuery](../connect-data/desktop-directquery-about.md)データセットを照会するレポートの表示です（シナリオ図には描かれていません）。

> [! NOTE]
> チーム、部門、企業のBIシナリオでは、*[パーソナルモード](../connect-data/service-gateway-personal-mode.md#on-premises-data-gateway-vs-on-premises-data-gateway-personal-mode)*のゲートウェイよりも、*標準モード*の集中型[データゲートウェイ](../connect-data/service-gateway-personal-mode.md)*のゲートウェイを強く推奨します。スタンダード・モードでは、データ・ゲートウェイはライブ接続とDirectQueryオペレーション（スケジュールされたデータ・リフレッシュ・オペレーションに加えて）をサポートします。

### System oversight

[アクティビティログ](../admin/service-admin-auditing.md)は、Power BIサービスで発生したユーザーの活動を記録します。Power BI管理者は、収集されたアクティビティログデータを使用して[監査](powerbi-adoption-roadmap-system-oversight.md#auditing)を行い、使用パターンや採用状況の把握に役立てることができます。また、アクティビティログは、ガバナンスの取り組み、セキュリティ監査、およびコンプライアンス要件をサポートするためにも有用です。

## Next steps

このシリーズの[次の記事](powerbi-implementation-planning-useage-scenario-enterprise-bi.md)では、エンタープライズBIシナリオにおける組織規模のコンテンツ配信について学びます。
