---
title: "Power BI usage scenarios: Self-service content publishing"
description: "Learn how Power BI self-service content publishing is about publishing content to development, test, and production with deployment pipelines."
author: peter-myers
ms.author: v-petermyers
ms.reviewer: maroche
ms.service: powerbi
ms.subservice: powerbi-resource
ms.topic: conceptual
ms.date: 02/07/2022
---

# Power BI usage scenarios: Self-service content publishing

[!INCLUDE [powerbi-implementation-planning-context](includes/powerbi-implementation-planning-context.md)]

分析ソリューションが組織にとって重要である場合、Power BIサービス内のコンテンツが消費者にとって安定して信頼できるものであることが重要です。ITチームはしばしば、複数の環境で作業することでこの問題を解決します。

- **開発**環境では、コンテンツの作成者や所有者がソリューションに変更や改善を加えます。**開発**環境では、コンテンツ制作者やオーナーがソリューションの変更や改善を行います。これらの変更が広くレビューできる状態になったら、ソリューションはテスト環境にデプロイされます（*プロモート*と呼ばれることもあります）。このレビューには、ソリューションの機能やデータの検証も含まれます。レビューが完了すると、ソリューションは本番環境にデプロイされます。
- **本番**環境は、消費者がリリースされたソリューションを閲覧し、対話する場所です。

本番環境とは、お客様がリリースされたソリューションを利用する場所です。このように構造化されたアプローチにより、コンテンツ制作者、オーナー、レビュー担当者は、お客様に悪影響を与えることなく変更を行い、検証できます。

秩序立ったライフサイクル管理プロセスを使用することで、エラーを減らし、不整合を最小限に抑え、お客様のユーザーエクスペリエンスを向上させます。コンテンツの作成者と所有者は、Power BIの[デプロイメントパイプライン](../create-reports/deployment-pipelines-overview.md)を使用して、*セルフサービスのコンテンツパブリッシング*を行うことができます。デプロイメントパイプラインは、プロセスを簡素化し、新しいコンテンツを公開する際のコントロールレベルを向上させます。

> [! NOTE] > このセルフサービス・コンテンツ・パブリッシングのシナリオは、[コンテンツ管理と展開](powerbi-implementation-planning-use-scenario-overview.md#content-management-and-deployment-scenarios)のシナリオの一つです。セルフサービスのシナリオの完全なリストについては、[Power BI使用シナリオ](powerbi-implementation-planning-useage-scenario-overview.md)の記事を参照してください。 > > 簡潔にするために、[コンテンツのコラボレーションと配信シナリオ](powerbi-implementation-planning-useage-scenario-overview.md#content-management-and-deployment-scenarios)のトピックで説明されているいくつかの側面は、この記事ではカバーされていません。完全にカバーするには、まずそれらの記事をお読みください。

## Scenario diagram

次の図は、セルフサービスのコンテンツパブリッシングをサポートするための、最も一般的なユーザーアクションとPower BIコンポーネントの概要を示しています。ここでは、開発、テスト、本番の各ワークスペースでコンテンツを促進するためのPower BI導入パイプラインの使用に焦点を当てています。

![](https://docs.microsoft.com/en-us/power-bi/guidance/media/powerbi-implementation-planning-usage-scenario-self-service-content-publishing/usage-scenario-self-service-content-publishing-inline.png)

イメージは、セルフサービス・コンテンツ・パブリッシングの図で、デプロイメント・パイプラインを使ってコンテンツを開発、テスト、本番に発行することです。この図の中の項目は、以下の表で説明されています。

シナリオ図では、以下のユーザーアクション、ツール、および機能が描かれています。

| **Item** | **Description** |
| --- | --- |
| ![Item 1.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-01-red-30x30.png) | Power BIコンテンツ制作者は、Power BI Desktopを使ってBIソリューションを開発します。 |
| ![Item 2.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-02-red-30x30.png) | Power BI Desktopファイル（.pbix）は、OneDriveの共有ライブラリに保存されます。|
| ![Item 3.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-03-red-30x30.png) | 準備ができたら、コンテンツ作成者はPower BIサービスにPower BI Desktopファイルを公開します。 |
| ![Item 4.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-04-red-30x30.png) | コンテンツは、**開発**専用の[ワークスペース](../collaborate-share/service-new-workspaces.md)に公開されます。|
| ![Item 5.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-05-red-30x30.png) | 開発（またはテスト）ワークスペースは、**Premium per user**、**Premium per capacity**、または**Embedded** [ライセンスモードに設定されています](.../collaborate-share/service-create-the-new-workspaces.md#premium-capacity-settings)。|
| ![Item 6.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-06-red-30x30.png) | コンテンツ制作者とオーナーは、開発ワークスペースで共同作業を行い、すべての要件が満たされていることを確認します。 |
| ![Item 7.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-07-red-30x30.png) | 展開パイプラインの管理者は、Power BIの[展開パイプライン](../create-reports/deployment-pipelines-overview.md)を開発、テスト、本番の3つのステージで構成します。各ステージは、Power BIサービスの個別のワークスペースに合わせます。デプロイメント設定とアクセスは、デプロイメント パイプラインに対して構成されます。 |
| ![Item 8.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-08-red-30x30.png) | 開発コンテンツの準備が整うと、デプロイメント・パイプラインは開発ステージとテストステージの間でコンテンツを比較する。一部または全部のアーティファクトは、**テスト**専用のワークスペースにデプロイされます。 |
| ![Item 9.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-09-red-30x30.png) | テスト（または開発）ワークスペースが、**Premium per user**、**Premium per capacity**、または**Embedded** [ライセンスモードに設定されています](.../collaborate-share/service-create-the-new-workspaces.md#premium-capacity-settings)。 |
| ![Item 10.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-10-red-30x30.png) | 展開パイプラインが展開を完了すると、コンテンツ作成者はテスト ワークスペースの展開後のアクティビティを手動で実行します。この作業には、スケジュールされたデータ更新の設定や、テスト ワークスペース用の Power BI アプリの公開などが含まれます。 |
| ![Item 11.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-11-red-30x30.png) | Quality assurance, data validations, and user acceptance testing occur by reviewers of the test workspace. |
| ![Item 12.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-12-red-30x30.png) | When the test content is fully validated, the deployment pipeline compares the content between the test and production stages. Some, or all, artifacts are deployed to a workspace that's dedicated to **production**. |
| ![Item 13.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-13-red-30x30.png) | The production workspace is set to **Premium per user**, **Premium per capacity**, or **Embedded** [license mode](../collaborate-share/service-create-the-new-workspaces.md#premium-capacity-settings). For a production workspace, **Premium per capacity** license mode is often more appropriate when there's a large number of read-only consumers. |
| ![Item 14.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-14-red-30x30.png) | Once the deployment pipeline completes deployment, content creators can manually perform post-deployment activities. Activities can include configuring scheduled data refresh or publishing a Power BI app for the production workspace. |
| ![Item 15.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-15-red-30x30.png) | Content viewers access the content using the production workspace or a Power BI app. |
| ![Item 16.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-16-red-30x30.png) | To connect to data sources that reside within a private organizational network, an On-premises data gateway is required. |
| ![Item 17.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-17-red-30x30.png) | Power BI administrators oversee and monitor activity in the Power BI service. Content that's deemed critical enough to have separate development, test, and production workspaces may be subject to stricter governance requirements than less critical content. |

## Key points

The following are some key points to emphasize about the self-service content publishing scenario.

### Deployment pipeline

A deployment pipeline consists of three stages: development, test, and production. A single workspace is assigned to each stage in the deployment pipeline. Artifacts that are [supported by deployment pipelines](../create-reports/deployment-pipelines-process.md#deployed-items) are published (or cloned) from one workspace to another when a deployment occurs. Once testing and validations are complete, the deployment pipeline can be reused many times to promote content quickly. The deployment pipeline interface is easy to implement for content creators who don't have the skills or desire to use code-based deployments (use of the Power BI REST APIs are described in the [enterprise content publishing](powerbi-implementation-planning-usage-scenario-overview.md#content-management-and-deployment-scenarios) scenario).

> [!NOTE]
> Publishing content using a deployment pipeline is known as a *metadata-only deployment*. In this case, data isn't overwritten or copied to the target workspace. A data refresh is usually required once the deployment completes—see the [post-deployment activities](#post-deployment-activities) topic below.

### Deployment process

It's a best practice to consider the entire workspace content as an *analytical package* that can be deployed together as a unit. Therefore, it's important to have clarity on the purpose and expectations of each workspace. Although a selective deployment of specific artifacts is possible, it's more efficient and less risky when a deployment represents a logical unit of content.

> [!TIP]
> Plan for how urgent issues will be handled, in addition to planned deployments. If an immediate fix is required, still follow the [standard practice](../create-reports/deployment-pipelines-best-practices.md#quick-fixes-to-content) of propagating all changes from development through to test and production using the deployment pipeline.

### Permissions model

Spend time planning the [permissions model](../create-reports/deployment-pipelines-best-practices.md#plan-your-permission-model). Full flexibility for applying different [workspace roles](../collaborate-share/service-roles-new-workspaces.md#workspace-roles) (between development, test, and production) is supported. As depicted in the scenario diagram, it's common to assign the following workspace permissions:

- **Development workspace:** Limit access to a team of content creators and owners who collaborate together.
- **Test workspace:** Limit access to reviewers involved with quality assurance, data validations, and user acceptance testing activities.
- **Production workspace:** Grant viewer access to content consumers of the Power BI app (and the workspace, when appropriate). Limit access to those who need to manage and publish production content, involving the fewest number of users possible.

> [!NOTE]
> Most content consumers are unaware of the development and test workspaces.

### Access for deployment pipeline

Pipeline user permissions (for who can deploy content with a deployment pipeline) are managed separately from the workspace roles. [Access to both the workspace and the deployment pipeline](../create-reports/deployment-pipelines-process.md#permissions) are required for the users conducting a deployment. Relevant [Premium permissions](../create-reports/deployment-pipelines-process.md#creating-a-premium-workspace) are also required.

When possible, it's recommended that the existing content creator or owner conduct the deployments. In some situations, permissions are more restricted for the production workspace. In that case, it may be appropriate to coordinate the production deployment with someone else who has permission to deploy to production.

[Pipeline users](../create-reports/deployment-pipelines-process.md#user-with-pipeline-access) who are assigned to the workspace member (or admin) role are allowed to compare stages and deploy content. Assigning pipeline users to this role minimizes permissions issues and allows for a smoother deployment process.

> [!TIP]
> Keep in mind that workspace roles are set separately for development, test, and production. However, pipeline access is set once for the entire pipeline.

### Power BI Premium licensing

Power BI deployment pipelines are a Premium feature. There are various [ways to obtain licensing](../create-reports/deployment-pipelines-troubleshooting.yml#what-type-of-capacity-can-i-assign-to-a-workspace-in-a-pipeline-), depending on whether the content is used for development, test, or production purposes. The scenario diagram depicts use of a Premium (P SKUs, such as P1, P2, P3, P4, or P5) [capacity-based license](../admin/service-premium-faq.yml#what-is-power-bi-premium---) for the production workspace, and a Power BI Premium Per User (PPU) [user-based Premium license](../admin/service-premium-per-user-faq.yml) for the development and test workspaces. Using PPU licensing for workspaces with very few users (as depicted in the scenario diagram) is a cost-effective way to use Premium features, while keeping them separate from the Premium capacity that's assigned for production workloads.

### Deployment settings

[Data source rules and parameter rules](../create-reports/deployment-pipelines-get-started.md#step-4---create-deployment-rules) are available for dynamically managing values that differ between development, test, and production. Use of deployment settings are an effective way to reduce effort and the risk of errors.

### Post-deployment activities

Purposefully, [certain properties aren't copied](../create-reports/deployment-pipelines-process.md#item-properties-that-are-not-copied) to the target workspace during a deployment. Several key post-deployment activities include:

- **Data refresh:** Data isn't copied from the source workspace to the target workspace. Publishing from a deployment pipeline is always a metadata-only deployment. Therefore, a data refresh is usually required after deploying to a target workspace. For first-time deployments, the data source credentials or gateway connectivity (as appropriate) must be configured as well.
- **Apps:** Power BI apps aren't published automatically by deployment pipelines.
- **Access roles, sharing permissions, and app permissions:** Permissions aren't overwritten during a deployment.
- **Workspace properties:** Properties, such as contacts and the workspace description, aren't overwritten during a deployment.
- **Artifact properties:** Certain artifact properties, such as sensitivity labels, may be overwritten during a deployment in [certain circumstances](../create-reports/deployment-pipelines-process.md#item-properties-copied-during-deployment).
- **Unsupported artifacts:** Additional manual steps may need to be taken for [artifacts that aren't supported](../create-reports/deployment-pipelines-process.md#deployed-items) by the deployment pipeline.

> [!CAUTION]
> There isn't a rollback process once a deployment has occurred with a deployment pipeline. Consider carefully what change management processes and approvals are required in order to deploy to the production workspace.

### OneDrive storage

The scenario diagram depicts using OneDrive for storing the source Power BI Desktop files. The goal is to store the source files in a location that is:

- Appropriately secured to ensure only publishers can access the source files. A [shared library](https://support.microsoft.com/office/create-a-new-shared-library-from-onedrive-for-work-or-school-345c8599-05d8-4bf8-9355-2b5cfabe04d0) (rather than a personal library) is a good choice.
- Backed up frequently so the files are safe from loss.
- Versioned when changes occur, to allow for a rollback to an earlier version.

> [!TIP]
> If a OneDrive location is [synchronized to a workspace](../collaborate-share/service-create-the-new-workspaces.md#set-a-workspace-onedrive), configure it only for the development workspace.

### Gateway setup

Typically, a data gateway is required when accessing data sources that reside within the private organizational network or a virtual network. The [On-premises data gateway](../connect-data/service-gateway-onprem.md) becomes relevant once a Power BI Desktop file is published to the Power BI service. The two purposes of a gateway are to [refresh imported data](../connect-data/refresh-data.md), or view a report that queries a live connection or [DirectQuery](../connect-data/desktop-directquery-about.md) dataset (not depicted in the scenario diagram).

When working with multiple environments, it's common to configure development, test, and production connections to use different source systems. In this case, use [data source rules and parameter rules](../create-reports/deployment-pipelines-get-started.md#step-4---create-deployment-rules) to manage values that differ between environments.

> [!NOTE]
> A centralized [data gateway](../connect-data/service-gateway-personal-mode.md#on-premises-data-gateway-vs-on-premises-data-gateway-personal-mode) in *standard mode* is strongly recommended over gateways in *[personal mode](../connect-data/service-gateway-personal-mode.md)*. In standard mode, the data gateway supports live connection and DirectQuery operations (in addition to scheduled data refresh operations).

### System oversight

The [activity log](../admin/service-admin-auditing.md) records user activities that occur in the Power BI service. Power BI administrators can use the activity log data that's collected to perform [auditing](powerbi-adoption-roadmap-system-oversight.md#auditing) to help them understand deployment activities that occur.

## Next steps

For other useful scenarios to help you with Power BI implementation decisions, see the [Power BI usage scenarios](powerbi-implementation-planning-usage-scenario-overview.md) article.
