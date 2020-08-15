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
ms.openlocfilehash: a25a47b81ce8c119e7aeb44660af32bb9cafb08a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685555"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>為您的 Microsoft 365 for enterprise 測試環境自動化授權和群組成員資格

*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*

以群組為基礎的授權會根據群組成員資格，自動指派或移除使用者帳戶的授權。 動態群組成員資格會根據使用者帳戶屬性（例如部門或國家/地區），新增或移除群組的成員。 本文會逐步引導您在 Microsoft 365 的企業版測試環境中示範。

在 Microsoft 365 企業版測試環境中設定自動授權和動態群組成員資格有兩個階段：

1. 建立適用于企業測試環境的 Microsoft 365。
2. 設定及測試動態群組成員資格和自動授權。

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，可查看企業用 Microsoft 365 測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>階段1：組建您的 Microsoft 365 企業版測試環境

如果您只想以輕量的方式測試自動授權和群組成員資格，請依照 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。
  
如果您想要在模擬的企業中測試自動授權和群組成員資格，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。
  
> [!NOTE]
> 測試自動授權和群組成員資格並不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。 這裡是以選項形式提供，可讓您測試自動授權和群組成員資格，並在代表一般組織的環境中實驗。 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>階段2：設定及測試動態群組成員資格和自動授權

首先，您會建立新的銷售群組，並新增動態群組成員資格規則，使設定為「銷售部門」的使用者帳戶會自動新增至 Sales 群組。

1. 使用網際網路瀏覽器的私人實例，使用您的 Microsoft 365 E5 測試實驗室訂閱的全域系統管理員帳戶登入 [microsoft 365 系統管理中心](https://admin.microsoft.com) 。
2. 在您瀏覽器的個別索引標籤上，移至 Azure 入口網站，網址為 [https://portal.azure.com](https://portal.azure.com) 。
3. 在 Azure 入口網站的搜尋方塊中輸入 [ **群組** ]，然後按一下 [ **群組**]。
4. 在 [ **所有群組** ] 窗格中，按一下 [ **新增群組**]。
5. 在 [ **群組類型**] 中，選取 [ **Microsoft 365**]。
6. 在 [ **組名**] 中輸入 **Sales**。
7. 在 [ **成員資格類型**] 中，選取 [ **動態使用者**]。
8. 按一下 [ **動態使用者成員**]。
9. 在 [ **動態成員資格規則** ] 窗格中： 
   - 選取 [ **部門** ] 屬性。
   - 選取 [ **等於** ] 運算子。
   - 在**值**中輸入**Sales** 。
10. 按一下 **[儲存]**。
11. 按一下 [建立]****。

接下來，您要設定 Sales 群組，讓成員自動獲指派 Microsoft 365 E5 授權。

1. 按一下 [ **Sales** ] 群組，然後按一下 [ **授權**]。
2. 在 [ **更新授權指派** ] 窗格中，選取 [ **Microsoft 365 E5**]，然後按一下 [ **儲存**]。
3. 關閉瀏覽器的 Azure 入口網站索引標籤。

接下來，在使用者4帳戶上測試動態群組成員資格和自動授權。 

1. 從瀏覽器的 [ **Microsoft Office 首頁** ] 索引標籤中，按一下 [ **管理**]。
2. 在 [ **Microsoft 365 系統管理中心** ] 索引標籤上，按一下 [作用中 **使用者**]。
3. 在 [作用中 **使用者** ] 頁面上，按一下 [ **使用者 4** ] 帳戶。
4. 在 [**使用者 4** ] 窗格上，按一下 [**產品授權**] 的 [**編輯**]。
5. 在 [ **產品授權** ] 窗格上，停用 **Microsoft 365 E5** 授權，然後按一下 [ **儲存 > 關閉**]。
6. 在 [使用者 4] 帳戶的內容中，確認未指派任何產品授權，而且沒有群組成員資格。
7. 按一下 [ **編輯** 以取得 **連絡人資訊**]。
8. 在 [ **編輯連絡人資訊** ] 窗格中，按一下 [ **連絡人資訊**]。
9. 在 [ **部門** ] 欄位中，輸入 **Sales**，然後按一下 [ **儲存 > 關閉**]。
10. 等候幾分鐘，然後定期按一下 [使用者 4] [帳戶] 窗格右上角的 [重新整理] 圖示。 

您應該會看到下列專案：

- 使用**Sales**群組更新的**群組成員資格**屬性。
- 使用**Microsoft 365 E5**授權更新的**產品授權**屬性。

請參閱下列文章，以在實際執行環境中部署動態群組成員資格和自動授權：

- 連結 TBD
- 連結 TBD

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[身分識別藍圖](identity-roadmap-microsoft-365.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[適用于企業的 Microsoft 365 檔](https://docs.microsoft.com/microsoft-365-enterprise/)
