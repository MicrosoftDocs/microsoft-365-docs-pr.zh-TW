---
title: 檢視監管人稽核活動
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
description: 使用 Advanced eDiscovery 保管人管理工具，在您的案例中輕鬆存取和搜尋保管人的活動。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f9e96d0b5dd3bf42dbba56a6e1be91014485ce98
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024763"
---
# <a name="view-custodian-audit-activity"></a>檢視監管人稽核活動

需要了解是否有使用者已檢視特定文件或清除信箱中的項目嗎？ Advanced eDiscovery 現在已與安全性 & 規範中心內的現有「審核記錄」搜尋工具整合。 使用此內嵌的經驗，您 Advanced eDiscovery 可以在案例中輕鬆存取及搜尋系統管理員的活動，以協助您進行調查。

## <a name="get-permissions"></a>取得許可權

您必須在 Exchange Online 中獲派為 [僅限檢視稽核記錄] 或 [稽核記錄] 角色，才能搜尋稽核記錄。 根據預設，這些角色會在 Exchange 系統管理員中心的 [權限] 頁面上，指派給 [法務遵循管理] 和 [組織管理] 角色群組。 若要提供讓使用者能夠搜尋進階電子文件探索稽核記錄的最低權限等級，您可以在 Exchange Online 中建立自訂角色群組、新增「僅供檢視稽核記錄」或「稽核記錄」角色，然後將使用者新增為這個新角色群組的成員。 如需詳細資訊，請參閱管理 Exchange Online 中的角色群組。

> [!IMPORTANT]
> 如果您在安全性 & 規範中心的 [許可權] 頁面上指派使用者 View-Only 的「審核記錄」或「審核記錄」角色，他們將無法搜尋審核記錄。 您必須在 Exchange Online 中指派權限。 這是因為用來搜尋稽核記錄的基礎 Cmdlet 是 Exchange Online Cmdlet。

## <a name="step-1-search-the-audit-log-for-activities-performed-by-a-custodian"></a>步驟1：搜尋針對保管人所執行之活動的審計記錄

1. 請移至 **eDiscovery > Advanced eDiscovery** ，然後開啟此案例。
  
2. 按一下 [ **來源** ] 索引標籤。
  
3. 在 [ **保管人** ] 頁面上，從清單中選取管理員，然後按一下彈出頁面上的 [ **查看保管人活動** ]。

    [保管人活動搜尋] 頁面隨即顯示。 附注您在上一個步驟中選取的系統管理員會顯示在 [ **保管人** ] 下拉式方塊中。 您可以在下拉式方塊中選取不同的保管人，但是一次只能搜尋一個保管人的活動。

    ![監管人活動搜尋頁面](../media/AeDCustodianActivities1.png)
   
4. 設定下列搜尋準則：
      
   1. **活動** -按一下下拉式清單，以顯示您可以搜尋的活動。 執行搜尋後，系統只會顯示所選活動的稽核記錄。 選取 [ **顯示所有活動的結果** ]，會顯示由系統管理員執行且符合其他搜尋準則之所有活動的結果。

      ![活動清單](../media/CustodianActivityAudit.PNG)
      
   1. **開始日期和結束日期** -選取日期和時間範圍，以顯示在該期間內發生的事件。 預設會選取最後七天。 日期和時間以國際標準時間 (UTC) 格式表示。 您可以指定的最大日期範圍是一年。
      
   1. **保管人** -按一下此方塊，然後選取特定保管人以顯示搜尋結果。 您在此方塊中選取之使用者所執行之選取活動的審計記錄會顯示在結果清單中。
      
5. 按一下 ![搜尋按鈕](../media/SearchButton.PNG)  使用您的搜尋準則執行搜尋。 搜尋結果會在載入之後，然後在 [保管人活動搜尋] 頁面的 [結果] 底下出現片刻。 

## <a name="step-2-view-the-audit-log-search-results"></a>步驟2：查看審核記錄搜尋結果

審核記錄搜尋的結果會顯示在 [保管人審核記錄] 頁面的 [結果] 底下。 最多 5000 (最新的) 事件會以150事件的增量顯示。 若要顯示更多事件，您可以在 [結果] 窗格中使用捲軸列，或按 Shift + End 顯示後續 150 個事件。

結果會包含搜尋所傳回之每個事件的下列相關資訊。
- **日期：** 事件發生時的日期和時間 (以 UTC 格式顯示)。

- **IP 位址：** 記錄活動時所使用的裝置之 IP 位址。 IP 位址會以 IPv4 或 IPv6 位址格式顯示。

- **使用者**：執行動作並觸發事件的使用者 (或服務帳戶)。

- **活動**：使用者執行的活動。 這個值對應您在 [活動] 下拉式清單中選取的活動。 若是來自 Exchange 系統管理員稽核記錄的事件，此欄中的這個值則是 Exchange Cmdlet。

- **項目**：已建立或修改為對應活動結果的物件。 例如，已檢視或修改的檔案或已更新的使用者帳戶。 並非所有活動在此資料行中都具有值。

- **詳細資料**：有關活動的其他詳細資料。 同樣地，並非所有活動都會有值。

## <a name="step-3-filter-the-search-results"></a>步驟 3：篩選搜尋結果

除了排序，您也可以篩選稽核記錄搜尋的結果。 這可協助您快速篩選特定使用者或活動的結果。 

若要篩選結果：

 1. 建立並執行審核記錄搜尋。
  
2. 當顯示結果時，按一下 **[篩選結果]**。
 
3. 關鍵字方塊隨即顯示在每個欄標頭底下。
  
4. 按一下欄標頭底下的其中一個方塊，然後輸入字詞或片語 (視您正在篩選的欄而定)。 結果將動態重新調整為顯示與您的篩選相符之事件。
  
5. 若要清除篩選，請按一下 [篩選] 方塊中的 **X** 或只按一下 [ **隱藏篩選**]。

## <a name="export-the-search-results-to-a-file"></a>將搜尋結果匯出至檔案

您可以將審核記錄搜尋的結果匯出為以逗號分隔的值 (本機電腦上的 CSV) 檔案。 您可以在 Microsoft Excel 中開啟此檔案，並使用搜尋、排序、篩選和分割包含多值儲存格的單一欄 () 多欄中。

1. 執行稽核記錄搜尋，然後修改搜尋準則，直到您獲得想要的結果為止。
  
2. 按一下 [匯出結果]，然後選取下列其中一個選項：

    - **儲存載入的結果：** 選擇此選項，只會匯出在「**保管人審核記錄搜尋**」頁面的 [**結果**] 下顯示的專案。 下載的 CSV 檔案會包含與頁面上顯示相同的欄 (及資料) (日期、使用者、活動、項目及詳細資料)。 包含更 **多**)  (的其他欄包含來自審計記錄專案的詳細資訊，包含在 CSV 檔案中。 因為您正在匯出 [稽核記錄搜尋] 頁面上所載入的相同結果 (且可檢視)，因此最多可匯出 5,000 個項目。
        
    - **下載所有結果：** 選擇此選項可從符合搜尋準則的審計記錄中匯出所有專案。 針對大型搜尋結果集，請選擇此選項，從審核記錄中下載所有專案，除了可顯示在 [ **保管人審核記錄** 搜尋] 頁面上的5000結果。 此選項會從審核記錄檔下載原始資料到 CSV 檔案，並包含來自名為 AuditData 的欄中的審計記錄專案的其他資訊。 如果您選擇此匯出選項，下載檔案可能需要較久的時間。這是因為如果您選擇其他選項，檔案可能會遠大於下載的檔案。
    
      > [!IMPORTANT]
      > 您可以從單一稽核記錄搜尋下載最多 50,000 個項目至 CSV 檔案。 如果已下載 50,000 個項目至 CSV 檔案，您可能可以假設有超過 50,000 個符合搜尋準則的事件。 若要匯出的內容超過此限制，請嘗試使用日期範圍來縮小稽核記錄項目的數量。 您可能需要使用較小的日期範圍執行多次搜尋，以匯出 50,000 個以上的項目。
        

3. 選取匯出選項之後，會在視窗底部顯示一則訊息，提示您開啟 CSV 檔、將其儲存至 [下載] 資料夾，或將其儲存至特定資料夾。

如需查看、篩選或匯出審計記錄搜尋結果的詳細資訊，請參閱在 [安全性 & 規範中心搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。
