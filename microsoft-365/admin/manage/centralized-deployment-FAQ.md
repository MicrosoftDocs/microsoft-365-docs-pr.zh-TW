---
title: 集中式部署常見問題
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
search.appverid:
- BCS160
- MET150
- MOE150
description: 從 Microsoft 365 系統管理中心，回顧有關集中式部署的常見問題解答。
ms.openlocfilehash: 39df2ec5a1671f800572bc845581bdbe2716d209
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43209661"
---
# <a name="centralized-deployment-faq"></a>集中式部署常見問題

集中式部署是 Office 365 系統管理員針對組織內的使用者和群組部署 Office 增益集（Word、Excel、PowerPoint 和 Outlook）的建議方法，前提是組織符合本文所述的使用集中式部署的所有需求。   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>如何知道我的組織是否已設定進行集中式部署？  

[！注意] 增益集的集中式部署需要使用者使用 Office 365 ProPlus （而且使用組織登入身分驗證登入 Office）和 Exchange Online 信箱。 您的訂閱目錄必須是在 Azure Active Directory 中或同盟至 Azure Active Directory。  
 
僅支援線上信箱的集中式部署。 它不支援部署至內部部署 Exchange 信箱。
 
您可以使用[Office 365 集中式部署相容性檢查](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker) 程式，判斷您的訂閱是否符合資格。 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>如何使用集中式部署來瞄準增益集使用者的指派？  

集中式部署支援對承租人中個別使用者、群組和所有人的工作分派。 集中式部署可用於最上層群組或沒有父項群組的群組中，但不適用於具有父項群組的嵌套群組或群組中的使用者。 集中式部署也是大多數 Azure Active Directory 群組的一部分，包括 Office 365 群組、通訊群組清單和安全性群組。  

最好是使用群組指派，而不是個別的使用者指派，以簡化管理。
 
如需詳細資訊，請參閱[使用者和群組指派](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments)。  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>增益集需要多長時間才能顯示給所有使用者？  

增益集最多可能需要24小時才能顯示所有使用者。 增益集更新、從開啟或關閉或增益集移除的變更所需的時間也相同。 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>身為系統管理員，如何管理使用者對組織增益集的存取權？

為了輕鬆將增益集部署至使用者、群組或整個組織，我們建議系統管理員使用集中式部署。

如需管理使用者存取的相關資訊，請參閱 </br>[關閉所有用戶端（Outlook 除外）的 Office Store，以避免增益集下載](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)。 </br>[指定可安裝和管理 Outlook 增益集的系統管理員和使用者](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN)。

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>集中式部署會為系統管理員提供彈性，以選擇 Outlook 增益集的部署方法？  

是。 集中式部署為系統管理員提供彈性，為增益集部署期間的 Outlook 增益集選擇三種部署方法之一：

**Fixed （預設值）**  增益集會自動部署至指派的使用者，且無法加以移除。  
 
**可用**使用者可以在 Outlook 中安裝增益集，方法是選擇 [首頁] > > 管理管理] 中取得更多增益集。   
 
**選用**增益集會自動部署至指派的使用者，但是可以選擇將它移除。  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>系統管理員可以更新企業營運（LOB）增益集嗎？  

是。 系統管理員可以上傳新的資訊清單檔案，以支援系統管理員部署的 LOB 增益集的中繼資料變更。增益集會在下次啟動 Office 應用程式時更新。 Web 應用程式可以隨時變更。  
 
如需詳細資訊，請參閱企業營運營運[增益集](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins)。  

## <a name="can-admins-turn-off-add-ins"></a>系統管理員是否可以關閉增益集？  

是。 系統管理員可以開啟或關閉其為所有使用者從 Microsoft 系統管理中心部署的增益集。

如需詳細資訊，請參閱[增益集狀態](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states)。  

##  <a name="can-admins-delete-or-remove-add-ins"></a>系統管理員可以刪除或移除增益集嗎？

是。 系統管理員可以從 Microsoft 系統管理中心刪除其為所有使用者部署的增益集。

如需詳細資訊，請參閱[刪除增益集](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in)。 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>使用集中式部署，系統管理員可以從 Office Store 部署付費增益集嗎？ 

否。 您目前無法使用集中式部署從 Office 存放區中部署付費增益集。  
 
我們建議您向外付費增益集的 ISV 開發人員要求資訊清單檔案或 URL。 然後，租使用者系統管理員可以使用集中式部署，將增益集部署為 LOB 增益集。
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>我需要哪些系統管理員角色來管理組織的增益集？  

您必須具有全域系統管理員角色，才能管理增益集。如果您是購買 Microsoft 365 for business 訂閱的人員，表示您是全域系統管理員。 
 
您的訂閱隨附一組系統管理員角色，您可以將其指派給組織中的其他使用者。 每個系統管理員角色會對應至常見商務功能，並讓您組織中的人員能夠在 Microsoft 365 系統管理中心中執行特定工作。  
 
如需詳細資訊，請參閱[指派系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide)。  