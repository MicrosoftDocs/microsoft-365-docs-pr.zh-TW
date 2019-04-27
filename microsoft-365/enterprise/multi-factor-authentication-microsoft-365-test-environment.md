---
title: 多重要素驗證您的 Microsoft 365 企業版測試環境
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
description: 設定使用文字訊息傳送至 Microsoft 365 企業版測試環境中的智慧型手機的多重要素驗證。
ms.openlocfilehash: ab346934ea639e819e4e45dd6560093629ee9cde
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353175"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>多重要素驗證您的 Microsoft 365 企業版測試環境

針對其他安全性層級的登入 Office 365 或任何服務或應用程式，為您的組織會使用 Azure AD 租用戶，您可以啟用 Azure 多重要素驗證，需要不只是使用者名稱和密碼，可驗證帳戶。 以多重要素驗證使用者，才能確認電話、 輸入傳送文字郵件驗證碼或其智慧型手機上指定應用程式密碼之後正確輸入其密碼。 只有在滿足這個第二次驗證要素之後，他們才可以登入。 
  
本文說明如何啟用及測試文字郵件的驗證為特定帳戶。
  
有兩個主要階段設定多重要素驗證 Microsoft 365 企業版測試環境中的帳戶：
  
1. 建立 Microsoft 365 企業版測試環境。
    
2. 啟用並測試 「 使用者 2 」 帳戶的多重要素驗證。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 按一下[這裡](https://aka.ms/m365etlgstack)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中文件的所有視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1： 建置 Microsoft 365 企業版測試環境

如果您只想以具有最小需求的輕量型方式測試多重要素驗證，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要在模擬的企業中測試多重要素驗證，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。
  
> [!NOTE]
> 測試多重要素驗證不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理 Active Directory 網域服務 (AD DS) 樹系中。 它提供了此選項，讓您可以測試多重要素驗證與代表典型組織的環境中實驗。 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>階段 2： 啟用並測試 「 使用者 2 」 帳戶的多重要素驗證

啟用多重要素驗證的 「 使用者 2 」 帳戶使用下列步驟：
  
1. 開啟瀏覽器的個別的私用執行個體，請移至 Microsoft 365 系統管理中心 ([https://portal.microsoft.com](https://portal.microsoft.com))，然後使用全域管理員帳戶登入。
    
2. 在左方的瀏覽區域中，按一下 [使用者] > [作用中的使用者]****。
    
3. 在 [作用中使用者] 窗格中，按一下 [**更多 > 多重要素驗證設定**]。
    
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


在身分識別階段中的資訊，以及部署在生產環境中的多重要素驗證的連結，請參閱[設定多重要素驗證](identity-multi-factor-authentication.md#identity-mfa)的步驟。
    
## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[階段 2：身分識別](identity-infrastructure.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)
