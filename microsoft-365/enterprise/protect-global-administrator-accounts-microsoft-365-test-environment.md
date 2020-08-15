---
title: 在 Microsoft 365 for enterprise test 環境中保護全域系統管理員帳戶
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 使用這些步驟來保護您的 Microsoft 365 企業版測試環境中的全域系統管理員帳戶。
ms.openlocfilehash: fff09ca41ff0b648d46b5c33f753affc01242264
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695179"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>在 Microsoft 365 for enterprise test 環境中保護全域系統管理員帳戶

*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*

您可以確保您的系統管理員帳戶盡可能安全，以防止組織的數位攻擊。 本文說明如何使用 Azure Active Directory (Azure AD) 條件式存取原則來保護全域系統管理員帳戶。

在 Microsoft 365 企業版測試環境中，保護全域系統管理員帳戶有兩個階段：

1.  建立適用于企業測試環境的 Microsoft 365。
2.  保護您的專屬全域管理員帳戶。

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，可查看企業用 Microsoft 365 測試實驗室指南堆疊中所有文章的視覺對應。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>階段1：組建您的 Microsoft 365 企業版測試環境

如果您只想以輕量的方式測試全域管理員帳戶保護，請依照 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。
  
如果您想要在模擬的企業中測試全域管理員帳戶保護，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。
  
> [!NOTE]
> 測試全域管理員帳戶保護並不需要模擬的企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 的目錄同步處理。 這裡是以選項形式提供，可讓您測試全域管理員帳戶保護，並在代表一般組織的環境中進行試驗。 
  
## <a name="phase-2-configure-conditional-access-policies"></a>階段2：設定條件式存取原則

首先，建立新的使用者帳戶做為專屬全域管理員。

1. 在個別的索引標籤上，開啟 [ [Microsoft 365 系統管理中心](https://admin.microsoft.com/)]。
2. 按一下 [ **使用者 > Active 使用者**]，然後按一下 [ **新增使用者**]。
3. 在 [**新增使用者**] 窗格中，在 **[名字**]、[**顯示名稱**] 和 [使用者**名稱]** 中輸入**DedicatedAdmin** 。
4. 按一下 [ **密碼**]，然後按一下 **[讓我建立密碼**]，然後輸入強式密碼。 在安全的位置記錄此新帳戶的密碼。
5. 按 [下一步]****。
6. 在 [ **指派產品授權** ] 窗格中，選取 [ **Microsoft 365 E5**]，然後按 **[下一步]**。
7. 在 [ **選用的設定** ] 窗格中，按一下 [ **角色**]，然後選取 [管理中心] [ **存取** 和 **全域管理員**]。按 **[下一步]**。
8. 在 [ **即將完成** ] 窗格中，按一下 **[完成新增**]，然後按一下 [ **關閉**]。

接下來，建立名為 GlobalAdmins 的新群組，並將 DedicatedAdmin 帳戶新增至該群組。

1. 在 [ **Microsoft 365 系統管理中心** ] 索引標籤上，按一下左側導覽窗格中的 [ **群組** ]，然後按一下 [ **群組**]。
2. 按一下 [ **新增群組**]。
3. 在 [ **選擇群組類型** ] 窗格中，選取 [ **安全性**]，然後按 **[下一步]**。
4. 在 [ **設定基礎** ] 窗格中，按一下 [ **建立群組**]，然後按一下 [ **關閉**]。
5. 在 [ **複查並完成新增群組** ] 窗格中，輸入 **GlobalAdmins**，然後按 **[下一步]**。
7. 在群組清單中，按一下 [ **GlobalAdmins** ] 群組。
8. 在 [ **GlobalAdmins** ] 窗格中，按一下 [ **成員**]，然後按一下 [ **全部查看] 和 [管理成員**]。
9. 在 [ **GlobalAdmins** ] 窗格中，按一下 [ **新增成員**]，選取 **DedicatedAdmin** 帳戶和全域系統管理員帳戶，然後按一下 [ **儲存] > 關閉 > 關閉**]。

接下來，建立條件式存取原則以要求全域管理員帳戶的多重要素驗證，以及在登入風險為中低或高時拒絕驗證。

此第一個原則要求所有全域管理員帳戶都使用 MFA。

1. 在瀏覽器的新索引標籤上，移至 [https://portal.azure.com](https://portal.azure.com) 。
2. 按一下 [ **Azure Active Directory > Security > 條件式存取**]。
3. 在 [ **條件式存取-原則** ] 窗格中，按一下 [ **基準原則：需要 MFA 進行系統管理員 (預覽]) **。
4. 在 [ **基線原則** ] 窗格中，按一下 [ **立即使用原則 > 儲存**]。

第二個原則會封鎖存取全域管理員帳戶時，當登入風險為「中」或「高」時。

1. 在 [ **條件式存取-原則** ] 窗格中，按一下 [ **新增原則**]。
2. 在 [**新增**] 窗格中，輸入 [**名稱**] 中的 [**全域管理員**]。
3. 在 [ **工作分派** ] 區段中，按一下 [ **使用者和群組**]。
4. 在 [**使用者和群組**] 窗格的 [**包含**] 索引標籤上，按一下 [**選取使用者和群組 > 使用者和群組] > 選取**]。
5. 在 [ **選取** ] 窗格中，按一下 [ **GlobalAdmins** ] 群組，然後按一下 [ **選取 > 完成**]。
6. 在 [ **工作分派** ] 區段中，按一下 [ **條件**]。
7. 在 [**條件**] 窗格中，按一下 [登**入風險**]，針對 [**設定** **] 按一下 [是]** ，按一下 [**高**] 和 [**中**]，然後按一下 [**選取**並**完成**]。
8. 在 [**新增**] 窗格的 [**存取控制**] 區段中，按一下 **[授**與]。
9. 在 [ **授** 與] 窗格中，按一下 [ **封鎖存取**]，然後按一下 [ **選取**]。
10. 在 [**新增**] 窗格中，按一下 [**啟用原則**] 的 [**開啟**]，然後按一下 [**建立**]。
11. 關閉 [ **Azure 入口網站** ] 和 [ **Microsoft 365 管理中心** ] 索引標籤。

若要測試第一個原則，請以 DedicatedAdmin 帳戶登出並登入。 您應該會收到設定 MFA 的提示。 這會示範正在套用第一個原則。

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[身分識別藍圖](identity-roadmap-microsoft-365.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[適用于企業的 Microsoft 365 檔](https://docs.microsoft.com/microsoft-365-enterprise/)
