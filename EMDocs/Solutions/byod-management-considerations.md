---
title: "管理に関する考慮事項"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 8/1/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ba8cc256-2075-457f-a827-7ec9213c5235
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: cc68855647cc3d8160a7153a96eb5e51443b3081
ms.sourcegitcommit: 45ffbe57b8a2ff1ba6d26efde7f4e2fee8495593
translationtype: MT
---
# <a name=""></a>管理に関する考慮事項

管理ドメインは、BYOD モデルをサポートするインフラストラクチャに必須です。BYOD の要求を完全にサポートするには、管理ドメインは、IT 部門がリソースを監視し、レポート機能を提供し、コンピューティング リソースとストレージ リソースを管理し、デバイスの構成と自動化を可能にし、アプリの展開およびプロビジョニングを管理できるようにする必要があります。

## <a name=""></a>モニタリング

管理ドメインの役割の 1 つは、企業の資産だけでなくユーザーが所有するモバイル デバイスについても、コンプライアンスの設定を監視することです。会社の基幹業務に従って、コンプライアンスに関する考慮事項を評価する必要があります。場合によっては、会社のデータが暗号化されている場合にのみ、ユーザーのデバイスに保存することを許可します。このようなポリシーを適用するには、IT 部門がセキュリティの設定を管理する必要があります。

ユーザー デバイスの管理レベルは、会社のポリシーおよび会社が導入する BYOD インフラストラクチャによって異なります。会社のリソースにアクセスするために完全ワイプ機能を提供する必要があると会社が決めた場合、IT 部門はこの設定をすべての監視対象デバイスに適用する必要があります。また、デバイスをメーカーの既定の設定にリセットし、必要に応じてすべての個人設定とデータをワイプする機能も必要です。次のセクションを使用して、BYOD インフラストラクチャに必要な監視オプションを決定してください。

### <a name="-"></a>監視オプション︰ 長所と短所

以下の一覧で、各監視オプションの長所と短所を確認してください。

- ユーザーのデバイスにインストールされた管理エージェント
    - 長所
        - ユーザーのデバイスをより詳細に制御
        - リモート ワイプ機能
        - 選択的ワイプ機能
        - 高速のアプリ展開とライフ サイクル管理
    - 短所
        - ユーザーのデバイスへの管理エージェントのインストールが必要
        - ユーザーの介入が大きい
        - エージェントをサポートするにはバックエンド管理インフラストラクチャが必要
- 管理エージェントがインストールされない
    - 長所
        - ユーザーのデバイスに管理エージェントがインストールされていない
        - アプリの視点からのみポリシーの適用を使用できる (例︰ 动态同步)
    - 短所
        - IT 部門がデバイスの管理に使用できるオプションに制限がある

前の表を見るとわかるように、BYOD インフラストラクチャ ソリューションを設計するとき、会社のポリシーを適用する場合は、エージェントをユーザーのデバイスにインストールする必要があります。

異なる種類のデバイスをサポートする場合は、デバイスの機能 （記憶域の暗号化、VPN 接続オプション、サポートされるプログラミング言語など） を理解する必要があります。会社のポリシーに準拠して実装できるものを評価します。コンプライアンスを満たすためのデバイスの監視は、ポリシーの適用によって行うことができます。データがユーザーのデバイスにある間はデバイスの暗号化を有効にすることを検討します。これにより、データ漏えい戦略をサポートできます。パスワード ロック解除、パスワード履歴、強いパスワードなどのポリシーを適用すると、社内デバイスとモバイル デバイスの両方で同様のセキュリティを実施できます。

配置管理器 でのコンプライアンスの設定により、IT 部門は企業内のサーバー、ラップトップ、デスクトップ コンピューター、およびモバイル デバイスの構成とコンプライアンスを管理できます。配置管理器 に組み込まれているモバイル デバイス用の既定のコンプライアンス設定を基準として使用し、会社のニーズに応じてカスタマイズしてください。配置管理器 でのコンプライアンス設定の詳細については、「[配置管理器 のコンプライアンス設定の概要](https://technet.microsoft.com/library/gg682139.aspx)」をご覧ください。

Windows 選択的ワイプを使用することにより、会社や個人のデバイスにちらばっている企業データを保護できます。データに対して Windows 選択的ワイプ ポリシーを使用するアプリを作成し、会社によって所有されているインターネット ドメイン上のデータを保護できます。针对设备数据管理的 Windows 選択的ワイプの詳細については、「Windows 选择性擦除 (デバイス データの管理のための Windows 選択的ワイプ) 」をご覧ください。

## <a name=""></a>レポート

デバイス レポート機能または単にデバイスの動作を理解することは、IT 部門が既知のデバイスの制御を維持するための基礎です。レポートを使用することで現在の環境をよりよく理解できます。環境だけでなくモバイル デバイスの機能も理解しようとするときは、次のようなことを確認します。

- 組織で使用されている iOS デバイスの数
- デバイスで実行されている iOS のバージョン
- デバイスにインストールされている企業アプリ
- 組織のデバイスが改造されているか

デバイスのインベントリおよびカスタマイズ可能なレポートを提供できる管理ソリューションの使用を検討します。このオプションを選択することにより、IT 部門はユーザーのデバイスについての詳細な情報をいっそう柔軟に探索できます。IT 部門は、社内およびクラウドで登録されたすべてのデバイスについてのレポートを入手できる必要があります。管理システムのレポート機能は、社内またはクラウドのどちらにあってもよく、両方であってもかまいません。そのような場合はハイブリッド ソリューションと呼ばれます。次の表を使用して、会社に適したレポート オプションを決定します。

### <a name="-"></a>レポート オプション︰ 長所と短所

以下の一覧で、各レポート オプションの長所と短所を確認してください。

- オンプレミス
    - 長所
        - 一元化されたレポート
        - IT 部門によって完全に管理される
        - カスタマイズ可能
        - オンプレミスで管理されているセキュリティ コントロール
    - 短所
        - オフプレミスに存在するデバイスをネイティブに列挙できない
        - クラウド ベースのソリューションと比較すると管理オーバーヘッドが大きい
- クラウド ベース
    - 長所
        - クラウド サービスに参加しているデバイスをレポートできる
        - コスト効率が高い
        - レポートの可用性 （どこからでもレポートを作成および表示できる）
        - オンプレミス ソリューションと比較すると管理コストが小さい
    - 短所
        - オンプレミスに存在するデバイスをネイティブに列挙できない
        - 通常、毎月サービスをサブスクライブする必要がある
- ハイブリッド
    - 長所
        - クラウド サービスに参加しているデバイスをレポートできる
        - コスト効率が高い
        - レポートの可用性 （どこからでもレポートを作成および表示できる）
        - オンプレミス管理ソリューションとの統合
    - 短所
        - 通常、毎月サービスをサブスクライブする必要がある

Microsoft Intune と System Center 2012 R2 を組み合わせることにより、オンプレミス デバイスとクラウド ベース デバイスの両方からレポートできます。配置管理器 には、アプリ レポート、ハードウェア インベントリ レポート、設定管理レポートなど、すぐに使用できる組み込みの UDM 用レポートが多数あります。PC 管理用とモバイル デバイス管理用にカスタム レポートや異なるレポートを作成する必要はありません。これらの機能は統合できます。

配置管理器 のレポート機能の詳細については、「[配置管理器 のレポートの概要](https://technet.microsoft.com/library/gg682105.aspx)」をご覧ください。

## <a name=""></a>コンピューティングと記憶域

新しいアプリが開発されて、ユーザーが自分のデバイスを使用してリモート アクセスしたとき、ソリューションが適切に計画されていない場合、アプリのパフォーマンスが低下する可能性があります。この設計の考慮事項ガイドではパフォーマンスについての詳細な考慮事項は示しませんが、管理インフラストラクチャに関する質問に答える必要があります。

- 会社で現在使用している管理ソリューションは、ユーザーのデバイスからアクセスされるアプリをサポートするプラットフォームの記憶域リソースおよびコンピューティング リソースを管理できますか。 
- 会社で現在使用されている管理ソリューションは、ユーザーのデバイスからアクセスされるアプリをサポートするプラットフォームのコンピューティング リソースおよび記憶域リソースを、事前に設定されているルールに従って増やすことができますか。現在使用されている管理ソリューションがこれら 2 つの要件に対応できない場合は、次の表で示されている 2 つの核心的要件に対応することによってコンピューティングおよび記憶域を管理できる管理ソリューションの使用を検討してください。

### <a name="-"></a>コンピューティングおよび記憶域管理機能︰ 長所と短所

以下の一覧で、各記憶域管理機能の長所と短所を確認してください。

- リソース プール
    - 長所
        - 異なる場所からコンピューティングおよび記憶域のプール リソースを割り当てることができる
        - 高レベルの可用性
        - リソース プールを利用できないソリューションより堅牢
    - 短所
        - リソース プールを利用できる管理ソリューションがほとんどない
        - データセンターでクラウド コンピューティング原理をまだ使用していない場合、実装の初期オーバーヘッドが高くなることがある
- 柔軟性
    - 長所
        - 需要に基づいてコンピューティングおよび記憶域プール リソースを動的に割り当てることができる
        - 高レベルの可用性
        - 実装後の管理が容易
    - 短所
        - 柔軟性機能を利用できる管理ソリューションがほとんどない
        - データセンターでクラウド コンピューティング原理をまだ使用していない場合、実装の初期オーバーヘッドが高くなることがある

System Center 2012 R2 は、リソース プールおよび柔軟性を使用して記憶域およびコンピューティングを管理できます。また、System 中心 2012 R2 では記憶域と差分ディスクの最適化が統合されており、ディスク データの大きな割合を複数の仮想ディスクの間で共有できるようにすることによって、記憶域の必要量が減り、記憶域コストが最適化されます。System Center 2012 R2 を使用して仮想化され、リモート ユーザーが使用するアプリによって使用されるサーバーは、このテクノロジを利用できます。

System Center 2012 R2 の記憶域機能の詳細については、「[System Center 2012 R2 の VMM の新機能](https://technet.microsoft.com/library/dn246490.aspx)」をご覧ください。 

## <a name=""></a>オートメーション

自動化を使用すると、準拠していないデバイスを修正でき、異なるレベルの非準拠重大度を割り当てることができます。BYOD のさまざまな領域で自動化の使用を考える必要があります。たとえば、モバイル デバイスによって使用される新しいサービスの展開をどのようにして自動化するか、 モバイル デバイスの承認プロセスをどのようにして自動化するか、などです。

示されているすべての BYOD サブドメインが自動化を利用できるように見えるかもしれませんが、リソースを自動化する責任は管理サブドメインにあります。自動化はオペレーティング システムに組み込むことができますが、その機能の拡張、および自動化の結果の監視とレポートに関する日々の IT 部門のタスクを軽減する手段の提供は、会社が使用する管理ソリューションで行う必要があります。System Center 2012 R2 での最も強力な自動化オプションは、Windows PowerShell です。System Center 2012 R2 の自動化の詳細については、「[与 Windows PowerShell 系统中心自动化 （Windows PowerShell を使用した 系统中心 の自動化）](https://technet.microsoft.com/library/dn507037(v=sc.20).aspx)」をご覧ください。ただし、堅牢性は劣りますがさらに単純なもう 1 つのタスク自動化タスクのオプションである、タスク シーケンスがあります。各オプションの長所と短所については、次の表を参考にしてください。

### <a name="-"></a>自動化オプション︰ 長所と短所

以下の一覧で、各自動化オプションの長所と短所を確認してください。

- Windows PowerShell
    - 長所
        - Windows オペレーティング システムとの統合
        - タスク シーケンスより堅牢
        - スクリプトを作成できる
        - プロシージャ、ループ、配列などのプログラミング原理を使用できる
        - 管理プラットフォームに含まれない機能を提供する
    - 短所
        - 使用するには高い技術スキルが必要
        - タスクによっては、最初の自動化スクリプトの作成に時間がかかることがある
- タスク シーケンス
    - 長所
        - 使いやすい
        - System Center で使用できるネイティブ機能
    - 短所
        - 機能が限られる
        - スクリプトを作成できない
        - 機能が 系统中心自体の一部のタスクに限定される

## <a name=""></a>展開とプロビジョニング

次のステップは、リモート デバイスに対するアプリの展開とプロビジョニングに関する考慮事項を理解することです。次の重要な 2 つの質問に答える必要があります。

- どのようにユーザーが自分のデバイスからアプリにアクセスするか
- どのように IT 部門がわかりやすく効果的な方法でユーザーにアプリをプロビジョニングするか

会社によって採用される管理ソリューションは、ユーザーが使用しているプラットフォームに関係なく、ソフトウェアの配布とプロビジョニングにも対応する必要があります。ユーザーは、デバイスから 1 つの場所に安全にアクセスして、作業に使用することを承認されているアプリをインストールできる必要があります。

この領域の 1 つの課題は、異なるプラットフォームを管理して、オンプレミスおよびクラウドで接続されるデバイスを IT 部門がすばやく識別できるように一元化された管理インターフェイスを維持することです。オンプレミスとクラウドの両方を統合し、Windows システムと非 Windows システムを管理できる管理プラットフォームを導入することを検討する必要があります。

オンプレミスの集中管理には、Configuration 管理器 を使用できます。このオプションを使用することで、IT 部門はエンタープライズ登録機能を利用して会社の にデバイスを登録できます。 配置管理器服务器配置管理器 を使用してデバイスを管理する方法の詳細については、「[配置管理器 と Microsoft Intune を使用してモバイル デバイスを管理する](https://technet.microsoft.com/library/jj884158.aspx)」をご覧ください。

Windows ベースのデバイスではなく他のプラットフォームを管理するには、Microsoft Intune クラウド サービスを利用できます。Microsoft Intune の企業ポータルを使用すると、ライセンスされたアプリを登録、管理、インストールできます。ユーザーはアプリに簡単にアクセスしてデバイスにアプリをインストールできます。 

>[!TIP] 
>Microsoft Intune[Microsoft Intune に関するページ](/intune/understand-explore/introduction-to-microsoft-intune)をご覧ください。 の詳細については、 

これら 2 つは異なるオプションですが、両方を統合して 1 つの場所からアプリの展開とプロビジョニングを行うことができます。次の表を参考にして、BYOD の設計に適したオプションを選択してください。

| **設計の要件**                                             | **展開とプロビジョニングのオプション**                |
|---------------------------------------------------------------------|--------------------------------------------------------|
| オンプレミスのデバイスだけにアプリを展開およびプロビジョニングする      | Microsoft System Center 2012                           |
| 会社の外部に存在するデバイスにアプリを展開およびプロビジョニングする   | Microsoft Intune                                       |
| Windows 以外のデバイスにアプリを展開およびプロビジョニングする                   | Microsoft Intune                                       |
| オンプレミスのデバイスだけにアプリを展開およびプロビジョニングする、会社の外部に存在するデバイスにアプリを展開およびプロビジョニングする、Windows 以外のデバイスにアプリを展開およびプロビジョニングする       | 配置管理器 と統合された Microsoft Intune
                                                                    
