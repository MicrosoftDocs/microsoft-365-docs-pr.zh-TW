---
title: 適用於 Microsoft 365 測試環境的 Azure AD 無縫單一登入
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
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
description: 摘要：設定並測試適用於 Microsoft 365 測試環境的 Azure AD 無縫單一登入。
ms.openlocfilehash: c8417d7ff1c4a2b9a753968804d187300b6c6195
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640594"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="b4cac-103">適用於 Microsoft 365 測試環境的 Azure AD 無縫單一登入</span><span class="sxs-lookup"><span data-stu-id="b4cac-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="b4cac-p101">Azure AD 無縫單一登入 (SSO) 會在使用者所在的個人電腦或裝置連線到公司網路時自動將他們登入。Azure AD 無縫 SSO 可讓使用者輕鬆存取雲端式應用程式，而不需要任何額外的內部部署元件。</span><span class="sxs-lookup"><span data-stu-id="b4cac-p101">Azure AD Seamless Single Sign-On (SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="b4cac-106">本文說明如何設定您的 Microsoft 365 測試環境以進行 Azure AD 無縫 SSO。</span><span class="sxs-lookup"><span data-stu-id="b4cac-106">This article describes how you can configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="b4cac-107">此測試環境的設定分為兩個階段︰</span><span class="sxs-lookup"><span data-stu-id="b4cac-107">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="b4cac-108">使用密碼雜湊同步處理建立 Microsoft 365 模擬企業測試環境。</span><span class="sxs-lookup"><span data-stu-id="b4cac-108">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="b4cac-109">在 APP1 上針對 Azure AD 無縫 SSO 設定 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="b4cac-109">Configure Azure AD Connect on APP1 for Azure AD Seamless SSO.</span></span>
    
![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="b4cac-111">按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="b4cac-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="b4cac-112">階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="b4cac-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="b4cac-p102">請遵循[適用於 Microsoft 365 的密碼雜湊同步處理](password-hash-sync-m365-ent-test-environment.md)中的指示。以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="b4cac-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![使用密碼雜湊同步處理測試環境的模擬企業](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="b4cac-116">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="b4cac-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="b4cac-117">Office 365 E5 和 EMS E5 試用版或付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="b4cac-117">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="b4cac-118">簡化的組織內部網域與網際網路的連線，由 Azure 虛擬網路的子網路上的 DC1、APP1 及 CLIENT1 虛擬機器組成</span><span class="sxs-lookup"><span data-stu-id="b4cac-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="b4cac-119">Azure AD Connect 會在 APP1 上執行，以將 TESTLAB Active Directory Domain Services (AD DS) 網域定期同步至 Office 365 和 EMS E5 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="b4cac-119">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="b4cac-120">階段 2：在 APP1 上針對 Azure AD 無縫 SSO 設定 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="b4cac-120">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="b4cac-121">在這個階段中，您會在 APP1 上針對 Azure AD 無縫 SSO 設定 Azure AD Connect，然後驗證它是否運作正常。</span><span class="sxs-lookup"><span data-stu-id="b4cac-121">In this phase, you configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="b4cac-122">在 APP1 上設定 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="b4cac-122">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="b4cac-123">從 [Azure 入口網站](https://portal.azure.com)，以您的全域管理員帳戶登入，然後以 TESTLAB\User1 帳戶連線到 APP1。</span><span class="sxs-lookup"><span data-stu-id="b4cac-123">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="b4cac-124">從 APP1 的桌面執行 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="b4cac-124">From the desktop of APP1, run Azure AD Connect.</span></span>

3. <span data-ttu-id="b4cac-125">在 [歡迎]\*\*\*\* 頁面上，按一下 [設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4cac-125">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="b4cac-126">在 [其他工作]\*\*\*\* 頁面上，按一下 [變更使用者登入]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4cac-126">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="b4cac-127">在 [連線到 Azure AD]\*\*\*\* 頁面上，輸入您的全域管理員帳戶認證，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4cac-127">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="b4cac-128">在 [使用者登入]\*\*\*\* 頁面上，選取 [啟用單登入]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4cac-128">On the **User sign-in** page, select **Enable single sign-on**, and then click **Next**.</span></span>

7. <span data-ttu-id="b4cac-129">在 [啟用單一登入]\*\*\*\* 頁面上，按一下 [輸入認證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4cac-129">On the **Enable single sign-on** page, click **Enter credentials**.</span></span>

8. <span data-ttu-id="b4cac-p103">在 [Windows 安全性]\*\*\*\* 對話方塊中，輸入 **user1** 和 user1 帳戶的密碼，然後按一下 [確定]\*\*\*\*。按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4cac-p103">In the **Windows Security** dialog box, type **user1** and the password of the user1 account, and then click **OK**. Click **Next**.</span></span>

9. <span data-ttu-id="b4cac-132">在 [準備設定]\*\*\*\* 頁面上，按一下 [設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4cac-132">On the **Ready to Configure** page, click **Configure**.</span></span>

10. <span data-ttu-id="b4cac-133">在 [組態完成]\*\*\*\* 頁面上，按一下 [結束]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4cac-133">On the **Configuration complete** page, click **Exit**.</span></span>

11. <span data-ttu-id="b4cac-p104">從 Azure 入口網站的左窗格，按一下 [Azure Active Directory > Azure AD Connect]\*\*\*\*。確認 [無縫單一登入]\*\*\*\* 功能顯示為 [已啟用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4cac-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="b4cac-136">接下來，以 <strong>user1@testlab.</strong>\<您的公用網域> User1 帳戶的使用者名稱測試登入 Office 365 訂閱的能力。</span><span class="sxs-lookup"><span data-stu-id="b4cac-136">Next, test the ability to sign in to your Office 365 subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="b4cac-137">從 APP1 上的 Internet Explorer 中，按一下設定圖示，然後按一下 [網際網路選項]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4cac-137">From Internet Explorer on APP1, click the settings icon, and then click **Internet Options**.</span></span>
 
2. <span data-ttu-id="b4cac-138">在 [網際網路選項]\*\*\*\* 中，按一下 [安全性]\*\*\*\* 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b4cac-138">In **Internet Options**, click the **Security** tab.</span></span>

3. <span data-ttu-id="b4cac-139">按一下 [近端內部網路]\*\*\*\*，然後按一下 [網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4cac-139">Click **Local intranet**, and then click **Sites**.</span></span>

4. <span data-ttu-id="b4cac-140">在 [近端內部網路]\*\*\*\* 中，按一下[進階]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4cac-140">In **Local intranet**, click **Advanced**.</span></span>

5. <span data-ttu-id="b4cac-141">在 [將這個網站新增到區域]\*\*\*\* 中，輸入 **https<span>://</span>autologon.microsoftazuread-sso.com**，然後按一下 [新增 > 關閉 > 確定 > 確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4cac-141">In **Add this website to the zone**, type **https<span>://</span>autologon.microsoftazuread-sso.com**, click **Add > Close > OK > OK**.</span></span>

6. <span data-ttu-id="b4cac-142">登出 Office 365，然後再次登入，這次指定不同的帳戶。</span><span class="sxs-lookup"><span data-stu-id="b4cac-142">Sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="b4cac-143">提示登入時，指定 <strong>user1@testlab.</strong>\<your public domain> name，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4cac-143">When prompted to sign in, specify <strong>user1@testlab.</strong>\<your public domain> name, and then click **Next**.</span></span> <span data-ttu-id="b4cac-144">您應該成功以 User1 登入，且系統不會提示您輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="b4cac-144">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="b4cac-145">這可證明 Azure AD 無縫 SSO 正在執行。</span><span class="sxs-lookup"><span data-stu-id="b4cac-145">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="b4cac-146">請注意，User1 雖具有 TESTLAB AD DS 網域的網域管理員權限，但並不是 Azure AD 和 Office 365 的全域管理員。</span><span class="sxs-lookup"><span data-stu-id="b4cac-146">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD and Office 365.</span></span> <span data-ttu-id="b4cac-147">因此，您不會看到 [管理員]\*\*\*\* 圖示選項。</span><span class="sxs-lookup"><span data-stu-id="b4cac-147">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="b4cac-148">以下是您產生的組態：</span><span class="sxs-lookup"><span data-stu-id="b4cac-148">Here is your resulting configuration:</span></span>

![使用傳遞驗證測試環境的模擬企業](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
<span data-ttu-id="b4cac-150">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="b4cac-150">This configuration consists of:</span></span>

- <span data-ttu-id="b4cac-151">已註冊 DNS 網域 testlab.\<您的網域名稱> 的 Office 365 E5 和 EMS E5 試用版或付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="b4cac-151">Office 365 E5 and EMS E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="b4cac-152">簡化的組織內部網域與網際網路的連線，由 Azure 虛擬網路的子網路上的 DC1、APP1 及 CLIENT1 虛擬機器組成</span><span class="sxs-lookup"><span data-stu-id="b4cac-152">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="b4cac-153">Azure AD Connect 在 APP1 上執行，以將來自 Office 365 和 EMS E5 訂閱之 Azure AD 租用戶的帳戶和群組清單同步至 TESTLAB AD DS 網域。</span><span class="sxs-lookup"><span data-stu-id="b4cac-153">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Office 365 and EMS E5 subscriptions to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="b4cac-154">啟用 Azure AD 無縫 SSO，可讓模擬內部網路上的電腦登入 Microsoft 365 雲端，而無需指定使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="b4cac-154">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifing a user account password.</span></span>

<span data-ttu-id="b4cac-155">如需在生產中設定 Azure AD 無縫 SSO 的相關資訊和連結，請參閱身分識別階段中的[簡化使用者登入](identity-secure-your-passwords.md#identity-sso)步驟。</span><span class="sxs-lookup"><span data-stu-id="b4cac-155">See the [Simplify user sign-in](identity-secure-your-passwords.md#identity-sso) step in the Identity phase for information and links to configure Azure AD Seamless SSO in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="b4cac-156">下一步</span><span class="sxs-lookup"><span data-stu-id="b4cac-156">Next step</span></span>

<span data-ttu-id="b4cac-157">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="b4cac-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4cac-158">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b4cac-158">See also</span></span>

[<span data-ttu-id="b4cac-159">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="b4cac-159">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b4cac-160">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="b4cac-160">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b4cac-161">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="b4cac-161">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


