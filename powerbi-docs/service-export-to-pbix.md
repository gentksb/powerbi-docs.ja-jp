---
title: "Power BI サービスからデスクトップにレポートをエクスポートする (プレビュー)"
description: "Power BI サービスから Power BI Desktop ファイルへのレポートのダウンロード"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: 30975e9192633043aed7e4196820ef34044b8fcb
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="export-a-report-from-power-bi-service-to-desktop-preview"></a>Power BI サービスからデスクトップにレポートをエクスポートする (プレビュー)
Power BI Desktop では、レポートを保存して **[発行]** を選ぶことにより、レポートを Power BI サービスにエクスポートできます (*ダウンロード* ともいいます)。 反対の方向にもエクスポートでき、Power BI サービスから Desktop にレポートをダウンロードできます。 どちらの方向でも、エクスポートされたファイルのファイル拡張子は *.pbix* です。

この記事の後半では、注意する必要のあるいくつかの制限事項と考慮事項について説明します。

![](media/service-export-to-pbix/power-bi-file-export.png)

## <a name="download-the-report-as-a-pbix"></a>レポートを .pbix としてダウンロードする
.pbix ファイルをダウンロードするには、次の手順に従います。

1. **Power BI サービス**で、ダウンロードするレポートを[編集ビュー](service-reading-view-and-editing-view.md)で開きます。
2. メニュー バーから、**[ファイル]、[レポートのダウンロード]** の順に選択します。
   
   > [!NOTE]
   > レポートをダウンロードするためには、レポートが 2016 年 11 月 23 日以降に [Power BI Desktop で作成されている](guided-learning/publishingandsharing.yml#step-2)か、それ以降に更新されている必要があります。 これに該当しない場合、Power BI サービスの *[レポートのダウンロード (プレビュー)]* メニュー オプションは淡色表示されます。
   > 
   > 
3. .pbix ファイルが作成されている間、進行状況が状態バナーに表示されます。 .pbix ファイルの準備ができると、開くか保存するように求められます。 ファイルの名前はレポートのタイトルと同じです。
   
    ![](media/service-export-to-pbix/power-bi-save-pbix.png)
   
    Power BI サービス (app.powerbi.com) または Power BI Desktop で .pbix ファイルを開くオプションが表示されるようになります。     
4. レポートを Desktop ですぐ開くには、**[開く]** を選びます。  まだ行っていない場合は、[Power BI Desktop をインストール](desktop-get-the-desktop.md)します。
   
    レポートを Desktop で開くとき、Power BI サービスのレポートで使用できる一部の機能が Desktop では使用できないという警告メッセージが表示されることがあります。
   
    ![](media/service-export-to-pbix/power-bi-export-to-pbix_2.png)
5. Power BI サービスでレポートを開くには、**[保存]** を選んだ後、**[データの取得]** を使って .pbix ファイルを保存した場所に移動します。
   
    ![](media/service-export-to-pbix/power-bi-get-data.png)

## <a name="considerations-and-troubleshooting"></a>考慮事項とトラブルシューティング
Power BI サービスからの *.pbix* ファイルのダウンロード (エクスポート) に関しては、重要な考慮事項と制限事項がいくつかあります。

* ファイルをダウンロードするには、レポートの編集アクセス権限が必要です。
* レポートが **Power BI Desktop** で作成され、 **Power BI サービス** に *発行* されているか、.pbix ファイルがサービスに *アップロード* されている必要があります。
* レポートは、2016 年 11 月 23 日以降に更新または発行されている必要があります。 この日より前に発行されたレポートはダウンロードできません。
* この機能は、**Power BI サービス** (コンテンツ パックを含みます) でもともと作成されたレポートには使用できません。
* ダウンロードしたファイルを開くときは常に、最新バージョンの **Power BI Desktop** を使用する必要があります。 最新バージョンではない **Power BI Desktop** では、ダウンロードした *.pbix* ファイルを開くことができない場合があります。
* データをエクスポートする機能を管理者が無効にしている場合、この機能は **Power BI サービス**に表示されません。

## <a name="next-steps"></a>次の手順
この機能に関しては、**Guy in a Cube** の簡単なビデオをご覧ください。

<iframe width="560" height="315" src="https://www.youtube.com/embed/ymWqU5jiUl0" frameborder="0" allowfullscreen></iframe>

また、**Power BI サービス**の使い方を知るのに役立つ記事を以下に示します。

* [Power BI のレポート](service-reports.md)
* [Power BI - 基本的な概念](service-basic-concepts.md)

以下のガイドは、**Power BI Desktop** をインストールした後で、すばやく作業を開始するのに役立ちます。

* [Power BI Desktop の概要](desktop-getting-started.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。   
