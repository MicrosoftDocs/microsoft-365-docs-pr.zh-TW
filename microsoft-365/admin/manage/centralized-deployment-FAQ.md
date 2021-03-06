---
title: 集中式部署常見問題集
f1.keywords:
- NOCSH
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
description: 從 Microsoft 365 系統管理中心中查看有關集中式部署的常見問題解答。
ms.openlocfilehash: 0da9ec9595fd433abe1e2e2ae3f2e3a0c6b3b9b5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228001"
---
# <a name="centralized-deployment-faq"></a>集中式部署常見問題集

集中式部署是 Office 365 系統管理員針對組織內的使用者和群組部署 Office 載入 PowerPoint Excel (宏的建議方法，只要組織符合本文所述的所有使用集中式部署的需求。   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>如何知道我的組織是否已設定進行集中式部署？  

[！注意] 增益集的集中式部署需要使用者使用 Microsoft 365 Apps 企業版 (，並使用其組織登入身分憑證登入 Office) 且具有 Exchange Online 信箱。 您的訂閱目錄必須是 in 或同盟 to Azure Active Directory。  
 
僅支援線上信箱的集中式部署。 它不支援部署至內部部署 Exchange 信箱。

您可以使用[集中式部署相容性檢查](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)程式   ，判斷您的訂閱是否符合資格。 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>如何使用集中式部署來瞄準增益集使用者的指派？  

集中式部署支援對承租人中個別使用者、群組和所有人的工作分派。 集中式部署可用於最上層群組或沒有父項群組的群組中，但不適用於具有父項群組的嵌套群組或群組中的使用者。 集中式部署也是大部分 Azure Active Directory 群組的一部分，包括 Office 365 群組、通訊群組清單和安全性群組。  

最好是使用群組指派，而不是個別的使用者指派，以簡化管理。
 
如需詳細資訊，請參閱 [使用者和群組指派](./centralized-deployment-of-add-ins.md#user-and-group-assignments)。  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>增益集需要多長時間才能顯示給所有使用者？  

增益集最多可能需要24小時才能顯示所有使用者。 增益集更新、從開啟或關閉或增益集移除的變更所需的時間也相同。 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>身為系統管理員，如何管理使用者對組織增益集的存取權？

為了輕鬆將增益集部署至使用者、群組或整個組織，我們建議系統管理員使用集中式部署。

如需管理使用者存取的相關資訊，請參閱：
 - [在所有用戶端上關閉 Office 儲存區，以避免增益集下載 (但 Outlook) ](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [指定可安裝和管理適用於 Outlook 增益集的系統管理員和使用者](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>集中式部署是否可讓系統管理員靈活地選擇 Outlook 增益集的部署方法？  

是。 集中式部署可讓系統管理員靈活地選擇三種部署方法的其中一種，以在增益集部署期間 Outlook 增益集：

**固定 (預設)**  增益集會自動部署至指派的使用者，且無法加以移除。  
 
**可用** 使用者可以在 Outlook 中安裝增益集，方法是選擇 [**首頁] > 取得更多增益集 > 系統管理員管理**。
 
**選用** 增益集會自動部署至指派的使用者，但是可以選擇將它移除。  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>系統管理員是否可以更新企業營運 (LOB) 增益集？  

是。 系統管理員可以上傳新的資訊清單檔案，以支援系統管理員部署的 LOB 增益集的中繼資料變更。增益集會在下次 Office 應用程式啟動時更新。 Web 應用程式可以隨時變更。  
 
如需詳細資訊，請參閱企業營運營運 [增益集](./manage-addins-in-the-admin-center.md)。  

## <a name="can-admins-turn-off-add-ins"></a>系統管理員是否可以關閉增益集？  

是。 系統管理員可以開啟或關閉其為所有使用者從 Microsoft 系統管理中心部署的增益集。

如需詳細資訊，請參閱 [增益集狀態](./manage-addins-in-the-admin-center.md#add-in-states)。  

##  <a name="can-admins-delete-or-remove-add-ins"></a>系統管理員可以刪除或移除增益集嗎？

是。 系統管理員可以從 Microsoft 系統管理中心刪除其為所有使用者部署的增益集。

如需詳細資訊，請參閱 [刪除增益集](./manage-addins-in-the-admin-center.md#delete-an-add-in)。 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>使用集中式部署，系統管理員可以從 Office 存放區中部署付費增益集嗎？ 

否。 您目前無法使用集中式部署，從 Office 儲存區中部署付費增益集。  
 
我們建議您向外付費增益集的 ISV 開發人員要求資訊清單檔案或 URL。 然後，租使用者系統管理員可以使用集中式部署，將增益集部署為 LOB 增益集。
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>我需要哪些系統管理員角色來管理組織的增益集？  

全域管理員是推薦的角色，具有增益集管理生命週期的完整存取權。 如果您是購買 Microsoft 365 商務版訂閱的人員，您就是全域系統管理員。 
 
您的訂閱隨附一組系統管理員角色，您可以將其指派給組織中的其他使用者。 每個系統管理員角色會對應至常見商務職能，並提供組織中的人員執行 Microsoft 365 系統管理中心中的特定工作。  
 
如需詳細資訊，請參閱 [指派系統管理員角色](../add-users/assign-admin-roles.md)。 
