---
title: 針對 Microsoft 365 群組和 Microsoft 團隊規劃組織和生命週期管理
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 有關 Microsoft 365 中的共同作業工具生命週期管理選項的精益
ms.openlocfilehash: 706f1aaecf22c4088d4539c208fef68320c5e710
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377184"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="1b3dd-103">針對 Microsoft 365 群組和 Microsoft 團隊規劃組織和生命週期管理</span><span class="sxs-lookup"><span data-stu-id="1b3dd-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="1b3dd-104">Microsoft 365 群組具有一套豐富的工具，可實施組織所需的控管功能。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="1b3dd-105">下一節將說明功能、建議最佳作法，並提供指導方針，以判斷進行控管需求的適當問題，以及如何符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="1b3dd-106">控制誰可以建立 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="1b3dd-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="1b3dd-107">使用者可以從多個端點（包括 Outlook、SharePoint、小組及其他環境）建立群組。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![影像 desc](../media/04.png)

<span data-ttu-id="1b3dd-109">我們強烈建議使用自助功能群組擁有者，協助使用者更輕鬆地完成其工作。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="1b3dd-110">限制群組和小組的建立會降低使用者的生產力，因為許多 Microsoft 365 服務都需要建立群組才能讓服務運作。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="1b3dd-111">考慮建立群組的下列管理選項：</span><span class="sxs-lookup"><span data-stu-id="1b3dd-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="1b3dd-112">若要限制群組蔓延，請使用 [群組到期原則](microsoft-365-groups-expiration-policy.md) ，以自動刪除未使用的群組。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="1b3dd-113">將群組建立功能限制為 [具有動態成員資格的安全性群組](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) 成員，例如，所有的全職員工。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-113">Limit group creation to members of a [security groups with dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="1b3dd-114">將群組建立限制在安全性群組中，並要求使用者在組織的群組使用原則中完成訓練，以便成為安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="1b3dd-115">如果您想要限制誰可以建立群組，請參閱 [管理誰可以建立 Microsoft 365 群組](manage-creation-of-groups.md) ，以取得如何設定此內容的資訊。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="1b3dd-116">群組刪除、還原及封存</span><span class="sxs-lookup"><span data-stu-id="1b3dd-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="1b3dd-117">刪除 Microsoft 365 群組時，預設會保留30天。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="1b3dd-118">此 30 天期間稱為「虛刪除」，因為您仍可還原該群組。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="1b3dd-119">30 天之後，該群組和關聯的內容將會被永久刪除，而且無法還原。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="1b3dd-120">如果您有保留原則可保留聊天、檔案或郵件，將會在刪除群組之後保留這些專案。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="1b3dd-121">如需詳細資訊，請參閱 [瞭解保留原則](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) 。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-121">See [Learn about retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) for details.</span></span>

<span data-ttu-id="1b3dd-122">如果您想要刪除群組，但保留一或多個群組聯機服務的內容，請參閱封存 [群組、小組和 Yammer](end-life-cycle-groups-teams-sites-yammer.md) 中的資訊。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="1b3dd-123">群組命名原則</span><span class="sxs-lookup"><span data-stu-id="1b3dd-123">Group naming policy</span></span>

<span data-ttu-id="1b3dd-124">群組命名原則可協助您以兩種方式管理群組：</span><span class="sxs-lookup"><span data-stu-id="1b3dd-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="1b3dd-125">您可以使用首碼/尾碼命名原則，在組名的開頭或結尾（或其相關的電子郵件地址），強制執行固定字串或 Azure AD 屬性。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="1b3dd-126">這樣一來，您就可以確保包含（例如，群組名稱中的部門名稱或地區名稱）。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="1b3dd-127">「封鎖的字」原則可以確保在群組名稱中不會使用特定的字詞，例如主管的名稱。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="1b3dd-128">當您從群組連線的任何服務建立群組時，會套用命名原則。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="1b3dd-129">如果您決定使用群組的命名原則，請參閱 [Microsoft 365 群組命名原則](groups-naming-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="1b3dd-130">群組到期原則</span><span class="sxs-lookup"><span data-stu-id="1b3dd-130">Group expiration policy</span></span>

<span data-ttu-id="1b3dd-131">您可以指定到期期限及任何超出該期間結束時間的群組，而且不會被更新。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="1b3dd-132">到期期限是在建立群組時或在最後一次更新的日期時開始。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="1b3dd-133">當您設定群組到期：</span><span class="sxs-lookup"><span data-stu-id="1b3dd-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="1b3dd-134">當到期臨近時，群組的擁有者會收到更新群組的通知。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="1b3dd-135">自動更新主動群組。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="1b3dd-136">任何未更新的群組都會被刪除。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="1b3dd-137">任何刪除的群組可在30天內由群組擁有人或系統管理員復原。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="1b3dd-138">到期原則是一種很好的方法，可確保刪除不再使用的群組，以限制群組大量蔓延。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="1b3dd-139">如果您想要建立群組到期原則，請參閱 [Microsoft 365 群組到期原則](microsoft-365-groups-expiration-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="1b3dd-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>
