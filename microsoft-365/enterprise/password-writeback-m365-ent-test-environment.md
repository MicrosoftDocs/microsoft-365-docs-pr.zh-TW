---
title: 適用於 Microsoft 365 測試環境的密碼回寫
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
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
description: 摘要：設定適用於 Microsoft 365 測試環境的密碼回寫。
ms.openlocfilehash: e2ccbe251c4e62790331b949f163816f789436cb
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291448"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a450f-103">適用於 Microsoft 365 測試環境的密碼回寫</span><span class="sxs-lookup"><span data-stu-id="a450f-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a450f-p101">密碼回寫能讓使用者透過 Azure Active Directory (Azure AD) 更新密碼，然後系統會將密碼複寫到本機 Active Directory Domain Services (AD DS)。使用密碼回寫，使用者不需要透過內部部署的 Active Directory Domain Services (AD DS) (其原始使用者帳戶儲存於此) 更新他們的密碼。這對於漫遊或遠端使用者非常有幫助，因為他們無法遠端存取內部部署網路。</span><span class="sxs-lookup"><span data-stu-id="a450f-p101">Password writeback allows users to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS). With password writeback, users don’t need to update their passwords through the on-premises Active Directory Domain Services (AD DS) where their original user accounts are stored. This helps roaming or remote users who do not have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="a450f-107">本文說明如何設定您的 Microsoft 365 測試環境以進行密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="a450f-107">This article describes how you can configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="a450f-108">此測試環境的設定分為兩個階段︰</span><span class="sxs-lookup"><span data-stu-id="a450f-108">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="a450f-109">使用密碼雜湊同步處理建立 Microsoft 365 模擬企業測試環境。</span><span class="sxs-lookup"><span data-stu-id="a450f-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="a450f-110">啟用適用於 TESTLAB AD DS 網域的密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="a450f-110">Enable password writeback for the TESTLAB AD DS domain.</span></span>
    
![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a450f-112">按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="a450f-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a450f-113">階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="a450f-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a450f-p102">首先，請遵循[密碼雜湊同步處理](password-hash-sync-m365-ent-test-environment.md)中的指示。以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="a450f-p102">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![使用密碼雜湊同步處理測試環境的模擬企業](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="a450f-117">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="a450f-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="a450f-118">Office 365 E5 和 EMS E5 試用版或付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="a450f-118">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="a450f-119">簡化的組織內部網域與網際網路的連線，由 Azure 虛擬網路的子網路上的 DC1、APP1 及 CLIENT1 虛擬機器組成</span><span class="sxs-lookup"><span data-stu-id="a450f-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="a450f-120">Azure AD Connect 在 APP1 上執行，以將 TESTLAB AD DS 網域同步至 Office 365 和 EMS E5 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="a450f-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="a450f-121">階段 2：啟用適用於 TESTLAB AD DS 網域的密碼回寫</span><span class="sxs-lookup"><span data-stu-id="a450f-121">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="a450f-122">首先，使用全域系統管理員角色設定使用者 1 帳戶。</span><span class="sxs-lookup"><span data-stu-id="a450f-122">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="a450f-123">從 [Office 入口網站](https://office.com)，以您的全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="a450f-123">From the [Office portal](https://office.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="a450f-p103">按一下 [系統管理員]\*\*\*\* 磚。在瀏覽器的新 [Microsoft 365 系統管理中心]\*\*\*\* 索引標籤上，按一下[作用中使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a450f-p103">Click the **Admin** tile. From the new **Microsoft 365 admin center** tab of your browser, click **Active users**.</span></span>
 
3. <span data-ttu-id="a450f-126">在 [作用中使用者]\*\*\*\* 頁面上，按一下 [user1]\*\*\*\* 帳戶。</span><span class="sxs-lookup"><span data-stu-id="a450f-126">On the **Active users** page, click the **user1** account,</span></span>

4. <span data-ttu-id="a450f-127">在 [user1]\*\*\*\* 窗格中，按一下 [角色]\*\*\*\* 旁的 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a450f-127">On the **user1** pane, click **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="a450f-p104">在 user1 的 [編輯使用者角色]\*\*\*\* 窗格中，按一下 [全域系統管理員]\*\*\*\*。按一下 [儲存]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a450f-p104">On the **Edit user roles** pane for user1, click **Global administrator**. Click **Save**, and then click **Close**.</span></span>

<span data-ttu-id="a450f-130">接下來，使用安全性設定來配置使用者 1 帳戶，該安全性設定允許其代表 TESTLAB AD DS 網域中的其他使用者變更密碼。。</span><span class="sxs-lookup"><span data-stu-id="a450f-130">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="a450f-131">從 [Azure 入口網站](https://portal.azure.com)，以您的全域管理員帳戶登入，然後以 TESTLAB\User1 帳戶連線到 APP1。</span><span class="sxs-lookup"><span data-stu-id="a450f-131">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="a450f-132">從 APP1 的桌面，按一下 [開始]\*\*\*\*，輸入 [Active]\*\*\*\*，然後按一下 [Active Directory 使用者及電腦]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a450f-132">From the desktop of APP1, click **Start**, type **active**, and then click **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="a450f-p105">按一下功能表列中的 [檢視]\*\*\*\*。如果**進階功能**未啟用，請按一下以啟用。</span><span class="sxs-lookup"><span data-stu-id="a450f-p105">Click **View** in the menu bar. If **Advanced features** is not enabled, click it to enable it.</span></span>

4. <span data-ttu-id="a450f-135">在樹狀窗格中，以滑鼠右鍵按一下您的網域，按一下 [內容]\*\*\*\*，然後按一下 [安全性]\*\*\*\* 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a450f-135">In the tree pane, right-click your domain, click **Properties**, and then click the **Security** tab.</span></span>

5. <span data-ttu-id="a450f-136">按一下 [進階]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a450f-136">Click **Advanced**.</span></span>

6. <span data-ttu-id="a450f-137">在 [使用權限]\*\*\*\* 索引標籤上，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a450f-137">On the **Permissions** tab, click **Add**.</span></span>

7. <span data-ttu-id="a450f-138">按一下 [選取主體]\*\*\*\*，輸入 [User1]\*\*\*\*，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a450f-138">Click **Select a principal**, type **User1**, and then click **OK**.</span></span>

8. <span data-ttu-id="a450f-139">在 [適用於]\*\*\*\* 中，選取 [子系使用者物件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a450f-139">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="a450f-140">在 [使用權限]\*\*\*\* 下，選取下列動作：</span><span class="sxs-lookup"><span data-stu-id="a450f-140">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="a450f-141">變更密碼</span><span class="sxs-lookup"><span data-stu-id="a450f-141">Change password</span></span>
    - <span data-ttu-id="a450f-142">重設密碼</span><span class="sxs-lookup"><span data-stu-id="a450f-142">Reset password</span></span>

10. <span data-ttu-id="a450f-143">在 [內容]\*\*\*\* 下，選取下列動作：</span><span class="sxs-lookup"><span data-stu-id="a450f-143">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="a450f-144">撰寫 lockoutTime</span><span class="sxs-lookup"><span data-stu-id="a450f-144">Write lockoutTime</span></span>
    - <span data-ttu-id="a450f-145">撰寫 pwdLastSet</span><span class="sxs-lookup"><span data-stu-id="a450f-145">Write pwdLastSet</span></span>

11. <span data-ttu-id="a450f-146">按三次 [確定]\*\*\*\* 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="a450f-146">Click **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="a450f-147">關閉 [Active Directory 使用者及電腦]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a450f-147">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="a450f-148">接著，在 APP1 上設定 Azure AD Connect 以進行密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="a450f-148">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="a450f-149">如有需要，請以 TESTLAB\User1 帳戶連線至 APP1。</span><span class="sxs-lookup"><span data-stu-id="a450f-149">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="a450f-150">從 APP1 的桌面，按兩下 [Azure AD Connect]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a450f-150">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="a450f-151">在 [歡迎]\*\*\*\* 頁面上，按一下 [設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a450f-151">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="a450f-152">在 [其他工作] \*\*\*\* 頁面，按一下 [自訂同步處理選項]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a450f-152">On the **Additional tasks** page, click **Customize synchronization options**, and then click **Next**.</span></span>

5. <span data-ttu-id="a450f-153">在 [連線到 Azure AD]\*\*\*\* 頁面上，輸入您的全域管理員帳戶認證，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a450f-153">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="a450f-154">在 [連線目錄]\*\*\*\* 和 [網域/OU]\*\* 篩選\*\*頁面上，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a450f-154">On the **Connect directories** and **Domain/OU filtering** pages, click **Next**.</span></span>

7. <span data-ttu-id="a450f-155">在 [選擇性功能]\*\*\*\* 頁面上，選取 [密碼回寫]\*\*\*\*，並按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a450f-155">On the **Optional features** page, select **Password writeback** and click **Next**.</span></span> 

8. <span data-ttu-id="a450f-156">在 [已可設定]\*\*\*\* 頁面上，按一下 [設定]\*\*\*\* 並等待程序完成。</span><span class="sxs-lookup"><span data-stu-id="a450f-156">On the **Ready to configure** page, click **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="a450f-157">當您看到設定完成時，請按一下 [結束]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a450f-157">When you see the configuration finish, click **Exit**.</span></span>

<span data-ttu-id="a450f-158">您現在可以為電腦 (未連線至模擬內部網路的虛擬網路) 上的使用者測試密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="a450f-158">You are now ready to test password writeback for users on computers that are not connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="a450f-159">以下是您產生的組態：</span><span class="sxs-lookup"><span data-stu-id="a450f-159">Here is your resulting configuration:</span></span>

![使用傳遞驗證測試環境的模擬企業](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="a450f-161">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="a450f-161">This configuration consists of:</span></span>

- <span data-ttu-id="a450f-162">已註冊 DNS 網域 TESTLAB.\<您的網域名稱> 的 Office 365 E5 和 EMS E5 試用版或付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="a450f-162">Office 365 E5 and EMS E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="a450f-163">簡化的組織內部網域與網際網路的連線，由 Azure 虛擬網路的子網路上的 DC1、APP1 及 CLIENT1 虛擬機器組成</span><span class="sxs-lookup"><span data-stu-id="a450f-163">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="a450f-164">Azure AD Connect 在 APP1 上執行，以將來自 Office 365 和 EMS E5 訂閱之 Azure AD 租用戶的帳戶和群組清單同步至 TESTLAB AD DS 網域。</span><span class="sxs-lookup"><span data-stu-id="a450f-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Office 365 and EMS E5 subscriptions to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="a450f-165">密碼回寫已啟用，因此使用者可以透過 Azure AD 變更其密碼，而不需要連線到簡化的內部網路。</span><span class="sxs-lookup"><span data-stu-id="a450f-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

<span data-ttu-id="a450f-166">如需在生產中進行密碼回寫的相關資訊和連結，請參閱身分識別階段中的「[簡化密碼更新](identity-password-reset.md#identity-pw-writeback)」步驟。</span><span class="sxs-lookup"><span data-stu-id="a450f-166">See the [Simplify password updates](identity-password-reset.md#identity-pw-writeback) step in the Identity phase for information and links to configure password writeback in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="a450f-167">下一步</span><span class="sxs-lookup"><span data-stu-id="a450f-167">Next step</span></span>

<span data-ttu-id="a450f-168">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="a450f-168">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a450f-169">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a450f-169">See also</span></span>

[<span data-ttu-id="a450f-170">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="a450f-170">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a450f-171">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="a450f-171">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a450f-172">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="a450f-172">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


