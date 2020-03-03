---
title: 在管理中心中的電子郵件 app 使用情況的 Microsoft 365 報告
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: c2ce12a2-934f-4dd4-ba65-49b02be4703d
description: 了解如何取得電子郵件 app 使用情況報告來了解電子郵件應用程式連線到 Exchange Online，而且所使用的 Outlook 版本使用者。
ms.openlocfilehash: bb75b28e41de37d4f21acedd4705db71f6c2c303
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353784"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>在管理中心中的電子郵件 app 使用情況的 Microsoft 365 報告

Microsoft 365**報告**儀表板顯示您的活動概觀跨組織中的產品。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。 在 [電子郵件應用程式使用量] 報告中，您可以看到多少電子郵件 app 正在連線到 Exchange Online。 您也可以看到使用者正在使用之 Outlook App 的版本資訊，這可讓您追蹤使用不支援之版本的使用者，並要求他們安裝支援的 Outlook 版本。
  
> [!NOTE]
> 您必須是全域系統管理員、 全域讀者或報告讀取者，在 Microsoft 365 或 Exchange、 SharePoint 或 Skype 商務系統管理員，才能查看報告。 
 
## <a name="how-to-get-to-the-email-apps-report"></a>如何取得電子郵件 app 報表

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。

    
2. 從 [**選取 [報告]** 下拉式清單，選取 [ **Exchange** \> **電子郵件 app 使用情況**。
  
## <a name="interpret-the-email-apps-report"></a>解讀電子郵件 app 報表

您可以透過檢視電子郵件 app 活動查看 [**使用者**] 和 [**用戶端**圖表。 
  
![電子郵件用戶端使用情況](../../media/2a775e46-750f-4fa6-8197-de4b24614bd7.png)
  
|||
|:-----|:-----|
|1.  <br/> |**電子郵件 app 使用情況**報告可檢視的趨勢，過去 7 天、 30 天、 前 90 天或 180 天。 不過，如果您在報表中選取的特定一天，表格 (7) 將會顯示資料 28 天，從目前的日期 （不是該報告產生的日期）。  <br/> |
|2.  <br/> |每個報告中的資料通常涵蓋的最後一個 24 到 48 小時。  <br/> |
|3.  <br/> |[**使用者**] 檢視會顯示您連線至 Exchange Online 的唯一使用者數目使用任何電子郵件應用程式。  <br/> |
|4.  <br/> |**應用程式**檢視您的唯一使用者數目會依據 app 顯示在選取的時間期間。  <br/> |
|5.  <br/> |[**版本**] 檢視您的每個版本的 Outlook 的唯一使用者數目視窗中顯示。  <br/> |
|6.  <br/> | 在 [**使用者**] 圖表中，Y 軸是連結到 app 的報表期間任何一天的單獨使用者數總計。  <br/>  在 [**使用者**] 圖表上，X 軸是數字的應用程式用於報表期間內的單獨使用者。  <br/>  在 [ **App** ] 圖表中，Y 軸是在報告期間內使用特定 app 的唯一使用者總數。  <br/>  在 [ **App** ] 圖表中，X 軸是您的組織中的應用程式清單。  <br/>  在 [**版本**] 圖表中，Y 軸是使用特定電腦版 Outlook 的唯一使用者總數。 若報表無法解析 Outlook 的版本號碼，數量將顯示為「未定」。  <br/>  [**版本**] 圖表上的 X 軸是您的組織中的應用程式清單。  <br/> |
|7.  <br/> |您可以篩選圖表 selectingan 項目在圖例中所見的數列。 例如，在 [**使用者**] 圖表中，選取 [ **Mac 郵件**] 或 [ **Outlook** ![電子郵件用戶端的清單。 選取 [電子郵件用戶端的用戶端上取得更多報告資料。](../../media/19b9da1b-7b69-4a04-8527-38349f859e84.png) ，以查看只與各類別相關的資訊。 變更此區段不會變更格線表格中的資訊。 Mac 郵件、Mac 版 Outlook、Outlook Mobile、電腦版 Outlook 與 Outlook 網頁版都是您組織中可能擁有的電子郵件 App 範例。  <br/> |
|8.  <br/> | 您可能無法在欄中看到下方清單中的所有項目，直到您新增那些項目之後才會出現。<br/> **Username**是電子郵件應用程式的擁有者的名稱。  <br/> **[上次活動日期**是使用者讀取或傳送電子郵件訊息的最晚日期。  <br/> **Mac 郵件**、 **Mac Outlook**與**Outlook**、 **Outlook mobile**和**outlook 網頁版**是您組織中可能擁有的電子郵件應用程式的範例。  <br/>  如果貴組織的原則防止您檢視可識別之使用者資訊的報告，您可以變更所有這類報告的隱私權設定。 請參閱**如何隱藏使用者層級的詳細資訊？** ] 區段中[的 Microsoft 365 系統管理中心的活動報告](activity-reports.md)中。  <br/> |
|9.  <br/> |選取 [**管理欄]** 來新增或移除報告中的欄。  <br/> ![電子郵件 app 使用情況報告-選擇欄](../../media/c17b2a5c-db41-474a-8334-0e5a621b2f16.png)|
|10.  <br/> |您可以也報告資料匯出到 Excel.csv 檔案，藉由選取 [**匯出**] 連結。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。  <br/> |
|||
   

