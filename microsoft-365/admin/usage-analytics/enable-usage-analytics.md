---
title: 啟用 Microsoft 365 使用情況分析
f1.keywords:
- CSH
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: 了解如何開始使用 Power BI 中的 Microsoft 365 使用情況分析範本應用程式租用戶收集資料。
ms.openlocfilehash: 651a820916f65a1695b7300772b1d2ce8aee92bb
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240039"
---
# <a name="enable-microsoft-365-usage-analytics"></a>啟用 Microsoft 365 使用情況分析

Microsoft 365 使用情況分析也適用於 Microsoft 365 美國政府社群。
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>若要啟用 Microsoft 365 使用情況分析的步驟

若要開始使用 Microsoft 365 使用情況分析，您必須先在 Microsoft 365 系統管理中心中，提供資料，然後啟動 Power BI 中的範本應用程式。
  
### <a name="get-power-bi"></a>取得 Power BI

如果您還沒有 Power BI，您可以[註冊 Power BI 專業版](https://go.microsoft.com/fwlink/p/?linkid=845347)。 選取 [**免費試用**來註冊試用或若要取得 Power BI 專業人員的**立即購買**]。
  
  
您也可以展開 [**產品**] 購買其中 Power BI 的版本。 

> [!NOTE]
> 您必須安裝、 自訂及發佈的範本應用程式的 Power BI 專業版授權。 如需詳細資訊，請參閱[必要條件](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。

您需要專業 Power BI 的授權，以共用您的內容，以及您將它與共用的人員進行太，或內容必須可在工作區中的[高階容量](https://docs.microsoft.com/power-bi/service-premium-what-is)。 
  
### <a name="enable-the-template-app"></a>啟用範本應用程式

若要啟用的範本應用程式，您必須是**全域系統管理員**、**報告讀取者**、 **Exchange 系統管理員**、**商務用 Skype 系統管理員**或**SharePoint 系統管理員**。 
  
如需詳細資訊，請參閱[關於系統管理員角色](../add-users/about-admin-roles.md)。 
  
1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。 
    
2. 在 [**使用狀況**] 頁面上，找出 [ **Microsoft 365 使用情況分析**卡片，並選取**要開始**。
    
3. 在報表上會開啟的面板設**使可 Power bi 的 Microsoft 365 使用情況分析的資料****上** \> **儲存**。 
  
這會資料收集程序，且會視您的租用戶大小而定的 2 到 48 小時內完成。 **移至 Power BI** ] 按鈕將會啟用 （不再灰色） 資料收集完畢時。 
    
### <a name="initiate-the-template-app"></a>啟動的範本應用程式

若要啟動的範本應用程式，您必須是**全域系統管理員**、**報告讀取者**、 **Exchange 系統管理員**、**商務用 Skype 系統管理員**或**SharePoint 系統管理員**。 
  
1. 複製租用戶識別碼，然後選取 [**移至 Power BI**。
    
2.  當您移到 Power BI 時，進行登入。 從瀏覽功能表中選取應用程式->取得應用程式。    
  
3. 在 [**應用程式**] 索引標籤中，輸入 [搜尋] 方塊中的 Microsoft 365，然後選取 [ **Microsoft 365 使用情況分析** \> **取得它現在**。

    [![選取 [立即取得](../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  一旦安裝應用程式。 按一下 [上] 磚以開啟它。

5.  按一下 [**瀏覽應用程式**來檢視將含有範例資料的應用程式]。 按一下 [應用程式連線至您的組織資料的**連線**。

6.  按一下之後**連線**，在 [**連線至 Microsoft 365 使用情況分析**] 畫面上，輸入您在步驟 (1) 複製的識別碼在租用戶中\>**下一步**。
    
7. 在下一個畫面上，選取**oAuth2**作為**驗證方法** \> **登入**。 如果您選擇任何其他驗證方法，將會失敗的範本應用程式的連線。
    
    ![Choose oAuth2 as authentication method](../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. 一旦具現化範本應用程式的 Microsoft 365 流量分析儀表板將可在 Power BI 網頁。 儀表板的初始載入需要 2 到 30 分鐘。
  
租用戶層級彙總則可在所有報告。 **使用者層級的詳細資訊才會變成可用 1st 或 15 天後選擇中的行事曆月之後**。 這會影響使用者活動下的所有報告 (請參閱[瀏覽和運用 Microsoft 365 使用情況分析中的報告](navigate-and-utilize-reports.md)的祕訣如何檢視及使用這些報告)。
    
## <a name="make-the-collected-data-anonymous"></a>將收集的資料匿名化

若要將所有報表收集的資料匿名化，您必須是全域系統管理員。 這麼做會隱藏和範本應用程式中報告的使用者、 群組和網站名稱等識別資訊。
  
1. 在系統管理中心，移至 [**設定** \> **設定**，並在 [**服務**] 索引標籤中，選擇**報告**。
    
2. 選取 [**報告**]，然後再選擇**顯示匿名識別碼**。 使用狀況報告以及範本應用程式，取得套用此設定。
  
3. 選取 [**儲存變更**。
