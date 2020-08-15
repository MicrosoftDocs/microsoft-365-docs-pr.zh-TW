---
title: 管理 Microsoft 365 使用者帳戶的工具
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
description: 瞭解使用哪些工具，以及如何管理 Microsoft 365 帳戶。
ms.openlocfilehash: 205c61c0cff896f93069d225c84dc3086ca30eb5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688747"
---
# <a name="tools-to-manage-microsoft-365-user-accounts"></a><span data-ttu-id="09790-103">管理 Microsoft 365 使用者帳戶的工具</span><span class="sxs-lookup"><span data-stu-id="09790-103">Tools to manage Microsoft 365 user accounts</span></span>

<span data-ttu-id="09790-104">您可以根據您的設定，以數種不同的方式管理 Microsoft 365 使用者。</span><span class="sxs-lookup"><span data-stu-id="09790-104">You can manage Microsoft 365 users in several different ways, depending on your configuration.</span></span> <span data-ttu-id="09790-105">您可以在 [Microsoft 365 系統管理中心](https://admin.microsoft.com)、Windows PowerShell、Active Directory 網域服務 (AD DS) 或 Azure Active Directory (azure AD) 管理入口網站中管理使用者。</span><span class="sxs-lookup"><span data-stu-id="09790-105">You can manage users in the [Microsoft 365 admin center](https://admin.microsoft.com), Windows PowerShell, in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin portal.</span></span> 

<span data-ttu-id="09790-106">一旦您購買 Microsoft 365，系統管理中心和 Windows PowerShell 便可用於管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="09790-106">As soon as you purchase Microsoft 365, the admin center and Windows PowerShell can be used to manage accounts.</span></span> <span data-ttu-id="09790-107">在管理雲端身分識別時，組織中的每個人都有個別的使用者識別碼和密碼，適用于 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="09790-107">When managing cloud identities, every person in your organization has a separate user ID and password for Microsoft 365.</span></span> <span data-ttu-id="09790-108">如果您想要與您的內部部署基礎結構整合，並讓使用者帳戶與 Microsoft 365 同步，您可以使用 Azure AD Connect，針對單一登入功能，提供身分識別和密碼的同步處理。</span><span class="sxs-lookup"><span data-stu-id="09790-108">If you want to integrate with your on-premises infrastructure and have user accounts synchronized with Microsoft 365, you can use Azure AD Connect to provide synchronization of identities and passwords for single sign-on functionality.</span></span>
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a><span data-ttu-id="09790-109">規劃管理使用者帳戶的位置和方式</span><span class="sxs-lookup"><span data-stu-id="09790-109">Plan for where and how you will manage your user accounts</span></span>

<span data-ttu-id="09790-110">您可以管理使用者帳戶的位置和方式，取決於您要用於 Microsoft 365 的身分識別模型。</span><span class="sxs-lookup"><span data-stu-id="09790-110">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="09790-111">這兩個整體模型為雲端驗證及同盟驗證。</span><span class="sxs-lookup"><span data-stu-id="09790-111">The two overall models are cloud authentication and federated authentication.</span></span>
  
### <a name="cloud-authentication"></a><span data-ttu-id="09790-112">雲端驗證</span><span class="sxs-lookup"><span data-stu-id="09790-112">Cloud authentication</span></span>

- <span data-ttu-id="09790-113">雲端驗證-建立及管理 Microsoft 365 系統管理中心中的使用者。</span><span class="sxs-lookup"><span data-stu-id="09790-113">Cloud authentication - Create and manage users in the Microsoft 365 admin center.</span></span> <span data-ttu-id="09790-114">您也可以使用 Windows PowerShell 或 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="09790-114">You can also use Windows PowerShell or Azure AD .</span></span> 
    
- <span data-ttu-id="09790-115">密碼雜湊同步處理 (PHS) 具有無縫單一登入-在 Azure AD 中啟用 AD DS 物件的驗證的最簡單方式。</span><span class="sxs-lookup"><span data-stu-id="09790-115">Password hash sync (PHS) with seamless single sign-on - The simplest way to enable authentication for AD DS objects in Azure AD.</span></span> <span data-ttu-id="09790-116">透過 PHS，您可以將 AD DS 使用者帳戶物件與 Microsoft 365 同步處理，並管理您的使用者內部部署。</span><span class="sxs-lookup"><span data-stu-id="09790-116">With PHS, you synchronize your AD DS user account objects with Microsoft 365 and manage your users on-premises.</span></span> 
    
- <span data-ttu-id="09790-117">透過無縫單一登入的傳遞驗證 (PTA) 使用一或多個內部部署伺服器上執行的軟體代理程式，為 Azure AD 驗證服務提供簡單的密碼驗證，以直接在您的 AD DS 驗證使用者。</span><span class="sxs-lookup"><span data-stu-id="09790-117">Pass-through authentication (PTA) with seamless single sign-on - Provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> 
    
### <a name="federated-authentication"></a><span data-ttu-id="09790-118">同盟驗證</span><span class="sxs-lookup"><span data-stu-id="09790-118">Federated authentication</span></span>

- <span data-ttu-id="09790-119">同盟驗證選項-主要針對具有更複雜驗證需求的大型企業組織，AD DS 物件會與 Microsoft 365 同步處理，而且使用者帳戶是在內部部署管理。</span><span class="sxs-lookup"><span data-stu-id="09790-119">Federated authentication options - Primarily for large enterprise organizations with more complex authentication requirements, AD DS objects are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> 
    
- <span data-ttu-id="09790-120">[協力廠商驗證和身分識別提供者](about-microsoft-365-identity.md) -AD DS 物件可同步處理至 Microsoft 365，而雲端資源存取主要是由協力廠商身分識別提供者 (IDP) 所管理。</span><span class="sxs-lookup"><span data-stu-id="09790-120">[Third-party authentication and identity providers](about-microsoft-365-identity.md) - AD DS objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IDP).</span></span> 
    
## <a name="managing-accounts"></a><span data-ttu-id="09790-121">管理帳戶</span><span class="sxs-lookup"><span data-stu-id="09790-121">Managing Accounts</span></span>

<span data-ttu-id="09790-122">決定組織建立及管理帳戶的方式時，請考慮下列需求：</span><span class="sxs-lookup"><span data-stu-id="09790-122">When deciding which way your organization will create and manage accounts, consider the following requirements:</span></span>
  
- <span data-ttu-id="09790-123">在內部部署環境中的伺服器上，必須安裝目錄同步作業軟體，以連接 Microsoft 365 和您的 AD DS 之間的身分識別。</span><span class="sxs-lookup"><span data-stu-id="09790-123">The directory synchronization software needs to be installed on servers within your on-premises environment to connect the identities between Microsoft 365 and your AD DS.</span></span>
    
- <span data-ttu-id="09790-124">任何目錄同步處理選項（包括 SSO 選項）都需要您的 AD DS 屬性符合標準。</span><span class="sxs-lookup"><span data-stu-id="09790-124">Any directory synchronization option, including SSO options, requires your AD DS attributes meet standards.</span></span> <span data-ttu-id="09790-125">您的目錄中所使用之屬性的詳細資訊，以及 (如果需要的任何) ，將在 [準備透過目錄同步作業將使用者布建至 Microsoft 365](prepare-for-directory-synchronization.md)時所述的清除作業。</span><span class="sxs-lookup"><span data-stu-id="09790-125">The specifics of what attributes are used in your directory and what cleanup (if any) is needed are described in [Prepare to provision users through directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span> 
    
- <span data-ttu-id="09790-126">規劃如何建立 Microsoft 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="09790-126">Plan how you are going to create Microsoft 365 accounts.</span></span>
    
    <span data-ttu-id="09790-127">下表列出不同的帳戶管理工具。</span><span class="sxs-lookup"><span data-stu-id="09790-127">The following table lists the different account management tools.</span></span>
    
|<span data-ttu-id="09790-128">**選項**</span><span class="sxs-lookup"><span data-stu-id="09790-128">**Option**</span></span>|<span data-ttu-id="09790-129">**附註**</span><span class="sxs-lookup"><span data-stu-id="09790-129">**Notes**</span></span>|
|:-----|:-----|
|<span data-ttu-id="09790-130">系統管理中心</span><span class="sxs-lookup"><span data-stu-id="09790-130">Admin center</span></span>  <br/> |[<span data-ttu-id="09790-131">個別或大量新增使用者</span><span class="sxs-lookup"><span data-stu-id="09790-131">Add users individually or in bulk</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  <span data-ttu-id="09790-132">提供簡單的 web 介面來新增及變更使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="09790-132">Provides a simple web interface to add and change user accounts.</span></span>  <br/>  <span data-ttu-id="09790-133">如果啟用目錄同步處理，則無法用來變更使用者 (位置和授權指派可以設定) 。</span><span class="sxs-lookup"><span data-stu-id="09790-133">Can't be used to change users if directory synchronization is enabled (location and license assignment can be set).</span></span>  <br/>  <span data-ttu-id="09790-134">無法與 SSO 選項搭配使用。</span><span class="sxs-lookup"><span data-stu-id="09790-134">Can't be used with SSO options.</span></span>  <br/> |
|<span data-ttu-id="09790-135">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="09790-135">Windows PowerShell</span></span>  <br/> |[<span data-ttu-id="09790-136">使用 Windows PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="09790-136">Manage Microsoft 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  <span data-ttu-id="09790-137">可讓您使用 Windows PowerShell 腳本，在大量使用者中新增使用者。</span><span class="sxs-lookup"><span data-stu-id="09790-137">Allows you to add users in bulk users by using a Windows PowerShell script.</span></span>  <br/>  <span data-ttu-id="09790-138">可用於將位置和授權指派給帳戶，不論帳戶是如何建立的。</span><span class="sxs-lookup"><span data-stu-id="09790-138">Can be used to assign location and licenses to accounts, regardless of how the accounts are created.</span></span>  <br/> |
|<span data-ttu-id="09790-139">大量匯入</span><span class="sxs-lookup"><span data-stu-id="09790-139">Bulk import</span></span>  <br/> |[<span data-ttu-id="09790-140">同時新增多個使用者</span><span class="sxs-lookup"><span data-stu-id="09790-140">Add several users at the same time</span></span>](add-several-users-at-the-same-time.md) <br/>  <span data-ttu-id="09790-141">可讓您匯入 CSV 檔案，將使用者群組新增至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="09790-141">Allows you to import a CSV file to add a group of users to Microsoft 365.</span></span>  <br/>  <span data-ttu-id="09790-142">無法與 SSO 選項搭配使用。</span><span class="sxs-lookup"><span data-stu-id="09790-142">Can't be used with SSO options.</span></span>  <br/> |
|<span data-ttu-id="09790-143">Azure AD</span><span class="sxs-lookup"><span data-stu-id="09790-143">Azure AD</span></span>  <br/> |<span data-ttu-id="09790-144">您可以使用 Microsoft 365 訂閱取得免費的 Azure AD 版本。</span><span class="sxs-lookup"><span data-stu-id="09790-144">You get a free edition of Azure AD with your Microsoft 365 subscription.</span></span> <span data-ttu-id="09790-145">您可以執行雲端使用者自助密碼重設的功能，以及使用免費版本自訂登入和存取面板頁面。</span><span class="sxs-lookup"><span data-stu-id="09790-145">You can perform functions like self-service password reset for cloud users, and customization of the Sign-in and Access Panel pages by using the free edition.</span></span> <span data-ttu-id="09790-146">若要取得增強的功能，您可以升級至 basic edition、Azure AD Premium P1 或 Azure AD Premium P2。</span><span class="sxs-lookup"><span data-stu-id="09790-146">To get enhanced functionality, you can upgrade to the basic edition, Azure AD Premium P1, or Azure AD Premium P2.</span></span> <span data-ttu-id="09790-147">如需支援的功能清單，請參閱 [AZURE AD edition](https://go.microsoft.com/fwlink/p/?LinkId=698465) 。</span><span class="sxs-lookup"><span data-stu-id="09790-147">See [Azure AD editions](https://go.microsoft.com/fwlink/p/?LinkId=698465) for the list of supported features.</span></span>  <br/> |
|<span data-ttu-id="09790-148">目錄同步處理</span><span class="sxs-lookup"><span data-stu-id="09790-148">Directory synchronization</span></span>  <br/> |[<span data-ttu-id="09790-149">整合您的內部部署身分識別與 Azure AD</span><span class="sxs-lookup"><span data-stu-id="09790-149">Integrating your on-premises identities with Azure AD</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  <span data-ttu-id="09790-150">若要使用或不使用密碼同步處理的目錄同步處理，請使用 [AZURE AD Connect with express 設定](https://go.microsoft.com/fwlink/p/?LinkID=698537)。</span><span class="sxs-lookup"><span data-stu-id="09790-150">For directory synchronization with or without password synchronization, use [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkID=698537).</span></span>  <br/>  <span data-ttu-id="09790-151">若為多個樹系和 SSO 選項，請使用 [自訂的 AZURE AD Connect 安裝](https://go.microsoft.com/fwlink/p/?LinkId=698430)。</span><span class="sxs-lookup"><span data-stu-id="09790-151">For multiple forests and SSO options, use [Custom Installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span></span>  <br/>  <span data-ttu-id="09790-152">提供啟用 SSO 所需的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="09790-152">Provides the infrastructure that's necessary to enable SSO.</span></span>  <br/>  <span data-ttu-id="09790-153">許多混合式案例的必要專案：</span><span class="sxs-lookup"><span data-stu-id="09790-153">Required for many hybrid scenarios:</span></span>  <br/>  <span data-ttu-id="09790-154">分段移轉</span><span class="sxs-lookup"><span data-stu-id="09790-154">Staged migration</span></span>  <br/>  <span data-ttu-id="09790-155">混合式 Exchange</span><span class="sxs-lookup"><span data-stu-id="09790-155">Hybrid Exchange</span></span>  <br/>  <span data-ttu-id="09790-156">從 AD DS 同步處理安全性和擁有郵件功能的群組。</span><span class="sxs-lookup"><span data-stu-id="09790-156">Synchronizes security and mail-enabled groups from your AD DS.</span></span>  <br/> |
   
- <span data-ttu-id="09790-157">不論您要如何將使用者帳戶新增至 Microsoft 365，您需要管理多個帳戶功能，例如指派授權、指定位置等等。</span><span class="sxs-lookup"><span data-stu-id="09790-157">Regardless of how you intend to add the user accounts to Microsoft 365, you need to manage several account features, such as assigning licenses, specifying location, and so on.</span></span> <span data-ttu-id="09790-158">您可以從系統管理中心管理這些功能，也可以 [使用 PowerShell 建立使用者帳戶](https://go.microsoft.com/fwlink/p/?LinkId=717083)。</span><span class="sxs-lookup"><span data-stu-id="09790-158">These features can be managed long-term from the admin center or you can also [create user accounts with PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=717083).</span></span>
    
    <span data-ttu-id="09790-159">如果您選擇透過系統管理中心新增及管理所有使用者，您會指定位置並指派授權，建立 Microsoft 365 帳戶時。</span><span class="sxs-lookup"><span data-stu-id="09790-159">If you choose to add and manage all your users through the admin center, you will specify the location and assign licenses at the same time as creating the Microsoft 365 account.</span></span> <span data-ttu-id="09790-160">因此，不需要進行許多規劃。</span><span class="sxs-lookup"><span data-stu-id="09790-160">As a result, not much planning is required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="09790-161">在 Microsoft 365 中建立帳戶，但未指派授權 (給 SharePoint 線上，) 表示帳戶擁有者可以查看 Microsoft 365 center，但無法存取公司訂閱內的任何服務。</span><span class="sxs-lookup"><span data-stu-id="09790-161">Creating accounts in Microsoft 365 without assigning a license (to SharePoint Online, for example) means that the account owner can view the Microsoft 365 center but can't access any of the services within your company's subscription.</span></span> <span data-ttu-id="09790-162">在您指派位置和授權後，系統會將帳戶複製到您指派的服務或服務。</span><span class="sxs-lookup"><span data-stu-id="09790-162">After you assign a location and the license, the account is replicated to the service or services that you assigned.</span></span> <span data-ttu-id="09790-163">使用者可以登入其帳戶，並使用您指派給他們的服務。</span><span class="sxs-lookup"><span data-stu-id="09790-163">The user can sign in to their account and use the services that you assigned to them.</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="09790-164">後續步驟</span><span class="sxs-lookup"><span data-stu-id="09790-164">Next steps</span></span>

[<span data-ttu-id="09790-165">Microsoft 365 與內部部署環境的整合</span><span class="sxs-lookup"><span data-stu-id="09790-165">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
## <a name="see-also"></a><span data-ttu-id="09790-166">另請參閱</span><span class="sxs-lookup"><span data-stu-id="09790-166">See Also</span></span>

[<span data-ttu-id="09790-167">管理 Microsoft 365 中的使用者和群組</span><span class="sxs-lookup"><span data-stu-id="09790-167">Manage users and groups in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users)
  
