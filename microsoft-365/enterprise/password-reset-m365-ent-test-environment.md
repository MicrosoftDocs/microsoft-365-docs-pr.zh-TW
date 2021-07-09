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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 摘要：設定並測試適用於 Microsoft 365 測試環境的密碼重設。
ms.openlocfilehash: 13169824866e91c1a09d412a875d2f4ce4391fa8
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339379"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="28936-103">適用於 Microsoft 365 測試環境的密碼重設</span><span class="sxs-lookup"><span data-stu-id="28936-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="28936-104">*此測試實驗室指南僅可用於企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="28936-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="28936-105">Azure Active Directory (Azure AD) 自助密碼重設 (SSPR) 允許使用者重設或解除鎖定其密碼或帳戶。</span><span class="sxs-lookup"><span data-stu-id="28936-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span>

<span data-ttu-id="28936-106">本文說明如何在 Microsoft 365 測試環境中設定及測試密碼重設。</span><span class="sxs-lookup"><span data-stu-id="28936-106">This article describes how to configure and test password resets in your Microsoft 365 test environment.</span></span>

<span data-ttu-id="28936-107">設定 SSPR 包含三個階段：</span><span class="sxs-lookup"><span data-stu-id="28936-107">Setting up SSPR involves three phases:</span></span>
- [<span data-ttu-id="28936-108">階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="28936-108">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="28936-109">階段 2：啟用密碼回寫</span><span class="sxs-lookup"><span data-stu-id="28936-109">Phase 2: Enable password writeback</span></span>](#phase-2-enable-password-writeback)
- [<span data-ttu-id="28936-110">階段 3：設定及測試密碼重設</span><span class="sxs-lookup"><span data-stu-id="28936-110">Phase 3: Configure and test password reset</span></span>](#phase-3-configure-and-test-password-reset)
    
![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="28936-112">如需適用于企業測試實驗室指南堆疊的 Microsoft 365 中的所有文章的視覺對應，請移至[Microsoft 365 for enterprise test lab guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="28936-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="28936-113">階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="28936-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="28936-114">首先，依照 [ [密碼雜湊同步](password-hash-sync-m365-ent-test-environment.md)處理] 中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="28936-114">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="28936-115">您產生的設定如下所示：</span><span class="sxs-lookup"><span data-stu-id="28936-115">Your resulting configuration looks like this:</span></span>
  
![使用密碼雜湊同步處理測試環境的模擬企業](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="28936-117">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="28936-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="28936-118">Microsoft 365 E5 試用版或付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="28936-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="28936-119">簡化的組織內部網路連接至網際網路，由 Azure 虛擬網路子網上的 DC1、APP1 和 CLIENT1 虛擬機器所組成。</span><span class="sxs-lookup"><span data-stu-id="28936-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="28936-120">Azure AD Connect 會在 APP1 上執行，以將 TESTLAB Active Directory Domain Services (AD DS) 網域同步至 Microsoft 365 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="28936-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="28936-121">階段 2：啟用密碼回寫</span><span class="sxs-lookup"><span data-stu-id="28936-121">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="28936-122">遵循[測試實驗室指南密碼回寫階段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="28936-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="28936-123">您必須啟用密碼回寫才能使用密碼重設。</span><span class="sxs-lookup"><span data-stu-id="28936-123">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="28936-124">階段 3：設定及測試密碼重設</span><span class="sxs-lookup"><span data-stu-id="28936-124">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="28936-125">在此階段中，在 Azure AD 租使用者中透過群組成員資格來設定密碼重設，然後驗證它是否運作正常。</span><span class="sxs-lookup"><span data-stu-id="28936-125">In this phase, configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="28936-126">首先，在特定 Azure AD 群組中啟用該帳戶的密碼重設。</span><span class="sxs-lookup"><span data-stu-id="28936-126">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="28936-127">從您瀏覽器的私用執行個體開啟 [https://portal.azure.com](https://portal.azure.com)，然後使用全域系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="28936-127">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="28936-128">在 Azure 入口網站中，選取 [ **Azure Active Directory**  >  **群組**] [  >  **新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="28936-128">In the Azure portal, select **Azure Active Directory** > **Groups** > **New group**.</span></span>
3. <span data-ttu-id="28936-129">將 [群組類型] 設為 [安全性]、[群組名稱] 設為 [PWReset]，以及將 [成員類型] 設為 [指派]。</span><span class="sxs-lookup"><span data-stu-id="28936-129">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span>
4. <span data-ttu-id="28936-130">選取 [ **成員**]，尋找並選取 [ **使用者 3**]，選取 [ **選取**]，然後選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="28936-130">Select **Members**, find and select **User 3**, select **Select**, and then select **Create**.</span></span>
5. <span data-ttu-id="28936-131">關閉 [群組] 窗格。</span><span class="sxs-lookup"><span data-stu-id="28936-131">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="28936-132">在 [Azure Active Directory] 窗格中，選取左側導覽中的 [**密碼重設**]。</span><span class="sxs-lookup"><span data-stu-id="28936-132">In the Azure Active Directory pane, select **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="28936-133">在 [密碼重設屬性] 窗格中，選擇 [已啟用自助式密碼重設] 選項底下的 [已選取]。</span><span class="sxs-lookup"><span data-stu-id="28936-133">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="28936-134">選取 [**選取群組**]，選取 [ **PWReset** ] 群組，然後選取 [**選取**  >  **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="28936-134">Select **Select group**, select the **PWReset** group, and then select **Select** > **Save**.</span></span>
9. <span data-ttu-id="28936-135">關閉私用瀏覽器執行個體。</span><span class="sxs-lookup"><span data-stu-id="28936-135">Close the private browser instance.</span></span>

<span data-ttu-id="28936-136">下一步，針對使用者3帳戶測試密碼重設。</span><span class="sxs-lookup"><span data-stu-id="28936-136">Next, test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="28936-137">開啟新的私用瀏覽器執行個體，並瀏覽至 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)。</span><span class="sxs-lookup"><span data-stu-id="28936-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
1. <span data-ttu-id="28936-138">以「使用者 3」的認證登入。</span><span class="sxs-lookup"><span data-stu-id="28936-138">Sign in with the User 3 account credentials.</span></span>
1. <span data-ttu-id="28936-139">在 [ **需要詳細資訊**] 中，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="28936-139">In **More information required**, select **Next**.</span></span> 
1. <span data-ttu-id="28936-140">在 [避免您失去帳戶的存取權] 中，將認證電話設為您的手機號碼，並將認證電子郵件設為您的公司或個人電子郵件帳戶。</span><span class="sxs-lookup"><span data-stu-id="28936-140">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
1. <span data-ttu-id="28936-141">驗證兩者後，選取 [ **看起來不錯**]，然後關閉瀏覽器的私人實例。</span><span class="sxs-lookup"><span data-stu-id="28936-141">After both are verified, select **Looks good**, and then close the private instance of the browser.</span></span>
1. <span data-ttu-id="28936-142">在新的私用瀏覽器實例中，移至 [https://aka.ms/sspr](https://aka.ms/sspr) 。</span><span class="sxs-lookup"><span data-stu-id="28936-142">In a new private browser instance, go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
1. <span data-ttu-id="28936-143">輸入使用者3帳戶名稱，並輸入 CAPTCHA 中的字元，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="28936-143">Enter the User 3 account name, enter the characters from the CAPTCHA, and then select **Next**.</span></span>
1. <span data-ttu-id="28936-144">若要 **驗證步驟 1**，請選取 [ **電子郵件我的備選電子郵件**]，然後選取 [ **電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="28936-144">For **verification step 1**, select **Email my alternate email**, and then select **Email**.</span></span> <span data-ttu-id="28936-145">當您收到電子郵件時，請輸入驗證碼，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="28936-145">When you receive the email, enter the verification code, and then select **Next**.</span></span>
1. <span data-ttu-id="28936-146">在 [ **回到您的帳戶**] 中，輸入使用者3帳戶的新密碼，然後選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="28936-146">In **Get back into your account**, enter a new password for the User 3 account, and then select **Finish**.</span></span> <span data-ttu-id="28936-147">請記下「使用者 3」帳戶變更的密碼，並儲存到安全的位置。</span><span class="sxs-lookup"><span data-stu-id="28936-147">Note the changed password of the User 3 account and store it in a safe location.</span></span>
1. <span data-ttu-id="28936-148">在相同瀏覽器的新分頁中，前往 [https://admin.microsoft.com](https://admin.microsoft.com)，並以「使用者 3」帳戶名稱及新密碼登入。</span><span class="sxs-lookup"><span data-stu-id="28936-148">In a separate tab of the same browser, go to [https://admin.microsoft.com](https://admin.microsoft.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="28936-149">您應該會看到 [Microsoft Office 首頁] 頁面。</span><span class="sxs-lookup"><span data-stu-id="28936-149">You should see the **Microsoft Office Home** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="28936-150">下一步</span><span class="sxs-lookup"><span data-stu-id="28936-150">Next step</span></span>

<span data-ttu-id="28936-151">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="28936-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="28936-152">另請參閱</span><span class="sxs-lookup"><span data-stu-id="28936-152">See also</span></span>

[<span data-ttu-id="28936-153">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="28936-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="28936-154">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="28936-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="28936-155">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="28936-155">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)