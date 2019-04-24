---
title: 自動化適用於 Microsoft 365 企業版測試環境的授權和群組成員資格
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 企業版測試環境中設定群組為基礎的授權和動態群組成員資格。
ms.openlocfilehash: 8ced249ee56e15c057001af60d790a8a4315dd17
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277237"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>自動化適用於 Microsoft 365 企業版測試環境的授權和群組成員資格

群組為基礎的授權會自動指派或移除根據群組成員資格的使用者帳戶的授權。 動態群組成員資格新增或移除使用者帳戶內容，例如部門或國家/地區為基礎的群組成員。 本文會引導您完成 Microsoft 365 企業版測試環境中這兩者的示範。

有兩個主要階段設定 Microsoft 365 企業版測試環境中的自動授權和動態群組成員資格：

1. 建立 Microsoft 365 企業版測試環境。
2. 設定並測試動態群組成員資格和自動授權。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1： 建置 Microsoft 365 企業版測試環境

如果您只想以具有最小需求的輕量型方式測試自動授權和群組成員資格，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要在模擬的企業中測試自動授權和群組成員資格，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。
  
> [!NOTE]
> 測試自動授權和群組成員資格不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理 Active Directory 網域服務 (AD DS) 樹系中。 它提供了此選項，讓您可以測試自動授權和群組成員資格與代表典型組織的環境中實驗。 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>階段 2： 設定並測試動態群組成員資格和自動授權

首先，您建立新的 「 業務 」 群組，並新增動態群組成員資格規則，以便與設定為銷售部門的使用者帳戶會自動新增至 「 業務 」 群組。

1. 使用網際網路瀏覽器的私用執行個體，登入 Office 入口網站，網址[https://office.com](https://office.com)與 Office 365 E5 試用版訂閱的全域系統管理員帳戶。
2. 在瀏覽器的個別索引標籤，移至 Azure 入口網站，網址[https://portal.azure.com](https://portal.azure.com)。
3. 在 Azure 入口網站中，按一下 [Azure Active Directory] > [使用者和群組] > [所有群組]****。
4. 在 [**所有群組**] 刀鋒視窗中，按一下 [**新的群組**。
5. 在 [**群組類型**] 中，選取 [ **Office 365**]。
6. 在 [**群組名稱**] 中，輸入 「**銷售額**」。
7. 在 [**成員資格類型**] 中，選取 [**動態使用者**]。
8. 按一下 [新增動態查詢]****。
9. 在 [新增使用者位置]****，請選取 [部門]****。
10. 在下一個欄位中，選取 [等於]****。
11. 在 [下一步] 欄位中，輸入 「**銷售額**」。
12. 按一下 [新增查詢]****，然後按一下 [建立]****。
13. 關閉**群組**和**群組-所有群組**刀。

接下來，您設定 「 業務 」 群組，以便成員自動獲指派 Office 365 E5 與 Enterprise Mobility + Security E5 授權。

1. 在 Azure Active directory [**概觀**] 刀鋒視窗中，按一下 [**授權 > 所有產品**]。
2. 在清單中，選取 [Enterprise Mobility + Security E5]**** 和 [Office 365 企業版 E5]****，然後按一下 [指派]****。
3. 在 [**指派授權**] 刀鋒視窗中，按一下 [**使用者和群組**。
4. 在 [群組] 清單中選取 [**銷售**] 群組。
5. 按一下 [選取]****，然後按一下 [指派]****。
6. 關閉瀏覽器的 Azure 入口網站索引標籤。

接下來，您測試動態群組成員資格及使用者 4 帳戶上的自動授權。 

1. 從瀏覽器的 [ **Microsoft Office 的首頁**] 索引標籤按一下 [**系統**]。
2. 從**Microsoft 365 系統管理中心**] 索引標籤上，按一下 [**作用中使用者**]。
3. 在 [**作用中使用者**] 頁面上，按一下 [**使用者 4**帳戶。
4. 在 [**使用者 4** ] 窗格中，按一下 [**編輯****產品**授權。
5. 在 [**產品授權**] 窗格中，關閉**Enterprise Mobility + Security E5** ] 和 [ **Office 365 企業版 E5**授權，，然後按一下 [**儲存 > 關閉**。
6. 在 [使用者 4 帳戶的內容，請確認已指派任何產品授權，且沒有任何群組的成員資格。
7. **連絡人資訊**，按一下 [**編輯**]。
8. 在 [**編輯連絡人資訊**] 窗格中，按一下 [**連絡人資訊**]。
9. 在 [**部門**] 欄位中，輸入**銷售**]，然後按一下 [**儲存 > 關閉**。
10. 請稍候幾分鐘，然後定期按一下右上角的 [使用者 4 的帳戶] 窗格中的重新整理圖示。 

在時間應該會看到:

- 更新 「**業務**」 群組的**群組成員資格**屬性。
- 以**Enterprise Mobility + Security E5** ] 和 [ **Office 365 企業版 E5**授權更新的**產品授權**屬性。

在身分識別階段中的資訊，以及部署動態群組成員資格和自動授權在生產環境中的連結，請參閱下列步驟：

- [設定自動授權](identity-self-service-group-management.md#identity-group-license)
- [設定動態群組成員資格](identity-self-service-group-management.md#identity-dyn-groups)

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[階段 2：身分識別](identity-infrastructure.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)
