---
title: 審閱集的高級 eDiscovery 儀表板
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 使用高級 eDiscovery 儀表板做為複查集，以快速分析您的主體，以找出可協助您開發考核策略的趨勢或關鍵統計資料。
ms.openlocfilehash: 36f30689047eec7ff2c2c49c6b0d54f1a60470e4
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741694"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets"></a>審閱集的高級 eDiscovery 儀表板

在高級 eDiscovery 中的某些案例中，您可能需要檢查大量的檔和電子郵件訊息。 開始審查程式之前，您可能會想要快速分析您的主體，以找出可協助您開發考核策略的趨勢或重要統計資料。 若要這麼做，您可以使用 Advanced eDiscovery 儀表板進行審核，以快速分析您的主體。

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a>步驟1：在審閱集儀表板上建立小工具

1. 在安全性 & 規範中心內，移至**eDiscovery > Advanced ediscovery** ，以顯示組織中案例的清單。
  
2. 選取現有的案例。
  
3. 按一下 [**複查集**] 索引標籤，然後選取一種複查集。
  
4. 在 [**個別結果**] 下拉式清單中，按一下 [**搜尋設定檔視圖**]。 

   ![DashbordPivot](../media/dashboardpivot.png)

   隨即會顯示 [**搜尋設定檔視圖**] 頁面。第一次顯示此頁面時，會顯示三個預設構件。

   ![儀表板](../media/dashboardonly.png)
  
5. 按一下**新的小工具**，然後選取下列其中一個專案：

   ![新增小工具下拉式清單](../media/NewWidgetDropdownBox.png)

   - **從文件庫選擇：** 會顯示小元件的預設文件庫。 按一下一個小工具，然後按一下 [**新增**]，將其新增至 [**搜尋設定檔視圖**] 頁面上的小工具。
  
   - **建立自訂構件：** 顯示可讓您用來設定自訂構件的飛彈出頁面。 

6. 若要建立自訂的小工具，請在 [**新增小**工具] 飛入頁面上執行下列動作：

   ![建立小工具](../media/addwidget.png)

    a. 輸入構件的名稱，它會顯示在 [widget] 標題列中。 需要命名小工具，但識別小工具資料有説明。

    b. 在 [**選擇樞紐分析表**] 下拉式清單中選取要用於小工具資料的屬性。 在此清單中的專案是審閱集內專案的可搜尋屬性。 如需這些屬性的說明，請參閱[Advanced eDiscovery 中的檔元資料欄位](document-metadata-fields-in-Advanced-eDiscovery.md)。 小工具的 pivot 選項會列在本主題的可搜尋**欄位名稱**欄中。

    c. 選取圖表類型以顯示選取的 pivot 屬性中的資料。

  6. 按一下 [**新增**] 以建立自訂構件，並將其顯示在 [**搜尋設定檔視圖**] 頁面上。

## <a name="step-2-create-a-review-set-search-query"></a>步驟2：建立複查集搜尋查詢

1. 按一下小工具標題列中的 [ **...** ]，然後按一下 [套用**條件**]。

   ![儀表板](../media/searchprofilehome.png)

2. 在飛入頁面上，按一下 [widget 鍵] 或 [小小工具] 圖表上的元素，以建立篩選。

   ![CreateFilter](../media/applyconditionfilter.png)

3. 對其他小小小元件重複步驟1-2。 

4. 當您完成時，按一下 [**另存**新檔]，將您的條件儲存為審閱集的新搜尋查詢。

   ![查詢](../media/savequery.png)

5. 關閉**搜尋設定檔視圖**，以回到搜尋結果檢視。

   如果您已建立任何視覺篩選器，則產生的查詢會套用至所顯示的搜尋結果，而您在步驟4中儲存的搜尋查詢會顯示在 [**已儲存的查詢**] 底下。 如需複查集合查詢的詳細資訊，請參閱[在審閱集中查詢資料](review-set-search.md)。
