---
title: レポートに視覚エフェクト、ページ、ドリルスルー、またはレポートのフィルターを追加する
description: Power BI でレポートにページ フィルター、視覚化フィルター、またはレポート フィルターを追加する
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/26/2018
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 3758415dc41a5f94419193240d4ce71aa4aca1d8
ms.sourcegitcommit: fb1885da7cf11367660edbf7b7346dc039ee9b5d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "47187216"
---
# <a name="add-a-filter-to-a-power-bi-service-report-in-editing-view"></a>Power BI サービス レポートへのフィルターの追加 (編集ビュー)
> [!TIP]
> 最初に「[Power BI レポートのフィルターと強調表示について](power-bi-reports-filters-and-highlighting.md)」を読むことをお勧めします。

この記事では、Power BI サービスの場合の例を示します。 ただし、手順は Power BI Desktop の場合とほぼ同じです。
> 
> 

## <a name="what-is-the-difference-between-report-filters-in-editing-view-versus-reading-view"></a>編集ビューと読み取りビューでのレポート フィルターの違い
レポートとの対話には 2 つのモードがあります。[読み取りビュー](consumer/end-user-reading-view.md)と[編集ビュー](service-interact-with-a-report-in-editing-view.md)です。  使用できるフィルター処理機能は、どのモードを使用しているかによって異なります。

* 編集ビューでは、レポート フィルター、ページ フィルター、ビジュアル フィルターを追加できます。 レポートを保存すると、フィルターが一緒に保存されます。 読み取りビューでレポートを表示しているユーザーは、追加したフィルターと対話することができます。
* 読み取りビューでは、レポートに既に存在しているレポート、ドリルスルー、ページ、ビジュアルの各フィルターと対話できますが、新しいフィルターを追加することはできません。 ただし、モバイル アプリでレポートを表示する場合でも、レポートを終了し、後で戻る場合でも、フィルター ウィンドウで行う変更の内容はレポートと共に保存されます。  

> [!NOTE]
> この記事では、レポートの**編集ビュー**でフィルターを作成する方法について説明します。  読み取りビューのフィルターの詳細については、[レポートの読み取りビューのフィルターとの対話](consumer/end-user-reading-view.md)に関するページを参照してください。


## <a name="filters-available-in-the-power-bi-filters-pane"></a>Power BI の *[フィルター]* ウィンドウで使用できるフィルター
Desktop と Power BI サービスのどちらを使用しているかに関係なく、フィルター ウィンドウはレポート キャンバスの右側に表示されます。 フィルター ウィンドウが表示されない場合は、右上隅にある ">" アイコンを選択して展開してください。

フィルターには次の 4 つの種類があります。

- **ページ フィルター**は、レポート ページ上のすべてのビジュアルに適用されます。     
- **ビジュアル フィルター**は、レポート ページ上の単一のビジュアルに適用されます。    
- **ドリルスルー フィルター**は、レポート内の単一のエンティティーに適用されます。    
- **レポート フィルター**は、レポート内のすべてのページに適用されます。    

    ![読み取りビューのフィルター ウィンドウ](media/power-bi-report-add-filter/power-bi-add-filter-reading-view.png)

レポートから離れてもフィルターは*持続する*ため、Power BI では、フィルター、スライサー、その他のデータ ビューに行った変更が保持されます。 そのため、レポートに戻ったとき、前回終了したところから再開できます。 フィルターの変更を残さない場合、一番上にあるメニュー バーから **[既定値にリセット]** を選択してください。

![永続的フィルター ボタン](media/power-bi-report-add-filter/power-bi-reset-to-default.png)

## <a name="add-a-filter-to-a-specific-visualization-aka-visual-filter"></a>特定の視覚化へのフィルター (ビジュアル フィルター) の追加
これを行うには、次の 2 つの方法があります。 

* 1 つは、視覚化によって既に使われているフィールドにフィルターを追加する方法です。
* もう 1 つは、視覚化によってまだ使われていないフィールドを識別し、そのフィールドを**ビジュアル レベル フィルター** バケットに直接追加する方法です。

### <a name="by-filtering-the-fields-already-in-the-visualization"></a>視覚化の既存フィールドのフィルター処理
1. [編集ビューでレポート](consumer/end-user-reading-view.md)を開きます。
   
   ![](media/power-bi-report-add-filter/power-bi-edit-view.png)
2. 視覚化およびフィルター ウィンドウとフィールド ウィンドウがまだ開いていない場合は開きます。
   
   ![](media/power-bi-report-add-filter/power-bi-display-panes.png)
3. ビジュアルを選んでアクティブにします。 ビジュアルで使用されているすべてのフィールドが **[フィールド]** ウィンドウで識別され、**[フィルター]** ウィンドウの **[ビジュアル レベル フィルター]** 見出しの下にリストされます。
   
   ![](media/power-bi-report-add-filter/power-bi-default-visual-filter.png)
4. この時点で、視覚化によって既に使われているフィールドにフィルターを追加します。 
   
   * **[ビジュアル レベル フィルター]** 領域まで下にスクロールし、矢印を選んでフィルター処理するフィールドを展開します。 この例では **StoreNumberName** をフィルター処理します。
     
      ![](media/power-bi-report-add-filter/power-bi-visual-level-filter.png) 
   * フィルター処理コントロールとして **[基本]**、**[詳細]**、または **[上位 N]** を設定します (「[レポート フィルターの使用方法](consumer/end-user-report-filter.md)」をご覧ください)。 この例では、基本フィルター処理を選択し、10、11、15、18 の数字の横にチェックマークを付けます。
     
      ![](media/power-bi-report-add-filter/power-bi-basic-filters.png) 
   * ビジュアルに新しいフィルターが反映されます。 レポートをフィルターとともに保存すると、レポート閲覧者が読み取りビューでフィルターと対話でき、値を選んだりクリアしたりすることができます。
     
      ![](media/power-bi-report-add-filter/power-bi-filter-effect.png)
5. 次に、まったく新しいフィールドをビジュアル レベル フィルターとして視覚化に追加しましょう。
   
   * [フィールド] ウィンドウで新しいビジュアル レベル フィルターとして追加するフィールドを選び、**[ビジュアル レベル フィルター]** 領域までドラッグします。  この例では、**[District Manager (地区マネージャー)]** を **[ビジュアル レベル フィルター]** バケットにドラッグし、Andrew Ma だけを選択します。 
     
      ![](media/power-bi-report-add-filter/power-bi-andrew.png)
   * **[District Manager (地区マネージャー)]** は、視覚化自体に追加されるのでは*ありません*。 視覚化はまだ **[StoreNumberName]** を軸とし、**[This Year Sales (今年の売上)]** を値として構成されています。  
     
      ![](media/power-bi-report-add-filter/power-bi-visualization.png)
   * また、視覚化自体は、指定した店舗での Andrew の今年の売上だけを表示するようにフィルター処理されます。
     
     ![](media/power-bi-report-add-filter/power-bi-filtered-andrew.png)

## <a name="add-a-filter-to-an-entire-page-aka-page-view-filter"></a>ページ全体へのフィルター (ページ ビュー フィルター) の追加
1. [編集ビューでレポート](consumer/end-user-reading-view.md)を開きます。
2. 視覚化およびフィルター ウィンドウとフィールド ウィンドウがまだ開いていない場合は開きます。
3. [フィールド] ウィンドウで新しいページ レベル フィルターとして追加するフィールドを選び、**[ページ レベル フィルター]** 領域までドラッグします。  
4. フィルターを適用する値を選び、フィルター処理コントロールとして **[基本]** または **[詳細]** を設定します (「[レポート フィルターの使用方法](consumer/end-user-report-filter.md)」をご覧ください)。
   
   ページでこのフィルターの影響を受けるすべての視覚化が、変更を反映するように再描画されます。 
   
   ![](media/power-bi-report-add-filter/filterpage.gif)

レポートをフィルターとともに保存すると、レポート閲覧者が読み取りビューでフィルターと対話でき、値を選んだりクリアしたりすることができます。

## <a name="add-a-drillthrough-filter"></a>ドリルスルー フィルターを追加する
Power BI サービスと Power BI Desktop のドリルスルーでは、サプライヤー、顧客、メーカーなど、特定のエンティティに注目した "*ドリルスルー先*" レポート ページを作成できます。 ユーザーは、他のレポート ページでそのエンティティのデータ ポイントを右クリックして、フォーカスされたページにドリルスルーできます。

### <a name="create-a-drillthrough-filter"></a>ドリルスルー フィルターを作成する
最初に、お客様の収益性のサンプルを編集ビューで開きます。 Executive ビジネス領域に注目したページを作成します。   

1. レポートに新しいページを追加し、「**Team Executive**」という名前を付けます。 これが "*ドリルスルー先*" ページになります。
2. チーム エグゼクティブ ビジネス分野の主要指標を追跡するための視覚化を追加します。    
3. [ドリル スルー フィルター] ウェルに **[Executive] > [Executive Name]** を追加します。    
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough-filter.png)
   
    レポート ページに戻る矢印が追加されることに注意してください。  戻る矢印を選ぶと、"*ドリルスルー元*" のレポート ページ (ドリルスルーを選んだときのページ) に戻ります。 戻る矢印は、読み取りビューでのみ機能します。
   
     ![](media/power-bi-report-add-filter/power-bi-back-arrow.png)

### <a name="use-the-drillthrough-filter"></a>ドリルスルー フィルターを使う
ドリルスルー フィルターのしくみを見てみましょう。

1. **[Team Scorecard]** レポート ページから始めます。    
2. Andrew Ma が自分のデータだけにフィルター処理された [Team Executive] レポート ページを見たいものとします。  左上の面グラフで任意の緑のデータ ポイントを右クリックして、[ドリルスルー] メニュー オプションを開きます。
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough.png)
3. **[ドリルスルー] > [Team Executive]** を選んで、**[Team Executive]** という名前のレポート ページにドリルスルーします。 このページは、右クリックしたデータ ポイント (この場合は Andrew Ma) に関する情報を表示するようにフィルター処理されています。 ドリルスルー フィルターにあるフィールドのみが、ドリルスルー レポート ページに渡されます。  
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough-executive.png)

## <a name="add-a-filter-to-an-entire-report-aka-report-filter"></a>レポート全体へのフィルターの追加 (レポート フィルター)
1. [編集ビューでレポート](consumer/end-user-reading-view.md)を開きます。
2. 視覚化およびフィルター ウィンドウとフィールド ウィンドウがまだ開いていない場合は開きます。
3. [フィールド] ウィンドウで新しいレポート レベル フィルターとして追加するフィールドを選び、**[レポート レベル フィルター]** 領域までドラッグします。  
4. フィルターを適用する値を選びます (「[レポート フィルターの使用方法](consumer/end-user-report-filter.md)」をご覧ください)。

    アクティブ ページおよびレポート内のすべてのページ上のビジュアルに、新しいフィルターが反映されます。 レポートをフィルターとともに保存すると、レポート閲覧者が読み取りビューでフィルターと対話でき、値を選んだりクリアしたりすることができます。

1. 戻る矢印を選んで、前のレポート ページに戻ります。

## <a name="considerations-and-troubleshooting"></a>考慮事項とトラブルシューティング

- ビジュアル レベル フィルターとページ レベル フィルターが異なる結果を返すことがあります。  たとえば、ビジュアル レベル フィルターを追加すると、Power BI は集計結果をフィルター処理します。  既定の集計は合計ですが、[集計の種類を変更](service-aggregates.md)することもできます。  

    その後、ページ レベル フィルターを追加すると、Power BI は集計せずにフィルター処理します。  これは、ページには、それぞれさまざまな集計の種類を利用できるさまざまなビジュアルが適用されている可能性があるためです。  そのため、フィルターは各データ行に適用されます。

- [フィールド] ウィンドウが表示されない場合は、レポートが[編集ビュー](service-interact-with-a-report-in-editing-view.md)になっていることを確認してください。    
- フィルターに多くの変更を加えた後で、レポート作成者の初期設定に戻す場合、一番上のメニュー バーから **[既定値にリセット]** を選択します。

## <a name="next-steps"></a>次の手順
 [レポート フィルターの使用方法](consumer/end-user-report-filter.md)

  [レポート内のフィルターと強調表示](power-bi-reports-filters-and-highlighting.md)

[レポートの読み取りビューでのフィルターとの対話と強調表示](consumer/end-user-reading-view.md)

[レポートのビジュアル相互間のクロスフィルター処理とクロス強調表示を変更する方法](consumer/end-user-interactions.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

