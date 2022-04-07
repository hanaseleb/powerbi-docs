---
title: "Power BI usage scenarios: On-premises reporting"
description: "Learn how Power BI on-premises reporting is about customer-managed reporting."
author: peter-myers
ms.author: v-petermyers
ms.reviewer: maroche
ms.service: powerbi
ms.subservice: powerbi-resource
ms.topic: conceptual
ms.date: 02/07/2022
---

# Power BI usage scenarios: On-premises reporting

[！INCLUDE [powerbi-implementation-planning-context](includes/powerbi-implementation-planning-context.md)]を参照してください。

*オンプレミスレポート*シナリオは、Power BIサービスを使用せずにPower BIソリューションを展開するためのいくつかの*ハイブリッドおよびカスタムシナリオ*の1つです。

このシナリオでは、[Power BI Report Server](../report-server/get-started.md)を使用します。Power BI Report Serverは、組織ネットワーク内でビジネス・インテリジェンス・コンテンツを公開、共有、消費するためのオンプレミスのポータルです。クラウドベースのPower BIサービスの代わりに、BIコンテンツの一部（または全部）を展開する必要がある場合に有効です。例えば、規制、法律、知的財産などの理由で、完全に顧客管理されたプラットフォームが必要な場合があります。

## Scenario diagram

次の図は、オンプレミスのレポートをサポートするための最も一般的なユーザーアクションとPower BIコンポーネントのハイレベルな概要を描いています。ここでは、組織ネットワーク内のWindowsサーバー上で動作するPower BI Report Serverの使用に焦点を当てています。

![](https://docs.microsoft.com/en-us/power-bi/guidance/media/powerbi-implementation-planning-usage-scenario-self-service-content-publishing/usage-scenario-self-service-content-publishing-inline.png)

イメージとしては、オンプレミスのレポーティングの図で、お客様が管理するポータルを配信するというものです。この図の中の項目は、以下の表で説明されています。

シナリオ図では、以下のユーザーアクション、ツール、機能が描かれています。

| **Item** | **Description** |
| --- | --- |
| ![Item 1.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-01-red-30x30.png) | Power BIのコンテンツ制作者が、BIソリューションを構築する。 |
| ![Item 2.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-02-red-30x30.png) | [Power BI Desktop for Report Server](../report-server/install-powerbi-desktop.md)は、1つまたは複数のデータソースからデータに接続します。複数のソースを組み合わせたクエリやデータマッシュアップは、[Power Query Editor](/power-query/power-query-what-is-power-query)で開発します。 |
| ![Item 3.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-03-red-30x30.png) | データモデルの開発とレポートの作成は、Power BI Desktop for Report Serverで行います。Power BI Report Serverに公開できる、特定のタイプのPower BI Desktopファイル（.pbix）を生成します。 |
| ![Item 4.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-04-red-30x30.png) | レポート作成者は、[Power BI Report Builder](../paginated-reports/report-builder-power-bi.md)を使ってページネーションレポートを作成することもできます。このツールは、Power BI Report Serverにパブリッシュできるレポート定義言語ファイル(.rdl)を生成します。 |
| ![Item 5.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-05-red-30x30.png) | レポート作成者は、Excelを使ってレポートを開発することもできます。Excelワークブックファイル（.xlsx）をPower BI Report Serverに公開できます。 |
| ![Item 6.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-06-red-30x30.png) | 準備ができたら、コンテンツ作成者はPower BI Report Serverにファイルを公開します。 |
| ![Item 7.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-07-red-30x30.png) | コンテンツはPower BI Report Serverの[フォルダ](../report-server/getting-around.md)に公開されます。 |
| ![Item 8.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-08-red-30x30.png) | レポートコンシューマーは、Power BI Report Serverに発行されたレポートを表示します。 |
| ![Item 9.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-09-red-30x30.png) | レポートコンシューマーは、[Power BI モバイルアプリ](../consumer/mobile/mobile-apps-for-mobile-devices.md)を使用してレポートを表示することもできます。 |
| ![Item 10.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-10-red-30x30.png) | サーバー管理者は、Windowsサーバーのインフラを管理します。 |
| ![Item 11.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-11-red-30x30.png) | データベース管理者は、Report Serverデータベースを含むPower BI Report Serverと、SQL Server Agentを管理します。 |
| ![Item 12.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-12-red-30x30.png) | SQL Server Agentのジョブは、定期的に[インポートデータセットのリフレッシュを行います](../report-server/configure-scheduled-refresh.md)。 |
| ![Item 13.](https://docs.microsoft.com/en-us/power-bi/guidance/media/common/icon-13-red-30x30.png) | 管理者は、Power BI Report Serverの活動を監督・監視します。 |

## Key points

オンプレミスでのレポート作成のシナリオについては、以下のようなポイントを重視しています。

### Report creator experience

コンテンツ制作者は、[Power BI Desktop for Report Server](https://powerbi.microsoft.com/report-server/)という特定のツールを使用します。このPower BI Desktopのバージョンは年に3回更新され、Power BI Report Serverのリリースサイクルに対応しています。

> Power BIサービスとPower BI Report Serverの両方のコンテンツを作成するレポート作成者のために、2つのバージョンのPower BI Desktopを並べてインストールすることができます。

### Report consumer experience

Power BI Report Serverのレポート消費者の体験は、Power BIサービスとは大きく異なります。Power BI Report Serverは、コンテンツを表示、保存、管理するためのWebポータルです。コンテンツファイル（.pbix、.rdl、または .xlsx）は、フォルダー階層に公開されます。詳しくは、[Webポータルでコンテンツを管理する](../report-server/getting-around.md)をご覧ください。

### Power BI Report Server

Power BI Report Serverは、SQL Server Reporting Services（SSRS）とは別の製品です。別々にライセンスされ、インストールされます。Power BI Report Serverは、SSRSを超える追加機能を備えているため、SSRSのスーパーセットと考えられています。

> Power BI Report ServerとPower BIサービスは、Microsoftの同じエンジニアリングチームによってサポートされていますが、この2つの製品には機能的に大きな違いがあります。Power BI Report Serverは、オンプレミスのレポーティングのための基本的なレポートポータルです。そのため、Power BI サービスとの間には多くの[機能の違い](../report-server/compare-report-server-service.md)があります。Power BI Report Serverの機能セットは意図的にシンプルに作られており、パリティを期待してはいけません。Power BI Report Serverをインストールする前に、使用する予定の重要な機能がサポートされているかどうかを確認してください。

### Report server databases

SQL ServerはReport Serverのデータベースをホストします。最も一般的なSQL Server Database Engineインスタンスは、オンプレミスのデータセンターで[Windowsサーバーにインストール](../report-server/system-requirements.md#database-server-version-requirements)されています。また、Azure（ホステッドクラウド）の仮想マシンにインストールしたり、Azure SQL Managed Instanceでホストすることもできます（シナリオ図には描かれていません）。データベースインフラストラクチャは、データベース管理者によって管理されます。

### Mobile access

Power BI Report Serverへのリモートモバイルアクセスを有効にするには、追加の設定を行う必要があります。詳しくは、[Report ServerへのPower BIモバイルアプリのリモートアクセスを設定する](../report-server/configure-powerbi-mobile-apps-remote.md)をご覧ください。

### Licensing Power BI Report Server

[Power BI Report Serverのライセンスには2つの方法があります](../report-server/get-started.md#licensing-power-bi-report-server)。Power BI Premium」と「SQL Server Enterprise Edition with Software Assurance」です。

Power BI Premiumのキャパシティを購入すると、キャパシティノードのVコアと同じ数のコアを持つオンプレミスのサーバーにPower BI Report Serverをインストールできます。これにより、Power BIサービス（クラウド）とPower BI Report Server（オンプレミスまたはAzureのホステッドクラウド）へのコンテンツの公開をサポートするハイブリッドアプローチを採用できます。

> Power BI Report ServerをPremium capacity feature setの一部としてライセンスする場合、P SKUでのみ利用できます。他のキャパシティベースのSKU（EMおよびA SKU）ではこの特典はなく、Power BI Premium Per User（PPU）もありません。

## Next steps

Power BIの導入判断に役立つ他のシナリオについては、[Power BI利用シナリオ](powerbi-implementation-planning-useage-scenario-overview.md)の記事をご覧ください。
