---
title: Power BI Desktop で Impala データベースに接続する
description: Power BI Desktop で Impala データベースに簡単に接続して使用する
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 781e9f6813fee63b7c5d83a2e7e60e1ed1eeedc0
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2018
ms.locfileid: "39326995"
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>Power BI Desktop で Impala データベースに接続する
Power BI Desktop では、**Impala** データベースに接続し、Power BI Desktop の他のデータ ソースの場合と同様に基になっているデータを使用できます。

## <a name="connect-to-an-impala-database"></a>Impala データベースに接続する
**Impala** データベースに接続するには、Power BI Desktop の **[ホーム]** リボンで **[データの取得]** を選択します。 左側のカテゴリから **[データベース]** を選択します。**[Impala]** が表示されます。

![](media/desktop-connect-impala/connect_impala_2.png)

表示された **[Impala]** ウィンドウ内のボックスに Impala サーバーの名前を入力するか、貼り付けます。**[OK]** をクリックします。 Power BI にデータを直接**インポート**したり、**DirectQuery** を使用したりできます。 詳しくは、「[Power BI Desktop の DirectQuery](desktop-use-directquery.md)」をご覧ください。

![](media/desktop-connect-impala/connect_impala_3a.png)

プロンプトが表示されたら、資格情報を入力するか、匿名で接続します。 Impala コネクタは、匿名、基本 (ユーザー名とパスワード)、Windows 認証をサポートします。

![](media/desktop-connect-impala/connect_impala_4.png)

> [!NOTE]
> 特定の **Impala** サーバーのユーザー名とパスワードを入力した場合、Power BI Desktop は以降もその同じ資格情報を使用して接続を試みます。 これらの資格情報を変更するには、**[ファイル]、[オプションと設定]、[データ ソース設定]** の順に移動します。
> 
> 

接続が正常に行われたら、**[ナビゲーター]** ウィンドウが開き、サーバー上で使用可能なデータが表示されます。その中から 1 つまたは複数の要素を選択し、**Power BI Desktop** にインポートして使用することができます。

![](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>考慮事項と制限事項
**Impala** コネクタにはいくつかの制限事項と考慮事項があるので注意してください。

* Impala コネクタは、3 つのサポートされた認証メカニズムのいずれかを使用して、オンプレミス データ ゲートウェイでサポートされます。

## <a name="next-steps"></a>次の手順
Power BI Desktop を使用して接続できるデータの種類は他にもあります。 データ ソースの詳細については、次のリソースを参照してください。

* [Power BI Desktop とは何ですか?](desktop-what-is-desktop.md)
* [Power BI Desktop のデータ ソース](desktop-data-sources.md)
* [Power BI Desktop でのデータの整形と結合](desktop-shape-and-combine-data.md)
* [Power BI Desktop で Excel ブックに接続する](desktop-connect-excel.md)   
* [Power BI Desktop にデータを直接入力する](desktop-enter-data-directly-into-desktop.md)   

