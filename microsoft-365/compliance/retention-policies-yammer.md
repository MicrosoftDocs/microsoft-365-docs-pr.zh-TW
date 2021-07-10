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
ms.openlocfilehash: 1398bf385631967d92de760924ef94e2b3c16441
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362291"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="db5de-103">了解 Yammer 的保留</span><span class="sxs-lookup"><span data-stu-id="db5de-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="db5de-104">*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="db5de-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="db5de-105">此功能處於預覽階段，可能會有所變更。</span><span class="sxs-lookup"><span data-stu-id="db5de-105">This feature is in preview and subject to change.</span></span>

<span data-ttu-id="db5de-106">本文中的資訊可補充[了解保留原則](retention.md)，因為其包含 Yammer 專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="db5de-106">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="db5de-107">若為其他工作負載，請參閱：</span><span class="sxs-lookup"><span data-stu-id="db5de-107">For other workloads, see:</span></span>

- [<span data-ttu-id="db5de-108">了解 SharePoint 和 OneDrive 的保留功能</span><span class="sxs-lookup"><span data-stu-id="db5de-108">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="db5de-109">了解 Microsoft Teams 保留</span><span class="sxs-lookup"><span data-stu-id="db5de-109">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="db5de-110">了解 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="db5de-110">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="db5de-111">保留與刪除包含的內容</span><span class="sxs-lookup"><span data-stu-id="db5de-111">What's included for retention and deletion</span></span>

<span data-ttu-id="db5de-112">您可以使用保留原則來保留及刪除下列 Yammer 項目：社群訊息和使用者訊息。</span><span class="sxs-lookup"><span data-stu-id="db5de-112">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and user messages.</span></span>

<span data-ttu-id="db5de-113">不會在這些訊息中包含來自其他人表情符號形式的反應。</span><span class="sxs-lookup"><span data-stu-id="db5de-113">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="db5de-114">Yammer 保留功能的運作方式</span><span class="sxs-lookup"><span data-stu-id="db5de-114">How retention works with Yammer</span></span>

<span data-ttu-id="db5de-115">使用本章節了解後端儲存空間和流程如何滿足您的合規性要求，並且應透過電子文件探索工具而不是 Yammer 應用程式中目前可見的訊息進行驗證。</span><span class="sxs-lookup"><span data-stu-id="db5de-115">Use this section to understand how your compliance requirements are met by backend storage and processes, and should be verified by eDiscovery tools rather than by messages that are currently visible in the Yammer app.</span></span>

<span data-ttu-id="db5de-116">您可以使用保留原則來保留 Yammer 中社群訊息和使用者訊息的資料，並刪除這些訊息。</span><span class="sxs-lookup"><span data-stu-id="db5de-116">You can use a retention policy to retain data from community messages and user messages in Yammer, and delete these messages.</span></span> <span data-ttu-id="db5de-117">在幕後，會使用 Exchange 信箱來儲存從這些訊息複製的資料。</span><span class="sxs-lookup"><span data-stu-id="db5de-117">Behind the scenes, Exchange mailboxes are used to store data copied from these messages.</span></span> <span data-ttu-id="db5de-118">來自 Yammer 使用者訊息的資料會儲存在使用者訊息中包含的每個使用者的信箱中的隱藏資料夾中，且會將社群訊息儲存在群組信箱中一個類似的隱藏資料夾中。</span><span class="sxs-lookup"><span data-stu-id="db5de-118">Data from Yammer user messages is stored in a hidden folder in the mailbox of each user included in the user message, and a similar hidden folder in a group mailbox is used for community messages.</span></span>

<span data-ttu-id="db5de-119">當訊息 @ 提及使用者或通知使用者回覆時，社群訊息的複本也可以儲存在使用者信箱的隱藏資料夾中。</span><span class="sxs-lookup"><span data-stu-id="db5de-119">Copies of community messages can also be stored in the hidden folder of user mailboxes when they @ mention users or notify the user of a reply.</span></span> <span data-ttu-id="db5de-120">雖然這些訊息源自社群訊息，但 Yammer 使用者訊息的保留原則通常會包含社群訊息的複本。</span><span class="sxs-lookup"><span data-stu-id="db5de-120">Although these messages originate as a community message, a retention policy for Yammer user messages will often include copies of community messages.</span></span>

<span data-ttu-id="db5de-121">這些隱藏資料夾不是為使用者或管理員直接存取而設計的，而是儲存合規性系統管理員可以使用電子文件探索工具搜尋的資料。</span><span class="sxs-lookup"><span data-stu-id="db5de-121">These hidden folders are not designed to be directly accessible to users or administrators, but instead, store data that compliance administrators can search with eDiscovery tools.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db5de-122">因為社群訊息的複本也可以儲存在使用者信箱中，具有 Yammer 使用者訊息刪除動作的保留原則可能會導致 Yammer 應用程式中的使用者無法再看到原始的社群訊息。</span><span class="sxs-lookup"><span data-stu-id="db5de-122">Because copies of community messages can also be stored in user mailboxes, a retention policy with a delete action for Yammer user messages can result in the original community message no longer visible to users in the Yammer app.</span></span>
> 
> <span data-ttu-id="db5de-123">不過，在社群群組信箱的隱藏資料夾中仍可使用原始訊息的複本，且可為合規性目的，透過電子文件探索搜尋存取。</span><span class="sxs-lookup"><span data-stu-id="db5de-123">However, a copy of the original message is still available in the hidden folder of the community group mailbox, and accessible with eDiscovery searches for compliance purposes.</span></span>

<span data-ttu-id="db5de-124">Yammer 訊息不受針對 Exchange 信箱設定的保留原則影響。</span><span class="sxs-lookup"><span data-stu-id="db5de-124">Yammer messages are not affected by retention policies that are configured for Exchange mailboxes.</span></span> <span data-ttu-id="db5de-125">儘管 Yammer 訊息會儲存在 Exchange 中，此 Yammer 資料只會由針對 **Yammer 社群訊息** 和 **Yammer 使用者訊息** 位置設定的保留原則包含。</span><span class="sxs-lookup"><span data-stu-id="db5de-125">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer user messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="db5de-126">如果使用者包含在保留 Yammer 資料的作用中保留原則中，且您刪除了包含在此原則中使用者的信箱，若要保留此 Yammer 資料，該信箱會轉換成[非作用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="db5de-126">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="db5de-127">如果您不需要為使用者保留此 Yammer 資料，請在刪除其信箱之前先將該使用者帳戶從保留原則排除。</span><span class="sxs-lookup"><span data-stu-id="db5de-127">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="db5de-128">針對 Yammer 訊息設定保留原則之後，Exchange 服務中的計時器工作就會針對儲存這些 Yammer 訊息所在的隱藏資料夾，定期評估其中項目。</span><span class="sxs-lookup"><span data-stu-id="db5de-128">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="db5de-129">計時器工作最多需要七天的時間來執行。</span><span class="sxs-lookup"><span data-stu-id="db5de-129">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="db5de-130">當這些項目超過其保留期間時，就會移至 SubstrateHolds 資料夾 (進行永久刪除前，每個使用者或群組信箱中用來儲存「虛刪除」項目的隱藏資料夾)。</span><span class="sxs-lookup"><span data-stu-id="db5de-130">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="db5de-131">有鑑於[保留的首要原則](retention.md#the-principles-of-retention-or-what-takes-precedence)，若因為另一個保留原則而必須保留同一個項目，或因為法律或調查理由，而該項目在 eDiscovery 保留之下，則一律會暫停永久刪除。</span><span class="sxs-lookup"><span data-stu-id="db5de-131">Because of the [first principle of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), permanent deletion is always suspended if the same item must be retained because of another retention policy, or it is under eDiscovery holds for legal or investigative reasons.</span></span>

<span data-ttu-id="db5de-132">針對 Yammer 訊息設定保留原則後，內容的路徑會取決於保留原則為保留然後刪除、僅保留或僅刪除。</span><span class="sxs-lookup"><span data-stu-id="db5de-132">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="db5de-133">當保留原則為保留然後刪除時：</span><span class="sxs-lookup"><span data-stu-id="db5de-133">When the retention policy is to retain and then delete:</span></span>

![Yammer 訊息的保留流程圖](../media/yammerretentionlifecycle.png)

<span data-ttu-id="db5de-135">針對圖表中的兩個路徑：</span><span class="sxs-lookup"><span data-stu-id="db5de-135">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="db5de-136">如果在保留期間使用者 **編輯或刪除某個 Yammer 訊息**，系統就立即複製原始訊息 (如果是編輯) 或將其移動 (如果是刪除) 到 SubstrateHolds 資料夾。</span><span class="sxs-lookup"><span data-stu-id="db5de-136">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="db5de-137">訊息會儲存在那裡直到保留期間到期為止，然後永久刪除訊息。</span><span class="sxs-lookup"><span data-stu-id="db5de-137">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="db5de-138">**如果未刪除 Yammer 訊息**，以及目前訊息經過編輯後，則會在保留期間到期後，將訊息移至 SubstrateHolds 資料夾。</span><span class="sxs-lookup"><span data-stu-id="db5de-138">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="db5de-139">此動作從到期日起最多需要七天才會完成。</span><span class="sxs-lookup"><span data-stu-id="db5de-139">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="db5de-140">當訊息位於 SubstrateHolds 資料夾，即會立即永久刪除。</span><span class="sxs-lookup"><span data-stu-id="db5de-140">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="db5de-141">SubstrateHolds 資料夾中的訊息可供電子文件探索工具搜尋。</span><span class="sxs-lookup"><span data-stu-id="db5de-141">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="db5de-142">在訊息遭到永久刪除 (在 [SubstrateHolds] 資料夾中) 前，電子文件探索工具都可以搜尋到這些訊息。</span><span class="sxs-lookup"><span data-stu-id="db5de-142">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="db5de-143">當保留原則為僅保留或僅刪除時，內容路徑為保留和刪除的變化。</span><span class="sxs-lookup"><span data-stu-id="db5de-143">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="db5de-144">「僅保留」保留原則的內容路徑</span><span class="sxs-lookup"><span data-stu-id="db5de-144">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="db5de-145">**如果已編輯或刪除 Yammer 訊息**：系統會立即在 SubstrateHolds 資料夾中建立原始訊息的複本，並保留在該處，直到保留期間到期。</span><span class="sxs-lookup"><span data-stu-id="db5de-145">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="db5de-146">然後訊息會從立即從 SubstrateHolds 資料夾中永久刪除。</span><span class="sxs-lookup"><span data-stu-id="db5de-146">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="db5de-147">**如果未修改或刪除 Yammer 訊息**，以及針對在保留期間經過編輯的目前訊息：保留期間前後不會有任何變化；訊息仍會保留在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="db5de-147">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="db5de-148">僅刪除保留原則的內容路徑</span><span class="sxs-lookup"><span data-stu-id="db5de-148">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="db5de-149">**如果未在保留期間刪除 Yammer 訊息**：在保留期間結束時，系統會將訊息移至 SubstrateHolds 資料夾。</span><span class="sxs-lookup"><span data-stu-id="db5de-149">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="db5de-150">此動作從到期日起最多需要七天才會完成。</span><span class="sxs-lookup"><span data-stu-id="db5de-150">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="db5de-151">然後訊息會從立即從 SubstrateHolds 資料夾中永久刪除。</span><span class="sxs-lookup"><span data-stu-id="db5de-151">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="db5de-152">**如果使用者在保留期間刪除 Yammer 訊息**，系統會立即將該項目移至 SubstrateHolds 資料夾，在其中會立即永久刪除該項目。</span><span class="sxs-lookup"><span data-stu-id="db5de-152">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="db5de-153">訊息和外部使用者</span><span class="sxs-lookup"><span data-stu-id="db5de-153">Messages and external users</span></span>

<span data-ttu-id="db5de-154">根據預設，Yammer 使用者訊息的保留原則會套用至貴組織中的所有使用者，但不會套用至外部使用者。</span><span class="sxs-lookup"><span data-stu-id="db5de-154">By default, a retention policy for Yammer user messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="db5de-155">如果您針對包含的使用者使用 **[編輯]** 選項，則可以將保留原則套用至外部使用者，並指定其帳戶。</span><span class="sxs-lookup"><span data-stu-id="db5de-155">You can apply a retention policy to external users if you use the **Edit** option for users included, and specify their account.</span></span>

<span data-ttu-id="db5de-156">目前不支援 Azure B2B 來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="db5de-156">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="db5de-157">當使用者離開組織時</span><span class="sxs-lookup"><span data-stu-id="db5de-157">When a user leaves the organization</span></span> 

<span data-ttu-id="db5de-158">如果某位使用者離開您的組織，且其 Microsoft 365 帳戶被刪除，則其要保留的 Yammer 使用者訊息會儲存在非作用中的信箱中。</span><span class="sxs-lookup"><span data-stu-id="db5de-158">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer user messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="db5de-159">這些訊息仍受限於在他們的信箱被設成非作用中之前，對使用者設定的任何保留原則，且內容可供電子文件探索搜尋。</span><span class="sxs-lookup"><span data-stu-id="db5de-159">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="db5de-160">如需詳細資訊，請參閱 [Exchange Online 中的非作用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="db5de-160">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="db5de-161">如果使用者將所有檔案儲存在 Yammer 中，請參閱適用於 SharePoint 和 OneDrive 的[同等小節](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。</span><span class="sxs-lookup"><span data-stu-id="db5de-161">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="db5de-162">限制</span><span class="sxs-lookup"><span data-stu-id="db5de-162">Limitations</span></span>

<span data-ttu-id="db5de-163">Yammer 保留原則目前處於預覽，且我們會持續努力將保留功能最佳化。</span><span class="sxs-lookup"><span data-stu-id="db5de-163">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="db5de-164">同時，當您對 Yammer 社群訊息和使用者訊息使用保留時，請注意下列限制：</span><span class="sxs-lookup"><span data-stu-id="db5de-164">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and user messages:</span></span>

- <span data-ttu-id="db5de-165">當您針對 **[Yammer 使用者訊息]** 位置選取 **[編輯]** 時，您可能會看到來賓和非信箱使用者。</span><span class="sxs-lookup"><span data-stu-id="db5de-165">When you select **Edit** for the **Yammer user messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="db5de-166">保留原則並非為這些使用者設計，因此請不要選取他們。</span><span class="sxs-lookup"><span data-stu-id="db5de-166">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="db5de-167">配置指導方針</span><span class="sxs-lookup"><span data-stu-id="db5de-167">Configuration guidance</span></span>

<span data-ttu-id="db5de-168">如果您才剛開始在 Microsoft 365 中進行設定保留，請參閱 [開始使用保留原則及保留標籤](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="db5de-168">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="db5de-169">如果您已準備好為 Yammer 設定保留原則，請參閱[建立及設定保留原則](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="db5de-169">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>