---
title: 企業用 Microsoft 365 測試實驗室指南
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 使用「測試實驗室指南」以設定企業用 Microsoft 365 的示範、概念證明或開發/測試環境。
ms.openlocfilehash: 5907edd1bc42b9d679ed020331f225ef2d2b2594
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818738"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a>企業用 Microsoft 365 測試實驗室指南

*本文適用於 Office 365 企業版和企業用 Microsoft 365。*

Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription. 

TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.

您也可以使用 TLG 針對應用程式開發和測試建立具有代表性的環境，亦稱為開發/測試環境。
  
![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

若要瞭解適用于企業版 Microsoft 365 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [測試實驗室堆疊](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)。

[![企業用 Microsoft 365 測試實驗室指南堆疊](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)

## <a name="base-configuration"></a>基本設定

First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:

- 當您想要在僅雲端環境中 (其中不包含任何內部部署元件) 設定及示範企業用 Microsoft 365 功能時，使用[輕量型基底組態](lightweight-base-configuration-microsoft-365-enterprise.md)。

- 當您想要在混合式雲端環境 (該環境使用內部部署元件，例如 Active Directory Domain Services (AD DS) 網域) 中設定及示範企業用 Microsoft 365 功能時，使用[模擬的企業基底組態](simulated-ent-base-configuration-microsoft-365-enterprise.md)。

您也可以建立 Office 365 E5 的測試環境，做法是不要將 Microsoft 365 E5 授權新增至您的試用版或生產測試環境。
    
## <a name="identity"></a>身分識別

若要示範身分識別相關的功能，請參閱：

- [密碼雜湊同步處理](password-hash-sync-m365-ent-test-environment.md)
  
   啟用並測試 AD DS 網域控制站的密碼雜湊型目錄同步處理。

- [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)
  
   啟用及測試對 AD DS 網域控制站的傳遞驗證。

- [同盟驗證](federated-identity-for-your-office-365-dev-test-environment.md)
  
   啟用及測試對 AD DS 網域控制站的同盟驗證。

- [Azure AD 無縫單一登入](single-sign-on-m365-ent-test-environment.md)
  
   使用 AD DS 網域控制站來啟用並測試 Azure AD 無縫單一登入 (SSO)。

- [多重要素驗證](multi-factor-authentication-microsoft-365-test-environment.md)
  
   為特定使用者帳戶啟用並測試智慧型手機的多重要素驗證。

- [保護全域系統管理員帳戶](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   使用條件式存取原則鎖定您的全域系統管理員帳戶。

- [密碼回寫](password-writeback-m365-ent-test-environment.md)

   您可使用密碼回寫，從 Azure AD 變更 AD DS 使用者帳戶的密碼。

- [密碼重設](password-reset-m365-ent-test-environment.md)

   使用自助密碼重設 (SSPR) 來重設密碼。

- [自動授權和群組成員資格](automate-licenses-group-membership-microsoft-365-test-environment.md)

   使用自動授權和動態群組成員資格，讓管理新帳戶比以往更容易。

- [Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md)

   掃描目前的使用者帳戶是否存在漏洞。

- [身分識別與裝置存取](identity-device-access-m365-test-environment.md)

   建立環境來測試建議的身分識別與裝置存取組態，以及條件式存取原則。


## <a name="mobile-device-management"></a>行動裝置管理

若要示範行動裝置管理相關的功能，請參閱：

- [裝置合規性原則](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   建立 Windows 10 裝置的使用者群組和裝置合規性原則。
    
- [註冊 iOS 和 Android 裝置](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   註冊 iOS 或 Android 裝置並從遠端管理。


## <a name="information-protection"></a>資訊保護

若要示範資訊保護相關的功能，請參閱：

- [增強的 Microsoft 365 安全性](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   設定增強的 Microsoft 365 安全性的設定，並且調查內建安全性工具。
  
- [資料分類](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   設定標籤並且將其套用至 SharePoint Online 小組網站中的文件。
    
- [特殊權限存取管理](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   設定特殊權限存取管理，以對您組織中提升權限和特殊權限的工作進行 Just-In-Time 存取。


