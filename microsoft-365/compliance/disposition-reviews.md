---
title: 進行處置檢查的概覽
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 當您建立保留標籤以保留 Microsoft 365 中的內容時，您可以選擇在保留期間結束時觸發處置檢查。
ms.openlocfilehash: ee9ea34ee8527558af4d249364b539d3fa1f2fdd
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634971"
---
# <a name="overview-of-disposition-reviews"></a>進行處置檢查的概覽

當內容到達保留期間結束時，可能會有幾個原因會讓您複查內容，以決定是否可以安全地刪除（「已處置」）。 例如，您可能需要：
  
- 在訴訟或審計事件中，封存相關內容的刪除（「處置」）。
    
- 若內容有調研或歷史值，請將內容從處置清單中移除儲存在封存中。
    
- 若原始原則為暫存檔或臨時方案，請為內容指派不同的保留期間。
    
- 將內容傳回給用戶端或轉接至另一個組織。
    
當您在 Microsoft 365 規範中心、Microsoft 365 安全性中心或 Office 365 安全性 & 合規性中心建立保留標籤時，您可以選擇在保留期間結束時觸發處置檢查。 在處置評審中：
  
- 您選擇的人員會收到電子郵件通知，告知他們具有要審閱的內容。 請注意，每週會傳送通知。
    
- 檢閱者會移至**Disposition**安全性&amp;與合規性中心的「處置」頁面，以查看內容。 檢閱者可以查看每個保留標籤的專案數目等候處理，然後選取保留標籤以查看具有該標籤的所有內容。
    
- 對於每個檔或電子郵件，檢閱者可以：
    
  - 套用其他保留標籤。
    
  - 延長保留期間。
    
  - 永久刪除它。
    
- 檢閱者可以查看擱置中或已完成的處理，並將該清單匯出為 .csv 檔案。

> [!NOTE]
> 處置評審需要 Office 365 企業版 E5 訂閱。
  
處置評審可將內容包含在 Exchange 信箱、SharePoint 網站、OneDrive 帳戶和 Office 365 群組中。 只有在檢閱者選擇永久刪除內容之後，才會刪除等候在這些位置中進行處置檢查的內容。
  
![安全性與合規性中心中的「處置」頁面](../media/Retention-Dispositions-v2-page.png)


## <a name="setting-up-the-disposition-review-by-creating-a-retention-label"></a>建立保留標籤來設定處置評審

這是設定處置評審的基本工作流程。 請注意，此流程會顯示已發佈的保留標籤，然後由使用者手動套用;另外，也可以將觸發處置檢查的保留標籤自動套用至內容。
  
![顯示處置運作方式之流程的圖表](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
當您在 Office 365 中建立保留標籤時，會有一個選項可供進行處置檢查。 在保留原則中無法使用此選項，只是設定為保留內容的保留標籤。
  
如需保留標籤的詳細資訊，請參閱[保留標籤](labels.md)。
  
![標籤的保留設定](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> 當您指定選項時，**當專案準備好可供複查時通知人員**，請指定使用者。 此選項不支援 Office 365 群組。

## <a name="disposing-content"></a>處置內容

當檢閱者透過電子郵件通知出內容可供審閱時，他們可以前往安全性&amp;與合規性中心的「**處置**」頁面。 檢閱者可以查看每個保留標籤的專案數目等候處理，然後選取保留標籤以查看具有該標籤的所有內容。

在您選取保留標籤之後，下一個頁面會顯示該標籤的所有擱置的可處置。

![處置選項](../media/Retention-Disposition-options-v2.png)

然後，檢閱者可以： 
  
- 套用其他保留標籤。
    
- 擴充保留期間。
    
- 永久刪除專案。

請注意，檢閱者可以選取多個專案並同時加以處置。
    
如果檢閱者具有該位置的許可權，則檢閱者也可以使用連結來查看其原始位置的檔。 在處置檢查期間，內容永遠不會從其原始位置移動，永遠不會刪除，除非檢閱者選擇這麼做。
  
請注意，電子郵件通知會以每週為單位自動傳送給檢閱者。 因此，當內容到達保留期間結束時，最多可能需要7天的時間，檢閱者收到內容正等待處置的電子郵件通知。
  
另外請注意，所有的處理動作都會經過審核。 為了確保這一點，您必須在第一次處理動作之前至少開啟一天的審計-如需詳細資訊，請參閱[Search the audit log In Office &amp; 365 Security 規章遵循中心](search-the-audit-log-in-security-and-compliance.md)。 
  
## <a name="permissions-for-disposition"></a>進行處置的許可權

若要存取「**部署**」頁面，必須將「**處置管理**」角色和「 **View-Only 審計記錄**」角色指派給檢閱者。 [查看](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)指派角色的指示。

特定于**View-Only 的審計記錄**角色：

- 因為用於搜尋審核記錄的基準指令程式是 Exchange Online Cmdlet，所以您必須使用[Exchange online 中的 exchange 系統管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)，而不是使用安全性 & 規範中心中的 [**許可權**] 頁面，指派此角色的使用者。 如需相關指示，請參閱[Manage role groups In Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。

- 此角色不支援 Office 365 群組。 請改為指派使用者信箱或郵件使用者。
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a>永久刪除處置內容之前的時間

只有在檢閱者選擇永久刪除內容之後，才會刪除等候進行處置檢查的內容。 當檢閱者選擇此選項時，SharePoint 網站或 OneDrive 帳戶中的內容會符合本節所述的標準清理程式：[保留原則如何使用內容就地運作](retention-policies.md#how-a-retention-policy-works-with-content-in-place)。
  
這表示：
  
- 文件庫中的內容將會移到第一階段回收站中的**7 天內**，然後在該範圍後永久刪除**93 天**。 回收站不是由搜尋編制索引，因此其內容無法用於 eDiscovery 暫止保留。

- 在處理的**7 天內**，將會永久刪除保留的保留文件庫中的內容。

- Exchange 信箱中的專案會在處理的**14 天內**永久刪除。 （請注意，預設設定為14天，但可以設定為30天。）
    
## <a name="view-pending-dispositions-and-disposed-items"></a>查看暫止的處理及已釋放的專案

在 [**暫**止的處理] 頁面上，您可以查看特定保留標籤的擱置和完成的處理方式： 
  
- **擱置的處理**會顯示已到達保留期間結束並需要進行處置評審的專案。 檢查每個專案之後，決定是否要將不同的保留標籤套用至該專案、擴充保留期間或永久刪除。 您可以選取多個專案。
    
- [已**釋放的專案**] 索引標籤會顯示已透過處置檢查的永久刪除專案。 它們會顯示在這裡，因為永久刪除程式可能需要數天的時間，如上一節所述。 套用不同保留標籤的專案，或將其保留期間擴充為審閱的一部分，不會出現在這裡。

![處置索引標籤](../media/Retention-Disposition-tabs.png)
    
### <a name="filter-the-disposition-views"></a>篩選處置視圖

您可以依保留標籤或時間範圍來篩選這些視圖。 針對暫止的處理，時間範圍是以到期日為基礎。 若為已處置的專案，時間範圍會根據刪除日期。
  
![處置篩選選項](../media/Retention-filter-options.png)

### <a name="export-the-disposition-items"></a>匯出處置專案

此外，您可以將其中一個視圖中的專案匯出為您可以在 Excel 中開啟的 .csv 檔案。
  
![在 Excel 中匯出的處置資料](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

