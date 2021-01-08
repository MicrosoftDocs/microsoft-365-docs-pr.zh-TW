---
title: 準備無法路由傳送的網域，以用於目錄同步處理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: 如果您有無法路由的網域與您的內部部署使用者帳戶相關聯，您必須先將其與您的 Microsoft 365 租使用者進行同步處理，瞭解如何處理。
ms.openlocfilehash: dcd941bbae159afeb0cf6ef4f5acbaf409966295
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780329"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a><span data-ttu-id="6ca02-103">準備無法路由傳送的網域，以用於目錄同步處理</span><span class="sxs-lookup"><span data-stu-id="6ca02-103">Prepare a non-routable domain for directory synchronization</span></span>

<span data-ttu-id="6ca02-104">當您同步處理內部部署目錄與 Microsoft 365 時，您必須在 Azure Active Directory (Azure AD) 中有一個已驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="6ca02-104">When you synchronize your on-premises directory with Microsoft 365, you have to have a verified domain in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="6ca02-105">只會同步處理與內部部署 Active Directory 網域服務 (AD DS) 網域相關聯 (Upn) 的使用者主體名稱。</span><span class="sxs-lookup"><span data-stu-id="6ca02-105">Only the User Principal Names (UPNs) that are associated with the on-premises Active Directory Domain Services (AD DS) domain are synchronized.</span></span> <span data-ttu-id="6ca02-106">不過，任何包含無法路由之網域的 UPN （如 "local" (範例： billa@contoso local) ）將同步處理至 onmicrosoft.com 域 (範例： billa@contoso.onmicrosoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="6ca02-106">However, any UPN that contains a non-routable domain, such as ".local" (example: billa@contoso.local), will be synchronized to an .onmicrosoft.com domain (example: billa@contoso.onmicrosoft.com).</span></span> 

<span data-ttu-id="6ca02-107">如果您目前在 AD DS 中為您的使用者帳戶使用 "local" 網域，建議您將其變更為使用已驗證的網域（例如 billa@contoso.com），以便與您的 Microsoft 365 網域正確同步。</span><span class="sxs-lookup"><span data-stu-id="6ca02-107">If you currently use a ".local" domain for your user accounts in AD DS, it's recommended that you change them to use a verified domain, such as billa@contoso.com, in order to properly synchronize with your Microsoft 365 domain.</span></span>
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a><span data-ttu-id="6ca02-108">如果我只有「內部」內部部署網域，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="6ca02-108">What if I only have a ".local" on-premises domain?</span></span>

<span data-ttu-id="6ca02-109">您可以使用 Azure AD Connect，將 AD DS 同步處理至您的 Microsoft 365 租使用者的 Azure AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="6ca02-109">You use Azure AD Connect for synchronizing your AD DS to the Azure AD tenant of your Microsoft 365 tenant.</span></span> <span data-ttu-id="6ca02-110">如需詳細資訊，請參閱 [將內部部署身分識別與 AZURE AD 整合](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad)。</span><span class="sxs-lookup"><span data-stu-id="6ca02-110">For more information, see [Integrating your on-premises identities with Azure AD](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad).</span></span>
  
<span data-ttu-id="6ca02-111">Azure AD Connect 會同步處理您的使用者的 UPN 和密碼，讓使用者可以使用內部部署所使用的相同認證來登入。</span><span class="sxs-lookup"><span data-stu-id="6ca02-111">Azure AD Connect synchronizes your users' UPN and password so that users can sign in with the same credentials they use on-premises.</span></span> <span data-ttu-id="6ca02-112">不過，Azure AD Connect 只會同步處理使用者至 Microsoft 365 所驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="6ca02-112">However, Azure AD Connect only synchronizes users to domains that are verified by Microsoft 365.</span></span> <span data-ttu-id="6ca02-113">這表示網域也會由 Azure AD 驗證，因為 Microsoft 365 identity 是由 Azure AD 所管理。</span><span class="sxs-lookup"><span data-stu-id="6ca02-113">This means that the domain also is verified by Azure AD because Microsoft 365 identities are managed by Azure AD.</span></span> <span data-ttu-id="6ca02-114">換句話說，網域必須是有效的網際網路網域 (例如，.com、org、.net、. us) 。</span><span class="sxs-lookup"><span data-stu-id="6ca02-114">In other words, the domain has to be a valid Internet domain (such as, .com, .org, .net, .us).</span></span> <span data-ttu-id="6ca02-115">如果內部 AD DS 只使用不可路由的網域 (例如 "local" ) ，這可能會比對您的 Microsoft 365 租使用者驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="6ca02-115">If your internal AD DS only uses a non-routable domain (for example, ".local"), this can't possibly match the verified domain you have for your Microsoft 365 tenant.</span></span> <span data-ttu-id="6ca02-116">您可以在內部部署 AD DS 中變更您的主要網域，或是新增一或多個 UPN 尾碼，以修正此問題。</span><span class="sxs-lookup"><span data-stu-id="6ca02-116">You can fix this issue by either changing your primary domain in your on-premises AD DS, or by adding one or more UPN suffixes.</span></span>
  
### <a name="change-your-primary-domain"></a><span data-ttu-id="6ca02-117">變更您的主要網域</span><span class="sxs-lookup"><span data-stu-id="6ca02-117">Change your primary domain</span></span>

<span data-ttu-id="6ca02-118">將您的主要網域變更為您已在 Microsoft 365 中驗證的網域，例如，contoso.com。</span><span class="sxs-lookup"><span data-stu-id="6ca02-118">Change your primary domain to a domain you have verified in Microsoft 365, for example, contoso.com.</span></span> <span data-ttu-id="6ca02-119">每個具有網域 contoso 的使用者都會更新為 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="6ca02-119">Every user that has the domain contoso.local is then updated to contoso.com.</span></span> <span data-ttu-id="6ca02-120">不過，這是非常相關的程式，但下一節將說明更簡單的解決方案。</span><span class="sxs-lookup"><span data-stu-id="6ca02-120">This is a very involved process, however, and an easier solution is described in the following section.</span></span>
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a><span data-ttu-id="6ca02-121">新增 UPN 尾碼並更新您的使用者</span><span class="sxs-lookup"><span data-stu-id="6ca02-121">Add UPN suffixes and update your users to them</span></span>

<span data-ttu-id="6ca02-122">您可以在 AD DS 中註冊新的 UPN 尾碼或尾碼，以符合您在 Microsoft 365 中驗證的網域 (或) 網域，來解決「本機」問題。</span><span class="sxs-lookup"><span data-stu-id="6ca02-122">You can solve the ".local" problem by registering new UPN suffix or suffixes in AD DS to match the domain (or domains) you verified in Microsoft 365.</span></span> <span data-ttu-id="6ca02-123">在您註冊新的尾碼後，您可以更新使用者 Upn，將 "local" 取代為新的功能變數名稱，例如，讓使用者帳戶看起來像是 billa@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="6ca02-123">After you register the new suffix, you update the user UPNs to replace the ".local" with the new domain name, for example, so that a user account looks like billa@contoso.com.</span></span>
  
<span data-ttu-id="6ca02-124">在您更新 Upn 以使用已驗證的網域之後，即可將您的內部部署 AD DS 與 Microsoft 365 進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="6ca02-124">After you have updated the UPNs to use the verified domain, you are ready to synchronize your on-premises AD DS with Microsoft 365.</span></span>
  
#### <a name="step-1-add-the-new-upn-suffix"></a><span data-ttu-id="6ca02-125">步驟1：新增 UPN 尾碼 \* \*</span><span class="sxs-lookup"><span data-stu-id="6ca02-125">Step 1: Add the new UPN suffix\*\*</span></span>
  
1. <span data-ttu-id="6ca02-126">在 AD DS 網域控制站的 [伺服器管理員] 中，選擇 [ **工具**] [ \> **Active Directory 網域及信任**]。</span><span class="sxs-lookup"><span data-stu-id="6ca02-126">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Domains and Trusts**.</span></span>
    
    <span data-ttu-id="6ca02-127">**或者，如果您沒有 Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="6ca02-127">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="6ca02-128">按 **Windows 鍵 + R** 以開啟 [ **執行** ] 對話方塊，然後在 [services.msc] 中輸入，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6ca02-128">Press **Windows key + R** to open the **Run** dialog, and then type in Domain.msc, and then choose **OK**.</span></span>
    
    ![選擇 [Active Directory 網域及信任]。](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. <span data-ttu-id="6ca02-130">在 [ **Active Directory 網域及信任** ] 視窗中，以滑鼠右鍵按一下 [ **active Directory 網域及信任**]，然後選擇 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6ca02-130">In the **Active Directory Domains and Trusts** window, right-click **Active Directory Domains and Trusts**, and then choose **Properties**.</span></span>
    
    ![以滑鼠右鍵按一下 [Active Directory 網域及信任]，然後選擇 [屬性]。](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. <span data-ttu-id="6ca02-132">在 [ **UPN 尾碼** ] 索引標籤的 [ **替代的 upn 尾碼** ] 方塊中，輸入新的 upn 尾碼或尾碼， **然後選擇 [新增]** \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6ca02-132">On the **UPN Suffixes** tab, in the **Alternative UPN Suffixes** box, type your new UPN suffix or suffixes, and then choose **Add** \> **Apply**.</span></span>
    
    ![新增 UPN 尾碼](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    <span data-ttu-id="6ca02-134">完成新增尾碼後，請選擇 **[確定]** 。</span><span class="sxs-lookup"><span data-stu-id="6ca02-134">Choose **OK** when you're done adding suffixes.</span></span> 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a><span data-ttu-id="6ca02-135">步驟2：變更現有使用者的 UPN 尾碼</span><span class="sxs-lookup"><span data-stu-id="6ca02-135">Step 2: Change the UPN suffix for existing users</span></span>
  
1. <span data-ttu-id="6ca02-136">在 AD DS 網域控制站的 [伺服器管理員] 中，選擇 [ **工具**] [ \> **Active Directory 使用者和電腦**]。</span><span class="sxs-lookup"><span data-stu-id="6ca02-136">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="6ca02-137">**或者，如果您沒有 Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="6ca02-137">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="6ca02-138">按 **Windows 鍵 + R** 以開啟 [**執行**] 對話方塊，然後在 [dsa.msc] 中輸入，然後按一下 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="6ca02-138">Press **Windows key + R** to open the **Run** dialog, and then type in Dsa.msc, and then click **OK**</span></span>
    
2. <span data-ttu-id="6ca02-139">選取使用者，以滑鼠右鍵按一下，然後選擇 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6ca02-139">Select a user, right-click, and then choose **Properties**.</span></span>
    
3. <span data-ttu-id="6ca02-140">在 [ **帳戶** ] 索引標籤的 [UPN 尾碼] 下拉式清單中，選擇新的 UPN 尾碼，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6ca02-140">On the **Account** tab, in the UPN suffix drop-down list, choose the new UPN suffix, and then choose **OK**.</span></span>
    
    ![為使用者新增 UPN 尾碼](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. <span data-ttu-id="6ca02-142">針對每位使用者完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="6ca02-142">Complete these steps for every user.</span></span>
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a><span data-ttu-id="6ca02-143">使用 PowerShell 變更所有使用者的 UPN 尾碼</span><span class="sxs-lookup"><span data-stu-id="6ca02-143">Use PowerShell to change the UPN suffix for all of your users</span></span>

<span data-ttu-id="6ca02-144">如果您有許多使用者帳戶需要更新，使用 PowerShell 會比較容易。</span><span class="sxs-lookup"><span data-stu-id="6ca02-144">If you have a lot of user accounts to update, it's easier to use PowerShell.</span></span> <span data-ttu-id="6ca02-145">下列範例使用 Cmdlet [microsoft.rtc.management.adconnect.schema.aduser](https://go.microsoft.com/fwlink/p/?LinkId=624312) 及 [Set-microsoft.rtc.management.adconnect.schema.aduser](https://go.microsoft.com/fwlink/p/?LinkId=624313) ，將所有 CONTOSO。在 AD DS 中的 contoso.com 的本機尾碼。</span><span class="sxs-lookup"><span data-stu-id="6ca02-145">The following example uses the cmdlets [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) and [Set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) to change all contoso.local suffixes to contoso.com in AD DS.</span></span> 

<span data-ttu-id="6ca02-146">例如，您可以執行下列 PowerShell 命令，將所有 contoso。本機尾碼更新為 contoso.com：</span><span class="sxs-lookup"><span data-stu-id="6ca02-146">For example, you could run the following PowerShell commands to update all contoso.local suffixes to contoso.com:</span></span>
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

<span data-ttu-id="6ca02-147">請參閱 [Active Directory Windows PowerShell 模組](https://go.microsoft.com/fwlink/p/?LinkId=624314) ，以深入瞭解在 AD DS 中使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6ca02-147">See [Active Directory Windows PowerShell module](https://go.microsoft.com/fwlink/p/?LinkId=624314) to learn more about using Windows PowerShell in AD DS.</span></span> 

