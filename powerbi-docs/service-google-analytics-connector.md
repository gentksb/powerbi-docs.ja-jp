---
title: 'サード パーティのサービス: Power BI Desktop のGoogle アナリティクス コネクタ'
description: 'サード パーティのサービス: Power BI Desktop のGoogle アナリティクス コネクタ'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 20deb3f0b2f42bfcde66cb685fd6242f7b4a4be3
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2018
ms.locfileid: "39327018"
---
# <a name="google-analytics-connector-for-power-bi-desktop"></a>Power BI Desktop のGoogle アナリティクス コネクタ
> [!NOTE]
> Power BI Desktop に含まれる Google アナリティクス コンテンツ パックおよびコネクタは、Google アナリティクス Core Reporting API に依存します。 そのため、機能と可用性は、時間の経過と共に変わる場合があります。
> 
> 

Google アナリティクス データへの接続には、**Google アナリティクス** コネクタを使用します。 接続するには、次の手順を実行します。

1. **Power BI Desktop** で、**[ホーム]** リボン タブにある **[データの取得]** を選択します。
2. **[データの取得]** ウィンドウで、左側のウィンドウのカテゴリから **[Online Services]** を選択します。
3. 右側のウィンドウに表示されている選択肢から、 **[Google アナリティクス]** を選択します。
4. ウィンドウの下部にある **[接続]** を選択します。  
   ![](media/service-google-analytics-connector/tps_googleanalytics_1.png)

コネクタがサード パーティ サービスであることを説明するダイアログが表示され、機能と可用性が時間の経過と共に変わる場合があるという警告やその他の説明が表示されます。  
![](media/service-google-analytics-connector/tps_googleanalytics_2.png)

**[続行]** を選択すると、Google アナリティクスにサインインするように求められます。  
![](media/service-google-analytics-connector/tps_googleanalytics_3.png)

資格情報を入力すると、Power BI がオフライン アクセスを求めていることが示されます。 これが、**Power BI Desktop** を使用して、Google アナリティクスのデータにアクセスする方法です。  

同意すると、**Power BI Desktop** に、現在サインインしていることを示すメッセージが表示されます。  
![](media/service-google-analytics-connector/tps_googleanalytics_5.png)

**[接続]** を選択すると、Google アナリティクス データが **Power BI Desktop** に接続され、データが読み込まれます。  
![](media/service-google-analytics-connector/tps_googleanalytics_6.png)

## <a name="changes-to-the-api"></a>API への変更
すべての変更に調和するように更新プログラムをリリースすることを試みていますが、API は、生成するクエリの結果に影響を与えるように変更される可能性があります。 特定のクエリがサポートされなくなる可能性もあります。 このような依存関係があることから、このコネクタの使用中にはクエリの結果は保証できません。

Google アナリティクス API への変更の詳細については、[変更履歴](https://developers.google.com/analytics/devguides/changelog)を参照してください。

