---
title: "Power BI usage scenarios"
description: "An overview of the Power BI implementation planning usage scenario articles."
author: peter-myers
ms.author: v-petermyers
ms.reviewer: maroche
ms.service: powerbi
ms.subservice: powerbi-resource
ms.topic: conceptual
ms.date: 02/07/2022
---

# Power BI usage scenarios

[!INCLUDE [powerbi-implementation-planning-context](includes/powerbi-implementation-planning-context.md)]

Power BIのエコシステムは多様で、さまざまな方法で実装できます。この連載では、一般的な使用シナリオを紹介し、Power BIの作成者と使用者によるさまざまな導入方法と活用方法を説明します。これらの使用シナリオがあなたの組織でどのように使用されているのか、また誰が使用しているのかを理解することは、あなたが取るべき実装戦略に影響を与えます。

> Power BIの最も一般的なコンポーネントは、それぞれのシナリオでPower BIがどのように使用されるかに基づいて特定されています。目的は、各使用シナリオで可能なすべてのオプションを呼び出すことではありません。むしろ、各シナリオ図は、そのシナリオに最も関連する主要な機能を描いています。

## How to use the scenarios

シナリオを参考にして、Power BIのアーキテクチャ計画や実装の決定に役立ててください。以下にいくつかの提案をします。

- 最初にシナリオを文書化された順に読みます。データ文化](powerbi-adoption-roadmap-data-culture.md)に適したシナリオに焦点を当てます。また、どの使用シナリオが適しているかを判断する際には、[コンテンツの所有権と管理](powerbi-adoption-roadmap-content-ownership-and-management.md)がどのように処理されるか、また[コンテンツの配信範囲](powerbi-adoption-roadmap-content-delivery-scope.md)についても考慮してください。
- あなたの組織において、BI業務のどの部分を強化できるかを検討してください。たとえば、データの重複を減らすことが目的であれば、[マネージドセルフサービスBI](powerbi-implementation-planning-useage-scenario-managed-self-service-bi.md)のシナリオに注目します。データ準備作業の効率化が目的であれば、[セルフサービスデータ準備](powerbi-implementation-planning-use-scenario-self-service-data-preparation.md)のシナリオに注目してください。
- 組織にさらなる価値をもたらしたり、リスクを軽減したりするPower BIの使用方法があるかどうかを判断します。例えば、集中化と分散化のバランスをとることが目的であれば（[コンテンツの所有と管理](powerbi-adoption-roadmap-content-ownership-and-management.md)の記事で詳しく説明しています）、[カスタマイズ可能なマネージドセルフサービスBI](powerbi-implementation-planning-use-scenario-customizable-managed-self-service-bi.md)のシナリオを検討します。 - BIオペレーションのうち、導入または強化したい分野を理解した後、望ましい将来の状態に到達するための戦術的なステップを定義するプロジェクトプランを作成します。

> 活用シナリオに記載されているアイデアを組み合わせて、自分の状況に合ったPower BI導入戦略を立てる必要があるかもしれません。さまざまな部門やビジネスユニットのユーザーのニーズをサポートするために、複数のPower BI導入方法を同時に利用することを想定してください。そうすることで、多様なコンテンツ制作者や様々なソリューションに対応することができるようになります。

## Content collaboration and delivery scenarios

以下の使用シナリオは、*コンテンツのコラボレーションと配信*に関するもので、主に[コンテンツの所有権と管理](powerbi-adoption-roadmap-content-ownership-and-management.md)、および[コンテンツの配信範囲](powerbi-adoption-roadmap-content-delivery-scope.md)に焦点を当てています。これらのシナリオは相互に関連しています。これらのシナリオは相互に関連しており、ビジネス・インテリジェンス・チームがどのように進化し、成長していくかに沿った形でお互いに構築されています。

- **[パーソナルBI](powerbi-implementation-planning-useage-scenario-personal-bi.md):** コンテンツ作成者は、個人で使用するためのコンテンツを作成するために、多くの自由と柔軟性を持っています。
- **[チームBI](powerbi-implementation-planning-use-scenario-team-bi.md):** 主に、チームで密接に働くメンバー間の非公式なコラボレーションに焦点を当てています。このシナリオでは、コラボレーションと配布の両方にワークスペースを使用することを説明します。また、Power BIの作成者と消費者の間のコラボレーションにMicrosoft Teamsを使用することの価値を紹介しています。 
- **[部門別BI](powerbi-implementation-planning-use-scenario-departmental-bi.md):** 部門やビジネスユニット内のより多くのユーザーにコンテンツを配布することに焦点を当てています。
- **[Enterprise BI](powerbi-implementation-planning-useage-scenario-enterprise-bi.md):** 大規模なコンテンツ配信に重点が置かれています。このシナリオでは、プレミアム容量を使用して、Power BIの無料ライセンスを持っているより多くの読み取り専用の消費者にコンテンツを配信することを説明します。

> [! NOTE] > [コンテンツの所有権と管理](powerbi-adoption-roadmap-content-ownership-and-management.md)と[コンテンツの配信範囲](powerbi-adoption-roadmap-content-delivery-scope.md)に関する追加情報は、[Power BI採用ロードマップ](powerbi-adoption-roadmap-overview.md)に記載されています。

## Self-service BI scenarios

4つの使用シナリオは、分析責任を組織の様々な分野の人々が担う「セルフサービスBI」活動のサポートに焦点を当てています。前述のコンテンツのコラボレーションと配信のシナリオもセルフサービスBIの側面を含んでいますが、少し異なる視点からのシナリオとなっています。このシナリオ群の目的は、Power BIを導入する際に計画すべきいくつかの重要な側面に焦点を当てることです。

ここで紹介するセルフサービスBIのシナリオは、主にデータ管理が一元化された「管理型セルフサービスBI」の使用を強調しています。この一元化されたデータの再利用性は、主要な目標の一つです。ビジネスユーザーは、レポートやダッシュボードの作成に責任を持ちます。

- **[マネージドセルフサービスBI](powerbi-implementation-planning-use-scenario-managed-self-service-bi.md):** 多くのレポート作成者が共有データセットを再利用することを目標としています。このシナリオでは、レポート作成プロセスをデータセット作成プロセスから切り離すことを説明します。カスタマイズ可能なマネージドセルフサービスBI](powerbi-implementation-planning-use-scenario-customizable-managed-self-service-bi.md):**データセット作成者が、新しい要件を満たすために既存のデータセットをカスタマイズまたは拡張することに焦点を当てています。
- **[セルフサービスデータ準備](powerbi-implementation-planning-use-scenario-self-service-data-preparation.md):** 一貫性を高め、労力を減らすために、データ準備作業を一元化することに焦点を当てています。このシナリオでは、データ準備のPower Queryロジックを多くの異なるPower BI Desktopファイルで繰り返さないように、Power BIデータフローの作成について説明します。データフローは、多数のデータセットのデータソースとして消費することができます。
- **[Prototyping and data sharing](powerbi-implementation-planning-useage-scenario-prototyping-and-sharing.md):** プロトタイピング技術は、サブジェクト・マター・エキスパートによるビジュアルや計算の要件を検証するのに非常に役立ちます。プロトタイピングのソリューションは、一時的な短期間のソリューションの場合もあれば、最終的に完全に検証されてリリースされるソリューションに発展する場合もあります。このシナリオでは、インタラクティブなプロトタイピングセッションでPower BI Desktopを使用します。続いて、サブジェクト・マター・エキスパートからの追加フィードバックが必要な場合は、Power BIサービスで共有します。

> Power BI導入ロードマップ(powerbi-adoption-roadmap-content-ownership-and-management.md)やコンテンツ配信範囲(powerbi-adoption-roadmap-content-delivery-scope.md)など、セルフサービスBIの活動や決定に影響する情報は、Power BI導入ロードマップ(powerbi-adoption-roadmap-overview.md)に記載されています。

## Content management and deployment scenarios

以下のコンテンツ管理と展開のシナリオは、コンテンツの作成者と所有者が、エラーを減らし、不整合を最小限に抑え、消費者のためにユーザーエクスペリエンスを向上させるために、どのように体系的で規律あるライフサイクル管理プロセスを使用するかについてのアプローチを説明しています。

- **[セルフサービスコンテンツパブリッシング](powerbi-implementation-planning-useage-scenario-self-service-content-publishing.md):** 消費者にとってコンテンツが安定していることに焦点を当てています。このシナリオでは、Power BI導入パイプラインを使用して、開発、テスト、本番の各ワークスペースでコンテンツを公開する方法を説明します。また、開発およびテスト用のワークスペースにはユーザーごとのプレミアムライセンスモードを、本番用のワークスペースには容量ごとのプレミアムライセンスモードを使用する方法（オプション）についても説明します。このシナリオでは、外部ツールであるTabular Editorを使用したデータモデルの管理について説明します。データモデルは、Power BI Premiumで利用可能なXMLAエンドポイントを使用してPower BIサービスにデプロイされます。
- **Enterprise content publishing (not currently available):** より洗練されたプログラム技術を使用して、開発、テスト、本番のワークスペースでコンテンツを公開することに焦点を当てています。このシナリオでは、Azure DevOpsがPower BI REST API操作を調整して実行し、コンテンツを展開します。

## Real-time scenarios

*このシナリオの記事は現在ありません。*

*リアルタイム*シナリオでは、データの更新をほぼリアルタイムで表示するためのさまざまなテクニックについて説明します。リアルタイムにデータを監視することで、一刻を争う意思決定の際に迅速に対応することができます。

## Embedding and hybrid scenarios

埋め込みとハイブリッド*のシナリオには、「エンタープライズ埋め込み」と「オンプレミスレポート」の2つがあります。これらのシナリオでは、Power BIサービスに加えて、またはPower BIサービスの代わりに使用できるコンテンツを展開・配布する方法について説明します。

- **エンタープライズエンベッディング（現在は提供されていません）：** ビジネスユーザーが日常的に使用しているツールやアプリケーションにビジュアルを統合することで、分析データにアクセスしやすくすることに焦点を当てています。このシナリオでは、Power BI REST APIを使用してカスタムアプリケーションにコンテンツを埋め込む方法を説明しています。
- **[オンプレミスレポート](powerbi-implementation-planning-use-scenario-on-premises-reporting.md):** 組織のネットワーク内でビジネスインテリジェンスコンテンツを公開、共有、消費するための基本的なポータルを使用することに重点を置いています。このシナリオでは、この目的のためにPower BI Report Serverを使用することを説明します。

## Next steps

本連載の[次の記事](powerbi-implementation-planning-useage-scenario-personal-bi.md)では、パーソナルBIの使用シナリオで個人のためのプライベート分析を有効にすることについて学びます。
