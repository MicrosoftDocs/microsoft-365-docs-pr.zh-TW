---
title: 適用於 Microsoft 365 測試環境的密碼重設
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 摘要：設定並測試適用於 Microsoft 365 測試環境的密碼重設。
ms.openlocfilehash: 8be1e898d0b995ddbed7b63c2f0ce07c969592c8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071592"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="0b0e1-103">適用於 Microsoft 365 測試環境的密碼重設</span><span class="sxs-lookup"><span data-stu-id="0b0e1-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="0b0e1-104">Azure Active Directory (Azure AD) 自助密碼重設 (SSPR) 允許使用者重設或解除鎖定其密碼或帳戶。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-104">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="0b0e1-105">本文將以三階段說明如何針對 Microsoft 365 測試環境，設定及測試密碼重設：</span><span class="sxs-lookup"><span data-stu-id="0b0e1-105">This article describes how you can configure and test password resets in your Microsoft 365 test environment in three phases:</span></span>

1.  <span data-ttu-id="0b0e1-106">建立 Microsoft 365 企業版測試環境。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-106">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="0b0e1-107">啟用密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-107">Enable password writeback.</span></span>
3.  <span data-ttu-id="0b0e1-108">設定及測試「使用者 2」帳戶的密碼重設。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-108">Configure and test password reset for the User 2 account.</span></span>
    
![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="0b0e1-110">按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="0b0e1-111">階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="0b0e1-111">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="0b0e1-p101">首先，請遵循[密碼雜湊同步處理](password-hash-sync-m365-ent-test-environment.md)中的指示。以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-p101">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![使用密碼雜湊同步處理測試環境的模擬企業](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="0b0e1-115">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="0b0e1-115">This configuration consists of:</span></span> 
  
- <span data-ttu-id="0b0e1-116">Office 365 E5 和 EMS E5 試用版或付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-116">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="0b0e1-117">簡化的組織內部網域與網際網路的連線，由 Azure 虛擬網路的子網路上的 DC1、APP1 及 CLIENT1 虛擬機器組成</span><span class="sxs-lookup"><span data-stu-id="0b0e1-117">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="0b0e1-118">Azure AD Connect 會在 APP1 上執行，以將 TESTLAB Active Directory Domain Services (AD DS) 網域同步至 Office 365 和 EMS E5 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-118">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>


## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="0b0e1-119">階段 2：啟用密碼回寫</span><span class="sxs-lookup"><span data-stu-id="0b0e1-119">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="0b0e1-120">遵循[測試實驗室指南密碼回寫階段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-120">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="0b0e1-121">您必須啟用密碼回寫才能使用密碼重設。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-121">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="0b0e1-122">階段 3：設定及測試密碼重設</span><span class="sxs-lookup"><span data-stu-id="0b0e1-122">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="0b0e1-123">在這個階段中，您會在透過群組成員資格在 Azure AD 租用戶中設定密碼重設，然後驗證是否運作正常。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-123">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="0b0e1-124">首先，在特定 Azure AD 群組中啟用該帳戶的密碼重設。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-124">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="0b0e1-125">從您瀏覽器的私用執行個體開啟 [https://portal.azure.com](https://portal.azure.com)，然後使用全域系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-125">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="0b0e1-126">在 Azure 入口網站中，按一下 [Azure Active Directory] > [群組] > [新增群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-126">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="0b0e1-p102">將 [群組類型]\*\*\*\* 設為 [安全性]\*\*\*\*、[群族名稱]\*\*\*\* 設為 [PWReset]\*\*\*\*，以及將 [成員類型]\*\*\*\* 設為 [指派]\*\*\*\*，然後按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-p102">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**. Click **Create**.</span></span>
5. <span data-ttu-id="0b0e1-129">在清單中按一下 [PWReset]\*\*\*\* 群組，然後再按一下 [成員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-129">Click the **PWReset** group in the list, and then click **Members**.</span></span>
6. <span data-ttu-id="0b0e1-p103">按一下 [新增成員]\*\*\*\*、接著按一下 [使用者 2]\*\*\*\*，然後再按一下 [選取]\*\*\*\*。關閉 [PWReset]\*\*\*\* 及 [群組]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-p103">Click **Add members**, click **User 2**, and then click **Select**. Close the **PWReset** and **Group** pages.</span></span>
7. <span data-ttu-id="0b0e1-132">在 Azure Active Directory 頁面上，按一下 [密碼重設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-132">On the Azure Active Directory page, click **Password reset**.</span></span>
8. <span data-ttu-id="0b0e1-133">在 [屬性]\*\*\*\* 頁面的 [啟用自助密碼重設]\*\*\*\* 下，選擇 [選取]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-133">From the **Properties** page, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
9. <span data-ttu-id="0b0e1-134">在 [選取群組]\*\*\*\* 中，選取 [PWReset]\*\*\*\*，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-134">From **Select group**, select **PWReset**, and then click **Save**.</span></span>
10. <span data-ttu-id="0b0e1-135">關閉私用瀏覽器執行個體。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-135">Close the private browser instance.</span></span>

<span data-ttu-id="0b0e1-136">下一階段，您將測試「使用者 2」帳戶的密碼重設。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-136">Next, you test password reset for the User 2 account.</span></span>

1. <span data-ttu-id="0b0e1-137">開啟新的私用瀏覽器執行個體，並瀏覽至 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="0b0e1-138">以「使用者 2」的認證登入。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-138">Sign in with the User 2 account credentials.</span></span>
3. <span data-ttu-id="0b0e1-139">在 [避免您失去帳戶的存取權]\*\*\*\* 中，將認證電話設為您的手機號碼，並將認證電子郵件設為您的公司或個人電子郵件帳戶。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-139">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
4. <span data-ttu-id="0b0e1-140">兩者皆經過驗證之後，按一下 [狀況良好]\*\*\*\*，並關閉瀏覽器的私用執行個體。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-140">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
5. <span data-ttu-id="0b0e1-141">開啟新的私用瀏覽器執行個體並前往 [https://aka.ms/sspr](https://aka.ms/sspr)。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-141">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
6. <span data-ttu-id="0b0e1-142">以「使用者 2」的帳戶認證登入，輸入 CAPTCHA 顯示的字元，然後再按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-142">Sign in with the User 2 account credentials, type the characters from the CAPTCHA, and then click **Next**.</span></span>
8. <span data-ttu-id="0b0e1-p104">對於 [驗證步驟 1]\*\*\*\*，請按一下 [寄電子郵件到我的備用電子郵件地址]\*\*\*\*，然後再按一下 [寄電子郵件]\*\*\*\*。當您收到電子郵件後，請輸入驗證碼，然後再按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-p104">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
9. <span data-ttu-id="0b0e1-p105">在 [取回您的帳戶]\*\*\*\* 中，輸入「使用者 2」帳戶的新密碼，然後按一下 [完成]\*\*\*\*。請記下「使用者 2」帳戶的密碼變更，並儲存到安全的位置。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-p105">In **Get back into your account**, type a new password for the User 2 account, and then click **Finish**. Note the changed password of the User 2 account and store it in a safe location.</span></span>
10. <span data-ttu-id="0b0e1-147">在相同瀏覽器的新分頁中，前往 [https://portal.office.com](https://portal.office.com)，並以「使用者 2」帳戶名稱及新密碼登入。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-147">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 2 account name and its new password.</span></span> <span data-ttu-id="0b0e1-148">您應該會看到 [Microsoft Office 首頁]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-148">You should see the **Microsoft Office Home** page.</span></span>

<span data-ttu-id="0b0e1-149">如需在生產中進行密碼重設的相關資訊和連結，請參閱身分識別階段中的「[簡化密碼重設](identity-secure-your-passwords.md#identity-pw-reset)」步驟。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-149">See the [Simplify password resets](identity-secure-your-passwords.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="0b0e1-150">下一步</span><span class="sxs-lookup"><span data-stu-id="0b0e1-150">Next step</span></span>

<span data-ttu-id="0b0e1-151">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="0b0e1-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b0e1-152">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0b0e1-152">See also</span></span>

[<span data-ttu-id="0b0e1-153">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="0b0e1-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="0b0e1-154">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="0b0e1-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="0b0e1-155">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="0b0e1-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
