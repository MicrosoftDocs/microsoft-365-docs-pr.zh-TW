---
title: 建議的安全檔原則-Microsoft 365 for enterprise |Microsoft 檔
description: 描述如何保護 SharePoint 檔案存取之 Microsoft 建議的原則。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 653bd90fb68eb42423d5f32633736bba4b5943b4
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464309"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a><span data-ttu-id="a4bb1-103">保護 SharePoint 網站和檔案的原則建議</span><span class="sxs-lookup"><span data-stu-id="a4bb1-103">Policy recommendations for securing SharePoint sites and files</span></span>

<span data-ttu-id="a4bb1-104">本文說明如何執行建議的身分識別和裝置存取原則，以保護 SharePoint 和 OneDrive 商務。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-104">This article describes how to implement the recommended identity and device-access policies to protect SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="a4bb1-105">本指南是以 [通用身分識別和裝置存取原則](identity-access-policies.md)為基礎。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="a4bb1-106">這些建議是根據您的需求細微性，以三種不同的安全性和保護層級來保護 SharePoint 檔案： **基準**、 **機密**和 **高管制**。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-106">These recommendations are based on three different tiers of security and protection for SharePoint files that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="a4bb1-107">您可以在 [ [概述](microsoft-365-policies-configurations.md)] 中深入瞭解這些安全性層，以及建議的用戶端作業系統。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-107">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in [the overview](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="a4bb1-108">除了執行這項指導之外，請務必設定具有適當保護的 SharePoint 網站，包括為敏感和高管制內容設定適當的許可權。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-108">In addition to implementing this guidance, be sure to configure SharePoint sites with the right amount of protection, including setting appropriate permissions for sensitive and highly-regulated content.</span></span>

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a><span data-ttu-id="a4bb1-109">更新常見原則，以納入 SharePoint 和 OneDrive 商務</span><span class="sxs-lookup"><span data-stu-id="a4bb1-109">Updating common policies to include SharePoint and OneDrive for Business</span></span>

<span data-ttu-id="a4bb1-110">為了保護 SharePoint 和 OneDrive 中的檔案，下圖說明要從一般身分識別和裝置存取原則更新哪些原則。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-110">To protect files in SharePoint and OneDrive, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="a4bb1-111">[![保護對小組及其相依服務之存取的原則更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span><span class="sxs-lookup"><span data-stu-id="a4bb1-111">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span></span>

[<span data-ttu-id="a4bb1-112">查看較大版本的此影像</span><span class="sxs-lookup"><span data-stu-id="a4bb1-112">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

<span data-ttu-id="a4bb1-113">如果您在建立通用原則時包含 SharePoint，您只需要建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-113">If you included SharePoint when you created the common policies, you only need to create the new policies.</span></span> <span data-ttu-id="a4bb1-114">針對條件式存取原則，SharePoint 包含 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-114">For Conditional Access policies, SharePoint includes OneDrive.</span></span>

<span data-ttu-id="a4bb1-115">新的原則會將特定存取需求套用至指定的 SharePoint 網站，以實現敏感和高管制內容的裝置保護。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-115">The new policies implement device protection for sensitive and highly-regulated content by applying specific access requirements to SharePoint sites that you specify.</span></span>

<span data-ttu-id="a4bb1-116">下表列出您需要複查和更新或為 SharePoint 建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-116">The following table lists the policies you either need to review and update or create new for SharePoint.</span></span> <span data-ttu-id="a4bb1-117">通用身分 [識別與裝置存取原則](identity-access-policies.md) 文章中相關之設定指示的常見原則連結。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-117">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="a4bb1-118">保護層級</span><span class="sxs-lookup"><span data-stu-id="a4bb1-118">Protection level</span></span>|<span data-ttu-id="a4bb1-119">原則</span><span class="sxs-lookup"><span data-stu-id="a4bb1-119">Policies</span></span>|<span data-ttu-id="a4bb1-120">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="a4bb1-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="a4bb1-121">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="a4bb1-121">**Baseline**</span></span>|[<span data-ttu-id="a4bb1-122">當登入風險為*中*或*高*時，需要 MFA</span><span class="sxs-lookup"><span data-stu-id="a4bb1-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="a4bb1-123">在雲端應用程式的指派中包含 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-123">Include SharePoint in the assignment of cloud apps.</span></span>|
|        |[<span data-ttu-id="a4bb1-124">封鎖不支援新式驗證的用戶端</span><span class="sxs-lookup"><span data-stu-id="a4bb1-124">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="a4bb1-125">在雲端應用程式的指派中包含 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-125">Include SharePoint in the assignment of cloud apps.</span></span>|
|        |[<span data-ttu-id="a4bb1-126">套用應用程式資料保護原則</span><span class="sxs-lookup"><span data-stu-id="a4bb1-126">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="a4bb1-127">請確定所有建議的應用程式都包含在應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-127">Be sure all recommended apps are included in the list of apps.</span></span> <span data-ttu-id="a4bb1-128">請務必更新每個平臺 (iOS、Android、Windows) 的原則。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-128">Be sure to update the policy for each platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="a4bb1-129">需要相容的電腦</span><span class="sxs-lookup"><span data-stu-id="a4bb1-129">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="a4bb1-130">在雲端應用程式的清單中包含 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-130">Include SharePoint in list of cloud apps.</span></span>|
|        |[<span data-ttu-id="a4bb1-131">在 SharePoint 中使用應用程式強制限制</span><span class="sxs-lookup"><span data-stu-id="a4bb1-131">Use app enforced restrictions in SharePoint</span></span>](#use-app-enforced-restrictions-in-sharepoint)|<span data-ttu-id="a4bb1-132">新增此新原則。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-132">Add this new policy.</span></span> <span data-ttu-id="a4bb1-133">這會告訴 Azure Active Directory (Azure AD) 使用 SharePoint 中指定的設定。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-133">This tells Azure Active Directory (Azure AD) to use the settings specified in SharePoint.</span></span> <span data-ttu-id="a4bb1-134">這個原則會套用至所有使用者，但是只會影響 SharePoint 存取原則中所包含之網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-134">This policy applies to all users, but only affects access to sites included in SharePoint access policies.</span></span>|
|<span data-ttu-id="a4bb1-135">**敏感度**</span><span class="sxs-lookup"><span data-stu-id="a4bb1-135">**Sensitive**</span></span>|[<span data-ttu-id="a4bb1-136">當登入風險為*低*、*中*或*高*時，需要 MFA</span><span class="sxs-lookup"><span data-stu-id="a4bb1-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="a4bb1-137">在雲端應用程式的指派中包含 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-137">Include SharePoint in the assignments of cloud apps.</span></span>|
|         |[<span data-ttu-id="a4bb1-138">需要相容 *的電腦和* 行動裝置</span><span class="sxs-lookup"><span data-stu-id="a4bb1-138">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="a4bb1-139">在雲端 app 清單中包含 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-139">Include SharePoint in the list of cloud apps.</span></span>|
||<span data-ttu-id="a4bb1-140">[SharePoint 存取控制原則](#sharepoint-access-control-policies)：允許來自未受管理裝置之特定 SharePoint 網站的瀏覽器存取權。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-140">[SharePoint access control policy](#sharepoint-access-control-policies): Allow browser-only access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="a4bb1-141">這可避免檔案的編輯和下載。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-141">This prevents edit and download of files.</span></span> <span data-ttu-id="a4bb1-142">使用 PowerShell 來指定網站。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-142">Use PowerShell to specify sites.</span></span>|
|<span data-ttu-id="a4bb1-143">**高管制**</span><span class="sxs-lookup"><span data-stu-id="a4bb1-143">**Highly regulated**</span></span>|[<span data-ttu-id="a4bb1-144">*永遠* 需要 MFA</span><span class="sxs-lookup"><span data-stu-id="a4bb1-144">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="a4bb1-145">在雲端應用程式的指派中包含 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-145">Include SharePoint in the assignment of cloud apps.</span></span>|
||<span data-ttu-id="a4bb1-146">[SharePoint 存取控制原則](#use-app-enforced-restrictions-in-sharepoint)：封鎖非管理裝置對特定 SharePoint 網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-146">[SharePoint access control policy](#use-app-enforced-restrictions-in-sharepoint): Block access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="a4bb1-147">使用 PowerShell 來指定網站。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-147">Use PowerShell to specify sites.</span></span>|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a><span data-ttu-id="a4bb1-148">在 SharePoint 中使用應用程式強制限制</span><span class="sxs-lookup"><span data-stu-id="a4bb1-148">Use app-enforced restrictions in SharePoint</span></span>

<span data-ttu-id="a4bb1-149">如果您在 SharePoint 中執行存取控制，您必須在 Azure AD 中建立此條件式存取原則，以通知 Azure AD 強制執行您在 SharePoint 中設定的原則。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-149">If you implement access controls in SharePoint, you must create this Conditional Access policy in Azure AD to tell Azure AD to enforce the policies you configure in SharePoint.</span></span> <span data-ttu-id="a4bb1-150">這個原則會套用至所有使用者，但是只會影響您在 SharePoint 中建立存取控制時使用 PowerShell 所指定之網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-150">This policy applies to all users, but only affects access to the sites you specify using PowerShell when you create the access controls in SharePoint.</span></span>

<span data-ttu-id="a4bb1-151">若要設定此原則，請參閱 [控制存取非管理裝置](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)中的「封鎖或限制存取特定 SharePoint 網站集合或 OneDrive 帳戶」。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-151">To configure this policy see "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="sharepoint-access-control-policies"></a><span data-ttu-id="a4bb1-152">SharePoint 的存取控制原則</span><span class="sxs-lookup"><span data-stu-id="a4bb1-152">SharePoint access control policies</span></span>

<span data-ttu-id="a4bb1-153">Microsoft 建議您使用裝置存取控制，以機密和高管制內容來保護 SharePoint 網站中的內容。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-153">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="a4bb1-154">您可以建立原則，以指定保護的層級，以及要套用保護的網站。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-154">You do this by creating a policy that specifies the level of protection and the sites to apply the protection to.</span></span>

- <span data-ttu-id="a4bb1-155">機密網站：允許僅供瀏覽器存取。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-155">Sensitive sites: Allow browser-only access.</span></span> <span data-ttu-id="a4bb1-156">這會防止使用者編輯及下載檔案。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-156">This prevents users from editing and downloading files.</span></span>
- <span data-ttu-id="a4bb1-157">高度管制網站：封鎖非管理裝置的存取。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-157">Highly regulated sites: Block access from unmanaged devices.</span></span>

<span data-ttu-id="a4bb1-158">請參閱「阻止或限制存取特定 SharePoint 網站集合或 OneDrive 帳戶」，以 [控制來自非管理裝置的存取](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-158">See "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="how-these-policies-work-together"></a><span data-ttu-id="a4bb1-159">這些原則共同運作的方式</span><span class="sxs-lookup"><span data-stu-id="a4bb1-159">How these policies work together</span></span>

<span data-ttu-id="a4bb1-160">請務必瞭解，SharePoint 網站許可權通常是以網站存取權的業務需求為基礎。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-160">It's important to understand that SharePoint site permissions are typically based on business need for access to sites.</span></span> <span data-ttu-id="a4bb1-161">這些許可權是由網站擁有者管理，而且可以是高動態的。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-161">These permissions are managed by site owners and can be highly dynamic.</span></span> <span data-ttu-id="a4bb1-162">使用 SharePoint 裝置存取原則可確保對這些網站的保護，不論是否將使用者指派至與基線、敏感或高度管制保護相關聯的 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-162">Using SharePoint device access policies ensures protection to these sites, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="a4bb1-163">下圖提供 SharePoint 裝置存取原則如何保護使用者對網站存取的範例。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-163">The following illustration provides an example of how SharePoint device access policies protect access to sites for a user.</span></span>

<span data-ttu-id="a4bb1-164">[![SharePoint 裝置存取原則如何保護網站的範例](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span><span class="sxs-lookup"><span data-stu-id="a4bb1-164">[![Example of how SharePoint device access policies protect sites](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span></span>

[<span data-ttu-id="a4bb1-165">查看較大版本的此影像</span><span class="sxs-lookup"><span data-stu-id="a4bb1-165">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

<span data-ttu-id="a4bb1-166">James 具有指派的基準條件式存取原則，但可獲得對具有敏感或高管制保護之 SharePoint 網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-166">James has baseline Conditional Access policies assigned, but he can be given access to SharePoint sites with sensitive or highly-regulated protection.</span></span>

- <span data-ttu-id="a4bb1-167">如果 James 存取敏感或高管制的網站，他是使用自己電腦的成員，只要其電腦符合規範，就會授與其存取權。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-167">If James accesses a sensitive or highly-regulated site he is a member of using his PC, his access is granted as long as his PC is compliant.</span></span>
- <span data-ttu-id="a4bb1-168">如果 James 存取機密的網站，他是使用未受管理的電話的成員（允許基準使用者使用），他只會收到對機密網站的瀏覽器存取權（由於為此網站設定的裝置存取原則）。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-168">If James accesses a sensitive site he is a member of using his unmanaged phone, which is allowed for baseline users, he will receive browser-only access to the sensitive site due to the device access policy configured for this site.</span></span>
- <span data-ttu-id="a4bb1-169">如果 James 存取高管制網站，他是使用非管理電話的成員，則會因此網站設定的存取原則而封鎖。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-169">If James accesses a highly regulated site he is a member of using his unmanaged phone, he will be blocked due to the access policy configured for this site.</span></span> <span data-ttu-id="a4bb1-170">他只能使用受管理和相容的電腦來存取此網站。</span><span class="sxs-lookup"><span data-stu-id="a4bb1-170">He can only access this site using his managed and compliant PC.</span></span>

## <a name="next-step"></a><span data-ttu-id="a4bb1-171">下一步</span><span class="sxs-lookup"><span data-stu-id="a4bb1-171">Next step</span></span>

![步驟4： Microsoft 365 雲端應用程式的原則](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="a4bb1-173">為下列專案設定條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="a4bb1-173">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="a4bb1-174">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a4bb1-174">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="a4bb1-175">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a4bb1-175">Exchange Online</span></span>](secure-email-recommended-policies.md)

