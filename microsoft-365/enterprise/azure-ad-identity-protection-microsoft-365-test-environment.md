---
title: Azure AD Identity Protection，您的 Microsoft 365 企業版測試環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 設定 Azure AD Identity Protection 及分析您的 Microsoft 365 企業版測試環境中的目前的帳戶。
ms.openlocfilehash: 97530dcec9c32882bbe3b66eb53eaa6d4668a838
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071712"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Azure AD Identity Protection，您的 Microsoft 365 企業版測試環境

Azure AD Identity Protection 可讓您偵測會影響組織身分識別的潛在弱點，設定自動式回應，並調查事件。 本文說明如何啟用 Azure AD Identity Protection，並檢視您的測試環境帳戶的分析。

有兩個主要階段設定 Microsoft 365 企業版測試環境中的 Azure AD Identity Protection:

1. 建立 Microsoft 365 企業版測試環境。
2. 啟用並使用 Azure AD Identity Protection。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 按一下[這裡](https://aka.ms/m365etlgstack) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1： 建置 Microsoft 365 企業版測試環境

如果您只想以具有最小需求的輕量型方式測試 Azure AD Identity Protection，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要在模擬的企業中測試 Azure AD Identity Protection，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。
  
> [!NOTE]
> 測試 Azure AD Identity Protection 不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理 Active Directory 網域服務 (AD DS) 樹系中。 它提供了此選項，讓您可以測試 Azure AD Identity Protection，並代表典型組織的環境中實驗。 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>階段 2： 啟用，並使用 Azure AD Identity Protection

1. 開啟瀏覽器的私用執行個體並登入 Azure 入口網站，網址[https://portal.azure.com](https://portal.azure.com)以全域系統管理員帳戶的 Microsoft 365 企業版測試環境。
2. 在 Azure 入口網站中，按一下 [**所有服務 > 市集**]。
3. 輸入**Azure AD Identity Protection** ，然後按一下它。
4. 在 [**快速入門**] 刀鋒視窗上，按一下**Onboard** [**設定**] 下，按一下**釘選到儀表板**]，然後按一下 [**建立**。
5. 在 Azure 入口網站中，按一下 [儀表板上的**Azure AD Identity Protection** 。 

   您應該會看到**Azure AD Identity Protection-概觀**] 刀鋒視窗中的儀表板。 下**弱點**，請注意其決定不用多重要素驗證註冊的使用者帳戶的數目。 此數字會根據先前 Microsoft 365 企業版測試實驗室指南，您必須完成而有所不同。

6. [所有類別的**調查]** 若要查看是否有任何使用者或已偵測到的事件。

進一步測試與試驗，請參閱[Simulating 風險事件](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)。

在身分識別階段中的資訊，以及部署在生產環境中的 Azure AD Identity Protection 的連結，請參閱[Protect 針對認證洩露](identity-secure-user-sign-ins.md#identity-ident-prot)步驟。

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[階段 2：身分識別](identity-infrastructure.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)
