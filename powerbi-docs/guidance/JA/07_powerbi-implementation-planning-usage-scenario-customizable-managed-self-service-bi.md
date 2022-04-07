---
title: "Power BI usage scenarios: Customizable managed self-service BI"
description: "Learn how Power BI customizable managed self-service BI is about creating new specialized datasets by extending and personalizing existing datasets."
author: peter-myers
ms.author: v-petermyers
ms.reviewer: maroche
ms.service: powerbi
ms.subservice: powerbi-resource
ms.topic: conceptual
ms.date: 02/07/2022
---

# Power BI usage scenarios: Customizable managed self-service BI

[!INCLUDE [powerbi-implementation-planning-context](includes/powerbi-implementation-planning-context.md)]

[Power BI採用ロードマップ](powerbi-adoption-roadmap-content-ownership-and-management.md#managed-self-service-bi)に記載されているように、*マネージドセルフサービスBI*は、*コアでの規律*と*エッジでの柔軟性*を重視したブレンドされたアプローチを特徴としています。データアーキテクチャは通常、中央のBI専門家からなる単一のチームが維持し、報告責任は部門やビジネスユニット内のクリエイターが負う。

しかし、コアデータアーキテクチャに必要なデータがすべて含まれていない場合、データセット作成者は、既存の共有データセットを拡張、パーソナライズ、またはカスタマイズできます。既存の一元的に提供されるデータセットでは満たされないビジネス要件を満たす、新しい特殊なデータセットを作成できます。重要なのは、コアデータが重複しないことです。このような使用方法を「カスタマイズ可能なマネージドセルフサービスBI」と呼びます。

> [!NOTE] > このカスタマイズ可能なマネージドセルフサービスBIシナリオは、セルフサービスBIシナリオの2番目のシナリオです。このシナリオは、（[マネージドセルフサービスBI](powerbi-implementation-planning-use-scenario-managed-self-service-bi.md)シナリオで紹介された）一元化された共有データセットで何ができるかを構築しています。すべてのシナリオのリストは、[Power BI使用シナリオ](powerbi-implementation-planning-useage-scenario-overview.md)の記事にあります。 > > 簡潔にするために、[コンテンツのコラボレーションと配信シナリオ](powerbi-implementation-planning-useage-scenario-overview.md#content-management-and-deployment-scenarios)のトピックで説明されているいくつかの側面は、この記事ではカバーされていません。完全にカバーするには、まずそれらの記事をお読みください。

## Scenario diagram

次の図は、カスタマイズ可能なマネージドセルフサービスBIをサポートするための、最も一般的なユーザーアクションとPower BIコンポーネントのハイレベルな概要を描いたものです。ビジネスユニットのコンテンツ作成者に、既存の共有データセットを拡張して専用のデータモデルを作成する機能を提供することに主眼を置いています。その目的は、可能な限り再利用性を実現し、追加の分析要件を満たすための柔軟性を確保することです。

![](https://docs.microsoft.com/en-us/power-bi/guidance/media/powerbi-implementation-planning-usage-scenario-customizable-managed-self-service-bi/usage-scenario-customizable-managed-self-service-bi-inline.png)

画像は、カスタマイズ可能なマネージドセルフサービスBIの図で、既存のデータセットを拡張してパーソナライズすることにより、新しい特殊なデータセットを作成するものです。図の中の項目は、下の表で説明されています。

シナリオ・ダイアグラムでは、以下のようなユーザーアクション、ツール、機能が描かれています。

| **Item** | **Description** |
| --- | --- |
| ![Item 1.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-01-red-30x30.png) | データセット作成者Aは、Power BI Desktopを使用してモデルを作成します。再利用を目的としたデータセットの場合、作成者は組織の壁を越えてユーザーをサポートする集中チーム（IT、エンタープライズBI、センターオブエクセレンスなど）に所属しているのが一般的です（必須ではありません）。 |
| ![Item 2.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-02-red-30x30.png) | Power BI Desktopは、1つまたは複数のデータソースからデータに接続します。 |
| ![Item 3.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-03-red-30x30.png) | データモデルの開発は、Power BI Desktopで行われます。多くのセルフサービスのレポート作成者がデータソースとして使用する可能性があるため、デザイン性の高い、ユーザーフレンドリーなモデルを作成するための努力がなされています。|
| ![Item 4.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-04-red-30x30.png) | 準備ができたら、データセット作成者Aは、モデルのみを含むPower BI Desktopファイル(.pbix)をPower BIサービスに公開します。|
| ![Item 5.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-05-red-30x30.png) | このデータセットは，共有データセットの保存と保護に特化したワークスペースに公開されています．このデータセットは再利用を目的としているので，[endorsed](../collaborate-share/service-endorse-content.md)となっています（必要に応じて認証または昇格されます）．また，データセットの再利用をさらに促すために，[discoverable](../collaborate-share/service-discovery.md)と表示されています．Power BIサービスの[lineage view](../collaborate-share/service-data-lineage.md)は、成果物間に存在する依存関係を追跡するために使用できます。 |
| ![Item 6.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-06-red-30x30.png) | [データセットハブでのデータセット発見](../connect-data/service-datasets-hub.md)が有効なのは、データセットが発見可能とマークされているからです。発見可能とは、データを探している他のPower BIコンテンツ作成者がデータセットハブでデータセットの存在を確認できるようにするものです。|
| ![Item 7.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-07-red-30x30.png) | データセット作成者Bは、Power BIサービスのデータセットハブを使用して、発見可能なデータセットを検索します。 |
| ![Item 8.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-08-red-30x30.png) | データセット作成者Bが許可を持っていない場合は、そのデータセットに対して [構築許可](../connect-data/service-datasets-build-permissions.md) を要求することができます。これにより、権限のある承認者に構築許可を求めるワークフローが開始されます。|
| ![Item 9.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-09-red-30x30.png) | Power BI Desktopでは、データセット作成者Bが、Power BIサービスにある元の共有データセットへのライブ接続を作成します。元のデータセットを拡張・カスタマイズすることが目的なので、[ライブ接続](../connect-data/desktop-report-lifecycle-datasets.md)を[DirectQueryモデルに変換](../connect-data/desktop-directquery-datasets-azure-analysis-services.md#using-directquery-for-live-connections)します。このアクションにより、Power BI Desktopファイルにローカルモデルが表示されます。 |
| ![Item 10.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-10-red-30x30.png) |Power BI Desktopは、追加のデータソースからデータに接続します。その目的は、共有データセットを増強して、新たに特化したデータセットで追加の分析要件を満たすことです。 |
| ![Item 11.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-11-red-30x30.png) | 既存のテーブル（リモートモデルとして知られる共有データセットから）と、インポートしたばかりの新しいテーブル（[ローカルモデル](../connect-data/desktop-directquery-datasets-azure-analysis-services.md#using-directquery-for-live-connections)に格納されている）の間に、Power BI Desktopでリレーションシップが作成されます。Power BI Desktopで追加の計算やモデリング作業を行い、専用モデルの設計を完成させます。|
| ![Item 12.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-12-red-30x30.png) | 準備ができたら、データセット作成者Bは、Power BIサービスにPower BI Desktopファイルを公開します。|
| ![Item 13.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-13-red-30x30.png) | 新しい特殊なデータセットは、部門が所有・管理しているデータセットの保存と保護に特化したワークスペースに公開されます。 |
| ![Item 14.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-14-red-30x30.png) | 特化型データセットは、元のPower BI共有データセットに接続されたままです。元の共有データセットに変更を加えると、[それに依存している下流の特化型データセットにも影響が及びます](../connect-data/desktop-directquery-datasets-azure-analysis-services.md#chaining)。 |
| ![Item 15.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-15-red-30x30.png) | その他のセルフサービスのレポート作成者は、特化したデータセットに接続された新しいレポートを作成することができます。レポート作成者は、Power BI Desktop、Power BI Report Builder、またはExcelの使用を選択できます。 |
| ![Item 16.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-16-red-30x30.png) | レポート作成者は、Power BI Desktopを使って新しいレポートを作成します。 |
| ![Item 17.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-17-red-30x30.png) | レポートは、レポートやダッシュボードの保存と保護に特化したワークスペースに公開されます。 |
| ![Item 18.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-18-red-30x30.png) | 公開されたレポートは、別のワークスペースに保存されている特殊なデータセットに接続されたままになります。特殊なデータセットに変更を加えると、そのデータセットに接続されているすべてのレポートに影響します。 |
| ![Item 19.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-19-red-30x30.png) | 組織内のプライベートネットワークに存在するデータソースに接続するためには、データリフレッシュのためにオンプレミスのデータゲートウェイが必要です。 |
| ![Item 20.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-20-red-30x30.png) |Power BI管理者は、Power BIサービスの活動を監督・監視します。 |

## Key points

カスタマイズ可能なマネージドセルフサービスBIのシナリオについて、強調すべきポイントは以下の通りです。

### Shared dataset

管理型セルフサービスBI*を機能させるためには、データセットの数を最小限にすることが重要なポイントとなります。このシナリオでは、「真実の単一バージョン」の実現に貢献する[共有データセット](../connect-data/service-datasets-across-workspaces.md)を描いています。

> シナリオ図では、わかりやすくするために、共有データセットを1つだけ描いています。しかし、すべての組織データを1つのデータセットでモデル化することは、通常、現実的ではありません。また、経験の浅いコンテンツ制作者がよくやるように、レポートごとに新しいデータセットを作るのも極端です。目標は、比較的少数のデータセットを使い、必要に応じて新しいデータセットを作成するという、適切なバランスをとることです。

### Augment the initial shared dataset

セルフサービスの作成者は、既存のデータセットに部署固有の追加データなどを追加する必要があります。このような場合には、[Power BIデータセットへのDirectQuery接続](../connect-data/desktop-directquery-datasets-azure-analysis-services.md)を使用できます。この機能により、中央で管理されているデータ資産への投資を活用しつつ、セルフサービスを可能にする理想的なバランスを実現しています。シナリオ図は、DirectQueryの接続を表しています。ライブ接続を DirectQuery 接続に変換することで、新しいテーブルを追加できるローカルモデルが作成されます。元の共有データセットのテーブル（リモートモデル）と、追加されたばかりの新しいテーブル（ローカルモデル）の間にリレーションシップを作成できます。新しいデータモデルをカスタマイズするために、追加の計算やデータモデリングを行うことができます。

> [!TIP]
> このシナリオでは、共有データセットの再利用に焦点を当てています。しかし、データモデラーが下流のデータモデルの作成を制限したい状況もあります。そのような場合は、Power BI Desktopの設定で[Discourage DirectQuery connections](../connect-data/desktop-discourage-directquery-connections-to-dataset.md#discourage-directquery-connections-to-a-dataset-using-power-bi-desktop)プロパティを有効にします。

### データセットの推奨

共有データセットは再利用を目的としているため、データセットを[認定](../collaborate-share/service-endorsse-content.md)しておくと便利です。認証された*データセットは，そのデータが信頼できるものであり，組織の品質基準を満たしていることをレポート作成者に伝えます．プロモーションされた*データセットは，データセットの所有者がそのデータに価値があり，他の人が使う価値があると考えていることを強調している。

> [! TIP]
> コンテンツを承認するために、一貫性があり、繰り返し可能で、厳格なプロセスを持つことは、ベストプラクティスです。認定されたコンテンツは、データの品質が検証されていることを示す必要があります。また、変更管理規則に従い、正式なサポートを受け、完全に文書化されていなければなりません。認証されたコンテンツは厳格な基準に合格しているため、信頼性に対する期待が高くなります。

### Dataset discovery

[データセットハブ](../connect-data/service-datasets-hub.md)は、レポート作成者が組織内のデータセットを見つけ、探索し、利用するのに役立ちます。データセットの推奨に加えて、[データセットの発見を可能にする](../connect-data/service-datasets-hub.md#make-your-dataset-discoverable)ことは、データセットの再利用を促進するために重要です。発見可能なデータセットは、レポート作成者がデータを検索する際に、データセットハブに表示されます。

> 注意
> データセットが発見可能に設定されていない場合、Build権限を持つPower BIユーザーのみがデータセットを見つけることができます。

### Request dataset access

レポート作成者は、[datasets hub](../connect-data/service-datasets-hub.md)の中に、使用したいデータセットを見つけることができます。そのデータセットに対する構築許可を持っていない場合は、アクセスを要求できます。データセットの [request access setting](../connect-data/service-datasets-build-permissions.md#configure-how-users-request-build-permission) に応じて、データセットの所有者にメールが送信されるか、アクセスを要求している人にカスタム指示が提示されます。

### Publish to separate workspaces

データセットが保存されている場所とは異なるワークスペースにレポートを発行することには、いくつかの利点があります。

まず、どのワークスペースのコンテンツを誰が管理するのかが明確になります。次に、レポート作成者は、コンテンツをレポート用ワークスペースに発行する権限を持っています（ワークスペースの管理者、メンバー、またはコントリビューターのロールを介して）。しかし、彼らは特定のデータセットに対する読み取り権限と構築権限しか持っていません。この手法により、ビューワ・ロールに割り当てられたユーザに対して、必要に応じて[行レベルのセキュリティ（RLS）](../admin/service-admin-rls.md)を有効にすることができます。

### Dependency and impact analysis

共有データセットが他のデータセットやレポートで使用されている場合、それらの依存オブジェクトは多くのワークスペースに存在する可能性があります。[lineage view](../collaborate-share/service-data-lineage.md)は、下流の依存関係を特定して理解するのに役立ちます。データセットの変更を計画するときは、まず [impact analysis](../collaborate-share/service-dataset-impact-analysis.md#perform-dataset-impact-analysis) を実行して、どのデータセットやレポートを編集したりテストしたりすべきかを理解します。

### Gateway setup

通常、データゲートウェイは、プライベート組織ネットワークまたは仮想ネットワーク内に存在するデータソースにアクセスする際に必要となります。[オンプレミスのデータゲートウェイ](../connect-data/service-gateway-onprem.md)は、Power BI DesktopのファイルがPower BIサービスに公開されると関係してきます。ゲートウェイの2つの目的は、[インポートされたデータのリフレッシュ](../connect-data/refresh-data.md)、またはライブ接続や[DirectQuery](../connect-data/desktop-directquery-about.md)のデータセットを照会するレポートを表示することです。

> [! NOTE] > カスタマイズ可能なマネージドセルフサービスBIシナリオでは、*[パーソナルモード](../connect-data/service-gateway-personal-mode.md#on-premises-data-gateway-vs-on-premises-data-gateway-personal-mode)*のゲートウェイよりも、*標準モード*の集中型[データゲートウェイ](../connect-data/service-gateway-personal-mode.md)*のゲートウェイを強く推奨します。スタンダード・モードでは、データ・ゲートウェイはライブ接続とDirectQueryオペレーション（スケジュールされたデータ・リフレッシュ・オペレーションに加えて）をサポートします。

### System oversight

[アクティビティログ](../admin/service-admin-auditing.md)は、Power BIサービスで発生したユーザーの活動を記録します。Power BI管理者は、収集されたアクティビティログデータを使用して[監査](powerbi-adoption-roadmap-system-oversight.md#auditing)を行い、使用パターンや採用状況の把握に役立てることができます。また、アクティビティログは、ガバナンスの取り組み、セキュリティ監査、コンプライアンス要件をサポートするためにも価値があります。カスタマイズ可能なマネージドセルフサービスのBIシナリオでは、オリジナルの共有データセットと依存するデータセットの使用状況を追跡することがとくに役立ちます。

## Next steps

このシリーズの[次の記事](powerbi-implementation-planning-useage-scenario-self-service-data-preparation.md)では、セルフサービスのデータ準備シナリオにおけるデータフローでのデータ準備作業の再利用について学びます。
