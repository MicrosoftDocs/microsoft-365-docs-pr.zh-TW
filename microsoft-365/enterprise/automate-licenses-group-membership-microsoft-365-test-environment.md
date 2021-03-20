---
title: 為您的 Microsoft 365 for enterprise 測試環境自動化授權和群組成員資格
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 在您的 Microsoft 365 for enterprise test 環境中，設定以群組為基礎的授權和動態群組成員資格。
ms.openlocfilehash: 26840e2884202a0fa9c4bb563f3d7c653482ef87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905365"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>為您的 Microsoft 365 for enterprise 測試環境自動化授權和群組成員資格

*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*

以群組為基礎的授權會根據群組成員資格，自動指派或移除使用者帳戶的授權。 動態群組成員資格會根據使用者帳戶屬性（例如 **部門** 或 **國家/地區**），新增或移除群組的成員。 本文將引導您逐步示範新增及移除 Microsoft 365 for enterprise test 環境中的群組成員。

在 Microsoft 365 企業版測試環境中設定自動授權和動態群組成員資格包括兩個階段：

- [階段1：組建您的 Microsoft 365 企業版測試環境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [階段2：設定及測試動態群組成員資格和自動授權](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>階段1：組建您的 Microsoft 365 企業版測試環境

如果您只想以輕量的方式測試自動授權和群組成員資格，請依照 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。
  
如果您想要在模擬的企業中測試自動授權和群組成員資格，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。
  
> [!NOTE]
> 測試自動授權和群組成員資格並不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。 它會以選項形式提供，以便您可以測試自動授權和群組成員資格，並在代表一般組織的環境中進行試驗。
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>階段2：設定及測試動態群組成員資格和自動授權

首先，建立名為 Sales 的新群組，並新增動態群組成員資格規則，讓與設定為「**銷售****部門**」的使用者帳戶自動加入 sales 群組。

1. 在網際網路瀏覽器的私人實例中，以 Microsoft 365 E5 測試實驗室訂閱的全域系統管理員帳戶登入 [microsoft 365 系統管理中心](https://admin.microsoft.com) 。
2. 在您瀏覽器的個別索引標籤上，移至 Azure 入口網站，網址為 [https://portal.azure.com](https://portal.azure.com) 。
3. 在 Azure 入口網站中，于搜尋方塊中輸入 **群組** ，然後選取 [ **群組**]。
4. 在 [ **所有群組** ] 窗格中，選取 [ **新增群組**]。
5. 在 [ **群組類型**] 中，選取 [ **Microsoft 365**]。
6. 在 [ **組名**] 中輸入 **Sales**。
7. 在 [ **成員資格類型**] 中，選取 [ **動態使用者**]。
8. 選取 [ **動態使用者成員**]。
9. 在 [ **動態成員資格規則** ] 窗格中： 
   - 選取 [ **部門** ] 屬性。
   - 選取 [ **等於** ] 運算子。
   - 在 [ **值** ] 方塊中，輸入 **Sales**。
10. 選取 [儲存]。
11. 選取 [建立]。

接下來，設定 Sales 群組，讓成員自動獲指派 Microsoft 365 E5 授權。

1. 選取 [ **銷售** ] 群組，然後選取 [ **授權**]。
2. 在 [ **更新授權指派** ] 窗格中，選取 [ **Microsoft 365 E5**]，然後選取 [ **儲存**]。
3. 在您的瀏覽器中，關閉 [Azure 入口網站] 索引標籤。

接下來，在使用者4帳戶上測試動態群組成員資格和自動授權：

1. 從瀏覽器的 [ **Microsoft Office 首頁** ] 索引標籤中，選取 [ **管理**]。
2. 從 [ **Microsoft 365 系統管理中心** ] 索引標籤中，選取 [作用中 **使用者**]。
3. 在 [作用中 **使用者** ] 頁面上，選取 [ **使用者 4** ] 帳戶。
4. 在 [**使用者 4** ] 窗格中，選取 [**產品授權**] 的 [**編輯**]。
5. 在 [**產品授權**] 窗格上，停用 **Microsoft 365 E5** 授權，然後選取 [**儲存**  >  **關閉**]。
6. 在 [使用者 4] 帳戶的內容中，確認未指派任何產品授權，而且沒有群組成員資格。
7. 如需 **聯繫資訊**，請選取 [ **編輯**]。
8. 在 [ **編輯連絡人資訊** ] 窗格中，選取 [ **連絡人資訊**]。
9. 在 [**部門**] 方塊中，輸入 **Sales**，然後選取 [**儲存**  >  **關閉**]。
10. 等候幾分鐘，然後定期選取 [使用者 4] [帳戶] 窗格右上角的 [重新整理 **] 圖示。**

及時，您應該會看到：

- 使用 **Sales** 群組更新的 **群組成員資格** 屬性。
- 使用 **Microsoft 365 E5** 授權更新的 **產品授權** 屬性。

請參閱下列文章，以在實際執行環境中部署動態群組成員資格和自動授權：

- [在 Azure Active Directory 中以群組為基礎的授權](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Azure Active Directory 中的動態群組](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[身分識別藍圖](identity-roadmap-microsoft-365.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[Microsoft 365 企業版文件](/microsoft-365-enterprise/)