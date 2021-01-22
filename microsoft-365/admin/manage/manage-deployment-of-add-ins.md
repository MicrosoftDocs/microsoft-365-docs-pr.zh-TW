---
title: 在系統管理中心部署增益集
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
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 瞭解如何使用系統管理中心的集中式部署，將外掛程式部署到貴組織的使用者和群組。
ms.openlocfilehash: ef7237f20780cb67bc84561ad8617dd8da6f8b82
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926351"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>在系統管理中心部署增益集

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。

::: moniker-end

Office 增益集可以協助您將文件個人化，也可以簡化您存取網路資訊的方式 (請參閱[開始使用 Office 增益集](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862))。 系統管理員可以使用 Microsoft 365 系統管理中心的集中式部署功能，為貴組織的使用者部署 Office 外掛程式。 若要將外掛程式部署到組織內部的使用者和群組，集中式部署是建議大多數系統管理員採用且功能最豐富的方法。 

若要瞭解如何判斷貴組織是否可支援集中式部署，請參閱判斷貴組織是否適合使用集中式部署來 [部署附加元件](centralized-deployment-of-add-ins.md)。

若要深入瞭解在部署後管理附加元件，請參閱在系統管理中心管理 [外掛程式](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  針對 Word，Excel 和 PowerPoint 會使用 [SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) 應用程式目錄，在內部部署環境中將外掛程式部署到使用者，而不需要連至 Microsoft 365 和/或 SharePoint 需要之支援。 針對 Outlook，請使用 Exchange 控制台在內部部署環境中部署，而不需要連至 Microsoft 365。
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>部署 Office 增益集的建議方式

若要使用階段方法推出附加元件，建議您進行下列操作：
  
1. 向一小組商務專案關係人以及 IT 部門的成員推出此附加元件。 如果部署成功，請移至步驟 2。
    
2. 為更多企業內部人員推出此附加元件。 再次評估結果，如果成功，請繼續進行完整部署。
    
3. 對所有使用者執行完整推出。
    
視目標物件的大小不同，您可以新增或移除推出步驟。
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>使用系統管理中心部署 Office 外掛程式

開始之前，請參閱判斷貴組織是否適合使用集中式部署 [來部署附加元件](centralized-deployment-of-add-ins.md)。
  
1. 在系統管理中心中，前往設定 \> **載入碼** 頁面。 如果您沒看到載入 **元件頁面，** 請前往設定整合式應用程式 \>  \> **載入元件** 頁面。
    
2. 選取 **頁面頂端的部署** 載入元件，然後選取下一 **步**。
 
    > [!NOTE]
    > 系統管理中心已更新為整合式應用程式的部署體驗。 如果您沒看到上述步驟，請前往設定整合式應用程式，以前往集中式部署  >  **區段**。 在整合式應用程式 **頁面的頂端** ，選擇 **載入元件**。
    
3. 選取一個選項，然後按照指示進行。
  
4. 如果您選取了從 Office 市儲存新增附加元件的選項，請選取您的附加元件。 </br>

    您可以按類別來查看可用的附加元件：**針對** 您建議、**評分或****名稱**。 Office 市儲存僅提供免費的附加元件。 目前尚不支援付費增益集。 選取某個附加元件之後，請接受條款與條件以繼續進行。 <br/> 

    > [!NOTE] 
    > 使用 Office 市儲存區選項時，更新和增強功能會自動部署至使用者。

5. 在下一頁中，選取所有人、特定使用者 **/** 群組，或只選取我來指定要將載入元件部署到哪些人員。 使用搜尋方塊尋找特定使用者或群組。 <br/>

    > [!NOTE] 
    > 若要瞭解適用于附加元件的其他狀態，請參閱 [In-in 狀態](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)。
  
6. 選取 **部署**。
  
7. 部署該附加元件時，會出現綠色刻度。 請遵循頁面上的指示測試載入元件。

    > [!NOTE]
    > 使用者可能需要重新開機 Office，以在 App 功能區上查看此附加元件圖示。 Outlook 外掛程式最多可能需要 24 小時才能顯示在 App 功能區上。
    
8. 完成後，選取下一 **步**。 如果您只為自己部署，您可以選取變更誰具有 **該附加** 元件的存取權限，以部署到更多使用者。

    如果您已經將該附加元件部署到組織的其他成員，請按照指示宣告該附加元件部署。 <br/>
  
    建議告知使用者和群組已部署之附加元件可供使用。 請考慮傳送一封電子郵件，說明何時及如何使用該附加元件。 包含或連結至協助使用者解決此附加元件問題的內容或常見問題。
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>將增益集指派給使用者和群組時的考慮事項

系統管理員可以將增益集指派給所有人或特定的使用者和群組。 每個選項都有其意涵：
  
- **所有人** 此選項會指派此外掛程式給組織每個使用者。 請謹慎使用此選項，並且只有在貴組織需要普遍使用此增益集時才使用此選項。 
    
- **使用者** 如果您將一個附加元件指派給個別使用者，然後將該附加元件部署到新的使用者，您必須先新增使用者。
    
- **群組** 如果您將一個附加元件指派給群組，則新加入群組的使用者會自動被指派該附加元件。 當使用者從群組移除時，該使用者會失去該附加元件的存取權限。 任一種情況下，管理員都不需要執行額外的動作。 

- **僅自己** 如果您只將一個附加元件指派給自己，則只會將這個附加元件指派給您的帳戶，這是測試該附加元件的理想方法。
    
適用于貴組織的正確選項取決於您的組選。 不過，我們建議您使用群組進行指派。 系統管理員可能會發現，使用群組及控制這些群組的成員資格，而非每次指派個別使用者，以輕鬆管理附加元件。 在某些情況下，您可能會想要手動指派使用者給特定使用者，以限制一小組使用者的存取權。
  
## <a name="more-about-office-add-ins-security"></a>Office 附加元件安全性的更多資訊

Office 增益集會與內含部分增益集中繼資料的 XML 資訊清單檔案合併，但最重要的是，Office 增益集會與指向包含所有程式碼和邏輯的 Web 應用程式合併。增益集可以有各種不同的功能。例如，增益集可以：
  
- 顯示資料。
    
- 閱讀使用者的文件以提供內容相關服務。
    
- 從使用者的文件讀取及寫入資料，以提供值給該使用者。
    
如需 Office 增益集類型和功能的詳細資訊，請參閱 [Office 增益集平台概觀](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins) (尤其是「分析 Office 增益集」一節)。
  
若要與使用者的文件互動，增益集必須在資訊清單中宣告需要的權限。五個層級的 JavaScript API 存取權限模型可為工作窗格增益集使用者提供基本的隱私權和安全性。Office 市集中的大多數增益集為 ReadWriteDocument 層級，且包含至少 ReadDocument 層級的大部分增益集支援功能。如需權限層級的詳細資訊，請參閱[要求取得用於內容和工作窗格增益集之 API 的權限](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins) (英文)。
  
更新資訊清單時，通常是變更增益集的圖示和文字。有時則會變更增益集的命令。不過，增益集的權限不會遭到變更。執行增益集的所有程式碼和邏輯的 Web 應用程式可能隨時變更，這是 Web 應用程式的本質所致。
  
增益集的更新會以下列方式進行：
  
- **企業經營型附加元件：** 在此案例中，當系統管理員明確上傳的顯示清單時，需要系統管理員上傳新的清單檔案以支援中繼資料變更。 在下次啟動相關的 Office 應用程式時，增益集就會更新。 Web 應用程式可以隨時變更。 

    > [!NOTE]
    > 系統管理員不需要移除 LOB 外掛程式，也不需要執行更新。   在 [附加元件> 區段，系統管理員只要按一下 LOB Add-in，然後選擇右下角的更新按鈕即可。 只有當新附加元件的版本大於現有附加元件版本時，更新才能作用。   
    
- **Office 市商店的附加元件：** 當系統管理員從 Office 市集選取一個附加元件時，如果 Office 市集中有附加元件更新，該附加元件稍後將會于集中式部署中更新。 在下次啟動相關的 Office 應用程式時，增益集就會更新。 Web 應用程式可以隨時變更。 
  
## <a name="learn-more"></a>深入了解

[在系統管理中心管理增益集](manage-addins-in-the-admin-center.md)

[建立您的第一個 Word 工作窗格附加元件](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)。

[從商店取得次要和取得外掛程式](minors-and-acquiring-addins-from-the-store.md)
  
[使用集中式部署 PowerShell Cmdlet 來管理外掛程式](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[疑難排解：使用者看不到外掛程式](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
