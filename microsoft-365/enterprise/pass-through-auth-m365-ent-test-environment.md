---
title: 適用於 Microsoft 365 測試環境的傳遞驗證
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
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
ms.assetid: ''
description: 摘要：設定適用於 Microsoft 365 測試環境的傳遞驗證。
ms.openlocfilehash: 98e0ad4b216fdc3940c0077cb308d6271ffed678
ms.sourcegitcommit: 7ae0389cf06e2f481ee646556720ab3f3e93ea32
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2019
ms.locfileid: "38757720"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="13b2d-103">適用於 Microsoft 365 測試環境的傳遞驗證</span><span class="sxs-lookup"><span data-stu-id="13b2d-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="13b2d-104">*這個測試實驗室指南可用於 Microsoft 365 企業版和 Office 365 企業版兩種測試環境。*</span><span class="sxs-lookup"><span data-stu-id="13b2d-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="13b2d-105">想要直接使用內部部署 Active Directory Domain Services (AD DS) 基礎結構，對 Microsoft 雲端式服務和應用程式進行驗證的組織，可以使用傳遞驗證。</span><span class="sxs-lookup"><span data-stu-id="13b2d-105">Organizations that want to directly use their on-premises Active Directory Domain Services (AD DS) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication.</span></span> <span data-ttu-id="13b2d-106">本文說明可以如何針對傳遞驗證設定 Microsoft 365 測試環境，以造成下列組態：</span><span class="sxs-lookup"><span data-stu-id="13b2d-106">This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![使用傳遞驗證測試環境的模擬企業](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="13b2d-108">設定此測試環境有兩個主要階段︰</span><span class="sxs-lookup"><span data-stu-id="13b2d-108">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="13b2d-109">使用密碼雜湊同步處理建立 Microsoft 365 模擬企業測試環境。</span><span class="sxs-lookup"><span data-stu-id="13b2d-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="13b2d-110">在 APP1 上針對傳遞驗證設定 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="13b2d-110">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="13b2d-112">按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="13b2d-112">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="13b2d-113">階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="13b2d-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="13b2d-p102">請遵循[適用於 Microsoft 365 的密碼雜湊同步處理](password-hash-sync-m365-ent-test-environment.md)中的指示。以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="13b2d-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![使用密碼雜湊同步處理測試環境的模擬企業](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="13b2d-117">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="13b2d-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="13b2d-118">Microsoft 365 E5 或 Office 365 E5 試用版或付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="13b2d-118">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="13b2d-119">簡化的組織內部網域與網際網路的連線，由 Azure 虛擬網路的子網路上的 DC1、APP1 及 CLIENT1 虛擬機器組成</span><span class="sxs-lookup"><span data-stu-id="13b2d-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="13b2d-120">Azure AD Connect 在 APP1 上執行，以定期將 TESTLAB AD DS 網域同步至 Microsoft 365 或 Office 365 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="13b2d-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="13b2d-121">階段 2：在 APP1 上針對傳遞驗證設定 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="13b2d-121">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="13b2d-122">在這個階段中，您會在 APP1 上設定 Azure AD Connect 以使用傳遞驗證，然後驗證它是否運作正常。</span><span class="sxs-lookup"><span data-stu-id="13b2d-122">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="13b2d-123">在 APP1 上設定 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="13b2d-123">Configure Azure AD Connect on APP1</span></span>

1.  <span data-ttu-id="13b2d-124">從 [Azure 入口網站](https://portal.azure.com)，以您的全域管理員帳戶登入，然後以 TESTLAB\User1 帳戶連線到 APP1。</span><span class="sxs-lookup"><span data-stu-id="13b2d-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="13b2d-125">從 APP1 的桌面執行 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="13b2d-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3.  <span data-ttu-id="13b2d-126">在 [歡迎]\*\*\*\* 頁面上，按一下 [設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="13b2d-126">On the **Welcome page**, click **Configure**.</span></span>

4.  <span data-ttu-id="13b2d-127">在 [其他工作] 頁面上，按一下 [變更使用者登入]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="13b2d-127">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.  <span data-ttu-id="13b2d-128">在 [連線到 Azure AD]\*\*\*\* 頁面上，輸入您的全域管理員帳戶認證，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="13b2d-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.  <span data-ttu-id="13b2d-129">在 [使用者登入]\*\*\*\* 頁面上，按一下 [傳遞驗證]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="13b2d-129">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.  <span data-ttu-id="13b2d-130">在 [準備設定]\*\*\*\* 頁面上，按一下 [設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="13b2d-130">On the **Ready to configure** page, click **Configure**.</span></span>

8.  <span data-ttu-id="13b2d-131">在 [組態完成]\*\*\*\* 頁面上，按一下 [結束]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="13b2d-131">On the **Configuration complete** page, click **Exit**.</span></span>

9.  <span data-ttu-id="13b2d-p104">從 Azure 入口網站的左窗格，按一下 [Azure Active Directory > Azure AD Connect]\*\*\*\*。確認 [傳遞驗證]\*\*\*\* 功能顯示為 [已啟用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="13b2d-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10. <span data-ttu-id="13b2d-p105">按一下 [傳遞驗證]\*\*\*\*。[傳遞驗證]\*\*\*\* 窗格會列出您的驗證代理程式安裝所在的伺服器。您應該會在清單中看到 APP1。關閉 [傳遞驗證]\*\*\*\* 窗格。</span><span class="sxs-lookup"><span data-stu-id="13b2d-p105">Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="13b2d-138">接下來，以 <strong>user1@testlab.</strong>\<您的公用網域> User1 帳戶的使用者名稱測試登入 Office 365 訂閱的能力。</span><span class="sxs-lookup"><span data-stu-id="13b2d-138">Next, test the ability to sign in to your Office 365 subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="13b2d-139">從 APP1 登出 Office 365，然後再次登入，這次指定不同的帳戶。</span><span class="sxs-lookup"><span data-stu-id="13b2d-139">From APP1, sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="13b2d-140">當系統提示輸入使用者名稱和密碼時，指定 <strong>user1@testlab.</strong>\<您的公用網域> 和 User1 密碼。</span><span class="sxs-lookup"><span data-stu-id="13b2d-140">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your public domain> and the User1 password.</span></span> <span data-ttu-id="13b2d-141">您應該可以用 User1 的身分成功登入。</span><span class="sxs-lookup"><span data-stu-id="13b2d-141">You should successfully sign in as User1.</span></span>

<span data-ttu-id="13b2d-142">請注意，User1 雖具有 TESTLAB AD DS 網域的網域管理員權限，但並不是 Office 365 全域管理員。</span><span class="sxs-lookup"><span data-stu-id="13b2d-142">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not an Office 365 global administrator.</span></span> <span data-ttu-id="13b2d-143">因此，您不會看到 [管理員]\*\*\*\* 圖示選項。</span><span class="sxs-lookup"><span data-stu-id="13b2d-143">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="13b2d-144">以下是您產生的組態：</span><span class="sxs-lookup"><span data-stu-id="13b2d-144">Here is your resulting configuration:</span></span>

![使用傳遞驗證測試環境的模擬企業](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="13b2d-146">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="13b2d-146">This configuration consists of:</span></span>

- <span data-ttu-id="13b2d-147">已註冊 DNS 網域 TESTLAB.\<您的網域名稱> 的 Microsoft 365 E5 或 Office 365 E5 試用版或付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="13b2d-147">Office 365 E5 and EMS E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="13b2d-p108">簡化的組織內部網路與網際網路連線，由 Azure 虛擬網路子網路上的 DC1、APP1 及 CLIENT1 虛擬機器組成。驗證代理程式會在 APP1 上執行，以處理來自 Microsoft 365 或 Office 365 訂閱 Azure AD 租用戶的傳遞驗證要求。</span><span class="sxs-lookup"><span data-stu-id="13b2d-p108">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="next-step"></a><span data-ttu-id="13b2d-150">下一步</span><span class="sxs-lookup"><span data-stu-id="13b2d-150">Next step</span></span>

<span data-ttu-id="13b2d-151">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="13b2d-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="13b2d-152">另請參閱</span><span class="sxs-lookup"><span data-stu-id="13b2d-152">See also</span></span>

[<span data-ttu-id="13b2d-153">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="13b2d-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="13b2d-154">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="13b2d-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="13b2d-155">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="13b2d-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


