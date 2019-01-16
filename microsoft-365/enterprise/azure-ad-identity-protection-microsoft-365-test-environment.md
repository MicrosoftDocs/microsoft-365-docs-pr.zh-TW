---
title: Azure AD 身分識別保護您的 Microsoft 365 企業版的測試環境
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
description: 設定 Azure AD 身分識別保護及分析 Microsoft 365 企業版測試環境中目前的帳戶。
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866203"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Azure AD 身分識別保護您的 Microsoft 365 企業版的測試環境

Azure AD 身分識別保護可讓您偵測可能會影響您組織的身分識別的弱點、 設定自動的回覆，及調查事件。本文說明如何啟用 Azure AD 身分識別保護及檢視您的測試環境的帳戶的分析。

有兩個階段來設定 Microsoft 365 企業版測試環境中的 Azure AD 身分識別保護：

1. 建立 Microsoft 365 企業版的測試環境。
2. 啟用並使用 Azure AD 身分識別保護。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境

如果您只想要測試 Azure AD 身分識別保護的基本需求的輕量型方式，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要測試 Azure AD 身分識別保護模擬 enterprise 中，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。
  
> [!NOTE]
> 測試 Azure AD 身分識別保護不需要模擬的企業測試環境中，其中包含連線至網際網路模擬內部網路和 Windows Server AD 樹系目錄同步處理。它會提供這裡是做為選項可以測試 Azure AD 身分識別保護和代表的典型組織的環境中實驗。 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>階段 2： 啟用及使用 Azure AD 身分識別保護

1. 開啟瀏覽器中的私人執行個體，且在 Azure 入口網站登入[https://portal.azure.com](https://portal.azure.com)與 Microsoft 365 企業版測試環境的全域管理員帳戶。
2. 在 Azure 入口網站中，按一下 [**所有服務 > 服務商場**。
3. 輸入**Azure AD 身分識別保護**，然後按一下。
4. **快速入門**blade，在 [**設定**] 下按一下**Onboard** 、 按一下 [**儀表板的 Pin**，然後按一下 [**建立**。
5. 在 Azure 入口網站中，按一下 [儀表板中的 [ **Azure AD 身分識別保護**]。 

   您應該會看到的儀表板**Azure AD 身分識別保護-概觀 （英文)** blade。下**弱點**，請注意其決定不含多重要素驗證註冊的使用者帳戶的數目。此號碼會隨舊版 Microsoft 365 Enterprise 測試實驗室指南，您已完成。

6. 按一下 [透過**調查**] 以查看是否有任何使用者或已偵測到的事件類別。

進一步測試及試驗，請參閱[Simulating 風險事件](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)。

請參閱[危害針對認證 Protect](identity-azure-ad-identity-protection.md)步驟的 「 身分識別 」 階段的資訊和部署 Azure AD 身分識別保護在生產環境中的連結。

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[階段 2：身分識別](identity-infrastructure.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)
