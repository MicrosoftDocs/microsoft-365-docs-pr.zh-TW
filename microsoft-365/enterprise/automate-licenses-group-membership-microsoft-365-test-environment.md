---
title: 自動化 Microsoft 365 企業版測試環境的授權與群組成員資格
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: 在 Microsoft 365 企業版測試環境中設定群組型授權和動態群組成員資格。
ms.openlocfilehash: 45a78af202f2d9ab029683aae4d95ed9a3370b08
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866507"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>自動化 Microsoft 365 企業版測試環境的授權與群組成員資格

群組型自動授權指派或移除授權根據群組成員資格的使用者帳戶。動態群組成員資格新增或移除使用者帳戶屬性，例如部門或國家 （地區） 為基礎的群組成員。本文會引導您完成兩者 Microsoft 365 企業版測試環境中的示範。

有兩個階段來設定 Microsoft 365 企業版測試環境中的自動授權和動態群組成員資格：

1. 建立 Microsoft 365 企業版的測試環境。
2. 設定和測試動態群組成員資格與自動授權。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境

如果您只是要測試的基本需求的輕量型方式的自動授權與群組成員資格，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要測試模擬企業中的自動授權與群組成員資格，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。
  
> [!NOTE]
> 測試自動化授權和群組成員資格不需要模擬的企業測試環境中，其中包含連線至網際網路模擬內部網路和 Windows Server AD 樹系目錄同步處理。它會提供這裡是做為選項可以測試自動化授權和群組成員資格和代表的典型組織的環境中實驗。 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>階段 2： 設定和測試動態群組成員資格與自動授權

首先，您建立新的銷售群組並新增動態群組成員資格規則以便與設為銷售部門的使用者帳戶會自動新增至 [銷售] 群組。

1. 使用網際網路瀏覽器的私人執行個體，請登入 Office 入口網站[https://office.com](https://office.com)與您的 Office 365 E5 試用版訂閱的全域管理員帳戶。
2. 在瀏覽器中的個別] 索引標籤上移至 Azure 入口網站[https://portal.azure.com](https://portal.azure.com)。
3. 在 Azure 入口網站中，按一下 [Azure Active Directory] > [使用者和群組] > [所有群組]****。
4. 在**所有群組**blade 中，按一下 [**新群組**。
5. 在**群組類型**] 中選取 [ **Office 365**]。
6. 在 [**群組名稱**] 中，輸入 「**銷售額**」。
7. 在 [**成員資格類型**選取**動態的使用者**。
8. 按一下 [新增動態查詢]****。
9. 在 [新增使用者位置]****，請選取 [部門]****。
10. 在下一個欄位中，選取 [等於]****。
11. 在 [下一步] 欄位中輸入 「**銷售額**」。
12. 按一下 [新增查詢]****，然後按一下 [建立]****。
13. 關閉**群組**及**群組所有群組**刀。

接下來，設定 [銷售] 群組，讓成員會自動指派 Office 365 E5 和 Enterprise 行動性 + 安全性 E5 授權。

1. 在 Azure Active Directory**概觀 （英文)** blade，按一下 [**授權 > 所有產品**。
2. 在清單中，選取 [Enterprise Mobility + Security E5]**** 和 [Office 365 企業版 E5]****，然後按一下 [指派]****。
3. 在**指派授權給**blade，按一下 [**使用者與群組**]。
4. 在群組清單中，選取 [**銷售**] 群組。
5. 按一下 [選取]****，然後按一下 [指派]****。
6. 關閉瀏覽器的 Azure 入口網站索引標籤。

接下來，測試動態群組成員資格和使用者 4 帳戶上的自動授權。 

1. 從您的瀏覽器的 [ **Microsoft Office Home** ] 索引標籤按一下 [**管理**]。
2. 從**Office 系統管理中心**] 索引標籤上，按一下 [**作用中使用者**]。
3. 在 [**作用中使用者**] 頁面上，按一下 [**使用者 4**帳戶。
4. 在 [**使用者 4** ] 窗格中，按一下 [**編輯****產品**授權。
5. 在 [**產品授權**] 窗格中開啟**企業行動性 + 安全性 E5**和**Office 365 企業版 E5**授權 off、] 和 [**儲存 > 關閉**。
6. 在使用者 4 帳戶的屬性，確認已指派任何產品授權有無群組成員資格。
7. 按一下 [取得**連絡人資訊**的 [**編輯**]。
8. 在 [**編輯連絡人資訊**] 窗格中，按一下 [**連絡人資訊**。
9. 在 [**部門**] 欄位中輸入 [**銷售**] 和 [**儲存 > 關閉**。
10. 等候數分鐘和定期 [右上方的 [使用者 4 帳戶] 窗格中的 [重新整理] 圖示。 

您應該在時間中會看到：

- 更新 [**銷售**] 群組的**群組成員資格**屬性。
- 更新**企業行動性 + 安全性 E5**和**Office 365 企業版 E5**授權的**產品授權**屬性。

請參閱下列步驟中的 「 身分識別 」 階段的資訊及連結部署動態群組成員資格與在生產環境中的自動授權：

- [設定自動授權](identity-group-based-licensing.md)
- [設定動態群組成員資格](identity-automatic-group-membership.md)

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[階段 2：身分識別](identity-infrastructure.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)
