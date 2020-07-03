---
title: 了解 Teams 的保留原則
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
description: 了解適用於 Microsoft Teams 的保留原則。
ms.openlocfilehash: 869f457ddb64e5d828dcb5f1244ba779f889e8c9
ms.sourcegitcommit: e3900c818877c2cdcd227917ec975c03e828c7ea
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2020
ms.locfileid: "44861160"
---
# <a name="learn-about-retention-policies-for-microsoft-teams"></a><span data-ttu-id="839e3-103">了解 Microsoft Teams 的保留原則</span><span class="sxs-lookup"><span data-stu-id="839e3-103">Learn about retention policies for Microsoft Teams</span></span>

><span data-ttu-id="839e3-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="839e3-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="839e3-105">本文中的資訊可補充[了解保留原則](retention-policies.md)，因為其包含 Microsoft Teams 專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="839e3-105">The information in this article supplements [Learn about retention policies](retention-policies.md) because it has information that's specific to Microsoft Teams.</span></span>

## <a name="how-a-retention-policy-works-with-microsoft-teams"></a><span data-ttu-id="839e3-106">保留原則如何與 Microsoft Teams 搭配使用</span><span class="sxs-lookup"><span data-stu-id="839e3-106">How a retention policy works with Microsoft Teams</span></span>

<span data-ttu-id="839e3-107">您可以使用保留原則來保留 Teams 中的聊天與頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="839e3-107">You can use a retention policy to retain chats and channel messages in Teams.</span></span> <span data-ttu-id="839e3-108">Teams 聊天會儲存在聊天內每個使用者信箱的隱藏資料夾中，Teams 頻道訊息則會儲存在小組群組信箱中類似的隱藏資料夾內。</span><span class="sxs-lookup"><span data-stu-id="839e3-108">Teams chats are stored in a hidden folder in the mailbox of each user included in the chat, and Teams channel messages are stored in a similar hidden folder in the group mailbox for the team.</span></span> 

<span data-ttu-id="839e3-109">請務必了解 Teams 使用的聊天服務是由 Azure 所提供，此服務也會儲存 Teams 的資料，且會根據預設永久保存。</span><span class="sxs-lookup"><span data-stu-id="839e3-109">It's important to understand that Teams uses an Azure-powered chat service that also stores this data, and by default this service stores the data indefinitely.</span></span> <span data-ttu-id="839e3-110">基於這個原因，我們強烈建議您使用 Teams 位置來保留並刪除 Teams 的資料。</span><span class="sxs-lookup"><span data-stu-id="839e3-110">For this reason, we strongly recommend that you use the Teams locations to retain and delete Teams data.</span></span> <span data-ttu-id="839e3-111">使用 Teams 位置將永久刪除 Exchange 信箱內和基礎 Azure 聊天服務中的資料。</span><span class="sxs-lookup"><span data-stu-id="839e3-111">Using the Teams locations will permanently delete data from both the Exchange mailboxes and the underlying Azure-powered chat service.</span></span> <span data-ttu-id="839e3-112">如需詳細資訊，請參閱 [Microsoft Teams 中的安全性與合規性](https://go.microsoft.com/fwlink/?linkid=871258)，特別是[資訊保護架構](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture)一節。</span><span class="sxs-lookup"><span data-stu-id="839e3-112">For more information, see [Security and compliance in Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258) and specifically, the [Information Protection Architecture](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture) section.</span></span>

<span data-ttu-id="839e3-113">Teams 聊天和頻道訊息不受針對使用者或群組信箱設定的保留原則影響。</span><span class="sxs-lookup"><span data-stu-id="839e3-113">Teams chats and channel messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="839e3-114">儘管 Teams 聊天和頻道訊息會儲存在 Exchange 中，此 Teams 資料只會透過針對 **Teams 頻道訊息**和 **Teams 聊天**位置設定的保留原則包含。</span><span class="sxs-lookup"><span data-stu-id="839e3-114">Even though Teams chats and channel messages are stored in Exchange, this Teams data is included only by a retention policy that's configured for the **Teams channel messages** and **Teams chats** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="839e3-115">如果使用者包含在保留 Teams 資料的作用中保留原則中，且您刪除了包含在此原則中使用者的信箱，若要保留此 Teams 資料，該信箱會轉換成[非作用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="839e3-115">If a user is included in an active retention policy that retains Teams data and you a delete a mailbox of a user who is included in this policy, to retain the Teams data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="839e3-116">如果您不需要為使用者保留此 Teams 資料，請在刪除其信箱之前先將該使用者帳戶從保留原則排除。</span><span class="sxs-lookup"><span data-stu-id="839e3-116">If you don't need to retain this Teams data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="839e3-117">針對聊天和頻道訊息設定保留原則後，內容的路徑會取決於保留原則為保留和刪除、僅保留或僅刪除。</span><span class="sxs-lookup"><span data-stu-id="839e3-117">After a retention policy is configured for chat and channel messages, the paths the content takes depend on whether the retention policy is to retain and delete, to retain only, or delete only.</span></span>

<span data-ttu-id="839e3-118">當保留原則為保留和刪除時：</span><span class="sxs-lookup"><span data-stu-id="839e3-118">When the retention policy is to retain and delete:</span></span>

![Teams 聊天和頻道訊息的保留流程圖](../media/TeamsRetentionLifecycle.png)

1. <span data-ttu-id="839e3-120">如果使用者在保留期間**修改或刪除聊天或頻道訊息**，則會將該訊息移動 (或如果是編輯的情況下，則為複製) 至 SubstrateHolds 資料夾 (這是每個使用者或群組信箱中的隱藏資料夾)，並儲存在此資料夾中，直到保留期間到期為止。</span><span class="sxs-lookup"><span data-stu-id="839e3-120">**If a chat or channel message is modified or deleted** by the user during the retention period, the message is moved (or copied, in the case of edit) to the SubstrateHolds folder (which is a hidden folder in every user or group mailbox) and is stored in this folder until the retention period expires.</span></span> <span data-ttu-id="839e3-121">訊息會在保留期間到期當日永久刪除。</span><span class="sxs-lookup"><span data-stu-id="839e3-121">Messages are permanently deleted on the day the retention period expires.</span></span>

2. <span data-ttu-id="839e3-122">如果在保留期間**未刪除某個聊天或頻道訊息**，則該訊息會在保留期間到期後的一天內 (可能需要 0 到 24 小時的時間) 移至 SubstrateHolds 資料夾。</span><span class="sxs-lookup"><span data-stu-id="839e3-122">**If a chat or channel message isn't deleted** during the retention period, the message is moved to the SubstrateHolds folder within one day after the retention period expires (it takes from 0 to 24 hours).</span></span> <span data-ttu-id="839e3-123">訊息會在移至 SubstrateHolds 資料夾的一天後永久刪除。</span><span class="sxs-lookup"><span data-stu-id="839e3-123">The message is permanently deleted one day after it is moved to the SubstrateHolds folder.</span></span> 

> [!NOTE]
> <span data-ttu-id="839e3-124">SubstrateHolds 資料夾中的訊息可供電子文件探索工具搜尋。</span><span class="sxs-lookup"><span data-stu-id="839e3-124">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="839e3-125">永久刪除某個訊息後，電子文件探索搜尋中就不會傳回該訊息。</span><span class="sxs-lookup"><span data-stu-id="839e3-125">After a message is permanently deleted, it won't be returned in an eDiscovery search.</span></span>

<span data-ttu-id="839e3-126">當保留原則為僅保留或僅刪除時，內容路徑為保留和刪除的變化：</span><span class="sxs-lookup"><span data-stu-id="839e3-126">When the retention policy is retain-only, or delete-only, the contents paths are variations of retain and delete:</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="839e3-127">「僅保留」保留原則的內容路徑</span><span class="sxs-lookup"><span data-stu-id="839e3-127">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="839e3-128">**如果在保留期間修改或刪除項目**：系統會在 SubstrateHolds 資料夾中建立原始訊息的複本，並保留到保留期間結束，然後在該項目到期後的一天永久刪除 SubstrateHolds 資料夾中的該複本。</span><span class="sxs-lookup"><span data-stu-id="839e3-128">**If a chat or channel message is modified or deleted** during the retention period: A copy of the original message is created in the SubstrateHolds folder and retained until the end of the retention period, when the copy in the SubstrateHolds folder is permanently deleted one day after the item expires.</span></span> 

2. <span data-ttu-id="839e3-129">**如果未在保留期間修改或刪除項目**：保留期間前後沒有任何變化；訊息仍會保留在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="839e3-129">**If the item is not modified or deleted** during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

#### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="839e3-130">僅刪除保留原則的內容路徑</span><span class="sxs-lookup"><span data-stu-id="839e3-130">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="839e3-131">**如果未在保留期間刪除訊息**：在保留期間結束時，系統會將訊息移至 SubstrateHolds 資料夾。</span><span class="sxs-lookup"><span data-stu-id="839e3-131">**If the message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> 

2. <span data-ttu-id="839e3-132">**如果使用者在保留期間刪除項目**，系統會立即將項目移至 SubstrateHolds 資料夾。</span><span class="sxs-lookup"><span data-stu-id="839e3-132">**If the item is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="839e3-133">如果使用者從該處刪除訊息或清空 SubstrateHolds 資料夾，就會永久刪除項目。</span><span class="sxs-lookup"><span data-stu-id="839e3-133">If a user deletes the message from there or empties the SubstrateHolds folder, the item is permanently deleted.</span></span> <span data-ttu-id="839e3-134">否則訊息會在處於 SubstrateHolds 資料夾的一天後永久刪除。</span><span class="sxs-lookup"><span data-stu-id="839e3-134">Otherwise, the message is permanently deleted one day after being in the SubstrateHolds folder.</span></span>


## <a name="skype-for-business-and-teams-interop-chats"></a><span data-ttu-id="839e3-135">商務用 Skype 和 Teams Interop 聊天</span><span class="sxs-lookup"><span data-stu-id="839e3-135">Skype for Business and Teams interop chats</span></span>

<span data-ttu-id="839e3-136">商務用 Skype 和 Teams Interop 聊天也是相同的運作流程。</span><span class="sxs-lookup"><span data-stu-id="839e3-136">The same flow works for Skype for Business and Teams interop chats.</span></span> <span data-ttu-id="839e3-137">商務用 Skype 聊天併入 Teams 後，會成為 Teams 聊天討論串中的訊息，並送到適當的信箱。</span><span class="sxs-lookup"><span data-stu-id="839e3-137">When a Skype for Business chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="839e3-138">Teams 保留原則會將這些訊息從 Teams 討論串中刪除。</span><span class="sxs-lookup"><span data-stu-id="839e3-138">Teams retention policies will delete these messages from the Teams thread.</span></span> 

<span data-ttu-id="839e3-139">不過，如果商務用 Skype 的聊天歷程記錄已開啟，且商務用 Skype 用戶端將這些歷程記錄儲存到信箱，則 Teams 保留原則不會處理這些聊天資料。</span><span class="sxs-lookup"><span data-stu-id="839e3-139">However, if conversation history is turned on for Skype for Business and from the Skype for Business client side that history is being saved into a mailbox, that chat data isn't handled by a Teams retention policy.</span></span>

## <a name="files-in-teams"></a><span data-ttu-id="839e3-140">Teams 中的檔案</span><span class="sxs-lookup"><span data-stu-id="839e3-140">Files in Teams</span></span>

<span data-ttu-id="839e3-141">在 Teams 聊天中共用的檔案會儲存在共用檔案之使用者的 OneDrive 帳戶中。</span><span class="sxs-lookup"><span data-stu-id="839e3-141">In Teams, files that are shared in chat are stored in the OneDrive account of the user who shared the file.</span></span> <span data-ttu-id="839e3-142">上傳至頻道的檔案則會儲存在團隊的 SharePoint 網站中。</span><span class="sxs-lookup"><span data-stu-id="839e3-142">Files that are uploaded to channels are stored in the SharePoint site for the team.</span></span> <span data-ttu-id="839e3-143">這表示要若保留或刪除 Teams 中的檔案，除了您為 Teams 所設定的任何保留原則以外，您必須再設定一或多個適用于 OneDrive 和 SharePoint 的保留原則。</span><span class="sxs-lookup"><span data-stu-id="839e3-143">This means that to retain or delete files in Teams, you must configure one or more retention policies that apply to OneDrive and SharePoint in addition to any retention policies you configure for Teams.</span></span> <span data-ttu-id="839e3-144">如需有關保留原則如何適用這些位置的詳細資訊，請參閱[了解 SharePoint 和 OneDrive 的保留原則](retention-policies-sharepoint.md)。</span><span class="sxs-lookup"><span data-stu-id="839e3-144">For more information about how retention policies work for these locations, see [Learn about retention policies for SharePoint and OneDrive](retention-policies-sharepoint.md).</span></span>

> [!NOTE]
> <span data-ttu-id="839e3-145">包含 Teams 頻道訊息或 Teams 聊天的保留原則只能包含 Teams 位置。</span><span class="sxs-lookup"><span data-stu-id="839e3-145">A retention policy that includes Teams channel messages or Teams chats can only include Teams locations.</span></span> <span data-ttu-id="839e3-146">因此，若要在 Teams 中保留或刪除這些檔案，您必須建立個別的保留原則。</span><span class="sxs-lookup"><span data-stu-id="839e3-146">So to retain or delete these files in Teams, you must create a separate retention policy.</span></span>
> 
> <span data-ttu-id="839e3-147">如果想要套用保留原則至某個特定小組的檔案，您可以選擇該小組的 SharePoint 網站，以及該小組中使用者的 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="839e3-147">If you want to apply a retention policy to the files of just a specific team, you can choose the SharePoint site for the Team, and the OneDrive accounts of users in the Team.</span></span>

<span data-ttu-id="839e3-148">套用至 SharePoint 或 OneDrive 的保留原則有可能會刪除 Teams 聊天中參考的檔案，或在頻道訊息刪除前就將其刪除。</span><span class="sxs-lookup"><span data-stu-id="839e3-148">It's possible that a retention policy that's applied to SharePoint or OneDrive could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="839e3-149">在這種情況下，檔案仍會顯示在 Teams 訊息中，但是當使用者按一下檔案時，會收到「找不到檔案」錯誤。</span><span class="sxs-lookup"><span data-stu-id="839e3-149">In this scenario, the file will still show up in the Teams message, but when users click the file, they'll get a "File not found" error.</span></span> <span data-ttu-id="839e3-150">此行為並非保留原則特定，因此也可能在使用者從 SharePoint 或 OneDrive 中手動刪除檔案時發生。</span><span class="sxs-lookup"><span data-stu-id="839e3-150">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

## <a name="meetings-and-external-users"></a><span data-ttu-id="839e3-151">會議和外部使用者</span><span class="sxs-lookup"><span data-stu-id="839e3-151">Meetings and external users</span></span>

<span data-ttu-id="839e3-152">頻道會議訊息的儲存方式與頻道訊息相同，因此，在您設定保留原則時，請針對此資料選取 [Teams 頻道訊息]\*\*\*\* 位置。</span><span class="sxs-lookup"><span data-stu-id="839e3-152">Channel meeting messages are stored the same way as channel messages, so for this data, select the **Teams channel messages** location when you configure your retention policy.</span></span>

<span data-ttu-id="839e3-153">臨時會議訊息的儲存方式與群組聊天相同，因此，在您設定保留原則時，請針對此資料選取 [Teams 聊天]\*\*\*\* 位置。</span><span class="sxs-lookup"><span data-stu-id="839e3-153">Impromptu meeting messages are stored in the same way as group chat messages, so for this data, select the **Teams chats** location when you configure your retention policy.</span></span>

<span data-ttu-id="839e3-154">在您的組織管理的會議中包含外部使用者時：</span><span class="sxs-lookup"><span data-stu-id="839e3-154">When external users are included in a meeting that your organization hosts:</span></span>

- <span data-ttu-id="839e3-155">如果外部使用者是使用您的租用戶中的來賓帳戶加入，則受限於您組織的 Teams 保留原則，此使用者會有一個陰影信箱。</span><span class="sxs-lookup"><span data-stu-id="839e3-155">If an external user joins by using a guest account in your tenant, this user has a shadow mailbox that can be subject to your organization's retention policy for Teams.</span></span> <span data-ttu-id="839e3-156">來自會議的任何訊息都會同時儲存在使用者的信箱和陰影信箱中。</span><span class="sxs-lookup"><span data-stu-id="839e3-156">Any messages from the meeting are stored in both your users' mailbox and the shadow mailbox.</span></span> 

- <span data-ttu-id="839e3-157">如果外部使用者是使用來自另一個 Microsoft 365 組織的帳戶加入，您的保留原則就無法刪除該使用者的訊息，因為訊息是儲存在該使用者在另一個租用戶的信箱中。</span><span class="sxs-lookup"><span data-stu-id="839e3-157">If an external user joins by using an account from another Microsoft 365 organization, your retention policies can't delete messages for this user because they are stored in that user's mailbox in another tenant.</span></span> <span data-ttu-id="839e3-158">不過，針對相同會議，您的保留原則可以為您的使用者刪除訊息。</span><span class="sxs-lookup"><span data-stu-id="839e3-158">For the same meeting however, your retention policies can delete messages for your users.</span></span>


## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="839e3-159">當使用者離開組織時</span><span class="sxs-lookup"><span data-stu-id="839e3-159">When a user leaves the organization</span></span> 

<span data-ttu-id="839e3-160">如果某位使用者離開您的組織，且其 Office 365 帳戶被刪除，則其要保留的交談訊息會儲存在非作用中的信箱中。</span><span class="sxs-lookup"><span data-stu-id="839e3-160">If a user leaves your organization and their Office 365 account is deleted, their chat messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="839e3-161">交談訊息在他們的信箱被設成非作用中信箱之前，仍會受置於使用者之任何保留原則的制約，並可供電子文件探索搜尋。</span><span class="sxs-lookup"><span data-stu-id="839e3-161">The chat messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="839e3-162">如需詳細資訊，請參閱 [Exchange Online 中的非作用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="839e3-162">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="839e3-163">如果使用者將所有檔案儲存在 Teams 中，請參閱適用于 SharePoint 和 OneDrive 的 [等效節](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。</span><span class="sxs-lookup"><span data-stu-id="839e3-163">If the user stored any files in Teams, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="839e3-164">限制</span><span class="sxs-lookup"><span data-stu-id="839e3-164">Limitations</span></span>

<span data-ttu-id="839e3-165">我們持續努力將 Teams 中的保留功能最佳化。</span><span class="sxs-lookup"><span data-stu-id="839e3-165">We're continuously working on optimizing retention functionality in Teams.</span></span> <span data-ttu-id="839e3-166">在此同時，請留意以下所述的一些限制：</span><span class="sxs-lookup"><span data-stu-id="839e3-166">In the meantime, here are a few limitations to be aware of:</span></span>
  
- <span data-ttu-id="839e3-167">**Teams 需要個別的保留原則**。</span><span class="sxs-lookup"><span data-stu-id="839e3-167">**Teams requires a separate retention policy**.</span></span> <span data-ttu-id="839e3-168">當您建立保留原則並將 Teams 位置切換為開啟時，其他所有位置都會切換為關閉。</span><span class="sxs-lookup"><span data-stu-id="839e3-168">When you create a retention policy and toggle on the Teams locations, all other locations toggle off.</span></span> <span data-ttu-id="839e3-169">包含 Teams 的保留原則只能包含 Teams 位置，不可包含其他位置。</span><span class="sxs-lookup"><span data-stu-id="839e3-169">A retention policy that includes Teams can include only Teams and no other locations.</span></span> 
    
- <span data-ttu-id="839e3-170">**Teams 不包含在全組織原則中**。</span><span class="sxs-lookup"><span data-stu-id="839e3-170">**Teams isn't included in an org-wide policy**.</span></span> <span data-ttu-id="839e3-171">如果建立全組織原則，則不會包含 Teams，因為它們需要個別的保留原則。</span><span class="sxs-lookup"><span data-stu-id="839e3-171">If you create an org-wide policy, Teams isn't included because it requires a separate retention policy.</span></span> 
    
- <span data-ttu-id="839e3-172">**Teams 不支援進階保留**。</span><span class="sxs-lookup"><span data-stu-id="839e3-172">**Teams doesn't support advanced retention**.</span></span> <span data-ttu-id="839e3-173">建立保留原則時，如果您選擇 [用來識別符合特定條件內容的進階設定][](create-retention-policies.md#advanced-settings-to-identify-content-that-meets-specific-conditions)，則無法使用 Teams 位置。</span><span class="sxs-lookup"><span data-stu-id="839e3-173">When you create a retention policy, if you choose the [Advanced settings to identify content that meets specific conditions](create-retention-policies.md#advanced-settings-to-identify-content-that-meets-specific-conditions), the Teams locations are not available.</span></span> <span data-ttu-id="839e3-174">目前，當您選取這些位置時，會將 Teams 中的保留套用至所有聊天和頻道訊息內容。</span><span class="sxs-lookup"><span data-stu-id="839e3-174">Currently, retention in Teams applies to all the chat and channel message content when you select those locations.</span></span> 

- <span data-ttu-id="839e3-175">**當您為 Teams 團隊頻道訊息設定保留原則時，不會包含私人頻道的訊息**。</span><span class="sxs-lookup"><span data-stu-id="839e3-175">**Teams messages in private channels aren't included when you configure a retention policy for Teams channel messages**.</span></span> <span data-ttu-id="839e3-176">而是會為使用者將來自私人頻道的訊息包含為群組聊天，其中包含 [Teams 聊天]\*\*\*\* 選項。</span><span class="sxs-lookup"><span data-stu-id="839e3-176">Instead, messages from private channels are included for the users as group chats with the **Teams chats** option.</span></span> 
    
- <span data-ttu-id="839e3-177">**Teams 最多可能需要三天的時間來清理到期的訊息**。</span><span class="sxs-lookup"><span data-stu-id="839e3-177">**Teams may take up to three days to clean up expired messages**.</span></span> <span data-ttu-id="839e3-178">保留期間到期時，套用至 Teams 的保留原則將會刪除聊天和頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="839e3-178">A retention policy applied to Teams will delete chat and channel messages when the retention period expires.</span></span> <span data-ttu-id="839e3-179">不過，要清理並永久刪除這些訊息最多可能需要三天的時間。</span><span class="sxs-lookup"><span data-stu-id="839e3-179">However, it may take up to three days to clean up these messages and permanently delete them.</span></span> <span data-ttu-id="839e3-180">同時，聊天和頻道訊息在保留期間到期後以及當訊息永久刪除時，仍可透過電子文件探索工具進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="839e3-180">Also, chat and channel messages will be searchable with eDiscovery tools during the time after the retention period expires and when messages are permanently deleted.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="839e3-181">過去，保留原則無法刪除少於 30 天的 Teams 內容，我們已移除此限制。</span><span class="sxs-lookup"><span data-stu-id="839e3-181">It used to be true that a retention policy couldn't delete Teams content that's less than 30 days old, but we've removed this limitation.</span></span> <span data-ttu-id="839e3-182">現在 Teams 內容的保留期間，可以是您選擇的任何天數，也可以是一天這麼短的時間。</span><span class="sxs-lookup"><span data-stu-id="839e3-182">Now the retention period for Teams content can be any number of days you choose and as short as one day.</span></span> <span data-ttu-id="839e3-183">如果您確實有一天的保留期間，在保留期間到期後，於永久刪除訊息之前，可能需要最長 3 天的時間。</span><span class="sxs-lookup"><span data-stu-id="839e3-183">If you do have a retention period of one day, it will take up to three days after the retention period expires before messages are permanently deleted.</span></span>

- <span data-ttu-id="839e3-184">**Outlook 中顯示不正確的問題**。</span><span class="sxs-lookup"><span data-stu-id="839e3-184">**Incorrect display issue in Outlook**.</span></span> <span data-ttu-id="839e3-185">如果您建立 Skype 或 Teams 位置的保留原則，當使用者在 Outlook 電腦版用戶端中檢視信箱資料夾的內容時，其中一個原則會顯示為預設資料夾原則。</span><span class="sxs-lookup"><span data-stu-id="839e3-185">If you create retention policies for Skype or Teams locations, one of those policies is shown as the default folder policy when a user views the properties of a mailbox folder in the Outlook desktop client.</span></span> <span data-ttu-id="839e3-186">這是 Outlook 中顯示不正確的問題，並且是[已知問題](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)。</span><span class="sxs-lookup"><span data-stu-id="839e3-186">This is an incorrect display issue in Outlook and [a known issue](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies).</span></span> <span data-ttu-id="839e3-187">應顯示為預設資料夾原則的是套用至資料夾的信箱保留原則。</span><span class="sxs-lookup"><span data-stu-id="839e3-187">What should be displayed as the default folder policy is the mailbox retention policy that's applied to the folder.</span></span> <span data-ttu-id="839e3-188">Skype 或 Teams 保留原則不會套用至使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="839e3-188">The Skype or Teams retention policy is not applied to the user's mailbox.</span></span>

- <span data-ttu-id="839e3-189">**設定問題**：</span><span class="sxs-lookup"><span data-stu-id="839e3-189">**Configuration issues**:</span></span> 
    - <span data-ttu-id="839e3-190">當您針對 [Teams 頻道訊息]\*\*\*\* 位置選取 [選擇小組]\*\*\*\* 時，您可能會看到也不是小組的 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="839e3-190">When you select **Choose teams** for the **Teams channel messages** location, you might see Office 365 groups that aren't also teams.</span></span> <span data-ttu-id="839e3-191">請勿選取這些群組。</span><span class="sxs-lookup"><span data-stu-id="839e3-191">Don't select these groups.</span></span>
    
    - <span data-ttu-id="839e3-192">當您針對 [Teams 聊天]\*\*\*\* 位置選取 [選擇使用者]\*\*\*\* 時，您可能會看到來賓和非信箱使用者。</span><span class="sxs-lookup"><span data-stu-id="839e3-192">When you select **Choose users** for the **Teams chats** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="839e3-193">保留原則並非為這些使用者設計，因此請不要選取他們。</span><span class="sxs-lookup"><span data-stu-id="839e3-193">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="how-to-configure-a-retention-policy-for-microsoft-teams"></a><span data-ttu-id="839e3-194">如何為 Microsoft Teams 設定保留原則</span><span class="sxs-lookup"><span data-stu-id="839e3-194">How to configure a retention policy for Microsoft Teams</span></span>

<span data-ttu-id="839e3-195">按照 [建立及設定保留原則][](create-retention-policies.md) 和 [選擇位置]\*\*\*\* 精靈頁面中的指示進行，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="839e3-195">Follow the instructions for [Create and configure retention policies](create-retention-policies.md) and for the **Choose locations** page of the wizard, select the following options:</span></span>

- <span data-ttu-id="839e3-196">[讓我選擇特定位置]\*\*\*\*  >  [Teams 頻道訊息]\*\*\*\* 和 [Teams 聊天]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="839e3-196">**Let me choose specific locations** > **Teams channel messages** and **Teams chats**</span></span>

<span data-ttu-id="839e3-197">套用至 Teams 的保留原則可能會使用[保留鎖定](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)，這可能為基於法規理由所需。</span><span class="sxs-lookup"><span data-stu-id="839e3-197">A retention policy that applies to Teams can use [Preservation Lock](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements), which might be required for regulatory reasons.</span></span>

## <a name="related-information"></a><span data-ttu-id="839e3-198">相關資訊</span><span class="sxs-lookup"><span data-stu-id="839e3-198">Related information</span></span>

[<span data-ttu-id="839e3-199">Microsoft Teams 中的保留原則</span><span class="sxs-lookup"><span data-stu-id="839e3-199">Retention policies in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/retention-policies)
