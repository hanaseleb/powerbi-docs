---
title: "Power BI usage scenarios: Self-service data preparation"
description: "Learn how Power BI self-service data preparation is about using dataflows to centralize data cleansing and transformation work."
author: peter-myers
ms.author: v-petermyers
ms.reviewer: maroche
ms.service: powerbi
ms.subservice: powerbi-resource
ms.topic: conceptual
ms.date: 02/07/2022
---

# Power BI usage scenarios: Self-service data preparation

[!INCLUDE [powerbi-implementation-planning-context](includes/powerbi-implementation-planning-context.md)]

データ準備（ETL：Extract、Transform、Loadの頭文字）は、ソースデータの品質や構造に応じて、多くの作業を必要とします。セルフサービス・データ・プリパレーション」は、ビジネス・アナリストによるデータ・プリパレーション作業の再利用性に焦点を当てた利用シナリオです。このシナリオでは、データ準備作業をPower Query（個々のPower BI Desktopファイル内）からPower Query Online（[Power BIデータフロー](../transform-model/dataflows/dataflows-introduction-self-service.md)を使用）に移すことで、再利用性という目標を達成しています。ロジックを一元化することで、「Single Source of the Truth」を実現し、他のコンテンツ制作者が必要とする労力を軽減できます。

データフローは、Power BIサービス、Power Apps、Dynamics 365 Customer Insightsのいずれかのツールで、[Power Query Online](https://powerquery.microsoft.com/)を使用して作成します。Power BIで作成されたデータフローは、「*分析*データフロー」と呼ばれます。Power Appsで作成するデータフローは、[2つのタイプ](/power-query/dataflows/understanding-differences-between-analytical-standard-dataflows)のいずれかになります。*「標準」または「分析」*です。このシナリオは、Power BIサービス内で作成・管理されるPower BIデータフローの使用のみを対象としています。リアルタイムに近いレポーティングを可能にするストリーミングデータフローは、このシナリオの対象外です。

> セルフサービスのデータ準備シナリオは、セルフサービスBIシナリオの1つです。セルフサービスシナリオの完全なリストについては、[Power BI使用シナリオ](powerbi-implementation-planning-useage-scenario-overview.md)の記事を参照してください。
> 簡潔にするために、[コンテンツコラボレーションと配信シナリオ](powerbi-implementation-planning-useage-scenario-overview.md#content-management-and-deployment-scenarios)のトピックで説明されているいくつかの側面は、この記事ではカバーされていません。完全にカバーするには、まずそれらの記事をお読みください。

## Scenario diagram

次の図は、セルフサービスでのデータ準備をサポートする最も一般的なユーザーアクションとPower BIコンポーネントのハイレベルな概要を示しています。ここでは、複数のデータセットのデータソースとなるデータフローをPower Query Onlineで作成することに主眼を置いています。目標は、データフローで一度だけ行われるデータ準備を多くのデータセットで活用することです。

![](https://docs.microsoft.com/en-us/power-bi/guidance/media/powerbi-implementation-planning-usage-scenario-self-service-data-preparation/usage-scenario-self-service-data-preparation-inline.png)

画像は、データクレンジングや変換作業を一元化するためのデータフローについて、セルフサービスのデータ準備の図を示しています。この図の中の項目は、以下の表で説明されています。

シナリオ図では、以下のユーザーアクション、ツール、機能が描かれています。

| **Item** | **Description** |
| --- | --- |
| ![Item 1.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-01-red-30x30.png) | データフロー作成者は、Power BI [dataflow](../transform-model/dataflows/dataflows-introduction-self-service.md)内でテーブルのコレクションを開発します。再利用を目的としたデータフローの場合、作成者は、組織の境界を越えてユーザーをサポートする集中チーム（IT、エンタープライズBI、またはセンターオブエクセレンスなど）に所属するのが一般的です（必須ではありません）。|
| ![Item 2.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-02-red-30x30.png) | データフローは、1つまたは複数のデータソースからデータに接続します。 |
| ![Item 3.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-03-red-30x30.png) | データフローの開発には、[Power QueryのWebベース版](/power-query/power-query-what-is-power-query#wher-can-you-use-power-query)であるPower Query Onlineを使用します。Power Query Onlineの使い慣れたPower Queryのインターフェースは、Power BI Desktopからの移行を容易にします。 |
| ![Item 4.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-04-red-30x30.png) | データフローは、データフローの保存と保護に特化したワークスペースにアーティファクトとして保存されます。データを最新の状態に保つためには、データフローの更新スケジュールが必要です（シナリオ・ダイアグラムには描かれていません）。 |
| ![Item 5.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-05-red-30x30.png) | データセット作成者は、Power BI Desktopを使って新しいデータモデルを作成します。 |
| ![Item 6.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-06-red-30x30.png) | データフローは、新しいデータモデルのデータソースとなります。 |
| ![Item 7.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-07-red-30x30.png) | データセット作成者は、Power BI Desktop内のPower Queryの機能をフルに活用することができます。データフローのデータをさらに変換したり、データフローの出力をマージするために、オプションで追加のクエリステップを適用することができます。 |
| ![Item 8.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-08-red-30x30.png) |準備ができたら、データセット作成者は、データモデルを含むPower BI Desktopファイル（.pbix）をPower BIサービスに公開します。データセットの更新は、データフローとは別に管理されます（シナリオ図には描かれていません）。 |
| ![Item 9.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-09-red-30x30.png) | このデータフローは、異なるワークスペースに存在する他のデータセットのデータソースとして再利用することができます。 |
| ![Item 10.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-10-red-30x30.png) | Power BIの管理者は、Adminポータルで設定を管理します。 |
| ![Item 11.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-11-red-30x30.png) | 管理ポータルでは、Power BI管理者は、[Azure接続](../admin/service-admin-portal.md#azure-connections)を設定して、データフローデータをAzure Data Lake Storage Gen2(ADLS Gen2)アカウントに保存することができます。設定には、テナントレベルのストレージアカウントの割り当てや、ワークスペースレベルのストレージ権限の有効化などがあります。 |
| ![Item 12.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-12-red-30x30.png) | デフォルトでは、データフローは、Power BI サービスが管理する内部ストレージを使用してデータを保存します。オプションとして、データフローが出力するデータを、組織の[ADLS Gen2](/azure/storage/blobs/data-lake-storage-introduction)アカウントに保存できます。このような保管方法は、*bring your own data lake*と呼ばれることもあります。データフローデータをデータレイクに保存するメリットは、他のBIツールからアクセスして消費できることです。 |
| ![Item 13.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-13-red-30x30.png) | ADLS Gen2のデータフローデータは、*filesystem*と呼ばれるPower BI固有のコンテナ内に保存されます。このコンテナー内には、 [ワークスペースごとにフォルダが存在する](/power-query/dataflows/What-is-the-cdm-storage-structure for-analytical-dataflows#whats-in-a-dataflow-folder.) が存在します。データフローごとにサブフォルダが作成され、テーブルごとにも作成されます。Power BIは、データフローのデータが更新されるたびに、スナップショットを生成します。スナップショットは、メタデータとデータファイルで構成される自己記述式です。 |
| ![Item 14.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-14-red-30x30.png) | その他のセルフサービスのデータセット作成者は、Power BI Desktopでデータフローをデータソースとして使用して新しいデータモデルを作成することができます。|
| ![Item 15.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-15-red-30x30.png) | Azure管理者は、組織のADLS Gen2アカウントの[permissions](../transform-model/dataflows/dataflows-azure-data-lake-storage-integration.md#prerequisites)を管理します。 |
| ![Item 16.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-16-red-30x30.png) | 組織内のプライベートネットワークに存在するデータソースに接続するためには、データリフレッシュのためにオンプレミスのデータゲートウェイが必要です。|
| ![Item 17.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-17-red-30x30.png) | Power BI管理者は、Power BIサービスの活動を監督・監視します。 |

## Key points

セルフサービスによるデータ準備のシナリオについては、以下のようなポイントが強調されています。

### Power BI dataflows

[Power BIのデータフロー](../transform-model/dataflows/dataflows-create.md)は、テーブル(以前は*エンティティ*と呼ばれていました)の集まりで構成されています。データフローを作成する作業はすべて[Power Query Online](https://powerquery.microsoft.com/)で行われ、[workspace](../collaborate-share/service-new-workspaces.md)に保存されます。

> [!NOTE] > 個人用ワークスペースではデータフローは作成できません。

### Support dataset creators

シナリオ図は、Power BIのデータフローを使用して、準備されたデータを他のセルフサービスのデータセット作成者に提供することを描いています。

> 注意
> データセットはデータフローをデータソースとして使用します。レポートはデータフローに直接接続することはできません。

Power BIデータフローを使用するメリットは以下の通りです。

- データセット作成者は、Power BI Desktopにある使い慣れたPower Queryインターフェースを使用します。
- データフローで定義されたデータ準備およびデータ変換ロジックは、一元化されているため何度でも再利用できます。
- データフローにデータ準備ロジックの変更を加えても、依存するデータモデルを更新する必要がない場合があります。カラムの削除や名前の変更、またはカラムのデータタイプの変更には、依存するデータモデルの更新が必要になります。
- 事前に準備されたデータは、Power BIのデータセット作成者が簡単に利用できます。データセット作成者が必要とする作業レベルは、データ準備作業がデータモデリング作業から *切り離されているため、軽減されます 
- データセット作成者がソースシステムに直接アクセスする必要が少なくなります。データフローのデータは、時間のスナップショットを表し、多くのデータセットで使用される場合、一貫性を促進する。
- データ準備ロジックをデータフローに切り離すことで、データセットのリフレッシュの成功率を高めることができる。データフローの更新が失敗した場合、データセットは最後に成功したデータフローの更新を使って更新されます。

> [! TIP]
> [star schema](star-schema.md)の設計原則を適用してデータフローテーブルを作成します。スタースキーマの設計は、Power BIデータセットの作成に適しています。また、データフローの出力を洗練させて、フレンドリーな名前を適用したり、特定のデータタイプを使用したりします。これらのテクニックは、依存するデータセットの一貫性を促進し、データセット作成者が行うべき作業を軽減するのに役立ちます。

### Dataset creator flexibility

Power BI Desktopでデータセット作成者が[データフローに接続する場合](../transform-model/desktop-connect-dataflows.md)、作成者はそのデータフローの出力を使用することに限定されません。また、Power Queryの全機能を利用することができます。この機能は、追加のデータ準備作業が必要な場合や、データをさらに変換する必要がある場合に便利です。

### Dataflow advanced features

Power BI Premiumを使用したデータフロー（[キャパシティ ライセンスまたは Premium Per User ライセンス](../transform-model/dataflows/dataflows-develop-solutions.md#solution) による）では、[高度な機能](../transform-model/dataflows/dataflows-premium-features.md) を使用できます。これらの機能は、企業内のデータ管理に非常に役立ちます（シナリオ図には描かれていません）。データフロー設計には、セルフサービスからエンタープライズ対応へとデータフローを進化させることができる、多くのテクニック、パターン、および[ベストプラクティス](../transform-model/dataflows/dataflows-best-practices.md)があります。

> [!NOTE]
> [上級機能](../transform-model/dataflows/dataflows-premium-features.md)の1つに、データフローのインクリメンタル・リフレッシュがあります。*データセット*のインクリメンタル リフレッシュはPower BI Proの機能ですが、*データフロー*のインクリメンタル リフレッシュはPremiumの機能です。

### Dataflow and dataset refresh

前述の通り、データフローはデータセットのためのデータソースです。ほとんどの場合、複数のデータ更新スケジュールが関係しています: 1つはデータフローのため、もう1つは各データセットのためです。また、プレミアム機能である[DirectQuery from the dataset to the dataflow](../transform-model/dataflows/dataflows-premium-features.md#use-directquery-with-dataflows-in-power-bi)を使用することも可能です（シナリオ・ダイアグラムには描かれていません）。

> [!Note]
> [Streaming dataflow](../transform-model/dataflows/dataflows-streaming.md)と呼ばれる別のタイプのデータフローがあります（シナリオ・ダイアグラムには描かれていません）。ストリーミングデータフローは、Power BIでほぼリアルタイムの分析を実現するための1つの手法です。

### Azure Data Lake Storage Gen2

Microsoft Azureでは、ADLS Gen2アカウントは、[階層的名前空間](/azure/storage/blobs/create-data-lake-storage-account)を有効にした特定のタイプのAzure Storageアカウントです。ADLS Gen2は、分析ワークロードを運用する上で、[パフォーマンス、管理、セキュリティ上の利点](/azure/storage/blobs/data-lake-storage-introduction)があります。デフォルトでは、Power BIのデータフローは、Power BIサービスが管理する内蔵のデータレイクアカウントである内部ストレージを使用します。オプションとして、組織のADLS Gen2アカウントに接続することで、組織独自のデータレイクを*bring*できます。

ここでは、組織のデータレイクアカウントを使用することのメリットを紹介します。

- Power BIのデータフローによって保存されたデータは、（オプションで）他のユーザーやプロセスがデータレイクからアクセスできます。これは、データフローの再利用がPower BI以外で発生する場合に役立ちます。たとえば、データはAzure Data Factoryによってアクセスできます。 - データレイク内のデータは、（オプションで）他のツールやシステムによって管理できます。この場合、Power BIはデータを管理するのではなく、データを消費できます（シナリオ図には描かれていません）。

### Tenant-level storage

管理ポータルの[Azure接続](../admin/service-admin-portal.md#azure-connections)セクションには、ADLS Gen2アカウントへの接続を設定する設定があります。この設定を行うことで、*bring your own data lake*が可能になります。設定すると、[ワークスペースがそのデータレイク・アカウントを使用するように設定される](../transform-model/dataflows/dataflows-azure-data-lake-storage-integration.md#connecting-to-an-azure-data-lake-gen-2-at-a-workspace-level)となります。

> [!重要]
> [Azure接続](../admin/service-admin-portal.md#azure-connections)を設定しても、Power BIテナントのすべてのデータフローがデフォルトでこのアカウントに保存されるわけではありません。内部ストレージではなく）明示的なストレージアカウントを使用するためには、各ワークスペースを特別に接続する必要があります。
> ワークスペースにデータフロー*を作成する前に、ワークスペースのAzure接続を*設定することが重要です。[Power BIデータセットのバックアップ](../admin/service-premium-backup-restore-dataset.md)にも同じAzureストレージアカウントが使用されます。

### Workspace-level storage

Power BIの管理者は、ワークスペースレベルのストレージ権限を許可する設定を行うことができます（管理ポータルの「Azure接続」セクションで）。この設定を有効にすると、[ワークスペース管理者がテナントレベルで定義されたものとは異なるストレージアカウントを使用できる](../transform-model/dataflows/dataflows-azure-data-lake-storage-integration.md#connecting-to-an-azure-data-lake-gen-2-at-a-workspace-level)ようになります。この設定を有効にすると、Azureで独自のデータレイクを管理している分散型の事業部ではとくに便利です。

> [! NOTE] > 管理ポータルの[ワークスペースレベルのストレージ許可](../admin/service-admin-portal.md#azure-connections)は、Power BIテナントのすべてのワークスペースに適用されます。

### Common Data Model format

ADLS Gen2アカウントのデータは、*[Common Data Model (CDM)]構造(/power-query/dataflows/What-is-the-cdm-storage-structure for-analytical-dataflows#what-is-the-common-data-model-storage-structure)*に格納されています。CDM構造とは、自己記述的なスキーマとデータをどのように格納するかを規定するメタデータフォーマットである。CDM構造は、多数のアプリケーションでデータを共有するために標準化されたフォーマットで、セマンティックな一貫性を実現します（シナリオ図には描かれていません）。

### Publish to separate workspaces

データフローを[ワークスペース](../collaborate-share/service-new-workspaces.md)に公開することには、依存するデータセットが保存されている場所とは別に、いくつかの利点があります。1つの利点は、誰がどのタイプのコンテンツを管理する責任があるのかが明確になることです（複数の人が異なる責任を負っている場合）。もう1つの利点は、コンテンツの種類ごとに特定のワークスペースの権限を割り当てることができることです。

> 個人用ワークスペースでは、データフローは作成できません。

### Gateway setup

通常、データゲートウェイは、プライベート組織ネットワークまたは仮想ネットワーク内に存在するデータソースにアクセスする際、必要となります。オンプレミスのデータゲートウェイ](../connect-data/service-gateway-onprem.md)は、Power BIデスクトップのファイルがPower BIサービスに公開されると関係してきます。ゲートウェイの2つの目的は、[インポートされたデータのリフレッシュ](../connect-data/refresh-data.md)、またはライブ接続や[DirectQuery](../connect-data/desktop-directquery-about.md)データセットを照会するレポートの表示です（シナリオ図には描かれていません）。

> [! NOTE] > チーム、部門、企業のBIシナリオでは、*[パーソナルモード](../connect-data/service-gateway-personal-mode.md#on-premises-data-gateway-vs-on-premises-data-gateway-personal-mode)*のゲートウェイよりも、*標準モード*の集中型[データゲートウェイ](../connect-data/service-gateway-personal-mode.md)*のゲートウェイを強く推奨します。スタンダード・モードでは、データ・ゲートウェイはライブ接続とDirectQueryオペレーション（スケジュールされたデータ・リフレッシュ・オペレーションに加えて）をサポートします。

### System oversight

アクティビティログ](../admin/service-admin-auditing.md)は、Power BIサービスで発生したユーザーの活動を記録します。Power BI管理者は、収集されたアクティビティログデータを使用して[監査](powerbi-adoption-roadmap-system-oversight.md#auditing)を行い、使用パターンや採用状況の把握に役立てることができます。アクティビティログは、ガバナンスの取り組み、セキュリティ監査、コンプライアンス要件をサポートするためにも有用です。セルフサービスのデータ準備シナリオでは、データフローの使用状況を追跡することがとくに役立ちます。

## Next steps

Power BIの導入判断に役立つ他のシナリオについては、[Power BI使用シナリオ](01_powerbi-implementation-planning-usage-scenario-overview.md)の記事をご覧ください。
