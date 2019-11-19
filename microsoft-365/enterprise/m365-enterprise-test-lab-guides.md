---
title: Microsoft 365 企業版測試實驗室指南
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/04/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 使用「測試實驗室指南」以設定 Microsoft 365 企業版的示範、概念證明或開發/測試環境。
ms.openlocfilehash: 2f6fd8c17096c9c25a0f1af886894e68d33e939d
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672569"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a><span data-ttu-id="28efa-103">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="28efa-103">Microsoft 365 Enterprise Test Lab Guides</span></span>

<span data-ttu-id="28efa-104">*本文適用於 Office 365 企業版和 Microsoft 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="28efa-104">*This article applies to both Office 365 Enterprise and Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="28efa-p101">測試實驗室指南 (TLG) 可協助您快速地了解 Microsoft 產品。它們提供規範的指示，可以設定簡化但是具有代表性的測試環境。您可以將這些環境用於示範、自訂或者針對試用版或付費訂閱持續時間建立複雜的概念證明。</span><span class="sxs-lookup"><span data-stu-id="28efa-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="28efa-p102">TLG 設計為模組化。它們根據彼此而建置，以建立能夠更加符合您學習或測試組態需求的多個組態。「我自行建置而且可以運作」提供實做經驗，可協助您了解新產品或案例的部署需求，因此您可以更有效地規劃在生產環境中裝載。</span><span class="sxs-lookup"><span data-stu-id="28efa-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="28efa-111">您也可以使用 TLG 針對應用程式開發和測試建立具有代表性的環境，亦稱為開發/測試環境。</span><span class="sxs-lookup"><span data-stu-id="28efa-111">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="28efa-113">按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="28efa-113">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

<span data-ttu-id="28efa-114">[![Microsoft 365 企業版測試實驗室指南堆疊](./media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="28efa-114">[![The Microsoft 365 Enterprise Test Lab Guide stack](./media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="28efa-115">基本設定</span><span class="sxs-lookup"><span data-stu-id="28efa-115">Base configuration</span></span>

<span data-ttu-id="28efa-p103">首先，您可以建立 [Microsoft 365 企業版](https://docs.microsoft.com/microsoft-365-enterprise/)的測試環境，以便包含 Office 365 E5、Enterprise Mobility + Security (EMS) E5 及 Windows 10 企業版。您可以建立兩個不同類型的基底組態：</span><span class="sxs-lookup"><span data-stu-id="28efa-p103">First, you create a test environment for [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:</span></span>

- <span data-ttu-id="28efa-118">當您想要在僅雲端環境中 (其中不包含任何內部部署元件) 設定及示範 Microsoft 365 企業版功能時，使用[輕量型基底組態](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="28efa-118">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="28efa-119">當您想要在混合式雲端環境 (該環境使用內部部署元件，例如 Active Directory Domain Services (AD DS) 網域) 中設定及示範 Microsoft 365 企業版功能時，使用[模擬的企業基底組態](simulated-ent-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="28efa-119">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="28efa-120">您也可以建立 Office 365 E5 的測試環境，做法是不要將 Microsoft 365 E5 授權新增至您的試用版或生產測試環境。</span><span class="sxs-lookup"><span data-stu-id="28efa-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="28efa-121">身分識別</span><span class="sxs-lookup"><span data-stu-id="28efa-121">Identity</span></span>

<span data-ttu-id="28efa-122">若要示範身分識別相關的功能，請參閱：</span><span class="sxs-lookup"><span data-stu-id="28efa-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="28efa-123">密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="28efa-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="28efa-124">啟用並測試 AD DS 網域控制站的密碼雜湊型目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="28efa-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="28efa-125">傳遞驗證</span><span class="sxs-lookup"><span data-stu-id="28efa-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="28efa-126">啟用及測試對 AD DS 網域控制站的傳遞驗證。</span><span class="sxs-lookup"><span data-stu-id="28efa-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="28efa-127">Azure AD 無縫單一登入</span><span class="sxs-lookup"><span data-stu-id="28efa-127">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="28efa-128">使用 AD DS 網域控制站來啟用並測試 Azure AD 無縫單一登入 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="28efa-128">Enable and test Azure AD Seamless Single Sign-on (SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="28efa-129">多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="28efa-129">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="28efa-130">為特定使用者帳戶啟用並測試智慧型手機的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="28efa-130">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="28efa-131">保護全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="28efa-131">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="28efa-132">使用條件式存取原則鎖定您的全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="28efa-132">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="28efa-133">密碼回寫</span><span class="sxs-lookup"><span data-stu-id="28efa-133">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="28efa-134">您可使用密碼回寫，從 Azure AD 變更 AD DS 使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="28efa-134">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="28efa-135">密碼重設</span><span class="sxs-lookup"><span data-stu-id="28efa-135">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="28efa-136">使用自助密碼重設 (SSPR) 來重設密碼。</span><span class="sxs-lookup"><span data-stu-id="28efa-136">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="28efa-137">自動授權和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="28efa-137">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="28efa-138">使用自動授權和動態群組成員資格，讓管理新帳戶比以往更容易。</span><span class="sxs-lookup"><span data-stu-id="28efa-138">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="28efa-139">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="28efa-139">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="28efa-140">掃描目前的使用者帳戶是否存在漏洞。</span><span class="sxs-lookup"><span data-stu-id="28efa-140">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="28efa-141">身分識別與裝置存取</span><span class="sxs-lookup"><span data-stu-id="28efa-141">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="28efa-142">建立環境來測試建議的身分識別與裝置存取組態，以及條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="28efa-142">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>


## <a name="mobile-device-management"></a><span data-ttu-id="28efa-143">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="28efa-143">Mobile device management</span></span>

<span data-ttu-id="28efa-144">若要示範行動裝置管理相關的功能，請參閱：</span><span class="sxs-lookup"><span data-stu-id="28efa-144">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="28efa-145">裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="28efa-145">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="28efa-146">建立 Windows 10 裝置的使用者群組和裝置合規性原則。</span><span class="sxs-lookup"><span data-stu-id="28efa-146">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="28efa-147">註冊 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="28efa-147">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="28efa-148">註冊 iOS 或 Android 裝置並從遠端管理。</span><span class="sxs-lookup"><span data-stu-id="28efa-148">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="28efa-149">資訊保護</span><span class="sxs-lookup"><span data-stu-id="28efa-149">Information protection</span></span>

<span data-ttu-id="28efa-150">若要示範資訊保護相關的功能，請參閱：</span><span class="sxs-lookup"><span data-stu-id="28efa-150">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="28efa-151">增強的 Office 365 安全性</span><span class="sxs-lookup"><span data-stu-id="28efa-151">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="28efa-152">設定增強的 Office 365 安全性的設定，並且調查內建安全性工具。</span><span class="sxs-lookup"><span data-stu-id="28efa-152">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="28efa-153">資料分類</span><span class="sxs-lookup"><span data-stu-id="28efa-153">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="28efa-154">設定 Office 365 標籤並且將其套用至 SharePoint Online 小組網站中的文件。</span><span class="sxs-lookup"><span data-stu-id="28efa-154">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="28efa-155">特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="28efa-155">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="28efa-156">設定特殊權限存取管理，以對您 Office 365 組織中提升權限和特殊權限的工作進行 Just-In-Time 存取。</span><span class="sxs-lookup"><span data-stu-id="28efa-156">Configure privileged access management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>


