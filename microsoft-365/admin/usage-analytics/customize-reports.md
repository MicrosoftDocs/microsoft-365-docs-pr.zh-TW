---
title: 在 Microsoft 365 使用方式分析中自訂報告
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: 瞭解如何在瀏覽器和 Power BI Desktop 中自訂報告。
ms.openlocfilehash: 8baeb1a9f48d8f1ccdb591a60fefe863502344b6
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841420"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>在 Microsoft 365 使用方式分析中自訂報告

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。

::: moniker-end

Microsoft 365 流量分析提供 Power BI 中的儀表板，可深入瞭解使用者採用和使用 Microsoft 365 的方式。 儀表板只是與使用狀況資料互動的起點。 您可以自訂報告，以獲得更多個人化洞察力。
  
您也可以使用 Power BI 桌面來進一步自訂報告，方法是將其連線至其他資料來源，以深入瞭解您的企業。
  
## <a name="customizing-reports-in-the-browser"></a>在瀏覽器中自訂報告

下列兩個範例示範如何修改現有的視覺效果，以及如何建立新的視覺效果。
  
### <a name="modify-an-existing-visual"></a>修改現有的視覺效果

此範例顯示如何在 **啟用/授權** 報告中修改 [ **啟用** ] 索引標籤。 
  
1. 在 [ **啟用/授權** ] 報告中，選取 [ **啟用** ] 索引標籤。
    
2. 在 [Power BI] 的 [其他頁面] 按鈕中，選擇上方的 [ **編輯** ] 按鈕，以進入編輯模式 ![ ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) 。 
    
    ![按一下右上方導覽中的 [編輯報告]](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. 在右上方，選擇 [ **複製此頁面** ]。
    
    ![選擇 [複製此頁面]](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. 在右下方，選擇顯示根據 OS （如 Android、iOS、Mac 等）啟動之使用者計數的任何橫條圖。
    
5. 在右側的 **視覺化** 區域中，若要從視覺中移除 **Mac 計數** ，請選取它旁邊的 **X** 。

    ![移除 Mac 計數](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a>建立新的視覺

下列範例顯示如何建立新的視覺效果，以每月追蹤新的 Yammer 使用者。
  
1. 使用左導覽移至 [ **產品使用狀況** ] 報告，然後選取 [ **Yammer** ] 索引標籤。
    
2. 選擇 ![ [POWER BI] 和 [編輯] 中的 [更多頁面] 按鈕，切換至編輯模式 ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png)  。 
    
3. 在頁面底部，選取 ![Power BI 中的 [新增頁面] 按鈕](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) 以建立新的頁面。
  
4. 在右側的 **視覺化** 區域中，選擇 [ **堆疊橫條圖** ] (頂端列（從左) 開始）。

    ![選取橫條圖](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. 選取該視覺化效果的右下方，並拖曳以放大顯示。

6. 在右側的 [ **欄位** ] 區域中，展開 [行事 **曆** ] 表格。

7. 將 **MonthName** 拖曳至 [欄位] 區域，其位於 **視覺化** 區域的 [ **座標軸** ] 標題下方。
 
    ![拖曳月份名稱](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. 在右側的 [ **欄位** ] 區域中，展開 [ **TenantProductUsage** ] 表格。

9. 將 **FirstTimeUsers** 拖曳至 [欄位] 區域，直接在 **值** 標題下方。

10. 將 **產品** 拖曳至 [ **篩選** ] 區域，直接在 [ **視覺層級篩選** ] 標題下。

11. 在出現的 [ **篩選類型** ] 區域中，選取 [ **Yammer** ] 核取方塊。

    ![選取 Yammer 核取方塊](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. 在視覺效果的清單下方，選擇 [ **Format** ![ Power BI Visualizaions] 中的格式圖示格式圖示 ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) 。

13. 按月，展開 [標題]，然後將 [ **標題] 文字** 值變更為 [ **第一次 Yammer] 使用者** 。
    
14. 將 **文字大小** 值變更為 **12** 。
    
15. 在右下方編輯頁面名稱，以變更新頁面的標題。

16.  按一下頂端的 [ **閱讀檢視** ]，然後按一下 [ **儲存** ] 來儲存報告。
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a>自訂 Power BI Desktop 中的報表

大多數客戶在 Power BI web 中修改報告和圖表視覺效果的情況都會夠用。 在某些情況下，您可能需要將此資料與其他資料來源結合，以獲得更深入的業務相關內容，在這種情況下，他們可以使用 Power BI Desktop 自訂及建立其他報告。 您可以免費下載 [POWER BI desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) 。 
  
### <a name="use-the-reporting-apis"></a>使用報表 APIs

您可以開始直接連線至 Microsoft 365 的 ODATA 報告 APIs，以加上這些報告。
  
1. 移至 [ **取得資料** \> ] **其他** \> **ODATA** 摘要 \> **Connect** 。
    
2. 在 [URL] 視窗中，輸入 "HTTPs:// <i></i> reports.office.com/pbi/v1.0/ \<tenantid\> "
    
    **附注：** 報告 APIs 是在預覽中，且在實際執行之前必須變更。 
  
    ![OData Power BI desktop 的摘要 URL](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. 當系統提示時，請輸入您的 Microsoft 365 (組織或學校) 系統管理員認證，以向 Microsoft 365 驗證。
    
    如需允許存取 Microsoft 365 採用範本應用程式報告之使用者的詳細資訊，請參閱 [FAQ](usage-analytics.md#faq) 。 
    
4. 連線授權後，您將會看到 [Navigator] 視窗，顯示可供連線的資料集。
    
    選取 [全部]，然後選擇 [ **負載** ]。
    
    這會將資料下載到您的 Power BI Desktop。 儲存此檔案，然後您就可以開始建立所需的報告。
    
    ![報告 API 中可用的 ODATA 值](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a>使用 Microsoft 365 流量分析範本

您也可以使用與 Microsoft 365 使用方式分析報告對應的 Power BI 範本檔案，作為連接至資料的起點。 使用 pbit 檔案的優點是已建立連接字串。 您也可以利用基礎架構傳回的資料與基礎架構傳回的所有自訂量值，並進一步加以建立。
  
您可以從 [下載中心](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)從 Microsoft 下載中心下載 Power BI 範本檔案。 下載 Power BI 範本檔案之後，請遵循下列步驟開始執行：
  
1. 開啟 pbit 檔案。
    
2. 在對話方塊中輸入您的租使用者識別碼值。
    
    ![輸入您的租使用者識別碼，以開啟 pbit 檔案](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. 當系統提示時，請輸入您的系統管理員認證以驗證 Microsoft 365。
    
     以取得允許存取 Microsoft 365 使用方式分析報告之使用者的詳細資訊。 
    
    授權後，就會在 Power BI 檔案中重新整理資料。
    
    資料負載可能需要一些時間，完成後，您可以將檔案儲存為 .pbix 檔案，繼續自訂報告或將額外的資料來源帶入此報告。
    
4. 遵循 [POWER bi 檔快速](https://go.microsoft.com/fwlink/?linkid=849802) 入門，以瞭解如何建立報表、將其發佈至 Power BI 服務，以及與您的組織共用。 請遵循此路徑進行自訂和共用，可能需要額外的 Power BI 授權。 如需詳細資訊，請參閱 Power BI [授權指南](https://go.microsoft.com/fwlink/p/?linkid=849803) 。 
    

