---
title: 深入瞭解資訊障礙
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用資訊障礙，以確保您的組織內的 Microsoft 小組能夠進行通訊法規遵從性。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5bd922bee0808262b297245340a2dd641f44018f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817532"
---
# <a name="information-barriers"></a><span data-ttu-id="53cbb-103">資訊屏障</span><span class="sxs-lookup"><span data-stu-id="53cbb-103">Information barriers</span></span>

<span data-ttu-id="53cbb-104">Microsoft 雲端服務包含強大的通訊和協同作業功能。</span><span class="sxs-lookup"><span data-stu-id="53cbb-104">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="53cbb-105">不過，假設您想要限制兩個群組之間的通訊，以避免組織中發生利益衝突。</span><span class="sxs-lookup"><span data-stu-id="53cbb-105">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="53cbb-106">或者，您可能想要限制組織內特定人員之間的通訊，以保護內部資訊。</span><span class="sxs-lookup"><span data-stu-id="53cbb-106">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="53cbb-107">Microsoft 365 可跨群組和組織進行通訊及共同作業，所以有沒有方法可以限制特定使用者群組之間的通訊（必要時）？</span><span class="sxs-lookup"><span data-stu-id="53cbb-107">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="53cbb-108">透過資訊障礙，您可以！</span><span class="sxs-lookup"><span data-stu-id="53cbb-108">With information barriers, you can!</span></span> 

<span data-ttu-id="53cbb-109">立即開始從 Microsoft 小組開始的資訊壁壘。</span><span class="sxs-lookup"><span data-stu-id="53cbb-109">Information barriers are rolling out now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="53cbb-110">假設您的[訂閱](#required-licenses-and-permissions)包含資訊障礙，合規性管理員或資訊屏障管理員可以定義原則，以允許或防止 Microsoft 小組中的使用者群組之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="53cbb-110">Assuming your [subscription](#required-licenses-and-permissions) includes information barriers, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="53cbb-111">資訊屏障原則可以用於下列情況：</span><span class="sxs-lookup"><span data-stu-id="53cbb-111">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="53cbb-112">Day trader 群組中的使用者不應該與行銷小組通訊</span><span class="sxs-lookup"><span data-stu-id="53cbb-112">User in the day trader group should not communicate with the marketing team</span></span>
- <span data-ttu-id="53cbb-113">工作機密公司資訊的融資人員不應該與組織內的某些群組進行通訊</span><span class="sxs-lookup"><span data-stu-id="53cbb-113">Finance personnel working on confidential company information should not communicate with certain groups within their organization</span></span>
- <span data-ttu-id="53cbb-114">內部團隊使用貿易秘訣材料時，不應與組織內特定群組的人員線上通話或聊天</span><span class="sxs-lookup"><span data-stu-id="53cbb-114">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="53cbb-115">調查小組應只通話或與產品開發小組線上交談</span><span class="sxs-lookup"><span data-stu-id="53cbb-115">A research team should only call or chat online with a product development team</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53cbb-116">資訊障礙***只支援***兩種方式限制。</span><span class="sxs-lookup"><span data-stu-id="53cbb-116">Information barriers ***only supports*** two way restrictions.</span></span> <span data-ttu-id="53cbb-117">一種方式限制，例如「行銷」可以與日商貿通訊，但無法與行銷進行***通訊。***</span><span class="sxs-lookup"><span data-stu-id="53cbb-117">One way restrictions, such as marketing can communicate with day traders, but day traders cannot communicate with marketing ***is not supported***.</span></span>

<span data-ttu-id="53cbb-118">針對上述所有範例案例（等等），您可以定義資訊屏障原則，以防止或允許 Microsoft 小組中的通訊。</span><span class="sxs-lookup"><span data-stu-id="53cbb-118">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="53cbb-119">這類原則可以防止使用者不應該來電或與其聊天，或讓使用者只能與 Microsoft 小組中的特定群組進行通訊。</span><span class="sxs-lookup"><span data-stu-id="53cbb-119">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="53cbb-120">透過資訊屏障原則，只要這些原則所涵蓋的使用者嘗試與 Microsoft 小組中的其他使用者通訊，便會進行檢查，以防止（或允許）通訊（如資訊屏障原則所定義）。</span><span class="sxs-lookup"><span data-stu-id="53cbb-120">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="53cbb-121">若要深入瞭解使用者對資訊障礙的經驗，請參閱[Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="53cbb-121">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53cbb-122">目前，資訊障礙不會套用到電子郵件通訊或透過 SharePoint 線上或 OneDrive 共用檔案。</span><span class="sxs-lookup"><span data-stu-id="53cbb-122">Currently, information barriers do not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span> <span data-ttu-id="53cbb-123">此外，資訊障礙獨立于[規範界限](set-up-compliance-boundaries.md)。</span><span class="sxs-lookup"><span data-stu-id="53cbb-123">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p><span data-ttu-id="53cbb-124">在您定義及套用資訊屏障原則之前，請確定您的組織沒有有效的[Exchange 通訊錄原則](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)。</span><span class="sxs-lookup"><span data-stu-id="53cbb-124">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span> <span data-ttu-id="53cbb-125">（資訊障礙是以通訊錄原則為基礎）。</span><span class="sxs-lookup"><span data-stu-id="53cbb-125">(Information barriers are based on address book policies.)</span></span> 

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="53cbb-126">資訊障礙發生什麼事</span><span class="sxs-lookup"><span data-stu-id="53cbb-126">What happens with information barriers</span></span>

<span data-ttu-id="53cbb-127">當資訊屏障原則到位時，不應與其他特定使用者通訊的使用者將無法找到、選取、聊天或呼叫這些使用者。</span><span class="sxs-lookup"><span data-stu-id="53cbb-127">When information barrier policies are in place, people who should not communicate with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="53cbb-128">透過資訊障礙，檢查功能已到位，可防止未經授權的通訊。</span><span class="sxs-lookup"><span data-stu-id="53cbb-128">With information barriers, checks are in place to prevent unauthorized communication.</span></span>

<span data-ttu-id="53cbb-129">資訊障礙最初隻適用于 Microsoft 小組聊天與通道。</span><span class="sxs-lookup"><span data-stu-id="53cbb-129">Initially, information barriers apply to Microsoft Teams chats and channels only.</span></span> <span data-ttu-id="53cbb-130">在 Microsoft 小組中，資訊障礙原則決定並防止下列未授權的通訊類型：</span><span class="sxs-lookup"><span data-stu-id="53cbb-130">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>
- <span data-ttu-id="53cbb-131">搜尋使用者</span><span class="sxs-lookup"><span data-stu-id="53cbb-131">Searching for a user</span></span>
- <span data-ttu-id="53cbb-132">新增成員至團隊</span><span class="sxs-lookup"><span data-stu-id="53cbb-132">Adding a member to a team</span></span>
- <span data-ttu-id="53cbb-133">與某人開始聊天會話</span><span class="sxs-lookup"><span data-stu-id="53cbb-133">Starting a chat session with someone</span></span>
- <span data-ttu-id="53cbb-134">開始群組聊天</span><span class="sxs-lookup"><span data-stu-id="53cbb-134">Starting a group chat</span></span>
- <span data-ttu-id="53cbb-135">邀請某人加入會議</span><span class="sxs-lookup"><span data-stu-id="53cbb-135">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="53cbb-136">共用畫面</span><span class="sxs-lookup"><span data-stu-id="53cbb-136">Sharing a screen</span></span>
- <span data-ttu-id="53cbb-137">撥打電話</span><span class="sxs-lookup"><span data-stu-id="53cbb-137">Placing a call</span></span> 

<span data-ttu-id="53cbb-138">如果納入資訊屏障原則中的人員可防止活動，他們將無法繼續進行。</span><span class="sxs-lookup"><span data-stu-id="53cbb-138">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="53cbb-139">此外，包含在資訊屏障原則中的每一位使用者都有可能封鎖為與 Microsoft 小組中的其他人員進行通訊。</span><span class="sxs-lookup"><span data-stu-id="53cbb-139">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="53cbb-140">當以資訊障礙原則影響的人員屬於同一個小組或群組聊天時，可能會從這些聊天會話中移除，並且可能不允許與群組進一步通訊。</span><span class="sxs-lookup"><span data-stu-id="53cbb-140">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="53cbb-141">若要深入瞭解使用者對資訊障礙的經驗，請參閱[Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="53cbb-141">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="53cbb-142">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="53cbb-142">Required licenses and permissions</span></span>

<span data-ttu-id="53cbb-143">資訊壁壘現在正在推出，並包含在訂閱中，例如：</span><span class="sxs-lookup"><span data-stu-id="53cbb-143">Information barriers are rolling out now, and are included in subscriptions, such as:</span></span>

- <span data-ttu-id="53cbb-144">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="53cbb-144">Microsoft 365 E5</span></span>
- <span data-ttu-id="53cbb-145">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="53cbb-145">Office 365 E5</span></span>
- <span data-ttu-id="53cbb-146">Office 365 進階合規性</span><span class="sxs-lookup"><span data-stu-id="53cbb-146">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="53cbb-147">Microsoft 365 規範 E5</span><span class="sxs-lookup"><span data-stu-id="53cbb-147">Microsoft 365 Compliance E5</span></span>

<span data-ttu-id="53cbb-148">如需詳細資訊，請參閱[規範解決方案](https://products.office.com/business/security-and-compliance/compliance-solutions)。</span><span class="sxs-lookup"><span data-stu-id="53cbb-148">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="53cbb-149">若要[定義或編輯資訊障礙原則](information-barriers-policies.md)，您必須被指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="53cbb-149">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="53cbb-150">Microsoft 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="53cbb-150">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="53cbb-151">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="53cbb-151">Office 365 global administrator</span></span>
- <span data-ttu-id="53cbb-152">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="53cbb-152">Compliance administrator</span></span>
- <span data-ttu-id="53cbb-153">IB 相容性管理（這是新的角色！）</span><span class="sxs-lookup"><span data-stu-id="53cbb-153">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="53cbb-154">（若要深入瞭解角色和許可權，請參閱[Office 365 Security & 合規性中心的許可權](../security/office-365-security/protect-against-threats.md)。）</span><span class="sxs-lookup"><span data-stu-id="53cbb-154">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/protect-against-threats.md).)</span></span>

<span data-ttu-id="53cbb-155">您必須熟悉 PowerShell Cmdlet，才能定義、驗證或編輯資訊障礙原則。</span><span class="sxs-lookup"><span data-stu-id="53cbb-155">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="53cbb-156">雖然我們在操作[方法文章](information-barriers-policies.md)中提供了幾個 PowerShell Cmdlet 範例，但您將需要知道組織的其他詳細資料，例如參數。</span><span class="sxs-lookup"><span data-stu-id="53cbb-156">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="53cbb-157">後續步驟</span><span class="sxs-lookup"><span data-stu-id="53cbb-157">Next steps</span></span>

- [<span data-ttu-id="53cbb-158">深入瞭解 Microsoft 小組中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="53cbb-158">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [<span data-ttu-id="53cbb-159">請參閱可用於資訊障礙原則的屬性</span><span class="sxs-lookup"><span data-stu-id="53cbb-159">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)

- [<span data-ttu-id="53cbb-160">定義資訊障礙的原則</span><span class="sxs-lookup"><span data-stu-id="53cbb-160">Define policies for information barriers</span></span>](information-barriers-policies.md)

- [<span data-ttu-id="53cbb-161">編輯（或移除）資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="53cbb-161">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md) 
