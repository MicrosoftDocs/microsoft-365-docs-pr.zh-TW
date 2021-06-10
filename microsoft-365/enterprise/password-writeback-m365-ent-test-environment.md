---
title: 適用於 Microsoft 365 測試環境的密碼回寫
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: 摘要：設定適用於 Microsoft 365 測試環境的密碼回寫。
ms.openlocfilehash: f1118c22ad1f65ea29bb14afacb7506a60d1fe1a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921477"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="79d66-103">適用於 Microsoft 365 測試環境的密碼回寫</span><span class="sxs-lookup"><span data-stu-id="79d66-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="79d66-104">*此測試實驗室指南僅可用於企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="79d66-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="79d66-105">使用者可以使用密碼寫回來更新其密碼，Azure Active Directory (Azure AD) ，然後將其複寫到您的本機 Active Directory 網域服務 (AD DS) 。</span><span class="sxs-lookup"><span data-stu-id="79d66-105">Users can use password writeback to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="79d66-106">使用密碼回寫時，使用者不必透過內部部署 AD DS （儲存其原始使用者帳戶）來更新其密碼。</span><span class="sxs-lookup"><span data-stu-id="79d66-106">With password writeback, users don't have to update their passwords through the on-premises AD DS where their original user accounts are stored.</span></span> <span data-ttu-id="79d66-107">這可協助漫遊或遠端使用者沒有其內部部署網路的遠端存取連線。</span><span class="sxs-lookup"><span data-stu-id="79d66-107">This helps roaming or remote users who don't have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="79d66-108">本文說明如何設定 Microsoft 365 測試環境，以進行密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="79d66-108">This article describes how to configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="79d66-109">設定密碼寫回的測試環境包括兩個階段：</span><span class="sxs-lookup"><span data-stu-id="79d66-109">Configuring your test environment for password writeback involves two phases:</span></span>
- [<span data-ttu-id="79d66-110">階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="79d66-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="79d66-111">階段 2：啟用適用於 TESTLAB AD DS 網域的密碼回寫</span><span class="sxs-lookup"><span data-stu-id="79d66-111">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="79d66-113">如需適用于企業測試實驗室指南堆疊的 Microsoft 365 中的所有文章的視覺對應，請移至[Microsoft 365 for enterprise test lab guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="79d66-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="79d66-114">階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="79d66-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="79d66-115">首先，依照 [ [密碼雜湊同步](password-hash-sync-m365-ent-test-environment.md)處理] 中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="79d66-115">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="79d66-116">您產生的設定如下所示：</span><span class="sxs-lookup"><span data-stu-id="79d66-116">Your resulting configuration looks like this:</span></span>
  
![使用密碼雜湊同步處理測試環境的模擬企業](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="79d66-118">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="79d66-118">This configuration consists of:</span></span>
  
- <span data-ttu-id="79d66-119">Microsoft 365 E5 試用版或付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="79d66-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="79d66-120">簡化的組織內部網路連接至網際網路，由 Azure 虛擬網路子網上的 DC1、APP1 和 CLIENT1 虛擬機器所組成。</span><span class="sxs-lookup"><span data-stu-id="79d66-120">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="79d66-121">Azure AD Connect 會在 APP1 上執行，以將 TESTLAB AD DS 網域同步至 Microsoft 365 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="79d66-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="79d66-122">階段 2：啟用適用於 TESTLAB AD DS 網域的密碼回寫</span><span class="sxs-lookup"><span data-stu-id="79d66-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="79d66-123">首先，使用全域系統管理員角色設定使用者 1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="79d66-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="79d66-124">從 [Microsoft 365 系統管理中心](https://portal.microsoft.com)，使用您的全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="79d66-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="79d66-125">選取 [作用中 **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="79d66-125">Select **Active users**.</span></span>
 
3. <span data-ttu-id="79d66-126">在 [作用中 **使用者** ] 頁面上，選取 [ **user1** ] 帳戶。</span><span class="sxs-lookup"><span data-stu-id="79d66-126">On the **Active users** page, select the **user1** account,</span></span>

4. <span data-ttu-id="79d66-127">在 [ **user1** ] 窗格中，選取 [**角色**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="79d66-127">On the **user1** pane, select **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="79d66-128">在 [ **編輯使用者角色** ] 窗格的 user1 上，選取 [ **全域管理員**]，然後選取 [ **儲存**]，然後選取 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="79d66-128">On the **Edit user roles** pane for user1, select **Global administrator**, select **Save**, and then select **Close**.</span></span>

<span data-ttu-id="79d66-129">接下來，使用安全性設定來配置使用者 1 帳戶，該安全性設定允許其代表 TESTLAB AD DS 網域中的其他使用者變更密碼。</span><span class="sxs-lookup"><span data-stu-id="79d66-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="79d66-130">從 [Azure 入口網站](https://portal.azure.com)，以您的全域管理員帳戶登入，然後以 TESTLAB\User1 帳戶連線到 APP1。</span><span class="sxs-lookup"><span data-stu-id="79d66-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="79d66-131">從 APP1 的桌面，選取 [ **開始**]，輸入 [ **active**]，然後選取 [ **active Directory 使用者和電腦**]。</span><span class="sxs-lookup"><span data-stu-id="79d66-131">From the desktop of APP1, select **Start**, enter **active**, and then select **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="79d66-132">在功能表列上，選取 [ **View**]。</span><span class="sxs-lookup"><span data-stu-id="79d66-132">On the menu bar, select **View**.</span></span> <span data-ttu-id="79d66-133">若未啟用 [ **高級功能** ]，請將其選取加以啟用。</span><span class="sxs-lookup"><span data-stu-id="79d66-133">If **Advanced features** is not enabled, select it to enable it.</span></span>

4. <span data-ttu-id="79d66-134">在樹狀窗格中，選取並按住 (，或以滑鼠右鍵按一下 [) 您的網域 **]，然後選取 [** 內容]，然後選取 [ **安全性** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="79d66-134">In the tree pane, select and hold (or right-click) your domain, select **Properties**, and then select the **Security** tab.</span></span>

5. <span data-ttu-id="79d66-135">選取 [ **高級**]。</span><span class="sxs-lookup"><span data-stu-id="79d66-135">Select **Advanced**.</span></span>

6. <span data-ttu-id="79d66-136">在 [ **許可權** ] 索引標籤上，選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="79d66-136">On the **Permissions** tab, select **Add**.</span></span>

7. <span data-ttu-id="79d66-137">選取 [ **選取主體**]，輸入 [ **User1**]，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79d66-137">Select **Select a principal**, enter **User1**, and then select **OK**.</span></span>

8. <span data-ttu-id="79d66-138">在 [適用於] 中，選取 [子系使用者物件]。</span><span class="sxs-lookup"><span data-stu-id="79d66-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="79d66-139">在 [使用權限] 下，選取下列動作：</span><span class="sxs-lookup"><span data-stu-id="79d66-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="79d66-140">**變更密碼**</span><span class="sxs-lookup"><span data-stu-id="79d66-140">**Change password**</span></span>
    - <span data-ttu-id="79d66-141">**重設密碼**</span><span class="sxs-lookup"><span data-stu-id="79d66-141">**Reset password**</span></span>

10. <span data-ttu-id="79d66-142">在 [內容] 下，選取下列動作：</span><span class="sxs-lookup"><span data-stu-id="79d66-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="79d66-143">**撰寫 lockoutTime**</span><span class="sxs-lookup"><span data-stu-id="79d66-143">**Write lockoutTime**</span></span>
    - <span data-ttu-id="79d66-144">**撰寫 pwdLastSet**</span><span class="sxs-lookup"><span data-stu-id="79d66-144">**Write pwdLastSet**</span></span>

11. <span data-ttu-id="79d66-145">選取 **[確定]** 三次，以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="79d66-145">Select **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="79d66-146">關閉 [Active Directory 使用者及電腦]。</span><span class="sxs-lookup"><span data-stu-id="79d66-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="79d66-147">接著，在 APP1 上設定 Azure AD Connect 以進行密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="79d66-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="79d66-148">如有需要，請以 TESTLAB\User1 帳戶連線至 APP1。</span><span class="sxs-lookup"><span data-stu-id="79d66-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="79d66-149">從 APP1 的桌面，按兩下 [Azure AD Connect]。</span><span class="sxs-lookup"><span data-stu-id="79d66-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="79d66-150">在 [ **歡迎] 頁面** 上，選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="79d66-150">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="79d66-151">在 [ **其他** 工作] 頁面上，選取 [ **自訂同步處理選項**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="79d66-151">On the **Additional tasks** page, select **Customize synchronization options**, and then select **Next**.</span></span>

5. <span data-ttu-id="79d66-152">在 [**連線至 Azure AD** ] 頁面上，輸入您的全域系統管理員帳號憑證，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="79d66-152">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="79d66-153">在 [**連線目錄**] 和 [**網域/OU 篩選**] 頁面上，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="79d66-153">On the **Connect directories** and **Domain/OU filtering** pages, select **Next**.</span></span>

7. <span data-ttu-id="79d66-154">在 [ **選用功能** ] 頁面上，選取 [ **密碼回寫**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="79d66-154">On the **Optional features** page, select **Password writeback**, and then select **Next**.</span></span>

8. <span data-ttu-id="79d66-155">在 [ **準備設定** ] 頁面上，選取 [ **設定** 並等候處理常式完成]。</span><span class="sxs-lookup"><span data-stu-id="79d66-155">On the **Ready to configure** page, select **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="79d66-156">當您看到設定完成時，請 **選取 [** 結束]。</span><span class="sxs-lookup"><span data-stu-id="79d66-156">When you see the configuration finish, select **Exit**.</span></span>

<span data-ttu-id="79d66-157">您現在可以為未連線到模擬內部網路之虛擬網路的電腦上的使用者測試密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="79d66-157">You are now ready to test password writeback for users on computers that aren't connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="79d66-158">您產生的設定如下所示：</span><span class="sxs-lookup"><span data-stu-id="79d66-158">Your resulting configuration looks like this:</span></span>

![使用傳遞驗證測試環境的模擬企業](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="79d66-160">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="79d66-160">This configuration consists of:</span></span>

- <span data-ttu-id="79d66-161">使用 DNS 網域 TESTLAB 的 Microsoft 365 E5 試用版或付費訂閱。\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="79d66-161">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<*your domain name*></span></span> <span data-ttu-id="79d66-162">註冊。</span><span class="sxs-lookup"><span data-stu-id="79d66-162">registered.</span></span>
- <span data-ttu-id="79d66-163">簡化的組織內部網路連接至網際網路，由 Azure 虛擬網路子網上的 DC1、APP1 和 CLIENT1 虛擬機器所組成。</span><span class="sxs-lookup"><span data-stu-id="79d66-163">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="79d66-164">Azure AD Connect 會在 APP1 上執行，以將來自 Microsoft 365 訂閱之 Azure AD 租用戶的帳戶和群組清單同步至 TESTLAB AD DS 網域。</span><span class="sxs-lookup"><span data-stu-id="79d66-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="79d66-165">密碼回寫已啟用，因此使用者可以透過 Azure AD 變更其密碼，而不需要連線到簡化的內部網路。</span><span class="sxs-lookup"><span data-stu-id="79d66-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="79d66-166">下一步</span><span class="sxs-lookup"><span data-stu-id="79d66-166">Next step</span></span>

<span data-ttu-id="79d66-167">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="79d66-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="79d66-168">另請參閱</span><span class="sxs-lookup"><span data-stu-id="79d66-168">See also</span></span>

[<span data-ttu-id="79d66-169">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="79d66-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="79d66-170">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="79d66-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="79d66-171">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="79d66-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)