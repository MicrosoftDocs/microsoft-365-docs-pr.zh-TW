---
title: 適用于 Microsoft 365 企業版測試環境的 Azure AD 身分識別保護
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
description: 設定 Azure AD 身分識別保護，並分析您 Microsoft 365 for enterprise 測試環境中目前的帳戶。
ms.openlocfilehash: 0cb0acf3faee13676573b04178bd6b4d3d36da4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905341"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>適用于 Microsoft 365 企業版測試環境的 Azure AD 身分識別保護

*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*

您可以使用 Azure Active Directory (Azure AD) 身分識別保護，偵測影響組織身分識別的潛在弱點、設定自動回應，以及調查事件。 本文說明如何使用 Azure AD Identity Protection 來查看測試環境帳戶的分析。

在 Microsoft 365 for enterprise 測試環境中設定 Azure AD 身分識別保護包括兩個階段：

- [階段1：組建您的 Microsoft 365 企業版測試環境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [階段2：使用 Azure AD 身分識別保護](#phase-2-use-azure-ad-identity-protection)

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>階段1：組建您的 Microsoft 365 企業版測試環境

如果您只想以輕量的方式測試 Azure AD 身分識別保護，請依照 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。
  
如果您想要在模擬的企業中測試 Azure AD 身分識別保護，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。
  
> [!NOTE]
> 測試 Azure AD 身分識別保護不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 (AD DS) 樹系中的 Active Directory 網域服務的目錄同步處理。 這裡是以選項形式提供的，可讓您測試 Azure AD 身分識別保護，並在代表一般組織的環境中進行試驗。
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>階段2：使用 Azure AD 身分識別保護

1. [https://portal.azure.com](https://portal.azure.com)使用 Microsoft 365 for enterprise 測試環境的全域系統管理員帳戶，開啟瀏覽器的私人實例，並登入 Azure 入口網站。
2. 在 Azure 入口網站的搜尋方塊中，輸入 **identity protection** ，然後選取 **Azure AD identity protection**。
3. 在 [身分 **識別保護-一覽表** ] 中，選取每個報告以查看其報告。
4. 在 [ **通知**] 底下，選取 [ **使用者的風險偵測警示**]。
5. 在 [偵測 **到風險的使用者警示** ] 窗格中，選取 [ **中**]。
6. **若要將電子郵件傳送給下列使用者**，請選取 [**包含**]，並確認您的全域系統管理員帳戶位於選取的成員清單中。
7. 選取 [儲存]。

在 [ **保護**] 底下，選取 [各種原則] 以查看如何進行設定。 如果您建立並啟用原則，請確定其不會封鎖所有使用者的存取，否則您可能無法登入。 若要避免這種情況，請排除特定的使用者帳戶，例如全域管理員。

如需進一步的測試及實驗，請參閱 [模擬風險事件](/azure/active-directory/active-directory-identityprotection-playbook)。

## <a name="next-step"></a>下一步

瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。

## <a name="see-also"></a>另請參閱

[身分識別藍圖](identity-roadmap-microsoft-365.md)

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[Microsoft 365 企業版文件](/microsoft-365-enterprise/)