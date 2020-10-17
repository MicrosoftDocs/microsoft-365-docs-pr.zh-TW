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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 使用「測試實驗室指南」以設定企業用 Microsoft 365 的示範、概念證明或開發/測試環境。
ms.openlocfilehash: fefbb18fd108dceba6f387fb8244619c4bb1c167
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487467"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="21a9e-103">企業用 Microsoft 365 測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="21a9e-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="21a9e-104">*本文適用於 Office 365 企業版和企業用 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="21a9e-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="21a9e-p101">測試實驗室指南 (TLG) 可協助您快速地了解 Microsoft 產品。它們提供規範的指示，可以設定簡化但是具有代表性的測試環境。您可以將這些環境用於示範、自訂或者針對試用版或付費訂閱持續時間建立複雜的概念證明。</span><span class="sxs-lookup"><span data-stu-id="21a9e-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span>

<span data-ttu-id="21a9e-p102">Tlg 設計為模組式。它們相互建立，以建立與您的學習或測試設定需求更接近的多個設定。「我自行建立並運作]，可協助您瞭解新產品或案例的部署需求，讓您能更好地規劃在生產環境中主控。</span><span class="sxs-lookup"><span data-stu-id="21a9e-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario, so that you can better plan for hosting it in production.</span></span>

<span data-ttu-id="21a9e-111">您也可以使用 Tlg 來建立具有代表性的環境，以開發及測試應用程式（也稱為開發/測試環境）。</span><span class="sxs-lookup"><span data-stu-id="21a9e-111">You can also use TLGs to create representative environments to develop and test applications, also known as dev/test environments.</span></span>
  
![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="21a9e-113">如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請展開下圖，或前往 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="21a9e-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, expand the following graphic or go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

<span data-ttu-id="21a9e-114">[![企業用 Microsoft 365 測試實驗室指南堆疊](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="21a9e-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="21a9e-115">基本設定</span><span class="sxs-lookup"><span data-stu-id="21a9e-115">Base configuration</span></span>

<span data-ttu-id="21a9e-p103">首先，建立 [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)的測試環境。您可以建立兩種不同的基本設定類型：</span><span class="sxs-lookup"><span data-stu-id="21a9e-p103">First, create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/). You can create two different types of base configurations:</span></span>

- <span data-ttu-id="21a9e-118">[羽量級基本](lightweight-base-configuration-microsoft-365-enterprise.md) 設定-當您想要在僅雲端環境中為企業功能（不包含任何內部部署元件）設定及示範 Microsoft 365 時，請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="21a9e-118">[Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) - Use this when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="21a9e-119">[模擬企業基本](simulated-ent-base-configuration-microsoft-365-enterprise.md) 設定-當您想要設定及365示範混合雲端環境中的企業功能（例如 Active Directory 網域服務 (AD DS) 網域）時，請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="21a9e-119">[Simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) - Use this when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="21a9e-120">您也可以建立 Office 365 E5 的測試環境，做法是不要將 Microsoft 365 E5 授權新增至您的試用版或生產測試環境。</span><span class="sxs-lookup"><span data-stu-id="21a9e-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="21a9e-121">身分識別</span><span class="sxs-lookup"><span data-stu-id="21a9e-121">Identity</span></span>

<span data-ttu-id="21a9e-122">若要示範身分識別相關的功能，請參閱：</span><span class="sxs-lookup"><span data-stu-id="21a9e-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="21a9e-123">密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="21a9e-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="21a9e-124">啟用並測試 AD DS 網域控制站的密碼雜湊型目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="21a9e-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="21a9e-125">傳遞驗證</span><span class="sxs-lookup"><span data-stu-id="21a9e-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="21a9e-126">啟用及測試對 AD DS 網域控制站的傳遞驗證。</span><span class="sxs-lookup"><span data-stu-id="21a9e-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="21a9e-127">同盟驗證</span><span class="sxs-lookup"><span data-stu-id="21a9e-127">Federated authentication</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
   <span data-ttu-id="21a9e-128">啟用及測試對 AD DS 網域控制站的同盟驗證。</span><span class="sxs-lookup"><span data-stu-id="21a9e-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="21a9e-129">Azure AD 無縫單一登入</span><span class="sxs-lookup"><span data-stu-id="21a9e-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="21a9e-130">使用 AD DS 網域控制站，啟用並測試 Azure AD 無縫單一登入 (無縫 SSO) 。</span><span class="sxs-lookup"><span data-stu-id="21a9e-130">Enable and test Azure AD Seamless Single Sign-on (Seamless SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="21a9e-131">多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="21a9e-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="21a9e-132">為特定使用者帳戶啟用並測試智慧型手機的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="21a9e-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="21a9e-133">保護全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="21a9e-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)

   <span data-ttu-id="21a9e-134">使用條件式存取原則鎖定您的全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="21a9e-134">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="21a9e-135">密碼回寫</span><span class="sxs-lookup"><span data-stu-id="21a9e-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="21a9e-136">您可使用密碼回寫，從 Azure AD 變更 AD DS 使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="21a9e-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="21a9e-137">密碼重設</span><span class="sxs-lookup"><span data-stu-id="21a9e-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="21a9e-138">使用自助密碼重設重設密碼。</span><span class="sxs-lookup"><span data-stu-id="21a9e-138">Use self-service password reset to reset your password.</span></span>

- [<span data-ttu-id="21a9e-139">自動授權和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="21a9e-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="21a9e-140">使用自動授權和動態群組成員資格，讓管理新帳戶比以往更容易。</span><span class="sxs-lookup"><span data-stu-id="21a9e-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="21a9e-141">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="21a9e-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="21a9e-142">掃描目前的使用者帳戶是否存在漏洞。</span><span class="sxs-lookup"><span data-stu-id="21a9e-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="21a9e-143">身分識別與裝置存取</span><span class="sxs-lookup"><span data-stu-id="21a9e-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="21a9e-144">建立環境來測試建議的身分識別與裝置存取組態，以及條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="21a9e-144">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>

## <a name="mobile-device-management"></a><span data-ttu-id="21a9e-145">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="21a9e-145">Mobile device management</span></span>

<span data-ttu-id="21a9e-146">若要示範行動裝置管理相關的功能，請參閱：</span><span class="sxs-lookup"><span data-stu-id="21a9e-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="21a9e-147">裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="21a9e-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="21a9e-148">建立 Windows 10 裝置的使用者群組和裝置合規性原則。</span><span class="sxs-lookup"><span data-stu-id="21a9e-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="21a9e-149">註冊 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="21a9e-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="21a9e-150">註冊 iOS 或 Android 裝置並從遠端管理。</span><span class="sxs-lookup"><span data-stu-id="21a9e-150">Enroll iOS or Android devices and manage them remotely.</span></span>

## <a name="information-protection"></a><span data-ttu-id="21a9e-151">資訊保護</span><span class="sxs-lookup"><span data-stu-id="21a9e-151">Information protection</span></span>

<span data-ttu-id="21a9e-152">若要示範資訊保護相關的功能，請參閱：</span><span class="sxs-lookup"><span data-stu-id="21a9e-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="21a9e-153">增強的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="21a9e-153">Increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="21a9e-154">設定增強的 Microsoft 365 安全性的設定，並且調查內建安全性工具。</span><span class="sxs-lookup"><span data-stu-id="21a9e-154">Configure settings for increased Microsoft 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="21a9e-155">資料分類</span><span class="sxs-lookup"><span data-stu-id="21a9e-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="21a9e-156">設定標籤並且將其套用至 SharePoint Online 小組網站中的文件。</span><span class="sxs-lookup"><span data-stu-id="21a9e-156">Configure and apply labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="21a9e-157">特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="21a9e-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="21a9e-158">設定特殊權限存取管理，以對您組織中提升權限和特殊權限的工作進行 Just-In-Time 存取。</span><span class="sxs-lookup"><span data-stu-id="21a9e-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your organization.</span></span>
