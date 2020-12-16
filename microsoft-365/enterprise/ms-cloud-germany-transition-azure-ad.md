---
title: 從 Microsoft Cloud Deutschland 進行遷移的其他 Azure Active Directory 資訊
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
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
description: 摘要：從 Microsoft Cloud 德國移動 (Microsoft Cloud Deutschland) 到新德文 datacenter 區域中的 Office 365 服務時，其他 Azure Active Directory 資訊。
ms.openlocfilehash: 4fc5dda95e5e7afc4d69141a9a4debd0a74c492b
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688742"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="bd0b5-103">從 Microsoft Cloud Deutschland 進行遷移的其他 Azure Active Directory 資訊</span><span class="sxs-lookup"><span data-stu-id="bd0b5-103">Additional Azure Active Directory information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="bd0b5-104">若要完成從 Azure 德文雲端移至 Azure public 雲端，建議您在 OpenID Connect (OIDC) 端點時，將應用程式的驗證端點、Azure Active Directory (Azure AD) 圖表和 MS Graph 端點更新為商業雲端端點，然後 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 開始報告商業性雲端端點。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-104">To complete the move from the Azure German cloud to the Azure public cloud we recommend that the authentication endpoint, Azure Active Directory (Azure AD) Graph, and MS Graph endpoints for your applications be updated to those of the commercial cloud when the OpenID Connect (OIDC) endpoint, `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`, starts reporting commercial cloud endpoints.</span></span> 
 
<span data-ttu-id="bd0b5-105">**我應該在何時進行此變更？**</span><span class="sxs-lookup"><span data-stu-id="bd0b5-105">**When should I make this change?**</span></span>

<span data-ttu-id="bd0b5-106">當您的租使用者完成從德文雲端遷移至商業雲端時，您會在 Azure/Office 入口網站中收到通知。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-106">You'll receive a notification in Azure/Office portal when your tenant completes migration from German cloud to the commercial cloud.</span></span> <span data-ttu-id="bd0b5-107">收到此通知之後，您有30天的時間可完成這些更新，讓您的應用程式繼續適用于從 Azure 德國雲端遷移到 Azure Public 雲端的承租人。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-107">You have 30 days after receiving this notification to complete these updates so that your app continues to work for tenants that are migrated from Azure Germany cloud to Azure Public cloud.</span></span>
 
<span data-ttu-id="bd0b5-108">更新您的登入授權有三個前置條件：</span><span class="sxs-lookup"><span data-stu-id="bd0b5-108">There are three preconditions to updating your sign-in authority:</span></span>

 - <span data-ttu-id="bd0b5-109">您租使用者的 OIDC 探索端點會傳回 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` AZURE AD public cloud 端點。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-109">OIDC discovery endpoint for your tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returns Azure AD public cloud endpoints.</span></span>

 - <span data-ttu-id="bd0b5-110">如果您的租使用者已設定同盟，則 Active Directory Federation Services (AD FS) 會更新，以與 Azure AD Public 同步處理。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-110">If your tenant is set up for federation, Active Directory Federation Services (AD FS) is updated to sync with Azure AD Public.</span></span> <span data-ttu-id="bd0b5-111">您可以依照指示更新 Azure AD Connect 設定，以進行此變更。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-111">You can follow instructions to update Azure AD Connect settings for making this change.</span></span>

 - <span data-ttu-id="bd0b5-112">您的應用程式所使用的資源應用程式（如果有的話）會修改為接受 Azure AD 德國和 Azure AD 公用所簽署的權杖。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-112">Resource applications, if any, used by your applications are modified to accept tokens that are signed by both Azure AD Germany and Azure AD Public.</span></span>
 
<span data-ttu-id="bd0b5-113">**什麼類型的應用程式？**</span><span class="sxs-lookup"><span data-stu-id="bd0b5-113">**What kind of applications?**</span></span>

<span data-ttu-id="bd0b5-114">應用程式可能是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bd0b5-114">An application could be any of the following:</span></span>

- [<span data-ttu-id="bd0b5-115">單一頁面應用程式 (SPA) </span><span class="sxs-lookup"><span data-stu-id="bd0b5-115">Single-page app (SPA)</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [<span data-ttu-id="bd0b5-116">登入使用者的 Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="bd0b5-116">Web app that signs in users</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [<span data-ttu-id="bd0b5-117">呼叫 web APIs 的 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="bd0b5-117">Web app that calls web APIs</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [<span data-ttu-id="bd0b5-118">受保護的 web API</span><span class="sxs-lookup"><span data-stu-id="bd0b5-118">Protected web API</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [<span data-ttu-id="bd0b5-119">呼叫 web APIs 的 web API</span><span class="sxs-lookup"><span data-stu-id="bd0b5-119">Web API that calls web APIs</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [<span data-ttu-id="bd0b5-120">桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="bd0b5-120">Desktop app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [<span data-ttu-id="bd0b5-121">後臺應用程式</span><span class="sxs-lookup"><span data-stu-id="bd0b5-121">Daemon app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [<span data-ttu-id="bd0b5-122">行動應用程式</span><span class="sxs-lookup"><span data-stu-id="bd0b5-122">Mobile app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> <span data-ttu-id="bd0b5-123">當應用程式切換成您的授權使用時 `login.microsoftonline.com` ，會以這個新的授權單位簽署權杖。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-123">When an application switches to using `login.microsoftonline.com` as your authority, the tokens will be signed by this new authority.</span></span> <span data-ttu-id="bd0b5-124">如果您主控其他應用程式所撥打的任何資源應用程式，您將需要允許進行寬鬆的權杖驗證。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-124">If you host any resource applications that other apps call into, you will need to allow for lax token validation.</span></span> <span data-ttu-id="bd0b5-125">這表示您的應用程式必須允許 Azure AD 德國和 Azure AD 公用雲端所簽署的權杖。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-125">This means that your app needs to allow tokens that are signed by both the Azure AD Germany and Azure AD public clouds.</span></span> <span data-ttu-id="bd0b5-126">除非所有呼叫您服務的用戶端應用程式都已完全遷移至 Azure AD public cloud，否則需要進行這種寬鬆的權杖驗證。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-126">This lax token validation is needed until all client applications that call your service are fully migrated to the Azure AD public cloud.</span></span> <span data-ttu-id="bd0b5-127">遷移之後，您的資源應用程式只需要接受由 Azure AD public 雲端簽署的權杖。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-127">After migration, your resource application only needs to accept tokens signed by the Azure AD public cloud.</span></span>

<span data-ttu-id="bd0b5-128">**我需要更新哪些專案？**</span><span class="sxs-lookup"><span data-stu-id="bd0b5-128">**What do I need to update?**</span></span>

1. <span data-ttu-id="bd0b5-129">如果您是在 Azure 德國用來驗證 Azure 德國或 Office 365 德國使用者的應用程式，請確定在 `https://login.microsoftonline.com` 驗證內容中做為授權使用。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-129">If you're hosting an application in Azure Germany that is used to authenticate Azure Germany or Office 365 Germany users, ensure that `https://login.microsoftonline.com` is used as the authority in the authentication context.</span></span>

    - <span data-ttu-id="bd0b5-130">請參閱 Azure AD 驗證上下文。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-130">See Azure AD authentication contexts.</span></span>
    - <span data-ttu-id="bd0b5-131">這兩者皆適用于您的應用程式的驗證，以及對您應用程式 (呼叫的任何 APIs 的驗證，也就是 Microsoft Graph，Azure AD Graph，Azure 資源管理員) 。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-131">This applies both to authentication to your application as well as authentication to any APIs that your application may be calling (that is, Microsoft Graph, Azure AD Graph, Azure Resource Manager).</span></span>

2. <span data-ttu-id="bd0b5-132">將 Azure AD Graph 端點更新為 `https://graph.windows.net` 。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-132">Update Azure AD Graph endpoint to be `https://graph.windows.net`.</span></span>

3. <span data-ttu-id="bd0b5-133">將 MS Graph 端點更新為 `https://graph.microsoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-133">Update MS Graph endpoint to be `https://graph.microsoft.com`.</span></span>

4. <span data-ttu-id="bd0b5-134">更新任何德國 cloud 端點 (例如 Exchange Online 和 SharePoint Online) 的使用者，這些端點是應用程式用來成為公用雲端的使用者。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-134">Update any German cloud endpoints (such as those for Exchange Online and SharePoint Online) that are used by your applications to be those of the public cloud.</span></span>

5. <span data-ttu-id="bd0b5-135">更新環境參數，使其 `AzurePublic` (，而不是 `AzureGermany`) 中的系統管理工具和腳本：</span><span class="sxs-lookup"><span data-stu-id="bd0b5-135">Update environment parameters to be `AzurePublic` (instead of `AzureGermany`) in administrative tools and scripts for:</span></span>

    - [<span data-ttu-id="bd0b5-136">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd0b5-136">Azure PowerShell</span></span>](https://docs.microsoft.com/powershell/azure/install-az-ps)
    - [<span data-ttu-id="bd0b5-137">Azure AD PowerShell (MSOnline) </span><span class="sxs-lookup"><span data-stu-id="bd0b5-137">Azure AD PowerShell (MSOnline)</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/overview)
    - [<span data-ttu-id="bd0b5-138">Azure AD PowerShell (AzureAD) </span><span class="sxs-lookup"><span data-stu-id="bd0b5-138">Azure AD PowerShell (AzureAD)</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?)
    - [<span data-ttu-id="bd0b5-139">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="bd0b5-139">Azure CLI</span></span>](https://docs.microsoft.com/cli/azure/install-azure-cli)
 
<span data-ttu-id="bd0b5-140">**我發佈的應用程式為何？**</span><span class="sxs-lookup"><span data-stu-id="bd0b5-140">**What about applications that I publish?**</span></span>

<span data-ttu-id="bd0b5-141">如果您發佈的應用程式可供租使用者以外的使用者使用，您可能需要變更您的應用程式註冊，以確保持續性。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-141">If you publish an application that is available to users who are outside of your tenant, you may need to change your application registration to ensure continuity.</span></span> <span data-ttu-id="bd0b5-142">其他使用您應用程式的承租人的移動時間可能會與租使用者的時間不同。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-142">Other tenants that use your application may be moved at a different time than your tenant.</span></span> <span data-ttu-id="bd0b5-143">為了確保使用者永遠無法存取應用程式，您需要同意將您的應用程式從 Azure 德國同步處理到 Azure 公用。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-143">To ensure that they never lose access to your application, you'll need to consent to your app being synchronized from Azure Germany to Azure public.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="bd0b5-144">其他考量因素</span><span class="sxs-lookup"><span data-stu-id="bd0b5-144">Additional considerations</span></span>

<span data-ttu-id="bd0b5-145">以下是 Azure AD 的其他一些考慮：</span><span class="sxs-lookup"><span data-stu-id="bd0b5-145">Here are some additional considerations for Azure AD:</span></span>

- <span data-ttu-id="bd0b5-146">對於同盟驗證：</span><span class="sxs-lookup"><span data-stu-id="bd0b5-146">For federated authentication:</span></span>

  - <span data-ttu-id="bd0b5-147">當租使用者轉換為處理過程中時，您不能建立、升級或降級同盟網域。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-147">You must not create, promote, or demote a federated domain while the tenant transition is in process.</span></span> <span data-ttu-id="bd0b5-148">在完成 Azure AD 服務的遷移之後 (租使用者完全完成) ，您可以繼續管理同盟網域。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-148">After the migration to the Azure AD service is complete (the tenant is fully complete), you can resume managing federated domains.</span></span>

  - <span data-ttu-id="bd0b5-149">如果您使用的同盟驗證使用的是 Active Directory Federation Services (AD FS) ，您不應該對發行人 URIs 所做的變更，以用於與您的內部部署 Active Directory 網域服務 (AD DS) 的所有驗證。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-149">If you're using federated authentication with Active Directory Federation Services (AD FS), you shouldn't make changes to Issuer URIs used for all authentication with your on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="bd0b5-150">變更簽發者 URIs 會導致網域中的使用者驗證失敗。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-150">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="bd0b5-151">簽發者 URIs 可以直接在 AD FS 中變更，也可以在將網域從 managed 轉換成同盟時變更，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-151">Issuer URIs can be changed directly in AD FS or when a domain is converted from managed to federated and vice versa.</span></span> <span data-ttu-id="bd0b5-152">Microsoft 建議客戶不要新增、移除或轉換要遷移之 Azure AD 租使用者中的同盟網域。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-152">Microsoft recommends customers don't add, remove, or convert a federated domain in the Azure AD tenant being migrated.</span></span> <span data-ttu-id="bd0b5-153">在遷移完全完成後，可以變更發行者 URIs。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-153">Issuer URIs can be changed after the migration is fully complete.</span></span>

- <span data-ttu-id="bd0b5-154">若為網路：</span><span class="sxs-lookup"><span data-stu-id="bd0b5-154">For networking:</span></span>

  - <span data-ttu-id="bd0b5-155">在 Azure 入口網站中，建立 IPv6 命名的網路無法運作 `http://portal.microsoftazure.de/` 。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-155">Creating IPv6-named networks doesn't work in the Azure portal, `http://portal.microsoftazure.de/`.</span></span> <span data-ttu-id="bd0b5-156">使用 Azure 入口網站 `https://portal.azure.com` 建立 IPv6 命名的網路。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-156">Use the Azure portal at `https://portal.azure.com` to create IPv6-named networks.</span></span>
 
   - <span data-ttu-id="bd0b5-157">您無法為 Azure Multi-Factor 驗證建立信任的 IP 位址範圍 (MFA) Microsoft Cloud Deutschland portal 中的服務設定。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-157">You can't create trusted IP address ranges for Azure Multi-Factor Authentication (MFA) service settings from the Microsoft Cloud Deutschland portal.</span></span> <span data-ttu-id="bd0b5-158">使用 Azure AD portal for Office 365 服務來建立 Azure MFA 信任的 IP 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-158">Use the Azure AD portal for Office 365 services to create Azure MFA trusted IP address ranges.</span></span>


- <span data-ttu-id="bd0b5-159">若為條件式存取：</span><span class="sxs-lookup"><span data-stu-id="bd0b5-159">For Conditional Access:</span></span> 

  - <span data-ttu-id="bd0b5-160">在完成 [AZURE AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 遷移階段) 之後，才支援具有下列授與控制的條件式存取原則 (完成 Office 365 服務的遷移：</span><span class="sxs-lookup"><span data-stu-id="bd0b5-160">Conditional Access policies with the following grant controls aren't supported until migration to Office 365 services is complete (after the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase):</span></span>

    - <span data-ttu-id="bd0b5-161">需要相容的裝置</span><span class="sxs-lookup"><span data-stu-id="bd0b5-161">Require Compliant Device</span></span>
    - <span data-ttu-id="bd0b5-162">需要核准的應用程式</span><span class="sxs-lookup"><span data-stu-id="bd0b5-162">Require Approved App</span></span>
    - <span data-ttu-id="bd0b5-163">需要應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="bd0b5-163">Require App Protection Policy</span></span>
    
  - <span data-ttu-id="bd0b5-164">當租使用者啟用的安全性預設值為 [已停用] 或 [已存在租使用者的條件式存取原則] 時，條件式存取原則介面提供錯誤的警告。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-164">The Conditional Access policy interface gives a false warning about security defaults being enabled for the tenant even when it's disabled, and Conditional Access policies already exist for the tenant.</span></span> <span data-ttu-id="bd0b5-165">您應該忽略警告或使用 Office 365 服務入口網站來管理條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-165">You should ignore the warning or use the Office 365 services portal to manage Conditional Access policies.</span></span> 

- <span data-ttu-id="bd0b5-166">僅在租使用者遷移完成後（包括所有 office 工作負載遷移）之後，才會支援 Intune 案例。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-166">Intune scenarios are supported only against worldwide endpoints after tenant migration is complete, including all office workloads migrations.</span></span>

- <span data-ttu-id="bd0b5-167">Microsoft Cloud Deutschland 使用行動代理程式更新方法進行 MFA 要求的使用者，可看到使用者 ObjectId (GUID) ，而不是 Microsoft 驗證應用程式中的使用者主體名稱 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-167">Microsoft Cloud Deutschland users who use the Mobile App Notification method for MFA requests see the user's ObjectId (a GUID) instead of the user principal name (UPN) in the Microsoft Authenticator app.</span></span> <span data-ttu-id="bd0b5-168">在 Office 365 服務中完成 Azure AD 租使用者的遷移後，新的 Microsoft 驗證者啟用會顯示使用者的 Upn。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-168">After migration of the Azure AD tenant is complete and hosted in Office 365 services, new Microsoft Authenticator activations will display users' UPNs.</span></span> <span data-ttu-id="bd0b5-169">現有的 Microsoft 驗證者帳戶會繼續顯示使用者 ObjectId，但他們會繼續使用行動代理程式更新。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-169">Existing Microsoft Authenticator accounts will continue to display the user ObjectId, but they'll continue to work for mobile app notifications.</span></span> 

- <span data-ttu-id="bd0b5-170">針對10月 22 2019 日之後建立的承租人，當租使用者遷移至 Office 365 服務時，可能會為租使用者自動啟用安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-170">For tenants that are created after October 22, 2019, security defaults may be auto-enabled for the tenant when it's migrated to the Office 365 service.</span></span> <span data-ttu-id="bd0b5-171">租使用者管理員可以選擇讓安全性預設值保持啟用並登錄 MFA，也可以停用此功能。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-171">Tenant admins can choose to leave security defaults enabled and register for MFA, or they can disable the feature.</span></span> <span data-ttu-id="bd0b5-172">如需詳細資訊，請參閱 [停用安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-172">For more information, see [Disabling security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults).</span></span> 

  > [!NOTE]
  > <span data-ttu-id="bd0b5-173">在遷移期間，未自動啟用的組織可能會在未來自動註冊，因為啟用安全性預設值的功能會在 Office 365 服務中推出。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-173">Organizations that are not auto-enabled during migration may still be auto-enrolled in the future as the feature to enable security defaults is rolled out in the Office 365 service.</span></span> <span data-ttu-id="bd0b5-174">選擇明確停用或啟用安全性預設值的系統管理員可以在 **Azure Active Directory > 屬性** 下更新功能來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-174">Admins who choose to explicitly disable or enable security defaults may do so by updating the feature under **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="bd0b5-175">管理員明確啟用該功能之後，將不會自動啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-175">After the feature is explicitly enabled by the admin, it will not be auto-enabled.</span></span>

- <span data-ttu-id="bd0b5-176">當租使用者在遷移後，就會有關于 Office 365 德國入口網站中的 Azure AD Connect 版本和 Office 365 入口網站版本的警告。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-176">There will be warning about the version of Azure AD Connect in the Office 365 Germany portal as well as in the Office 365 portal once the tenant is in migration.</span></span> <span data-ttu-id="bd0b5-177">如果在遷移完成之後，版本警告不再顯示警告，可以忽略這種情況。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-177">This can be ignored if the version warning is no longer showing the warning after the migration is complete.</span></span> <span data-ttu-id="bd0b5-178">如果在遷移之前或之後有任何警告，請在任一入口網站中更新 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-178">If there's a warning, either before or after migration, in either portal, Azure AD Connect must be updated.</span></span> <span data-ttu-id="bd0b5-179">警告訊息說：「我們偵測到您正在使用過期的目錄同步處理工具。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-179">The warning message says: "We detected you're using an outdated directory sync tool.</span></span> <span data-ttu-id="bd0b5-180">建議您移至 Microsoft 下載中心以取得最新版本的 Azure AD Connect。」</span><span class="sxs-lookup"><span data-stu-id="bd0b5-180">We recommend you go to the Microsoft Download Center to get the latest version of Azure AD Connect."</span></span>

## <a name="more-information"></a><span data-ttu-id="bd0b5-181">其他資訊</span><span class="sxs-lookup"><span data-stu-id="bd0b5-181">More information</span></span>

<span data-ttu-id="bd0b5-182">開始：</span><span class="sxs-lookup"><span data-stu-id="bd0b5-182">Getting started:</span></span>

- [<span data-ttu-id="bd0b5-183">從 Microsoft Cloud Deutschland 遷移至新德文 datacenter 區域中的 Office 365 服務</span><span class="sxs-lookup"><span data-stu-id="bd0b5-183">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="bd0b5-184">Microsoft Cloud Deutschland 移轉協助</span><span class="sxs-lookup"><span data-stu-id="bd0b5-184">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="bd0b5-185">如何選擇加入移轉</span><span class="sxs-lookup"><span data-stu-id="bd0b5-185">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="bd0b5-186">遷移期間的客戶體驗</span><span class="sxs-lookup"><span data-stu-id="bd0b5-186">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="bd0b5-187">在轉換中移動：</span><span class="sxs-lookup"><span data-stu-id="bd0b5-187">Moving through the transition:</span></span>

- [<span data-ttu-id="bd0b5-188">移轉階段的動作與影響</span><span class="sxs-lookup"><span data-stu-id="bd0b5-188">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="bd0b5-189">其他預備工作</span><span class="sxs-lookup"><span data-stu-id="bd0b5-189">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="bd0b5-190">[AZURE AD](ms-cloud-germany-transition-azure-ad.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="bd0b5-190">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="bd0b5-191">雲端應用程式：</span><span class="sxs-lookup"><span data-stu-id="bd0b5-191">Cloud apps:</span></span>

- [<span data-ttu-id="bd0b5-192">Dynamics 365 的移轉程式資訊</span><span class="sxs-lookup"><span data-stu-id="bd0b5-192">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="bd0b5-193">Power BI 移轉程式資訊</span><span class="sxs-lookup"><span data-stu-id="bd0b5-193">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="bd0b5-194">開始升級您的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd0b5-194">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
