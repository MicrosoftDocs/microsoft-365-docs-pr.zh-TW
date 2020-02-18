---
title: 適用於 Microsoft 365 測試環境的密碼重設
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
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
ms.openlocfilehash: c8d5ed0c7feac98afd3230a305f4ab1f850ca7f8
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066139"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a1156-103">適用於 Microsoft 365 測試環境的密碼重設</span><span class="sxs-lookup"><span data-stu-id="a1156-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a1156-104">*這個測試實驗室指南只能用於 Microsoft 365 企業版測試環境。*</span><span class="sxs-lookup"><span data-stu-id="a1156-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a1156-105">Azure Active Directory (Azure AD) 自助密碼重設 (SSPR) 允許使用者重設或解除鎖定其密碼或帳戶。</span><span class="sxs-lookup"><span data-stu-id="a1156-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="a1156-106">本文將以三階段說明如何針對 Microsoft 365 測試環境，設定及測試密碼重設：</span><span class="sxs-lookup"><span data-stu-id="a1156-106">This article describes how you can configure and test password resets in your Microsoft 365 test environment in three phases:</span></span>

1.  <span data-ttu-id="a1156-107">建立 Microsoft 365 企業版測試環境。</span><span class="sxs-lookup"><span data-stu-id="a1156-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="a1156-108">啟用密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="a1156-108">Enable password writeback.</span></span>
3.  <span data-ttu-id="a1156-109">設定及測試「使用者 3」帳戶的密碼重設。</span><span class="sxs-lookup"><span data-stu-id="a1156-109">Configure and test password reset for the User 3 account.</span></span>
    
![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a1156-111">按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="a1156-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a1156-112">階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="a1156-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a1156-p101">首先，請遵循[密碼雜湊同步處理](password-hash-sync-m365-ent-test-environment.md)中的指示。以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="a1156-p101">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![使用密碼雜湊同步處理測試環境的模擬企業](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="a1156-116">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="a1156-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="a1156-117">Microsoft 365 E5 或 Office 365 E5 試用版或付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="a1156-117">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="a1156-118">簡化的組織內部網域與網際網路的連線，由 Azure 虛擬網路的子網路上的 DC1、APP1 及 CLIENT1 虛擬機器組成</span><span class="sxs-lookup"><span data-stu-id="a1156-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="a1156-119">Azure AD Connect 會在 APP1 上執行，以將 TESTLAB Active Directory Domain Services (AD DS) 網域同步至 Microsoft 365 或 Office 365 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="a1156-119">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="a1156-120">階段 2：啟用密碼回寫</span><span class="sxs-lookup"><span data-stu-id="a1156-120">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="a1156-121">遵循[測試實驗室指南密碼回寫階段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="a1156-121">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="a1156-122">您必須啟用密碼回寫才能使用密碼重設。</span><span class="sxs-lookup"><span data-stu-id="a1156-122">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="a1156-123">階段 3：設定及測試密碼重設</span><span class="sxs-lookup"><span data-stu-id="a1156-123">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="a1156-124">在這個階段中，您會在透過群組成員資格在 Azure AD 租用戶中設定密碼重設，然後驗證是否運作正常。</span><span class="sxs-lookup"><span data-stu-id="a1156-124">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="a1156-125">首先，在特定 Azure AD 群組中啟用該帳戶的密碼重設。</span><span class="sxs-lookup"><span data-stu-id="a1156-125">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="a1156-126">從您瀏覽器的私用執行個體開啟 [https://portal.azure.com](https://portal.azure.com)，然後使用全域系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="a1156-126">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="a1156-127">在 Azure 入口網站中，按一下 [Azure Active Directory] > [群組] > [新增群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1156-127">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="a1156-128">將 [群組類型]\*\*\*\* 設為 [安全性]\*\*\*\*、[群組名稱]\*\*\*\* 設為 [PWReset]\*\*\*\*，以及將 [成員類型]\*\*\*\* 設為 [指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1156-128">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span> 
4. <span data-ttu-id="a1156-129">按一下 [成員]\*\*\*\*，尋找並選取 [使用者 3]\*\*\*\*，然後按一下 [選取]\*\*\*\*，接著按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1156-129">Click **Members**, find and select **User 3**, and then click **Select**, and then click **Create**.</span></span>
5. <span data-ttu-id="a1156-130">關閉 [群組]\*\*\*\* 窗格。</span><span class="sxs-lookup"><span data-stu-id="a1156-130">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="a1156-131">在 [Azure Active Directory] 窗格中，按一下左側導覽的 [密碼重設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1156-131">In the Azure Active Directory pane, click **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="a1156-132">在 [密碼重設屬性]\*\*\*\* 窗格中，選擇 [已啟用自助式密碼重設]\*\*\*\* 選項底下的 [已選取]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1156-132">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="a1156-133">按一下 [選取群組]\*\*\*\*，選取 [PWReset]\*\*\*\* 群組，然後按一下 [選取] > [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1156-133">Click **Select group**, select the **PWReset** group, and then click **Select > Save**.</span></span>
9. <span data-ttu-id="a1156-134">關閉私用瀏覽器執行個體。</span><span class="sxs-lookup"><span data-stu-id="a1156-134">Close the private browser instance.</span></span>

<span data-ttu-id="a1156-135">下一階段，您將測試「使用者 3」帳戶的密碼重設。</span><span class="sxs-lookup"><span data-stu-id="a1156-135">Next, you test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="a1156-136">開啟新的私用瀏覽器執行個體，並瀏覽至 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)。</span><span class="sxs-lookup"><span data-stu-id="a1156-136">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="a1156-137">以「使用者 3」的認證登入。</span><span class="sxs-lookup"><span data-stu-id="a1156-137">Sign in with the User 3 account credentials.</span></span>
3. <span data-ttu-id="a1156-138">在 [需要更多資訊]\*\*\*\* 中按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1156-138">In **More information required**, click **Next**.</span></span> 
5. <span data-ttu-id="a1156-139">在 [避免您失去帳戶的存取權]\*\*\*\* 中，將認證電話設為您的手機號碼，並將認證電子郵件設為您的公司或個人電子郵件帳戶。</span><span class="sxs-lookup"><span data-stu-id="a1156-139">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
7. <span data-ttu-id="a1156-140">兩者皆經過驗證之後，按一下 [狀況良好]\*\*\*\*，並關閉瀏覽器的私用執行個體。</span><span class="sxs-lookup"><span data-stu-id="a1156-140">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
8. <span data-ttu-id="a1156-141">開啟新的私用瀏覽器執行個體並前往 [https://aka.ms/sspr](https://aka.ms/sspr)。</span><span class="sxs-lookup"><span data-stu-id="a1156-141">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
9. <span data-ttu-id="a1156-142">輸入「使用者 3」的帳戶名稱，輸入 CAPTCHA 顯示的字元，然後再按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1156-142">Type the User 3 account name, type the characters from the CAPTCHA, and then click **Next**.</span></span>
10. <span data-ttu-id="a1156-p102">對於 [驗證步驟 1]\*\*\*\*，請按一下 [寄電子郵件到我的備用電子郵件地址]\*\*\*\*，然後再按一下 [寄電子郵件]\*\*\*\*。當您收到電子郵件後，請輸入驗證碼，然後再按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1156-p102">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
11. <span data-ttu-id="a1156-145">在 [取回您的帳戶]\*\*\*\* 中，輸入「使用者 3」帳戶的新密碼，然後按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1156-145">In **Get back into your account**, type a new password for the User 3 account, and then click **Finish**.</span></span> <span data-ttu-id="a1156-146">請記下「使用者 3」帳戶變更的密碼，並儲存到安全的位置。</span><span class="sxs-lookup"><span data-stu-id="a1156-146">Note the changed password of the User 3 account and store it in a safe location.</span></span>
12. <span data-ttu-id="a1156-147">在相同瀏覽器的新分頁中，前往 [https://portal.office.com](https://portal.office.com)，並以「使用者 3」帳戶名稱及新密碼登入。</span><span class="sxs-lookup"><span data-stu-id="a1156-147">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="a1156-148">您應該會看到 [Microsoft Office 首頁]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="a1156-148">You should see the **Microsoft Office Home** page.</span></span>

<span data-ttu-id="a1156-149">如需在生產中進行密碼重設的相關資訊和連結，請參閱身分識別階段中的「[簡化密碼重設](identity-secure-your-passwords.md#identity-pw-reset)」步驟。</span><span class="sxs-lookup"><span data-stu-id="a1156-149">See the [Simplify password resets](identity-secure-your-passwords.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="a1156-150">下一步</span><span class="sxs-lookup"><span data-stu-id="a1156-150">Next step</span></span>

<span data-ttu-id="a1156-151">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="a1156-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1156-152">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a1156-152">See also</span></span>

[<span data-ttu-id="a1156-153">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="a1156-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a1156-154">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="a1156-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a1156-155">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="a1156-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
