---
title: 適用於 Office 365 測試環境的密碼雜湊同步處理
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 摘要：為您的 Office 365 測試環境設定及示範密碼雜湊同步處理並且登入。
ms.openlocfilehash: 2d5fbd3ed2a2afb994fc36f5ba3a15a8c55a274e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819385"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="58e93-103">適用於 Office 365 測試環境的密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="58e93-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="58e93-104">*這個測試實驗室指南可用於 Microsoft 365 企業版和 Office 365 企業版兩種測試環境。*</span><span class="sxs-lookup"><span data-stu-id="58e93-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="58e93-105">許多組織使用 Azure AD Connect 和密碼雜湊同步處理，將其內部部署 Active Directory Domain Services (AD DS) 樹系中的帳戶集同步處理至 Microsoft 365 訂閱的 Azure AD 租用戶帳戶集。</span><span class="sxs-lookup"><span data-stu-id="58e93-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> <span data-ttu-id="58e93-106">本文說明如何將密碼雜湊同步處理新增至 Office 365 測試環境，進而產生下列組態：</span><span class="sxs-lookup"><span data-stu-id="58e93-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, resulting in the following configuration:</span></span>
  
![使用密碼雜湊同步處理測試環境的模擬企業](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="58e93-108">設定此測試環境有兩個主要階段︰</span><span class="sxs-lookup"><span data-stu-id="58e93-108">There are two phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="58e93-109">建立 Microsoft 365 模擬企業測試環境。</span><span class="sxs-lookup"><span data-stu-id="58e93-109">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2. <span data-ttu-id="58e93-110">在 APP1 上安裝及設定 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="58e93-110">Install and configure Azure AD Connect on APP1.</span></span>
    
> [!TIP]
> <span data-ttu-id="58e93-111">如需 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應，請移至 [Microsoft 365 企業測試實驗室指南堆疊](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="58e93-111">Go to [Microsoft 365 Enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="58e93-112">階段 1：建立 Microsoft 365 模擬企業測試環境</span><span class="sxs-lookup"><span data-stu-id="58e93-112">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="58e93-113">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="58e93-113">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="58e93-114">Here is your resulting configuration.</span><span class="sxs-lookup"><span data-stu-id="58e93-114">Here is your resulting configuration.</span></span>
  
![模擬企業基本設定](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="58e93-116">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="58e93-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="58e93-117">Microsoft 365 E5 或 Office 365 E5 試用版或付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="58e93-117">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="58e93-118">簡化的組織內部網域與網際網路的連線，由 Azure 虛擬網路中的 DC1、APP1 及 CLIENT1 虛擬機器組成。</span><span class="sxs-lookup"><span data-stu-id="58e93-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="58e93-119">DC1 是 testlab 的網域控制站。\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="58e93-119">DC1 is a domain controller for the testlab.\<your public domain name></span></span> <span data-ttu-id="58e93-120">AD DS 網域。</span><span class="sxs-lookup"><span data-stu-id="58e93-120">AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="58e93-121">階段 2：建立及註冊 testlab 網域</span><span class="sxs-lookup"><span data-stu-id="58e93-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="58e93-122">在這個階段，您會新增公用 DNS 網域並將它新增至您的訂閱。</span><span class="sxs-lookup"><span data-stu-id="58e93-122">In this phase you add a public DNS domain and add it to your subscription.</span></span>

<span data-ttu-id="58e93-123">首先，請使用您的公用 DNS 註冊提供者，根據您目前的網域名稱建立新的公用 DNS 網域名稱，並將它新增至您的訂閱。</span><span class="sxs-lookup"><span data-stu-id="58e93-123">First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your subscription.</span></span> <span data-ttu-id="58e93-124">我們建議您使用名稱 **testlab.**\<your public domain>。</span><span class="sxs-lookup"><span data-stu-id="58e93-124">We recommend using the name **testlab.**\<your public domain>.</span></span> <span data-ttu-id="58e93-125">例如，如果您的公用網域名稱是 **<span>contoso</span>.com**，請新增公用網域名稱 **<span>testlab</span>.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="58e93-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="58e93-126">接下來，您要新增 **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="58e93-126">Next, you add the **testlab.**\<your public domain></span></span> <span data-ttu-id="58e93-127">網域至您的 Microsoft 365 或 Office 365 試用版或付費訂閱版，請瀏覽網域註冊程式。</span><span class="sxs-lookup"><span data-stu-id="58e93-127">domain to your Microsoft 365 or Office 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="58e93-128">這包括將其他 DNS 記錄新增至 **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="58e93-128">This consists of adding additional DNS records to the **testlab.**\<your public domain></span></span> <span data-ttu-id="58e93-129">網域。</span><span class="sxs-lookup"><span data-stu-id="58e93-129">domain.</span></span> <span data-ttu-id="58e93-130">如需詳細資訊，請參閱[新增網域至 Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain)。</span><span class="sxs-lookup"><span data-stu-id="58e93-130">For more information, see [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain).</span></span> 

<span data-ttu-id="58e93-131">以下是產生的組態。</span><span class="sxs-lookup"><span data-stu-id="58e93-131">Here is your resulting configuration.</span></span>
  
![testlab 網域名稱註冊](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="58e93-133">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="58e93-133">This configuration consists of:</span></span>

- <span data-ttu-id="58e93-134">Microsoft 365 E5 或 Office 365 E5 試用版或付費訂閱版，其包含有 DNS 網域 testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="58e93-134">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your public domain name></span></span> <span data-ttu-id="58e93-135">註冊。</span><span class="sxs-lookup"><span data-stu-id="58e93-135">registered.</span></span>
- <span data-ttu-id="58e93-136">簡化的組織內部網域與網際網路的連線，由 Azure 虛擬網路的子網路上的 DC1、APP1 及 CLIENT1 虛擬機器組成</span><span class="sxs-lookup"><span data-stu-id="58e93-136">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="58e93-137">請注意 testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="58e93-137">Notice how the testlab.\<your public domain name></span></span> <span data-ttu-id="58e93-138">現在如何：</span><span class="sxs-lookup"><span data-stu-id="58e93-138">is now:</span></span>

- <span data-ttu-id="58e93-139">由公用 DNS 記錄支援。</span><span class="sxs-lookup"><span data-stu-id="58e93-139">Supported by public DNS records.</span></span>
- <span data-ttu-id="58e93-140">已在您的 Microsoft 365 訂閱中註冊。</span><span class="sxs-lookup"><span data-stu-id="58e93-140">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="58e93-141">模擬內部網路上的 AD DS 網域。</span><span class="sxs-lookup"><span data-stu-id="58e93-141">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="58e93-142">階段 3：在 APP1 上安裝 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="58e93-142">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="58e93-143">在這個階段，您會在 APP1 上安裝及設定 Azure AD Connect 工具，然後確認它可運作。</span><span class="sxs-lookup"><span data-stu-id="58e93-143">In this phase, you install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="58e93-144">首先，在 APP1 上安裝及設定 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="58e93-144">First, you install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="58e93-145">從 [Azure 入口網站](https://portal.azure.com)，以您的全域管理員帳戶登入，然後以 TESTLAB\\User1 帳戶連線到 APP1。</span><span class="sxs-lookup"><span data-stu-id="58e93-145">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="58e93-146">從 APP1 的桌面，開啟系統管理員層級 Windows PowerShell 命令提示字元，然後執行下列命令以停用 Internet Explorer 增強的安全性：</span><span class="sxs-lookup"><span data-stu-id="58e93-146">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="58e93-147">從工作列按一下 [Internet Explorer]\*\*\*\*，然後移至 [https://aka.ms/aadconnect](https://aka.ms/aadconnect)。</span><span class="sxs-lookup"><span data-stu-id="58e93-147">From the task bar, click **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="58e93-148">在 [Microsoft Azure Active Directory Connect] 頁面上，按一下 [下載]\*\*\*\*，然後按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58e93-148">On the Microsoft Azure Active Directory Connect page, click **Download**, and then click **Run**.</span></span>
    
5. <span data-ttu-id="58e93-149">在 [歡迎使用 Azure AD Connect]\*\*\*\* 頁面上，按一下 [我同意]\*\*\*\*，然後按一下 [繼續]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58e93-149">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue**.</span></span>
    
6. <span data-ttu-id="58e93-150">在 [快速設定]\*\*\*\* 頁面上，按一下 [使用快速設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58e93-150">On the **Express Settings** page, click **Use express settings**.</span></span>
    
7. <span data-ttu-id="58e93-151">在 [連線到 Azure AD]\*\*\*\* 頁面上，在 [使用者名稱]\*\*\*\* 中輸入您的全域系統管理員帳戶名稱，在 [密碼]\*\*\*\* 中輸入其密碼，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58e93-151">On the **Connect to Azure AD** page, type your global administrator account name in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="58e93-152">在 [連線到 AD DS]\*\*\*\* 頁面上，在 [使用者名稱]\*\*\*\* 中輸入 **TESTLAB\\User1**，在 [密碼]\*\*\*\* 中輸入其密碼，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58e93-152">On the **Connect to AD DS** page, type **TESTLAB\\User1** in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="58e93-153">在 [準備設定]\*\*\*\* 頁面上，按一下 [安裝]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58e93-153">On the **Ready to configure** page, click **Install**.</span></span>
    
10. <span data-ttu-id="58e93-154">在 [組態完成]\*\*\*\* 頁面上，按一下 [結束]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58e93-154">On the **Configuration complete** page, click **Exit**.</span></span>
    
11. <span data-ttu-id="58e93-155">在 Internet Explorer 中，移至 Microsoft 365 系統管理中心 ([https://portal.microsoft.com](https://portal.microsoft.com))。</span><span class="sxs-lookup"><span data-stu-id="58e93-155">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="58e93-156">在左方的瀏覽區域中，按一下 [使用者] > [作用中的使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58e93-156">In the left navigation, click **Users > Active users**.</span></span>
    
    <span data-ttu-id="58e93-157">請注意名為 **User1** 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="58e93-157">Note the account named **User1**.</span></span> <span data-ttu-id="58e93-158">此帳戶是來自 TESTLAB AD DS 網域，且經過證明目錄同步作業可以運作。</span><span class="sxs-lookup"><span data-stu-id="58e93-158">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="58e93-159">按一下 **User1** 帳戶，然後按一下 [授權與 App]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58e93-159">Click the **User1** account, and then click **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="58e93-160">在 [產品授權]\*\*\*\* 中，選取您的位置 (如有需要)，停用 **Office 365 E5** 授權，並啟用 **Microsoft 365 E5** 授權。</span><span class="sxs-lookup"><span data-stu-id="58e93-160">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license and enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="58e93-161">按一下頁面底部的 [儲存]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58e93-161">Click **Save** at the bottom of the page, and then click **Close**.</span></span>
    
<span data-ttu-id="58e93-162">接下來，您要測試使用 <strong>user1@testlab.</strong>\<your domain name>登入訂閱的能力。</span><span class="sxs-lookup"><span data-stu-id="58e93-162">Next, you test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your domain name></span></span> <span data-ttu-id="58e93-163">User1 帳戶的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="58e93-163">user name of the User1 account.</span></span>

1. <span data-ttu-id="58e93-164">從 APP1 登出，然後再次登入，這次指定不同的帳戶。</span><span class="sxs-lookup"><span data-stu-id="58e93-164">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="58e93-165">當系統提示輸入使用者名稱和密碼時，指定 <strong>user1@testlab.</strong>\<your domain name></span><span class="sxs-lookup"><span data-stu-id="58e93-165">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name></span></span> <span data-ttu-id="58e93-166">和 User1 密碼。</span><span class="sxs-lookup"><span data-stu-id="58e93-166">and the User1 password.</span></span> <span data-ttu-id="58e93-167">您應該可以用 User1 的身分成功登入。</span><span class="sxs-lookup"><span data-stu-id="58e93-167">You should successfully sign in as User1.</span></span> 
 
<span data-ttu-id="58e93-168">請注意，User1 雖具有 TESTLAB AD DS 網域的網域管理員權限，但並不是全域管理員。</span><span class="sxs-lookup"><span data-stu-id="58e93-168">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="58e93-169">因此，您不會看到 [管理員]\*\*\*\* 圖示選項。</span><span class="sxs-lookup"><span data-stu-id="58e93-169">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="58e93-170">以下是產生的組態。</span><span class="sxs-lookup"><span data-stu-id="58e93-170">Here is your resulting configuration.</span></span>

![使用密碼雜湊同步處理測試環境的模擬企業](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="58e93-172">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="58e93-172">This configuration consists of:</span></span> 
  
- <span data-ttu-id="58e93-173">Microsoft 365 E5 或 Office 365 E5 試用版或付費訂閱版，其包含有 DNS 網域TESTLAB.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="58e93-173">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name></span></span> <span data-ttu-id="58e93-174">註冊。</span><span class="sxs-lookup"><span data-stu-id="58e93-174">registered.</span></span>
- <span data-ttu-id="58e93-175">簡化的組織內部網域與網際網路的連線，由 Azure 虛擬網路的子網路上的 DC1、APP1 及 CLIENT1 虛擬機器組成</span><span class="sxs-lookup"><span data-stu-id="58e93-175">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="58e93-176">Azure AD Connect 在 APP1 上執行，以定期將 TESTLAB AD DS 網域同步至 Microsoft 365 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="58e93-176">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>
- <span data-ttu-id="58e93-177">TESTLAB AD DS 網域中的 User1 帳戶已經與 Azure AD 租用戶同步處理。</span><span class="sxs-lookup"><span data-stu-id="58e93-177">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="58e93-178">下一步</span><span class="sxs-lookup"><span data-stu-id="58e93-178">Next step</span></span>

<span data-ttu-id="58e93-179">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="58e93-179">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="58e93-180">另請參閱</span><span class="sxs-lookup"><span data-stu-id="58e93-180">See also</span></span>

[<span data-ttu-id="58e93-181">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="58e93-181">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="58e93-182">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="58e93-182">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="58e93-183">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="58e93-183">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


