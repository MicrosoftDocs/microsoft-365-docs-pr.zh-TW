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
ms.openlocfilehash: f063a18dcadf5de74b43b2efeba3910f65e40102
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153495"
---
# <a name="information-barriers"></a><span data-ttu-id="35dbb-103">資訊屏障</span><span class="sxs-lookup"><span data-stu-id="35dbb-103">Information barriers</span></span>

## <a name="overview"></a><span data-ttu-id="35dbb-104">概觀</span><span class="sxs-lookup"><span data-stu-id="35dbb-104">Overview</span></span>

<!--

# Information barriers (click-through test)

## Overview



 [![Click-Through for Information Barriers](./media/information-barriers/clickthrough-information-barriers-thumbnail.png)](./media/information-barriers/clickthrough-information-barriers.pdf)


Click through an overview of Information Barriers: [PDF](./media/information-barriers/clickthrough-information-barriers.pdf) | [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/Click-Through-Test/microsoft-365/compliance/media/information-barriers/Clickthrough-Information-Barriers.pptx)

OLD: Move comment field here

 [![Click-Through for Information Barriers](./media/information-barriers/Clickthrough_InformationBarriers_Thumbnail.png)](./media/information-barriers/Clickthrough_InformationBarriers.pdf)

For the PowerPoint slide of this Click-Through, click [here](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/Click-Through-Test/microsoft-365/compliance/media/information-barriers/InfoBarriersExample.pptx).

>[!Tip]
>Try this new [Click-Through on information barriers](media/information-barriers/Clickthrough_InformationBarriers.pdf) for a quick overview of the essential facts.
>

--> 


<span data-ttu-id="35dbb-105">Microsoft 雲端服務包含強大的通訊和協同作業功能。</span><span class="sxs-lookup"><span data-stu-id="35dbb-105">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="35dbb-106">不過，假設您想要限制兩個群組之間的通訊，以避免組織中發生利益衝突。</span><span class="sxs-lookup"><span data-stu-id="35dbb-106">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="35dbb-107">或者，您可能想要限制組織內特定人員之間的通訊，以保護內部資訊。</span><span class="sxs-lookup"><span data-stu-id="35dbb-107">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="35dbb-108">Microsoft 365 可跨群組和組織進行通訊及共同作業，所以有沒有方法可以限制特定使用者群組之間的通訊（必要時）？</span><span class="sxs-lookup"><span data-stu-id="35dbb-108">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="35dbb-109">透過資訊障礙，您可以！</span><span class="sxs-lookup"><span data-stu-id="35dbb-109">With information barriers, you can!</span></span> 

<span data-ttu-id="35dbb-110">立即開始從 Microsoft 小組開始的資訊壁壘。</span><span class="sxs-lookup"><span data-stu-id="35dbb-110">Information barriers are rolling out now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="35dbb-111">假設您的[訂閱](#required-licenses-and-permissions)包含資訊障礙，合規性管理員或資訊屏障管理員可以定義原則，以允許或防止 Microsoft 小組中的使用者群組之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="35dbb-111">Assuming your [subscription](#required-licenses-and-permissions) includes information barriers, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="35dbb-112">資訊屏障原則可以用於下列情況：</span><span class="sxs-lookup"><span data-stu-id="35dbb-112">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="35dbb-113">Day trader 群組中的使用者不應該與行銷小組通訊</span><span class="sxs-lookup"><span data-stu-id="35dbb-113">User in the day trader group should not communicate with the marketing team</span></span>
- <span data-ttu-id="35dbb-114">工作機密公司資訊的融資人員不應該與組織內的某些群組進行通訊</span><span class="sxs-lookup"><span data-stu-id="35dbb-114">Finance personnel working on confidential company information should not communicate with certain groups within their organization</span></span>
- <span data-ttu-id="35dbb-115">內部團隊使用貿易秘訣材料時，不應與組織內特定群組的人員線上通話或聊天</span><span class="sxs-lookup"><span data-stu-id="35dbb-115">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="35dbb-116">調查小組應只通話或與產品開發小組線上交談</span><span class="sxs-lookup"><span data-stu-id="35dbb-116">A research team should only call or chat online with a product development team</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35dbb-117">資訊障礙***只支援***兩種方式限制。</span><span class="sxs-lookup"><span data-stu-id="35dbb-117">Information barriers ***only supports*** two way restrictions.</span></span> <span data-ttu-id="35dbb-118">一種方式限制，例如「行銷」可以與日商貿通訊，但無法與行銷進行***通訊。***</span><span class="sxs-lookup"><span data-stu-id="35dbb-118">One way restrictions, such as marketing can communicate with day traders, but day traders cannot communicate with marketing ***is not supported***.</span></span>

<span data-ttu-id="35dbb-119">針對上述所有範例案例（等等），您可以定義資訊屏障原則，以防止或允許 Microsoft 小組中的通訊。</span><span class="sxs-lookup"><span data-stu-id="35dbb-119">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="35dbb-120">這類原則可以防止使用者不應該來電或與其聊天，或讓使用者只能與 Microsoft 小組中的特定群組進行通訊。</span><span class="sxs-lookup"><span data-stu-id="35dbb-120">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="35dbb-121">透過資訊屏障原則，只要這些原則所涵蓋的使用者嘗試與 Microsoft 小組中的其他使用者通訊，便會進行檢查，以防止（或允許）通訊（如資訊屏障原則所定義）。</span><span class="sxs-lookup"><span data-stu-id="35dbb-121">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="35dbb-122">若要深入瞭解使用者對資訊障礙的經驗，請參閱[Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="35dbb-122">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35dbb-123">目前，資訊障礙不會套用到電子郵件通訊或透過 SharePoint 線上或 OneDrive 共用檔案。</span><span class="sxs-lookup"><span data-stu-id="35dbb-123">Currently, information barriers do not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span> <span data-ttu-id="35dbb-124">此外，資訊障礙獨立于[規範界限](set-up-compliance-boundaries.md)。</span><span class="sxs-lookup"><span data-stu-id="35dbb-124">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p><span data-ttu-id="35dbb-125">在您定義及套用資訊屏障原則之前，請確定您的組織沒有有效的[Exchange 通訊錄原則](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)。</span><span class="sxs-lookup"><span data-stu-id="35dbb-125">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span> <span data-ttu-id="35dbb-126">（資訊障礙是以通訊錄原則為基礎）。</span><span class="sxs-lookup"><span data-stu-id="35dbb-126">(Information barriers are based on address book policies.)</span></span> 

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="35dbb-127">資訊障礙發生什麼事</span><span class="sxs-lookup"><span data-stu-id="35dbb-127">What happens with information barriers</span></span>

<span data-ttu-id="35dbb-128">當資訊屏障原則到位時，不應與其他特定使用者通訊的使用者將無法找到、選取、聊天或呼叫這些使用者。</span><span class="sxs-lookup"><span data-stu-id="35dbb-128">When information barrier policies are in place, people who should not communicate with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="35dbb-129">透過資訊障礙，檢查功能已到位，可防止未經授權的通訊。</span><span class="sxs-lookup"><span data-stu-id="35dbb-129">With information barriers, checks are in place to prevent unauthorized communication.</span></span>

<span data-ttu-id="35dbb-130">資訊障礙最初隻適用于 Microsoft 小組聊天與通道。</span><span class="sxs-lookup"><span data-stu-id="35dbb-130">Initially, information barriers apply to Microsoft Teams chats and channels only.</span></span> <span data-ttu-id="35dbb-131">在 Microsoft 小組中，資訊障礙原則決定並防止下列未授權的通訊類型：</span><span class="sxs-lookup"><span data-stu-id="35dbb-131">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>
- <span data-ttu-id="35dbb-132">搜尋使用者</span><span class="sxs-lookup"><span data-stu-id="35dbb-132">Searching for a user</span></span>
- <span data-ttu-id="35dbb-133">新增成員至團隊</span><span class="sxs-lookup"><span data-stu-id="35dbb-133">Adding a member to a team</span></span>
- <span data-ttu-id="35dbb-134">與某人開始聊天會話</span><span class="sxs-lookup"><span data-stu-id="35dbb-134">Starting a chat session with someone</span></span>
- <span data-ttu-id="35dbb-135">開始群組聊天</span><span class="sxs-lookup"><span data-stu-id="35dbb-135">Starting a group chat</span></span>
- <span data-ttu-id="35dbb-136">邀請某人加入會議</span><span class="sxs-lookup"><span data-stu-id="35dbb-136">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="35dbb-137">共用畫面</span><span class="sxs-lookup"><span data-stu-id="35dbb-137">Sharing a screen</span></span>
- <span data-ttu-id="35dbb-138">撥打電話</span><span class="sxs-lookup"><span data-stu-id="35dbb-138">Placing a call</span></span> 

<span data-ttu-id="35dbb-139">如果納入資訊屏障原則中的人員可防止活動，他們將無法繼續進行。</span><span class="sxs-lookup"><span data-stu-id="35dbb-139">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="35dbb-140">此外，包含在資訊屏障原則中的每一位使用者都有可能封鎖為與 Microsoft 小組中的其他人員進行通訊。</span><span class="sxs-lookup"><span data-stu-id="35dbb-140">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="35dbb-141">當以資訊障礙原則影響的人員屬於同一個小組或群組聊天時，可能會從這些聊天會話中移除，並且可能不允許與群組進一步通訊。</span><span class="sxs-lookup"><span data-stu-id="35dbb-141">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="35dbb-142">若要深入瞭解使用者對資訊障礙的經驗，請參閱[Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="35dbb-142">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="35dbb-143">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="35dbb-143">Required licenses and permissions</span></span>

<span data-ttu-id="35dbb-144">資訊壁壘現在正在推出，並包含在訂閱中，例如：</span><span class="sxs-lookup"><span data-stu-id="35dbb-144">Information barriers are rolling out now, and are included in subscriptions, such as:</span></span>

- <span data-ttu-id="35dbb-145">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="35dbb-145">Microsoft 365 E5</span></span>
- <span data-ttu-id="35dbb-146">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="35dbb-146">Office 365 E5</span></span>
- <span data-ttu-id="35dbb-147">Office 365 進階合規性</span><span class="sxs-lookup"><span data-stu-id="35dbb-147">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="35dbb-148">Microsoft 365 E5 資訊保護和合規性</span><span class="sxs-lookup"><span data-stu-id="35dbb-148">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="35dbb-149">如需詳細資訊，請參閱[規範解決方案](https://products.office.com/business/security-and-compliance/compliance-solutions)。</span><span class="sxs-lookup"><span data-stu-id="35dbb-149">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="35dbb-150">若要[定義或編輯資訊障礙原則](information-barriers-policies.md)，您必須被指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="35dbb-150">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="35dbb-151">Microsoft 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="35dbb-151">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="35dbb-152">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="35dbb-152">Office 365 global administrator</span></span>
- <span data-ttu-id="35dbb-153">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="35dbb-153">Compliance administrator</span></span>
- <span data-ttu-id="35dbb-154">IB 相容性管理（這是新的角色！）</span><span class="sxs-lookup"><span data-stu-id="35dbb-154">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="35dbb-155">（若要深入瞭解角色和許可權，請參閱[Office 365 Security & 合規性中心的許可權](../security/office-365-security/protect-against-threats.md)。）</span><span class="sxs-lookup"><span data-stu-id="35dbb-155">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/protect-against-threats.md).)</span></span>

<span data-ttu-id="35dbb-156">您必須熟悉 PowerShell Cmdlet，才能定義、驗證或編輯資訊障礙原則。</span><span class="sxs-lookup"><span data-stu-id="35dbb-156">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="35dbb-157">雖然我們在操作[方法文章](information-barriers-policies.md)中提供了幾個 PowerShell Cmdlet 範例，但您將需要知道組織的其他詳細資料，例如參數。</span><span class="sxs-lookup"><span data-stu-id="35dbb-157">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="35dbb-158">後續步驟</span><span class="sxs-lookup"><span data-stu-id="35dbb-158">Next steps</span></span>

- [<span data-ttu-id="35dbb-159">深入瞭解 Microsoft 小組中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="35dbb-159">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [<span data-ttu-id="35dbb-160">請參閱可用於資訊障礙原則的屬性</span><span class="sxs-lookup"><span data-stu-id="35dbb-160">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)

- [<span data-ttu-id="35dbb-161">定義資訊障礙的原則</span><span class="sxs-lookup"><span data-stu-id="35dbb-161">Define policies for information barriers</span></span>](information-barriers-policies.md)

- [<span data-ttu-id="35dbb-162">編輯（或移除）資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="35dbb-162">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md) 
