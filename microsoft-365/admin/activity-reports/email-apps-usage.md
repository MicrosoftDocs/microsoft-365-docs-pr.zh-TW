---
title: 系統管理中心的 Microsoft 365 報告-電子郵件應用程式使用方式
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
description: 瞭解如何取得「電子郵件應用程式使用方式」報告，以瞭解如何連線至 Exchange Online 和 Outlook 版本使用者所使用的電子郵件應用程式。
ms.openlocfilehash: c6ee72390f0b9e9ead0f07c41d64bf5b7264fc1b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948241"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>系統管理中心的 Microsoft 365 報告-電子郵件應用程式使用方式

Microsoft 365 **報告** 儀表板會向您顯示組織中各產品的活動概況。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。 在 [電子郵件應用程式使用狀況] 報告中，您可以看到有多少電子郵件應用程式正在連線到 Exchange Online。 您也可以看到使用者正在使用之 Outlook App 的版本資訊，這可讓您追蹤使用不支援之版本的使用者，並要求他們安裝支援的 Outlook 版本。
  
> [!NOTE]
> 您必須是 Microsoft 365 中的全域系統管理員、全域讀取者或報告讀取器、Exchange、SharePoint、小組服務、小組通訊或商務用 Skype 系統管理員，才能查看報告。  
 
## <a name="how-to-get-to-the-email-apps-report"></a>如何取得「電子郵件應用程式」報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。

    
2. 從 [ **選取報告** ] 下拉式清單中，選取 [ **Exchange** \> **電子郵件 app 使用狀況**]。
  
## <a name="interpret-the-email-apps-report"></a>轉譯電子郵件應用程式報告

您可以查看 [ **使用者** ] 和 [ **用戶端** ] 圖表，以取得電子郵件應用程式活動的方式。 
  
![使用的電子郵件客戶程式](../../media/2a775e46-750f-4fa6-8197-de4b24614bd7.png)
  
|項目|描述|
|:-----|:-----|
|1.  <br/> |您可以針對過去7天、30天、90天或180天的趨勢，查看「 **電子郵件應用程式使用方式** 報告」。 不過，如果您在報告中選取某一天，則 table (7) 會從目前的日期顯示最多28天的資料， (不是) 產生報表的日期。  <br/> |
|2.  <br/> |每個報告中的資料通常會涵蓋過去24到48小時。  <br/> |
|3.  <br/> |[ **使用者** ] 視圖會顯示使用任何電子郵件應用程式連線至 Exchange Online 的特殊使用者數目。  <br/> |
|4.  <br/> |[ **應用程式** ] 視圖會以應用程式為您顯示選取的時段內，依應用程式的唯一使用者數目。  <br/> |
|5.  <br/> |**版本**視圖顯示 Windows 中每個 Outlook 版本的唯一使用者數目。  <br/> |
|6.  <br/> | 在 [ **使用者** ] 圖表上，Y 軸是在報表期間的任意一天連接至應用程式的唯一使用者總數。  <br/>  在 [ **使用者** ] 圖表上，X 軸是使用該報告期間之應用程式的唯一使用者數目。  <br/>  在 [ **應用程式** ] 圖表上，Y 軸是在報表期間內使用特定 app 的唯一使用者總數。  <br/>  在 [ **app** ] 圖表上，X 軸是您組織中的應用程式清單。  <br/>  在 [ **版本** ] 圖表上，Y 軸是使用特定版本 Outlook desktop 的唯一使用者總數。 如果報表無法解析 Outlook 的版本號碼，該數量會顯示為 **未定**。  <br/>  在 [ **版本** ] 圖表上，X 軸是您組織中的應用程式清單。  <br/> |
|7.  <br/> |您可以選取圖例中的專案，以篩選您在圖表上看到的數列。 例如，在 [ **使用者** ] 圖表上，選取 [ **Mac 郵件** ] 或 [ **Outlook** ![ 的電子郵件用戶端清單]。 選取電子郵件客戶程式以在該用戶端上取得更多報告資料。](../../media/19b9da1b-7b69-4a04-8527-38349f859e84.png) ，以查看只與各類別相關的資訊。 變更此區段不會變更格線表格中的資訊。 Mac 郵件、Mac 版 Outlook、Outlook Mobile、電腦版 Outlook 與 Outlook 網頁版都是您組織中可能擁有的電子郵件 App 範例。  <br/> |
|8.  <br/> | 您可能無法在欄中看到下方清單中的所有項目，直到您新增那些項目之後才會出現。<br/> **Username** 是電子郵件應用程式擁有者的名稱。  <br/> [**上次活動日期**] 是使用者讀取或傳送電子郵件訊息的最晚日期。  <br/> **Mac 郵件**、 **Mac outlook** 和 **outlook**、 **outlook mobile** 和 outlook **網頁** 版都是您組織中可能擁有的電子郵件 app 範例。  <br/>  如果貴組織的原則防止您檢視可識別之使用者資訊的報告，您可以變更所有這類報告的隱私權設定。 請參閱[Microsoft 365 系統管理中心的活動報告中](activity-reports.md)的 [**我要如何隱藏使用者層級詳細資料？** ] 區段。  <br/> |
|9.  <br/> |選取 [ **管理欄** ] 以新增或移除報告中的欄。  <br/> ![電子郵件應用程式使用方式報告-選擇欄](../../media/82008680-cd28ab00-9686-11ea-8692-b3d72117c20b.png)|
|10.  <br/> |您也可以選取 [ **匯出** ] 連結，將報告資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。  <br/> |
|||
   
