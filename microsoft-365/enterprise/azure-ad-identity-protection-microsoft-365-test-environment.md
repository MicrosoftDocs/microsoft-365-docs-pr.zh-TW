---
title: Azure AD Identity Protection，您的 Microsoft 365 企業版測試環境
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 設定 Azure AD Identity Protection 及分析您的 Microsoft 365 企業版測試環境中的目前的帳戶。
ms.openlocfilehash: 376fc838191314e93ae37accb7fc5066456499fb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597160"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Azure AD Identity Protection，您的 Microsoft 365 企業版測試環境

*這個測試實驗室指南只能用於 Microsoft 365 企業版測試環境。*

Azure Active Directory (Azure AD) 身分識別保護可讓您偵測會影響組織身分識別的潛在弱點，設定自動式回應，並調查事件。 本文說明如何使用 Azure AD Identity Protection 來檢視您的測試環境帳戶的分析。

有兩個主要階段設定 Microsoft 365 企業版測試環境中的 Azure AD Identity Protection:

1. 建立 Microsoft 365 企業版測試環境。
2. 使用 Azure AD Identity Protection。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1：建置您的 Microsoft 365 企業版測試環境

如果您只想以具有最小需求的輕量型方式測試 Azure AD Identity Protection，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要在模擬的企業中測試 Azure AD Identity Protection，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。
  
> [!NOTE]
> 測試 Azure AD Identity Protection 不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理的 Active Directory 網域服務 (AD DS) 樹系。 它提供了此選項，讓您可以測試 Azure AD Identity Protection，並代表典型組織的環境中實驗。 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>階段 2： 使用 Azure AD Identity Protection

1. 開啟瀏覽器的私用執行個體並登入 Azure 入口網站，網址[https://portal.azure.com](https://portal.azure.com)以全域系統管理員帳戶的 Microsoft 365 企業版測試環境。
2. 在 Azure 入口網站中，在 [搜尋] 方塊中，輸入**identity protection** ，然後按一下 [ **Azure AD Identity Protection**。
3. 在 [ **Identity Protection-概觀**] 刀鋒視窗中，按一下 [在每一份報告來查看他們已回報。
4. [**通知**，按一下 [**使用者風險偵測到的警示**。
5. 在 [**使用者風險偵測到提醒**] 窗格中，選取 [**中等**]。
6. 針對**電子郵件傳送給下列的使用者**，按一下 [ **Included**並確認您的全域系統管理員帳戶是在清單中選取的成員。
7. 按一下 [儲存]****。

按一下 [**保護**，查看如何將其設定不同的原則。 如果您建立並啟動原則，請確定它不會封鎖存取太寬範圍的條件，或您可能無法登入，即使為全域系統管理員。

進一步測試與試驗，請參閱[Simulating 風險事件](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)。

在身分識別階段中的資訊，以及部署在生產環境中的 Azure AD Identity Protection 的連結，請參閱[Protect 針對認證洩露](identity-secure-user-sign-ins.md#identity-ident-prot)步驟。

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[階段 2：身分識別](identity-infrastructure.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)
