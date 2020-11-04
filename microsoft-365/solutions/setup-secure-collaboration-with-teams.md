---
title: 使用 Microsoft 365 設定安全的共同作業
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: 瞭解如何設定小組中的安全內容共同作業，以根據其敏感度來保護您的資料。
ms.openlocfilehash: 310605d0db84e33be1d5fdc925fadcfcdf9dddaf
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906796"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a><span data-ttu-id="6cdd5-103">使用 Microsoft 365 設定安全的共同作業</span><span class="sxs-lookup"><span data-stu-id="6cdd5-103">Set up secure collaboration with Microsoft 365</span></span>

<span data-ttu-id="6cdd5-104">能夠輕易與適當的人員分享資訊，同時避免 oversharing 是組織成功的關鍵。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-104">Being able to easily share information with the right people while preventing oversharing is key to an organization's success.</span></span> <span data-ttu-id="6cdd5-105">這包括可以安全地與只有應有存取權的使用者共用機密資料。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-105">This includes being able to share sensitive data safely with only those who should have access to it.</span></span> <span data-ttu-id="6cdd5-106">視專案而定，這可能包括與組織外部人員共用機密資料。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-106">Depending on the project, this might include sharing sensitive data with people outside your organization.</span></span>

<span data-ttu-id="6cdd5-107">這個共同作業方案指南包含兩個元件，可協助您：</span><span class="sxs-lookup"><span data-stu-id="6cdd5-107">This collaboration solution guidance includes two components to help you:</span></span>
- <span data-ttu-id="6cdd5-108">以適當的保護層級，為每個專案部署 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="6cdd5-108">Deploy Microsoft Teams with the right level of protection for each project</span></span>
- <span data-ttu-id="6cdd5-109">針對每個專案設定具有適當安全性設定的外部共用</span><span class="sxs-lookup"><span data-stu-id="6cdd5-109">Configure external sharing with appropriate security settings for each project</span></span>

![以適當的安全性設定，以適當的保護和設定外部共用來部署團隊](..\media\solutions-architecture-center\secure-collaboration-overview.png)

<span data-ttu-id="6cdd5-111">如果您無法使用多功能和便於使用的內容共同作業工具，使用者通常會透過電子郵件檔進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-111">If versatile and easy-to-use content collaboration tools aren't available, users will often collaborate by emailing documents.</span></span> <span data-ttu-id="6cdd5-112">這是一種單調乏味且容易出錯的共同作業方法，可增加不適當共用資訊的風險。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-112">This is a tedious and error-prone method of collaboration, and can increase the risk of inappropriate sharing of information.</span></span> <span data-ttu-id="6cdd5-113">如果人員發現共用資訊過於困難，他們可能會回復為使用不受 IT 管理的消費產品。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-113">If people find sharing information too difficult, they could revert to using consumer products that are not governed by IT.</span></span> <span data-ttu-id="6cdd5-114">這可能會帶來更大的風險。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-114">This can pose an even greater risk.</span></span>

<span data-ttu-id="6cdd5-115">使用 Microsoft 365，您可以使用各種設定來部署小組，以協助：</span><span class="sxs-lookup"><span data-stu-id="6cdd5-115">With Microsoft 365, you can deploy Teams with a variety of configurations that help:</span></span>

- <span data-ttu-id="6cdd5-116">保護您的智慧財產權</span><span class="sxs-lookup"><span data-stu-id="6cdd5-116">Protect your intellectual property</span></span>
- <span data-ttu-id="6cdd5-117">啟用輕鬆合作</span><span class="sxs-lookup"><span data-stu-id="6cdd5-117">Enable easy collaboration</span></span>
- <span data-ttu-id="6cdd5-118">建立安全性和可用性之間的平衡，以提升使用者滿意度並降低陰影的風險</span><span class="sxs-lookup"><span data-stu-id="6cdd5-118">Create a balance between security and usability that increases user satisfaction and reduces the risk of shadow IT</span></span>

<span data-ttu-id="6cdd5-119">如果資訊未適當共用，大部分的組織都有各種資訊，但敏感度程度不同，而且業務影響程度也會不同。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-119">Most organizations have a variety of information, with varying degrees of sensitivity and varying degrees of business impact if the information is inappropriately shared.</span></span> <span data-ttu-id="6cdd5-120">根據特定資訊的敏感度，您可能想要允許與共享：</span><span class="sxs-lookup"><span data-stu-id="6cdd5-120">Depending on the sensitivity of a given piece of information, you may want to allow sharing with:</span></span>

- <span data-ttu-id="6cdd5-121">任何人 (未驗證) </span><span class="sxs-lookup"><span data-stu-id="6cdd5-121">Anyone (unauthenticated)</span></span>
- <span data-ttu-id="6cdd5-122">組織內的人員</span><span class="sxs-lookup"><span data-stu-id="6cdd5-122">People inside the organization</span></span>
- <span data-ttu-id="6cdd5-123">組織內的特定人員</span><span class="sxs-lookup"><span data-stu-id="6cdd5-123">Specific people inside the organization</span></span>
- <span data-ttu-id="6cdd5-124">組織內部和外部的特定人員</span><span class="sxs-lookup"><span data-stu-id="6cdd5-124">Specific people inside and outside the organization</span></span>

<span data-ttu-id="6cdd5-125">「行銷手冊」等資訊是要在組織外廣泛共用。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-125">Information such as marketing brochures are meant for sharing broadly outside the organization.</span></span> <span data-ttu-id="6cdd5-126">諸如諸如自助共用之外的資訊（例如，自助）可能不會影響任何業務，如果是外部共用。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-126">Information such as cafeteria menus aren't meant for external sharing, but would have no business impact if they were shared externally.</span></span> <span data-ttu-id="6cdd5-127">這些類型的資訊需要很少或沒有防護。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-127">These types of information need little or no protection.</span></span>

<span data-ttu-id="6cdd5-128">在開發時，這些相同的行銷手冊只會在組織內共用。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-128">Those same marketing brochures, while under development, might only be shared inside the organization.</span></span> <span data-ttu-id="6cdd5-129">在此情況下，小組中的預設共用設定可能已足夠。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-129">In this case, the default sharing settings in Teams may be sufficient.</span></span>

<span data-ttu-id="6cdd5-130">在開發中的新產品資訊可能被視為敏感，甚至是在組織內。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-130">Information about a new product that is under development might be considered sensitive, even within the organization.</span></span> <span data-ttu-id="6cdd5-131">在此情況下，可能會有較大程度的保護。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-131">A greater degree of protection might be appropriate in this case.</span></span> <span data-ttu-id="6cdd5-132">例如，您可以限制對此資訊的存取權給特定小組的成員。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-132">You could restrict access to this information to members of a specific team, for example.</span></span> <span data-ttu-id="6cdd5-133">視專案而定，您可能需要與組織外部的人員（例如廠商或夥伴組織）進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-133">Depending on the project, you may need to collaborate with people outside your organization, such as a vendor or partner organization.</span></span>

<span data-ttu-id="6cdd5-134">對貴組織成功與否重要的資訊，或具有嚴格的安全性或規範需求可能需要更高的保護等級。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-134">Information that is critical to your organization's success, or has stringent security or compliance requirements might require even greater levels of protection.</span></span>

![從低 (發行的摺頁冊) 到高 (敏感商務資料) ](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

<span data-ttu-id="6cdd5-136">針對上述所有案例，您可以使用 Microsoft 團隊中的團隊來儲存、共用及共同作業資訊。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-136">For all the scenarios noted above, you can use teams in Microsoft Teams to store, share, and collaborate on the information.</span></span> 

<span data-ttu-id="6cdd5-137">若要設定安全 collabration，您可以使用這些 Microsoft 365 功能。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-137">To configure secure collabration, you use these Microsoft 365 capabilities and features.</span></span>

| <span data-ttu-id="6cdd5-138">產品或元件</span><span class="sxs-lookup"><span data-stu-id="6cdd5-138">Product or component</span></span> | <span data-ttu-id="6cdd5-139">功能</span><span class="sxs-lookup"><span data-stu-id="6cdd5-139">Capability or feature</span></span> | <span data-ttu-id="6cdd5-140">授權</span><span class="sxs-lookup"><span data-stu-id="6cdd5-140">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="6cdd5-141">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="6cdd5-141">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="6cdd5-142">SPO、OneDrive 及小組的安全附件;安全檔;小組的安全連結</span><span class="sxs-lookup"><span data-stu-id="6cdd5-142">Safe Attachments for SPO, OneDrive and Teams; Safe Documents; Safe Links for Teams</span></span>    | <span data-ttu-id="6cdd5-143">Microsoft 365 E1，E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="6cdd5-143">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="6cdd5-144">SharePoint</span><span class="sxs-lookup"><span data-stu-id="6cdd5-144">SharePoint</span></span>    | <span data-ttu-id="6cdd5-145">網站與檔案共用原則、網站共用許可權、共用連結、存取要求、網站來賓共用設定</span><span class="sxs-lookup"><span data-stu-id="6cdd5-145">Site and file sharing policies, Site sharing permissions, Sharing links, Access requests, Site guest sharing settings</span></span> | <span data-ttu-id="6cdd5-146">Microsoft 365 E1，E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="6cdd5-146">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="6cdd5-147">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6cdd5-147">Microsoft Teams</span></span>   | <span data-ttu-id="6cdd5-148">來賓存取、私人團隊、專用通道</span><span class="sxs-lookup"><span data-stu-id="6cdd5-148">Guest access, private teams, private channels</span></span> | <span data-ttu-id="6cdd5-149">Microsoft 365 E1，E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="6cdd5-149">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="6cdd5-150">Microsoft 365 合規性</span><span class="sxs-lookup"><span data-stu-id="6cdd5-150">Microsoft 365 Compliance</span></span>  | <span data-ttu-id="6cdd5-151">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="6cdd5-151">Sensitivity labels</span></span>    | <span data-ttu-id="6cdd5-152">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="6cdd5-152">Microsoft 365 E3 and E5</span></span> |

### <a name="using-teams-for-all-kinds-of-data"></a><span data-ttu-id="6cdd5-153">針對所有種類的資料使用團隊</span><span class="sxs-lookup"><span data-stu-id="6cdd5-153">Using Teams for all kinds of data</span></span>

<span data-ttu-id="6cdd5-154">若要使用不同的 sensitivities 管理資訊存取，我們 [為小組開發了三個不同的保護層級](configure-teams-three-tiers-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-154">To manage access to information with different sensitivities, we've developed [three different tiers of protection for Teams](configure-teams-three-tiers-protection.md).</span></span> <span data-ttu-id="6cdd5-155">您可以自訂這些層級，以更好地解決需求或您的業務。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-155">You can customize any of these tiers to better address the needs or your business.</span></span> 

![Teams 邏輯架構海報的縮圖影像](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


<span data-ttu-id="6cdd5-157">這些層級- *基準* 、 *敏感* 和 *高敏感度* -逐步增加保護，協助避免 oversharing 和潛在的資訊洩漏，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-157">These tiers - *baseline* , *sensitive* , and *highly sensitive* - gradually increase the protections that help prevent oversharing and potential information leakage, as shown in the following table.</span></span>

||<span data-ttu-id="6cdd5-158">**基準層**</span><span class="sxs-lookup"><span data-stu-id="6cdd5-158">**Baseline tier**</span></span>|<span data-ttu-id="6cdd5-159">**機密層**</span><span class="sxs-lookup"><span data-stu-id="6cdd5-159">**Sensitive tier**</span></span>|<span data-ttu-id="6cdd5-160">**高度機密層**</span><span class="sxs-lookup"><span data-stu-id="6cdd5-160">**Highly sensitive tier**</span></span>|
|:--|:-----------|:------------|:-------------------|
|<span data-ttu-id="6cdd5-161">公用或私人團隊</span><span class="sxs-lookup"><span data-stu-id="6cdd5-161">Public or private team</span></span>|<span data-ttu-id="6cdd5-162">兩者之一</span><span class="sxs-lookup"><span data-stu-id="6cdd5-162">Either</span></span>|<span data-ttu-id="6cdd5-163">Private</span><span class="sxs-lookup"><span data-stu-id="6cdd5-163">Private</span></span>|<span data-ttu-id="6cdd5-164">Private</span><span class="sxs-lookup"><span data-stu-id="6cdd5-164">Private</span></span>|
|<span data-ttu-id="6cdd5-165">未經驗證的共用</span><span class="sxs-lookup"><span data-stu-id="6cdd5-165">Unauthenticated sharing</span></span>|<span data-ttu-id="6cdd5-166">已封鎖</span><span class="sxs-lookup"><span data-stu-id="6cdd5-166">Blocked</span></span>|<span data-ttu-id="6cdd5-167">已封鎖</span><span class="sxs-lookup"><span data-stu-id="6cdd5-167">Blocked</span></span>|<span data-ttu-id="6cdd5-168">已封鎖</span><span class="sxs-lookup"><span data-stu-id="6cdd5-168">Blocked</span></span>|
|<span data-ttu-id="6cdd5-169">檔案共用</span><span class="sxs-lookup"><span data-stu-id="6cdd5-169">File sharing</span></span>|<span data-ttu-id="6cdd5-170">已允許</span><span class="sxs-lookup"><span data-stu-id="6cdd5-170">Allowed</span></span>|<span data-ttu-id="6cdd5-171">允許</span><span class="sxs-lookup"><span data-stu-id="6cdd5-171">Allowed</span></span>|<span data-ttu-id="6cdd5-172">只有小組擁有者可以共用。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-172">Only team owners can share.</span></span>|
|<span data-ttu-id="6cdd5-173">小組成員資格</span><span class="sxs-lookup"><span data-stu-id="6cdd5-173">Team membership</span></span>|<span data-ttu-id="6cdd5-174">任何人都可以加入 public 團隊。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-174">Anyone can join public teams.</span></span><br><span data-ttu-id="6cdd5-175">加入私人團隊所需的小組擁有者核准。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-175">Team owner approval required to join private teams.</span></span>|<span data-ttu-id="6cdd5-176">加入所需的小組擁有者核准。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-176">Team owner approval required to join.</span></span>|<span data-ttu-id="6cdd5-177">加入所需的小組擁有者核准。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-177">Team owner approval required to join.</span></span>|
|<span data-ttu-id="6cdd5-178">檔加密</span><span class="sxs-lookup"><span data-stu-id="6cdd5-178">Document encryption</span></span>|||<span data-ttu-id="6cdd5-179">可用於敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="6cdd5-179">Available with sensitivity label</span></span>|
|<span data-ttu-id="6cdd5-180">來賓共用</span><span class="sxs-lookup"><span data-stu-id="6cdd5-180">Guest sharing</span></span>|<span data-ttu-id="6cdd5-181">允許</span><span class="sxs-lookup"><span data-stu-id="6cdd5-181">Allowed</span></span>|<span data-ttu-id="6cdd5-182">可以允許或封鎖</span><span class="sxs-lookup"><span data-stu-id="6cdd5-182">Can be allowed or blocked</span></span>|<span data-ttu-id="6cdd5-183">可以允許或封鎖</span><span class="sxs-lookup"><span data-stu-id="6cdd5-183">Can be allowed or blocked</span></span>|
|<span data-ttu-id="6cdd5-184">非管理裝置</span><span class="sxs-lookup"><span data-stu-id="6cdd5-184">Unmanaged devices</span></span>|<span data-ttu-id="6cdd5-185">無限制</span><span class="sxs-lookup"><span data-stu-id="6cdd5-185">No restriction</span></span>|<span data-ttu-id="6cdd5-186">僅限網頁存取</span><span class="sxs-lookup"><span data-stu-id="6cdd5-186">Web-only access</span></span>|<span data-ttu-id="6cdd5-187">已封鎖</span><span class="sxs-lookup"><span data-stu-id="6cdd5-187">Blocked</span></span>|

<span data-ttu-id="6cdd5-188">設定這些層級包括：</span><span class="sxs-lookup"><span data-stu-id="6cdd5-188">Configuring these tiers involves:</span></span>

- <span data-ttu-id="6cdd5-189">為來賓存取和專用通道設定小組中的設定</span><span class="sxs-lookup"><span data-stu-id="6cdd5-189">Configuring settings in Teams for guest access and private channels</span></span>
- <span data-ttu-id="6cdd5-190">為內部及來賓共用、存取要求和共用連結設定小組相關 SharePoint 網站中的設定</span><span class="sxs-lookup"><span data-stu-id="6cdd5-190">Configuring settings in a team's associated SharePoint site for internal and guest sharing, access requests, and sharing links</span></span>
- <span data-ttu-id="6cdd5-191">針對 *敏感* 和 *高敏感度* 的層級，設定敏感度標籤來分類小組，以及控制來賓共用和非管理裝置的存取</span><span class="sxs-lookup"><span data-stu-id="6cdd5-191">For the *sensitive* and *highly sensitive* tiers, configuring sensitivity labels to classify the teams, and control guest sharing and access from unmanaged devices</span></span>
- <span data-ttu-id="6cdd5-192">針對 *高度敏感* 的層級，設定靈敏度標籤以加密其所套用的檔</span><span class="sxs-lookup"><span data-stu-id="6cdd5-192">For the *highly sensitive* tier, configuring a sensitivity label to encrypt the documents to which it is applied</span></span>

<span data-ttu-id="6cdd5-193">從基準層開始，然後根據需要新增使用 *敏感* 和 *高度機密* 階層的團隊，以協助保護組織中的資訊。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-193">Start with the baseline tier, and then add teams that use the *sensitive* and *highly sensitive* tiers as needed to help protect the information in your organization.</span></span> <span data-ttu-id="6cdd5-194">請參閱下列資源以開始執行：</span><span class="sxs-lookup"><span data-stu-id="6cdd5-194">See these resources to get started:</span></span>

- [<span data-ttu-id="6cdd5-195">為小組設定基準保護</span><span class="sxs-lookup"><span data-stu-id="6cdd5-195">Configure teams with baseline protection</span></span>](configure-teams-baseline-protection.md)
- [<span data-ttu-id="6cdd5-196">為團隊設定高敏感性資料保護</span><span class="sxs-lookup"><span data-stu-id="6cdd5-196">Configure teams with protection for sensitive data</span></span>](configure-teams-sensitive-protection.md)
- [<span data-ttu-id="6cdd5-197">為小組設定高敏感度資料保護</span><span class="sxs-lookup"><span data-stu-id="6cdd5-197">Configure teams with protection for highly sensitive data</span></span>](configure-teams-highly-sensitive-protection.md)

<span data-ttu-id="6cdd5-198">如果您有高度機密的專案需要在組織內共用額外的保護，您可以設定一個小組，該小組使用自己的敏感度標籤來加密檔案，只有小組成員可以讀取這些檔案。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-198">If you have a highly sensitive project that requires additional protection from sharing even within your organization, you can configure a team that uses its own sensitivity label to encrypt files so that only team members can read them.</span></span> <span data-ttu-id="6cdd5-199">如需詳細資訊，請參閱 [Configure a team with security 隔離](secure-teams-security-isolation.md) 。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-199">See [Configure a team with security isolation](secure-teams-security-isolation.md) for details.</span></span>

### <a name="sharing-with-people-outside-your-organization"></a><span data-ttu-id="6cdd5-200">與組織外部的人員共用</span><span class="sxs-lookup"><span data-stu-id="6cdd5-200">Sharing with people outside your organization</span></span>

<span data-ttu-id="6cdd5-201">您可能需要 [與組織外部的人員共用任何敏感度的資訊](collaborate-with-people-outside-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-201">You may need to [share information of any sensitivity with people outside your organization](collaborate-with-people-outside-your-organization.md).</span></span> <span data-ttu-id="6cdd5-202">這可能包括與單一人員共用單一檔，以從世界各地的大型夥伴組織或兼職處理主要專案。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-202">This could range from sharing a single document with a single person to collaborating on a major project with a large partner organization or freelancers from around the world.</span></span> <span data-ttu-id="6cdd5-203">在 Microsoft 365 中，您可以輕鬆執行這種外部共用，並提供適當的防範措施，協助保護您的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-203">In Microsoft 365, this range of external sharing can be done easily and with the appropriate safeguards to help protect your sensitive information.</span></span>

<span data-ttu-id="6cdd5-204">這些資源會協助您開始設定您的環境，以與組織外部的人員進行合作：</span><span class="sxs-lookup"><span data-stu-id="6cdd5-204">These resources will help you get started with setting up your environment for collaborating with people outside your organization:</span></span>

- <span data-ttu-id="6cdd5-205">[在檔上共同](collaborate-on-documents.md) 作業，以共用個別的資料夾檔案。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-205">[Collaborate on documents](collaborate-on-documents.md) for sharing individual files of folders.</span></span>
- <span data-ttu-id="6cdd5-206">[在網站中共同](collaborate-in-site.md) 作業，以與在 SharePoint 網站中的客人進行合作。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-206">[Collaborate in a site](collaborate-in-site.md) for collaborating with guests in a SharePoint site.</span></span>
- <span data-ttu-id="6cdd5-207">[以](collaborate-as-team.md) 團隊方式共同作業，以與小組中的客人合作。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-207">[Collaborate as a team](collaborate-as-team.md) for collaborating with guests in a team.</span></span>

<span data-ttu-id="6cdd5-208">根據所共用資訊的敏感度，您可以新增安全保護，以協助防止 oversharing。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-208">Depending on the sensitivity of the information being shared, you can add safeguards to help prevent oversharing.</span></span> <span data-ttu-id="6cdd5-209">這些資源將協助您設定組織所需的保護：</span><span class="sxs-lookup"><span data-stu-id="6cdd5-209">These resources will help you set up the protections that you need for your organization:</span></span>

- [<span data-ttu-id="6cdd5-210">與未驗證使用者共用檔案和資料夾的最佳做法</span><span class="sxs-lookup"><span data-stu-id="6cdd5-210">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)
- [<span data-ttu-id="6cdd5-211">在與組織外的人員共用檔案時，限制資訊意外暴露</span><span class="sxs-lookup"><span data-stu-id="6cdd5-211">Limit accidental exposure to files when sharing with people outside your organization</span></span>](share-limit-accidental-exposure.md)
- [<span data-ttu-id="6cdd5-212">建立安全的來賓共用環境</span><span class="sxs-lookup"><span data-stu-id="6cdd5-212">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="6cdd5-213">如果您有一個主要專案與一個夥伴組織，您可以使用 Azure 權利管理，在您為專案設定的小組中管理該組織的客人。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-213">If you have a major project with a partner organization, you can use Azure Entitlement Management to manage the guests from that organization in a team that you set up for the project.</span></span> <span data-ttu-id="6cdd5-214">如需詳細資訊，請參閱 [Create a B2B extranet with managed guests](b2b-extranet.md) 。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-214">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="deploy-the-secure-collaboration-solution"></a><span data-ttu-id="6cdd5-215">部署安全的共同作業解決方案</span><span class="sxs-lookup"><span data-stu-id="6cdd5-215">Deploy the secure collaboration solution</span></span>

<span data-ttu-id="6cdd5-216">當您準備好部署此方案時，請繼續執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6cdd5-216">When you're ready to deploy this solution, continue with these steps:</span></span>
1. <span data-ttu-id="6cdd5-217">[為小組設定三種不同的保護層級](configure-teams-three-tiers-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-217">Configure the [three different tiers of protection for Teams](configure-teams-three-tiers-protection.md).</span></span>
2. <span data-ttu-id="6cdd5-218">設定 [與組織外部人員共用任何敏感度資訊的](collaborate-with-people-outside-your-organization.md)設定。</span><span class="sxs-lookup"><span data-stu-id="6cdd5-218">Configure settings for [sharing information of any sensitivity with people outside your organization](collaborate-with-people-outside-your-organization.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6cdd5-219">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6cdd5-219">See also</span></span>

[<span data-ttu-id="6cdd5-220">Microsoft 365 安全性文件</span><span class="sxs-lookup"><span data-stu-id="6cdd5-220">Microsoft 365 security documentation</span></span>](https://docs.microsoft.com/microsoft-365/security)

[<span data-ttu-id="6cdd5-221">Microsoft 365 合規性文件</span><span class="sxs-lookup"><span data-stu-id="6cdd5-221">Microsoft 365 compliance documentation</span></span>](https://docs.microsoft.com/microsoft-365/compliance)

[<span data-ttu-id="6cdd5-222">歡迎使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6cdd5-222">Welcome to Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
