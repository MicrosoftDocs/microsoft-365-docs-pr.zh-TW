---
title: 管理 Microsoft 365 使用者帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: 瞭解如何管理 Microsoft 365 使用者帳戶。
ms.openlocfilehash: a7b6d89a0f66605dde168b85d74fcd8e513afc15
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327756"
---
# <a name="manage-microsoft-365-user-accounts"></a><span data-ttu-id="97375-103">管理 Microsoft 365 使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="97375-103">Manage Microsoft 365 user accounts</span></span>

<span data-ttu-id="97375-104">您可以根據您的設定，以數種不同的方式管理 Microsoft 365 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="97375-104">You can manage Microsoft 365 user accounts in several different ways, depending on your configuration.</span></span> <span data-ttu-id="97375-105">您可以在 [Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/add-users/)、 [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)、Active DIRECTORY 網域服務 (AD DS) 或 Azure ACTIVE directory (azure AD) 管理入口網站中管理使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="97375-105">You can manage user accounts in the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/), [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin portal.</span></span> 

<span data-ttu-id="97375-106">一旦您購買 Microsoft 365，Microsoft 365 系統管理中心和 PowerShell 便可用於管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="97375-106">As soon as you purchase Microsoft 365, the Microsoft 365 admin center and PowerShell can be used to manage accounts.</span></span> <span data-ttu-id="97375-107">管理雲端身分識別時，組織中的每個人都有個別的使用者帳戶名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="97375-107">When managing cloud identities, every person in your organization has a separate user account name and password.</span></span> <span data-ttu-id="97375-108">如果您想要與您的內部部署基礎結構整合，並讓使用者帳戶與 Microsoft 365 同步，您可以使用 Azure AD Connect，針對單一登入 (SSO) 功能，提供身分識別和密碼的同步處理。</span><span class="sxs-lookup"><span data-stu-id="97375-108">If you want to integrate with your on-premises infrastructure and have user accounts synchronized with Microsoft 365, you can use Azure AD Connect to provide synchronization of identities and passwords for single sign-on (SSO) functionality.</span></span>
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a><span data-ttu-id="97375-109">規劃管理使用者帳戶的位置和方式</span><span class="sxs-lookup"><span data-stu-id="97375-109">Plan for where and how you will manage your user accounts</span></span>

<span data-ttu-id="97375-110">您可以管理使用者帳戶的位置和方式，取決於您要用於 Microsoft 365 的身分識別模型。</span><span class="sxs-lookup"><span data-stu-id="97375-110">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="97375-111">這兩個整體模型為雲端且混合式。</span><span class="sxs-lookup"><span data-stu-id="97375-111">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="97375-112">僅雲端</span><span class="sxs-lookup"><span data-stu-id="97375-112">Cloud-only</span></span>

<span data-ttu-id="97375-113">您可以在 Microsoft 365 系統管理中心建立及管理使用者。</span><span class="sxs-lookup"><span data-stu-id="97375-113">You create and manage users in the Microsoft 365 admin center.</span></span> <span data-ttu-id="97375-114">您也可以使用 PowerShell 或 Azure AD 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="97375-114">You can also use PowerShell or the Azure AD admin center.</span></span> 
    
### <a name="hybrid"></a><span data-ttu-id="97375-115">混合式</span><span class="sxs-lookup"><span data-stu-id="97375-115">Hybrid</span></span>

<span data-ttu-id="97375-116">使用者帳戶是與 Microsoft 365 從 AD DS 同步處理的，所以您必須使用內部部署 AD DS 工具來管理使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="97375-116">User accounts are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage user accounts.</span></span> 
    
## <a name="managing-accounts"></a><span data-ttu-id="97375-117">管理帳戶</span><span class="sxs-lookup"><span data-stu-id="97375-117">Managing Accounts</span></span>

<span data-ttu-id="97375-118">決定組織建立及管理帳戶的方式時，請考慮下列需求：</span><span class="sxs-lookup"><span data-stu-id="97375-118">When deciding which way your organization will create and manage accounts, consider the following requirements:</span></span>
  
- <span data-ttu-id="97375-119">在內部部署環境中的伺服器上，必須安裝目錄同步作業軟體，以連接 Microsoft 365 和您的 AD DS 之間的身分識別。</span><span class="sxs-lookup"><span data-stu-id="97375-119">The directory synchronization software needs to be installed on servers within your on-premises environment to connect the identities between Microsoft 365 and your AD DS.</span></span>
    
- <span data-ttu-id="97375-120">任何目錄同步處理選項（包括 SSO 選項）都需要您的 AD DS 屬性符合標準。</span><span class="sxs-lookup"><span data-stu-id="97375-120">Any directory synchronization option, including SSO options, requires that your AD DS attributes meet standards.</span></span> <span data-ttu-id="97375-121">您的目錄中所使用的屬性，以及在 [準備目錄同步處理至 Microsoft 365](prepare-for-directory-synchronization.md)時所需的清除)  (的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="97375-121">The specifics of what attributes are used in your directory and what cleanup (if any) is needed are described in [Prepare for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span> 
    
- <span data-ttu-id="97375-122">規劃如何建立 Microsoft 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="97375-122">Plan how you are going to create Microsoft 365 accounts.</span></span>
    
<span data-ttu-id="97375-123">下表列出不同的帳戶管理工具。</span><span class="sxs-lookup"><span data-stu-id="97375-123">The following table lists the different account management tools.</span></span>
    
|<span data-ttu-id="97375-124">工具</span><span class="sxs-lookup"><span data-stu-id="97375-124">Tool</span></span>|<span data-ttu-id="97375-125">附註</span><span class="sxs-lookup"><span data-stu-id="97375-125">Notes</span></span>|
|:-----|:-----|
|<span data-ttu-id="97375-126">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="97375-126">Microsoft 365 admin center</span></span>  <br/> |[<span data-ttu-id="97375-127">個別或大量新增使用者</span><span class="sxs-lookup"><span data-stu-id="97375-127">Add users individually or in bulk</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  <span data-ttu-id="97375-128">提供簡單的 web 介面來新增及變更使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="97375-128">Provides a simple web interface to add and change user accounts.</span></span>  <br/>  <span data-ttu-id="97375-129">如果啟用目錄同步處理，則無法用來變更使用者 (位置和授權指派可以設定) 。</span><span class="sxs-lookup"><span data-stu-id="97375-129">Can't be used to change users if directory synchronization is enabled (location and license assignment can be set).</span></span>  <br/>  <span data-ttu-id="97375-130">無法與 SSO 選項搭配使用。</span><span class="sxs-lookup"><span data-stu-id="97375-130">Can't be used with SSO options.</span></span>  <br/> |
|<span data-ttu-id="97375-131">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="97375-131">Windows PowerShell</span></span>  <br/> |[<span data-ttu-id="97375-132">使用 Windows PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="97375-132">Manage Microsoft 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  <span data-ttu-id="97375-133">可讓您使用 Windows PowerShell 腳本，在大量使用者中新增使用者。</span><span class="sxs-lookup"><span data-stu-id="97375-133">Allows you to add users in bulk users by using a Windows PowerShell script.</span></span>  <br/>  <span data-ttu-id="97375-134">可用於將位置和授權指派給帳戶，不論帳戶是如何建立的。</span><span class="sxs-lookup"><span data-stu-id="97375-134">Can be used to assign location and licenses to accounts, regardless of how the accounts are created.</span></span>  <br/> |
|<span data-ttu-id="97375-135">大量匯入</span><span class="sxs-lookup"><span data-stu-id="97375-135">Bulk import</span></span>  <br/> |[<span data-ttu-id="97375-136">同時新增多個使用者</span><span class="sxs-lookup"><span data-stu-id="97375-136">Add several users at the same time</span></span>](add-several-users-at-the-same-time.md) <br/>  <span data-ttu-id="97375-137">可讓您匯入 CSV 檔案，將使用者群組新增至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="97375-137">Allows you to import a CSV file to add a group of users to Microsoft 365.</span></span>  <br/>  <span data-ttu-id="97375-138">無法與 SSO 選項搭配使用。</span><span class="sxs-lookup"><span data-stu-id="97375-138">Can't be used with SSO options.</span></span>  <br/> |
|<span data-ttu-id="97375-139">Azure AD</span><span class="sxs-lookup"><span data-stu-id="97375-139">Azure AD</span></span>  <br/> |<span data-ttu-id="97375-140">您可以使用 Microsoft 365 訂閱取得免費的 Azure AD 版本。</span><span class="sxs-lookup"><span data-stu-id="97375-140">You get a free edition of Azure AD with your Microsoft 365 subscription.</span></span> <span data-ttu-id="97375-141">您可以執行雲端使用者自助密碼重設的功能，以及使用免費版本自訂登入和存取面板頁面。</span><span class="sxs-lookup"><span data-stu-id="97375-141">You can perform functions like self-service password reset for cloud users, and customization of the Sign-in and Access Panel pages by using the free edition.</span></span> <span data-ttu-id="97375-142">若要取得增強的功能，您可以升級至 basic edition、Azure AD Premium P1 或 Azure AD Premium P2。</span><span class="sxs-lookup"><span data-stu-id="97375-142">To get enhanced functionality, you can upgrade to the basic edition, Azure AD Premium P1, or Azure AD Premium P2.</span></span> <span data-ttu-id="97375-143">如需支援的功能清單，請參閱 [AZURE AD edition](https://go.microsoft.com/fwlink/p/?LinkId=698465) 。</span><span class="sxs-lookup"><span data-stu-id="97375-143">See [Azure AD editions](https://go.microsoft.com/fwlink/p/?LinkId=698465) for the list of supported features.</span></span>  <br/> |
|<span data-ttu-id="97375-144">目錄同步處理</span><span class="sxs-lookup"><span data-stu-id="97375-144">Directory synchronization</span></span>  <br/> |[<span data-ttu-id="97375-145">整合您的內部部署身分識別與 Azure AD</span><span class="sxs-lookup"><span data-stu-id="97375-145">Integrating your on-premises identities with Azure AD</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  <span data-ttu-id="97375-146">若要使用或不使用密碼同步處理的目錄同步處理，請使用 [AZURE AD Connect with express 設定](https://go.microsoft.com/fwlink/p/?LinkID=698537)。</span><span class="sxs-lookup"><span data-stu-id="97375-146">For directory synchronization with or without password synchronization, use [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkID=698537).</span></span>  <br/>  <span data-ttu-id="97375-147">若為多個樹系和 SSO 選項，請使用 [自訂的 AZURE AD Connect 安裝](https://go.microsoft.com/fwlink/p/?LinkId=698430)。</span><span class="sxs-lookup"><span data-stu-id="97375-147">For multiple forests and SSO options, use [Custom Installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span></span>  <br/>  <span data-ttu-id="97375-148">提供啟用 SSO 所需的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="97375-148">Provides the infrastructure that's necessary to enable SSO.</span></span>  <br/>  <span data-ttu-id="97375-149">許多混合式案例（例如分段遷移和混合式 Exchange）都是必要的</span><span class="sxs-lookup"><span data-stu-id="97375-149">Required for many hybrid scenarios such as staged migration and hybrid Exchange</span></span>  <br/>  <span data-ttu-id="97375-150">從 AD DS 同步處理安全性和擁有郵件功能的群組。</span><span class="sxs-lookup"><span data-stu-id="97375-150">Synchronizes security and mail-enabled groups from your AD DS.</span></span>  <br/> |
|||
   
- <span data-ttu-id="97375-151">不論您要如何將使用者帳戶新增至 Microsoft 365，您需要管理多個帳戶功能，例如指派授權、指定位置等等。</span><span class="sxs-lookup"><span data-stu-id="97375-151">Regardless of how you intend to add the user accounts to Microsoft 365, you need to manage several account features, such as assigning licenses, specifying location, and so on.</span></span> <span data-ttu-id="97375-152">您可以從 Microsoft 365 系統管理中心管理這些功能，也可以 [使用 PowerShell 建立使用者帳戶](https://go.microsoft.com/fwlink/p/?LinkId=717083)。</span><span class="sxs-lookup"><span data-stu-id="97375-152">These features can be managed long-term from the Microsoft 365 admin center or you can also [create user accounts with PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=717083).</span></span>
    
    <span data-ttu-id="97375-153">如果您選擇透過系統管理中心新增及管理所有使用者，您會指定位置並指派授權，建立 Microsoft 365 帳戶時。</span><span class="sxs-lookup"><span data-stu-id="97375-153">If you choose to add and manage all your users through the admin center, you will specify the location and assign licenses at the same time as creating the Microsoft 365 account.</span></span> <span data-ttu-id="97375-154">因此，不需要進行許多規劃。</span><span class="sxs-lookup"><span data-stu-id="97375-154">As a result, not much planning is required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="97375-155">在 Microsoft 365 中建立帳戶，但未指派授權 (給 SharePoint 線上，) 表示帳戶擁有者可以查看 Microsoft 365 center，但無法存取公司訂閱內的任何服務。</span><span class="sxs-lookup"><span data-stu-id="97375-155">Creating accounts in Microsoft 365 without assigning a license (to SharePoint Online, for example) means that the account owner can view the Microsoft 365 center but can't access any of the services within your company's subscription.</span></span> <span data-ttu-id="97375-156">在您指派位置和授權後，系統會將帳戶複製到您指派的服務或服務。</span><span class="sxs-lookup"><span data-stu-id="97375-156">After you assign a location and the license, the account is replicated to the service or services that you assigned.</span></span> <span data-ttu-id="97375-157">使用者可以登入其帳戶，並使用您指派給他們的服務。</span><span class="sxs-lookup"><span data-stu-id="97375-157">The user can sign in to their account and use the services that you assigned to them.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="97375-158">請參閱</span><span class="sxs-lookup"><span data-stu-id="97375-158">See also</span></span>

[<span data-ttu-id="97375-159">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="97375-159">Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users)

[<span data-ttu-id="97375-160">PowerShell</span><span class="sxs-lookup"><span data-stu-id="97375-160">PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)  
