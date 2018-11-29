---
title: Microsoft 365 企業版的多重要素驗證測試環境
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
description: 設定使用文字訊息傳送給 Microsoft 365 企業版測試環境中的智慧型手機的多重要素驗證。
ms.openlocfilehash: aae493e79a197635b2e14fa7f238a3189ed695ae
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866121"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 企業版的多重要素驗證測試環境

登入 Office 365 或任何服務或您的組織會使用 Azure AD 租用戶的應用程式的安全性其他層級，您可以啟用 Azure 需要超過剛使用者名稱和密碼，確認的多重要素驗證帳戶。使用多重要素驗證的使用者所需確認電話、 輸入驗證碼傳送文字郵件內或智慧型電話上指定的應用程式密碼後正確地輸入其密碼。未滿足此第二個驗證因素之後才可以登入。 
  
本文說明如何啟用並測試的特定帳戶的文字訊息型驗證。
  
有帳戶 Microsoft 365 企業版測試環境中的多重要素驗證設定的兩個階段：
  
1. 建立 Microsoft 365 企業版的測試環境。
    
2. 啟用並測試使用者 2 帳戶的多重要素驗證。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 按一下[這裡](https://aka.ms/m365etlgstack) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境

如果您只想要測試多重要素驗證的最低需求的輕量型方式，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要測試模擬企業中的多重要素驗證，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。
  
> [!NOTE]
> 測試多重要素驗證不需要模擬的企業測試環境中，其中包含連線至網際網路模擬內部網路和 Windows Server AD 樹系目錄同步處理。它會提供這裡是做為選項可以測試多重要素驗證和代表的典型組織的環境中實驗。 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>階段 2： 啟用並測試使用者 2 帳戶的多重要素驗證

啟用多重要素驗證使用者 2 帳戶進行這些步驟：
  
1. 開啟瀏覽器中的個別的私人執行個體，請移至 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com))，並再登入您的全域管理員帳戶。
    
2. 從主要的入口網站頁面中，按一下 [管理]****。
    
3. 在左方的瀏覽區域中，按一下 [使用者] > [作用中的使用者]****。
    
4. 在 [作用中使用者] 窗格中，按一下 [**更多 > 多重要素驗證安裝**。
    
5. 在清單中，選取**使用者 2**帳戶。
    
6. **使用者 2** ] 區段中的 [**快速步驟**，按一下 [**啟用**。
    
7. **如何啟用多重要素驗證**] 對話方塊中，按一下 [**啟用多重要素驗證**]。
    
8. 在**更新成功**] 對話方塊中，按一下 [**關閉**]。
    
9. 在 [ **Microsoft Office Home** ] 索引標籤上按一下 [使用者帳戶中的圖示右上方，和 [**登出**。
    
10. 關閉瀏覽器執行個體。
   
完成設定使用者 2 帳戶使用的文字訊息的驗證和測試這些步驟：
  
1. 開啟瀏覽器中新的私人執行個體。
    
2. 移至 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com)) 和登入的使用者 2 帳戶 (user2 @\<組織名稱 >。 onmicrosoft.com) 和密碼。
    
3. 登入之後, 會提示您設定如需詳細資訊的帳戶。按一下 [**下一步**]。
    
4. 在 [**其他安全性驗證**] 頁面上：
    
   - 選取 [國家或地區。
    
   - 輸入要接收文字訊息智慧型手機電話號碼。
    
   - 在**方法**中，按一下 [**傳送我文字訊息的程式碼**。
    
5. 按 [下一步]****。
    
6. 輸入驗證碼從智慧型手機上接收的文字訊息，然後按一下**確認**。
    
7. 在**步驟 3： 保留現有的應用程式**頁面、 使用者 2 帳戶將顯示應用程式密碼記錄在安全的位置，然後再按一下 [**完成**。
    
8. 如果這是第一次您登入的使用者 2 帳戶後，系統提示您變更密碼。按兩次，輸入原始密碼] 和 [新密碼] 和 [**更新密碼，登入**。安全的位置記錄的新密碼。
    
    您應請參閱 ＜ Office 365 入口網站使用者 2 在瀏覽器的 [ **Microsoft Office Home** ] 索引標籤。


請參閱 「 身分識別 」 階段的資訊及連結部署在生產環境中的多重要素驗證[設定多重要素驗證](identity-multi-factor-authentication.md)步驟。
    
## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[階段 2：身分識別](identity-infrastructure.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)
