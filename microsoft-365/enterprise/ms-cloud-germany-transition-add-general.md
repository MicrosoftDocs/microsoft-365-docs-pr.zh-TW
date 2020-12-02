---
title: 從 Microsoft Cloud Deutschland 遷移的其他一般資訊
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：從 Microsoft Cloud (德國移至 Microsoft 雲端 Deutschland 時，服務的其他一般資訊，) 新德文 datacenter 區域中的 Office 365 服務。
ms.openlocfilehash: 6fa09165f8aaa68e0f9fc567d96a4e53baaa594e
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551779"
---
# <a name="additional-general-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="bc7ff-103">從 Microsoft Cloud Deutschland 遷移的其他一般資訊</span><span class="sxs-lookup"><span data-stu-id="bc7ff-103">Additional general information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="bc7ff-104">下列各節提供有關服務、準備工作考慮和客戶經驗的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-104">The following sections provide additional information on services, pre-work considerations, and customer experience.</span></span>

## <a name="azure-active-directory"></a><span data-ttu-id="bc7ff-105">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bc7ff-105">Azure Active Directory</span></span>

<span data-ttu-id="bc7ff-106">若要完成從 Azure 德文雲端移至 Azure public 雲端，建議您在 OpenID Connect (OIDC) 端點時，將應用程式的驗證端點、Azure Active Directory (Azure AD) 圖表和 MS Graph 端點更新為商業雲端端點，然後 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 開始報告商業性雲端端點。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-106">To complete the move from the Azure German cloud to the Azure public cloud we recommend that the authentication endpoint, Azure Active Directory (Azure AD) Graph, and MS Graph endpoints for your applications be updated to those of the commercial cloud when the OpenID Connect (OIDC) endpoint, `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`, starts reporting commercial cloud endpoints.</span></span> 
 
<span data-ttu-id="bc7ff-107">**我應該在何時進行此變更？**</span><span class="sxs-lookup"><span data-stu-id="bc7ff-107">**When should I make this change?**</span></span>

<span data-ttu-id="bc7ff-108">當您的租使用者完成從德文雲端遷移至商業雲端時，您會在 Azure/Office 入口網站中收到通知。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-108">You'll receive a notification in Azure/Office portal when your tenant completes migration from German cloud to the commercial cloud.</span></span> <span data-ttu-id="bc7ff-109">收到此通知之後，您有30天的時間可完成這些更新，讓您的應用程式繼續適用于從 Azure 德國雲端遷移到 Azure Public 雲端的承租人。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-109">You have 30 days after receiving this notification to complete these updates so that your app continues to work for tenants that are migrated from Azure Germany cloud to Azure Public cloud.</span></span>
 
<span data-ttu-id="bc7ff-110">更新您的登入授權有三個前置條件：</span><span class="sxs-lookup"><span data-stu-id="bc7ff-110">There are three preconditions to updating your sign-in authority:</span></span>

 - <span data-ttu-id="bc7ff-111">您租使用者的 OIDC 探索端點會傳回 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` AZURE AD public cloud 端點。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-111">OIDC discovery endpoint for your tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returns Azure AD public cloud endpoints.</span></span>

 - <span data-ttu-id="bc7ff-112">如果您的租使用者已設定同盟，則 Active Directory Federation Services (AD FS) 會更新，以與 Azure AD Public 同步處理。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-112">If your tenant is set up for federation, Active Directory Federation Services (AD FS) is updated to sync with Azure AD Public.</span></span> <span data-ttu-id="bc7ff-113">您可以依照指示更新 Azure AD Connect 設定，以進行此變更。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-113">You can follow instructions to update Azure AD Connect settings for making this change.</span></span>

 - <span data-ttu-id="bc7ff-114">您的應用程式所使用的資源應用程式（如果有的話）會修改為接受 Azure AD 德國和 Azure AD 公用所簽署的權杖。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-114">Resource applications, if any, used by your applications are modified to accept tokens that are signed by both Azure AD Germany and Azure AD Public.</span></span>
 
<span data-ttu-id="bc7ff-115">**什麼類型的應用程式？**</span><span class="sxs-lookup"><span data-stu-id="bc7ff-115">**What kind of applications?**</span></span>

<span data-ttu-id="bc7ff-116">應用程式可能是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bc7ff-116">An application could be any of the following:</span></span>

- <span data-ttu-id="bc7ff-117">單一頁面應用程式 (SPA) </span><span class="sxs-lookup"><span data-stu-id="bc7ff-117">Single-page app (SPA)</span></span>
- <span data-ttu-id="bc7ff-118">登入使用者的 Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="bc7ff-118">Web app that signs in users</span></span>
- <span data-ttu-id="bc7ff-119">呼叫 web APIs 的 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="bc7ff-119">Web app that calls web APIs</span></span>
- <span data-ttu-id="bc7ff-120">受保護的 web API</span><span class="sxs-lookup"><span data-stu-id="bc7ff-120">Protected web API</span></span>
- <span data-ttu-id="bc7ff-121">呼叫 web APIs 的 web API</span><span class="sxs-lookup"><span data-stu-id="bc7ff-121">Web API that calls web APIs</span></span>
- <span data-ttu-id="bc7ff-122">桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="bc7ff-122">Desktop app</span></span>
- <span data-ttu-id="bc7ff-123">後臺應用程式</span><span class="sxs-lookup"><span data-stu-id="bc7ff-123">Daemon app</span></span>
- <span data-ttu-id="bc7ff-124">行動應用程式</span><span class="sxs-lookup"><span data-stu-id="bc7ff-124">Mobile app</span></span>
 
> [!NOTE] 
> <span data-ttu-id="bc7ff-125">當應用程式切換成您的授權使用時 `login.microsoftonline.com` ，會以這個新的授權單位簽署權杖。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-125">When an application switches to using `login.microsoftonline.com` as your authority, the tokens will be signed by this new authority.</span></span> <span data-ttu-id="bc7ff-126">如果您主控其他應用程式所撥打的任何資源應用程式，您將需要允許進行寬鬆的權杖驗證。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-126">If you host any resource applications that other apps call into, you will need to allow for lax token validation.</span></span> <span data-ttu-id="bc7ff-127">這表示您的應用程式必須允許 Azure AD 德國和 Azure AD 公用雲端所簽署的權杖。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-127">This means that your app needs to allow tokens that are signed by both the Azure AD Germany and Azure AD public clouds.</span></span> <span data-ttu-id="bc7ff-128">除非所有呼叫您服務的用戶端應用程式都已完全遷移至 Azure AD public cloud，否則需要進行這種寬鬆的權杖驗證。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-128">This lax token validation is needed until all client applications that call your service are fully migrated to the Azure AD public cloud.</span></span> <span data-ttu-id="bc7ff-129">遷移之後，您的資源應用程式只需要接受由 Azure AD public 雲端簽署的權杖。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-129">After migration, your resource application only needs to accept tokens signed by the Azure AD public cloud.</span></span>

<span data-ttu-id="bc7ff-130">**我需要更新哪些專案？**</span><span class="sxs-lookup"><span data-stu-id="bc7ff-130">**What do I need to update?**</span></span>

1. <span data-ttu-id="bc7ff-131">如果您是在 Azure 德國用來驗證 Azure 德國或 Office 365 德國使用者的應用程式，請確定在 `https://login.microsoftonline.com` 驗證內容中做為授權使用。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-131">If you're hosting an application in Azure Germany that is used to authenticate Azure Germany or Office 365 Germany users, ensure that `https://login.microsoftonline.com` is used as the authority in the authentication context.</span></span>

    - <span data-ttu-id="bc7ff-132">請參閱 Azure AD 驗證上下文。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-132">See Azure AD authentication contexts.</span></span>
    - <span data-ttu-id="bc7ff-133">這兩者皆適用于您的應用程式的驗證，以及對您應用程式 (呼叫的任何 APIs 的驗證，也就是 Microsoft Graph，Azure AD Graph，Azure 資源管理員) 。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-133">This applies both to authentication to your application as well as authentication to any APIs that your application may be calling (that is, Microsoft Graph, Azure AD Graph, Azure Resource Manager).</span></span>

2. <span data-ttu-id="bc7ff-134">將 Azure AD Graph 端點更新為 `https://graph.windows.net` 。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-134">Update Azure AD Graph endpoint to be `https://graph.windows.net`.</span></span>

3. <span data-ttu-id="bc7ff-135">將 MS Graph 端點更新為 `https://graph.microsoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-135">Update MS Graph endpoint to be `https://graph.microsoft.com`.</span></span>

4. <span data-ttu-id="bc7ff-136">更新任何德國 cloud 端點 (例如 Exchange Online 和 SharePoint Online) 的使用者，這些端點是應用程式用來成為公用雲端的使用者。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-136">Update any German cloud endpoints (such as those for Exchange Online and SharePoint Online) that are used by your applications to be those of the public cloud.</span></span>

5. <span data-ttu-id="bc7ff-137">更新環境參數，使其 `AzurePublic` (，而不是 `AzureGermany`) 中的系統管理工具和腳本：</span><span class="sxs-lookup"><span data-stu-id="bc7ff-137">Update environment parameters to be `AzurePublic` (instead of `AzureGermany`) in administrative tools and scripts for:</span></span>

    - <span data-ttu-id="bc7ff-138">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc7ff-138">Azure PowerShell</span></span>
    - <span data-ttu-id="bc7ff-139">Azure AD PowerShell (MSOnline) </span><span class="sxs-lookup"><span data-stu-id="bc7ff-139">Azure AD PowerShell (MSOnline)</span></span>
    - <span data-ttu-id="bc7ff-140">Azure AD PowerShell (AzureAD) </span><span class="sxs-lookup"><span data-stu-id="bc7ff-140">Azure AD PowerShell (AzureAD)</span></span>
    - <span data-ttu-id="bc7ff-141">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="bc7ff-141">Azure CLI</span></span>
 
<span data-ttu-id="bc7ff-142">**我發佈的應用程式為何？**</span><span class="sxs-lookup"><span data-stu-id="bc7ff-142">**What about applications that I publish?**</span></span>

<span data-ttu-id="bc7ff-143">如果您發佈的應用程式可供租使用者以外的使用者使用，您可能需要變更您的應用程式註冊，以確保持續性。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-143">If you publish an application that is available to users who are outside of your tenant, you may need to change your application registration to ensure continuity.</span></span> <span data-ttu-id="bc7ff-144">其他使用您應用程式的承租人的移動時間可能會與租使用者的時間不同。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-144">Other tenants that use your application may be moved at a different time than your tenant.</span></span> <span data-ttu-id="bc7ff-145">為了確保使用者永遠無法存取應用程式，您需要同意將您的應用程式從 Azure 德國同步處理到 Azure 公用。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-145">To ensure that they never lose access to your application, you'll need to consent to your app being synchronized from Azure Germany to Azure public.</span></span>

### <a name="additional-considerations"></a><span data-ttu-id="bc7ff-146">其他考量因素</span><span class="sxs-lookup"><span data-stu-id="bc7ff-146">Additional considerations</span></span>

<span data-ttu-id="bc7ff-147">以下是 Azure AD 的其他一些考慮：</span><span class="sxs-lookup"><span data-stu-id="bc7ff-147">Here are some additional considerations for Azure AD:</span></span>

- <span data-ttu-id="bc7ff-148">對於同盟驗證：</span><span class="sxs-lookup"><span data-stu-id="bc7ff-148">For federated authentication:</span></span>

  - <span data-ttu-id="bc7ff-149">當租使用者轉換為處理過程中時，您不能建立、升級或降級同盟網域。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-149">You must not create, promote, or demote a federated domain while the tenant transition is in process.</span></span> <span data-ttu-id="bc7ff-150">在完成 Azure AD 服務的遷移之後 (租使用者完全完成) ，您可以繼續管理同盟網域。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-150">After the migration to the Azure AD service is complete (the tenant is fully complete), you can resume managing federated domains.</span></span>

  - <span data-ttu-id="bc7ff-151">如果您使用的同盟驗證使用的是 Active Directory Federation Services (AD FS) ，您不應該對發行人 URIs 所做的變更，以用於與您的內部部署 Active Directory 網域服務 (AD DS) 的所有驗證。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-151">If you're using federated authentication with Active Directory Federation Services (AD FS), you shouldn't make changes to Issuer URIs used for all authentication with your on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="bc7ff-152">變更簽發者 URIs 會導致網域中的使用者驗證失敗。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-152">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="bc7ff-153">簽發者 URIs 可以直接在 AD FS 中變更，也可以在將網域從 managed 轉換成同盟時變更，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-153">Issuer URIs can be changed directly in AD FS or when a domain is converted from managed to federated and vice versa.</span></span> <span data-ttu-id="bc7ff-154">Microsoft 建議客戶不要新增、移除或轉換要遷移之 Azure AD 租使用者中的同盟網域。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-154">Microsoft recommends customers don't add, remove, or convert a federated domain in the Azure AD tenant being migrated.</span></span> <span data-ttu-id="bc7ff-155">在遷移完全完成後，可以變更發行者 URIs。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-155">Issuer URIs can be changed after the migration is fully complete.</span></span>

- <span data-ttu-id="bc7ff-156">若為網路：</span><span class="sxs-lookup"><span data-stu-id="bc7ff-156">For networking:</span></span>

  - <span data-ttu-id="bc7ff-157">在 Azure 入口網站中，建立 IPv6 命名的網路無法運作 `http://portal.microsoftazure.de/` 。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-157">Creating IPv6-named networks doesn't work in the Azure portal, `http://portal.microsoftazure.de/`.</span></span> <span data-ttu-id="bc7ff-158">使用 Azure 入口網站 `https://portal.azure.com` 建立 IPv6 命名的網路。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-158">Use the Azure portal at `https://portal.azure.com` to create IPv6-named networks.</span></span>
 
   - <span data-ttu-id="bc7ff-159">您無法為 Azure Multi-Factor 驗證建立信任的 IP 位址範圍 (MFA) Microsoft Cloud Deutschland portal 中的服務設定。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-159">You can't create trusted IP address ranges for Azure Multi-Factor Authentication (MFA) service settings from the Microsoft Cloud Deutschland portal.</span></span> <span data-ttu-id="bc7ff-160">使用 Azure AD portal for Office 365 服務來建立 Azure MFA 信任的 IP 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-160">Use the Azure AD portal for Office 365 services to create Azure MFA trusted IP address ranges.</span></span>


- <span data-ttu-id="bc7ff-161">若為條件式存取：</span><span class="sxs-lookup"><span data-stu-id="bc7ff-161">For Conditional Access:</span></span> 

  - <span data-ttu-id="bc7ff-162">在完成 [AZURE AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 遷移階段) 之後，才支援具有下列授與控制的條件式存取原則 (完成 Office 365 服務的遷移：</span><span class="sxs-lookup"><span data-stu-id="bc7ff-162">Conditional Access policies with the following grant controls aren't supported until migration to Office 365 services is complete (after the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase):</span></span>

    - <span data-ttu-id="bc7ff-163">需要相容的裝置</span><span class="sxs-lookup"><span data-stu-id="bc7ff-163">Require Compliant Device</span></span>
    - <span data-ttu-id="bc7ff-164">需要核准的應用程式</span><span class="sxs-lookup"><span data-stu-id="bc7ff-164">Require Approved App</span></span>
    - <span data-ttu-id="bc7ff-165">需要應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="bc7ff-165">Require App Protection Policy</span></span>
    
  - <span data-ttu-id="bc7ff-166">當租使用者啟用的安全性預設值為 [已停用] 或 [已存在租使用者的條件式存取原則] 時，條件式存取原則介面提供錯誤的警告。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-166">The Conditional Access policy interface gives a false warning about security defaults being enabled for the tenant even when it's disabled, and Conditional Access policies already exist for the tenant.</span></span> <span data-ttu-id="bc7ff-167">您應該忽略警告或使用 Office 365 服務入口網站來管理條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-167">You should ignore the warning or use the Office 365 services portal to manage Conditional Access policies.</span></span> 

- <span data-ttu-id="bc7ff-168">僅在租使用者遷移完成後（包括所有 office 工作負載遷移）之後，才會支援 Intune 案例。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-168">Intune scenarios are supported only against worldwide endpoints after tenant migration is complete, including all office workloads migrations.</span></span>

- <span data-ttu-id="bc7ff-169">Microsoft Cloud Deutschland 使用行動代理程式更新方法進行 MFA 要求的使用者，可看到使用者 ObjectId (GUID) ，而不是 Microsoft 驗證應用程式中的使用者主體名稱 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-169">Microsoft Cloud Deutschland users who use the Mobile App Notification method for MFA requests see the user's ObjectId (a GUID) instead of the user principal name (UPN) in the Microsoft Authenticator app.</span></span> <span data-ttu-id="bc7ff-170">在 Office 365 服務中完成 Azure AD 租使用者的遷移後，新的 Microsoft 驗證者啟用會顯示使用者的 Upn。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-170">After migration of the Azure AD tenant is complete and hosted in Office 365 services, new Microsoft Authenticator activations will display users' UPNs.</span></span> <span data-ttu-id="bc7ff-171">現有的 Microsoft 驗證者帳戶會繼續顯示使用者 ObjectId，但他們會繼續使用行動代理程式更新。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-171">Existing Microsoft Authenticator accounts will continue to display the user ObjectId, but they'll continue to work for mobile app notifications.</span></span> 

- <span data-ttu-id="bc7ff-172">針對10月 22 2019 日之後建立的承租人，當租使用者遷移至 Office 365 服務時，可能會為租使用者自動啟用安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-172">For tenants that are created after October 22, 2019, security defaults may be auto-enabled for the tenant when it's migrated to the Office 365 service.</span></span> <span data-ttu-id="bc7ff-173">租使用者管理員可以選擇讓安全性預設值保持啟用並登錄 MFA，也可以停用此功能。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-173">Tenant admins can choose to leave security defaults enabled and register for MFA, or they can disable the feature.</span></span> <span data-ttu-id="bc7ff-174">如需詳細資訊，請參閱 [停用安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-174">For more information, see [Disabling security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults).</span></span> 

  > [!NOTE]
  > <span data-ttu-id="bc7ff-175">在遷移期間，未自動啟用的組織可能會在未來自動註冊，因為啟用安全性預設值的功能會在 Office 365 服務中推出。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-175">Organizations that are not auto-enabled during migration may still be auto-enrolled in the future as the feature to enable security defaults is rolled out in the Office 365 service.</span></span> <span data-ttu-id="bc7ff-176">選擇明確停用或啟用安全性預設值的系統管理員可以在 **Azure Active Directory > 屬性** 下更新功能來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-176">Admins who choose to explicitly disable or enable security defaults may do so by updating the feature under **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="bc7ff-177">管理員明確啟用該功能之後，將不會自動啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-177">After the feature is explicitly enabled by the admin, it will not be auto-enabled.</span></span>

- <span data-ttu-id="bc7ff-178">當租使用者在遷移後，就會有關于 Office 365 德國入口網站中的 Azure AD Connect 版本和 Office 365 入口網站版本的警告。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-178">There will be warning about the version of Azure AD Connect in the Office 365 Germany portal as well as in the Office 365 portal once the tenant is in migration.</span></span> <span data-ttu-id="bc7ff-179">如果在遷移完成之後，版本警告不再顯示警告，可以忽略這種情況。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-179">This can be ignored if the version warning is no longer showing the warning after the migration is complete.</span></span> <span data-ttu-id="bc7ff-180">如果在遷移之前或之後有任何警告，請在任一入口網站中更新 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-180">If there's a warning, either before or after migration, in either portal, Azure AD Connect must be updated.</span></span> <span data-ttu-id="bc7ff-181">警告訊息說：「我們偵測到您正在使用過期的目錄同步處理工具。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-181">The warning message says: "We detected you're using an outdated directory sync tool.</span></span> <span data-ttu-id="bc7ff-182">建議您移至 Microsoft 下載中心以取得最新版本的 Azure AD Connect。」</span><span class="sxs-lookup"><span data-stu-id="bc7ff-182">We recommend you go to the Microsoft Download Center to get the latest version of Azure AD Connect."</span></span>

## <a name="exchange-online"></a><span data-ttu-id="bc7ff-183">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bc7ff-183">Exchange Online</span></span> 

- <span data-ttu-id="bc7ff-184">`myaccount.msft.com` 只會在轉換 Office 365 之後運作。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-184">`myaccount.msft.com` will only work after the cutover of Office 365.</span></span> <span data-ttu-id="bc7ff-185">連結會產生「發生錯誤」錯誤訊息，直到這段時間為止。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-185">Links will produce "something went wrong" error messages until that time.</span></span>

- <span data-ttu-id="bc7ff-186">在其他環境中存取共用信箱的 Outlook Web App 使用者 (例如，德國環境中的使用者存取全域環境中的共用信箱) 會提示您第二次驗證。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-186">Users of Outlook Web App that access a shared mailbox in the other environment (for example, a user in the Germany environment accesses a shared mailbox in the global environment) will be prompted to authenticate a second time.</span></span> <span data-ttu-id="bc7ff-187">使用者必須先驗證並存取其信箱 `outlook.office.de` ，然後開啟中的共用信箱 `outlook.office365.com` 。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-187">The user must first authenticate and access their mailbox in `outlook.office.de`, then open the shared mailbox that is in `outlook.office365.com`.</span></span> <span data-ttu-id="bc7ff-188">當存取另一個服務中所主控的共用資源時，他們將需要第二次進行驗證。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-188">They'll need to authenticate a second time when accessing the shared resources that are hosted in the other service.</span></span>

- <span data-ttu-id="bc7ff-189">針對現有的 Microsoft Cloud Deutschland 客戶或過渡中的客戶。使用檔案 > 資訊將共用信箱新增至 Outlook 時 **> 新增帳戶**，查看行事曆許可權可能會失敗 (Outlook 用戶端嘗試使用 Rest API `https://outlook.office.de/api/v2.0/Me/Calendars` 。 ) 客戶若要新增帳戶以查看行事曆許可權，您可以新增登錄機碼，如在 [outlook 中共用行事曆的使用者經驗變更](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 中所述，此動作會成功。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-189">For existing Microsoft Cloud Deutschland customers or those in transition, when a shared mailbox is added to Outlook by using **File > Info > Add Account**, viewing calendar permissions may fail (the Outlook client attempts to use the Rest API `https://outlook.office.de/api/v2.0/Me/Calendars`.) Customers who want to add an account to view calendar permissions can add the registry key as described in [User experience changes for sharing a calendar in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) to ensure this action will succeed.</span></span> <span data-ttu-id="bc7ff-190">使用群組原則，可在整個組織中部署此登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-190">This registry key can be deployed organization-wide by using Group Policy.</span></span>

- <span data-ttu-id="bc7ff-191">在遷移階段，使用 PowerShell Cmdlet **New-new-migrationendpoint**、 **Set-MigrationEndpoint** 和 **MigrationsServerAvailability** 可能會導致 proxy) 上的錯誤 (錯誤。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-191">During the migration phase, using the PowerShell cmdlets **New-migrationEndpoint**, **Set-MigrationEndpoint**, and **Test-MigrationsServerAvailability** can result in errors (error on proxy).</span></span> <span data-ttu-id="bc7ff-192">當仲裁信箱已遷移至世界，但不是由系統管理員信箱遷移時，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-192">This happens when the arbitration mailbox has migrated to worldwide but the admin mailbox hasn't or vice-versa.</span></span> <span data-ttu-id="bc7ff-193">若要解決此問題，在建立租使用者 PowerShell 會話時，請使用仲裁信箱做為 **ConnectionUri** 中的路由提示。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-193">To resolve this, while creating the tenant PowerShell session, use the arbitration mailbox as the routing hint in the **ConnectionUri**.</span></span> <span data-ttu-id="bc7ff-194">例如：`New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`</span><span class="sxs-lookup"><span data-stu-id="bc7ff-194">For example: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`</span></span>

- <span data-ttu-id="bc7ff-195">如果您使用的是 Exchange Online 混合式：</span><span class="sxs-lookup"><span data-stu-id="bc7ff-195">If you're using Exchange Online hybrid:</span></span>

    - <span data-ttu-id="bc7ff-196">您必須先重新執行混合式設定向導 (HCW) 以在轉換之前更新 Microsoft Cloud Deutschland 的內部部署設定，然後在 Office 365 服務時重新執行 HCW。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-196">You must rerun the Hybrid Configuration wizard (HCW) to update on-premises configuration against Microsoft Cloud Deutschland before the transition, and rerun the HCW upon cleanup against the Office 365 services.</span></span> <span data-ttu-id="bc7ff-197">如果您使用自訂網域，可能需要其他的 DNS 更新。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-197">Additional DNS updates may be required if you use custom domains.</span></span>

<span data-ttu-id="bc7ff-198">如需在此工作負載遷移階段中所需動作的相關資訊，或有關管理或使用影響的詳細資訊，請參閱 Exchange Online 中的 [遷移階段動作和影響](ms-cloud-germany-transition-phases.md#exchange-online)的章節。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-198">For more information about actions that are required during the migration phase of this workload or about the impact to administration or usage, review the Exchange Online section of [Migration phases actions and impacts](ms-cloud-germany-transition-phases.md#exchange-online).</span></span>

## <a name="office-services"></a><span data-ttu-id="bc7ff-199">Office 服務</span><span class="sxs-lookup"><span data-stu-id="bc7ff-199">Office Services</span></span>

<span data-ttu-id="bc7ff-200">Office 中最近使用 (MRU) 服務，是從德國服務切換至 Office 365 服務，而不是遷移。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-200">The most recently used (MRU) service in Office is a cutover from the Germany service to Office 365 services, not a migration.</span></span> <span data-ttu-id="bc7ff-201">從 Office.com 入口網站遷移後，只會顯示從 Office 365 服務端的 MRU 連結。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-201">Only MRU links from the Office 365 services side will be visible after migration from the Office.com portal.</span></span> <span data-ttu-id="bc7ff-202">來自德國服務的 MRU 連結在 Office 365 服務中不會顯示為 MRU 連結。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-202">MRU links from the Germany service aren't visible as MRU links in Office 365 services.</span></span> <span data-ttu-id="bc7ff-203">在 Office 365 中，只有在完成承租人遷移後，才能存取 MRU 連結。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-203">In Office 365, MRU links are accessible only after the tenant migration is complete.</span></span>

## <a name="sharepoint-online-and-onedrive"></a><span data-ttu-id="bc7ff-204">線上 SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="bc7ff-204">SharePoint Online and OneDrive</span></span>

- <span data-ttu-id="bc7ff-205">當 SharePoint Online 移轉到德國區域完成後，會重新建立資料索引。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-205">Upon completion of the SharePoint Online migration to the German region, data indexes are rebuilt.</span></span> <span data-ttu-id="bc7ff-206">與搜尋索引相依的功能可能會受到影響時重建索引完成。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-206">Features that are dependent on search indexes may be affected while reindexing completes.</span></span>

- <span data-ttu-id="bc7ff-207">如果您的組織仍然使用 SharePoint 2010 工作流程，他們將無法再在 2021 12 月31日之後運作。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-207">If your organization still uses SharePoint 2010 workflows, they'll no longer function after December 31, 2021.</span></span> <span data-ttu-id="bc7ff-208">SharePoint 2013 工作流程仍然受到支援，不過預設為從 2020 1 月1日開始的新承租人關閉。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-208">SharePoint 2013 workflows will remain supported, although turned off by default for new tenants starting on November 1, 2020.</span></span> <span data-ttu-id="bc7ff-209">在完成 SharePoint 線上服務的遷移之後，建議您移至 [電源自動化] 或其他支援的解決方案。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-209">After migration to the SharePoint Online service is complete, we recommend that you to move to Power Automate or other supported solutions.</span></span>

- <span data-ttu-id="bc7ff-210">OneDrive 遷移至德文地區後，就會重建資料索引。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-210">Upon completion of the OneDrive migration to the German region, data indexes are rebuilt.</span></span> <span data-ttu-id="bc7ff-211">在建立索引的過程中，取決於搜尋索引的功能可能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-211">Features that depend on search indexes may be affected while reindexing is in progress.</span></span>


## <a name="more-information"></a><span data-ttu-id="bc7ff-212">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="bc7ff-212">More information</span></span>

<span data-ttu-id="bc7ff-213">開始：</span><span class="sxs-lookup"><span data-stu-id="bc7ff-213">Getting started:</span></span>

- [<span data-ttu-id="bc7ff-214">從 Microsoft Cloud Deutschland 遷移至新德文 datacenter 區域中的 Office 365 服務</span><span class="sxs-lookup"><span data-stu-id="bc7ff-214">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="bc7ff-215">Microsoft Cloud Deutschland 移轉協助</span><span class="sxs-lookup"><span data-stu-id="bc7ff-215">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="bc7ff-216">如何選擇加入移轉</span><span class="sxs-lookup"><span data-stu-id="bc7ff-216">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="bc7ff-217">遷移期間的客戶體驗</span><span class="sxs-lookup"><span data-stu-id="bc7ff-217">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="bc7ff-218">在轉換中移動：</span><span class="sxs-lookup"><span data-stu-id="bc7ff-218">Moving through the transition:</span></span>

- [<span data-ttu-id="bc7ff-219">遷移階段的動作和影響</span><span class="sxs-lookup"><span data-stu-id="bc7ff-219">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="bc7ff-220">其他預備工作</span><span class="sxs-lookup"><span data-stu-id="bc7ff-220">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="bc7ff-221">[服務](ms-cloud-germany-transition-add-general.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-221">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="bc7ff-222">雲端應用程式：</span><span class="sxs-lookup"><span data-stu-id="bc7ff-222">Cloud apps:</span></span>

- [<span data-ttu-id="bc7ff-223">Dynamics 365 的移轉程式資訊</span><span class="sxs-lookup"><span data-stu-id="bc7ff-223">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="bc7ff-224">Power BI 移轉程式資訊</span><span class="sxs-lookup"><span data-stu-id="bc7ff-224">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="bc7ff-225">開始升級您的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bc7ff-225">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
