---
title: 適用於 Microsoft 365 測試環境的密碼重設
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/30/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 摘要：設定並測試適用於 Microsoft 365 測試環境的密碼重設。
ms.openlocfilehash: a90cb362a2831bf0bcf3fe05932e3a4345d52b2e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866701"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="06401-103">適用於 Microsoft 365 測試環境的密碼重設</span><span class="sxs-lookup"><span data-stu-id="06401-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="06401-104">Azure AD 自助密碼重設 (SSPR) 允許使用者重設或解除鎖定其密碼或帳戶。</span><span class="sxs-lookup"><span data-stu-id="06401-104">Azure AD self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="06401-105">本文將以兩階段說明如何針對 Microsoft 365 測試環境，設定及測試密碼重設：</span><span class="sxs-lookup"><span data-stu-id="06401-105">This article describes how you can configure and test password resets in your Microsoft 365 test environment in two phases:</span></span>

1.  <span data-ttu-id="06401-106">使用密碼雜湊同步處理建立 Microsoft 365 模擬企業測試環境。</span><span class="sxs-lookup"><span data-stu-id="06401-106">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="06401-107">設定及測試「使用者 2」帳戶的密碼重設。</span><span class="sxs-lookup"><span data-stu-id="06401-107">Configure and test password reset for the User 2 account.</span></span>
    
![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="06401-109">按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="06401-109">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="06401-110">階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="06401-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="06401-p101">請遵循[適用於 Microsoft 365 的密碼雜湊同步處理](password-hash-sync-m365-ent-test-environment.md)中的指示。以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="06401-p101">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![使用傳遞驗證測試環境的模擬企業](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="06401-114">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="06401-114">This configuration consists of:</span></span> 
  
- <span data-ttu-id="06401-115">Office 365 E5 和 EMS E5 試用版或永久訂閱。</span><span class="sxs-lookup"><span data-stu-id="06401-115">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="06401-116">簡化的組織內部網域與網際網路的連線，由 Azure 虛擬網路的子網路上的 DC1、APP1 及 CLIENT1 虛擬機器組成</span><span class="sxs-lookup"><span data-stu-id="06401-116">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="06401-117">Azure AD Connect 在 APP1 上執行，以將 TESTLAB Windows Server AD 網域同步至 Office 365 和 EMS E5 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="06401-117">Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="phase-2-configure-and-test-password-reset"></a><span data-ttu-id="06401-118">階段 2：設定及測試密碼重設</span><span class="sxs-lookup"><span data-stu-id="06401-118">Phase 2: Configure and test password reset</span></span>

<span data-ttu-id="06401-119">在這個階段中，您會在透過群組成員資格在 Azure AD 租用戶中設定密碼重設，然後驗證是否運作正常。</span><span class="sxs-lookup"><span data-stu-id="06401-119">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="06401-120">首先，在特定 Azure AD 群組中啟用該帳戶的密碼重設。</span><span class="sxs-lookup"><span data-stu-id="06401-120">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="06401-121">從您瀏覽器的私用執行個體開啟 [https://portal.azure.com](https://portal.azure.com)，然後使用全域系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="06401-121">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="06401-122">在 Azure 入口網站中，按一下 [Azure Active Directory] > [群組] > [新增群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06401-122">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="06401-p102">將 [群組類型]\*\*\*\* 設為 [安全性]\*\*\*\*、[群族名稱]\*\*\*\* 設為 [PWReset]\*\*\*\*，以及將 [成員類型]\*\*\*\* 設為 [指派]\*\*\*\*，然後按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06401-p102">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**. Click **Create**.</span></span>
5. <span data-ttu-id="06401-125">在清單中按一下 [PWReset]\*\*\*\* 群組，然後再按一下 [成員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06401-125">Click the **PWReset** group in the list, and then click **Members**.</span></span>
6. <span data-ttu-id="06401-p103">按一下 [新增成員]\*\*\*\*、接著按一下 [使用者 2]\*\*\*\*，然後再按一下 [選取]\*\*\*\*。關閉 [PWReset]\*\*\*\* 及 [群組]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="06401-p103">Click **Add members**, click **User 2**, and then click **Select**. Close the **PWReset** and **Group** pages.</span></span>
7. <span data-ttu-id="06401-128">在 Azure Active Directory 頁面上，按一下 [密碼重設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06401-128">On the Azure Active Directory page, click **Password reset**.</span></span>
8. <span data-ttu-id="06401-129">在 [屬性]\*\*\*\* 頁面的 [啟用自助密碼重設]\*\*\*\* 下，選擇 [選取]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06401-129">From the **Properties** page, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
9. <span data-ttu-id="06401-130">在 [選取群組]\*\*\*\* 中，選取 [PWReset]\*\*\*\*，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06401-130">From **Select group**, select **PWReset**, and then click **Save**.</span></span>
10. <span data-ttu-id="06401-131">關閉私用瀏覽器執行個體。</span><span class="sxs-lookup"><span data-stu-id="06401-131">Close the private browser instance.</span></span>

<span data-ttu-id="06401-132">下一階段，您將測試「使用者 2」帳戶的密碼重設。</span><span class="sxs-lookup"><span data-stu-id="06401-132">Next, you test password reset for the User 2 account.</span></span>

1. <span data-ttu-id="06401-133">開啟新的私用瀏覽器執行個體，並瀏覽至 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)。</span><span class="sxs-lookup"><span data-stu-id="06401-133">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="06401-134">以「使用者 2」的認證登入。</span><span class="sxs-lookup"><span data-stu-id="06401-134">Sign in with the User 2 account credentials.</span></span>
3. <span data-ttu-id="06401-135">在 [避免您失去帳戶的存取權]\*\*\*\* 中，將認證電話設為您的手機號碼，並將認證電子郵件設為您的公司或個人電子郵件帳戶。</span><span class="sxs-lookup"><span data-stu-id="06401-135">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
4. <span data-ttu-id="06401-136">兩者皆經過驗證之後，按一下 [狀況良好]\*\*\*\*，並關閉瀏覽器的私用執行個體。</span><span class="sxs-lookup"><span data-stu-id="06401-136">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
5. <span data-ttu-id="06401-137">開啟新的私用瀏覽器執行個體並前往 [https://aka.ms/sspr](https://aka.ms/sspr)。</span><span class="sxs-lookup"><span data-stu-id="06401-137">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
6. <span data-ttu-id="06401-138">以「使用者 2」的帳戶認證登入，輸入 CAPTCHA 顯示的字元，然後再按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06401-138">Sign in with the User 2 account credentials, type the characters from the CAPTCHA, and then click **Next**.</span></span>
8. <span data-ttu-id="06401-p104">對於 [驗證步驟 1]\*\*\*\*，請按一下 [寄電子郵件到我的備用電子郵件地址]\*\*\*\*，然後再按一下 [寄電子郵件]\*\*\*\*。當您收到電子郵件後，請輸入驗證碼，然後再按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06401-p104">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
9. <span data-ttu-id="06401-p105">在 [取回您的帳戶]\*\*\*\* 中，輸入「使用者 2」帳戶的新密碼，然後按一下 [完成]\*\*\*\*。請記下「使用者 2」帳戶的密碼變更，並儲存到安全的位置。</span><span class="sxs-lookup"><span data-stu-id="06401-p105">In **Get back into your account**, type a new password for the User 2 account, and then click **Finish**. Note the changed password of the User 2 account and store it in a safe location.</span></span>
10. <span data-ttu-id="06401-p106">在相同瀏覽器的新分頁中，前往 [https://portal.office.com](https://portal.office.com)，並以「使用者 2」帳戶名稱及新密碼登入。您應該會看見 [Office 首頁]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="06401-p106">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 2 account name and its new password. You should see the **Office Home** page.</span></span>

<span data-ttu-id="06401-145">如需在生產中進行密碼重設的相關資訊和連結，請參閱身分識別階段中的「[簡化密碼重設](identity-password-reset.md)」步驟。</span><span class="sxs-lookup"><span data-stu-id="06401-145">See the [Simplify password resets](identity-password-reset.md) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="06401-146">下一步</span><span class="sxs-lookup"><span data-stu-id="06401-146">Next step</span></span>

<span data-ttu-id="06401-147">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="06401-147">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="06401-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="06401-148">See also</span></span>

[<span data-ttu-id="06401-149">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="06401-149">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="06401-150">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="06401-150">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="06401-151">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="06401-151">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
