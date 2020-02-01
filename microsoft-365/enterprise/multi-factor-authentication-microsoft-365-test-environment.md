---
title: 多重要素驗證您的 Microsoft 365 企業版測試環境
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
description: 設定使用文字訊息傳送至 Microsoft 365 企業版測試環境中的智慧型手機的多重要素驗證。
ms.openlocfilehash: d99e22cdbd8b08f4752a953b63c2d5215a78ec6c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596830"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>多重要素驗證您的 Microsoft 365 企業版測試環境

*這個測試實驗室指南可用於 Microsoft 365 企業版和 Office 365 企業版兩種測試環境。*

針對其他安全性層級的登入 Microsoft 365，或任何服務或應用程式的訂用帳戶使用 Azure AD 租用戶，您可以啟用 Azure 多重要素驗證，需要不只是使用者名稱和密碼，可驗證帳戶。 

以多重要素驗證使用者，才能確認電話、 輸入傳送文字郵件驗證碼或其智慧型手機上指定應用程式密碼之後正確輸入其密碼。 只有在滿足這個第二次驗證要素之後，他們才可以登入。 
  
本文說明如何啟用及測試文字郵件的驗證，為特定的使用者帳戶。
  
有兩個主要階段設定多重要素驗證 Microsoft 365 企業版測試環境中的帳戶：
  
1. 建立 Microsoft 365 企業版測試環境。
    
2. 啟用並測試 「 使用者 2 」 帳戶的多重要素驗證。

3. 啟用並測試與條件式存取原則 （選用） 的多重要素驗證。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1：建置您的 Microsoft 365 企業版測試環境

如果您只想以具有最小需求的輕量型方式測試多重要素驗證，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要在模擬的企業中測試多重要素驗證，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。
  
> [!NOTE]
> 測試多重要素驗證不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理的 Active Directory 網域服務 (AD DS) 樹系。 它提供了此選項，讓您可以測試多重要素驗證與代表典型組織的環境中實驗。 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>階段 2： 啟用並測試 「 使用者 2 」 帳戶的多重要素驗證

啟用多重要素驗證的 「 使用者 2 」 帳戶使用下列步驟：
  
1. 開啟瀏覽器的個別的私用執行個體，請移至 Microsoft 365 系統管理中心 ([https://portal.microsoft.com](https://portal.microsoft.com))，然後使用全域管理員帳戶登入。
    
2. 在左方的瀏覽區域中，按一下 [使用者] > [作用中的使用者]****。
    
3. 在 [作用中使用者] 窗格中，按一下 [**多重要素驗證**。
    
4. 在清單中，選取 「**使用者 2** 」 帳戶。
    
5. 在 [**使用者 2** ] 區段中，[**快速步驟**，按一下 [**啟用**。
    
6. 在 [**關於啟用多重要素驗證**] 對話方塊中，按一下 [**啟用多重要素驗證**]。
    
7. 在**更新成功**] 對話方塊中，按一下 [**關閉**]。
    
8. 在**Microsoft 365 系統管理中心**] 索引標籤上，按一下右上方，使用者帳戶圖示，然後按一下 [**登出]**。
    
9. 關閉瀏覽器執行個體。
   
完成文字郵件驗證和測試這些步驟的 「 使用者 2 」 帳戶的設定：
  
1. 開啟瀏覽器的新的私用執行個體。
    
2. 移至 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com)) 並以使用者 2 帳戶名稱和密碼登入。
    
3. 登入後，系統會提示您若要設定之帳戶的詳細資訊。 按 [下一步]****。
    
4. 在**其他安全性驗證**] 頁面上：
    
   - 選取您的國家/地區或區域。
    
   - 輸入將接收文字訊息智慧型手機的電話號碼。
    
   - 在**方法**中，按一下 [**傳送我透過文字訊息的程式碼**。
    
5. 按 [下一步]****。
    
6. 從智慧型手機上接收簡訊輸入驗證碼，然後按一下 [**驗證**。
    
7. 在**步驟 3： 保留您現有的應用程式**頁面、 使用者 2 」 帳戶的顯示的應用程式密碼記錄於安全的位置，然後再按一下 [**完成**。
    
8. 如果這是第一次您登入的使用者 2 帳戶後，系統會提示您要變更密碼。 按兩次，輸入原始密碼] 和 [新密碼，然後按一下 [**更新密碼並登入**。 新的密碼記錄於安全的位置。
    
    在瀏覽器的 [ **Microsoft Office 的首頁**] 索引標籤上，您應該針對使用者 2 看到 Office 入口網站。

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>階段 3： 啟用並測試與條件式存取原則的多重要素驗證

*這個階段中只能用於 Microsoft 365 企業版測試環境。*

在這個階段中，您會啟用使用群組和條件式存取原則的使用者 3 帳戶的多重要素驗證。

接下來，建立名為 MFAUsers 的新群組和使用者 3 帳戶新增到它。

1. 在**Microsoft 365 系統管理中心**] 索引標籤上，按一下 [**群組**]，請在左側導覽中，，，然後按一下 [**群組**。
2. 按一下 [**新增群組**。
3. 在 [**選擇群組類型**] 窗格中，選取 [**安全性**]，然後按一下 [**下一步**。
4. 在 [**設定 [基本**] 窗格中，按一下 [**建立群組**]，然後按一下 [**關閉**。
5. 在 [**檢閱並完成新增群組**] 窗格中，輸入**MFAUsers**，，然後按 [**下一步**。
6. 在群組清單中，按一下 [ **MFAUsers**群組]。
7. 在**MFAUsers** ] 窗格中，按一下 [**成員**]，然後按一下 [**檢視所有及管理成員**。
8. 在**MFAUsers** ] 窗格中，按一下 [**新增成員**、 選取的**使用者 3**帳戶後，，然後按一下 [**儲存 > Close > 關閉**。

接下來，建立條件式存取原則以多重要素驗證需要 MFAUsers 群組的成員。

1. 在瀏覽器的新索引標籤，移至 [ [https://portal.azure.com](https://portal.azure.com)。
2. 按一下 [ **Azure Active Directory > 安全性 > 條件式存取**。
3. 在 [**條件式存取 – 原則**] 窗格中，按一下 [**新增原則**]。
4. 在 [**新增**] 窗格中，輸入**名稱**中的**使用者帳戶的 MFA** 。
5. 在 [**指派**] 區段中，按一下 [**使用者和群組**。
6. 在 [**使用者和群組**] 窗格的 [**包含**] 索引標籤中，按一下 [**選取使用者及群組 > 使用者和群組 >，請選取**。
7. 在 [**選取**] 窗格中，按一下 [ **MFAUsers** ] 群組中，然後按一下 [**選取 > 完成**。
8. 在 [**新增**] 窗格中的 [**存取控制**] 區段中，按一下 [**授與**]。
9. 在 [**授與**] 窗格中，按一下 [**需要多重要素驗證**，，然後按一下 [**選取**。
10. 在 [**新增**] 窗格中，**啟用原則**，請按一下 [ **** ，然後按一下 [**建立**]。
11. 關閉 [ **Azure 入口網站**和**Microsoft 365 系統管理中心**] 索引標籤。

若要測試此原則，登出並以使用者 3 帳戶登入。 應該會提示您設定 MFA。 此示範 MFAUsers 原則會被套用。

在身分識別階段中的資訊，以及部署在生產環境中的多重要素驗證的連結，請參閱[設定多重要素驗證](identity-secure-user-sign-ins.md#identity-mfa)的步驟。
    
## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[階段 2：身分識別](identity-infrastructure.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)
