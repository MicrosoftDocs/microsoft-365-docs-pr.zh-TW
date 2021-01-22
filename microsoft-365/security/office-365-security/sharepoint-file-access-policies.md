---
title: 建議的安全檔策略 - 適用于企業的 Microsoft 365 |Microsoft Docs
description: 描述如何保護 SharePoint 檔案存取之 Microsoft 建議的原則。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: a3485896cae5e41808cfd16a77d484a35c768a6d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931767"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a><span data-ttu-id="0df59-103">保護 SharePoint 網站和檔案安全的政策建議</span><span class="sxs-lookup"><span data-stu-id="0df59-103">Policy recommendations for securing SharePoint sites and files</span></span>

<span data-ttu-id="0df59-104">本文說明如何執行建議的身分識別與裝置存取策略，以保護 SharePoint 和商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="0df59-104">This article describes how to implement the recommended identity and device-access policies to protect SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="0df59-105">本指引以一 [般身分識別與裝置存取策略為根據](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0df59-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="0df59-106">這些建議是以三種不同的 SharePoint 檔案安全性和保護層級為基礎，可根據您的需求細微度來加以應用程式：比較基準、敏感性及 **高度規範**。  </span><span class="sxs-lookup"><span data-stu-id="0df59-106">These recommendations are based on three different tiers of security and protection for SharePoint files that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="0df59-107">您可以進一步瞭解這些安全性層級，以及建議的用戶端作業系統，這些在概觀中的建議是 [參照的](microsoft-365-policies-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="0df59-107">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in [the overview](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="0df59-108">除了執行此指引外，務必將 SharePoint 網站設定為適當的保護量，包括針對敏感和高度規範的內容設定適當許可權。</span><span class="sxs-lookup"><span data-stu-id="0df59-108">In addition to implementing this guidance, be sure to configure SharePoint sites with the right amount of protection, including setting appropriate permissions for sensitive and highly-regulated content.</span></span>

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a><span data-ttu-id="0df59-109">更新一般策略以包含 SharePoint 和商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="0df59-109">Updating common policies to include SharePoint and OneDrive for Business</span></span>

<span data-ttu-id="0df59-110">若要保護 SharePoint 和 OneDrive 中的檔案，下圖說明要從一般身分識別與裝置存取策略更新哪些策略。</span><span class="sxs-lookup"><span data-stu-id="0df59-110">To protect files in SharePoint and OneDrive, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="0df59-111">[![保護 Teams 存取權及其從屬服務之策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span><span class="sxs-lookup"><span data-stu-id="0df59-111">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span></span>

[<span data-ttu-id="0df59-112">查看此影像的較大版本</span><span class="sxs-lookup"><span data-stu-id="0df59-112">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

<span data-ttu-id="0df59-113">如果您在建立共同策略時包含了 SharePoint，則只需要建立新策略。</span><span class="sxs-lookup"><span data-stu-id="0df59-113">If you included SharePoint when you created the common policies, you only need to create the new policies.</span></span> <span data-ttu-id="0df59-114">針對條件式存取策略，SharePoint 會包含 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="0df59-114">For Conditional Access policies, SharePoint includes OneDrive.</span></span>

<span data-ttu-id="0df59-115">新原則會針對敏感和受到高度規範的內容，將特定的存取需求，針對您指定的 SharePoint 網站，來實施裝置保護。</span><span class="sxs-lookup"><span data-stu-id="0df59-115">The new policies implement device protection for sensitive and highly-regulated content by applying specific access requirements to SharePoint sites that you specify.</span></span>

<span data-ttu-id="0df59-116">下表列出您需要檢查及更新，或為 SharePoint 建立新設定時需要執行之策略。</span><span class="sxs-lookup"><span data-stu-id="0df59-116">The following table lists the policies you either need to review and update or create new for SharePoint.</span></span> <span data-ttu-id="0df59-117">共同策略會連結至共同身分識別與裝置存取策略文章中的相關 [組組](identity-access-policies.md) 指示。</span><span class="sxs-lookup"><span data-stu-id="0df59-117">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="0df59-118">保護層級</span><span class="sxs-lookup"><span data-stu-id="0df59-118">Protection level</span></span>|<span data-ttu-id="0df59-119">原則</span><span class="sxs-lookup"><span data-stu-id="0df59-119">Policies</span></span>|<span data-ttu-id="0df59-120">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="0df59-120">More information</span></span>|
|---|---|---|
|<span data-ttu-id="0df59-121">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="0df59-121">**Baseline**</span></span>|[<span data-ttu-id="0df59-122">當登錄風險中或高 *時需要* MFA</span><span class="sxs-lookup"><span data-stu-id="0df59-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="0df59-123">在指派雲端 App 中納入 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="0df59-123">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="0df59-124">封鎖不支援新式驗證的用戶端</span><span class="sxs-lookup"><span data-stu-id="0df59-124">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="0df59-125">在指派雲端 App 中納入 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="0df59-125">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="0df59-126">Apply APP 資料保護原則</span><span class="sxs-lookup"><span data-stu-id="0df59-126">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="0df59-127">請確定所有建議的應用程式都包含在應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="0df59-127">Be sure all recommended apps are included in the list of apps.</span></span> <span data-ttu-id="0df59-128">請務必針對 iOS、Android、Windows (每個平臺更新) 。</span><span class="sxs-lookup"><span data-stu-id="0df59-128">Be sure to update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="0df59-129">需要相容的電腦</span><span class="sxs-lookup"><span data-stu-id="0df59-129">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="0df59-130">在雲端應用程式清單中納入 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="0df59-130">Include SharePoint in list of cloud apps.</span></span>|
||[<span data-ttu-id="0df59-131">在 SharePoint 使用應用程式強制限制</span><span class="sxs-lookup"><span data-stu-id="0df59-131">Use app enforced restrictions in SharePoint</span></span>](#use-app-enforced-restrictions-in-sharepoint)|<span data-ttu-id="0df59-132">新增此新政策。</span><span class="sxs-lookup"><span data-stu-id="0df59-132">Add this new policy.</span></span> <span data-ttu-id="0df59-133">這告訴 Azure Active Directory (Azure AD) 使用 SharePoint 中指定的設定。</span><span class="sxs-lookup"><span data-stu-id="0df59-133">This tells Azure Active Directory (Azure AD) to use the settings specified in SharePoint.</span></span> <span data-ttu-id="0df59-134">此原則會適用于所有使用者，但只會影響 SharePoint 存取原則中包含的網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="0df59-134">This policy applies to all users, but only affects access to sites included in SharePoint access policies.</span></span>|
|<span data-ttu-id="0df59-135">**敏感度**</span><span class="sxs-lookup"><span data-stu-id="0df59-135">**Sensitive**</span></span>|[<span data-ttu-id="0df59-136">當登錄風險低、中或高時 *需要*  MFA</span><span class="sxs-lookup"><span data-stu-id="0df59-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="0df59-137">在雲端應用程式的指派中納入 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="0df59-137">Include SharePoint in the assignments of cloud apps.</span></span>|
||[<span data-ttu-id="0df59-138">需要符合規範的 PC *及* 行動裝置</span><span class="sxs-lookup"><span data-stu-id="0df59-138">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="0df59-139">在雲端應用程式清單中納入 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="0df59-139">Include SharePoint in the list of cloud apps.</span></span>|
||<span data-ttu-id="0df59-140">[SharePoint 存取控制政策](#sharepoint-access-control-policies)：允許瀏覽器僅從未管理裝置存取特定 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="0df59-140">[SharePoint access control policy](#sharepoint-access-control-policies): Allow browser-only access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="0df59-141">這可防止編輯和下載檔案。</span><span class="sxs-lookup"><span data-stu-id="0df59-141">This prevents edit and download of files.</span></span> <span data-ttu-id="0df59-142">使用 PowerShell 指定網站。</span><span class="sxs-lookup"><span data-stu-id="0df59-142">Use PowerShell to specify sites.</span></span>|
|<span data-ttu-id="0df59-143">**高管制**</span><span class="sxs-lookup"><span data-stu-id="0df59-143">**Highly regulated**</span></span>|[<span data-ttu-id="0df59-144">*一* 直需要 MFA</span><span class="sxs-lookup"><span data-stu-id="0df59-144">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="0df59-145">在指派雲端 App 中納入 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="0df59-145">Include SharePoint in the assignment of cloud apps.</span></span>|
||<span data-ttu-id="0df59-146">[SharePoint 存取控制政策](#use-app-enforced-restrictions-in-sharepoint)：封鎖未管理裝置對特定 SharePoint 網站的存取。</span><span class="sxs-lookup"><span data-stu-id="0df59-146">[SharePoint access control policy](#use-app-enforced-restrictions-in-sharepoint): Block access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="0df59-147">使用 PowerShell 指定網站。</span><span class="sxs-lookup"><span data-stu-id="0df59-147">Use PowerShell to specify sites.</span></span>|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a><span data-ttu-id="0df59-148">在 SharePoint 中使用應用程式強制限制</span><span class="sxs-lookup"><span data-stu-id="0df59-148">Use app-enforced restrictions in SharePoint</span></span>

<span data-ttu-id="0df59-149">如果您在 SharePoint 中實施存取控制，您必須在 Azure AD 中建立此條件式存取策略，以告訴 Azure AD 要強制執行您于 SharePoint 中設定的政策。</span><span class="sxs-lookup"><span data-stu-id="0df59-149">If you implement access controls in SharePoint, you must create this Conditional Access policy in Azure AD to tell Azure AD to enforce the policies you configure in SharePoint.</span></span> <span data-ttu-id="0df59-150">此原則會適用于所有使用者，但只會影響當您在 SharePoint 中建立存取控制時，對使用 PowerShell 所指定網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="0df59-150">This policy applies to all users, but only affects access to the sites you specify using PowerShell when you create the access controls in SharePoint.</span></span>

<span data-ttu-id="0df59-151">若要設定此策略，請參閱「封鎖或限制特定 SharePoint 網站集合或 OneDrive 帳戶的存取權」，瞭解未管理裝置存取權 [中的「封鎖或限制存取特定 SharePoint 網站集合或](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)OneDrive 帳戶」。</span><span class="sxs-lookup"><span data-stu-id="0df59-151">To configure this policy see "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="sharepoint-access-control-policies"></a><span data-ttu-id="0df59-152">SharePoint 存取控制策略</span><span class="sxs-lookup"><span data-stu-id="0df59-152">SharePoint access control policies</span></span>

<span data-ttu-id="0df59-153">Microsoft 建議您使用裝置存取控制，以敏感且受到高度規範的內容來保護 SharePoint 網站中的內容。</span><span class="sxs-lookup"><span data-stu-id="0df59-153">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="0df59-154">若要這麼做，請建立原則，指定保護層級和要保護的網站。</span><span class="sxs-lookup"><span data-stu-id="0df59-154">You do this by creating a policy that specifies the level of protection and the sites to apply the protection to.</span></span>

- <span data-ttu-id="0df59-155">機密網站：允許瀏覽器存取。</span><span class="sxs-lookup"><span data-stu-id="0df59-155">Sensitive sites: Allow browser-only access.</span></span> <span data-ttu-id="0df59-156">這可防止使用者編輯和下載檔案。</span><span class="sxs-lookup"><span data-stu-id="0df59-156">This prevents users from editing and downloading files.</span></span>
- <span data-ttu-id="0df59-157">受到高度規範的網站：封鎖未受管理裝置的存取權限。</span><span class="sxs-lookup"><span data-stu-id="0df59-157">Highly regulated sites: Block access from unmanaged devices.</span></span>

<span data-ttu-id="0df59-158">請參閱未管理裝置在 Control 存取中的「封鎖或限制特定 SharePoint 網站集合或 OneDrive 帳戶的[存取」。](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)</span><span class="sxs-lookup"><span data-stu-id="0df59-158">See "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="how-these-policies-work-together"></a><span data-ttu-id="0df59-159">那些政策如何共同作業</span><span class="sxs-lookup"><span data-stu-id="0df59-159">How these policies work together</span></span>

<span data-ttu-id="0df59-160">請注意，SharePoint 網站許可權通常是以存取網站的業務需求為基礎。</span><span class="sxs-lookup"><span data-stu-id="0df59-160">It's important to understand that SharePoint site permissions are typically based on business need for access to sites.</span></span> <span data-ttu-id="0df59-161">這些許可權是由網站擁有者管理，而且可能是高度動態的。</span><span class="sxs-lookup"><span data-stu-id="0df59-161">These permissions are managed by site owners and can be highly dynamic.</span></span> <span data-ttu-id="0df59-162">使用 SharePoint 裝置存取策略可確保這些網站的保護，不論使用者被指派給與比較基準、機密或高度受規範保護相關聯的 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="0df59-162">Using SharePoint device access policies ensures protection to these sites, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="0df59-163">下圖提供 SharePoint 裝置存取策略如何保護使用者存取網站的範例。</span><span class="sxs-lookup"><span data-stu-id="0df59-163">The following illustration provides an example of how SharePoint device access policies protect access to sites for a user.</span></span>

<span data-ttu-id="0df59-164">[![SharePoint 裝置存取策略如何保護網站的範例](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span><span class="sxs-lookup"><span data-stu-id="0df59-164">[![Example of how SharePoint device access policies protect sites](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span></span>

[<span data-ttu-id="0df59-165">查看此影像的較大版本</span><span class="sxs-lookup"><span data-stu-id="0df59-165">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

<span data-ttu-id="0df59-166">James 已指派比較基準條件式存取策略，但具有敏感或高度規範保護的 SharePoint 網站存取權。</span><span class="sxs-lookup"><span data-stu-id="0df59-166">James has baseline Conditional Access policies assigned, but he can be given access to SharePoint sites with sensitive or highly-regulated protection.</span></span>

- <span data-ttu-id="0df59-167">如果 James 存取其使用電腦的成員之敏感或受到高度規範的網站，只要他的電腦符合規範，即會授予其存取權。</span><span class="sxs-lookup"><span data-stu-id="0df59-167">If James accesses a sensitive or highly-regulated site he is a member of using his PC, his access is granted as long as his PC is compliant.</span></span>
- <span data-ttu-id="0df59-168">如果 James 存取一個機密網站，而他就是其未受管理電話的成員之一 ，而比較基準使用者是允許的，由於針對這個網站設定了裝置存取策略，他會收到機密網站的瀏覽器存取權。</span><span class="sxs-lookup"><span data-stu-id="0df59-168">If James accesses a sensitive site he is a member of using his unmanaged phone, which is allowed for baseline users, he will receive browser-only access to the sensitive site due to the device access policy configured for this site.</span></span>
- <span data-ttu-id="0df59-169">如果 James 存取受到高度規範的網站，而他就是使用未受管理電話的成員，他將會因為此網站的存取策略而被封鎖。</span><span class="sxs-lookup"><span data-stu-id="0df59-169">If James accesses a highly regulated site he is a member of using his unmanaged phone, he will be blocked due to the access policy configured for this site.</span></span> <span data-ttu-id="0df59-170">他只能使用自己受管理且相容的電腦來存取這個網站。</span><span class="sxs-lookup"><span data-stu-id="0df59-170">He can only access this site using his managed and compliant PC.</span></span>

## <a name="next-step"></a><span data-ttu-id="0df59-171">下一步</span><span class="sxs-lookup"><span data-stu-id="0df59-171">Next step</span></span>

![步驟 4：Microsoft 365 雲端應用程式政策](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="0df59-173">設定條件式存取策略：</span><span class="sxs-lookup"><span data-stu-id="0df59-173">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="0df59-174">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0df59-174">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="0df59-175">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0df59-175">Exchange Online</span></span>](secure-email-recommended-policies.md)
