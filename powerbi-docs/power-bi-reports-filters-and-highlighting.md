---
title: Power BI レポートのフィルターと強調表示について
description: Power BI レポートのフィルターと強調表示について
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/26/2018
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: de4fc463b02e8cae59f20216b5b1d30be431ae98
ms.sourcegitcommit: fb1885da7cf11367660edbf7b7346dc039ee9b5d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "47187170"
---
# <a name="about-filters-and-highlighting-in-power-bi-reports"></a>Power BI レポートのフィルターと強調表示について
***フィルター処理***を実行すると、絞り込んだデータ以外のすべてのデータが削除されます。  ***強調表示***はフィルター処理ではありません。データが削除されることはなく、表示されるデータのサブセットが強調表示され、強調表示対象外のデータは淡色表示になります。

Power BI ではさまざまな方法でレポートをフィルター処理および強調表示できます。 すべての情報をまとめて説明すると混乱するので、次のように分けて説明します。

* フィルターと強調表示の概要 (この記事)
* [編集ビューや独自レポートでフィルターと強調表示を作成して使用する](power-bi-report-add-filter.md)方法。 レポートの編集権限がある場合、レポートでフィルターと強調表示を作成、変更、削除できます。
* [共有レポートまたはレポート読み取りビューでフィルターと強調表示を使用する](consumer/end-user-reading-view.md)方法。 できることには限りがありますが、それでもさまざまなフィルター処理と強調表示のオプションを使用できます。  
* [編集ビューで使用できるフィルターと強調表示のコントロールの詳細なツアー](consumer/end-user-report-filter.md)。フィルターの種類の詳細 (例: 日付と時刻、数値、テキスト) や、基本オプションと詳細オプションの違いなどです。
* フィルターと強調表示の既定の動作を理解した後は、[ページの視覚エフェクトが相互にフィルターおよび強調表示する方法を変更する方法を学習](consumer/end-user-interactions.md)してください。

> [!TIP]
> Power BI はどのようにしてデータの関連方法を認識しているのでしょうか?   Power BI は基となる[データモデル](https://support.office.com/article/Create-a-Data-Model-in-Excel-87e7a54c-87dc-488e-9410-5c75dbcb0f7b?ui=en-US&rs=en-US&ad=US)内の各種テーブルとフィールド間のリレーションシップを使用して、レポート ページ上の項目を相互に対話させます。
> 
> 

## <a name="introduction-to-filters-and-highlighting-in-reports-using-the-filters-pane"></a>フィルター ウィンドウを使用したレポートでのフィルターと強調表示の概要
 この記事では、Power BI サービスでのフィルター処理と強調表示の概要を示します。  ただし、操作は Power BI Desktop の場合とほぼ同じです。  

![](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-reading-view.png)

フィルターと強調表示は、**フィルター** ウィンドウを使用して、またはレポート自体で直接選択することによって (アドホック、後述)、適用できます。 フィルター ウィンドウには、レポートで使用されているテーブルとフィールド、および適用されているフィルター (ある場合) が表示されます。 フィルターは、**ページ レベル**、**レポート レベル**、**ドリルスルー**、**ビジュアル レベル**に分かれます。  レポート キャンバスで視覚エフェクトを選択した場合は、ビジュアル レベル フィルターだけが表示されます。

> [!TIP]
> フィルターの横に **[All]** と表示されている場合は、フィールド全体がフィルターとして含まれることを意味します。  たとえば、次のスクリーンショットの **[Chain(All)]** は、このレポート ページにすべてのストア チェーンに関するデータが含まれることを示します。  一方、レポート レベル フィルターの **[FiscalYear is 2013 or 2014]** は、レポートに 2013 年および 2014 年の会計年度のデータのみが含まれることを示します。
> 
> 

## <a name="filters-in-reading-view-versus-editing-view"></a>読み取りビューのフィルターと編集ビューのフィルター
レポートとの対話には 2 つのモード ([読み取りビューと編集ビュー](consumer/end-user-reading-view.md)) があります。  使用できるフィルター処理機能は、どのモードを使用しているかによって異なります。

* 編集ビューでは、レポート、ページ、ドリルスルー、ビジュアルの各フィルターを追加できます。 モバイル アプリで開く場合でも、レポートを保存すると、フィルターはレポートと共に保存されます。 読み取りビューでレポートを表示しているユーザーは、追加したフィルターと対話できますが、新しいフィルターを追加することはできません。
* 読み取りビューでは、レポートに既に存在するすべてのフィルターと対話して、行った選択の内容を保存することができます。  ただし、新しいフィルターを追加することはできません。

### <a name="the-filters-pane-in-reading-view"></a>読み取りビューのフィルター ウィンドウ
読み取りビューでしかレポートにアクセスできない場合、フィルター ウィンドウは次のようになります。

![](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading-view.png)

レポートのこのページには、6 個のページ レベル フィルターと 1 個のレポート レベル フィルターがあります。

ビジュアル レベル フィルターが存在するかどうかを確認するには、ビジュアルを選択します。 次の図では、バブル チャートに 6 個のフィルターが適用されています。

![](media/power-bi-reports-filters-and-highlighting/power-bi-filter-visual-level.png)

読み取りビューでは、既存のフィルターを変更することによってデータを調べます。 モバイル アプリでレポートを開く場合でも、加えた変更の内容はレポートと共に保存されます。 そのしくみについては、「[Power BI サービスのレポートの読み取りビューと編集ビュー](consumer/end-user-reading-view.md)」の記事を参照してください。

### <a name="the-filters-pane-in-editing-view"></a>編集ビューのフィルター ウィンドウ
レポートに対する所有者権限を持つユーザーが編集ビューでレポートを開くと、**フィルター**は使用可能な複数の編集ウィンドウの 1 つとして表示されます。

![](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-editing-view.png)

前の読み取りビューと同じように、レポートのこのページには 6 個のページ レベル フィルターと 1 個のレポート レベル フィルターがあります。 また、バブル チャートを選択すると、6 個のビジュアル レベル フィルターが適用されていることがわかります。

ただし、編集ビューでは、フィルターと強調表示に関してさらに多くの機能を使用できます。 最大の違いは、新しいフィルターを追加できることです。 追加およびその他の方法については、「[Power BI でのレポートへのフィルターの追加](power-bi-report-add-filter.md)」をご覧ください。

## <a name="ad-hoc-filtering-and-highlighting"></a>アドホックのフィルター処理と強調表示
レポート キャンバスでフィールドを選択すると、ページの他の部分がフィルター処理および強調表示されます。 同じビジュアルの空いている領域を選択すると、フィルターおよび強調表示が解除されます。 この種のフィルター処理と強調表示では、データの影響を簡単に調べることができます。 この種のクロスフィルター処理とクロス強調表示を微調整する場合は、「[Power BI レポートでの視覚化の相互作用](consumer/end-user-interactions.md)」を参照してください。

![](media/power-bi-reports-filters-and-highlighting/power-bi-adhoc-filter.gif)

レポートの終了時に、変更内容が保存されます。 フィルター処理を取り消し、レポート作成者が設定したフィルター処理、スライス、ドリル、並べ替えに戻すには、一番上のメニュー バーから **[既定値にリセット]** を選択してください。

![](media/power-bi-reports-filters-and-highlighting/power-bi-reset-to-default.png)

## <a name="next-steps"></a>次の手順
[フィルターとの対話と強調表示 (読み取りビュー)](consumer/end-user-reading-view.md)

[レポートへのフィルターの追加 (編集ビュー)](power-bi-report-add-filter.md)

[レポート フィルターの使用方法](consumer/end-user-report-filter.md)

[レポートのビジュアル相互間のクロスフィルター処理とクロス強調表示を変更する方法](consumer/end-user-interactions.md)

[Power BI のレポート](consumer/end-user-reports.md)で詳細を確認する

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

