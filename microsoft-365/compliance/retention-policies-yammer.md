---
title: 了解 Yammer 的保留
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解適用於 Yammer 的保留原則。
ms.openlocfilehash: d4988eee419a38497d4fa35cdb3e2f7fec103688
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53052924"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="b227e-103">了解 Yammer 的保留</span><span class="sxs-lookup"><span data-stu-id="b227e-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="b227e-104">*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="b227e-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="b227e-105">此功能處於預覽階段，可能會有所變更。</span><span class="sxs-lookup"><span data-stu-id="b227e-105">This feature is in preview and subject to change.</span></span>

<span data-ttu-id="b227e-106">本文中的資訊可補充[了解保留原則](retention.md)，因為其包含 Yammer 專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="b227e-106">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="b227e-107">若為其他工作負載，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b227e-107">For other workloads, see:</span></span>

- [<span data-ttu-id="b227e-108">了解 SharePoint 和 OneDrive 的保留功能</span><span class="sxs-lookup"><span data-stu-id="b227e-108">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="b227e-109">了解 Microsoft Teams 保留</span><span class="sxs-lookup"><span data-stu-id="b227e-109">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="b227e-110">了解 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="b227e-110">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="b227e-111">保留與刪除包含的內容</span><span class="sxs-lookup"><span data-stu-id="b227e-111">What's included for retention and deletion</span></span>

<span data-ttu-id="b227e-112">您可以對 Yammer 使用保留原則來保留及刪除下列 Yammer 項目：社群訊息和私人訊息。</span><span class="sxs-lookup"><span data-stu-id="b227e-112">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and private messages.</span></span>

<span data-ttu-id="b227e-113">不會在這些訊息中包含來自其他人表情符號形式的反應。</span><span class="sxs-lookup"><span data-stu-id="b227e-113">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="b227e-114">Yammer 保留功能的運作方式</span><span class="sxs-lookup"><span data-stu-id="b227e-114">How retention works with Yammer</span></span>

<span data-ttu-id="b227e-115">您可以使用保留原則來保留及刪除 Yammer 中的社群訊息和私人訊息。</span><span class="sxs-lookup"><span data-stu-id="b227e-115">You can use a retention policy to retain and delete community messages and private messages in Yammer.</span></span> <span data-ttu-id="b227e-116">私人訊息會儲存在訊息中包含的每個使用者信箱的隱藏資料夾中，而社群訊息則會儲存在社群群組信箱中的類似隱藏資料夾中。</span><span class="sxs-lookup"><span data-stu-id="b227e-116">Private messages are stored in a hidden folder in the mailbox of each user included in the message, and community messages are stored in a similar hidden folder in the group mailbox for the community.</span></span>

<span data-ttu-id="b227e-117">Yammer 訊息不受針對使用者或群組信箱設定的保留原則影響。</span><span class="sxs-lookup"><span data-stu-id="b227e-117">Yammer messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="b227e-118">儘管 Yammer 訊息會儲存在 Exchange 中，此 Yammer 資料只會由針對 **Yammer 社群訊息** 和 **Yammer 使用者訊息** 位置設定的保留原則包含。</span><span class="sxs-lookup"><span data-stu-id="b227e-118">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer user messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="b227e-119">如果使用者包含在保留 Yammer 資料的作用中保留原則中，且您刪除了包含在此原則中使用者的信箱，若要保留此 Yammer 資料，該信箱會轉換成[非作用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="b227e-119">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="b227e-120">如果您不需要為使用者保留此 Yammer 資料，請在刪除其信箱之前先將該使用者帳戶從保留原則排除。</span><span class="sxs-lookup"><span data-stu-id="b227e-120">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="b227e-121">針對 Yammer 訊息設定保留原則之後，Exchange 服務中的計時器工作就會針對儲存這些 Yammer 訊息所在的隱藏資料夾，定期評估其中項目。</span><span class="sxs-lookup"><span data-stu-id="b227e-121">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="b227e-122">計時器工作最多需要七天的時間來執行。</span><span class="sxs-lookup"><span data-stu-id="b227e-122">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="b227e-123">當這些項目超過其保留期間時，就會移至 SubstrateHolds 資料夾 (進行永久刪除前，每個使用者或群組信箱中用來儲存「虛刪除」項目的隱藏資料夾)。</span><span class="sxs-lookup"><span data-stu-id="b227e-123">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="b227e-124">有鑑於[保留的首要原則](retention.md#the-principles-of-retention-or-what-takes-precedence)，若因為另一個保留原則而必須保留同一個項目，或因為法律或調查理由，而該項目在 eDiscovery 保留之下，則一律會暫停永久刪除。</span><span class="sxs-lookup"><span data-stu-id="b227e-124">Because of the [first principle of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), permanent deletion is always suspended if the same item must be retained because of another retention policy, or it is under eDiscovery holds for legal or investigative reasons.</span></span>

<span data-ttu-id="b227e-125">針對 Yammer 訊息設定保留原則後，內容的路徑會取決於保留原則為保留然後刪除、僅保留或僅刪除。</span><span class="sxs-lookup"><span data-stu-id="b227e-125">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="b227e-126">當保留原則為保留然後刪除時：</span><span class="sxs-lookup"><span data-stu-id="b227e-126">When the retention policy is to retain and then delete:</span></span>

![Yammer 訊息的保留流程圖](../media/yammerretentionlifecycle.png)

<span data-ttu-id="b227e-128">針對圖表中的兩個路徑：</span><span class="sxs-lookup"><span data-stu-id="b227e-128">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="b227e-129">如果在保留期間使用者 **編輯或刪除某個 Yammer 訊息**，系統就立即複製原始訊息 (如果是編輯) 或將其移動 (如果是刪除) 到 SubstrateHolds 資料夾。</span><span class="sxs-lookup"><span data-stu-id="b227e-129">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="b227e-130">訊息會儲存在那裡直到保留期間到期為止，然後永久刪除訊息。</span><span class="sxs-lookup"><span data-stu-id="b227e-130">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="b227e-131">**如果未刪除 Yammer 訊息**，以及目前訊息經過編輯後，則會在保留期間到期後，將訊息移至 SubstrateHolds 資料夾。</span><span class="sxs-lookup"><span data-stu-id="b227e-131">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="b227e-132">此動作從到期日起最多需要七天才會完成。</span><span class="sxs-lookup"><span data-stu-id="b227e-132">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="b227e-133">當訊息位於 SubstrateHolds 資料夾，即會立即永久刪除。</span><span class="sxs-lookup"><span data-stu-id="b227e-133">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="b227e-134">SubstrateHolds 資料夾中的訊息可供電子文件探索工具搜尋。</span><span class="sxs-lookup"><span data-stu-id="b227e-134">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="b227e-135">在訊息遭到永久刪除 (在 [SubstrateHolds] 資料夾中) 前，電子文件探索工具都可以搜尋到這些訊息。</span><span class="sxs-lookup"><span data-stu-id="b227e-135">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="b227e-136">當保留原則為僅保留或僅刪除時，內容路徑為保留和刪除的變化。</span><span class="sxs-lookup"><span data-stu-id="b227e-136">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="b227e-137">「僅保留」保留原則的內容路徑</span><span class="sxs-lookup"><span data-stu-id="b227e-137">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="b227e-138">**如果已編輯或刪除 Yammer 訊息**：系統會立即在 SubstrateHolds 資料夾中建立原始訊息的複本，並保留在該處，直到保留期間到期。</span><span class="sxs-lookup"><span data-stu-id="b227e-138">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="b227e-139">然後訊息會從立即從 SubstrateHolds 資料夾中永久刪除。</span><span class="sxs-lookup"><span data-stu-id="b227e-139">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="b227e-140">**如果未修改或刪除 Yammer 訊息**，以及針對在保留期間經過編輯的目前訊息：保留期間前後不會有任何變化；訊息仍會保留在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="b227e-140">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="b227e-141">僅刪除保留原則的內容路徑</span><span class="sxs-lookup"><span data-stu-id="b227e-141">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="b227e-142">**如果未在保留期間刪除 Yammer 訊息**：在保留期間結束時，系統會將訊息移至 SubstrateHolds 資料夾。</span><span class="sxs-lookup"><span data-stu-id="b227e-142">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="b227e-143">此動作從到期日起最多需要七天才會完成。</span><span class="sxs-lookup"><span data-stu-id="b227e-143">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="b227e-144">然後訊息會從立即從 SubstrateHolds 資料夾中永久刪除。</span><span class="sxs-lookup"><span data-stu-id="b227e-144">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="b227e-145">**如果使用者在保留期間刪除 Yammer 訊息**，系統會立即將該項目移至 SubstrateHolds 資料夾，在其中會立即永久刪除該項目。</span><span class="sxs-lookup"><span data-stu-id="b227e-145">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="b227e-146">訊息和外部使用者</span><span class="sxs-lookup"><span data-stu-id="b227e-146">Messages and external users</span></span>

<span data-ttu-id="b227e-147">根據預設，Yammer 使用者訊息的保留原則會套用至貴組織中的所有使用者，但不會套用至外部使用者。</span><span class="sxs-lookup"><span data-stu-id="b227e-147">By default, a retention policy for Yammer user messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="b227e-148">如果您使用 [選擇使用者 **]** 並指定其帳戶，則可以將保留原則套用至外部使用者。</span><span class="sxs-lookup"><span data-stu-id="b227e-148">You can apply a retention policy to external users if you use the **Choose user** and specify their account.</span></span> 

<span data-ttu-id="b227e-149">目前不支援 Azure B2B 來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="b227e-149">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="b227e-150">當使用者離開組織時</span><span class="sxs-lookup"><span data-stu-id="b227e-150">When a user leaves the organization</span></span> 

<span data-ttu-id="b227e-151">如果某位使用者離開您的組織，且其 Microsoft 365 帳戶被刪除，則其要保留的 Yammer 使用者訊息會儲存在非作用中的信箱中。</span><span class="sxs-lookup"><span data-stu-id="b227e-151">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer user messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="b227e-152">這些訊息仍受限於在他們的信箱被設成非作用中之前，對使用者設定的任何保留原則，且內容可供電子文件探索搜尋。</span><span class="sxs-lookup"><span data-stu-id="b227e-152">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="b227e-153">如需詳細資訊，請參閱 [Exchange Online 中的非作用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="b227e-153">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="b227e-154">如果使用者將所有檔案儲存在 Yammer 中，請參閱適用於 SharePoint 和 OneDrive 的[同等小節](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。</span><span class="sxs-lookup"><span data-stu-id="b227e-154">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="b227e-155">限制</span><span class="sxs-lookup"><span data-stu-id="b227e-155">Limitations</span></span>

<span data-ttu-id="b227e-156">Yammer 保留原則目前處於預覽，且我們會持續努力將保留功能最佳化。</span><span class="sxs-lookup"><span data-stu-id="b227e-156">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="b227e-157">在此同時，當您對 Yammer 社群訊息和私人訊息使用保留時，請注意下列限制：</span><span class="sxs-lookup"><span data-stu-id="b227e-157">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and private messages:</span></span>

- <span data-ttu-id="b227e-158">當您針對 [Yammer 使用者訊息 **]** 位置選取 [選擇使用者 **]** 時，您可能會看到來賓和非信箱使用者。</span><span class="sxs-lookup"><span data-stu-id="b227e-158">When you select **Choose users** for the **Yammer user messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="b227e-159">保留原則並非為這些使用者設計，因此請不要選取他們。</span><span class="sxs-lookup"><span data-stu-id="b227e-159">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="b227e-160">配置指導方針</span><span class="sxs-lookup"><span data-stu-id="b227e-160">Configuration guidance</span></span>

<span data-ttu-id="b227e-161">如果您才剛開始在 Microsoft 365 中進行設定保留，請參閱 [開始使用保留原則及保留標籤](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="b227e-161">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="b227e-162">如果您已準備好為 Yammer 設定保留原則，請參閱[建立及設定保留原則](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b227e-162">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>