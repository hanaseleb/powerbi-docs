---
title: "Power BI usage scenarios: Managed self-service BI"
description: "Learn how Power BI managed self-service BI is about reuse of centralized shared datasets by other report creators."
author: peter-myers
ms.author: v-petermyers
ms.reviewer: maroche
ms.service: powerbi
ms.subservice: powerbi-resource
ms.topic: conceptual
ms.date: 02/07/2022
---

# Power BI usage scenarios: Managed self-service BI

[!INCLUDE [powerbi-implementation-planning-context](includes/powerbi-implementation-planning-context.md)]

[Power BI採用ロードマップ](powerbi-adoption-roadmap-content-ownership-and-management.md#managed-self-service-bi)に記載されているように、*マネージドセルフサービスBI*は、*コアでの規律*と*エッジでの柔軟性*を重視したブレンドされたアプローチを特徴としています。データアーキテクチャは、通常、中央のBI専門家からなる単一のチームによって維持され、レポート作成の責任は、部門またはビジネスユニット内の作成者にあります。

通常、データセット作成者よりもレポート作成者の方が多く存在します。これらのレポート作成者は、組織のどのエリアにも存在します。セルフサービス型のレポート作成者は、迅速にコンテンツを作成する必要のある場合が多いため、混合型のアプローチを採用することで、データセットの作成という追加の労力を必要とせず、タイムリーな意思決定をサポートするレポートの作成に集中できます。

> [! NOTE] > マネージドセルフサービスBIシナリオは、セルフサービスBIシナリオの最初のものです。セルフサービスBIシナリオの完全なリストは、[Power BI使用シナリオ](powerbi-implementation-planning-useage-scenario-overview.md)の記事を参照してください。 > > 簡潔にするために、[コンテンツコラボレーションと配信シナリオ](powerbi-implementation-planning-useage-scenario-overview.md#content-management-and-deployment-scenarios)のトピックで説明されているいくつかの側面は、この記事ではカバーされていません。完全にカバーするには、まずそれらの記事をお読みください。

## Scenario diagram

次の図は、管理されたセルフサービスBIをサポートする、最も一般的なユーザーアクションとPower BIコンポーネントのハイレベルな概要を描いています。主な目的は、多くのレポート作成者が一元化された共有データセットを再利用することです。そのために、このシナリオでは、モデル開発プロセスをレポート作成プロセスから切り離すことに焦点を当てます。

![](https://docs.microsoft.com/en-us/power-bi/guidance/media/powerbi-implementation-planning-usage-scenario-managed-self-service-bi/usage-scenario-managed-self-service-bi-inline.png)

画像はマネージドセルフサービスBⅠの図で、一元化された共有データセットを他のレポート作成者が再利用するというものです。図の中の項目は、下の表で説明されています。

シナリオ図では、以下のユーザーアクション、ツール、機能が描かれています。

| **Item** | **Description** |
| --- | --- |
| ![Item 1.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-01-red-30x30.png) | データセットの作成者は、Power BI Desktopを使用してモデルを開発します。再利用を目的としたデータセットの作成者は、組織の壁を越えてユーザーをサポートする集中チーム（IT、エンタープライズBI、センターオブエクセレンスなど）に所属しているのが一般的です（必須ではありません）。|
| ![Item 2.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-02-red-30x30.png) | Power BI Desktopは、1つまたは複数のデータソースからデータに接続します。|
| ![Item 3.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-03-red-30x30.png) | データモデルの開発は、Power BI Desktopで行われます。多くのセルフサービスのレポート作成者がデータソースとして使用するため、デザイン性の高い、ユーザーフレンドリーなモデルを作成するための努力がなされています。|
| ![Item 4.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-04-red-30x30.png) | 準備ができたら、データセット作成者は、モデルのみを含むPower BI Desktopファイル（.pbix）をPower BIサービスに公開します。|
| ![Item 5.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-05-red-30x30.png) | このデータセットは，共有データセットの保存と保護に特化したワークスペースに公開されています．このデータセットは再利用を目的としているので，[endorsed](../collaborate-share/service-endorse-content.md)となっています（必要に応じて認証または昇格されます）．また，データセットの再利用をさらに促すために，[discoverable](../collaborate-share/service-discovery.md)と表示されています．Power BIサービスの[lineage view](/collaborate-share/service-data-lineage.md)は、データセットに接続されているレポートなど、成果物間に存在する依存関係を追跡するために使用できます。 |
| ![Item 6.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-06-red-30x30.png) |[データセットハブでのデータセット発見](../connect-data/service-datasets-hub.md)が有効なのは、データセットが発見可能とマークされているからです。発見可能とは、データを探している他のPower BIコンテンツ作成者がデータセットハブでデータセットの存在を確認できるようにするものです。 |
| ![Item 7.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-07-red-30x30.png) | レポート作成者は、Power BIサービスのデータセットハブを使って、発見可能なデータセットを検索します。 |
| ![Item 8.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-08-red-30x30.png) | レポート作成者が権限を持っていない場合は、データセットの[構築権限](/connect-data/service-datasets-build-permissions.md)を要求できます。これにより、権限のある承認者にビルド権限を要求するワークフローが開始されます。 |
| ![Item 9.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-09-red-30x30.png) | レポート作成者は、Power BI Desktopを使用して新しいレポートを作成します。レポートは、共有データセットへの「ライブ接続」(../connect-data/desktop-report-lifecycle-datasets.md)を使用します。|
| ![Item 10.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-10-red-30x30.png) | レポートクリエーターは、Power BI Desktopでレポートを作成します。 |
| ![Item 11.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-11-red-30x30.png) | 準備ができたら、レポート作成者は、Power BI DesktopファイルをPower BIサービスに公開します。 |
| ![Item 12.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-12-red-30x30.png) | レポートは、レポートやダッシュボードの保存と保護に特化したワークスペースに公開されます。 |
| ![Item 13.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-13-red-30x30.png) | 公開されたレポートは、別のワークスペースに保存されている共有データセットに接続されたままになります。共有データセットを変更すると、そのデータセットに接続されているすべてのレポートに影響します。 |
| ![Item 14.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-14-red-30x30.png) | その他のセルフサービスのレポート作成者は、既存の共有データセットを使用して新しいレポートを作成することができます。レポート作成者は、Power BI Desktop、Power BI Report Builder、またはExcelの使用を選択できます。 |
| ![Item 15.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-15-red-30x30.png) | 組織内のプライベートネットワークに存在するデータソースに接続するためには、データリフレッシュのためにオンプレミスのデータゲートウェイが必要です。 |
| ![Item 16.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-16-red-30x30.png) | Power BI管理者は、Power BIサービスの活動を監督・監視します。 |

## Key points

マネージドセルフサービスBIのシナリオについて、強調すべきポイントは以下の通りです。

### Shared dataset

管理されたセルフサービスBI*を機能させるための重要な側面は、データセットの数を最小限にすることです。このシナリオでは、「単一バージョンの真実」の実現に役立つ[共有データセット](../connect-data/service-datasets-across-workspaces.md)について説明します。

> [!NOTE] > 簡単にするために、シナリオ図では共有データセットを1つだけ描いています。しかし、すべての組織データを1つのデータセットでモデル化することは、通常、現実的ではありません。極端な話、経験の浅いコンテンツ制作者がよくやるように、レポートごとに新しいデータセットを作ることもできます。マネージドセルフサービスBIの目標は、データセットの数を比較的少なくし、必要に応じて新しいデータセットを作成するという適切なバランスをとることです。

### Decouple dataset and reports

データセットとレポートが切り離されていると、労力と責任の分離が容易になります。共有データセットは、IT、BI、センターオブエクセレンスなどの集中チームが管理し、レポートはビジネスユニットのサブジェクトマターエキスパートが管理するのが一般的です。しかし、それは必須ではありません。例えば、このパターンは、再利用性を実現したいコンテンツ制作者であれば誰でも採用できます。

> [!NOTE] > 簡単にするために、データフローはシナリオ・ダイアグラムに描かれていません。データフローについては、[self-service data preparation](powerbi-implementation-planning-use-scenario-self-service-data-preparation.md)のシナリオを参照してください。

### Dataset endorsement

共有データセットは再利用を目的としているため、そのデータセットを[認定](../collaborate-share/service-endorsse-content.md)しておくと便利です。認証された*データセットは、そのデータが信頼できるものであり、組織の品質基準を満たしていることをレポート作成者に伝えます。プロモーションされた*データセットは、データセットの所有者が、そのデータは価値があり、他の人が使う価値があると信じていることを強調しています。

> [!TIP] > コンテンツを承認するために、一貫性があり、反復可能で、厳格なプロセスを持つことは、ベストプラクティスです。認証されたコンテンツは、データの品質が検証されていることを示す必要があります。また、変更管理規則に従い、正式なサポートを受け、完全に文書化されていなければなりません。認証されたコンテンツは厳格な基準に合格しているため、信頼性に対する期待が高くなります。

### Dataset discovery

[データセットハブ](../connect-data/service-datasets-hub.md)は、レポート作成者が組織内のデータセットを見つけ、探索し、利用するのに役立ちます。データセットの推奨に加えて、[データセットの発見を可能にする](../connect-data/service-datasets-hub.md#make-your-dataset-discoverable)ことは、データセットの再利用を促進するために重要です。発見可能なデータセットは、レポート作成者がデータを検索する際に、データセットハブに表示されます。

> 注意
> データセットが発見可能に設定されていない場合、Build権限を持つPower BIユーザーのみがデータセットを見つけることができます。

### Request dataset access

レポート作成者は、[datasets hub](../connect-data/service-datasets-hub.md)の中に、使用したいデータセットを見つけることができます。そのデータセットに対する構築許可を持っていない場合は、アクセスを要求できます。データセットの [request access setting](../connect-data/service-datasets-build-permissions.md#configure-how-users-request-build-permission) に応じて、データセットの所有者にメールが送信されるか、アクセスを要求している人にカスタム指示が提示されます。

### Live connection to the shared dataset

Power BI Desktopの[ライブ接続](../connect-data/desktop-report-lifecycle-datasets.md)は、レポートを既存のデータセットに接続します。ライブ接続では、Power BI Desktopのファイルに新しいデータモデルを作成する必要がありません。

> [!重要] > ライブ接続を使用する場合、レポート作成者が必要とするすべてのデータは、接続されたデータセット内に存在する必要があります。ただし、[カスタマイズ可能なマネージドセルフサービスBI](powerbi-implementation-planning-useage-scenario-customizable-managed-self-service-bi.md)のシナリオでは、データセットを追加のデータや計算で拡張する方法を説明しています。

### Publish to separate workspaces

データセットが保存されている場所とは異なるワークスペースにレポートを発行することには、いくつかの利点があります。

まず、どのワークスペースのコンテンツを誰が管理するのかが明確になります。次に、レポート作成者は、コンテンツをレポート用ワークスペースに発行する権限を持っています（ワークスペースの管理者、メンバー、またはコントリビューターのロールを介して）。しかし、彼らは特定のデータセットに対する読み取り権限と構築権限しか持っていません。この手法により、ビューアロールに割り当てられたユーザに対して、必要に応じて[行レベルセキュリティ（RLS）](../admin/service-admin-rls.md)を有効にできます。

> [!重要]
> Power BI Desktopレポートをワークスペースに発行すると、RLSロールは、ワークスペースでビューアーロールに割り当てられているメンバーに適用されます。ビューアーがデータセットに対するビルド権限を持っていても、RLSは適用されます。詳しくは、[Power BIのワークスペースでRLSを使う](../admin/service-admin-rls.md#using-rls-with-workspaces-in-power-bi)をご覧ください。

### Dependency and impact analysis

共有データセットが多くのレポートで使用される場合、それらのレポートは多くのワークスペースに存在する可能性があります。[lineage view](../collaborate-share/service-data-lineage.md)は、下流の依存関係を特定して理解するのに役立ちます。データセットの変更を計画するときは、まず [impact analysis](../collaborate-share/service-dataset-impact-analysis.md#perform-dataset-impact-analysis) を実行して、編集やテストが必要な依存性のあるレポートを理解します。

### Gateway setup

通常、データゲートウェイは、プライベート組織ネットワークまたは仮想ネットワーク内に存在するデータソースにアクセスする際に必要となります。オンプレミスの[データゲートウェイ](../connect-data/service-gateway-onprem.md)は、Power BI DesktopのファイルがPower BIサービスに公開されると関係してきます。ゲートウェイの2つの目的は、[インポートされたデータのリフレッシュ](../connect-data/refresh-data.md)、またはライブ接続や[DirectQuery](../connect-data/desktop-directquery-about.md)データセットを照会するレポートを表示することです。

> [! NOTE] > マネージドセルフサービスBIシナリオでは、*[パーソナルモード](../connect-data/service-gateway-personal-mode.md#on-premises-data-gateway-vs-on-premises-data-gateway-personal-mode)*のゲートウェイよりも、*標準モード*の集中型[データゲートウェイ](../connect-data/service-gateway-personal-mode.md)*の方が強く推奨されます。スタンダード・モードでは、データ・ゲートウェイはライブ接続とDirectQueryオペレーション（スケジュールされたデータ・リフレッシュ・オペレーションに加えて）をサポートします。
> 
### System oversight

[アクティビティログ](../admin/service-admin-auditing.md)は、Power BIサービスで発生したユーザーの活動を記録します。Power BI管理者は、収集されたアクティビティログデータを使用して[監査](powerbi-adoption-roadmap-system-oversight.md#auditing)を行い、使用パターンや採用状況の把握に役立てることができます。アクティビティログは、ガバナンスの取り組み、セキュリティ監査、コンプライアンス要件をサポートするためにも有用です。マネージドセルフサービスBIのシナリオでは、共有データセットの使用状況を追跡することが特に役立ちます。レポートとデータセットの比率が高ければ、データセットがうまく再利用されていることになります。

## 次のステップ

このシリーズの[次の記事](powerbi-implementation-planning-use-scenario-customizable-managed-self-service-bi.md)では、追加のタイプの要件を満たすために共有データセットをカスタマイズし、拡張する方法について学びます。
