---
title: "ビジネス ニーズの特定"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 8/1/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 85783069-14fb-4ead-a159-657d694eb1a7
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 03f66bb41e7669070de684ae847c6b109e8ffd69
ms.sourcegitcommit: 45ffbe57b8a2ff1ba6d26efde7f4e2fee8495593
translationtype: MT
---
# <a name="-"></a>ビジネス ニーズを特定する

>[!NOTE]
>このトピックは、大規模な設計の考慮事項ガイドの一部です。ガイドの先頭から開始する場合は、[メイン トピック](mdm-design-considerations-guide.md)を参照してください。このガイド全体のダウンロード可能なコピーを入手する場合は、[TechNet ギャラリー](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)にアクセスしてください。

要件は会社によって異なります。会社が同じ業界に属する場合でも、実際の事業要件は異なることがあります。業界のベスト プラクティスを活用することはできますが、モバイル デバイス管理ソリューションの要件を最終的に特定するのはその会社のビジネス ニーズです。ビジネス ニーズを特定するために、次の質問に答えてください。

- 
            **ユーザー**︰ モビリティを採用する際の重要な点の 1 つは、ユーザーをモビリティ ソリューションの中心に置き、ユーザーの生産性の向上を実現すると同時に、会社のデータのセキュリティと可用性を維持することです。これはユーザーの要件を理解する上で重要です。
    - ユーザーは自分のデバイスを持ち込み、会社のリソースにアクセスできますか。
        - できる場合、会社のリソースにアクセスするための要件は何ですか。
    - 会社には複数のユーザー ニーズが存在しますか。
        - 存在する場合、各ユーザーのプロファイルはモバイル戦略にどのような影響を与えますか。
    - ユーザーは、オンプレミス環境でアクセスできるすべてのアプリにモバイル デバイスからアクセスできますか。
        - できない場合、ユーザーはどのアプリを利用できますか。
            - それらのアプリは、サポートされているすべてのモバイル デバイス プラットフォームで利用できますか。
            - サポートされているすべてのモバイル デバイス プラットフォームで実行するために、アプリを改良したり、更新したりする必要はありますか。
    - ユーザーにとって必要なのは、電子メール （カレンダー、連絡先、タスクを含む） の機能に基本的なアクセスができることだけですか。

- 
            **デバイスの所有権**︰ 会社のデバイス所有権ポリシーを理解する必要があります。
    - モバイル デバイスの所有者は誰ですか。 
        - 社員ですか。
        - 会社ですか。  
        - 両方でしょうか。
- 
            **プラットフォーム**︰ 会社で使用されるモバイル デバイス オペレーティング システムの把握は、導入とサポートに関する決定を行うために非常に重要となります。
    - どのモバイル デバイス用オペレーティング システムがサポートされますか。
        - Android 的 ですか。
        - iOS ですか。
        - Windows ですか。
        - Windows Phone ですか。
        - 全部ですか。
        - 上記の選択肢の組み合わせですか。
    - どのモバイル OS バージョンがサポートされますか。
        - 最新版のみですか。
        - 現行-1 （現行バージョンとその前のバージョン） ですか。
- 
            **アプリケーション**︰ モビリティを採用する大きな理由は生産性の向上であるため、従業員が使用するアプリケーション （アプリ） は、組織で使用されるすべてのモバイル デバイス オペレーティング システムで実行できる必要があります。これは考慮するべき重要な点です。なぜなら、最も重要なアプリをモバイル環境で完全に携帯可能にする企業もあれば、選択肢を理解した上でなければアプリをモバイル デバイスに展開しない企業もあるからです。個々のアプリの要件を特定するために、次の質問に答えてください。
    - アプリにはユーザーのデバイスからインターネットでアクセスする必要がありますか。 
    - アプリはユーザーの個人情報を収集しますか。
        - 集める場合、インストールの際、アプリはプライバシーの問題とデータの収集についてユーザーに通知しますか。
    - アプリは、クラウド サービスとの統合を必要としますか。
        - アプリは特定のオペレーティング システムで実行されるように開発されましたか。または、どのようなオペレーティング システムでも実行できますか。
    - ユーザーが自分のデバイスからリモート デスクトップ経由でアプリを利用できるようにする予定ですか。
    - アプリは企業リソースに常時アクセスする必要がありますか。あるいは、オフライン モードで実行できますか。
    - アプリはソーシャル ネットワークと統合されていますか。
    - すべてのアプリを BYOD 利用可能にしますか。
    - これらのアプリをユーザーのデバイスにどのようにして展開する予定ですか。
    - これらのアプリの展開オプションにはどのようなものがありますか。
    - インストール要件はターゲット デバイスによって変わりますか。それとも、同じですか。
    - 各アプリをインストールするために、ターゲット デバイスにどのくらいの領域が必要ですか。 
    - ユーザーのデバイスからバックエンドのアプリ サーバーにネットワーク経由でデータを転送するとき、アプリはデータを暗号化しますか。
    - アプリは離れた場所からネットワーク経由でアンインストールできますか。あるいは、デバイスのコンソール経由でアンインストールする必要がありますか。
    - 会社では、パートナーの SaaS アプリのデータにアクセスできるようにする必要はありますか。
    - アプリは待機時間の長いネットワークで動作しますか。 
    - アプリは認証機能を提供しますか。
        - 提供する場合、どのような認証方法をアプリは使用しますか。

この作業の間、会社がモバイル デバイスに関して管理とコンプライアンスのポリシーを既に用意しているか確認し、そのポリシーがモバイル デバイスの管理ソリューションの選択にどのような影響を与えるのか評価する必要もあります。

>[!TIP] 
> 各回答をメモし、答えの裏側にある論理的根拠を理解します。次のセクションでは、利用可能なオプションと各オプションの長所と短所を確認します。 以上の質問に答えると、ビジネス ニーズに最適なソリューションを選択できるようになります。


