---
title: 建議的安全文件原則 - Microsoft 365 企業版 | Microsoft Docs
description: 描述如何保護 SharePoint 檔案存取之 Microsoft 建議的原則。
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 72dd50649dba9e290d50c2831557c06db3cb7586
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866404"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a><span data-ttu-id="2caa1-103">保護 SharePoint 網站及檔案的原則建議</span><span class="sxs-lookup"><span data-stu-id="2caa1-103">Policy recommendations for securing SharePoint sites and files</span></span>
<span data-ttu-id="2caa1-p101">本文說明如何實作的建議的身分識別和來保護 SharePoint Online 和 OneDrive for Business 的裝置存取原則。這份指導建立之[一般身分識別與裝置存取的原則](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2caa1-p101">This article describes how to implement the recommended identity and device-access policies to protect SharePoint Online and OneDrive for Business. This guidance builds on the [Common identity and device access policies](identity-access-policies.md).</span></span> 

<span data-ttu-id="2caa1-p102">這些建議根據三種不同的層的安全性與保護 SharePoint 檔案可以套用根據您的需要的層次：**基準**、**機密**、 和**高度規範**。您可以深入了解這些安全性各層和建議的用戶端作業系統與這些建議[概觀 （英文)](microsoft-365-policies-configurations.md)中所參照。</span><span class="sxs-lookup"><span data-stu-id="2caa1-p102">These recommendations are based on three different tiers of security and protection for SharePoint files that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**. You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [the overview](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="2caa1-p103">除了實作這份指導，請務必設定 SharePoint 網站與右邊的保護，包括設定適當的權限的機密與高度規範的內容量。如需建立網站的比較基準 」、 機密、 和高度規範保護的詳細資訊，請參閱[Secure SharePoint Online 網站及檔案](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)。</span><span class="sxs-lookup"><span data-stu-id="2caa1-p103">In addition to implementing this guidance, be sure to configure SharePoint sites with the right amount of protection, including setting appropriate permissions for sensitive and highly-regulated content. For more information on creating sites for baseline, sensitive, and highly-regulated protection, see [Secure SharePoint Online sites and files](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files).</span></span> 

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a><span data-ttu-id="2caa1-110">更新加入 SharePoint 和 OneDrive for Business 的一般原則</span><span class="sxs-lookup"><span data-stu-id="2caa1-110">Updating common policies to include SharePoint and OneDrive for Business</span></span>
<span data-ttu-id="2caa1-p104">下圖說明設定的建議原則保護 SharePoint Online 和 OneDrive for Business 的檔案。它會指出哪些原則應更新或新建立要新增的 SharePoint Online 和 OneDrive for Business 的保護。</span><span class="sxs-lookup"><span data-stu-id="2caa1-p104">The following diagram illustrates the set of recommended policies for protecting files in SharePoint Online and OneDrive for Business. It indicates which policies should be updated or newly created to add protection for SharePoint Online and OneDrive for Business.</span></span>

![SharePoint Online 與 OneDrive 原則的摘要](../images/identity-access-ruleset-sharepoint.png)

<span data-ttu-id="2caa1-p105">如果當您建立通用原則包含 SharePoint Online，您只需要建立新的原則。當設定條件式存取規則，SharePoint Online 包含 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="2caa1-p105">If you included SharePoint Online when you created the common policies, you only need create the new policies. When configuring conditional access rules, SharePoint Online includes OneDrive for Business.</span></span>

<span data-ttu-id="2caa1-116">新的原則套用至指定的 SharePoint 網站的特定存取需求實作裝置保護機密和高度規範的內容。</span><span class="sxs-lookup"><span data-stu-id="2caa1-116">The new policies implement device protection for sensitive and highly-regulated content by applying specific access requirements to SharePoint sites that you specify.</span></span> 

<span data-ttu-id="2caa1-p106">下表列出您也需要檢閱和更新或建立新的 SharePoint Online 的原則。一般原則連結至[常見的身分識別與裝置存取原則](identity-access-policies.md)文章中的關聯的設定指示。</span><span class="sxs-lookup"><span data-stu-id="2caa1-p106">The following table lists the policies you either need to review and update or create new for SharePoint Online. The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>


|<span data-ttu-id="2caa1-119">保護層級</span><span class="sxs-lookup"><span data-stu-id="2caa1-119">Protection level</span></span>|<span data-ttu-id="2caa1-120">Policies</span><span class="sxs-lookup"><span data-stu-id="2caa1-120">Policies</span></span>|<span data-ttu-id="2caa1-121">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="2caa1-121">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="2caa1-122">**基準**</span><span class="sxs-lookup"><span data-stu-id="2caa1-122">**Baseline**</span></span>|[<span data-ttu-id="2caa1-123">登入風險為*medium*或*high*時需要 MFA</span><span class="sxs-lookup"><span data-stu-id="2caa1-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2caa1-124">包含 SharePoint Online 中的雲端應用程式的工作分派</span><span class="sxs-lookup"><span data-stu-id="2caa1-124">Include SharePoint Online in the assignment of cloud apps</span></span>|
|        |[<span data-ttu-id="2caa1-125">不支援經過驗證的封鎖用戶端</span><span class="sxs-lookup"><span data-stu-id="2caa1-125">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="2caa1-126">包含 SharePoint Online 中的雲端應用程式的工作分派</span><span class="sxs-lookup"><span data-stu-id="2caa1-126">Include SharePoint Online in the assignment of cloud apps</span></span>|
|        |[<span data-ttu-id="2caa1-127">定義應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="2caa1-127">Define app protection policies</span></span>](identity-access-policies.md#define-app-protection-policies)|<span data-ttu-id="2caa1-p107">請務必的應用程式清單中包括所有建議的應用程式。請務必更新每個平台 (iOS、 Android、 Windows) 的原則</span><span class="sxs-lookup"><span data-stu-id="2caa1-p107">Be sure all recommended apps are included in the list of apps. Be sure to update the policy for each platform (iOS, Android, Windows)</span></span>|
|        |[<span data-ttu-id="2caa1-130">需要相容的 Pc</span><span class="sxs-lookup"><span data-stu-id="2caa1-130">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="2caa1-131">包含 SharePoint Online 的雲端應用程式清單中</span><span class="sxs-lookup"><span data-stu-id="2caa1-131">Include SharePoint Online in list of cloud apps</span></span>|
|        |[<span data-ttu-id="2caa1-132">在 SharePoint Online 中使用強制執行的應用程式限制</span><span class="sxs-lookup"><span data-stu-id="2caa1-132">Use app enforced restrictions in SharePoint Online</span></span>](#use-app-enforced-restrictions-in-sharepoint-online)|<span data-ttu-id="2caa1-p108">新增此新原則。這會告知 Azure AD 使用 SharePoint Online 中所指定的設定。此規則套用至所有使用者，但只會影響包含在 SharePoint Online 存取原則的網站存取權</span><span class="sxs-lookup"><span data-stu-id="2caa1-p108">Add this new policy. This tells Azure AD to use the settings specified in SharePoint Online. This rule applies to all users, but only affects access to sites included in SharePoint Online access policies</span></span>|
|<span data-ttu-id="2caa1-136">**敏感性**</span><span class="sxs-lookup"><span data-stu-id="2caa1-136">**Sensitive**</span></span>|[<span data-ttu-id="2caa1-137">登入風險為*低*、 *medium*或*high*時需要 MFA</span><span class="sxs-lookup"><span data-stu-id="2caa1-137">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2caa1-138">包含 SharePoint Online 中的雲端應用程式的工作分派</span><span class="sxs-lookup"><span data-stu-id="2caa1-138">Include SharePoint Online in the assignments of cloud apps</span></span>|
|         |[<span data-ttu-id="2caa1-139">需要相容的 Pc*和*行動裝置</span><span class="sxs-lookup"><span data-stu-id="2caa1-139">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="2caa1-140">包含 SharePoint Online 的雲端應用程式清單中</span><span class="sxs-lookup"><span data-stu-id="2caa1-140">Include SharePoint Online in the list of cloud apps</span></span>|
||<span data-ttu-id="2caa1-141">[SharePoint Online 的存取控制原則](#sharepoint-online-access-control-policies)： 允許從未受管理的裝置僅供瀏覽器存取特定的 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="2caa1-141">[SharePoint Online access control policy](#sharepoint-online-access-control-policies): Allow browser-only access to specific SharePoint sites from unmanaged devices</span></span>|<span data-ttu-id="2caa1-p109">這可防止編輯及下載的檔案。使用 PowerShell 來指定的網站</span><span class="sxs-lookup"><span data-stu-id="2caa1-p109">This prevents edit and download of files. Use PowerShell to specify sites</span></span>|
|<span data-ttu-id="2caa1-144">**高管制**</span><span class="sxs-lookup"><span data-stu-id="2caa1-144">**Highly regulated**</span></span>|[<span data-ttu-id="2caa1-145">*永遠*需要 MFA</span><span class="sxs-lookup"><span data-stu-id="2caa1-145">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2caa1-146">包含 SharePoint Online 中的雲端應用程式的工作分派</span><span class="sxs-lookup"><span data-stu-id="2caa1-146">Include SharePoint Online in the assignment of cloud apps</span></span>|
||<span data-ttu-id="2caa1-147">[SharePoint Online 的存取控制原則](#use-app-enforced-restrictions-in-sharepoint-online)： 從未受管理的裝置封鎖特定的 SharePoint 網站的存取</span><span class="sxs-lookup"><span data-stu-id="2caa1-147">[SharePoint Online access control policy](#use-app-enforced-restrictions-in-sharepoint-online): Block access to specific SharePoint sites from unmanaged devices</span></span>|<span data-ttu-id="2caa1-148">使用 PowerShell 來指定的網站</span><span class="sxs-lookup"><span data-stu-id="2caa1-148">Use PowerShell to specify sites</span></span>|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a><span data-ttu-id="2caa1-149">在 SharePoint Online 中使用應用程式強制執行的限制</span><span class="sxs-lookup"><span data-stu-id="2caa1-149">Use app-enforced restrictions in SharePoint Online</span></span>
<span data-ttu-id="2caa1-p110">如果您在 SharePoint Online 中實作存取控制項，您必須建立此設定格式化的條件存取原則以告訴您在 SharePoint Online 中設定的原則強制執行的 Azure AD 的 Azure AD。此規則套用至所有使用者，但只會影響您指定當您在 SharePoint Online 中建立存取控制項使用 PowerShell 網站存取權。</span><span class="sxs-lookup"><span data-stu-id="2caa1-p110">If you implement access controls in SharePoint Online, you must create this conditional access policy in Azure AD to tell Azure AD to enforce the policies you configure in SharePoint Online. This rule applies to all users, but only affects access to the sites you specify using PowerShell when you create the access controls in SharePoint Online.</span></span>

<span data-ttu-id="2caa1-152">若要在本文中設定此原則，請參閱 「 封鎖] 或 [限制存取特定的 SharePoint 網站集合或 OneDrive 帳戶":[控制存取來自未受管理的裝置](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622)。</span><span class="sxs-lookup"><span data-stu-id="2caa1-152">To configure this policy see "Block or limit access to specific SharePoint site collections or OneDrive accounts" in this article: [Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).</span></span>


## <a name="sharepoint-online-access-control-policies"></a><span data-ttu-id="2caa1-153">SharePoint Online 的存取控制原則</span><span class="sxs-lookup"><span data-stu-id="2caa1-153">SharePoint Online access control policies</span></span>
<span data-ttu-id="2caa1-p111">Microsoft 建議您保護敏感和高度規範內容的裝置存取控制項使用在 SharePoint 網站內容。您執行這項作業來建立指定的保護及套用來保護所有網站層級的原則。</span><span class="sxs-lookup"><span data-stu-id="2caa1-p111">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls. You do this by creating a policy that specifies the level of protection and the sites to apply the protection to.</span></span> 
- <span data-ttu-id="2caa1-p112">機密網站： 允許瀏覽器唯讀存取。這樣會讓使用者編輯及下載檔案。</span><span class="sxs-lookup"><span data-stu-id="2caa1-p112">Sensitive sites: Allow browser-only access. This prevents users from editing and downloading files.</span></span>
- <span data-ttu-id="2caa1-158">高度規範網站： 封鎖來自未受管理的裝置的存取。</span><span class="sxs-lookup"><span data-stu-id="2caa1-158">Highly regulated sites: Block access from unmanaged devices.</span></span>

<span data-ttu-id="2caa1-159">請參閱本文中的"封鎖] 或 [限制存取特定的 SharePoint 網站集合或 OneDrive 帳戶":[控制存取來自未受管理的裝置](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622)。</span><span class="sxs-lookup"><span data-stu-id="2caa1-159">See "Block or limit access to specific SharePoint site collections or OneDrive accounts" in this article: [Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622) .</span></span> 

## <a name="how-these-policies-work-together"></a><span data-ttu-id="2caa1-160">這些原則如何搭配運作</span><span class="sxs-lookup"><span data-stu-id="2caa1-160">How these policies work together</span></span>
<span data-ttu-id="2caa1-p113">請務必了解 SharePoint 網站權限通常根據網站存取權的業務需求。這些權限由網站擁有者管理，可高度動態。使用裝置存取原則可確保這些網站，不論是否將使用者指派至 Azure AD 群組來保護 SharePoint 基準、 機密、 相關聯或高度規範保護。</span><span class="sxs-lookup"><span data-stu-id="2caa1-p113">It's important to understand that SharePoint site permissions are typically based on business need for access to sites. These permissions are managed by site owners and can be highly dynamic. Using SharePoint device access policies ensures protection to these sites, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span> 

<span data-ttu-id="2caa1-164">下圖提供範例 SharePoint 裝置存取原則如何保護網站存取權。</span><span class="sxs-lookup"><span data-stu-id="2caa1-164">The following illustration provides an example of how SharePoint device access policies protect access to sites.</span></span>

![SharePoint 裝置存取原則如何保護的網站](../images/SharePoint-rules-scenario.png)

<span data-ttu-id="2caa1-166">在此圖例中：</span><span class="sxs-lookup"><span data-stu-id="2caa1-166">In the illustration:</span></span>
- <span data-ttu-id="2caa1-167">James 指派給與比較基準保護相關聯的設定格式化的條件存取原則，但他可以授與存取權敏感或高度規範保護相關聯的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="2caa1-167">James is assigned to conditional access policies associated with baseline protection, but he can be given access to SharePoint sites associated with sensitive or highly-regulated protection.</span></span> 
- <span data-ttu-id="2caa1-168">如果 James 存取專為機密或高度規範他是使用其電腦的成員，其授與存取只要其電腦是相容。</span><span class="sxs-lookup"><span data-stu-id="2caa1-168">If James accesses a sensitive or highly-regulated site he is a member of using his PC, his access is granted as long as his PC is compliant.</span></span>
- <span data-ttu-id="2caa1-169">如果 James 存取機密網站他的成員使用其未受管理的電話，允許基準使用者，他就會收到僅供瀏覽器存取機密網站因為針對此網站設定的裝置存取原則。</span><span class="sxs-lookup"><span data-stu-id="2caa1-169">If James accesses a sensitive site he is a member of using his unmanaged phone, which is allowed for baseline users, he will receive browser-only access to the sensitive site due to the device access policy configured for this site.</span></span> 
- <span data-ttu-id="2caa1-p114">如果 James 可存取他是使用其未受管理的電話成員的高度規範的網站，他將會封鎖因為設定此網站的存取原則。他只可以存取此網站使用其受管理與相容的 PC。</span><span class="sxs-lookup"><span data-stu-id="2caa1-p114">If James accesses a highly regulated site he is a member of using his unmanaged phone, he will be blocked due to the access policy configured for this site. He can only access this site using his managed and compliant PC.</span></span>


<!---
##Block access to content from unmanaged devices (SharePoint admin center)
In the case of SharePoint Online, when a conditional access policy is applied to enforce Intune app protection policies, this might not apply to all applications that access SharePoint Online. Some applications, such as Exchange, have access to some SharePoint resources. For example, Exchange allows attaching SharePoint files by default. Conditional access policies applied to SharePoint Online will not restrict this access. 

To ensure baseline protection is applied uniformly, regardless of which service is accessing SharePoint Online and OneDrive for Business, configure access controls directly in SharePoint admin center. We recommend you configure the following:
- Block access from unmanaged devices. This includes devices that aren't compliant or joined to a domain. 
- Block access from app that don't use modern authentication.

See [Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).
-->



## <a name="next-steps"></a><span data-ttu-id="2caa1-172">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2caa1-172">Next steps</span></span>
[<span data-ttu-id="2caa1-173">保護 SharePoint Online 網站與檔案</span><span class="sxs-lookup"><span data-stu-id="2caa1-173">Secure SharePoint Online sites and files</span></span>](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
