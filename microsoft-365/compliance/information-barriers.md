---
title: 深入瞭解 Microsoft 365 中的資訊障礙
description: 使用資訊障礙，以確保在組織內使用 Microsoft Teams 來進行通訊法規遵從性。
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ef3fce82a10792c8289a4a3c4e3cb5639a4d178
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051875"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a><span data-ttu-id="94f56-103">深入瞭解 Microsoft 365 中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="94f56-103">Learn about information barriers in Microsoft 365</span></span>

<span data-ttu-id="94f56-104">Microsoft 雲端服務包括強大的通訊和共同作業功能。</span><span class="sxs-lookup"><span data-stu-id="94f56-104">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="94f56-105">不過，假設您想要限制兩個群組之間的通訊和共同作業，以避免組織中發生利益衝突。</span><span class="sxs-lookup"><span data-stu-id="94f56-105">But suppose that you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="94f56-106">或者，您可能想要限制組織內特定人員之間的通訊和共同作業，以保護內部資訊。</span><span class="sxs-lookup"><span data-stu-id="94f56-106">Or, perhaps you want to restrict communication and collaboration between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="94f56-107">Microsoft 365 能夠跨群組和組織進行通訊及共同作業，所以有一個方法可以限制特定使用者群組之間的通訊和共同作業（必要時）？</span><span class="sxs-lookup"><span data-stu-id="94f56-107">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communication and collaboration  among specific groups of users when necessary?</span></span> <span data-ttu-id="94f56-108">透過資訊障礙，您可以！</span><span class="sxs-lookup"><span data-stu-id="94f56-108">With information barriers, you can!</span></span>

<span data-ttu-id="94f56-109">Microsoft Teams、SharePoint 線上及商務用 OneDrive 支援資訊障礙。</span><span class="sxs-lookup"><span data-stu-id="94f56-109">Microsoft Teams, SharePoint Online, and OneDrive for Business support information barriers.</span></span> <span data-ttu-id="94f56-110">假設您的[訂閱](#required-licenses-and-permissions)包含資訊障礙、合規性管理員或資訊屏障管理員可以定義原則，以允許或防止 Microsoft Teams 中使用者群組之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="94f56-110">Assuming your [subscription](#required-licenses-and-permissions) includes information barriers, a compliance administrator, or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="94f56-111">資訊屏障原則可以用於下列情況：</span><span class="sxs-lookup"><span data-stu-id="94f56-111">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="94f56-112">Day trader 群組中的使用者應該不會與行銷小組進行通訊或共用檔案</span><span class="sxs-lookup"><span data-stu-id="94f56-112">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="94f56-113">從事機密公司資訊的融資人員不應該與組織內的某些群組進行通訊或共用檔案</span><span class="sxs-lookup"><span data-stu-id="94f56-113">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="94f56-114">內部團隊使用貿易秘訣材料時，不應與組織內特定群組的人員線上通話或聊天</span><span class="sxs-lookup"><span data-stu-id="94f56-114">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="94f56-115">調查小組應只通話或與產品開發小組線上交談</span><span class="sxs-lookup"><span data-stu-id="94f56-115">A research team should only call or chat online with a product development team</span></span>
- <span data-ttu-id="94f56-116">Day trader 群組的網站不得由 day trader 群組以外的任何人共用或存取</span><span class="sxs-lookup"><span data-stu-id="94f56-116">A site for day trader group should not be shared or accessed by anyone outside the day trader group</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94f56-117">資訊障礙 \***只支援** _ 兩種方式限制。</span><span class="sxs-lookup"><span data-stu-id="94f56-117">Information barriers \***only supports** _ two way restrictions.</span></span> <span data-ttu-id="94f56-118">單一的方式限制（例如，行銷）可以與日交易進行通訊及共同作業，但是 _不支援_ 使用「行銷」來進行通訊和合作</span><span class="sxs-lookup"><span data-stu-id="94f56-118">One way restrictions, such as marketing can communicate and collaborate with day traders, but day traders cannot communicate and collaborate with marketing _\*_is not supported_\*\*.</span></span>

<span data-ttu-id="94f56-119">在所有上述範例案例中 (和更多) 時，可以定義資訊屏障原則，以防止或允許 Microsoft Teams 中的通訊及共同作業，SharePoint 線上及 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="94f56-119">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications and collaboration in Microsoft Teams, SharePoint Online and OneDrive.</span></span> <span data-ttu-id="94f56-120">這類原則可以防止使用者不應該來電或與其聊天，或讓使用者只能與 Microsoft Teams 中的特定群組進行通訊。</span><span class="sxs-lookup"><span data-stu-id="94f56-120">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="94f56-121">透過資訊屏障原則，每當這些原則所涵蓋的使用者嘗試與 Microsoft Teams 中的其他使用者進行通訊及共同作業時，就會執行 SharePoint 線上或 OneDrive 檢查，以避免 (或允許) 的通訊及共同作業 (如資訊屏障原則所定義) 。</span><span class="sxs-lookup"><span data-stu-id="94f56-121">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate and collaborate with others in Microsoft Teams, SharePoint Online or OneDrive checks are done to prevent (or allow) communication and collaboration (as defined by information barrier policies).</span></span>

<span data-ttu-id="94f56-122">若要深入瞭解使用者對資訊障礙的經驗，請參閱：</span><span class="sxs-lookup"><span data-stu-id="94f56-122">To learn more about the user experience with information barriers, see:</span></span>

- [<span data-ttu-id="94f56-123">Microsoft Teams 中的資訊屏障</span><span class="sxs-lookup"><span data-stu-id="94f56-123">Information barriers in Microsoft Teams</span></span>](/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="94f56-124">線上 SharePoint 的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="94f56-124">Information barriers in SharePoint Online</span></span>](/sharepoint/information-barriers)
- [<span data-ttu-id="94f56-125">OneDrive 中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="94f56-125">Information barriers in OneDrive</span></span>](/onedrive/information-barriers)

> [!IMPORTANT]
> <span data-ttu-id="94f56-126">目前資訊障礙不適用於電子郵件通訊。</span><span class="sxs-lookup"><span data-stu-id="94f56-126">Currently, information barriers do not apply to email communications.</span></span> <span data-ttu-id="94f56-127">此外，資訊障礙獨立于 [規範界限](set-up-compliance-boundaries.md)。</span><span class="sxs-lookup"><span data-stu-id="94f56-127">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p> <span data-ttu-id="94f56-128">在您定義及套用資訊屏障原則之前，請確定您的組織沒有作用中[Exchange 通訊錄原則](/exchange/address-books/address-book-policies/address-book-policies)。</span><span class="sxs-lookup"><span data-stu-id="94f56-128">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span> <span data-ttu-id="94f56-129"> (資訊障礙是以通訊錄原則為基礎。 ) </span><span class="sxs-lookup"><span data-stu-id="94f56-129">(Information barriers are based on address book policies.)</span></span>

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="94f56-130">資訊障礙發生什麼事</span><span class="sxs-lookup"><span data-stu-id="94f56-130">What happens with information barriers</span></span>

<span data-ttu-id="94f56-131">當資訊屏障原則到位時，不應該與其他特定使用者通訊或共用檔案的使用者將無法找到、選取、聊天或呼叫這些使用者。</span><span class="sxs-lookup"><span data-stu-id="94f56-131">When information barrier policies are in place, people who should not communicate or share files with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="94f56-132">透過資訊障礙，檢查功能已到位，可防止未經授權的通訊和協同作業。</span><span class="sxs-lookup"><span data-stu-id="94f56-132">With information barriers, checks are in place to prevent unauthorized communication and collaboration.</span></span> 

<span data-ttu-id="94f56-133">資訊障礙適用于 Microsoft Teams (聊天和頻道) ，SharePoint 線上及 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="94f56-133">Information barriers applies to Microsoft Teams (chats and channels), SharePoint Online and OneDrive.</span></span> <span data-ttu-id="94f56-134">在 Microsoft Teams 中，資訊屏障原則決定並防止以下種類的未經授權的通訊：</span><span class="sxs-lookup"><span data-stu-id="94f56-134">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>

- <span data-ttu-id="94f56-135">搜尋使用者</span><span class="sxs-lookup"><span data-stu-id="94f56-135">Searching for a user</span></span>
- <span data-ttu-id="94f56-136">新增成員至團隊</span><span class="sxs-lookup"><span data-stu-id="94f56-136">Adding a member to a team</span></span>
- <span data-ttu-id="94f56-137">開始與其他人的聊天工作階段</span><span class="sxs-lookup"><span data-stu-id="94f56-137">Starting a chat session with someone</span></span>
- <span data-ttu-id="94f56-138">開始群組聊天</span><span class="sxs-lookup"><span data-stu-id="94f56-138">Starting a group chat</span></span>
- <span data-ttu-id="94f56-139">邀請其他人加入會議</span><span class="sxs-lookup"><span data-stu-id="94f56-139">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="94f56-140">共用螢幕</span><span class="sxs-lookup"><span data-stu-id="94f56-140">Sharing a screen</span></span>
- <span data-ttu-id="94f56-141">撥打電話</span><span class="sxs-lookup"><span data-stu-id="94f56-141">Placing a call</span></span>
- <span data-ttu-id="94f56-142">與其他使用者共用檔案</span><span class="sxs-lookup"><span data-stu-id="94f56-142">Sharing a file with another user</span></span>
- <span data-ttu-id="94f56-143">透過共用連結存取檔案</span><span class="sxs-lookup"><span data-stu-id="94f56-143">Access to file through sharing link</span></span>

<span data-ttu-id="94f56-144">如果將相關人員包括在資訊屏障原則中以阻止活動，則他們將無法繼續進行。</span><span class="sxs-lookup"><span data-stu-id="94f56-144">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="94f56-145">此外，系統可能已將資訊屏障原則中包含的每個人封鎖，無法與 Microsoft Teams 中的其他人通訊。</span><span class="sxs-lookup"><span data-stu-id="94f56-145">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="94f56-146">當受到資訊屏障原則影響的人員屬於同一個小組或群組聊天時，系統可能會從這些聊天工作階段中移除這些人員，而且這些人可能無法與群組進一步通訊。</span><span class="sxs-lookup"><span data-stu-id="94f56-146">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="94f56-147">若要深入瞭解資訊障礙的使用者經驗，請參閱[Microsoft Teams 中的資訊障礙](/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="94f56-147">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams).</span></span>

<span data-ttu-id="94f56-148">在 SharePoint Online 和 OneDrive 中，資訊屏障原則會決定並防止下列類型的未授權共同作業：</span><span class="sxs-lookup"><span data-stu-id="94f56-148">In SharePoint Online and OneDrive, information barrier policies determine and prevent the following kinds of unauthorized collaborations:</span></span>

- <span data-ttu-id="94f56-149">將成員新增至網站</span><span class="sxs-lookup"><span data-stu-id="94f56-149">Adding a member to a site</span></span>
- <span data-ttu-id="94f56-150">依使用者存取網站或內容</span><span class="sxs-lookup"><span data-stu-id="94f56-150">Accessing site or content by a user</span></span>
- <span data-ttu-id="94f56-151">與其他使用者共用網站或內容</span><span class="sxs-lookup"><span data-stu-id="94f56-151">Sharing site or content with another user</span></span>
- <span data-ttu-id="94f56-152">搜尋網站</span><span class="sxs-lookup"><span data-stu-id="94f56-152">Searching a site</span></span>

<span data-ttu-id="94f56-153">若要深入瞭解資訊障礙的使用者經驗，請參閱[SharePoint Online 中的資訊障礙](/sharepoint/information-barriers)。</span><span class="sxs-lookup"><span data-stu-id="94f56-153">To learn more about the user experience with information barriers, see [information barriers in SharePoint Online](/sharepoint/information-barriers)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="94f56-154">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="94f56-154">Required licenses and permissions</span></span>

<span data-ttu-id="94f56-155">資訊壁壘現在正在推出，並包含在訂閱中，例如：</span><span class="sxs-lookup"><span data-stu-id="94f56-155">Information barriers are rolling out now, and are included in subscriptions, such as:</span></span>

- <span data-ttu-id="94f56-156">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="94f56-156">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="94f56-157">Office 365E5/A5</span><span class="sxs-lookup"><span data-stu-id="94f56-157">Office 365 E5/A5</span></span>
- <span data-ttu-id="94f56-158">Office 365 進階合規性</span><span class="sxs-lookup"><span data-stu-id="94f56-158">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="94f56-159">Microsoft 365規範 E5/A5</span><span class="sxs-lookup"><span data-stu-id="94f56-159">Microsoft 365 Compliance E5/A5</span></span>
- <span data-ttu-id="94f56-160">Microsoft 365 內部風險管理</span><span class="sxs-lookup"><span data-stu-id="94f56-160">Microsoft 365 Insider Risk Management</span></span>

<span data-ttu-id="94f56-161">如需詳細資訊，請參閱[Microsoft 365 授權指南以取得安全性 & 相容性](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。</span><span class="sxs-lookup"><span data-stu-id="94f56-161">For more information, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

<span data-ttu-id="94f56-162">若要 [定義或編輯資訊障礙原則](information-barriers-policies.md)，您必須被指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="94f56-162">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="94f56-163">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="94f56-163">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="94f56-164">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="94f56-164">Office 365 global administrator</span></span>
- <span data-ttu-id="94f56-165">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="94f56-165">Compliance administrator</span></span>
- <span data-ttu-id="94f56-166">IB 合規性管理</span><span class="sxs-lookup"><span data-stu-id="94f56-166">IB Compliance Management</span></span>

<span data-ttu-id="94f56-167"> (若要深入瞭解角色和許可權，請參閱[Office 365 Security & 合規性中心的許可權](../security/defender-365-security/permissions-in-the-security-and-compliance-center.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="94f56-167">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](../security/defender-365-security/permissions-in-the-security-and-compliance-center.md).)</span></span>

<span data-ttu-id="94f56-168">您必須熟悉 PowerShell Cmdlet，才能定義、驗證或編輯資訊障礙原則。</span><span class="sxs-lookup"><span data-stu-id="94f56-168">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="94f56-169">雖然我們在操作 [方法文章](information-barriers-policies.md)中提供了幾個 PowerShell Cmdlet 範例，但您將需要知道組織的其他詳細資料，例如參數。</span><span class="sxs-lookup"><span data-stu-id="94f56-169">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know other details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="94f56-170">後續步驟</span><span class="sxs-lookup"><span data-stu-id="94f56-170">Next steps</span></span>

- [<span data-ttu-id="94f56-171">深入瞭解 Microsoft Teams 中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="94f56-171">Learn more about information barriers in Microsoft Teams</span></span>](/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="94f56-172">深入瞭解 SharePoint 線上中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="94f56-172">Learn more about information barriers in SharePoint Online</span></span>](/sharepoint/information-barriers)
- [<span data-ttu-id="94f56-173">深入瞭解 OneDrive 中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="94f56-173">Learn more about information barriers in OneDrive</span></span>](/onedrive/information-barriers)
- [<span data-ttu-id="94f56-174">請參閱可用於資訊障礙原則的屬性</span><span class="sxs-lookup"><span data-stu-id="94f56-174">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="94f56-175">定義資訊屏障的原則</span><span class="sxs-lookup"><span data-stu-id="94f56-175">Define policies for information barriers</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="94f56-176">編輯 (或移除) 資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="94f56-176">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md)