---
title: 在 Microsoft 365 流量分析中自訂報告
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: 瞭解在瀏覽器中自訂報告和 Power BI Desktop。
ms.openlocfilehash: c48e20d234e6e3de75ab54daaf2c169eef3a42ad
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288608"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>在 Microsoft 365 流量分析中自訂報告

Microsoft 365 流量分析提供 Power BI 中的儀表板，可深入瞭解使用者採用和使用 Microsoft 365 的方式。 儀表板只是與使用狀況資料互動的起點。 您可以自訂報告，以獲得更多個人化洞察力。

您也可以使用 Power BI 桌面來進一步自訂報告，方法是將其連線至其他資料來源，以深入瞭解您的業務。

## <a name="customizing-reports-in-the-browser"></a>在瀏覽器中自訂報告

下列兩個範例示範如何修改現有的視覺效果，以及如何建立新的視覺效果。

### <a name="modify-an-existing-visual"></a>修改現有的視覺效果

此範例顯示如何在 **啟用/授權** 報告中修改 [**啟用**] 索引標籤。

1. 在 [ **啟用/授權** ] 報告中，選取 [ **啟用** ] 索引標籤。

2. 在 [Power BI] 按鈕的 [其他頁面] 按鈕上方選擇 [**編輯**] 按鈕，以進入編輯模式 ![ ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) 。

    ![按一下右上方導覽中的 [編輯報告]](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)

3. 在右上方，選擇 [ **複製此頁面**]。

    ![選擇 [複製此頁面]](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)

4. 在右下方，選擇顯示根據 OS （如 Android、iOS、Mac 等）啟動之使用者計數的任何橫條圖。

5. 在右側的 **視覺化** 區域中，若要從視覺中移除 **Mac 計數** ，請選取它旁邊的 **X** 。

    ![移除 Mac 計數](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)

### <a name="create-a-new-visual"></a>建立新的視覺

下列範例顯示如何建立新的視覺效果，以在每月的時間追蹤新的 Yammer 使用者。

1. 使用左導覽移至 [**產品使用狀況** 報告]，然後選取 [ **Yammer** ] 索引標籤。

2. ![在 Power BI 及編輯] 中選擇 [更多頁面] 按鈕，即可切換至編輯模式 ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) 。 

3. 在頁面底部，選取 ![Power BI 中的 [新增頁面] 按鈕](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) 以建立新的頁面。

4. 在右側的 **視覺化** 區域中，選擇 [ **堆疊橫條圖** ] (頂端列（從左) 開始）。

    ![選取橫條圖](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)

5. 選取該視覺化效果的右下方，並拖曳以放大顯示。

6. 在右側的 [ **欄位** ] 區域中，展開 [行事 **曆** ] 表格。

7. 將 **MonthName** 拖曳至 [欄位] 區域，其位於 **視覺化** 區域的 [**座標軸**] 標題下方。

    ![拖曳月份名稱](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)

8. 在右側的 [ **欄位** ] 區域中，展開 [ **TenantProductUsage** ] 表格。

9. 將 **FirstTimeUsers** 拖曳至 [欄位] 區域，直接在 **值** 標題下方。

10. 將 **產品** 拖曳至 [ **篩選** ] 區域，直接在 [ **視覺層級篩選** ] 標題下。

11. 在出現的 [**篩選類型**] 區域中，選取 [ **Yammer** ] 核取方塊。

    ![選取 Yammer 核取方塊](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)

12. 在視覺效果的清單下方，選擇 Power BI Visualizaions 中的 **格式** 圖示 ![ 格式圖示 ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) 。

13. 展開 [標題]，然後 **依月 Yammer 使用者** 將 **標題文字** 值變更為第一次。

14. 將 **文字大小** 值變更為 **12**。

15. 在右下方編輯頁面名稱，以變更新頁面的標題。

16. 按一下頂端的 [ **閱讀檢視** ]，然後按一下 [ **儲存**] 來儲存報告。

## <a name="customizing-the-reports-in-power-bi-desktop"></a>在 Power BI Desktop 中自訂報告

大多數客戶在 Power BI 網頁中修改報告和圖表視覺效果都已足夠。 在某些情況下，您可能需要將此資料與其他資料來源結合，以獲得更深入的業務相關資訊，在這種情況下，他們可以使用 Power BI Desktop 自訂及建立額外的報表。 您可以免費下載[Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) 。

### <a name="use-the-reporting-apis"></a>使用報表 APIs

您可以開始直接連線至 ODATA 報告 APIs，使其能開啟這些報告 Microsoft 365。

1. 移至 [**取得資料**] \> **其他** \> **ODATA** 摘要 \> **連線**。

2. 在 [URL] 視窗中，輸入 "HTTPs:// <i></i> reports.office.com/pbi/v1.0/ \<tenantid\> "

    **附注：** 報告 APIs 是在預覽中，且在實際執行之前必須變更。

    ![OData Power BI 桌面的摘要 URL](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)

3. 在系統提示時，輸入您的 Microsoft 365 (組織或學校) 系統管理員認證，以進行 Microsoft 365 驗證。

    請參閱[FAQ](usage-analytics.md#faq) ，以取得允許存取 Microsoft 365 採用範本應用程式報告之人員的詳細資訊。

4. 連線授權後，您將會看到 [Navigator] 視窗，顯示可供連線的資料集。

    選取 [全部]，然後選擇 [ **負載**]。

    這會將資料下載到您的 Power BI Desktop。 儲存此檔案，然後您就可以開始建立所需的報告。

    ![報告 API 中可用的 ODATA 值](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)

### <a name="use-the-microsoft-365-usage-analytics-template"></a>使用 Microsoft 365 流量分析範本

您也可以使用對應至 Microsoft 365 使用方式分析報告的 Power BI 範本檔，做為連接資料的起點。 使用 pbit 檔案的優點是已建立連接字串。 您也可以利用基礎架構傳回的資料與基礎架構傳回的所有自訂量值，並進一步加以建立。

您可以從[Microsoft 下載中心](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)下載 Power BI 範本檔案。 下載 Power BI 範本檔之後，請遵循下列步驟開始執行：

1. 開啟 pbit 檔案。

2. 在對話方塊中輸入您的租使用者識別碼值。

    ![輸入您的租使用者識別碼，以開啟 pbit 檔案](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)

3. 當系統提示時，請輸入您的系統管理員認證，以驗證 Microsoft 365。

     以取得允許存取 Microsoft 365 使用方式分析報告之使用者的詳細資訊。

    授權後，就會在 Power BI 檔中重新整理資料。

    資料負載可能需要一些時間，完成後，您可以將檔案儲存為 .pbix 檔案，繼續自訂報告或將額外的資料來源帶入此報告。

4. 遵循[Power BI 檔的快速](/power-bi/fundamentals/desktop-getting-started)入門，以瞭解如何建立報表、將報表發佈至 Power BI 服務，以及與組織共用。 請遵循此路徑進行自訂和共用，可能需要額外的 Power BI 授權。 如需詳細資訊，請參閱 Power BI[授權指南](https://go.microsoft.com/fwlink/p/?linkid=849803)。
