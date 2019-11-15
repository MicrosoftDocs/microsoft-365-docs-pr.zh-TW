---
title: 保護您的 Microsoft 365 企業版測試環境中的全域系統管理員帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 使用下列步驟來保護 Microsoft 365 企業版測試環境中的全域系統管理員帳戶。
ms.openlocfilehash: c7ee5bca3f5841ac7751e497ca88391daf965301
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640355"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>保護您的 Microsoft 365 企業版測試環境中的全域系統管理員帳戶

您可以防止數位攻擊您的組織藉由確保您的系統管理員帳戶會盡可能的安全。 本文說明如何使用 Azure Active Directory (Azure AD) 條件式存取原則來保護全域系統管理員帳戶。

有兩個階段，以保護您的 Microsoft 365 企業版測試環境中的全域系統管理員帳戶：

1.  建立 Microsoft 365 企業版測試環境。
2.  保護您專用的全域系統管理員帳戶。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1：建置您的 Microsoft 365 企業版測試環境

如果您只想以具有最小需求的輕量型方式測試全域系統管理員帳戶保護，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要在模擬的企業中測試全域系統管理員帳戶保護，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。

  
> [!NOTE]
> 測試保護不需要模擬的企業測試環境，其中包含的模擬內部網路的全域系統管理員帳戶連線至網際網路和 Active Directory 網域服務 (AD DS) 的目錄同步處理。 它提供了此選項，讓您可以測試全域系統管理員帳戶保護與代表典型組織的環境中實驗。 
  
## <a name="phase-2-configure-conditional-access-policies"></a>階段 2： 設定條件式存取原則

首先，建立新的使用者帳戶為專用的全域系統管理員。

1. 個別索引標籤上，開啟[Microsoft 365 系統管理中心](https://admin.microsoft.com/)。
2. [**作用中使用者**] 下方按一下 [**新增使用者**]。
3. 在 [**新增使用者**] 頁面上，輸入**DedicatedAdmin**中**第一個名稱**、**顯示名稱**和**使用者名稱**。
4. 按一下 [**密碼**] 和 [**讓我建立密碼**，然後輸入 [強式密碼。 此新帳戶的密碼記錄於安全的位置。
5. 清除 [**讓這位使用者變更其密碼，當使用者第一次登入**。
6. 按一下 [**角色**]，然後按一下 [**全域系統管理員**。
7. 按一下 [**產品授權**]，然後再開啟的 [ **Enterprise Mobility + Security E5** ] 和 [ **Office 365 企業版 E5 授權**。
8. 按一下 [新增]****。
9. 在**已新增使用者] 頁面上**，清除 [**傳送電子郵件中的密碼**，，然後再按一下 [**關閉**。

接下來，建立名為 GlobalAdmins 的新群組，並將 DedicatedAdmin 帳戶新增至它。

1. 在**Microsoft 365 系統管理中心**] 索引標籤上，按一下左側導覽中，在 [群組] 圖示，然後按一下**群組**。
2. 按一下 [**新增群組**。
3. 在 [**新增群組**] 頁面上，輸入**GlobalAdmins**。
4. 全域管理員帳戶，按一下 [**選取擁有者**按一下，然後按一下 [**新增 > 關閉**。
5. 在群組清單中，按一下 [ **GlobalAdmins**群組]。
6. 在**GlobalAdmins**頁面上，按一下 [**編輯成員**]，然後按一下 [**新增成員**。
7. 在清單中，按一下 [ **DedicatedAdmin**帳戶]，然後按一下 [**儲存 > Close > Close > 系統管理中心**。

接下來，建立需要的全域系統管理員帳戶的多重要素驗證，並拒絕驗證登入風險中或高時的條件式存取原則。

此第一個原則需要所有的全域系統管理員帳戶使用 MFA。

1. 在瀏覽器的新索引標籤，移至 [ [https://portal.azure.com](https://portal.azure.com)。
2. 按一下 [ **Azure Active Directory > 條件式存取**]。
3. 在 [**條件式存取 – 原則**] 刀鋒視窗中，按一下 [**基準線原則： 系統管理員 （預覽） 需要 MFA**。
4. **[比較基準原則...** ] 刀鋒視窗上，按一下 [**立即 > 儲存使用原則**。

以全域系統管理員帳戶驗證登入風險中或高時此第二個原則封鎖存取。

1. 在 [**條件式存取 – 原則**] 刀鋒視窗中，按一下 [**新增原則**]。
2. 在 [**新增**] 刀鋒視窗中，輸入**全域系統管理員**在 [**名稱]**。
3. 在 [**指派**] 區段中，按一下 [**使用者和群組**。
4. 在 [**使用者和群組**] 刀鋒視窗的 [**包含**] 索引標籤中，按一下 [**選取使用者及群組 > 使用者和群組 > 選取**。
5. 在 [**選取**] 刀鋒視窗上，按一下 [ **GlobalAdmins > 選取 > 完成**]。
6. 在 [**指派**] 區段中，按一下 [**條件**]。
7. 在 [**條件**] 刀鋒視窗中，按一下 [**登入風險**、 按一下 [**是]** 的**設定**、 按一下 [**高**] 和 [**媒體**，然後按一下**選取**並**完成**。
8. 在 [**新增**] 刀鋒視窗中的 [**存取控制**] 區段中，按一下 [**授與**]。
9. 在 [**授與**] 刀鋒視窗中，按一下 [**封鎖存取**]，然後按一下 [**選取**。
10. 在 [**新增**] 刀鋒視窗上**啟用原則**，請按一下 [ **** ，然後按一下 [**建立**。
11. 關閉 [ **Azure 入口網站**和**Microsoft 365 系統管理中心**] 索引標籤。

若要測試的第一個原則，請登出，並使用 DedicatedAdmin 帳戶登入。 應該會提示您的使用者帳戶上設定 MFA。 此示範，將第一個會被套用原則。

在身分識別階段中的資訊，以及保護您的全域系統管理員帳戶，在生產環境中的連結，請參閱[保護全域系統管理員帳戶](identity-create-protect-global-admins.md#identity-global-admin)的步驟。

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[階段 2：身分識別](identity-infrastructure.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)
