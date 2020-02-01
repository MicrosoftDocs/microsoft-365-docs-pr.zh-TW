---
title: 檢視 custodian 稽核活動
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
description: ''
ms.openlocfilehash: 46dffe5c388f247604bc67dc24916206452745da
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597260"
---
# <a name="view-custodian-audit-activity"></a>檢視 custodian 稽核活動

需要了解是否有使用者已檢視特定文件或清除信箱中的項目嗎？ 進階電子文件現在已與現有的安全性 & 規範中心的稽核記錄搜尋工具整合。 使用此內嵌的體驗，您可以使用進階電子文件 Custodian 管理工具來協助您調查輕鬆地存取搜尋並活動 custodians 內您的案例。

## <a name="before-you-begin"></a>開始之前

您必須在 Exchange Online 中獲派為 [僅限檢視稽核記錄] 或 [稽核記錄] 角色，才能搜尋 Office 365 稽核記錄。 根據預設，這些角色會在 Exchange 系統管理員中心的 [權限] 頁面上，指派給 [法務遵循管理] 和 [組織管理] 角色群組。 若要讓使用者能夠搜尋進階電子文件稽核記錄的最低權限，您可以在 Exchange Online 中建立自訂角色群組、 新增 「 僅檢視稽核記錄檔] 或 [稽核記錄 」 角色，並再將使用者新增新的角色群組的成員身分。 如需詳細資訊，請參閱管理 Exchange Online 中的角色群組。

> [!IMPORTANT]
> 如果您將 Security & 合規性中心的權限] 頁面上僅檢視稽核記錄檔] 或 [稽核記錄檔角色指派使用者，他們將無法搜尋 Office 365 稽核記錄。 您必須在 Exchange Online 中指派權限。 這是因為用來搜尋稽核記錄的基礎 Cmdlet 是 Exchange Online Cmdlet。

## <a name="step-1-search-the-audit-log-for-activities-performed-by-a-custodian"></a>步驟 1： 搜尋 custodian 所執行的活動的稽核記錄檔

1. 移至**eDiscovery > 進階電子文件**，並開啟案例。
  
2. 按一下 [ **Custodians** ] 索引標籤。
  
3. 從清單中，選取 custodian，然後按一下 [延伸] 頁面上的 [**檢視 custodian 活動**。

    Custodian 活動搜尋頁面隨即顯示。 附註您在上一個步驟中選取 custodian 會顯示在**Custodian**下拉式方塊。 您可以在下拉式方塊中，選取不同的 custodians，但您可以僅搜尋活動的一個 custodian 一次。

    ![Custodian 活動搜尋頁面](media/AeDCustodianActivities1.png)
   
4. 設定下列搜尋準則：
      
   a. **活動**-按一下下拉式清單，顯示您可以搜尋的活動。 執行搜尋之後，會顯示只有選取活動的稽核記錄。 選取 [**顯示所有活動的結果**會顯示所有活動 custodian 所執行的其他搜尋準則相符的結果。

      ![活動的清單](media/CustodianActivityAudit.PNG)
      
      b. **開始日期和結束日期**-選取日期與時間範圍，以顯示該期間內發生的事件。 預設會選取過去 7 天。 日期和時間以國際標準時間 (UTC) 格式表示。 您可以指定的最大的日期範圍是一年。
      
      c. **Custodians** -按一下 [在這個方塊，然後選取 [顯示搜尋結果提供給特定 custodian。 選取您在此方塊中選取的使用者所執行的活動的稽核記錄會顯示在結果清單中。
      
   5. 按一下   ![[搜尋] 按鈕](media/SearchButton.PNG)  若要執行搜尋使用您的搜尋準則。 載入的搜尋結果時，並在幾分鐘之後他們顯示的結果下 Custodian 活動的 [搜尋] 頁面上。 

## <a name="step-2-view-the-audit-log-search-results"></a>步驟 2： 檢視稽核記錄搜尋結果

稽核記錄搜尋結果] 底下會顯示結果 Custodian 稽核記錄 」 頁面。 最大值為 5000 個 （最新） 的事件都會顯示在 150 事件以遞增。 若要顯示更多事件，您可以在 [結果] 窗格中使用捲軸列，或按 Shift + End 顯示後續 150 個事件。

結果包含下列搜尋傳回的每個事件的相關資訊。
- **日期：** 事件發生時的日期和時間 (以 UTC 格式顯示)。

- **IP 位址：** 記錄活動時所使用的裝置之 IP 位址。 IP 位址會以 IPv4 或 IPv6 位址格式顯示。

- **使用者**：執行動作並觸發事件的使用者 (或服務帳戶)。

- **活動**：使用者執行的活動。 這個值對應您在 [活動] 下拉式清單中選取的活動。 若是來自 Exchange 系統管理員稽核記錄的事件，此欄中的這個值則是 Exchange Cmdlet。

- **項目**：已建立或修改為對應活動結果的物件。 例如，已檢視或修改的檔案或已更新的使用者帳戶。 並非所有活動在此資料行中都具有值。

- **詳細資料**： 活動相關的其他詳細資料。 同樣地，並非所有活動會都有一個值。

## <a name="step-3-filter-the-search-results"></a>步驟 3：篩選搜尋結果

除了排序，您也可以篩選稽核記錄搜尋的結果。 這可協助您快速篩選特定使用者或活動的結果。 

若要篩選結果：

 1. 建立並執行稽核記錄搜尋。
  
2. 當顯示結果時，按一下 [篩選結果]****。
 
3. 關鍵字方塊隨即顯示在每個欄標頭底下。
  
4. 按一下欄標頭底下的其中一個方塊，然後輸入字詞或片語 (視您正在篩選的欄而定)。 結果將動態重新調整為顯示與您的篩選相符之事件。
  
5. 若要清除篩選，請按一下 [篩選] 方塊中的**X**或只要按一下 [**隱藏篩選**。

## <a name="export-the-search-results-to-a-file"></a>將搜尋結果匯出至檔案

您可以將稽核記錄搜尋結果匯出至本機電腦上的逗點分隔的值 (CSV) 檔案。 您可以在 Microsoft Excel 中開啟此檔案，並使用多個資料行到功能，例如搜尋，排序、 篩選及分割的單一資料行 （包含多重值的儲存格）。

1. 執行稽核記錄搜尋，然後修改搜尋準則，直到您獲得想要的結果為止。
  
2. 按一下 [匯出結果]，然後選取下列其中一個選項：

    - **儲存載入結果：** 選擇此選項以匯出**Custodian 稽核記錄搜尋**] 頁面的**結果**下顯示的項目。 下載的 CSV 檔案會包含與頁面上顯示相同的欄 (及資料) (日期、使用者、活動、項目及詳細資料)。 （標題為**多個**） 額外一欄隨附於 CSV 檔案包含稽核記錄項目從的詳細資訊。 因為您正在匯出 [稽核記錄搜尋] 頁面上所載入的相同結果 (且可檢視)，因此最多可匯出 5,000 個項目。
        
    - **下載所有的結果：** 選擇此選項以從符合搜尋準則的 Office 365 稽核記錄檔匯出所有的項目。 一組大型的搜尋結果，選擇此選項以從除了可以**Custodian 稽核記錄**搜尋] 頁面顯示 5000 筆結果的稽核記錄檔下載所有項目。 此選項將稽核記錄檔從下載的未經處理資料至 CSV 檔案，並包含名為 AuditData] 欄中的稽核記錄項目中的其他資訊。 如果您選擇此匯出選項，下載檔案可能需要較久的時間。這是因為如果您選擇其他選項，檔案可能會遠大於下載的檔案。
    
      > [!IMPORTANT]
      > 您可以從單一稽核記錄搜尋下載最多 50,000 個項目至 CSV 檔案。 如果已下載 50,000 個項目至 CSV 檔案，您可能可以假設有超過 50,000 個符合搜尋準則的事件。 若要匯出的內容超過此限制，請嘗試使用日期範圍來縮小稽核記錄項目的數量。 您可能需要使用較小的日期範圍執行多次搜尋，以匯出 50,000 個以上的項目。
        

3. 選取 [匯出] 選項後，會提示您開啟 CSV 檔案，將它儲存到 [下載項目] 資料夾中，或將其儲存至特定資料夾視窗底部顯示訊息

如需檢視的詳細資訊，篩選，或匯出稽核記錄搜尋結果，請參閱[的搜尋稽核記錄在安全 & 合規性中心](search-the-audit-log-in-security-and-compliance.md)。
