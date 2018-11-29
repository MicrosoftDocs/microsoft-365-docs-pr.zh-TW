---
title: 保護您的 Microsoft 365 Enterprise 的測試環境中的全域管理員帳戶
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
description: 使用下列步驟來保護 Microsoft 365 企業版測試環境中的全域管理員帳戶。
ms.openlocfilehash: 233e2178b060df4950c340e034d5f51216fac8fb
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866142"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>保護您的 Microsoft 365 Enterprise 的測試環境中的全域管理員帳戶

若要防止對貴組織的數位攻擊，您可以確保您的系統管理員帳戶會盡可能的安全。本文說明如何使用 Office 365 雲端應用程式安全性和 Azure AD 的設定格式化的條件存取原則來保護全域管理員帳戶。

有兩個階段來保護 Microsoft 365 企業版測試環境中的全域管理員帳戶：

1.  建立 Microsoft 365 企業版的測試環境。
2.  保護您專用的全域系統管理員帳戶。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 按一下[這裡](https://aka.ms/m365etlgstack) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。
  

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境

如果您只想要測試全域管理員帳戶保護的基本需求的輕量型方式，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要測試全域管理員帳戶保護模擬 enterprise 中，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。
  
> [!NOTE]
> 測試全域管理員帳戶保護不需要模擬的企業測試環境中，其中包含模擬內部網路連線至網際網路和 Windows Server AD 樹系目錄同步處理。它會提供這裡是做為選項可以測試全域管理員帳戶保護和代表的典型組織的環境中實驗。 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a>階段 2： 設定雲端應用程式安全性和設定格式化的條件存取原則

首先，建立 Office 365 雲端應用程式安全性原則監視全域管理員帳戶活動並將通知傳送給您的全域管理員帳戶的電子郵件地址。 

1. 登入 Office 365 入口網站[http://portal.office.com](http://portal.office.com)使用全域管理員帳戶。
2. 按一下 [**系統**] 磚。在 [ **Office 系統管理中心**] 索引標籤上按一下 [**系統中心 > 安全性與規範**。
3. 在左側的導覽窗格中，按一下 [**提醒 > 管理進階提醒**。
4. **進階提醒的管理**] 頁面上按一下 [**開啟 Office 365 雲端應用程式安全性**] 和 [**移至 Office 365 雲端應用程式安全性**。
5. 在 [新的**儀表板**] 索引標籤，按一下 [**控制項 > 原則**。
6. 在 [**原則**] 頁面上按一下 [**建立原則**] 和 [**活動原則**。
7. 在 [**原則名稱**輸入**系統管理的活動**。
8. 在**原則嚴重性**，按一下 [**高**]。
9. 在 [**類別**] 中，按一下 [**權限的帳戶**。
10. 在**建立篩選器原則**中**符合下列所有的活動**，按一下 [**系統管理的活動**。
11. 在**警告**中，按一下 [**傳送做為電子郵件通知**。在 [**至**] 輸入您的全域管理員帳戶的電子郵件地址。
12. 在頁面的底端，按一下 [**建立**]。
13. 關閉 [**儀表板**] 索引標籤。
    
下一步] 建立新的使用者帳戶為專用的全域管理員。

1. 在 [ **Office 系統管理中心**] 索引標籤上**作用中使用者**] 底下按一下 [**新增使用者**]。
2. 在 [**新增使用者**] 頁面上輸入**DedicatedAdmin**的**名字**、**顯示名稱**和**使用者名稱**。
3. 按一下 [**密碼**] 和 [**讓我建立密碼**，然後輸入 [強式密碼。安全的位置記錄此新帳戶的密碼。
4. 清除 [**讓此變更其密碼時第一次登入的使用者**。
5. 按一下 [**角色**]，然後按一下 [**全域管理員**。
6. 按一下 [**產品授權**，然後再開啟**企業行動性 + 安全性 E5**和**Office 365 企業版 E5 授權**。
7. 按一下 [新增]****。
8. 在**已新增使用者] 頁面上**，清除**傳送電子郵件中的密碼**，然後再按一下 [**關閉**]。

接下來，建立名為 GlobalAdmins 的新群組並將 DedicatedAdmin 帳戶新增至其。

1. 在**Office 系統管理中心**] 索引標籤按一下 [群組] 圖示的左方導覽，和 [**群組**。
2. 按一下 [**新增群組**]。
3. 在 [**新增群組**] 頁面上輸入**GlobalAdmins**。
4. 按一下 [**選取擁有者**按一下您的全域管理員帳戶] 和 [**新增 > 關閉**。
5. 在群組清單中，按一下 [ **GlobalAdmins**群組]。
6. 在**GlobalAdmins** ] 頁面上，按一下 [**編輯成員**] 及 [**新增成員**。
7. 在清單中，按一下 [ **DedicatedAdmin**帳戶] 和 [**儲存 > Close > Close > 系統管理中心**。

接下來，建立條件式存取原則以全域管理員帳戶需要多重要素驗證和拒絕驗證登入風險時中型或高。

此第一個原則要求所有全域管理員帳戶使用 MFA。

1. 在 [新增] 索引標籤的瀏覽器中移至[https://portal.azure.com](https://portal.azure.com)。
2. 按一下 [ **Azure Active Directory > 條件式存取**。
3. 在 [**設定格式化的條件存取 – 原則**blade 中，按一下 [**基準原則： 的系統管理員 （預覽） 需要 MFA**。
4. 在**基準原則...** blade 中，按一下 [**立即使用原則 > 儲存**。

此第二個原則封鎖存取權全域管理員帳戶驗證登入風險時中型或高。

1. 在**設定格式化的條件存取 – 原則**blade 中，按一下 [**新的原則**。
2. 在**新增**blade 中，輸入**全域管理員**的**名稱**。
3. 在 [**工作分派**] 區段中，按一下 [**使用者與群組**]。
4. 按一下 [**加入**] 索引標籤的**使用者和群組**blade**選取的使用者和群組 > 使用者和群組 > 選取**。
5. 在 [**選取**blade，按一下 [ **GlobalAdmins > 選取 > 完成**。
6. 在 [**工作分派**] 區段中，按一下 [**條件**]。
7. 上**條件**blade 中，按一下 [**登入風險**、 按一下 [**是]** 的**設定**、 [**高**] 和 [**中等**和 [**選取**並**完成**。
8. **新增**blade 的 [**存取控制**] 區段中的 [**授與**。
9. 在**授與**blade 中，按一下 [**封鎖存取**] 和 [**選取**。
10. 在**新增**blade、**啟用原則**，請按一下 [**** 然後再按一下 [**建立**。
11. 關閉 [ **Azure 入口網站**與**Office 系統管理中心**] 索引標籤。

若要測試的第一個原則，請登出並使用 DedicatedAdmin 帳戶登入。您應提示使用者帳戶上設定 MFA。這將示範如何套用的第一個原則。

請參閱 「 身分識別 」 階段的資訊及連結來保護您的全域管理員帳戶在生產環境中[保護全域管理員帳戶](identity-designate-protect-admin-accounts.md)的步驟。

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[階段 2：身分識別](identity-infrastructure.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)
