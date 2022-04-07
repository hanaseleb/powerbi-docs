---
title: "Power BI usage scenarios: Team BI"
description: "Learn how Power BI team BI is about small team collaboration."
author: peter-myers
ms.author: v-petermyers
ms.reviewer: maroche
ms.service: powerbi
ms.subservice: powerbi-resource
ms.topic: conceptual
ms.date: 02/07/2022
---

# Power BI usage scenarios: Team BI

[!INCLUDE [powerbi-implementation-planning-context](includes/powerbi-implementation-planning-context.md)] 

価値あるBIソリューションができあがったら、今度は同僚とのコラボレーションです。目標は、[personal BI](powerbi-implementation-planning-use-scenario-personal-bi.md)のシナリオで達成できる以上の付加価値を提供することです。

[Power BI採用ロードマップ](powerbi-adoption-roadmap-content-delivery-scope.md#team-bi)に記載されているように、*team BI*は、密接に協力し合う少人数のチームに焦点を当てています。非公式な方法でお互いにコラボレーションし、コンテンツを共有することは、通常、チームBIの主要な目的です（より正式なコンテンツの配信は、[部門BI](powerbi-implementation-planning-use-scenario-departmental-bi.md)と[エンタープライズBI](powerbi-implementation-planning-use-scenario-enterprise-bi.md)のシナリオでカバーされています）。

親しい同僚と仕事をする場合、小規模なチームのコラボレーションは、単にワークスペース内で行うことができます。ワークスペースは、小規模なチームのメンバーが非公式にコンテンツを閲覧する方法と考えることができます（Power BIアプリを公開するという形式をとらずに、これは[部門別BI](powerbi-implementation-planning-use-scenario-departmental-bi.md)のシナリオで説明しています）。

> [! NOTE] > 4つの*コンテンツのコラボレーションと配信*の使用シナリオがあり、それらは互いに積み重なっています。チームBIシナリオは、4つのシナリオのうちの2番目のシナリオです。すべてのシナリオのリストは、[Power BI usage scenarios](powerbi-implementation-planning-useage-scenario-overview.md)の記事に記載されています。

## Scenario diagram

次の図は、チームBIをサポートする最も一般的なユーザーアクションとPower BIコンポーネントのハイレベルな概要を描いています。ここでは、少人数のチームコラボレーションに焦点を当てています。

![teambi](https://docs.microsoft.com/en-us/power-bi/guidance/media/powerbi-implementation-planning-usage-scenario-team-bi/usage-scenario-team-bi-expanded.png)

画像は、小規模なチームコラボレーションをテーマにしたチームB Iの図を示しています。図の中の項目は、下の表で説明されています。" lightbox="media/powerbi-implementation-planning-usage-scenario-team-bi/usage-scenario-team-bi-expanded.png" border="false":::

シナリオ図では、以下のようなユーザーのアクション、ツール、機能が描かれています。

| **Item** | **Description** |
| --- | --- |
| ![Item 1.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-01-red-30x30.png) | Power BIのコンテンツ制作者は、Power BI Desktopを使ってBIソリューションを開発します。チームBIのシナリオでは、クリエイターは、分散したチーム、部門、またはビジネスユニット内で作業するのが一般的です。 |
| ![Item 2.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-02-red-30x30.png) | Power BI Desktopは、1つまたは複数のデータソースからデータに接続します。クエリや、複数のソースを組み合わせたデータマッシュアップは、Power Query Editorで開発します。|
| ![Item 3.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-03-red-30x30.png) | データモデルの開発とレポートの作成は、Power BI Desktopで行います。チームBIソリューションでは、データを視覚的に配置することで、チームメンバーがデータの意味や意義を理解することを目的としています。|
| ![Item 4.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-04-red-30x30.png) | 準備ができたら、コンテンツ作成者はPower BI Desktopファイル（.pbix）をPower BIサービスに公開します。 |
| ![Item 5.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-05-red-30x30.png) | コンテンツは、ワークスペースに公開されます。その主な目的は、少人数のチームに情報を提供し、コラボレーションを可能にすることです。|
| ![Item 6.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-06-red-30x30.png) | [ワークスペースの役割](../collaborate-share/service-roles-new-workspaces.md) (ビューアー以上)に割り当てられたすべてのユーザーは、ワークスペース内のコンテンツを表示し、対話します。Webブラウザーを使用してPower BIサービスにサインインするという方法もあります。|
| ![Item 7.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-07-red-30x30.png) | 公開されたコンテンツの閲覧には、Power BIのモバイルアプリも利用できます。 |
| ![Item 8.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-08-red-30x30.png) | Microsoft Teamsで頻繁に仕事をするユーザーは、Power BIコンテンツを管理したり、[Teamsで直接表示するのが便利だと思うかもしれません](../collaborate-share/service-collaborate-microsoft-teams.md)。ユーザーは、Microsoft Teams用のPower BIアプリを使用したり、チームチャンネル内に埋め込まれたレポートを閲覧したりすることができます。また、ユーザー同士でプライベートチャットを行い、Teamsで直接通知を受け取ることもできます。|
| ![Item 9.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-09-red-30x30.png) | 管理者、メンバー、または貢献者の [ワークスペースの役割](.../collaborate-share/service-roles-new-workspaces.md) に割り当てられたユーザーは、ワークスペースのコンテンツを公開および管理できます。 |
| ![Item 10.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-10-red-30x30.png) | Power BIサービスでは、データリフレッシュのスケジュールを設定することで、データセットやデータフローにインポートされたデータを常に最新の状態に保つことができます。|
| ![Item 11.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-11-red-30x30.png) |組織内のプライベートネットワークに存在するデータソースに接続するためには、データリフレッシュのためにオンプレミスのデータゲートウェイが必要です。 |
| ![Item 12.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-12-red-30x30.png) |その他のセルフサービスのコンテンツ作成者は、既存のデータセットを使って新しいレポートを作成できます。Power BI Desktop、Excel、またはPower BI Report Builder（シナリオ図には描かれていません）を使用できます。このような形での[既存データセットの再利用](../connect-data/desktop-report-lifecycle-datasets.md)が強く推奨されています。 |
| ![Item 13.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-13-red-30x30.png) | Power BI管理者は、Power BIサービスのアクティビティを監督・監視します。チームBIソリューションは、[パーソナルBI](powerbi-implementation-planning-useage-scenario-personal-bi.md)よりも多くのガバナンス要件が課せられる可能性がありますが、[部門BI](powerbi-implementation-planning-useage-scenario-departmental-bi.md)や[エンタープライズBI](powerbi-implementation-planning-useage-scenario-enterprise-bi.md)よりは少ないかもしれません。 |

## Key points

チームBIのシナリオについて、強調したいポイントは以下の通りです。

### Source file storage

[Power BI Desktop](../fundamentals/desktop-what-is-desktop.md)は、クエリ、モデル、およびインタラクティブなレポートを開発するためのオーサリングツールです。チームBIではコラボレーションが重要視されるため、ソースのPower BI Desktopファイルを安全な共有場所に保存することが重要です。OneDrive for BusinessやSharePoint（シナリオ図には描かれていません）のような場所は、バージョン履歴が組み込まれており、ファイルの自動同期が可能なので便利です。共有ライブラリは、セキュリティが確保され、同僚が簡単にアクセスでき、バージョン管理機能も組み込まれています。

BIソリューションの共同管理に、異なるスキルセットを持つ複数の人が関わっている場合は、モデルとレポートを別々のPower BI Desktopファイルに分離することを検討してください（[マネージドセルフサービスBI](powerbi-implementation-planning-use-scenario-managed-self-service-bi.md)のシナリオで説明しています）。このアプローチは、データセットの再利用を促し、Power BI Desktopファイルを編集している人を交互に変え続けるよりも効率的です。例えば、ある人がデータセットを編集している間に、別の人がレポートを編集しているような場合には、特に有効です。

### Workspaces

Power BIの[ワークスペース](../collaborate-share/service-create-the-new-workspaces.md)は、データセットやレポートなどの関連アーティファクトを保存するためのPower BIサービスの論理的コンテナとして機能します。チームBIのシナリオでは、少数のユーザーがレポートを閲覧するだけでなく、コラボレーションのためにワークスペースを使用することが実用的で簡単です。Power BIアプリとしてのコンテンツの配布は、[部門別BI](powerbi-implementation-planning-useage-scenario-departmental-bi.md)のシナリオで説明しています。

### Workspace access and sharing

ワークスペースは、コンテンツを整理するだけでなく、セキュリティの境界を形成します。チームメンバがワークスペースに公開されているすべてのアーティファクトを編集または表示する必要がある場合は、ユーザをワークスペースの役割に割り当てます。4つの[ワークスペースの役割](../collaborate-share/service-roles-new-workspaces.md)（管理者、メンバー、貢献者、閲覧者）は、権限を過剰に提供することなく、セルフサービスのコンテンツ作成者と消費者の生産性をサポートします。

> また、ワークスペース・ユーザーは、個々のレポートを共有することができます（.../collaborate-share/service-share-dashboards.md）。共有によって、ワークスペースのロールが割り当てられていない人に読み取り専用のアクセスを与えることができます。しかし、多くのアーティファクトや多くのユーザーに対して設定するのは面倒なので、共有は制限するようにしてください。

### Power BI user licenses

ワークスペースで共同作業を行う場合、すべてのユーザーが[Power BI ProまたはPower BI Premium Per User（PPU）ライセンス](https://powerbi.microsoft.com/pricing/)を持っている必要があります。

> [!!! NOTE] > Power BI ProまたはPPUライセンスの要件には、1つの例外があります。ワークスペースがPremium容量に割り当てられている場合、Power BI無料ライセンスのユーザー（適切な権限を持つ）は、ワークスペース（および/またはPower BIアプリ）のコンテンツを表示できます。この方法は、[enterprise BI](powerbi-implementation-planning-use-scenario-enterprise-bi.md)のシナリオで説明されています。

### Reuse existing datasets

既存のデータセットを再利用することは、チームのコラボレーションにとって重要です。それは、「単一の真実のバージョン」を促進するのに役立ちます。少数のデータセット作成者が多数のレポート作成者をサポートする場合は、特に重要です。Power BI Desktopの[ライブ接続](../connect-data/desktop-report-lifecycle-datasets.md)を使えば、レポートを既存のデータセットに接続することができ、別のデータセットを作成する必要がありません。また、ユーザーがExcelレポートの作成を希望する場合は、[Analyze in Excel](../collaborate-share/service-analyze-in-excel.md)機能を使用することができます。このような接続方法は、データをExcelにエクスポートするよりも好ましいものです。

- 重複したデータセットの作成を避けることができる
- データや計算に一貫性がなくなるリスクを減らすことができる
- Power BIサービスに保存されているデータセットに接続されたまま、ビジュアル内のすべてのスライス、ダイシング、ピボット機能をサポートする。

既存のデータセットにアクセスするには、コンテンツ作成者がそのデータセットの[ビルド許可](../connect-data/service-datasets-build-permissions.md)を持っている必要があります。これは、ユーザーが[ワークスペースの役割](../collaborate-share/service-roles-new-workspaces.md)（コントリビューター以上）に割り当てられたときに直接または間接的に付与されるか、Power BIアプリの公開やアーティファクトの共有時に付与されます。[マネージドセルフサービスBI](powerbi-implementation-planning-useage-scenario-managed-self-service-bi.md)シナリオでは、共有データセットの再利用についてさらに検討しています。

### Power BI integration with Microsoft Teams

Microsoft Teamsのような最新のコラボレーション ツールを使用することで、ユーザーはデータに基づいた意思決定を行うことができます。Microsoft Teamsは、自然なワークフローの中でPower BIのコンテンツを閲覧しながら、データに関する共同討議をサポートします。より多くのコラボレーションオプションについては、[Microsoft TeamsでPower BIを使ったコラボレーション](../collaborate-share/service-collaborate-microsoft-teams.md)を参照してください。

### Gateway setup

通常、データゲートウェイは、プライベート組織ネットワークまたは仮想ネットワーク内に存在するデータソースにアクセスするさいに必要となります。[オンプレミスのデータゲートウェイ](../connect-data/service-gateway-onprem.md)は、Power BIデスクトップのファイルがPower BIサービスに公開されると関係してきます。ゲートウェイの2つの目的は、[インポートされたデータのリフレッシュ](../connect-data/refresh-data.md)、または[ライブ接続](../connect-data/desktop-directquery-about.md#live-connections)または[DirectQuery](../connect-data/desktop-directquery-about.md)のデータセット（シナリオ図には描かれていません）を照会するレポートの表示です。

> [! NOTE] > チーム、部門、企業のBIシナリオでは、*[パーソナルモード](../connect-data/service-gateway-personal-mode.md#on-premises-data-gateway-vs-on-premises-data-gateway-personal-mode)*のゲートウェイよりも、*スタンダードモード*の集中型[データゲートウェイ](../connect-data/service-gateway-personal-mode.md)*のゲートウェイを強く推奨します。スタンダード・モードでは、データ・ゲートウェイはライブ接続とDirectQueryオペレーション（スケジュールされたデータ・リフレッシュ・オペレーションに加えて）をサポートします。

### System oversight

[アクティビティログ](../admin/service-admin-auditing.md)は、Power BIサービスで発生したユーザーの活動を記録します。Power BI管理者は、収集されたアクティビティログデータを使用して[監査](powerbi-adoption-roadmap-system-oversight.md#auditing)を行い、使用パターンや採用状況の把握に役立てることができます。また、アクティビティログは、ガバナンスの取り組み、セキュリティ監査、およびコンプライアンス要件をサポートするためにも有用です。

## Next steps

本連載の[次回](powerbi-implementation-planning-useage-scenario-departmental-bi.md)では、部門別BI利用シナリオで、より多くの視聴者にコンテンツを配信する方法をご紹介します。
