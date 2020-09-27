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
ms.openlocfilehash: 2918efe63947ee17cd7f55f19876ae4b98de7a8a
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204325"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="b4762-103">了解 Yammer 的保留</span><span class="sxs-lookup"><span data-stu-id="b4762-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="b4762-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="b4762-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="b4762-105">本文中的資訊可補充[了解保留原則](retention.md)，因為其包含 Yammer 專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="b4762-105">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="b4762-106">Yammer 保留功能的運作方式</span><span class="sxs-lookup"><span data-stu-id="b4762-106">How retention works with Yammer</span></span>

<span data-ttu-id="b4762-107">您可以使用保留原則來保留及刪除 Yammer 中的社群訊息和私人訊息。</span><span class="sxs-lookup"><span data-stu-id="b4762-107">You can use a retention policy to retain and delete community messages and private messages in Yammer.</span></span> <span data-ttu-id="b4762-108">私人訊息會儲存在訊息中包含的每個使用者信箱的隱藏資料夾中，而社群訊息則會儲存在社群群組信箱中的類似隱藏資料夾中。</span><span class="sxs-lookup"><span data-stu-id="b4762-108">Private messages are stored in a hidden folder in the mailbox of each user included in the message, and community messages are stored in a similar hidden folder in the group mailbox for the community.</span></span>

<span data-ttu-id="b4762-109">Yammer 訊息不受針對使用者或群組信箱設定的保留原則影響。</span><span class="sxs-lookup"><span data-stu-id="b4762-109">Yammer messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="b4762-110">儘管 Yammer 訊息會儲存在 Exchange 中，此 Yammer 資料只會由針對 **Yammer 社群訊息**和 **Yammer 私人訊息**位置設定的保留原則包含。</span><span class="sxs-lookup"><span data-stu-id="b4762-110">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer private messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="b4762-111">如果使用者包含在保留 Yammer 資料的作用中保留原則中，且您刪除了包含在此原則中使用者的信箱，若要保留此 Yammer 資料，該信箱會轉換成[非作用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="b4762-111">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="b4762-112">如果您不需要為使用者保留此 Yammer 資料，請在刪除其信箱之前先將該使用者帳戶從保留原則排除。</span><span class="sxs-lookup"><span data-stu-id="b4762-112">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="b4762-113">針對 Yammer 訊息設定保留原則之後，Exchange 服務中的計時器工作就會針對儲存這些 Yammer 訊息所在的隱藏資料夾，定期評估其中項目。</span><span class="sxs-lookup"><span data-stu-id="b4762-113">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="b4762-114">計時器工作最多需要七天的時間來執行。</span><span class="sxs-lookup"><span data-stu-id="b4762-114">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="b4762-115">當這些項目超過其保留期間時，就會移至 SubstrateHolds 資料夾 (進行永久刪除前，每個使用者或群組信箱中用來儲存「虛刪除」項目的隱藏資料夾)。</span><span class="sxs-lookup"><span data-stu-id="b4762-115">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

<span data-ttu-id="b4762-116">針對 Yammer 訊息設定保留原則後，內容的路徑會取決於保留原則為保留然後刪除、僅保留或僅刪除。</span><span class="sxs-lookup"><span data-stu-id="b4762-116">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="b4762-117">當保留原則為保留然後刪除時：</span><span class="sxs-lookup"><span data-stu-id="b4762-117">When the retention policy is to retain and then delete:</span></span>

![Yammer 訊息的保留流程圖](../media/yammerretentionlifecycle.png)

<span data-ttu-id="b4762-119">針對圖表中的兩個路徑：</span><span class="sxs-lookup"><span data-stu-id="b4762-119">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="b4762-120">如果在保留期間使用者**編輯或刪除某個 Yammer 訊息**，系統就立即複製原始訊息 (如果是編輯) 或將其移動 (如果是刪除) 到 SubstrateHolds 資料夾。</span><span class="sxs-lookup"><span data-stu-id="b4762-120">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="b4762-121">訊息會儲存在那裡直到保留期間到期為止，然後永久刪除訊息。</span><span class="sxs-lookup"><span data-stu-id="b4762-121">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="b4762-122">**如果未刪除 Yammer 訊息**，以及目前訊息經過編輯後，則會在保留期間到期後，將訊息移至 SubstrateHolds 資料夾。</span><span class="sxs-lookup"><span data-stu-id="b4762-122">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="b4762-123">此動作從到期日起最多需要七天才會完成。</span><span class="sxs-lookup"><span data-stu-id="b4762-123">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="b4762-124">當訊息位於 SubstrateHolds 資料夾，即會立即永久刪除。</span><span class="sxs-lookup"><span data-stu-id="b4762-124">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="b4762-125">SubstrateHolds 資料夾中的訊息可供電子文件探索工具搜尋。</span><span class="sxs-lookup"><span data-stu-id="b4762-125">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="b4762-126">在訊息遭到永久刪除 (在 [SubstrateHolds] 資料夾中) 前，電子文件探索工具都可以搜尋到這些訊息。</span><span class="sxs-lookup"><span data-stu-id="b4762-126">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="b4762-127">當保留原則為僅保留或僅刪除時，內容路徑為保留和刪除的變化。</span><span class="sxs-lookup"><span data-stu-id="b4762-127">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="b4762-128">「僅保留」保留原則的內容路徑</span><span class="sxs-lookup"><span data-stu-id="b4762-128">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="b4762-129">**如果已編輯或刪除 Yammer 訊息**：系統會立即在 SubstrateHolds 資料夾中建立原始訊息的複本，並保留在該處，直到保留期間到期。</span><span class="sxs-lookup"><span data-stu-id="b4762-129">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="b4762-130">然後訊息會從立即從 SubstrateHolds 資料夾中永久刪除。</span><span class="sxs-lookup"><span data-stu-id="b4762-130">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="b4762-131">**如果未修改或刪除 Yammer 訊息**，以及針對在保留期間經過編輯的目前訊息：保留期間前後不會有任何變化；訊息仍會保留在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="b4762-131">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="b4762-132">僅刪除保留原則的內容路徑</span><span class="sxs-lookup"><span data-stu-id="b4762-132">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="b4762-133">**如果未在保留期間刪除 Yammer 訊息**：在保留期間結束時，系統會將訊息移至 SubstrateHolds 資料夾。</span><span class="sxs-lookup"><span data-stu-id="b4762-133">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="b4762-134">此動作從到期日起最多需要七天才會完成。</span><span class="sxs-lookup"><span data-stu-id="b4762-134">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="b4762-135">然後訊息會從立即從 SubstrateHolds 資料夾中永久刪除。</span><span class="sxs-lookup"><span data-stu-id="b4762-135">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="b4762-136">**如果使用者在保留期間刪除 Yammer 訊息**，系統會立即將該項目移至 SubstrateHolds 資料夾，在其中會立即永久刪除該項目。</span><span class="sxs-lookup"><span data-stu-id="b4762-136">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="b4762-137">訊息和外部使用者</span><span class="sxs-lookup"><span data-stu-id="b4762-137">Messages and external users</span></span>

<span data-ttu-id="b4762-138">根據預設，Yammer 私人訊息的保留原則會套用至組織中的所有使用者，但不會套用至外部使用者。</span><span class="sxs-lookup"><span data-stu-id="b4762-138">By default, a retention policy for Yammer private messages apply to all users in your organization, but not external users.</span></span> <span data-ttu-id="b4762-139">如果您使用 [選擇使用者 **]** 並指定其帳戶，則可以將保留原則套用至外部使用者。</span><span class="sxs-lookup"><span data-stu-id="b4762-139">You can apply a retention policy to external users if you use the **Choose user** and specify their account.</span></span> 

<span data-ttu-id="b4762-140">目前不支援 Azure B2B 來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="b4762-140">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="b4762-141">當使用者離開組織時</span><span class="sxs-lookup"><span data-stu-id="b4762-141">When a user leaves the organization</span></span> 

<span data-ttu-id="b4762-142">如果某位使用者離開您的組織，且其 Microsoft 365 帳戶被刪除，則其要保留的 Yammer 私人訊息會儲存在非作用中的信箱中。</span><span class="sxs-lookup"><span data-stu-id="b4762-142">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer private messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="b4762-143">這些訊息仍受限於在他們的信箱被設成非作用中之前，對使用者設定的任何保留原則，且內容可供電子文件探索搜尋。</span><span class="sxs-lookup"><span data-stu-id="b4762-143">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="b4762-144">如需詳細資訊，請參閱 [Exchange Online 中的非作用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="b4762-144">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="b4762-145">如果使用者將所有檔案儲存在 Yammer 中，請參閱適用於 SharePoint 和 OneDrive 的[同等小節](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。</span><span class="sxs-lookup"><span data-stu-id="b4762-145">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="b4762-146">限制</span><span class="sxs-lookup"><span data-stu-id="b4762-146">Limitations</span></span>

<span data-ttu-id="b4762-147">Yammer 保留原則目前處於預覽，且我們會持續努力將保留功能最佳化。</span><span class="sxs-lookup"><span data-stu-id="b4762-147">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="b4762-148">在此同時，當您對 Yammer 社群訊息和私人訊息使用保留時，請注意以下幾個限制：</span><span class="sxs-lookup"><span data-stu-id="b4762-148">In the meantime, here are a few limitations to be aware of when you use retention for Yammer community messages and private messages:</span></span>

- <span data-ttu-id="b4762-149">**不會保留 Yammer 訊息的讚和其他反應**。</span><span class="sxs-lookup"><span data-stu-id="b4762-149">**Likes and other reactions are not retained for Yammer messages**.</span></span> <span data-ttu-id="b4762-150">保留原則不支援來自其他人表情符號格式的反應。</span><span class="sxs-lookup"><span data-stu-id="b4762-150">Reactions from others in the form of emoticons aren't supported by retention policies.</span></span>

- <span data-ttu-id="b4762-151">當您針對 [Yammer 私人訊息 **]** 位置選取 [選擇使用者 **]** 時，您可能會看到來賓和非信箱使用者。</span><span class="sxs-lookup"><span data-stu-id="b4762-151">When you select **Choose users** for the **Yammer private messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="b4762-152">保留原則並非為這些使用者設計，因此請不要選取他們。</span><span class="sxs-lookup"><span data-stu-id="b4762-152">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="b4762-153">配置指導方針</span><span class="sxs-lookup"><span data-stu-id="b4762-153">Configuration guidance</span></span>

<span data-ttu-id="b4762-154">如果您才剛開始在 Microsoft 365 中進行設定保留，請參閱 [開始使用保留原則及保留標籤](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="b4762-154">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="b4762-155">如果您已準備好為 Yammer 設定保留原則，請參閱[建立及設定保留原則](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b4762-155">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>
