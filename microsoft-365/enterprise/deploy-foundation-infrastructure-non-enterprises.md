---
title: 適用於非企業的 Microsoft 365 企業版底層基礎結構
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/22/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 提供非企業組織逐步執行 Microsoft 365 企業版底層基礎結構的簡化階段。
ms.openlocfilehash: 64d911a9d59d5b9b1a450a9a122463699ec8eab8
ms.sourcegitcommit: 2cf0d57b1771b37db773c3eaabac8456a6fa9195
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2019
ms.locfileid: "34419812"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-for-non-enterprises"></a><span data-ttu-id="00cdd-103">適用於非企業的 Microsoft 365 企業版底層基礎結構</span><span class="sxs-lookup"><span data-stu-id="00cdd-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="00cdd-104">非企業組織也可以部署 Microsoft 365 企業版，體驗經過整合而安全的基礎結構協助團隊合作並盡情發揮創意的商業價值。</span><span class="sxs-lookup"><span data-stu-id="00cdd-104">Non-enterprise organizations can also deploy Microsoft 365 Enterprise and realize the business value of an integrated and secure infrastructure that enables teamwork and unlocks creativity.</span></span> <span data-ttu-id="00cdd-105">非企業型態的組織通常有：</span><span class="sxs-lookup"><span data-stu-id="00cdd-105">A non-enterprise typically has:</span></span>

- <span data-ttu-id="00cdd-106">少量的內部部署 IT 基礎結構，例如電子郵件、檔案伺服器和 Active Directory Domain Services (AD DS) 網域，或者完全沒有。</span><span class="sxs-lookup"><span data-stu-id="00cdd-106">A small amount of on-premises IT infrastructure, such as email and file servers and an Active Directory Domain Services (AD DS) domain, or none at all.</span></span>
- <span data-ttu-id="00cdd-107">少量的 IT 人員，其中大部分都是 IT 通才，而不是特定技術或工作負載 (例如網路或電子郵件) 的專家。</span><span class="sxs-lookup"><span data-stu-id="00cdd-107">A small IT staff, most of whom are IT generalists, rather than specialists in a specific technology or workload such as networking or email.</span></span>

<span data-ttu-id="00cdd-108">對於非企業型態的較小型組織，Microsoft 提供 [Microsoft 365 商務版](https://www.microsoft.com/microsoft-365/business)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-108">For your smaller, non-enterprise organization, Microsoft offers [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business).</span></span> <span data-ttu-id="00cdd-109">不過，有一些原因您可能需要 Microsoft 365 企業版，例如：</span><span class="sxs-lookup"><span data-stu-id="00cdd-109">However, there are reasons why you might need Microsoft 365 Enterprise, such as:</span></span>

- <span data-ttu-id="00cdd-110">您的組織需要或即將需要 300 個以上的 Microsoft 365 授權，這也是 Microsoft 365 商務版的最大授權數目。</span><span class="sxs-lookup"><span data-stu-id="00cdd-110">Your organization needs more or will need more than 300 Microsoft 365 licenses, which is the maximum for Microsoft 365 Business.</span></span>
- <span data-ttu-id="00cdd-111">您的組織需要 Microsoft 365 商務版無法提供的進階生產力、語音、安全性和分析功能。</span><span class="sxs-lookup"><span data-stu-id="00cdd-111">Your organization needs the advanced productivity, voice, security, and analytics that are not available with Microsoft 365 Business.</span></span>

<span data-ttu-id="00cdd-112">本文將逐步引導您以簡化的方式部署適用於非企業的 Microsoft 365 企業版底層基礎結構。</span><span class="sxs-lookup"><span data-stu-id="00cdd-112">This article steps you through a simplified deployment of the foundation infrastructure of Microsoft 365 Enterprise suitable for your non-enterprise.</span></span>

## <a name="first-set-up-your-subscription"></a><span data-ttu-id="00cdd-113">首先設定您的訂閱</span><span class="sxs-lookup"><span data-stu-id="00cdd-113">First, set up your subscription</span></span>

<span data-ttu-id="00cdd-114">您必須為您的訂閱設定網域名稱系統 (DNS) 網域。</span><span class="sxs-lookup"><span data-stu-id="00cdd-114">You must set up the Domain Name System (DNS) domains for your subscription.</span></span> <span data-ttu-id="00cdd-115">如果您已經有 Office 365 訂閱，這應該已經完成。</span><span class="sxs-lookup"><span data-stu-id="00cdd-115">If you already have an Office 365 subscription, this should have been done.</span></span> <span data-ttu-id="00cdd-116">如果沒有，請依照[新增網域至 Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="00cdd-116">If not, follow the instructions in [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span></span>

<span data-ttu-id="00cdd-117">接下來，您需要為 Microsoft 365 設定額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="00cdd-117">Next, you need to configure additional security for Microsoft 365.</span></span> <span data-ttu-id="00cdd-118">請依照[設定增強的安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)中的指示。</span><span class="sxs-lookup"><span data-stu-id="00cdd-118">Follow the instructions in [Configure increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

## <a name="phase-1-networking"></a><span data-ttu-id="00cdd-119">第 1 階段：網路</span><span class="sxs-lookup"><span data-stu-id="00cdd-119">Phase 1: Networking</span></span>

<span data-ttu-id="00cdd-120">非企業組織在每間辦公室通常要有當地的網際網路連線，而且不要使用 proxy 伺服器、防火牆或封包檢查裝置。</span><span class="sxs-lookup"><span data-stu-id="00cdd-120">Non-enterprise organizations typically have local Internet connections in each office and do not use proxy servers, firewalls, or packet inspection devices.</span></span> <span data-ttu-id="00cdd-121">每間辦公室的網際網路服務提供者 (ISP) 都要有當地的 DNS 伺服器，讓流量能夠導向到最接近您辦公室和內部部署使用者的 Microsoft 365 雲端伺服器。</span><span class="sxs-lookup"><span data-stu-id="00cdd-121">The Internet service provider (ISP) at each office has a regionally local DNS server so that traffic is directed to the Microsoft 365 cloud servers that are closest to your offices and their on-premises users.</span></span>

<span data-ttu-id="00cdd-122">因此，您只需要向您的 ISP 確認每間辦公室的連線：</span><span class="sxs-lookup"><span data-stu-id="00cdd-122">Therefore, you only need to verify with your ISP that the connection at each of your office locations:</span></span>

- <span data-ttu-id="00cdd-123">使用當地的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="00cdd-123">Uses a regionally local DNS server.</span></span>
- <span data-ttu-id="00cdd-124">當使用者開始使用更多 Microsoft 365 雲端服務時，能夠配合目前及未來的需求。</span><span class="sxs-lookup"><span data-stu-id="00cdd-124">Is adequate for current and future needs as your users begin using more Microsoft 365 cloud services.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="00cdd-125">您目前的設定</span><span class="sxs-lookup"><span data-stu-id="00cdd-125">Your configuration so far</span></span>

<span data-ttu-id="00cdd-126">以下是將第 1 階段項目醒目提示的視覺摘要。</span><span class="sxs-lookup"><span data-stu-id="00cdd-126">Here is a visual summary with the Phase 1 element highlighted.</span></span> <span data-ttu-id="00cdd-127">**您的組織**可以有多間辦公室，每一間都能夠透過當地的網際網路連線，連線到使用當地 DNS 伺服器的 ISP。</span><span class="sxs-lookup"><span data-stu-id="00cdd-127">**Your organization** can be multiple offices, each of which has a local Internet connection with an ISP that uses a regionally local DNS server.</span></span> <span data-ttu-id="00cdd-128">透過 ISP，每間辦公室的使用者都可以連線到最接近的 Microsoft 網路位置，並且取得 Microsoft 365 訂閱的資源。</span><span class="sxs-lookup"><span data-stu-id="00cdd-128">Through the ISP, users in each office can reach the nearest Microsoft network location and the resources of your Microsoft 365 subscription.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/networking-config.png)

## <a name="phase-2-identity"></a><span data-ttu-id="00cdd-129">第 2 階段：身分識別</span><span class="sxs-lookup"><span data-stu-id="00cdd-129">Phase 2: Identity</span></span>

<span data-ttu-id="00cdd-130">組織的每位員工都必須能夠登入，條件是在您的 Microsoft 365 企業版訂閱的 Azure Active Directory (Azure AD) 租用戶中必須要有使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="00cdd-130">Each of the employees of your organization must be able to sign in, which requires a user account in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 Enterprise subscription.</span></span> <span data-ttu-id="00cdd-131">然後使用群組來包含使用者帳戶和其他群組來進行通訊，或取得授權資源 (例如 SharePoint Online 網站或小組) 的存取權。</span><span class="sxs-lookup"><span data-stu-id="00cdd-131">Groups are then used to contain user accounts and other groups to communicate or gain access to permissioned resources, such as a SharePoint Online site or a team.</span></span> 

### <a name="administrator-accounts"></a><span data-ttu-id="00cdd-132">系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="00cdd-132">Administrator accounts</span></span>

<span data-ttu-id="00cdd-133">透過非常強的密碼與多重要素驗證 (MFA)，保護您的全域系統管理員使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="00cdd-133">Protect your global administrator user accounts by requiring very strong passwords and multi-factor authentication (MFA).</span></span> <span data-ttu-id="00cdd-134">如需詳細資訊，請參閱[保護全域系統管理員帳戶](identity-designate-protect-admin-accounts.md#protect-global-administrator-accounts)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-134">See [Protect your Office 365 global administrator accounts](identity-designate-protect-admin-accounts.md#protect-global-administrator-accounts) for more information about configuration.</span></span>

<span data-ttu-id="00cdd-135">如果您的組織需要高安全性而且擁有 Microsoft 365 企業版 E5，請使用 Azure AD Privileged Identity Management 啟用系統管理員即時存取。</span><span class="sxs-lookup"><span data-stu-id="00cdd-135">If your organization requires high security and you have Microsoft 365 Enterprise E5, use Azure AD Privileged Identity Management to enable just-in-time administrator access.</span></span> <span data-ttu-id="00cdd-136">如需詳細資訊，請參閱[設定隨選全域系統管理員](identity-designate-protect-admin-accounts.md#set-up-on-demand-global-administrators)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-136">See [Set up on-demand global administrators](identity-designate-protect-admin-accounts.md#set-up-on-demand-global-administrators) for more information.</span></span>

### <a name="recommendations-for-groups"></a><span data-ttu-id="00cdd-137">群組的建議</span><span class="sxs-lookup"><span data-stu-id="00cdd-137">Recommendations for groups</span></span>

<span data-ttu-id="00cdd-138">如果您有內部部署 AD DS 網域，請在 Microsoft 365 企業版中繼續使用這些群組，如同 Azure AD 中的群組。</span><span class="sxs-lookup"><span data-stu-id="00cdd-138">If you have an on-premises AD DS domain, continue to use those groups in Microsoft 365 Enterprise as groups in Azure AD.</span></span>

<span data-ttu-id="00cdd-139">如果您沒有內部部署 AD DS 網域，請使用這些安全性層級在 Azure AD 中建立安全性群組。</span><span class="sxs-lookup"><span data-stu-id="00cdd-139">If you don’t have an on-premises AD DS domain, create security groups in Azure AD using these levels of security.</span></span>

| <span data-ttu-id="00cdd-140">安全性層級</span><span class="sxs-lookup"><span data-stu-id="00cdd-140">Security Level</span></span> | <span data-ttu-id="00cdd-141">描述</span><span class="sxs-lookup"><span data-stu-id="00cdd-141">Description</span></span> | <span data-ttu-id="00cdd-142">範例</span><span class="sxs-lookup"><span data-stu-id="00cdd-142">Examples</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="00cdd-143">基準</span><span class="sxs-lookup"><span data-stu-id="00cdd-143">Baseline</span></span> | <span data-ttu-id="00cdd-144">這是保護資料，以及保護存取資料的身分識別和裝置的最低和預設標準。</span><span class="sxs-lookup"><span data-stu-id="00cdd-144">This is a minimum and default  standard for protecting data and the identities and devices that access your data.</span></span> <BR><BR> <span data-ttu-id="00cdd-145">這通常是由大部分使用者管理的大部分組織資料。</span><span class="sxs-lookup"><span data-stu-id="00cdd-145">This is typically most of your organization’s data managed by most of your users.</span></span> | <span data-ttu-id="00cdd-146">第一線員工 (例如銷售、行銷、客戶服務、管理和製造) 的群組。</span><span class="sxs-lookup"><span data-stu-id="00cdd-146">Groups for first line workers, such as sales, marketing, support, administration, and manufacturing.</span></span> |
| <span data-ttu-id="00cdd-147">敏感性</span><span class="sxs-lookup"><span data-stu-id="00cdd-147">Sensitive</span></span> | <span data-ttu-id="00cdd-148">這可以額外保護必須以超過基準層級保護的資料子集。</span><span class="sxs-lookup"><span data-stu-id="00cdd-148">This is additional protection for a subset of your data that must be protected beyond the baseline level.</span></span> <span data-ttu-id="00cdd-149">這些群組包含的使用者可以使用和建立特定部門的敏感性資料，以及並非每個人都能取得的專案敏感性資料。</span><span class="sxs-lookup"><span data-stu-id="00cdd-149">These groups contain users that use and create sensitive data that is specific to departments and projects that are not meant to be available to everyone.</span></span> | <span data-ttu-id="00cdd-150">正在開發新產品的產品團隊或行銷團隊</span><span class="sxs-lookup"><span data-stu-id="00cdd-150">Product or marketing teams that are developing future products</span></span> |
| <span data-ttu-id="00cdd-151">高管制</span><span class="sxs-lookup"><span data-stu-id="00cdd-151">Highly regulated</span></span> | <span data-ttu-id="00cdd-152">這是保護的最高層級，適用於高度機密、被視為是智慧財產或商業機密的少量資料，或必須遵守安全性規範的資料。</span><span class="sxs-lookup"><span data-stu-id="00cdd-152">Highly regulated: This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span> |  <span data-ttu-id="00cdd-153">研究、法律和財務團隊。</span><span class="sxs-lookup"><span data-stu-id="00cdd-153">Research, legal, and financial teams.</span></span> <BR><BR> <span data-ttu-id="00cdd-154">儲存或使用客戶或合作夥伴資料的團隊。</span><span class="sxs-lookup"><span data-stu-id="00cdd-154">Teams storing or using customer or partner data.</span></span> |

### <a name="hybrid-identity"></a><span data-ttu-id="00cdd-155">混合式身分識別</span><span class="sxs-lookup"><span data-stu-id="00cdd-155">Hybrid identity</span></span>

<span data-ttu-id="00cdd-156">如果您有內部部署 AD DS 網域，請在伺服器上使用密碼雜湊同步處理 (PHS) 設定 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="00cdd-156">If you have an on-premises AD DS domain, configure Azure AD Connect on a server with password hash synchronization (PHS).</span></span> <span data-ttu-id="00cdd-157">如需詳細資訊，請參閱[同步處理身分識別](identity-azure-ad-connect.md)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-157">See [Synchronize identities](identity-azure-ad-connect.md) for more information.</span></span>

### <a name="more-secure-user-access-with-conditional-access-policies"></a><span data-ttu-id="00cdd-158">條件式存取原則的使用者存取更安全</span><span class="sxs-lookup"><span data-stu-id="00cdd-158">More secure user access with conditional access policies</span></span>

<span data-ttu-id="00cdd-159">Azure AD 會評估使用者登入的條件，而且可以使用條件式存取原則來授與或拒絕存取，然後強制實行完成登入必須採取的進一步動作。</span><span class="sxs-lookup"><span data-stu-id="00cdd-159">Azure AD evaluates the conditions of user sign-ins and can use conditional access policies to grant or deny access and impose further actions that must be taken to complete the sign-in.</span></span> <span data-ttu-id="00cdd-160">例如，如果 Azure AD 判斷登入是在中高風險的情況下發生，就可以要求使用者執行 MFA 才能完成登入。</span><span class="sxs-lookup"><span data-stu-id="00cdd-160">For example, if Azure AD determines that the sign-in is happening under medium or high-risk conditions, it can require the user to perform MFA to complete the sign-in.</span></span>

<span data-ttu-id="00cdd-161">您要將條件式存取原則套用到使用者帳戶或群組。</span><span class="sxs-lookup"><span data-stu-id="00cdd-161">You apply conditional access policies to user accounts or groups.</span></span> <span data-ttu-id="00cdd-162">若要更容易指派條件式存取原則，請在組織中建立這些 Azure AD 安全性群組：</span><span class="sxs-lookup"><span data-stu-id="00cdd-162">To facilitate an easier assignment of conditional access policies, create these Azure AD security groups in your organization:</span></span>

- <span data-ttu-id="00cdd-163">BASELINE</span><span class="sxs-lookup"><span data-stu-id="00cdd-163">Baseline</span></span>

  <span data-ttu-id="00cdd-164">包含能夠存取基準資料的使用者的群組或使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="00cdd-164">Contains the groups or user accounts for users with access to baseline data.</span></span>

- <span data-ttu-id="00cdd-165">SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="00cdd-165">Sensitive</span></span>

  <span data-ttu-id="00cdd-166">包含能夠存取敏感性資料的使用者的群組或使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="00cdd-166">Contains the groups or user accounts for users with access to sensitive data.</span></span>

- <span data-ttu-id="00cdd-167">HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="00cdd-167">HIGHLY-REGULATED</span></span>

  <span data-ttu-id="00cdd-168">包含能夠存取高管制資料的使用者的群組或使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="00cdd-168">Contains the groups or user accounts for users with access to highly regulated data.</span></span>

- <span data-ttu-id="00cdd-169">COND-ACCESS-EXCLUDE</span><span class="sxs-lookup"><span data-stu-id="00cdd-169">COND-ACCESS-EXCLUDE</span></span>

  <span data-ttu-id="00cdd-170">這是一個空白群組，您可以用來暫時將某位使用者排除在條件式存取原則之外。</span><span class="sxs-lookup"><span data-stu-id="00cdd-170">An empty group that you can use to temporarily exclude a user from conditional access policies.</span></span>

<span data-ttu-id="00cdd-171">以下是要啟用或建立的 Azure AD 條件式存取原則清單。</span><span class="sxs-lookup"><span data-stu-id="00cdd-171">Here is the list of Azure AD conditional access policies to enable or create.</span></span>

| <span data-ttu-id="00cdd-172">Azure AD 條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="00cdd-172">Azure AD conditional access policy</span></span> | <span data-ttu-id="00cdd-173">要套用的群組</span><span class="sxs-lookup"><span data-stu-id="00cdd-173">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="00cdd-174">基準原則：管理員需要進行 MFA</span><span class="sxs-lookup"><span data-stu-id="00cdd-174">Baseline policy: Require MFA for admins</span></span> | <span data-ttu-id="00cdd-175">此原則會套用到管理員角色，因此不需要指定群組。</span><span class="sxs-lookup"><span data-stu-id="00cdd-175">This policy applies to admin roles, so no groups need to be specified.</span></span> <span data-ttu-id="00cdd-176">只需要啟用此原則。</span><span class="sxs-lookup"><span data-stu-id="00cdd-176">This policy just needs to be enabled.</span></span> <span data-ttu-id="00cdd-177">必須建立並啟用所有後續的原則。</span><span class="sxs-lookup"><span data-stu-id="00cdd-177">All subsequent policies need to be created and enabled.</span></span> |
| <span data-ttu-id="00cdd-178">封鎖不支援新式驗證的用戶端</span><span class="sxs-lookup"><span data-stu-id="00cdd-178">Block clients that don't support modern authentication</span></span> | <span data-ttu-id="00cdd-179">在原則設定中選取 [所有使用者]。</span><span class="sxs-lookup"><span data-stu-id="00cdd-179">Select “All users” in the policy settings.</span></span> |
| <span data-ttu-id="00cdd-180">登入風險為中或高時需要 MFA (需要 Microsoft 365 企業版 E5)</span><span class="sxs-lookup"><span data-stu-id="00cdd-180">Require MFA when sign-in risk is medium or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="00cdd-181">BASELINE</span><span class="sxs-lookup"><span data-stu-id="00cdd-181">Baseline</span></span> |
| <span data-ttu-id="00cdd-182">登入風險為低、中或高時需要 MFA (需要 Microsoft 365 企業版 E5)</span><span class="sxs-lookup"><span data-stu-id="00cdd-182">Require MFA when sign-in risk is low, medium, or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="00cdd-183">SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="00cdd-183">Sensitive</span></span> |
| <span data-ttu-id="00cdd-184">永遠需要 MFA</span><span class="sxs-lookup"><span data-stu-id="00cdd-184">Always require MFA</span></span> | <span data-ttu-id="00cdd-185">HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="00cdd-185">HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="00cdd-186">在 iOS 和 Android 裝置上必須是核准的應用程式</span><span class="sxs-lookup"><span data-stu-id="00cdd-186">Require approved apps on iOS and Android devices</span></span> | <span data-ttu-id="00cdd-187">BASELINE、SENSITIVE、HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="00cdd-187">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="00cdd-188">需要相容的電腦</span><span class="sxs-lookup"><span data-stu-id="00cdd-188">Require compliant PCs</span></span> | <span data-ttu-id="00cdd-189">BASELINE</span><span class="sxs-lookup"><span data-stu-id="00cdd-189">Baseline</span></span> |
| <span data-ttu-id="00cdd-190">需要相容的電腦，以及 iOS 和 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="00cdd-190">Require compliant PCs and iOS and Android devices</span></span> | <span data-ttu-id="00cdd-191">SENSITIVE、HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="00cdd-191">SENSITIVE, HIGHLY-REGULATED</span></span> |
|||

<span data-ttu-id="00cdd-192">以下是要建立和啟用的 Azure AD Identity Protection (需要 Microsoft 365 企業版 E5) 使用者風險原則。</span><span class="sxs-lookup"><span data-stu-id="00cdd-192">Here is the Azure AD Identity Protection (requires Microsoft 365 Enterprise E5) user risk policy to create and enable.</span></span>

| <span data-ttu-id="00cdd-193">Azure AD Identity Protection 使用者風險原則</span><span class="sxs-lookup"><span data-stu-id="00cdd-193">Azure AD Identity Protection user risk policy</span></span> | <span data-ttu-id="00cdd-194">要套用的群組</span><span class="sxs-lookup"><span data-stu-id="00cdd-194">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="00cdd-195">高風險使用者必須變更密碼</span><span class="sxs-lookup"><span data-stu-id="00cdd-195">High risk users must change passwords</span></span> | <span data-ttu-id="00cdd-196">在原則設定中選取 [所有使用者]。</span><span class="sxs-lookup"><span data-stu-id="00cdd-196">Select “All users” in the policy settings.</span></span> |
|||

<span data-ttu-id="00cdd-197">如需指示，請參閱[一般身分識別與裝置存取原則](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-197">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="groups-for-easier-management"></a><span data-ttu-id="00cdd-198">更容易管理的群組</span><span class="sxs-lookup"><span data-stu-id="00cdd-198">Groups for easier management</span></span>

<span data-ttu-id="00cdd-199">以下是一些讓您能夠更輕鬆組成群組和管理授權的功能。</span><span class="sxs-lookup"><span data-stu-id="00cdd-199">Here are some features that can make group and licensing management easier for you.</span></span>

| <span data-ttu-id="00cdd-200">功能</span><span class="sxs-lookup"><span data-stu-id="00cdd-200">Feature</span></span> | <span data-ttu-id="00cdd-201">用途</span><span class="sxs-lookup"><span data-stu-id="00cdd-201">Use</span></span> |
|:------|:-----|
| <span data-ttu-id="00cdd-202">自助式群組管理</span><span class="sxs-lookup"><span data-stu-id="00cdd-202">Self-service group management</span></span> | <span data-ttu-id="00cdd-203">允許由群組擁有者而不是 IT 人員管理 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="00cdd-203">Allow management of Azure AD groups by group owners instead of IT staff.</span></span> <span data-ttu-id="00cdd-204">如需詳細資訊，請參閱[自助式群組管理](identity-self-service-group-management.md#allow-users-to-create-and-manage-their-own-groups)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-204">See [Self-service group management](identity-self-service-group-management.md#allow-users-to-create-and-manage-their-own-groups) for more information.</span></span> |
| <span data-ttu-id="00cdd-205">動態群組成員資格</span><span class="sxs-lookup"><span data-stu-id="00cdd-205">Dynamic group membership</span></span> | <span data-ttu-id="00cdd-206">根據使用者帳戶屬性 (例如部門或國家/地區) 來設定自動新增或移除 Azure AD 群組的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="00cdd-206">Configure automatic addition or removal of user accounts from Azure AD groups based on user account attributes, such as Department or Country.</span></span> <span data-ttu-id="00cdd-207">如需詳細資訊，請參閱[動態群組成員資格](identity-self-service-group-management.md#set-up-dynamic-group-membership)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-207">See [Dynamic group membership](identity-self-service-group-management.md#set-up-dynamic-group-membership) for more information.</span></span> |
| <span data-ttu-id="00cdd-208">群組型授權</span><span class="sxs-lookup"><span data-stu-id="00cdd-208">Group-based licensing</span></span> | <span data-ttu-id="00cdd-209">使用群組成員資格，可自動指派或取消指派授權給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="00cdd-209">Use group membership to automatically assign or unassign licenses to user accounts.</span></span> <span data-ttu-id="00cdd-210">如需詳細資訊，請參閱[群組型授權](identity-self-service-group-management.md#set-up-automatic-licensing)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-210">See [Group-based licensing](identity-self-service-group-management.md#set-up-automatic-licensing) for more information.</span></span> |
|  |  |

<span data-ttu-id="00cdd-211">如果您使用群組型授權，請建立一個名為 LICENSED 的群組來包含已指派 Microsoft 365 企業版授權的使用者帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="00cdd-211">If you are using group-based licensing, create a group named LICENSED to contain user account names that are assigned a Microsoft 365 Enterprise license.</span></span>

### <a name="monitor-user-access"></a><span data-ttu-id="00cdd-212">監視使用者存取</span><span class="sxs-lookup"><span data-stu-id="00cdd-212">Monitor user access</span></span>

<span data-ttu-id="00cdd-213">如果您有 Microsoft 365 企業版 E5，就可以使用 Azure AD Identity Protection 來監視和分析使用者登入是否有認證洩露的問題。</span><span class="sxs-lookup"><span data-stu-id="00cdd-213">If you have Microsoft 365 Enterprise E5, you can use Azure AD Identity Protection to monitor and analyze user sign-ins for credential compromise.</span></span> <span data-ttu-id="00cdd-214">如需詳細資訊，請參閱[防護認證洩露](identity-multi-factor-authentication.md#protect-against-credential-compromise)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-214">See [Protect against credential compromise](identity-multi-factor-authentication.md#protect-against-credential-compromise) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="00cdd-215">您目前的設定</span><span class="sxs-lookup"><span data-stu-id="00cdd-215">Your configuration so far</span></span>

<span data-ttu-id="00cdd-216">以下是混合式身分識別在身分識別階段的視覺摘要 (將新項目醒目提示)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-216">Here is a visual summary of the Identity phase for hybrid identity, with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/identity-config.png)
 
<span data-ttu-id="00cdd-217">新的和醒目提示的身分識別項目包括：</span><span class="sxs-lookup"><span data-stu-id="00cdd-217">The new and highlighted identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-adds.png) | <span data-ttu-id="00cdd-218">有使用者帳戶和群組的內部部署 AD DS 網域。</span><span class="sxs-lookup"><span data-stu-id="00cdd-218">An on-premises AD DS domain with user accounts and groups.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aadconnect.png) | <span data-ttu-id="00cdd-219">執行 Azure AD Connect 的 Windows 伺服器。</span><span class="sxs-lookup"><span data-stu-id="00cdd-219">A Windows-based server running Azure AD Connect.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts.png) | <span data-ttu-id="00cdd-220">Azure AD 中已同步處理的 AD DS 帳戶和群組。</span><span class="sxs-lookup"><span data-stu-id="00cdd-220">The synchronized set of AD DS accounts and groups in Azure AD.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="00cdd-221">用於驗證、保護全域帳戶，以及更容易管理群組和授權的 Azure AD 設定。</span><span class="sxs-lookup"><span data-stu-id="00cdd-221">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="00cdd-222">Azure AD 條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="00cdd-222">Azure AD conditional access policies.</span></span> |
|||

## <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="00cdd-223">第 3 階段：Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="00cdd-223">Phase 3: Windows 10 Enterprise</span></span>

<span data-ttu-id="00cdd-224">若要確保您的 Windows 10 企業版裝置已整合到 Microsoft 365 的身分識別和安全性基礎結構，您的選項有：</span><span class="sxs-lookup"><span data-stu-id="00cdd-224">To ensure that your Windows 10 Enterprise devices are integrated into the identity and security infrastructure of Microsoft 365, here are your options:</span></span>

- <span data-ttu-id="00cdd-225">僅雲端 (您沒有內部部署 AD DS 網域)</span><span class="sxs-lookup"><span data-stu-id="00cdd-225">Cloud-only (you do not have on-premises AD DS domain)</span></span>

  <span data-ttu-id="00cdd-226">將每個 Windows 10 企業版裝置加入訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="00cdd-226">Join each Windows 10 Enterprise device to the Azure AD tenant of your subscription.</span></span>

  <span data-ttu-id="00cdd-227">如需詳細資訊，請參閱[將您的工作裝置加入組織的網路](https://docs.microsoft.com/zh-TW/azure/active-directory/user-help/user-help-join-device-on-network)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-227">See [Join your work device to your organization's network](https://docs.microsoft.com/en-us/azure/active-directory/user-help/user-help-join-device-on-network) for more information.</span></span>

- <span data-ttu-id="00cdd-228">混合式 (您有內部部署 AD DS 網域)</span><span class="sxs-lookup"><span data-stu-id="00cdd-228">Hybrid (you have on-premises AD DS domain)</span></span>

  <span data-ttu-id="00cdd-229">針對每個已加入 AD DS 網域的現有 Windows 10 企業版裝置，將它們加入 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="00cdd-229">For each existing Windows 10 Enterprise device already joined to your AD DS domain, join them to the Azure AD tenant.</span></span> <span data-ttu-id="00cdd-230">如需指示，請參閱[如何設定已加入混合式 Azure Active Directory 的裝置](https://go.microsoft.com/fwlink/p/?linkid=872870)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-230">See [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870) for the instructions.</span></span>

  <span data-ttu-id="00cdd-231">針對每個新的 Windows 10 企業版裝置，將它們加入您的 AD DS 網域，然後將它們加入 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="00cdd-231">For each new Windows 10 Enterprise device, join them to your AD DS domain, and then join them to the Azure AD tenant.</span></span>

  <span data-ttu-id="00cdd-232">針對每個 Windows 10 企業版裝置，註冊它們來進行行動裝置管理。</span><span class="sxs-lookup"><span data-stu-id="00cdd-232">For each Windows 10 Enterprise device, enroll them for mobile device management.</span></span> <span data-ttu-id="00cdd-233">如需指示，請參閱[透過 Intune 使用群組原則來註冊 Windows 10 裝置](https://go.microsoft.com/fwlink/p/?linkid=872871)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-233">See [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for the instructions.</span></span>

<span data-ttu-id="00cdd-234">一旦安裝並加入，每個 Windows 10 企業版裝置都會自動安裝來自 Windows Update for Business 雲端服務的更新。</span><span class="sxs-lookup"><span data-stu-id="00cdd-234">Once installed and joined, each Windows 10 Enterprise device automatically installs updates from the Windows Update for Business cloud service.</span></span> <span data-ttu-id="00cdd-235">在非企業組織中通常不需要設定基礎結構，就能散發和安裝更新。</span><span class="sxs-lookup"><span data-stu-id="00cdd-235">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute and install updates.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="00cdd-236">您目前的設定</span><span class="sxs-lookup"><span data-stu-id="00cdd-236">Your configuration so far</span></span>

<span data-ttu-id="00cdd-237">以下是 Windows 10 企業版階段的視覺摘要 (將新項目醒目提示)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-237">Here is a visual summary of the Windows 10 Enterprise phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/win10-config.png)
 
<span data-ttu-id="00cdd-238">新的和醒目提示的 Windows 10 企業版項目包括：</span><span class="sxs-lookup"><span data-stu-id="00cdd-238">The new and highlighted Windows 10 Enterprise elements include:</span></span>

|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/win10-device.png) | <span data-ttu-id="00cdd-239">在 Windows 裝置 (以內部部署膝上型電腦為例) 上安裝的 Windows 10 企業版。</span><span class="sxs-lookup"><span data-stu-id="00cdd-239">Windows 10 Enterprise installed on Windows devices, with the on-premises laptop as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/win10-cloud.png) | <span data-ttu-id="00cdd-240">大量授權服務中心 (提供 Windows 10 企業版新安裝的映像)，和 Windows Update for Business 服務 (提供最新的更新)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-240">The Volume Licensing Service Center, which provides images for new installations of Windows 10 Enterprise, and the Windows Update for Business service, which provides the latest updates.</span></span> |
|||

## <a name="phase-4-office-365-proplus"></a><span data-ttu-id="00cdd-241">第4 階段：Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="00cdd-241">Phase 4: Office 365 ProPlus</span></span>

<span data-ttu-id="00cdd-242">Microsoft 365 企業版包含 Microsoft Office 的訂閱版本 Office 365 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="00cdd-242">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Microsoft Office.</span></span> <span data-ttu-id="00cdd-243">Office 365 專業增強版與 Office 2016 或 Office 2019 一樣，直接安裝在用戶端裝置上。</span><span class="sxs-lookup"><span data-stu-id="00cdd-243">Like Office 2016 or Office 2019, Office 365 ProPlus is installed directly on your client devices.</span></span> <span data-ttu-id="00cdd-244">不過 Office 365 專業增強版會定期收到新功能。</span><span class="sxs-lookup"><span data-stu-id="00cdd-244">However, Office 365 ProPlus receives new features on a regular basis.</span></span> <span data-ttu-id="00cdd-245">如需詳細資訊，請參閱[關於企業中的 Office 365 專業增強版](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-245">See [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) for more information.</span></span>

<span data-ttu-id="00cdd-246">如果是非企業組織，請在裝置上手動安裝 Office 365 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="00cdd-246">For your non-enterprise organization, manually install Office 365 ProPlus on devices.</span></span> <span data-ttu-id="00cdd-247">準備新裝置時，或者使用者在上線時都可以進行。</span><span class="sxs-lookup"><span data-stu-id="00cdd-247">This can be done as part of preparing a new device for use, or it can be done by the user as part of their onboarding process.</span></span>

<span data-ttu-id="00cdd-248">無論是哪一種情況，系統管理員或使用者都要在 https://portal.office.com 登入 Office 365 入口網站。</span><span class="sxs-lookup"><span data-stu-id="00cdd-248">In either case, the administrator or the user signs in to the Office 365 portal at https://portal.office.com.</span></span> <span data-ttu-id="00cdd-249">在 [Microsoft Office 首頁]\*\*\*\* 索引標籤上，按一下 [安裝 Office]\*\*\*\*，然後逐步完成安裝程序。</span><span class="sxs-lookup"><span data-stu-id="00cdd-249">On the **Microsoft Office Home** tab, click **Install Office** and step through the installation process.</span></span>

<span data-ttu-id="00cdd-250">安裝 Office 365 專業增強版的每部電腦，每個月都會下載功能更新。</span><span class="sxs-lookup"><span data-stu-id="00cdd-250">Feature updates to Office 365 ProPlus are downloaded monthly by each computer on which it is installed.</span></span> <span data-ttu-id="00cdd-251">在非企業組織中通常不需要設定基礎結構，就能散發 Office 365 專業增強版更新。</span><span class="sxs-lookup"><span data-stu-id="00cdd-251">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute Office 365 ProPlus updates.</span></span> 

### <a name="your-configuration-so-far"></a><span data-ttu-id="00cdd-252">您目前的設定</span><span class="sxs-lookup"><span data-stu-id="00cdd-252">Your configuration so far</span></span>

<span data-ttu-id="00cdd-253">以下是 Office 365 專業增強版階段的視覺摘要 (將新項目醒目提示)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-253">Here is a visual summary of the Office 365 ProPlus phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-config.png)
 
<span data-ttu-id="00cdd-254">新的和醒目提示的 Office 365 專業增強版項目包括：</span><span class="sxs-lookup"><span data-stu-id="00cdd-254">The new and highlighted Office 365 ProPlus elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-device.png) | <span data-ttu-id="00cdd-255">在裝置 (以內部部署膝上型電腦為例) 上安裝的 Office 365 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="00cdd-255">Office 365 ProPlus installed on devices, with the on-premises laptop as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-cdn.png) | <span data-ttu-id="00cdd-256">Office 365 專業增強版的 Office 內容傳遞網路 (CDN)，讓裝置存取 Office 365 專業增強版更新。</span><span class="sxs-lookup"><span data-stu-id="00cdd-256">The Office Content Delivery Network (CDN) for Office 365 ProPlus, which devices access for Office 365 ProPlus updates.</span></span> |
|||

## <a name="phase-5-mobile-device-management"></a><span data-ttu-id="00cdd-257">第 5 階段：行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="00cdd-257">Phase 5: Mobile device management</span></span>

<span data-ttu-id="00cdd-258">Microsoft 365 企業版包括 Microsoft Intune，可管理行動裝置。</span><span class="sxs-lookup"><span data-stu-id="00cdd-258">Microsoft 365 Enterprise includes Microsoft Intune for mobile device management.</span></span> <span data-ttu-id="00cdd-259">使用 Intune 可以管理 iOS、Android、macOS 和 Windows 等裝置，保護組織資源 (包括資料) 的存取。</span><span class="sxs-lookup"><span data-stu-id="00cdd-259">With Intune, you can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="00cdd-260">Intune 與 Azure AD 的使用者、群組和電腦帳戶整合。</span><span class="sxs-lookup"><span data-stu-id="00cdd-260">Intune integrates with the users, groups, and computer accounts of Azure AD.</span></span>

<span data-ttu-id="00cdd-261">Intune 提供兩種類型的行動裝置管理：</span><span class="sxs-lookup"><span data-stu-id="00cdd-261">Intune provides two types of mobile device management:</span></span>

- <span data-ttu-id="00cdd-262">行動裝置管理 (MDM) - 如果裝置已在 Intune 中註冊。</span><span class="sxs-lookup"><span data-stu-id="00cdd-262">Mobile device management (MDM) is when devices get enrolled in Intune.</span></span> <span data-ttu-id="00cdd-263">註冊之後，這些裝置就是受管理的裝置，可以接收組織所使用的原則、規則和設定。</span><span class="sxs-lookup"><span data-stu-id="00cdd-263">Once enrolled, they are managed devices and can receive the policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="00cdd-264">這類裝置通常是您的組織所擁有，然後分發給您的員工。</span><span class="sxs-lookup"><span data-stu-id="00cdd-264">These types of devices are typically owned by your organization and issued to your employees.</span></span>

- <span data-ttu-id="00cdd-265">擁有自己個人裝置的使用者可能不希望註冊裝置，或以您的原則和設定由 Intune 管理。</span><span class="sxs-lookup"><span data-stu-id="00cdd-265">Users with their own personal devices may not want to enroll their devices or be managed by Intune with your policies and settings.</span></span> <span data-ttu-id="00cdd-266">不過，您仍然必須保護組織的資源和資料。</span><span class="sxs-lookup"><span data-stu-id="00cdd-266">However, you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="00cdd-267">在本案例中，您可以使用行動應用程式管理 (MAM) 保護應用程式。</span><span class="sxs-lookup"><span data-stu-id="00cdd-267">For this scenario, you can protect your apps using mobile application management (MAM).</span></span> <span data-ttu-id="00cdd-268">這類裝置就是所謂的「攜帶您的裝置」(BYOD)，而且通常是您的員工所擁有。</span><span class="sxs-lookup"><span data-stu-id="00cdd-268">These types of devices are referred to as bring your own devices (BYOD) and are typically owned by your employees.</span></span> 

<span data-ttu-id="00cdd-269">Intune 原則可以強制執行裝置合規性和應用程式保護。</span><span class="sxs-lookup"><span data-stu-id="00cdd-269">Intune policies can enforce device compliance and app protection.</span></span> <span data-ttu-id="00cdd-270">以下是要建立的 Intune 原則清單。</span><span class="sxs-lookup"><span data-stu-id="00cdd-270">Here is the list of Intune policies to create.</span></span>

| <span data-ttu-id="00cdd-271">Intune 原則</span><span class="sxs-lookup"><span data-stu-id="00cdd-271">Intune policies</span></span> | <span data-ttu-id="00cdd-272">要套用的群組</span><span class="sxs-lookup"><span data-stu-id="00cdd-272">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="00cdd-273">Windows 的裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="00cdd-273">Device compliance policy for Windows</span></span> | <span data-ttu-id="00cdd-274">BASELINE、SENSITIVE、HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="00cdd-274">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="00cdd-275">iOS 的裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="00cdd-275">Device compliance policy for iOS</span></span> | <span data-ttu-id="00cdd-276">SENSITIVE、HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="00cdd-276">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="00cdd-277">macOS 的裝置合規性</span><span class="sxs-lookup"><span data-stu-id="00cdd-277">Device compliance for macOS</span></span> | <span data-ttu-id="00cdd-278">SENSITIVE、HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="00cdd-278">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="00cdd-279">Android 和 Android Enterprise 的裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="00cdd-279">Device compliance policy for Android and Android Enterprise</span></span> | <span data-ttu-id="00cdd-280">SENSITIVE、HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="00cdd-280">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="00cdd-281">iOS 的應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="00cdd-281">App protection policy for iOS</span></span> | <span data-ttu-id="00cdd-282">BASELINE、SENSITIVE、HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="00cdd-282">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="00cdd-283">macOS 的應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="00cdd-283">App protection policy for macOS</span></span> | <span data-ttu-id="00cdd-284">BASELINE、SENSITIVE、HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="00cdd-284">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="00cdd-285">Android 和 Android Enterprise 的應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="00cdd-285">App protection policy for Android and Android Enterprise</span></span> | <span data-ttu-id="00cdd-286">BASELINE、SENSITIVE、HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="00cdd-286">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
|||
    
<span data-ttu-id="00cdd-287">如需指示，請參閱[一般身分識別與裝置存取原則](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-287">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="00cdd-288">您目前的設定</span><span class="sxs-lookup"><span data-stu-id="00cdd-288">Your configuration so far</span></span>

<span data-ttu-id="00cdd-289">以下是行動裝置管理階段的視覺摘要 (將新項目醒目提示)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-289">Here is a visual summary of the Mobile Device Management phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-config.png)
 
<span data-ttu-id="00cdd-290">新的和醒目提示的行動裝置管理項目包括：</span><span class="sxs-lookup"><span data-stu-id="00cdd-290">The new and highlighted mobile device management elements include:</span></span>

|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-device.png) | <span data-ttu-id="00cdd-291">已在 Intune 中註冊的裝置，以執行 Windows 10 企業版的內部部署膝上型電腦為例。</span><span class="sxs-lookup"><span data-stu-id="00cdd-291">Devices that are enrolled in Intune, showing the on-premises laptop running Windows 10 Enterprise as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-policies.png) | <span data-ttu-id="00cdd-292">用於裝置合規性和應用程式保護的 Intune 原則。</span><span class="sxs-lookup"><span data-stu-id="00cdd-292">Intune policies for device compliance and app protection.</span></span> |
|||

## <a name="phase-6-information-protection"></a><span data-ttu-id="00cdd-293">第 6 階段：資訊保護</span><span class="sxs-lookup"><span data-stu-id="00cdd-293">Phase 6: Information protection</span></span>

<span data-ttu-id="00cdd-294">Microsoft 365 企業版有許多資訊保護功能，可讓您套用不同的控管、安全性和保護層級，以不同的方式處理資料的類別。</span><span class="sxs-lookup"><span data-stu-id="00cdd-294">Microsoft 365 Enterprise has a host of information protection features that allow you treat classifications of data differently by applying different levels of governance, security, and protection.</span></span> 

<span data-ttu-id="00cdd-295">例如，大多數員工之間的一般通信與他們處理的文件需要某種基準層級的保護。</span><span class="sxs-lookup"><span data-stu-id="00cdd-295">For example, normal correspondence between most employees and the documents that they work on need a certain baseline level of protection.</span></span> <span data-ttu-id="00cdd-296">財務記錄、客戶資料和智慧財產則需要較高層級的保護。</span><span class="sxs-lookup"><span data-stu-id="00cdd-296">Financial records, customer data, and your intellectual property need a higher level of protection.</span></span>

<span data-ttu-id="00cdd-297">資訊保護策略的第一步是判斷保護的層級。</span><span class="sxs-lookup"><span data-stu-id="00cdd-297">The first step to an information protection strategy is to determine the levels of protection.</span></span> <span data-ttu-id="00cdd-298">許多組織會使用條件式存取原則已經在使用的這些層級：</span><span class="sxs-lookup"><span data-stu-id="00cdd-298">Many organizations use these levels, which are already being used for conditional access policies:</span></span>

- <span data-ttu-id="00cdd-299">基準</span><span class="sxs-lookup"><span data-stu-id="00cdd-299">Baseline</span></span>

  <span data-ttu-id="00cdd-300">範例包括一般業務通訊 (電子郵件)，以及管理、銷售和客戶服務員工的檔案。</span><span class="sxs-lookup"><span data-stu-id="00cdd-300">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span>

- <span data-ttu-id="00cdd-301">敏感性</span><span class="sxs-lookup"><span data-stu-id="00cdd-301">Sensitive</span></span>

  <span data-ttu-id="00cdd-302">範例包括財務和法務資訊，以及新產品或新服務的研發資料。</span><span class="sxs-lookup"><span data-stu-id="00cdd-302">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span>

- <span data-ttu-id="00cdd-303">高管制</span><span class="sxs-lookup"><span data-stu-id="00cdd-303">Highly regulated</span></span>

  <span data-ttu-id="00cdd-304">範例包括客戶和合作夥伴的個人識別資訊，以及組織的智慧財產。</span><span class="sxs-lookup"><span data-stu-id="00cdd-304">Examples include customer and partner personally identifiable information and your organization’s intellectual property.</span></span>

<span data-ttu-id="00cdd-305">根據這些資料安全性層級，下一步就要找出並實作：</span><span class="sxs-lookup"><span data-stu-id="00cdd-305">Based on these levels of data security, the next step is to identify and implement:</span></span>

- <span data-ttu-id="00cdd-306">自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="00cdd-306">Custom sensitive information types</span></span>

  <span data-ttu-id="00cdd-307">Microsoft 365 提供各式各樣的敏感性資訊類型，例如健康情況服務與信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="00cdd-307">Microsoft 365 supplies a wide selection of sensitive information types, such as health service and credit card numbers.</span></span> <span data-ttu-id="00cdd-308">如果您在 Microsoft 365 提供的清單中找不到需要的類型，可以自行建立。</span><span class="sxs-lookup"><span data-stu-id="00cdd-308">If you do not find one that you need in the Microsoft 365-supplied list, you can create your own.</span></span>

- <span data-ttu-id="00cdd-309">保留標籤</span><span class="sxs-lookup"><span data-stu-id="00cdd-309">Retention labels</span></span>

  <span data-ttu-id="00cdd-310">為了符合組織的原則和地區的法規，您可能必須指定應該將特定類型的文件或具有特定內容的文件保留多久。</span><span class="sxs-lookup"><span data-stu-id="00cdd-310">To comply with organization policies and regional regulations, you might have to specify how long specific types of documents or documents with specific contents should be retained.</span></span> <span data-ttu-id="00cdd-311">您可以使用保留標籤，針對電子郵件和文件實作這個設定。</span><span class="sxs-lookup"><span data-stu-id="00cdd-311">You can implement this for email and document using retention labels.</span></span>

- <span data-ttu-id="00cdd-312">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="00cdd-312">Sensitivity labels</span></span>

  <span data-ttu-id="00cdd-313">您可以使用命名的敏感度標籤來標示電子郵件或文件，以便套用其他安全性層級。</span><span class="sxs-lookup"><span data-stu-id="00cdd-313">You can label email or documents with a named sensitivity label so that the additional levels of security can be applied.</span></span> <span data-ttu-id="00cdd-314">範例包括浮水印、加密和權限，指定誰可以存取電子郵件或文件，以及這些人可以執行的動作。</span><span class="sxs-lookup"><span data-stu-id="00cdd-314">Examples are watermarks, encryption, and permissions, which specify who is allowed to access the email or document and what they are allowed to do.</span></span>

<span data-ttu-id="00cdd-315">如需詳細資訊，請參閱 [Microsoft 365 分類類型](infoprotect-configure-classification.md#microsoft-365-classification-types)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-315">See [Microsoft 365 classification types](infoprotect-configure-classification.md#microsoft-365-classification-types) for more information.</span></span>

<span data-ttu-id="00cdd-316">如果您使用權限的敏感度標籤，可能需要建立額外的 Azure AD 安全性群組來定義誰可以對電子郵件和文件執行什麼動作。</span><span class="sxs-lookup"><span data-stu-id="00cdd-316">If you use sensitivity labels with permissions, you might have to create additional Azure AD security groups to define who is allowed to do what with email and documents.</span></span> 

<span data-ttu-id="00cdd-317">例如，您需要建立 RESEARCH 敏感度標籤來保護研究團隊的電子郵件和文件。</span><span class="sxs-lookup"><span data-stu-id="00cdd-317">For example, you need to create a RESEARCH sensitivity label to protect the email and documents of your research team.</span></span> <span data-ttu-id="00cdd-318">您決定某些研究人員必須能夠變更以 RESEARCH 敏感度標籤標示的文件，其他非研究人員的員工則只能檢視以 RESEARCH 敏感度標籤標示的文件。</span><span class="sxs-lookup"><span data-stu-id="00cdd-318">You determine that some researchers must have the ability to change documents marked with the RESEARCH sensitivity label and other non-research employees need have the ability to only view documents marked with the RESEARCH sensitivity label.</span></span> <span data-ttu-id="00cdd-319">這表示您必須建立和管理兩個額外的群組：</span><span class="sxs-lookup"><span data-stu-id="00cdd-319">This means you need to create and manage two additional groups:</span></span>

- <span data-ttu-id="00cdd-320">RESEARCH-ALL</span><span class="sxs-lookup"><span data-stu-id="00cdd-320">RESEARCH-ALL</span></span>
- <span data-ttu-id="00cdd-321">RESEARCH-VIEW</span><span class="sxs-lookup"><span data-stu-id="00cdd-321">RESEARCH-VIEW</span></span>

<span data-ttu-id="00cdd-322">這些群組和權限會變成 RESEARCH 敏感度標籤設定的一部分。</span><span class="sxs-lookup"><span data-stu-id="00cdd-322">These groups and their permissions become part of the RESEARCH sensitivity label's configuration.</span></span>

<span data-ttu-id="00cdd-323">對於以群組型權限設定的敏感度標籤，您必須管理這些群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="00cdd-323">For sensitivity labels configured with group-based permissions, you must manage the membership of these groups.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="00cdd-324">您目前的設定</span><span class="sxs-lookup"><span data-stu-id="00cdd-324">Your configuration so far</span></span>

<span data-ttu-id="00cdd-325">以下是資訊保護階段的視覺摘要 (將新項目醒目提示)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-325">Here is a visual summary of the Information Protection phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-config.png)
 
<span data-ttu-id="00cdd-326">新的和醒目提示的資訊保護項目包括：</span><span class="sxs-lookup"><span data-stu-id="00cdd-326">The new and highlighted information protection elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-labels.png) | <span data-ttu-id="00cdd-327">使用者可以套用至文件的三個安全性層級的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="00cdd-327">Sensitivity labels for the three levels of security that users can apply to documents.</span></span> |
|||

<span data-ttu-id="00cdd-328">不會顯示保留標籤和自訂資訊類型。</span><span class="sxs-lookup"><span data-stu-id="00cdd-328">Retention labels and custom information types are not shown.</span></span>

## <a name="onboarding"></a><span data-ttu-id="00cdd-329">登入</span><span class="sxs-lookup"><span data-stu-id="00cdd-329">User Onboarding</span></span>

<span data-ttu-id="00cdd-330">您可以透過這個基礎結構，使用這些程序將 Microsoft 365 企業版的員工登入。</span><span class="sxs-lookup"><span data-stu-id="00cdd-330">With this infrastructure, you can onboard an employee for Microsoft 365 Enterprise with these processes.</span></span>

### <a name="a-new-windows-10-enterprise-device"></a><span data-ttu-id="00cdd-331">新的 Windows 10 企業版裝置</span><span class="sxs-lookup"><span data-stu-id="00cdd-331">A new Windows 10 Enterprise device</span></span>

<span data-ttu-id="00cdd-332">提供員工新的 Windows 10 企業版裝置之前：</span><span class="sxs-lookup"><span data-stu-id="00cdd-332">Before giving an employee a new Windows 10 Enterprise device:</span></span>

- <span data-ttu-id="00cdd-333">對於僅雲端身分識別</span><span class="sxs-lookup"><span data-stu-id="00cdd-333">For cloud-only identity</span></span>

  <span data-ttu-id="00cdd-334">將裝置加入 Microsoft 365 企業版訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="00cdd-334">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>

- <span data-ttu-id="00cdd-335">對於混合式身分識別</span><span class="sxs-lookup"><span data-stu-id="00cdd-335">For hybrid identity</span></span>

  <span data-ttu-id="00cdd-336">將裝置加入您的 AD DS、將裝置加入您的 Azure AD 租用戶，然後在 Intune 中註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="00cdd-336">Join the device to your AD DS, join the device to your Azure AD tenant, and then enroll the device in Intune.</span></span>

### <a name="existing-employee-with-an-ad-ds-user-account"></a><span data-ttu-id="00cdd-337">有 AD DS 使用者帳戶的現有員工</span><span class="sxs-lookup"><span data-stu-id="00cdd-337">Existing employee with an AD DS user account</span></span>

<span data-ttu-id="00cdd-338">如果使用混合式身分識別，首次登入組織時，請將 AD DS 使用者帳戶新增至這些 Azure AD 群組：</span><span class="sxs-lookup"><span data-stu-id="00cdd-338">As part of the initial onboarding for your organization when using hybrid identity, add the AD DS user account to these Azure AD groups:</span></span>

- <span data-ttu-id="00cdd-339">LICENSED</span><span class="sxs-lookup"><span data-stu-id="00cdd-339">Licensed</span></span>
- <span data-ttu-id="00cdd-340">屬於 BASELINE、SENSITIVE 和 HIGHLY-REGULATED Azure AD 群組之成員的適當 AD DS 或 Azure AD 安全性群組</span><span class="sxs-lookup"><span data-stu-id="00cdd-340">The appropriate AD DS or Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="00cdd-341">敏感度標籤群組 (如有需要)</span><span class="sxs-lookup"><span data-stu-id="00cdd-341">Sensitivity label groups (as needed)</span></span>

<span data-ttu-id="00cdd-342">現有的員工應該已經新增至適當的群組、部門及地區 AD DS 群組。</span><span class="sxs-lookup"><span data-stu-id="00cdd-342">The existing employee should already be added to the appropriate workgroup, departmental, and regional AD DS groups.</span></span>

### <a name="new-employee-with-cloud-only-user-account"></a><span data-ttu-id="00cdd-343">有僅雲端使用者帳戶的新進員工</span><span class="sxs-lookup"><span data-stu-id="00cdd-343">New employee with cloud-only user account</span></span>

<span data-ttu-id="00cdd-344">如果使用僅雲端身分識別，首次登入組織時，請將新的使用者帳戶新增至這些群組：</span><span class="sxs-lookup"><span data-stu-id="00cdd-344">As part of the initial onboarding for your organization when using cloud-only identity, add the new user account to these groups:</span></span>

- <span data-ttu-id="00cdd-345">LICENSED</span><span class="sxs-lookup"><span data-stu-id="00cdd-345">Licensed</span></span>
- <span data-ttu-id="00cdd-346">屬於 BASELINE、SENSITIVE 和 HIGHLY-REGULATED Azure AD 群組之成員的適當 Azure AD 安全性群組</span><span class="sxs-lookup"><span data-stu-id="00cdd-346">The appropriate Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="00cdd-347">工作群組、部門和地區群組</span><span class="sxs-lookup"><span data-stu-id="00cdd-347">Workgroup, departmental, and regional groups</span></span>
- <span data-ttu-id="00cdd-348">敏感度標籤群組 (如有需要)</span><span class="sxs-lookup"><span data-stu-id="00cdd-348">Sensitivity label groups (as needed)</span></span>

### <a name="initial-sign-in-to-microsoft-365"></a><span data-ttu-id="00cdd-349">首次登入 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="00cdd-349">Initial sign-in to Microsoft 365</span></span>

<span data-ttu-id="00cdd-350">對於有 AD DS 使用者帳戶、第一次登入 Microsoft 365 的新進員工或現有員工，請指導他們：</span><span class="sxs-lookup"><span data-stu-id="00cdd-350">For the first time new employees or existing employees with an AD DS user account sign in to Microsoft 365, instruct them to:</span></span>

1. <span data-ttu-id="00cdd-351">使用他們的使用者帳戶認證登入裝置。</span><span class="sxs-lookup"><span data-stu-id="00cdd-351">Sign into their devices with their user account credentials.</span></span>
2. <span data-ttu-id="00cdd-352">使用瀏覽器，登入 Office 365 入口網站 https://portal.office.com。</span><span class="sxs-lookup"><span data-stu-id="00cdd-352">Using a browser on your local computer, sign in to the https://portal.office.com using your global administrator account.</span></span>
3. <span data-ttu-id="00cdd-353">從 [Office 365 首頁]\*\*\*\* 索引標籤，按一下 [安裝 Office]\*\*\*\*，在裝置上安裝 Office 365 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="00cdd-353">From the **Office 365 Home** tab, click **Install Office** to install Office 365 ProPlus on their device.</span></span>

## <a name="end-results"></a><span data-ttu-id="00cdd-354">最終結果</span><span class="sxs-lookup"><span data-stu-id="00cdd-354">End results</span></span>

<span data-ttu-id="00cdd-355">以下是為您的非企業組織設定 Microsoft 365 企業版底層基礎結構的結果。</span><span class="sxs-lookup"><span data-stu-id="00cdd-355">Here are the results of configuring the Microsoft 365 Enterprise foundation infrastructure for your non-enterprise organization.</span></span>

### <a name="infrastructure-results"></a><span data-ttu-id="00cdd-356">基礎結構結果</span><span class="sxs-lookup"><span data-stu-id="00cdd-356">Infrastructure results</span></span>

<span data-ttu-id="00cdd-357">組建和設定 Microsoft 365 企業版基礎結構之後，您應該會有：</span><span class="sxs-lookup"><span data-stu-id="00cdd-357">After the build-out and configuration of your Microsoft 365 Enterprise infrastructure, you should have:</span></span>

- <span data-ttu-id="00cdd-358">每間辦公室都有當地的網際網路連線，並且由使用當地 DNS 伺服器的 ISP 提供足夠的頻寬。</span><span class="sxs-lookup"><span data-stu-id="00cdd-358">A local Internet connection for each of your offices with sufficient bandwidth supplied by an ISP that uses a regionally local DNS server.</span></span>
- <span data-ttu-id="00cdd-359">對於混合式身分識別，在伺服器上執行的 Azure AD Connect 會與您的 Azure AD 租用戶同步處理您的內部部署 AD DS 網域。</span><span class="sxs-lookup"><span data-stu-id="00cdd-359">For hybrid identity, Azure AD Connect running on a server that synchronizes your on-premises AD DS domain with your Azure AD tenant.</span></span>
- <span data-ttu-id="00cdd-360">下列群組：</span><span class="sxs-lookup"><span data-stu-id="00cdd-360">These universal groups include:</span></span>
  - <span data-ttu-id="00cdd-361">LICENSED</span><span class="sxs-lookup"><span data-stu-id="00cdd-361">Licensed</span></span>
  - <span data-ttu-id="00cdd-362">COND-ACCESS-EXCLUDE</span><span class="sxs-lookup"><span data-stu-id="00cdd-362">COND-ACCESS-EXCLUDE</span></span>
  - <span data-ttu-id="00cdd-363">也同樣屬於 BASELINE、SENSITIVE 和 HIGHLY-REGULATED Azure AD 群組之成員的適當 AD DS 或 Azure AD 安全性群組</span><span class="sxs-lookup"><span data-stu-id="00cdd-363">The appropriate AD DS or Azure AD security groups that are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span> 
  - <span data-ttu-id="00cdd-364">工作群組、部門和地區群組</span><span class="sxs-lookup"><span data-stu-id="00cdd-364">Workgroup, departmental, and regional groups</span></span>
  - <span data-ttu-id="00cdd-365">敏感度標籤群組 (如有需要)</span><span class="sxs-lookup"><span data-stu-id="00cdd-365">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="00cdd-366">使用 BASELINE、SENSITIVE、HIGHLY-REGULATED 和 COND-ACCESS-EXCLUDE Azure AD 群組的 Azure AD 登入條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="00cdd-366">Azure AD sign-in conditional access policies that use the BASELINE, SENSITIVE, and HIGHLY-REGULATED, and COND-ACCESS-EXCLUDE Azure AD groups.</span></span>
- <span data-ttu-id="00cdd-367">Intune 應用程式和裝置合規性原則。</span><span class="sxs-lookup"><span data-stu-id="00cdd-367">Intune application and device compliance policies.</span></span>
- <span data-ttu-id="00cdd-368">自訂敏感性資訊類型 (如有需要)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-368">Custom sensitive information types (as needed).</span></span>
- <span data-ttu-id="00cdd-369">保留標籤 (如有需要)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-369">Retention labels (as needed).</span></span>
- <span data-ttu-id="00cdd-370">敏感度標籤 (如有需要)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-370">Sensitivity labels (as needed).</span></span>

<span data-ttu-id="00cdd-371">以下是組織使用混合式身分識別時的基礎結構視覺摘要，其中包含您的 AD DS 網域、Azure AD Connect 伺服器，以及已同步處理的 AD DS 使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="00cdd-371">Here is a visual summary of the infrastructure if your organization uses hybrid identity, which includes your AD DS domain, an Azure AD Connect server, and synchronized AD DS users and groups.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/final-hybrid-config.png)
 
<span data-ttu-id="00cdd-372">以下是組織使用僅雲端身分識別時的基礎結構視覺摘要。</span><span class="sxs-lookup"><span data-stu-id="00cdd-372">Here is a visual summary of the infrastructure if your organization uses cloud-only identity.</span></span>
 
![](./media/deploy-foundation-infrastructure-non-enterprises/final-cloud-only-config.png)

### <a name="employee-results"></a><span data-ttu-id="00cdd-373">員工結果</span><span class="sxs-lookup"><span data-stu-id="00cdd-373">Employee results</span></span>

<span data-ttu-id="00cdd-374">每位員工登入之後應該會有：</span><span class="sxs-lookup"><span data-stu-id="00cdd-374">After their onboarding, each employee should have:</span></span>

- <span data-ttu-id="00cdd-375">從員工裝置到所在地區的 Microsoft 365 雲端服務，具有效能良好的內部部署網路路徑。</span><span class="sxs-lookup"><span data-stu-id="00cdd-375">A performant, on-premises network path from their device to the Microsoft 365 cloud services in their region.</span></span>
- <span data-ttu-id="00cdd-376">具有下列群組成員資格的使用帳戶：</span><span class="sxs-lookup"><span data-stu-id="00cdd-376">A user account with these group memberships:</span></span>
   - <span data-ttu-id="00cdd-377">LICENSED</span><span class="sxs-lookup"><span data-stu-id="00cdd-377">Licensed</span></span>
   - <span data-ttu-id="00cdd-378">適當的 AD DS 或 Azure AD 安全性群組，也同樣屬於條件式存取原則的 BASELINE、SENSITIVE 和 HIGHLY-REGULATED Azure AD 群組的成員</span><span class="sxs-lookup"><span data-stu-id="00cdd-378">The appropriate AD DS or Azure AD security groups, which are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups for conditional access policies</span></span> 
   - <span data-ttu-id="00cdd-379">適當的工作群組、部門和地區群組</span><span class="sxs-lookup"><span data-stu-id="00cdd-379">The appropriate workgroup, departmental, and regional groups</span></span>
   - <span data-ttu-id="00cdd-380">敏感度標籤群組 (如有需要)</span><span class="sxs-lookup"><span data-stu-id="00cdd-380">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="00cdd-381">具備下列條件的 Windows 10 企業版裝置：</span><span class="sxs-lookup"><span data-stu-id="00cdd-381">A Windows 10 Enterprise device that:</span></span>
   - <span data-ttu-id="00cdd-382">已加入 Azure AD 租用戶 (僅雲端) 或同時加入 Azure AD 租用戶與 AD DS 網域 (混合式)。</span><span class="sxs-lookup"><span data-stu-id="00cdd-382">Is joined to the Azure AD tenant (cloud-only) or to both the Azure AD tenant and your AD DS domain (hybrid).</span></span>
   - <span data-ttu-id="00cdd-383">使用最新的 Windows 10 企業版產品改良功能和安全性增強功能自動更新本身。</span><span class="sxs-lookup"><span data-stu-id="00cdd-383">Automatically updates itself with the latest Windows 10 Enterprise product improvements and security enhancements.</span></span>
   - <span data-ttu-id="00cdd-384">已安裝 Office 365 專業增強版，它會使用最新的 Office 產品改良功能和安全性增強功能自動更新本身。</span><span class="sxs-lookup"><span data-stu-id="00cdd-384">Has Office 365 ProPlus installed, which automatically updates itself with the latest Office product improvements and security enhancements.</span></span>
   - <span data-ttu-id="00cdd-385">已在 Intune 中註冊，而且遵守 Intune 裝置合規性原則和應用程式保護原則。</span><span class="sxs-lookup"><span data-stu-id="00cdd-385">Is enrolled in Intune and subject to Intune device compliance policies and app protection policies.</span></span>

## <a name="next-step"></a><span data-ttu-id="00cdd-386">後續步驟</span><span class="sxs-lookup"><span data-stu-id="00cdd-386">Next step</span></span>

<span data-ttu-id="00cdd-387">部署您的[工作負載和案例](deploy-workloads.md)，善加利用底層基礎結構的功能與設定。</span><span class="sxs-lookup"><span data-stu-id="00cdd-387">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
