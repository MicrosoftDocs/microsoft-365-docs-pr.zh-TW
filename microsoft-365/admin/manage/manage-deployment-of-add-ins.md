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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 瞭解如何使用系統管理中心的集中式部署，將增益集部署至組織中的使用者和群組。
ms.openlocfilehash: 51db2bf7b618bddf2c6de417b7f5e53c91a64a1b
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/11/2020
ms.locfileid: "45102857"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>在系統管理中心部署增益集

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。

::: moniker-end

Office 增益集可以協助您將文件個人化，也可以簡化您存取網路資訊的方式 (請參閱[開始使用 Office 增益集](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862))。 身為系統管理員，您可以使用 Microsoft 365 系統管理中心的 [集中式部署] 功能，為組織中的使用者部署 Office 增益集。 若要將增益集部署至組織內的使用者和群組，[集中式部署] 是建議和功能最豐富的方法。 

如需如何判斷您的組織是否可支援集中式部署的詳細資訊，請參閱判斷您的組織是否可使用[集中式部署增益集](centralized-deployment-of-add-ins.md)。

若要深入瞭解如何在部署後管理增益集，請參閱[在系統管理中心管理增益集](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  Word、Excel 及 PowerPoint 會使用[SharePoint 應用程式目錄](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)，將增益集部署至內部部署環境中的使用者，但不連接至 Microsoft 365 和/或支援所需 SharePoint 增益集。 Outlook 使用 Exchange 控制台在內部部署環境中部署，但不連接至 Microsoft 365。
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>部署 Office 增益集的建議方式

若要使用逐步式方法來推出增益集，建議您執行下列作業：
  
1. 將增益集推出給一小部分的商務專案關係人和 IT 部門的成員。 如果部署成功，請移至步驟2。
    
2. 向商務中的更多人員推出增益集。 請再次評估結果，如果成功，則繼續進行完整部署。
    
3. 對所有使用者執行完整的展示。
    
視目標物件的大小而定，您可以新增或移除向外展開步驟。
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>使用系統管理中心部署 Office 增益集

開始之前，請參閱[判斷集中式部署的增益集是否適用于您的組織](centralized-deployment-of-add-ins.md)。
  
1. 在系統管理中心中，移至 [**設定** \> **增益集**] 頁面。
    
2. 選取頁面頂端的 [**部署增益集**]，然後選取 **[下一步]**。
    
3. 選取 [選項]，然後依照指示執行。
  
4. 如果您選取 [從 Office Store 新增增益集] 選項，請讓增益集成為選取範圍。 </br>

    您可以依類別來查看可用的增益集：**建議您**、**評級**或**名稱**。 Office Store 只有免費的增益集可供使用。 目前尚不支援付費增益集。 選取增益集之後，請接受條款及條件以繼續。 <br/> 

    > [!NOTE] 
    > 透過 Office Store 選項，更新及增強功能會自動給使用者。

5. 在下一個頁面上，選取 [**所有人**]、[**特定使用者/群組**] 或 [**僅限我**]，以指定要部署增益集的人員。 使用 [搜尋] 方塊尋找特定的使用者或群組。 <br/>

    > [!NOTE] 
    > 若要瞭解適用于增益集的其他狀態，請參閱[增益集狀態](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)。
  
6. 選取 [**部署**]。
  
7. 部署增益集時，會出現綠色的勾選標記。 依照頁面上的指示測試增益集。

    > [!NOTE]
    > 使用者可能需要重新開機 Office 來查看應用程式功能區上的增益集圖示。 Outlook 增益集最多可能需要24小時才能出現在應用程式功能區上。
    
8. 完成時，選取 **[下一步]**。 如果您只是自行部署，您可以選取 [**變更可存取增益集的人員**]，以部署至其他使用者。

    如果您已將增益集部署至組織的其他成員，請依照指示宣告增益集的部署。 <br/>
  
    建議使用已部署增益集的使用者和群組。 請考慮傳送描述何時及如何使用增益集的電子郵件。 包含或連結，以協助內容或 FAQs 如果增益集發生問題，可能會協助使用者。
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>將增益集指派給使用者和群組時的考慮事項

系統管理員可以將增益集指派給所有人或特定的使用者和群組。 每個選項都有其意涵：
  
- **所有人**此選項會將增益集指派給組織中的每一位使用者。 請謹慎使用此選項，並且只有在貴組織需要普遍使用此增益集時才使用此選項。 
    
- **使用者**如果您將增益集指派給個別使用者，然後將增益集部署至新的使用者，您必須先新增新的使用者。
    
- **群組**如果您將增益集指派給群組，則新增至群組的使用者會自動指派增益集。 當使用者從群組中移除時，使用者將無法存取增益集。 在這兩種情況下，系統管理員不需要其他的動作。 

- **僅自己**如果您將增益集指派給您自己，增益集就會指派給您的帳戶，這是測試增益集的理想選擇。
    
組織的右選項視您的設定而定。 不過，我們建議您使用群組來進行工作分派。 身為系統管理員，您可能會發現使用群組來管理增益集及控制這些群組的成員資格，而不是每次指派個別使用者。 在某些情況下，您可能會想要限制一小部分使用者的存取，只要手動指派使用者給特定的使用者。
  
## <a name="more-about-office-add-ins-security"></a>更多關於 Office 增益集的安全性

Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:
  
- 顯示資料。
    
- 閱讀使用者的文件以提供內容相關服務。
    
- 從使用者的文件讀取及寫入資料，以提供值給該使用者。
    
如需 Office 增益集類型和功能的詳細資訊，請參閱 [Office 增益集平台概觀](https://go.microsoft.com/fwlink/p/?linkid=846362) (尤其是「分析 Office 增益集」一節)。
  
To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863).
  
When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.
  
增益集的更新會以下列方式進行：
  
- **企業營運增益集：** 在此情況下，管理員明確上傳資訊清單的地方，增益集需要系統管理員上載新的資訊清單檔案，以支援中繼資料變更。 在下次啟動相關的 Office 應用程式時，增益集就會更新。 Web 應用程式可以隨時變更。 

    > [!NOTE]
    > 管理員不需要移除 LOB 增益集進行更新。   在 [增益集] 區段中，系統管理員只要按一下 LOB 增益集，然後選擇右下角的 [**更新] 按鈕**即可。 只有當新增益集的版本高於現有增益集的版本時，更新才會運作。   
    
- **Office Store 增益集：** 當系統管理員從 Office Store 中選取增益集時，如果 Office Store 中的增益集更新，增益集將在稍後的集中式部署中更新。 在下次啟動相關的 Office 應用程式時，增益集就會更新。 Web 應用程式可以隨時變更。 
  
## <a name="learn-more"></a>深入了解

建立及建立[Office 增益集](https://go.microsoft.com/fwlink/p/?linkid=846362)

[管理管理中心內的增益集](manage-addins-in-the-admin-center.md)

[對存放區中的增益集進行未成年人和取得](minors-and-acquiring-addins-from-the-store.md)
  
[使用集中式部署 PowerShell Cmdlet 來管理增益集](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[疑難排解：使用者未看到增益集](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
