---
title: 建議的安全檔原則-Microsoft 365 for enterprise |Microsoft 檔
description: 描述如何保護 SharePoint 檔案存取之 Microsoft 建議的原則。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.openlocfilehash: f3a9cc2c3bae32a8fee10e814f96968b864e78a5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290414"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a><span data-ttu-id="4cb43-103">保護 SharePoint 網站和檔案的原則建議</span><span class="sxs-lookup"><span data-stu-id="4cb43-103">Policy recommendations for securing SharePoint sites and files</span></span>

<span data-ttu-id="4cb43-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="4cb43-104">**Applies to**</span></span>
- [<span data-ttu-id="4cb43-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4cb43-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4cb43-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="4cb43-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- <span data-ttu-id="4cb43-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4cb43-107">SharePoint Online</span></span> 


<span data-ttu-id="4cb43-108">本文說明如何執行建議的身分識別和裝置存取原則，以保護 SharePoint 和 OneDrive 商務。</span><span class="sxs-lookup"><span data-stu-id="4cb43-108">This article describes how to implement the recommended identity and device-access policies to protect SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="4cb43-109">本指南是以 [通用身分識別和裝置存取原則](identity-access-policies.md)為基礎。</span><span class="sxs-lookup"><span data-stu-id="4cb43-109">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="4cb43-110">這些建議是根據您的需求細微性，以三種不同的安全性和保護層級來保護 SharePoint 檔案： **基準**、 **機密** 和 **高管制**。</span><span class="sxs-lookup"><span data-stu-id="4cb43-110">These recommendations are based on three different tiers of security and protection for SharePoint files that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="4cb43-111">您可以在 [ [概述](microsoft-365-policies-configurations.md)] 中深入瞭解這些安全性層，以及建議的用戶端作業系統。</span><span class="sxs-lookup"><span data-stu-id="4cb43-111">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in [the overview](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="4cb43-112">除了執行這項指導之外，請務必設定具有適當保護的 SharePoint 網站，包括為敏感和高管制內容設定適當的許可權。</span><span class="sxs-lookup"><span data-stu-id="4cb43-112">In addition to implementing this guidance, be sure to configure SharePoint sites with the right amount of protection, including setting appropriate permissions for sensitive and highly-regulated content.</span></span>

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a><span data-ttu-id="4cb43-113">更新常見原則，以納入 SharePoint 和 OneDrive 商務</span><span class="sxs-lookup"><span data-stu-id="4cb43-113">Updating common policies to include SharePoint and OneDrive for Business</span></span>

<span data-ttu-id="4cb43-114">為了保護 SharePoint 和 OneDrive 中的檔案，下圖說明要從一般身分識別和裝置存取原則更新哪些原則。</span><span class="sxs-lookup"><span data-stu-id="4cb43-114">To protect files in SharePoint and OneDrive, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="4cb43-115">[![保護對小組及其相依服務之存取的原則更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span><span class="sxs-lookup"><span data-stu-id="4cb43-115">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span></span>

[<span data-ttu-id="4cb43-116">查看較大版本的此影像</span><span class="sxs-lookup"><span data-stu-id="4cb43-116">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

<span data-ttu-id="4cb43-117">如果您在建立通用原則時包含 SharePoint，您只需要建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="4cb43-117">If you included SharePoint when you created the common policies, you only need to create the new policies.</span></span> <span data-ttu-id="4cb43-118">針對條件式存取原則，SharePoint 包含 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="4cb43-118">For Conditional Access policies, SharePoint includes OneDrive.</span></span>

<span data-ttu-id="4cb43-119">新的原則會將特定存取需求套用至指定的 SharePoint 網站，以實現敏感和高管制內容的裝置保護。</span><span class="sxs-lookup"><span data-stu-id="4cb43-119">The new policies implement device protection for sensitive and highly-regulated content by applying specific access requirements to SharePoint sites that you specify.</span></span>

<span data-ttu-id="4cb43-120">下表列出您需要複查和更新或為 SharePoint 建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="4cb43-120">The following table lists the policies you either need to review and update or create new for SharePoint.</span></span> <span data-ttu-id="4cb43-121">通用身分 [識別與裝置存取原則](identity-access-policies.md) 文章中相關之設定指示的常見原則連結。</span><span class="sxs-lookup"><span data-stu-id="4cb43-121">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="4cb43-122">保護層級</span><span class="sxs-lookup"><span data-stu-id="4cb43-122">Protection level</span></span>|<span data-ttu-id="4cb43-123">原則</span><span class="sxs-lookup"><span data-stu-id="4cb43-123">Policies</span></span>|<span data-ttu-id="4cb43-124">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="4cb43-124">More information</span></span>|
|---|---|---|
|<span data-ttu-id="4cb43-125">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="4cb43-125">**Baseline**</span></span>|[<span data-ttu-id="4cb43-126">當登入風險為 *中* 或 *高* 時，需要 MFA</span><span class="sxs-lookup"><span data-stu-id="4cb43-126">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="4cb43-127">在雲端應用程式的指派中包含 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="4cb43-127">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="4cb43-128">封鎖不支援新式驗證的用戶端</span><span class="sxs-lookup"><span data-stu-id="4cb43-128">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="4cb43-129">在雲端應用程式的指派中包含 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="4cb43-129">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="4cb43-130">套用應用程式資料保護原則</span><span class="sxs-lookup"><span data-stu-id="4cb43-130">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="4cb43-131">請確定所有建議的應用程式都包含在應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="4cb43-131">Be sure all recommended apps are included in the list of apps.</span></span> <span data-ttu-id="4cb43-132">請務必更新每個平臺 (iOS、Android、Windows) 的原則。</span><span class="sxs-lookup"><span data-stu-id="4cb43-132">Be sure to update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="4cb43-133">需要相容的電腦</span><span class="sxs-lookup"><span data-stu-id="4cb43-133">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="4cb43-134">在雲端應用程式的清單中包含 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="4cb43-134">Include SharePoint in list of cloud apps.</span></span>|
||[<span data-ttu-id="4cb43-135">在 SharePoint 中使用應用程式強制限制</span><span class="sxs-lookup"><span data-stu-id="4cb43-135">Use app enforced restrictions in SharePoint</span></span>](#use-app-enforced-restrictions-in-sharepoint)|<span data-ttu-id="4cb43-136">新增此新原則。</span><span class="sxs-lookup"><span data-stu-id="4cb43-136">Add this new policy.</span></span> <span data-ttu-id="4cb43-137">這會告訴 Azure Active Directory (Azure AD) 使用 SharePoint 中指定的設定。</span><span class="sxs-lookup"><span data-stu-id="4cb43-137">This tells Azure Active Directory (Azure AD) to use the settings specified in SharePoint.</span></span> <span data-ttu-id="4cb43-138">這個原則會套用至所有使用者，但是只會影響 SharePoint 存取原則中所包含之網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="4cb43-138">This policy applies to all users, but only affects access to sites included in SharePoint access policies.</span></span>|
|<span data-ttu-id="4cb43-139">**敏感度**</span><span class="sxs-lookup"><span data-stu-id="4cb43-139">**Sensitive**</span></span>|[<span data-ttu-id="4cb43-140">當登入風險為 *低*、*中* 或 *高* 時，需要 MFA</span><span class="sxs-lookup"><span data-stu-id="4cb43-140">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="4cb43-141">在雲端應用程式的指派中包含 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="4cb43-141">Include SharePoint in the assignments of cloud apps.</span></span>|
||[<span data-ttu-id="4cb43-142">需要相容 *的電腦和* 行動裝置</span><span class="sxs-lookup"><span data-stu-id="4cb43-142">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="4cb43-143">在雲端 app 清單中包含 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="4cb43-143">Include SharePoint in the list of cloud apps.</span></span>|
||<span data-ttu-id="4cb43-144">[SharePoint 存取控制原則](#sharepoint-access-control-policies)：允許來自未受管理裝置之特定 SharePoint 網站的瀏覽器存取權。</span><span class="sxs-lookup"><span data-stu-id="4cb43-144">[SharePoint access control policy](#sharepoint-access-control-policies): Allow browser-only access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="4cb43-145">這可避免檔案的編輯和下載。</span><span class="sxs-lookup"><span data-stu-id="4cb43-145">This prevents edit and download of files.</span></span> <span data-ttu-id="4cb43-146">使用 PowerShell 來指定網站。</span><span class="sxs-lookup"><span data-stu-id="4cb43-146">Use PowerShell to specify sites.</span></span>|
|<span data-ttu-id="4cb43-147">**高管制**</span><span class="sxs-lookup"><span data-stu-id="4cb43-147">**Highly regulated**</span></span>|[<span data-ttu-id="4cb43-148">*永遠* 需要 MFA</span><span class="sxs-lookup"><span data-stu-id="4cb43-148">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="4cb43-149">在雲端應用程式的指派中包含 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="4cb43-149">Include SharePoint in the assignment of cloud apps.</span></span>|
||<span data-ttu-id="4cb43-150">[SharePoint 存取控制原則](#use-app-enforced-restrictions-in-sharepoint)：封鎖非管理裝置對特定 SharePoint 網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="4cb43-150">[SharePoint access control policy](#use-app-enforced-restrictions-in-sharepoint): Block access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="4cb43-151">使用 PowerShell 來指定網站。</span><span class="sxs-lookup"><span data-stu-id="4cb43-151">Use PowerShell to specify sites.</span></span>|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a><span data-ttu-id="4cb43-152">在 SharePoint 中使用應用程式強制限制</span><span class="sxs-lookup"><span data-stu-id="4cb43-152">Use app-enforced restrictions in SharePoint</span></span>

<span data-ttu-id="4cb43-153">如果您在 SharePoint 中執行存取控制，您必須在 Azure AD 中建立此條件式存取原則，以通知 Azure AD 強制執行您在 SharePoint 中設定的原則。</span><span class="sxs-lookup"><span data-stu-id="4cb43-153">If you implement access controls in SharePoint, you must create this Conditional Access policy in Azure AD to tell Azure AD to enforce the policies you configure in SharePoint.</span></span> <span data-ttu-id="4cb43-154">這個原則會套用至所有使用者，但是只會影響您在 SharePoint 中建立存取控制時使用 PowerShell 所指定之網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="4cb43-154">This policy applies to all users, but only affects access to the sites you specify using PowerShell when you create the access controls in SharePoint.</span></span>

<span data-ttu-id="4cb43-155">若要設定此原則，請參閱 [控制存取非管理裝置](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)中的「封鎖或限制存取特定 SharePoint 網站集合或 OneDrive 帳戶」。</span><span class="sxs-lookup"><span data-stu-id="4cb43-155">To configure this policy see "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="sharepoint-access-control-policies"></a><span data-ttu-id="4cb43-156">SharePoint 的存取控制原則</span><span class="sxs-lookup"><span data-stu-id="4cb43-156">SharePoint access control policies</span></span>

<span data-ttu-id="4cb43-157">Microsoft 建議您使用裝置存取控制，以機密和高管制內容來保護 SharePoint 網站中的內容。</span><span class="sxs-lookup"><span data-stu-id="4cb43-157">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="4cb43-158">您可以建立原則，以指定保護的層級，以及要套用保護的網站。</span><span class="sxs-lookup"><span data-stu-id="4cb43-158">You do this by creating a policy that specifies the level of protection and the sites to apply the protection to.</span></span>

- <span data-ttu-id="4cb43-159">機密網站：允許僅供瀏覽器存取。</span><span class="sxs-lookup"><span data-stu-id="4cb43-159">Sensitive sites: Allow browser-only access.</span></span> <span data-ttu-id="4cb43-160">這會防止使用者編輯及下載檔案。</span><span class="sxs-lookup"><span data-stu-id="4cb43-160">This prevents users from editing and downloading files.</span></span>
- <span data-ttu-id="4cb43-161">高度管制網站：封鎖非管理裝置的存取。</span><span class="sxs-lookup"><span data-stu-id="4cb43-161">Highly regulated sites: Block access from unmanaged devices.</span></span>

<span data-ttu-id="4cb43-162">請參閱「阻止或限制存取特定 SharePoint 網站集合或 OneDrive 帳戶」，以 [控制來自非管理裝置的存取](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="4cb43-162">See "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="how-these-policies-work-together"></a><span data-ttu-id="4cb43-163">這些原則共同運作的方式</span><span class="sxs-lookup"><span data-stu-id="4cb43-163">How these policies work together</span></span>

<span data-ttu-id="4cb43-164">請務必瞭解，SharePoint 網站許可權通常是以網站存取權的業務需求為基礎。</span><span class="sxs-lookup"><span data-stu-id="4cb43-164">It's important to understand that SharePoint site permissions are typically based on business need for access to sites.</span></span> <span data-ttu-id="4cb43-165">這些許可權是由網站擁有者管理，而且可以是高動態的。</span><span class="sxs-lookup"><span data-stu-id="4cb43-165">These permissions are managed by site owners and can be highly dynamic.</span></span> <span data-ttu-id="4cb43-166">使用 SharePoint 裝置存取原則可確保對這些網站的保護，不論是否將使用者指派至與基線、敏感或高度管制保護相關聯的 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="4cb43-166">Using SharePoint device access policies ensures protection to these sites, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="4cb43-167">下圖提供 SharePoint 裝置存取原則如何保護使用者對網站存取的範例。</span><span class="sxs-lookup"><span data-stu-id="4cb43-167">The following illustration provides an example of how SharePoint device access policies protect access to sites for a user.</span></span>

<span data-ttu-id="4cb43-168">[![SharePoint 裝置存取原則如何保護網站的範例](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span><span class="sxs-lookup"><span data-stu-id="4cb43-168">[![Example of how SharePoint device access policies protect sites](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span></span>

[<span data-ttu-id="4cb43-169">查看較大版本的此影像</span><span class="sxs-lookup"><span data-stu-id="4cb43-169">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

<span data-ttu-id="4cb43-170">James 具有指派的基準條件式存取原則，但可獲得對具有敏感或高管制保護之 SharePoint 網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="4cb43-170">James has baseline Conditional Access policies assigned, but he can be given access to SharePoint sites with sensitive or highly-regulated protection.</span></span>

- <span data-ttu-id="4cb43-171">如果 James 存取敏感或高管制的網站，他是使用自己電腦的成員，只要其電腦符合規範，就會授與其存取權。</span><span class="sxs-lookup"><span data-stu-id="4cb43-171">If James accesses a sensitive or highly-regulated site he is a member of using his PC, his access is granted as long as his PC is compliant.</span></span>
- <span data-ttu-id="4cb43-172">如果 James 存取機密的網站，他是使用未受管理的電話的成員（允許基準使用者使用），他只會收到對機密網站的瀏覽器存取權（由於為此網站設定的裝置存取原則）。</span><span class="sxs-lookup"><span data-stu-id="4cb43-172">If James accesses a sensitive site he is a member of using his unmanaged phone, which is allowed for baseline users, he will receive browser-only access to the sensitive site due to the device access policy configured for this site.</span></span>
- <span data-ttu-id="4cb43-173">如果 James 存取高管制網站，他是使用非管理電話的成員，則會因此網站設定的存取原則而封鎖。</span><span class="sxs-lookup"><span data-stu-id="4cb43-173">If James accesses a highly regulated site he is a member of using his unmanaged phone, he will be blocked due to the access policy configured for this site.</span></span> <span data-ttu-id="4cb43-174">他只能使用受管理和相容的電腦來存取此網站。</span><span class="sxs-lookup"><span data-stu-id="4cb43-174">He can only access this site using his managed and compliant PC.</span></span>

## <a name="next-step"></a><span data-ttu-id="4cb43-175">下一步</span><span class="sxs-lookup"><span data-stu-id="4cb43-175">Next step</span></span>

![步驟4： Microsoft 365 雲端應用程式的原則](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="4cb43-177">為下列專案設定條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="4cb43-177">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="4cb43-178">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4cb43-178">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="4cb43-179">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4cb43-179">Exchange Online</span></span>](secure-email-recommended-policies.md)
