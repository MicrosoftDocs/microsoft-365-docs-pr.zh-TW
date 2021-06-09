---
title: 使用稽核記錄中的共用稽核
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
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.collection:
- M365-security-compliance
- SPO_Content
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: 系統管理員可以瞭解如何在 Microsoft 365 審核記錄檔中使用共用審核，以找出與組織外部使用者共用的資源。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d26a8022f8d59aeb56a03c50ae546777c882ef7a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819293"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a>使用稽核記錄中的共用稽核

「共用」是 SharePoint 線上和商務用 OneDrive 中的主要活動，而且在組織中廣泛使用。 管理員可以在審核記錄中使用共用審核，以決定組織中共用的使用方式。 
  
## <a name="the-sharepoint-sharing-schema"></a>SharePoint 共用架構

共用事件 (不包括與共享原則及共用) 連結相關的事件，其主要方式是與檔案及資料夾相關的事件不同：一個使用者執行的動作會影響另一個使用者。 例如，當資源使用者 A 給使用者 B 存取檔時。 在此範例中，使用者 A 是  *作用*  中的使用者，而使用者 B 是  *目標使用者*。 在 SharePoint 檔案架構中，作用中使用者的動作只會影響檔本身。 當使用者 A 開啟檔案時， **FileAccessed** 事件所需的唯一資訊就是作用中的使用者。 若要解決這種差異，有一個稱為「 *SharePoint 共用架構*」的不同架構，可捕獲共用事件的詳細資訊。 這可確保系統管理員可以查看共用資源和共用資源之使用者的人員。 
  
共用架構會在與共享事件相關的審計記錄中提供兩個額外的欄位： 
  
- **TargetUserOrGroupType：** 識別目標使用者或群組是成員、來賓、SharePointGroup、SecurityGroup 或 Partner。

- **TargetUserOrGroupName：** 儲存與上一個範例中 (使用者 B 共用資源之目標使用者或群組的 UPN 或名稱) 。 

除了來自審計記錄架構（如 User、 *Operation 及 Date*）以外的其他屬性之外，這兩個欄位也可告訴您完整的 *情景，告訴* 您 *哪些* 使用者已 *與其共用哪個* 資源。 
  
還有另一個架構屬性非常重要的共用案例。 當您匯出審計記錄檔搜尋結果時，匯出之 CSV 檔案中的 [ **AuditData** ] 欄會儲存共用事件的相關資訊。 例如，當使用者與其他使用者共用網站時，可將目標使用者新增至 SharePoint 群組來完成。 **AuditData** 欄會捕獲此資訊，以提供系統管理員的上下文。 請參閱 [步驟 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) 以取得如何在 **AuditData** ] 欄中剖析資訊的指示。

## <a name="sharepoint-sharing-events"></a>共用事件 SharePoint

當使用者 *(使用者)* 想要與另一個使用者 (*目標* 使用者) 共用資源時，就會定義「共用」。 與外部使用者共用資源相關的審計記錄 (您組織外部的使用者，且在組織的 Azure Active Directory 中沒有來賓帳戶) 由下列事件（記錄在審計記錄檔中）識別：

- **SharingInvitationCreated：** 您組織中的使用者企圖共用資源 (可能是與外部使用者) 網站。 這會產生外部共用邀請傳送給目標使用者。 此時不會授與資源的存取權。

- **SharingInvitationAccepted：** 外部使用者已接受由行動使用者傳送的共用邀請，而且現在可以存取該資源。

- **AnonymousLinkCreated：** 匿名連結 (也稱為「任何人」連結) 會為資源建立。 因為匿名連結可以建立並複製，所以假設具有匿名連結的任何檔都已與目標使用者共用。

- **AnonymousLinkUsed：** 顧名思義，當使用匿名連結存取資源時，會記錄此事件。 

- **SecureLinkCreated：** 使用者已建立「特定人員連結」，以與特定人員共用資源。 這個目標使用者可能是您組織外部的人員。 共用資源的人員會在 **AddedToSecureLink** 事件的「審計」記錄中識別。 這兩個事件的時間戳記幾乎相同。

- **AddedToSecureLink：** 已將使用者新增至特定人員連結。 使用此事件中的 [ **TargetUserOrGroupName** ] 欄位來識別新增至對應的 [特定人員] 連結的使用者。 這個目標使用者可能是您組織外部的人員。

## <a name="sharing-auditing-work-flow"></a>共用審核工作流程
  
當使用者 (作用中使用者) 想要與另一個使用者共用資源時 (目標使用者) 、SharePoint (或商務用 OneDrive) 會先檢查目標使用者的電子郵件地址是否已與組織目錄中的使用者帳戶相關聯。 [！注意事項] 如果目標使用者在目錄中 (，且具有對應的 guest 使用者帳戶) ，SharePoint 會執行下列動作：
  
-  將目標使用者新增至適當的 SharePoint 群組，然後記錄 **AddedToGroup** 事件，立即指派目標使用者的許可權以存取資源。 
    
- 將共用通知傳送至目標使用者的電子郵件地址。
    
- 記錄 **SharingSet** 事件。 在「審核記錄搜尋」工具的 [活動] 中，此事件的「共用檔、資料夾或網站」的易記名稱是「共用」 **和「存取權要求** 」。 請參閱 [步驟 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file)中的螢幕擷取畫面。 
    
若目標使用者的使用者帳戶不在目錄中，SharePoint 會執行下列作業： 
    
   - 根據共用資源的方式，記錄下列其中一項事件：
   
      - **AnonymousLinkCreated**
   
      - **SecureLinkCreated**
   
      - **AddedToSecureLink** 

      - **SharingInvitationCreated** (只有當共用資源是網站時，才會記錄此事件) 
    
   - 當目標使用者接受傳送給他們的共用邀請時 (按一下邀請函) 中的連結時，SharePoint 會記錄 **SharingInvitationAccepted** 事件，並指派目標使用者許可權來存取資源。 若目標使用者已傳送匿名連結，則會在目標使用者使用連結存取資源之後記錄 **AnonymousLinkUsed** 事件。 針對安全連結，當外部使用者使用連結存取資源時，會記錄 **FileAccessed** 事件。

也會記錄有關目標使用者的其他資訊，例如邀請的使用者識別碼，以及接受邀請的使用者。 在某些情況下，這些使用者 (或電子郵件地址) 可能不同。 

## <a name="how-to-identify-resources-shared-with-external-users"></a>如何識別與外部使用者共用的資源

管理員的常見需求是建立與組織外部使用者共用的所有資源清單。 在 Office 365 中使用共用審核，管理員可以產生此清單。 方法如下。
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>步驟1：搜尋共用事件，並將結果匯出至 CSV 檔案

第一步是在審核記錄中搜尋共用事件。 如需詳細資訊 (包括搜尋審核記錄檔所需的許可權) ，請參閱在 [安全性 & 規範中心搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用您的公司或學校帳戶登入。
    
3. 在安全性與合規性中心的左窗格中，按一下 [搜尋]   >  [稽核記錄搜尋]。
    
    [稽核記錄搜尋] 頁面隨即顯示。 
    
4. 在 [ **活動**] 底下，按一下 [ **共用和存取要求活動** ] 以搜尋共用相關事件。 
    
    ![在 [活動] 底下，選取 [共用和存取要求活動]](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  選取 [日期和時間範圍]，以尋找在該期間內發生的共用事件。 
    
6. 按一下 [ **搜尋** ] 以執行搜尋。 
    
7. 當搜尋執行完畢並顯示結果之後，按一下 [ **匯出結果**] \> **下載所有結果**。
    
    選取 [匯出] 選項之後，視窗底部的訊息會提示您開啟或儲存 CSV 檔案。
    
8. 按一下 [**另** 存新檔] \>  ，將 CSV 檔案儲存至本機電腦上的資料夾。 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a>步驟2：使用 PowerQuery 編輯器格式化匯出的審計記錄檔

下一步是在 Power Query 編輯器 Excel 中使用 JSON 轉換功能，以分割 **AuditData** 欄中的每個屬性， (是由多屬性 JSON 物件) 放在自己的欄中。 這可讓您篩選欄，以查看與共享相關的記錄

如需逐步指示，請參閱[匯出、設定及檢視稽核記錄檔的記錄](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)中的「步驟 2：使用 Power Query 編輯器設定匯出之稽核記錄的格式」(部分機器翻譯)。

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a>步驟3：篩選 CSV 檔案以取得與外部使用者共用的資源

下一步是篩選 CSV，以取得先前在「 [SharePoint 共用事件](#sharepoint-sharing-events)」區段中所述的不同共用相關事件。 或者，您也可以篩選 **TargetUserOrGroupType** 欄，以顯示此屬性的值為 **Guest** 的所有記錄。 

在您遵循上一個步驟中的指示，使用 PowerQuery 編輯器準備 CSV 檔案之後，請執行下列操作：
    
1. 開啟您在步驟2中建立的 Excel 檔案。 

2. 在 [ **首頁** ] 索引標籤上，按一下 [ **排序 & 篩選**]，然後按一下 [ **篩選**]。
    
3. 在 [**作業**] 欄上的 [**排序 & 篩選**] 下拉式清單中，清除所有選取專案，然後選取下列一或多個與共享相關的事件，然後按一下 **[確定]**。
 
   - **SharingInvitationCreated**
   
   - **AnonymousLinkCreated**
   
   - **SecureLinkCreated**
   
   - **AddedToSecureLink** 
    
    Excel 會顯示所選取之事件的列。
    
4. 移至名為 **TargetUserOrGroupType** 的欄，並選取它。 
    
5. 在 [ **排序 & 篩選** ] 下拉式清單中，清除所有選取專案，然後選取 [ **TargetUserOrGroupType：來賓**]，然後按一下 **[確定]**。
    
    現在 Excel 會顯示共用事件的列，以及目標使用者在組織外部的位置，因為 **TargetUserOrGroupType：來賓** 的值會識別外部使用者。 
  
> [!TIP]
> 對於顯示的審計記錄，[ **ObjectId** ] 欄位會識別與目標使用者共用的資源;例如  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx` 。
