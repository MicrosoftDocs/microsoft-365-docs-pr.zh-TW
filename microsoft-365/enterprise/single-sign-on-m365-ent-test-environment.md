---
title: 適用於 Microsoft 365 測試環境的 Azure AD 無縫單一登入
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
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
description: 摘要：設定並測試適用於 Microsoft 365 測試環境的 Azure AD 無縫單一登入。
ms.openlocfilehash: 7fcbc82cfb35c598358c8160dd06427c2a9c59a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904861"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="471de-103">適用於 Microsoft 365 測試環境的 Azure AD 無縫單一登入</span><span class="sxs-lookup"><span data-stu-id="471de-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="471de-104">*此測試實驗室指南可用於 enterprise 和 Office 365 企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="471de-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="471de-105">Azure AD 無縫單一 Sign-On (無縫 SSO) 會在使用者位於連接至其組織網路的電腦或裝置上時，自動登入使用者。</span><span class="sxs-lookup"><span data-stu-id="471de-105">Azure AD Seamless Single Sign-On (Seamless SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network.</span></span> <span data-ttu-id="471de-106">Azure AD 無縫 SSO 可讓使用者輕鬆存取雲端架構應用程式，而不需要任何其他內部部署元件。</span><span class="sxs-lookup"><span data-stu-id="471de-106">Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="471de-107">本文說明如何針對 Azure AD 無縫 SSO 設定 Microsoft 365 測試環境。</span><span class="sxs-lookup"><span data-stu-id="471de-107">This article describes how to configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="471de-108">設定 Azure AD 無縫 SSO 包含兩個階段：</span><span class="sxs-lookup"><span data-stu-id="471de-108">Setting up Azure AD Seamless SSO involves two phases:</span></span>
- [<span data-ttu-id="471de-109">階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="471de-109">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="471de-110">階段 2：在 APP1 上針對 Azure AD 無縫 SSO 設定 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="471de-110">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="471de-112">如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="471de-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="471de-113">階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="471de-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="471de-114">依照 [Microsoft 365 的密碼雜湊同步](password-hash-sync-m365-ent-test-environment.md)處理中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="471de-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="471de-115">您產生的設定如下所示：</span><span class="sxs-lookup"><span data-stu-id="471de-115">Your resulting configuration looks like this:</span></span>
  
![使用密碼雜湊同步處理測試環境的模擬企業](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="471de-117">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="471de-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="471de-118">Microsoft 365 E5 試用版或付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="471de-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="471de-119">簡化的組織內部網路連接至網際網路，由 Azure 虛擬網路子網上的 DC1、APP1 和 CLIENT1 虛擬機器所組成。</span><span class="sxs-lookup"><span data-stu-id="471de-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="471de-120">Azure AD Connect 會在 APP1 執行，定期將 AD DS) 網域 (的 TESTLAB Active Directory 網域服務同步處理至您 Microsoft 365 訂閱的 Azure AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="471de-120">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="471de-121">階段 2：在 APP1 上針對 Azure AD 無縫 SSO 設定 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="471de-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="471de-122">在此階段中，針對 Azure AD 無縫 SSO 的 APP1 設定 Azure AD Connect，然後驗證它是否運作正常。</span><span class="sxs-lookup"><span data-stu-id="471de-122">In this phase, configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="471de-123">在 APP1 上設定 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="471de-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="471de-124">從 [Azure 入口網站](https://portal.azure.com)，以您的全域管理員帳戶登入，然後以 TESTLAB\User1 帳戶連線到 APP1。</span><span class="sxs-lookup"><span data-stu-id="471de-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="471de-125">從 APP1 桌面，執行 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="471de-125">From the APP1 desktop, run Azure AD Connect.</span></span>

3. <span data-ttu-id="471de-126">在 [ **歡迎] 頁面** 上，選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="471de-126">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="471de-127">在 [ **其他** 工作] 頁面上，選取 [ **變更使用者登入**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="471de-127">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>

5. <span data-ttu-id="471de-128">在 [連線 **到 AZURE AD]** 頁面上，輸入您的全域系統管理員帳號憑證，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="471de-128">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="471de-129">在 [ **使用者登入** ] 頁面上，選取 [ **啟用單一登入**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="471de-129">On the **User sign-in** page, select **Enable single sign-on**, and then select **Next**.</span></span>

7. <span data-ttu-id="471de-130">在 [ **啟用單一登入** ] 頁面上，選取 [ **輸入認證**]。</span><span class="sxs-lookup"><span data-stu-id="471de-130">On the **Enable single sign-on** page, select **Enter credentials**.</span></span>

8. <span data-ttu-id="471de-131">在 [ **Windows 安全性** ] 對話方塊中，輸入 **user1** 及 user1 帳戶的密碼，然後選取 **[確定]**，然後選取 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="471de-131">In the **Windows Security** dialog box, enter **user1** and the password of the user1 account, select **OK**, and then select **Next**.</span></span>

9. <span data-ttu-id="471de-132">在 [ **準備設定** ] 頁面上，選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="471de-132">On the **Ready to Configure** page, select **Configure**.</span></span>

10. <span data-ttu-id="471de-133">在 [設定完成] 頁面上 **，選取 [\*\*\*\*結束**]。</span><span class="sxs-lookup"><span data-stu-id="471de-133">On the **Configuration complete** page, select **Exit**.</span></span>

11. <span data-ttu-id="471de-134">從 Azure 入口網站的左窗格中，選取 [ **azure Active Directory**  >  **Azure AD Connect**]。</span><span class="sxs-lookup"><span data-stu-id="471de-134">From the Azure portal, in the left pane, select **Azure Active Directory** > **Azure AD Connect**.</span></span> <span data-ttu-id="471de-135">確認 **無縫單一登入** 功能顯示為 [ **已啟用**]。</span><span class="sxs-lookup"><span data-stu-id="471de-135">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="471de-136">接下來，使用 user1@testlab 測試登入訂閱的功能 <strong>。</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="471de-136">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="471de-137">User1 帳戶的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="471de-137">user name of the User1 account.</span></span>

1. <span data-ttu-id="471de-138">從 Internet Explorer 的 APP1 上，選取 [設定] 圖示，然後選取 [ **網際網路選項**]。</span><span class="sxs-lookup"><span data-stu-id="471de-138">From Internet Explorer on APP1, select the settings icon, and then select **Internet Options**.</span></span>
 
2. <span data-ttu-id="471de-139">在 [ **網際網路選項**] 中，選取 [ **安全性** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="471de-139">In **Internet Options**, select the **Security** tab.</span></span>

3. <span data-ttu-id="471de-140">選取 [ **本機內部** 網路]，然後選取 [ **網站**]。</span><span class="sxs-lookup"><span data-stu-id="471de-140">Select **Local intranet**, and then select **Sites**.</span></span>

4. <span data-ttu-id="471de-141">在 [ **本機內部** 網路] 中，選取 [ **高級**]。</span><span class="sxs-lookup"><span data-stu-id="471de-141">In **Local intranet**, select **Advanced**.</span></span>

5. <span data-ttu-id="471de-142">在 **[將此網站新增至] 區域** 中，輸入 **HTTPs：<span>//</span>autologon.microsoftazuread-sso.com**，然後選取 [**新增**  >  **關閉**  >  **]**[確定  >  **]**。</span><span class="sxs-lookup"><span data-stu-id="471de-142">In **Add this website to the zone**, enter **https <span>://</span>autologon.microsoftazuread-sso.com**, select **Add** > **Close** > **OK** > **OK**.</span></span>

6. <span data-ttu-id="471de-143">登出然後再次登入，這次指定不同的帳戶。</span><span class="sxs-lookup"><span data-stu-id="471de-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="471de-144">當系統提示您登入時，請指定 <strong>user1@testlab。</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="471de-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="471de-145">名稱，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="471de-145">name, and then select **Next**.</span></span> <span data-ttu-id="471de-146">您應該成功以 User1 登入，且系統不會提示您輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="471de-146">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="471de-147">這可證明 Azure AD 無縫 SSO 正在執行。</span><span class="sxs-lookup"><span data-stu-id="471de-147">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="471de-148">請注意，User1 雖具有 TESTLAB AD DS 網域的網域管理員權限，但並不是 Azure AD 的全域管理員。</span><span class="sxs-lookup"><span data-stu-id="471de-148">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="471de-149">因此，您不會看到 [管理員] 圖示選項。</span><span class="sxs-lookup"><span data-stu-id="471de-149">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="471de-150">以下是您產生的組態：</span><span class="sxs-lookup"><span data-stu-id="471de-150">Here is your resulting configuration:</span></span>

![使用傳遞驗證測試環境的模擬企業](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="471de-152">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="471de-152">This configuration consists of:</span></span>

- <span data-ttu-id="471de-153">使用 DNS 網域 testlab 的 Microsoft 365 E5 試用版或付費訂閱。\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="471de-153">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<*your domain name*></span></span> <span data-ttu-id="471de-154">註冊。</span><span class="sxs-lookup"><span data-stu-id="471de-154">registered.</span></span>
- <span data-ttu-id="471de-155">簡化的組織內部網路連接至網際網路，由 Azure 虛擬網路子網上的 DC1、APP1 和 CLIENT1 虛擬機器所組成。</span><span class="sxs-lookup"><span data-stu-id="471de-155">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="471de-156">Azure AD Connect 會在 APP1 上執行，以將來自 Microsoft 365 訂閱之 Azure AD 租用戶的帳戶和群組清單同步至 TESTLAB AD DS 網域。</span><span class="sxs-lookup"><span data-stu-id="471de-156">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="471de-157">啟用 Azure AD 無縫 SSO，使模擬內部網路上的電腦無需指定使用者帳戶密碼，即可登入 Microsoft 365 雲端資源。</span><span class="sxs-lookup"><span data-stu-id="471de-157">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifying a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="471de-158">下一步</span><span class="sxs-lookup"><span data-stu-id="471de-158">Next step</span></span>

<span data-ttu-id="471de-159">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="471de-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="471de-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="471de-160">See also</span></span>

[<span data-ttu-id="471de-161">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="471de-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="471de-162">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="471de-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="471de-163">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="471de-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)