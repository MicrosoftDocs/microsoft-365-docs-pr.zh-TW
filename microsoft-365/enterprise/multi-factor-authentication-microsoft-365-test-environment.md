---
title: Microsoft 365 for enterprise test 環境多重要素驗證
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
- seo-marvel-apr2020
description: 使用 Microsoft 365 for enterprise test 環境中傳送至 smart phone 的文字訊息，設定多重要素驗證。
ms.openlocfilehash: 4ed50d37e0f4e73d5d1fc62e295df374c61b9786
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686271"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>適用于 Microsoft 365 企業版測試環境的多重要素驗證

*此測試實驗室指南可用於 enterprise 和 Office 365 企業測試環境的 Microsoft 365。*

若要取得其他安全性，以供登入 Microsoft 365 或任何服務或應用程式使用您訂閱的 Azure AD 租使用者，您可以啟用 Azure 多重要素驗證，它只需要使用者名稱和密碼，即可驗證帳戶。 

使用多重要素驗證時，使用者必須認可電話、輸入短信中所傳送的驗證碼，或在正確輸入密碼後，使用智慧型電話上的應用程式驗證驗證。 只有在滿足這個第二次驗證要素之後，他們才可以登入。 
  
本文說明如何為特定使用者帳戶啟用並測試以郵件為基礎的驗證。
  
針對企業測試環境365中的帳戶設定多重要素驗證有兩個階段：
  
1. 建立適用于企業測試環境的 Microsoft 365。
    
2. 為使用者2帳戶啟用並測試多重要素驗證。

3. 使用條件式存取原則 (選用) ，啟用並測試多重要素驗證。

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 請移至 [測試實驗室指南堆疊](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) ，以查看 Microsoft 365 For Enterprise 測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>階段1：組建您的 Microsoft 365 企業版測試環境

如果您只想以輕量的方式測試多重要素驗證，請依照 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。
  
如果您想要在模擬的企業中測試多重要素驗證，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。
  
> [!NOTE]
> 測試多重要素驗證並不需要模擬的企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。 這裡是以選項形式提供，可讓您測試多重要素驗證，並在代表一般組織的環境中進行嘗試。 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>階段2：針對使用者2帳戶啟用並測試多重要素驗證

使用下列步驟為使用者2帳戶啟用多重要素驗證：
  
1. 開啟瀏覽器的個別私人實例，移至 Microsoft 365 管理中心 ([https://portal.microsoft.com](https://portal.microsoft.com)) ，然後使用全域系統管理員帳戶登入。
    
2. 在左方的瀏覽區域中，按一下 [使用者] > [作用中的使用者]****。
    
3. 在 [作用中的使用者] 窗格中，按一下 [ **多重要素驗證**]。
    
4. 在清單中，選取 [ **使用者 2** ] 帳戶。
    
5. 在 [ **使用者 2** ] 區段的 [ **快速步驟**] 下方，按一下 [ **啟用**]。
    
6. 在 [ **相關啟用多重要素驗證** ] 對話方塊中，按一下 [ **啟用多重要素驗證**]。
    
7. 在 [ **更新成功** ] 對話方塊中，按一下 [ **關閉**]。
    
8. 在 [ **Microsoft 365 系統管理中心**] 索引標籤上，按一下右上方的使用者帳戶圖示，然後按一下 **[登出]。**
    
9. 關閉瀏覽器實例。
   
完成「使用者2」帳戶的設定，以使用文字訊息進行驗證，並使用下列步驟進行測試：
  
1. 開啟瀏覽器的新的私人實例。
    
2. 請移至 [Microsoft 365 系統管理中心](https://admin.microsoft.com) ，並使用使用者2帳戶名稱和密碼登入。
    
3. 登入後，系統會提示您設定帳戶以取得詳細資訊。 按 [下一步]****。
    
4. 在 [ **其他安全性驗證** ] 頁面上：
    
   - 選取您的國家或地區。
    
   - 輸入將接收文字訊息之智慧型電話的電話號碼。
    
   - 在 **方法**中，按一下 [以 **文字訊息傳送程式碼**]。
    
5. 按 [下一步]****。
    
6. 從 smart phone 上收到的文字訊息中輸入驗證碼，然後按一下 [ **驗證**]。
    
7. 在 [ **步驟3：保留現有的應用程式** ] 頁面上，按一下 [ **完成**]。
    
8. 如果這是您第一次使用使用者2帳戶登入，系統會提示您變更密碼。 輸入原始密碼和新密碼兩次，然後按一下 [ **更新密碼並登入**]。 將新密碼記錄在安全的位置。
    
    您應該會在瀏覽器的 [ **Microsoft Office 首頁** ] 索引標籤上，看到使用者2的 Office 入口網站。

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>階段3：使用條件式存取原則來啟用及測試多重要素驗證

*此階段僅可用於適用于企業測試環境的 Microsoft 365。*

在此階段中，您會使用群組和條件式存取原則，為使用者3帳戶啟用多重要素驗證。

接下來，建立名為 MFAUsers 的新群組，並將使用者3帳戶新增至該群組。

1. 在 [ **Microsoft 365 系統管理中心** ] 索引標籤上，按一下左側導覽窗格中的 [ **群組** ]，然後按一下 [ **群組**]。
2. 按一下 [ **新增群組**]。
3. 在 [ **選擇群組類型** ] 窗格中，選取 [ **安全性**]，然後按 **[下一步]**。
4. 在 [ **設定基礎** ] 窗格中，按一下 [ **建立群組**]，然後按一下 [ **關閉**]。
5. 在 [ **複查並完成新增群組** ] 窗格中，輸入 **MFAUsers**，然後按 **[下一步]**。
6. 在群組清單中，按一下 [ **MFAUsers** ] 群組。
7. 在 [ **MFAUsers** ] 窗格中，按一下 [ **成員**]，然後按一下 [ **全部查看] 和 [管理成員**]。
8. 在 [ **MFAUsers** ] 窗格中，按一下 [ **新增成員**]，選取 [ **使用者 3** ] 帳戶，然後按一下 [ **儲存] > 關閉 > 關閉**]。

接下來，建立條件式存取原則，以要求 MFAUsers 群組成員的多重要素驗證。

1. 在瀏覽器的新索引標籤上，移至 [https://portal.azure.com](https://portal.azure.com) 。
2. 按一下 [ **Azure Active Directory > Security > 條件式存取**]。
3. 在 [ **條件式存取-原則** ] 窗格中，按一下 [ **新增原則**]。
4. 在 [**新增**] 窗格中，為 [**名稱**] 中的**使用者帳戶輸入 MFA** 。
5. 在 [ **工作分派** ] 區段中，按一下 [ **使用者和群組**]。
6. 在 [**使用者和群組**] 窗格的 [**包含**] 索引標籤上，按一下 [**選取使用者和群組 > 使用者和群組] > 選取**]。
7. 在 [ **選取** ] 窗格中，按一下 [ **MFAUsers** ] 群組，然後按一下 [ **選取 > 完成**]。
8. 在 [**新增**] 窗格的 [**存取控制**] 區段中，按一下 **[授**與]。
9. 在 [ **授** 與] 窗格中，按一下 [ **需要多重要素驗證**]，然後按一下 [ **選取**]。
10. 在 [**新增**] 窗格中，按一下 [**啟用原則**] 的 [**開啟**]，然後按一下 [**建立**]。
11. 關閉 [ **Azure 入口網站** ] 和 [ **Microsoft 365 管理中心** ] 索引標籤。

若要測試此原則，請使用使用者3帳戶登出並登入。 您應該會收到設定 MFA 的提示。 這會示範所套用的 MFAUsers 原則。

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[身分識別藍圖](identity-roadmap-microsoft-365.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[適用于企業的 Microsoft 365 檔](https://docs.microsoft.com/microsoft-365-enterprise/)
