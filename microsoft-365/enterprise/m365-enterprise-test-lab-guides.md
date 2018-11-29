---
title: Microsoft 365 企業版測試實驗室指南
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 使用「測試實驗室指南」以設定 Microsoft 365 企業版的示範、概念證明或開發/測試環境。
ms.openlocfilehash: df723647748532936e40bbdb4e34ff698b9fa650
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866619"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a><span data-ttu-id="6dc14-103">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="6dc14-103">Microsoft 365 Enterprise Test Lab Guides</span></span>

<span data-ttu-id="6dc14-p101">測試實驗室指南 (TLG) 可協助您快速地了解 Microsoft 產品。它們提供規範的指示，可以設定簡化但是具有代表性的測試環境。您可以將這些環境用於示範、自訂或者針對試用版或付費訂閱持續時間建立複雜的概念證明。</span><span class="sxs-lookup"><span data-stu-id="6dc14-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="6dc14-p102">TLG 設計為模組化。它們根據彼此而建置，以建立能夠更加符合您學習或測試組態需求的多個組態。「我自行建置而且可以運作」提供實做經驗，可協助您了解新產品或案例的部署需求，因此您可以更有效地規劃在生產環境中裝載。</span><span class="sxs-lookup"><span data-stu-id="6dc14-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="6dc14-110">您也可以使用 TLG 針對應用程式開發和測試建立具有代表性的環境，亦稱為開發/測試環境。</span><span class="sxs-lookup"><span data-stu-id="6dc14-110">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="6dc14-112">按一下[這裡](https://aka.ms/m365etlgstack) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="6dc14-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="base-configuration"></a><span data-ttu-id="6dc14-113">基本設定</span><span class="sxs-lookup"><span data-stu-id="6dc14-113">Base configuration</span></span>

<span data-ttu-id="6dc14-p103">首先，您可以建立 [Microsoft 365 企業版](https://docs.microsoft.com/microsoft-365-enterprise/)的測試環境，以便包含 Office 365 E5、Enterprise Mobility + Security (EMS) E5 及 Windows 10 企業版。您可以建立兩個不同類型的基底組態：</span><span class="sxs-lookup"><span data-stu-id="6dc14-p103">First, you create a test environment for [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:</span></span>

- <span data-ttu-id="6dc14-116">當您想要在僅雲端環境中 (其中不包含任何內部部署元件) 設定及示範 Microsoft 365 企業版功能時，使用[輕量型基底組態](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="6dc14-116">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="6dc14-117">當您想要在混合式雲端環境中 (該環境使用內部部署元件，例如 Windows Server Active Directory (AD) 網域) 設定及示範 Microsoft 365 企業版功能時，使用[模擬的企業基底組態](simulated-ent-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="6dc14-117">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as a Windows Server Active Directory (AD) domain.</span></span>
    
## <a name="identity"></a><span data-ttu-id="6dc14-118">身分識別</span><span class="sxs-lookup"><span data-stu-id="6dc14-118">Identity</span></span>

<span data-ttu-id="6dc14-119">若要示範身分識別相關的功能，請參閱：</span><span class="sxs-lookup"><span data-stu-id="6dc14-119">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="6dc14-120">密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="6dc14-120">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="6dc14-121">從 Windows Server AD 網域控制站啟用及測試密碼雜湊型目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="6dc14-121">Enable and test password hash-based directory synchronization from a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="6dc14-122">傳遞驗證</span><span class="sxs-lookup"><span data-stu-id="6dc14-122">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="6dc14-123">啟用及測試對 Windows Server AD 網域控制站的傳遞驗證。</span><span class="sxs-lookup"><span data-stu-id="6dc14-123">Enable and test pass-through authentication to a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="6dc14-124">Azure AD 無縫單一登入</span><span class="sxs-lookup"><span data-stu-id="6dc14-124">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="6dc14-125">使用 Windows Server AD 網域控制站來啟用並測試 Azure AD 無縫單一登入 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="6dc14-125">Enable and test Azure AD Seamless Single Sign-on (SSO) with a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="6dc14-126">多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="6dc14-126">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="6dc14-127">為特定使用者帳戶啟用並測試智慧型手機的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="6dc14-127">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="6dc14-128">保護全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="6dc14-128">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="6dc14-129">使用 Office 365 雲端 App 安全性和條件式存取原則鎖定您的全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="6dc14-129">Lock down your global administrator accounts with Office 365 Cloud App Security and conditional access policies.</span></span>

- [<span data-ttu-id="6dc14-130">密碼重設</span><span class="sxs-lookup"><span data-stu-id="6dc14-130">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="6dc14-131">使用自助密碼重設 (SSPR) 來重設密碼。</span><span class="sxs-lookup"><span data-stu-id="6dc14-131">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="6dc14-132">自動授權和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="6dc14-132">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="6dc14-133">使用自動授權和動態群組成員資格，讓管理新帳戶比以往更容易。</span><span class="sxs-lookup"><span data-stu-id="6dc14-133">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="6dc14-134">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="6dc14-134">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="6dc14-135">掃描目前的使用者帳戶是否存在漏洞。</span><span class="sxs-lookup"><span data-stu-id="6dc14-135">Scan your current user accounts for vulnerabilities.</span></span>

## <a name="mobile-device-management"></a><span data-ttu-id="6dc14-136">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="6dc14-136">Mobile device management</span></span>

<span data-ttu-id="6dc14-137">若要示範行動裝置管理相關的功能，請參閱：</span><span class="sxs-lookup"><span data-stu-id="6dc14-137">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="6dc14-138">MAM 原則</span><span class="sxs-lookup"><span data-stu-id="6dc14-138">MAM policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="6dc14-139">建立使用者群組和適用於 iOS 和 Android 裝置的行動應用程式管理 (MAM) 原則。</span><span class="sxs-lookup"><span data-stu-id="6dc14-139">Create user groups and mobile application management (MAM) policies for iOS and Android devices.</span></span>
    
- [<span data-ttu-id="6dc14-140">註冊 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="6dc14-140">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="6dc14-141">註冊 iOS 或 Android 裝置並從遠端管理。</span><span class="sxs-lookup"><span data-stu-id="6dc14-141">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="6dc14-142">資訊保護</span><span class="sxs-lookup"><span data-stu-id="6dc14-142">Information protection</span></span>

<span data-ttu-id="6dc14-143">若要示範資訊保護相關的功能，請參閱：</span><span class="sxs-lookup"><span data-stu-id="6dc14-143">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="6dc14-144">增強的 Office 365 安全性</span><span class="sxs-lookup"><span data-stu-id="6dc14-144">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="6dc14-145">設定增強的 Office 365 安全性的設定，並且調查內建安全性工具。</span><span class="sxs-lookup"><span data-stu-id="6dc14-145">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="6dc14-146">資料分類</span><span class="sxs-lookup"><span data-stu-id="6dc14-146">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="6dc14-147">設定 Office 365 標籤並且將其套用至 SharePoint Online 小組網站中的文件。</span><span class="sxs-lookup"><span data-stu-id="6dc14-147">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="6dc14-148">Microsoft 365 企業版測試環境的特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="6dc14-148">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="6dc14-149">設定特殊權限存取管理，以對您 Office 365 組織中提升權限和特殊權限的工作進行 Just-In-Time 存取。</span><span class="sxs-lookup"><span data-stu-id="6dc14-149">Configure privileged acccess management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="6dc14-150">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6dc14-150">See also</span></span>

[<span data-ttu-id="6dc14-151">使用雲端採用測試實驗室指南來體驗 Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="6dc14-151">Experience the Microsoft Cloud with Cloud Adoption Test Lab Guides</span></span>](https://mva.microsoft.com/training-courses/experience-the-microsoft-cloud-with-cloud-adoption-test-lab-guides-17960?l=LXNRdhSLE_1000115881)
    
[<span data-ttu-id="6dc14-152">One Microsoft Cloud 測試實驗室指南堆疊</span><span class="sxs-lookup"><span data-stu-id="6dc14-152">One Microsoft Cloud Test Lab Guide stack</span></span>](http://aka.ms/catlgstack)
