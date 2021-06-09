---
title: Microsoft 365系統管理中心的報告-電子郵件應用程式使用方式
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: c2ce12a2-934f-4dd4-ba65-49b02be4703d
description: 瞭解如何取得「電子郵件應用程式使用方式」報告，以瞭解如何連接至 Exchange Online 的電子郵件應用程式，以及使用者所使用 Outlook 版本。
ms.openlocfilehash: f2a7b79a00b47896dac4427c532f85dccb931c60
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921929"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Microsoft 365系統管理中心的報告-電子郵件應用程式使用方式

[Microsoft 365 **報告**] 儀表板會顯示您組織中產品的活動概況。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。 在 [電子郵件應用程式使用狀況] 報告中，您可以看到有多少電子郵件應用程式正在連接至 Exchange Online。 您也可以看到使用者正在使用之 Outlook App 的版本資訊，這可讓您追蹤使用不支援之版本的使用者，並要求他們安裝支援的 Outlook 版本。
  
> [!NOTE]
> 您必須是全域系統管理員、全域讀取者或報告讀取者 Microsoft 365 或 Exchange、SharePoint、Teams 服務、Teams 通訊或商務用 Skype 管理員查看報告。  
 
## <a name="how-to-get-to-the-email-apps-report"></a>如何取得「電子郵件應用程式」報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。
2. 選取 [**電子郵件活動**] 底下的 [**流覽**]。 
3. 從 [**電子郵件活動**] 下拉式清單中，選取 [ **Exchange** \> **電子郵件應用程式使用**]。
  
## <a name="interpret-the-email-apps-report"></a>轉譯電子郵件應用程式報告

您可以查看 [ **使用者** ] 和 [ **用戶端** ] 圖表，以取得電子郵件應用程式活動的方式。 
  
![使用的電子郵件客戶程式](../../media/d78af7db-2b41-4d37-8b6e-bc7e47edd1dd.png)
  
|項目|描述|
|:-----|:-----|
|1.  <br/> |您可以針對過去7天、30天、90天或180天的趨勢，查看「 **電子郵件應用程式使用方式** 報告」。 不過，如果您在報告中選取某一天，則 table (7) 會從目前的日期顯示最多28天的資料， (不是) 產生報表的日期。  <br/> |
|2.  <br/> |每個報告中的資料通常會涵蓋過去24到48小時。  <br/> |
|3.  <br/> |[**使用者**] 視圖會顯示使用任何電子郵件應用程式連線至 Exchange Online 的唯一使用者數目。  <br/> |
|4.  <br/> |[ **應用程式** ] 視圖會以應用程式為您顯示選取的時段內，依應用程式的唯一使用者數目。  <br/> |
|5.  <br/> |**版本** 視圖會顯示 Windows 中每個 Outlook 版本的唯一使用者數目。  <br/> |
|6.  <br/> | 在 [ **使用者** ] 圖表上，Y 軸是在報表期間的任意一天連接至應用程式的唯一使用者總數。  <br/>  在 [ **使用者** ] 圖表上，X 軸是使用該報告期間之應用程式的唯一使用者數目。  <br/>  在 [ **應用程式** ] 圖表上，Y 軸是在報表期間內使用特定 app 的唯一使用者總數。  <br/>  在 [ **app** ] 圖表上，X 軸是您組織中的應用程式清單。  <br/>  在 [**版本**] 圖表上，Y 軸是使用特定版本 Outlook 桌面的唯一使用者總數。 如果報表無法解析 Outlook 的版本號碼，該數量會顯示為 **未定**。  <br/>  在 [ **版本** ] 圖表上，X 軸是您組織中的應用程式清單。  <br/> |
|7.  <br/> |您可以選取圖例中的專案，以篩選您在圖表上看到的數列。  <br/> |
|8.  <br/> | 您可能無法在欄中看到下方清單中的所有項目，直到您新增那些項目之後才會出現。<br/> **Username** 是電子郵件應用程式擁有者的名稱。  <br/> [**上次活動日期**] 是使用者讀取或傳送電子郵件訊息的最晚日期。  <br/> **mac 郵件**、 **mac Outlook** 和 **Outlook**、 **Outlook** **網頁上** 的行動和 Outlook 都是您組織中可能擁有的電子郵件 app 範例。  <br/>  如果貴組織的原則防止您檢視可識別之使用者資訊的報告，您可以變更所有這類報告的隱私權設定。 請參閱 [Microsoft 365 系統管理中心的活動報告中](activity-reports.md)的 [**我要如何隱藏使用者層級詳細資料？** ] 區段。  <br/> |
|9.  <br/> |選取 **[選擇欄位** ]，以新增或移除報告中的欄。  <br/> ![電子郵件應用程式使用方式報告-選擇欄](../../media/041bd6ff-27e8-409d-9608-282edcfa2316.png)|
|10.  <br/> |您也可以選取 [**匯出**] 連結，將報表資料匯出至 Excel .csv 檔案中。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。  <br/> |
|||
   
