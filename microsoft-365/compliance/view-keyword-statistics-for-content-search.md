---
title: 查看 eDiscovery 搜尋結果的統計資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: 瞭解如何使用「搜尋統計資料」功能，顯示與「Microsoft 365 規範中心」中的核心 eDiscovery 案例相關聯的內容搜尋和搜尋的統計資料。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311093"
---
# <a name="view-statistics-for-ediscovery-search-results"></a>查看 eDiscovery 搜尋結果的統計資料

建立並執行內容搜尋或與核心 eDiscovery 案例相關聯的搜尋之後，您可以查看估計搜尋結果的統計資料。 這包括搜尋結果摘要 (類似搜尋快顯視窗中所顯示之預計搜尋結果的摘要) 、查詢統計資料（如包含符合搜尋查詢之專案的內容位置數），以及具有最相符專案之內容位置的身分識別。
  
此外，您也可以使用關鍵字清單，設定搜尋，以在搜尋查詢中傳回每個關鍵字的統計資料。 這可讓您比較查詢中每一個關鍵字所傳回的結果數目。
  
您也可以將搜尋統計資料下載到 CSV 檔案。 如此可讓您使用 Excel 中的篩選和排序功能來比較結果，並為您的搜尋結果準備報告。
  
## <a name="get-statistics-for-searches"></a>取得搜尋的統計資料

顯示內容搜尋的統計資料，或與核心 eDiscovery 案例相關聯的搜尋：
  
1. 在 [Microsoft 365 規範中心] 中，按一下 [**全部顯示**]，然後執行下列其中一項操作：

   - 按一下 [ **內容搜尋** ]，然後選取搜尋以顯示飛出頁面。

     或

   - 按一下 [ **eDiscovery**  >  **Core**]，選取案例，然後選取 [**搜尋**] 索引標籤上的搜尋以顯示飛入頁面。

2. 在選取搜尋的飛入頁面上，按一下 [ **搜尋統計資料] 索引** 標籤。
  
   ![[搜尋統計資料] 索引標籤](../media/SearchStatistics1.png)

[ **搜尋統計資料] 索引** 標籤包含下列區段，其中包含有關搜尋的不同類型的統計資料。

### <a name="search-content"></a>搜尋內容

這個區段會顯示搜尋所傳回之預估專案的圖形摘要。 這會指出符合搜尋準則的專案數。 此資訊可讓您瞭解搜尋傳回之專案的預估數目。

![搜尋搜尋評估](../media/SearchContentReport.png)

- **依位置預估專案** 數目：搜尋傳回的預估專案總數。 也會顯示位於 [信箱] 和 [網站] 中的特定專案數目。

- **具有點擊作業的預估位置**：包含搜尋傳回之專案的內容位置總數。 也會顯示特定數目的信箱和網站位置。

- **依位置 (的資料量（以 MB 為單位）)**：搜尋傳回之所有預估專案的總大小。 也會顯示信箱專案和網站專案的特定大小。

### <a name="condition-report"></a>條件報告

本節顯示搜尋查詢的統計資料，以及符合搜尋查詢不同部分之估計專案數目的統計資料。 您可以使用這些統計資料來分析符合每個搜尋查詢元件的專案數。 這可協助您細化搜尋準則，並視需要縮小範圍的範圍。 您也可以下載 CSV 格式的此報告複本。

![條件報告](../media/SearchContentReportNoKeywordList.png)

- **位置類型**：查詢統計資料適用的內容位置類型。 **Exchange** 的值會指出信箱位置;值 **SharePoint** 表示網站位置。

- **部分**：搜尋查詢的部分適用的統計資料。 **主要** 表示整個搜尋查詢。 **關鍵字** 表示列中的統計資料是針對特定的關鍵字。 如果您使用關鍵字清單進行搜尋查詢，則會在此表格中包含每個查詢元件的統計資料。 如需詳細資訊，請參閱 [取得搜尋的關鍵字統計資料](#get-keyword-statistics-for-searches)。

- **條件**：搜尋查詢的實際元件 (關鍵字或條件) ，其傳回的統計資料會顯示在對應的列中。

- **具有點擊的位置**： [ **位置類型** ] 欄) 所指定的內容位置數目 (，包含符合 [ **條件** ] 欄中所列之 primary 或關鍵字查詢的專案。

- **專案**：從指定的內容位置 (的專案數，) 符合 [ **條件** ] 欄中所列的查詢。 如先前所述，如果專案包含要搜尋之關鍵字的多個實例，它只會在此欄位中計算一次。

- **Size (MB)**：在指定的內容位置中 (的所有專案總大小，) 符合 [ **條件** ] 欄中的搜尋查詢。

### <a name="top-locations"></a>主要位置

此區段顯示搜尋傳回專案中的特定內容位置的統計資料。 會顯示前 1,000 個位置。 您也可以下載 CSV 格式的此報告複本。

- 位置名稱 (信箱的電子郵件地址，以及網站) 的 URL。

-  (信箱或網站) 的位置類型。

- 搜尋所傳回的內容位置中的專案數預估。

- 每個內容位置預估專案的總大小。

## <a name="get-keyword-statistics-for-searches"></a>取得搜尋的關鍵字統計資料

如先前所述，[ **條件報告** ] 區段會顯示搜尋查詢，以及符合查詢之專案 (和大小) 的數目。 如果您在建立或編輯搜尋查詢時使用關鍵字清單，您可以取得增強的統計資料，顯示與每個關鍵字或關鍵字片語相符的專案數目。 這可協助您快速識別查詢的哪些部分是最 (及最低的) 有效。 例如，如果關鍵字會傳回大量的專案，您可以選擇縮小關鍵字查詢以縮小搜尋結果。

若要建立關鍵字清單並查看搜尋的關鍵字統計資料：
  
1. 在 [Microsoft 365 規範中心] 中，建立新的內容搜尋或與核心 eDiscovery 案例相關聯的搜尋。

2. 在搜尋嚮導的 [ **條件** ] 頁面上。 選取 [ **顯示關鍵字清單** ] 核取方塊。

   ![顯示關鍵字清單核取方塊](../media/SearchKeywordsList1.png)

3. 在 [關鍵字] 表格的列中輸入關鍵字或關鍵字階段。 例如，在第一列中輸入 [ **預算** ]，然後在第二列中輸入 [ **安全性** ]，然後在第三列中輸入 **FY2021** 。

   ![在清單中輸入最多20個關鍵字或關鍵字片語](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > 為了避免大型關鍵字清單所造成的問題，您最多隻能有20列的搜尋查詢的關鍵字清單中。

4. 將關鍵字新增至您要搜尋並取得統計資料的清單後，請執行搜尋。

5. 當搜尋完成時，請選取它以顯示飛出頁面。

6. 在 [ **搜尋統計資料] 索引** 標籤上，按一下 [ **條件] 報告** 以顯示搜尋的關鍵字統計資料。

    ![顯示每個關鍵字的統計資料](../media/SearchKeywordsList3.png)
  
    如先前的螢幕擷取畫面所示，會顯示每個關鍵字的統計資料。這包括：

    - 搜尋中包含的每個內容位置類型的關鍵字統計資料。

    - 未編制索引的信箱專案數目。

    - 在 **Part** 欄) 中，每個關鍵字 (的實際搜尋查詢和結果會標示為 **關鍵字**，其中包含搜尋查詢的任何條件。

    - 完整的搜尋查詢 (會在 **Part** 欄) 中識別為 **主要** 的，以及針對每個位置類型的完整查詢的統計資料。 請注意，[ **摘要** ] 索引標籤上顯示的是相同的統計資料。
