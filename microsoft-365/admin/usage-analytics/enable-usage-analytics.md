---
title: 啟用 Microsoft 365 使用情況分析
f1.keywords:
- CSH
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
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: 瞭解如何使用 Power BI 中的 Microsoft 365 流量分析範本應用程式，來開始收集租使用者的資料。
ms.openlocfilehash: 01923887b4af143d1490e14d59a6174700e6ae93
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635411"
---
# <a name="enable-microsoft-365-usage-analytics"></a>啟用 Microsoft 365 使用情況分析

Microsoft 365 美國政府 Community 尚無法使用 Microsoft 365 流量分析。
  
## <a name="before-you-begin"></a>開始之前

若要開始使用 Microsoft 365 流量分析，您必須先在 Microsoft 365 系統管理中心中提供資料，然後在 Power BI 中啟動範本應用程式。
  
## <a name="get-power-bi"></a>取得 Power BI

如果您尚無 Power BI，可以[註冊 Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347)。 選取 [**嘗試免費** 註冊試用版] 或 [**立即購買**] 以取得 Power BI Pro。
  
  
您也可以展開 [**產品**] 以購買 Power BI 的版本。 

> [!NOTE]
> 您需要 Power BI Pro 授權才能安裝、自訂及發佈範本應用程式。 如需詳細資訊，請參閱 [必要條件](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。

若要共用您的資料，這兩者和您與您共用資料的人員、需要 Power BI Pro 授權，或是內容必須位於[Power BI premium service](/power-bi/service-premium-what-is)的工作區中。 
  
## <a name="enable-the-template-app"></a>啟用範本應用程式

若要啟用範本應用程式，您必須是 **全域系統管理員**。
  
如需詳細資訊，請參閱 [關於系統管理員角色](../add-users/about-admin-roles.md) 。 
  
1. 在系統管理中心中，移至 [**設定** 的 \> **組織設定** \> **服務**] 索引標籤。 
    
2. 在 [ **服務** ] 索引標籤上，選取 [  **報告**]。
    
3. 在開啟的 [報告] 面板上，設定 **可讓報表資料 Microsoft 365 Power BI 儲存的流量分析**  \> ****。 
  
資料收集程式會在兩到48小時內完成，視租使用者的大小而定。 將會啟用 [**移至 Power BI** ] 按鈕 (當資料收集完成時，) 不再是灰色的。 
    
## <a name="start-the-template-app"></a>啟動範本應用程式

若要啟動範本應用程式，您必須是 **全域系統管理員**、**報告讀取** 者、 **Exchange 管理員**、**商務用 Skype 系統管理員** 或 **SharePoint 系統管理員**。 
  
1. 複製租使用者識別碼，然後選取 [**移至 Power BI**]。
    
2.  當您移到 Power BI 時，進行登入。 然後 -> 從流覽功能表中選取 [應用程式 **取得應用程式**]。    
  
3. 在 [**應用程式**] 索引標籤的 [搜尋] 方塊中輸入 Microsoft 365，然後選取 [ **Microsoft 365 流量分析**] \> **立即取得**。

    [![選取 [立即取得]](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  安裝應用程式之後。 選取拼貼以開啟它。

5.  選取 [ **流覽應用程式** ] 以查看具有範例資料的應用程式。 選擇 [**連線**]，將應用程式連線至您組織的資料。

6.  選擇 [**連線**]，在 **連線上 Microsoft 365 流量分析**] 畫面中，輸入 [租使用者識別碼] (不含破折號，) 您在步驟 (1) 中複製，然後選取 **[下一步]**。
    
7. 在下一個畫面中，選取 [ **OAuth2** ] 做為 **驗證方法**[登 \> **入**]。 如果您選擇任何其他驗證方法，則與範本應用程式的連線將會失敗。
    
    ![選擇 Microsoft 帳戶做為驗證方法](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. 範本應用程式具現化後，網頁上 Power BI 會提供 Microsoft 365 流量分析儀表板。 儀表板的初次載入需要2到30分鐘。
  
在 [加入] 中的所有報告中，均提供租使用者層級匯總。 **使用者層級的詳細資料只會在下一個行事曆中的第五個月使用**。 這會影響所有「使用者活動」下的報告 (請參閱[流覽並使用報表 Microsoft 365 流量分析](navigate-and-utilize-reports.md)，以取得如何查看和使用這些報表的秘訣) 。
    
## <a name="make-the-collected-data-anonymous"></a>將收集的資料匿名化

若要將所有報表收集的資料匿名化，您必須是全域系統管理員。 這會在報表和範本應用程式中隱藏識別資訊，例如使用者、群組和網站名稱。
  
1. 在系統管理中心中，移至 [**設定** 的 \> **Org 設定**]，然後在 [**服務**] 索引標籤上選擇 [**報告**]。
    
2. 選取 [ **報告**]，然後選擇 **顯示匿名識別碼**。 此設定會同時套用至使用狀況報告和範本應用程式。
  
3. 選取 **[儲存變更]**。

## <a name="related-content"></a>相關內容

[關於流量分析](usage-analytics.md) (文章) \
[取得最新版的流量分析](get-the-latest-version-of-usage-analytics.md) (文章) \
[流覽並使用報表 Microsoft 365 流量分析](navigate-and-utilize-reports.md) (文章) 