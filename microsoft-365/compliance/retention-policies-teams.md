---
title: 了解 Teams 的保留
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
ms.openlocfilehash: 908c6a1482761815995330b71f0d2d2f96677b64
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908266"
---
# <a name="learn-about-retention-for-microsoft-teams"></a><span data-ttu-id="c4e94-103">了解 Microsoft Teams 的保留</span><span class="sxs-lookup"><span data-stu-id="c4e94-103">Learn about retention for Microsoft Teams</span></span>

><span data-ttu-id="c4e94-104">*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="c4e94-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="c4e94-105">如果您在 Teams 訊息中得知保留原則已刪除聊天或訊息，請參閱 [關於保留原則的 Teams 訊息](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="c4e94-105">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="c4e94-106">本頁面上的資訊適用於管理這些保留原則的 IT 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="c4e94-106">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="c4e94-107">本文中的資訊可補充 [了解保留原則](retention.md)，因為其包含 Microsoft Teams 訊息專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="c4e94-107">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Microsoft Teams messages.</span></span>

<span data-ttu-id="c4e94-108">若為其他工作負載，請參閱：</span><span class="sxs-lookup"><span data-stu-id="c4e94-108">For other workloads, see:</span></span>

- [<span data-ttu-id="c4e94-109">了解 SharePoint 和 OneDrive 的保留功能</span><span class="sxs-lookup"><span data-stu-id="c4e94-109">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="c4e94-110">了解 Yammer 的保留</span><span class="sxs-lookup"><span data-stu-id="c4e94-110">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)
- [<span data-ttu-id="c4e94-111">了解 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="c4e94-111">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="c4e94-112">保留與刪除包含的內容</span><span class="sxs-lookup"><span data-stu-id="c4e94-112">What's included for retention and deletion</span></span>

<span data-ttu-id="c4e94-113">您可以使用 Teams 的保留原則來刪除 Teams 聊天訊息和頻道訊息，而除了郵件中的文字，還可以基於合規性理由保留下列項目：內嵌影像、表格、超文字連結、其他 Teams 訊息和檔案的連結，以及[卡片內容](/microsoftteams/platform/task-modules-and-cards/what-are-cards)。</span><span class="sxs-lookup"><span data-stu-id="c4e94-113">Teams chats messages and channel messages can be deleted by using retention policies for Teams, and in addition to the text in the messages, the following items can be retained for compliance reasons: Embedded images, tables, hypertext links, links to other Teams messages and files, and [card content](/microsoftteams/platform/task-modules-and-cards/what-are-cards).</span></span> <span data-ttu-id="c4e94-114">聊天訊息包括聊天中所有人的姓名，頻道訊息包括小組名稱和訊息標題 (如有)。</span><span class="sxs-lookup"><span data-stu-id="c4e94-114">Chat messages include all the names of the people in the chat, and channel messages include the team name and the message title (if supplied).</span></span> 

<span data-ttu-id="c4e94-p102">保留原則目前不支援私人頻道中的 Teams 訊息。當您對 Teams 使用保留原則，系統不會保留程式碼片段、來自 Teams 行動用戶端的錄製語音備忘錄、縮圖、宣告影像，以及來自其他人表情符號形式的反應。</span><span class="sxs-lookup"><span data-stu-id="c4e94-p102">Teams messages in private channels are currently not supported for retention policies. Code snippets, recorded voice memos from the Teams mobile client, thumbnails, announcement images, and reactions from others in the form of emoticons are not retained when you use retention policies for Teams.</span></span>

<span data-ttu-id="c4e94-p103">Teams 保留原則中不包括與 Teams 一起使用的電子郵件和檔案。這些項目有各自的保留原則。</span><span class="sxs-lookup"><span data-stu-id="c4e94-p103">Emails and files that you use with Teams aren't included in retention policies for Teams. These items have their own retention policies.</span></span>

## <a name="how-retention-works-with-microsoft-teams"></a><span data-ttu-id="c4e94-119">保留如何與 Microsoft Teams 搭配使用</span><span class="sxs-lookup"><span data-stu-id="c4e94-119">How retention works with Microsoft Teams</span></span>

<span data-ttu-id="c4e94-120">使用本節了解後端儲存空間和流程如何滿足您的合規性要求，並且應透過電子文件探索工具而不是 Teams 應用程式中目前可見的郵件進行驗證。</span><span class="sxs-lookup"><span data-stu-id="c4e94-120">Use this section to understand how your compliance requirements are met by backend storage and processes, and should be verified by eDiscovery tools rather than by messages that are currently visible in the Teams app.</span></span>

<span data-ttu-id="c4e94-121">您可以使用保留原則來保留 Teams 中聊天和頻道訊息的資料，並刪除這些聊天和訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-121">You can use a retention policy to retain data from chats and channel messages in Teams, and delete these chats and messages.</span></span> <span data-ttu-id="c4e94-122">在幕後，會使用 Exchange 信箱來儲存複製自這些郵件的資料。</span><span class="sxs-lookup"><span data-stu-id="c4e94-122">Behind the scenes, Exchange mailboxes are used to store data copied from these messages.</span></span> <span data-ttu-id="c4e94-123">來自 Teams 聊天的資料會儲存在聊天內包含的每個使用者信箱的隱藏資料夾中，且會將群組信箱中的一個類似的隱藏資料夾用於 Teams 頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-123">Data from Teams chats is stored in a hidden folder in the mailbox of each user included in the chat, and a similar hidden folder in a group mailbox is used for Teams channel messages.</span></span> <span data-ttu-id="c4e94-124">這些隱藏資料夾不是為使用者或管理員直接存取而設計的，而是儲存合規性系統管理員可以使用電子文件探索工具搜尋的資料。</span><span class="sxs-lookup"><span data-stu-id="c4e94-124">These hidden folders are not designed to be directly accessible to users or administrators, but instead, store data that compliance administrators can search with eDiscovery tools.</span></span>

<span data-ttu-id="c4e94-125">這些信箱是依其 RecipientTypeDetails 屬性列出：</span><span class="sxs-lookup"><span data-stu-id="c4e94-125">These mailboxes are, listed by their RecipientTypeDetails attribute:</span></span>

- <span data-ttu-id="c4e94-126">**UserMailbox**：這些信箱會儲存雲端式 Teams 使用者的郵件資料。</span><span class="sxs-lookup"><span data-stu-id="c4e94-126">**UserMailbox**: These mailboxes store message data for cloud-based Teams users.</span></span>
- <span data-ttu-id="c4e94-127">**MailUser**：這些信箱會儲存 [內部部署 Teams 使用者](search-cloud-based-mailboxes-for-on-premises-users.md)的郵件資料。</span><span class="sxs-lookup"><span data-stu-id="c4e94-127">**MailUser**: These mailboxes store message data for [on-premises Teams users](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>
- <span data-ttu-id="c4e94-128">**GroupMailbox**：這些信箱會儲存 Teams 頻道的訊息資料。</span><span class="sxs-lookup"><span data-stu-id="c4e94-128">**GroupMailbox**: These mailboxes store message data for Teams channels.</span></span>

<span data-ttu-id="c4e94-129">其他信箱類型 (例如用於 Teams 會議室的 RoomMailbox) 不支援使用 Teams 保留原則。</span><span class="sxs-lookup"><span data-stu-id="c4e94-129">Other mailbox types, such as RoomMailbox that is used for Teams conference rooms, are not supported for Teams retention policies.</span></span>

<span data-ttu-id="c4e94-130">Teams 使用 Azure 支援的聊天服務作為其所有訊息 (聊天和頻道訊息) 的主要儲存空間。</span><span class="sxs-lookup"><span data-stu-id="c4e94-130">Teams uses an Azure-powered chat service as its primary storage for all messages (chats and channel messages).</span></span> <span data-ttu-id="c4e94-131">如果您基於合規性理由需要刪除 Teams 訊息，Teams 的保留原則可以在一段特定期間之後，根據訊息建立的時間刪除訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-131">If you need to delete Teams messages for compliance reasons, retention policies for Teams can delete messages after a specified period, based on when they were created.</span></span> <span data-ttu-id="c4e94-132">然後，訊息將從儲存用於合規性作業的 Exchange 信箱和 Azure 支援的基礎聊天服務使用的主要存儲空間中永久删除。</span><span class="sxs-lookup"><span data-stu-id="c4e94-132">Messages are then permanently deleted from both the Exchange mailboxes where they stored for compliance operations, and from the primary storage used by the underlying Azure-powered chat service.</span></span> <span data-ttu-id="c4e94-133">如需基礎架構的詳細資訊，請參閱 [Microsoft Teams 中的安全性與合規性](/MicrosoftTeams/security-compliance-overview)，特別是[資訊保護架構](/MicrosoftTeams/security-compliance-overview#information-protection-architecture)一節。</span><span class="sxs-lookup"><span data-stu-id="c4e94-133">For more information about the underlying architecture, see [Security and compliance in Microsoft Teams](/MicrosoftTeams/security-compliance-overview) and specifically, the [Information Protection Architecture](/MicrosoftTeams/security-compliance-overview#information-protection-architecture) section.</span></span>

<span data-ttu-id="c4e94-134">儘管此來自 Teams 聊天和頻道訊息的資料會儲存在信箱中，您必須為 **Teams 頻道訊息** 和 **Teams 聊天** 位置設定保留原則。</span><span class="sxs-lookup"><span data-stu-id="c4e94-134">Although this data from Teams chats and channel messages are stored in mailboxes, you must configure a retention policy for the **Teams channel messages** and **Teams chats** locations.</span></span> <span data-ttu-id="c4e94-135">Teams 聊天和頻道訊息不包含於針對 Exchange 使用者或群組信箱設定的保留原則。</span><span class="sxs-lookup"><span data-stu-id="c4e94-135">Teams chats and channel messages are not included in retention policies that are configured for Exchange user or group mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="c4e94-136">如果使用者包含在保留 Teams 訊息的作用中保留原則中，且您刪除了包含在此原則中使用者的信箱，該信箱會轉換成[非作用中信箱](inactive-mailboxes-in-office-365.md)，以保留 Teams 資料。</span><span class="sxs-lookup"><span data-stu-id="c4e94-136">If a user is included in an active retention policy that retains Teams messages and you delete a mailbox of a user who is included in this policy, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md) to retain the Teams data.</span></span> <span data-ttu-id="c4e94-137">如果您不需要為使用者保留此 Teams 資料，請在刪除其信箱之前先將該使用者帳戶從保留原則排除。</span><span class="sxs-lookup"><span data-stu-id="c4e94-137">If you don't need to retain this Teams data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="c4e94-138">將保留原則設定為聊天和頻道訊息之後，Exchange 服務中的計時器工作就會針對儲存這些 Teams 訊息的隱藏資料夾，定期評估其中項目。</span><span class="sxs-lookup"><span data-stu-id="c4e94-138">After a retention policy is configured for chat and channel messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Teams messages are stored.</span></span> <span data-ttu-id="c4e94-139">通常需要 1-7 天執行計時器工作。</span><span class="sxs-lookup"><span data-stu-id="c4e94-139">The timer job typically takes 1-7 days to run.</span></span> <span data-ttu-id="c4e94-140">當這些項目超過其保留期間時，就會移至 [SubstrateHolds] 資料夾 (進行永久刪除前，每個使用者或群組信箱中用來儲存「虛刪除」項目的另一個隱藏資料夾)。</span><span class="sxs-lookup"><span data-stu-id="c4e94-140">When these items have expired their retention period, they are moved to the SubstrateHolds folder—another hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span> 

<span data-ttu-id="c4e94-141">訊息在 [SubstrateHolds] 資料夾中至少保留 1 天，如果它們符合删除條件，計時器工作將在下次執行時永久删除它們。</span><span class="sxs-lookup"><span data-stu-id="c4e94-141">Messages remain in the SubstrateHolds folder for at least 1 day, and then if they are eligible for deletion, the timer job permanently deletes them the next time it runs.</span></span>

> [!NOTE]
> <span data-ttu-id="c4e94-142">有鑑於[保留的首要原則](retention.md#the-principles-of-retention-or-what-takes-precedence)，若因為另一個保留原則而必須保留同一個項目，或因為法律或調查理由，而該項目在 eDiscovery 保留之下，則一律會暫停永久刪除。</span><span class="sxs-lookup"><span data-stu-id="c4e94-142">Because of the [first principle of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), permanent deletion is always suspended if the same item must be retained because of another retention policy, or it is under eDiscovery holds for legal or investigative reasons.</span></span>

<span data-ttu-id="c4e94-143">針對聊天和頻道訊息設定保留原則後，內容的路徑會取決於保留原則為保留然後刪除、僅保留或僅刪除。</span><span class="sxs-lookup"><span data-stu-id="c4e94-143">After a retention policy is configured for chat and channel messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="c4e94-144">當保留原則為保留然後刪除時：</span><span class="sxs-lookup"><span data-stu-id="c4e94-144">When the retention policy is to retain and then delete:</span></span>

![Teams 聊天和頻道訊息的保留流程圖](../media/teamsretentionlifecycle.png)

<span data-ttu-id="c4e94-146">針對圖表中的兩個路徑：</span><span class="sxs-lookup"><span data-stu-id="c4e94-146">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="c4e94-147">如果在保留期間有使用者 **編輯或刪除某個聊天或頻道訊息**，系統就會複製原始訊息 (如果是編輯) 或將其移動 (如果是刪除) 到 [SubstrateHolds] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c4e94-147">**If a chat or channel message is edited or deleted** by a user during the retention period, the original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="c4e94-148">郵件在該處至少儲存 1 天。</span><span class="sxs-lookup"><span data-stu-id="c4e94-148">The message is stored there for at least 1 day.</span></span> <span data-ttu-id="c4e94-149">保留到期後，下次執行計時器工作時 (通常在 1-7 天之間) 將永久删除訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-149">When the retention period expires, the message is permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span>

2. <span data-ttu-id="c4e94-150">**如果使用者未刪除聊天或頻道訊息**，以及目前訊息經過編輯後，則會在保留期間到期後，將訊息移至 [SubstrateHolds] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c4e94-150">**If a chat or channel message is not deleted** by a user and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="c4e94-151">此動作通常需要 1-7 天 (從到期日起) 執行。</span><span class="sxs-lookup"><span data-stu-id="c4e94-151">This action typically takes between 1-7 days from the expiry date.</span></span> <span data-ttu-id="c4e94-152">訊息位於 [SubstrateHolds] 資料夾中時，它將在該處存儲至少 1 天，然後在下次執行計時器工作時 (通常在 1-7 天之間) 永久删除該訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-152">When the message is in the SubstrateHolds folder, it is stored there for at least 1 day, and then the message is permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span> 

> [!NOTE]
> <span data-ttu-id="c4e94-153">儲存在信箱中的郵件 (包括隱藏資料夾) 可透過電子文件探索工具進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="c4e94-153">Messages stored in mailboxes, including the hidden folders, are searchable by eDiscovery tools.</span></span> <span data-ttu-id="c4e94-154">在 [SubstrateHolds] 資料夾中訊息遭到永久刪除前，電子文件探索工具都可以搜尋到這些訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-154">Until messages are permanently deleted from the SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="c4e94-155">當訊息從 [SubstrateHolds] 資料夾中被永久删除時，删除動作被傳遞到後端 Azure 聊天服務，然後該服務將相同的動作轉送到 Teams 用戶端應用程式。</span><span class="sxs-lookup"><span data-stu-id="c4e94-155">When messages are permanently deleted from the SubstrateHolds folder, a delete operation is communicated to the backend Azure chat service, that then relays the same operation to the Teams client app.</span></span> <span data-ttu-id="c4e94-156">此通訊或快取的延遲可以解釋在短時間內，使用者可能仍然在其 Teams 應用程式中看到這些訊息，但在電子文件探索搜尋中沒有退回這些訊息中的資料之原因。</span><span class="sxs-lookup"><span data-stu-id="c4e94-156">Delays in this communication or caching can explain why, for a short period of time, users might still see these messages in their Teams app, but data from these messages isn't returned in eDiscovery searches.</span></span> <span data-ttu-id="c4e94-157">在 Teams 應用程式中可見的訊息並不能準確反映它們是被保留還是被永久删除以滿足合規性要求。</span><span class="sxs-lookup"><span data-stu-id="c4e94-157">Messages visible in the Teams app are not an accurate reflection of whether they are retained or permanently deleted for compliance requirements.</span></span>

<span data-ttu-id="c4e94-158">當保留原則為僅保留或僅刪除時，內容路徑為保留和刪除的變化。</span><span class="sxs-lookup"><span data-stu-id="c4e94-158">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="c4e94-159">「僅保留」保留原則的內容路徑</span><span class="sxs-lookup"><span data-stu-id="c4e94-159">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="c4e94-160">如果在保留期間有使用者 **編輯或刪除某個聊天或頻道訊息**，系統就會複製原始訊息 (如果是編輯) 或將其移動 (如果是刪除) 到 [SubstrateHolds] 資料夾，並保留至少 1 天。</span><span class="sxs-lookup"><span data-stu-id="c4e94-160">**If a chat or channel message is edited or deleted** by a user during the retention period: The original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder, and retained there for at least 1 day.</span></span> <span data-ttu-id="c4e94-161">如果保留原則設定為永久保留，則該項將保留在該處。</span><span class="sxs-lookup"><span data-stu-id="c4e94-161">If the retention policy is configured to retain forever, the item remains there.</span></span> <span data-ttu-id="c4e94-162">如果保留原則保留期具有結束日期，並且已過期，則下次執行計時器工作時 (通常在 1-7 天之間) 將永久删除該訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-162">If the retention policy has an end date for the retention period and it expires, the message is permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span>

2. <span data-ttu-id="c4e94-163">**如果使用者未修改或刪除聊天或頻道訊息**，以及針對在保留期間經過編輯的目前訊息：保留期間前後不會有任何變化；訊息仍會保留在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="c4e94-163">**If the chat or channel message is not modified or deleted** by a user and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="c4e94-164">僅刪除保留原則的內容路徑</span><span class="sxs-lookup"><span data-stu-id="c4e94-164">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="c4e94-165">如果在保留期間有使用者 **編輯或刪除某個聊天或頻道訊息**：系統就會複製原始訊息 (如果是編輯) 或將其移動 (如果是刪除) 到 [SubstrateHolds] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c4e94-165">**If the chat or channel message is edited or deleted** by a user during the retention period: The original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="c4e94-166">訊息將在那裡保留至少 1 天，並在下次執行計時器工作永久删除 (通常在 1-7 天之間)。</span><span class="sxs-lookup"><span data-stu-id="c4e94-166">The message is retained there for at least 1 day and permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span>

2. <span data-ttu-id="c4e94-167">**如果使用者未在保留期間刪除聊天或頻道訊息**：在保留期間結束時，系統會將訊息移至 SubstrateHolds 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c4e94-167">**If a chat or channel message is not deleted** by a user during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="c4e94-168">此動作通常需要 1-7 天 (從到期日起) 執行。</span><span class="sxs-lookup"><span data-stu-id="c4e94-168">This action typically takes between 1-7 days from the expiry date.</span></span> <span data-ttu-id="c4e94-169">訊息將在該處保留至少 1 天，並在下次執行計時器工作永久删除 (通常在 1-7 天之間)。</span><span class="sxs-lookup"><span data-stu-id="c4e94-169">The message is retained there for at least 1 day and then permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span>

#### <a name="example-flows-and-timings-for-retention-policies"></a><span data-ttu-id="c4e94-170">保留原則的流程和計時範例</span><span class="sxs-lookup"><span data-stu-id="c4e94-170">Example flows and timings for retention policies</span></span>

<span data-ttu-id="c4e94-171">使用以下範例可以了解上一節中介紹的流程和計時如何套用於具有以下設定的保留原則：</span><span class="sxs-lookup"><span data-stu-id="c4e94-171">Use the following examples to see how the processes and timings explained in the previous sections apply to retention policies that have the following configurations:</span></span>

- [<span data-ttu-id="c4e94-172">範例 1：只保留 7 年</span><span class="sxs-lookup"><span data-stu-id="c4e94-172">Example 1: Retain-only for 7 years</span></span>](#example-1-retain-only-for-7-years)
- [<span data-ttu-id="c4e94-173">範例 2：保留 30 天，然後删除</span><span class="sxs-lookup"><span data-stu-id="c4e94-173">Example 2: Retain for 30 days and then delete</span></span>](#example-2-retain-for-30-days-and-then-delete)
- [<span data-ttu-id="c4e94-174">範例 3：僅在 1 天后删除</span><span class="sxs-lookup"><span data-stu-id="c4e94-174">Example 3: Delete-only after 1 day</span></span>](#example-3-delete-only-after-1-day)

<span data-ttu-id="c4e94-175">對於所有涉及永久删除的範例，根據[保留原則](retention.md#the-principles-of-retention-or-what-takes-precedence)，如果郵件受另一個保留原則的約束以保留該項目，或者受電子文件探索保留的約束，則此動作將暫止。</span><span class="sxs-lookup"><span data-stu-id="c4e94-175">For all examples that refer to permanent deletion, because of the [principles of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), this action is suspended if the message is subject to another retention policy to retain the item or it is subject to an eDiscovery hold.</span></span>

##### <a name="example-1-retain-only-for-7-years"></a><span data-ttu-id="c4e94-176">範例 1：只保留 7 年</span><span class="sxs-lookup"><span data-stu-id="c4e94-176">Example 1: Retain-only for 7 years</span></span>

<span data-ttu-id="c4e94-177">在第 1 天，使用者建立一個聊天或頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-177">On day 1, a user creates a chat or channel message.</span></span>

<span data-ttu-id="c4e94-178">在第 5 天，使用者編輯該訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-178">On day 5, the user edits that message.</span></span>

<span data-ttu-id="c4e94-179">在第 30 天，使用者删除目前訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-179">On day 30, the user deletes the current message.</span></span>

<span data-ttu-id="c4e94-180">保留結果：</span><span class="sxs-lookup"><span data-stu-id="c4e94-180">Retention outcomes:</span></span>

- <span data-ttu-id="c4e94-181">對於原始訊息：</span><span class="sxs-lookup"><span data-stu-id="c4e94-181">For the original message:</span></span>
    - <span data-ttu-id="c4e94-182">在第 5 天，將複製訊息至 [SubstrateHolds] 資料夾，在該資料夾中，從第 1 天 (保留期) 起至少 7 年內仍可使用電子文件探索工具對其進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="c4e94-182">On day 5, the message is copied to the SubstrateHolds folder where it can still be searched with eDiscovery tools for a minimum of 7 years from day 1 (the retention period).</span></span>

- <span data-ttu-id="c4e94-183">對於目前 (已編輯) 訊息：</span><span class="sxs-lookup"><span data-stu-id="c4e94-183">For the current (edited) message:</span></span>
    - <span data-ttu-id="c4e94-184">在第 30 天，訊息將移動至 [SubstrateHolds] 資料夾，在該資料夾中，從第 1 天 (保留期) 起至少 7 年內仍可使用電子文件探索工具對其進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="c4e94-184">On day 30, the message moves to the SubstrateHolds folder where it can still be searched with eDiscovery tools for a minimum of 7 years from day 1 (the retention period).</span></span>

<span data-ttu-id="c4e94-185">如果使用者在指定保留期之後 (而不是在保留期內) 删除了目前訊息，則訊息仍將被移動到 [SubstrateHolds] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c4e94-185">If the user had deleted the current message after the specified retention period, instead of within the retention period, the message would still be moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="c4e94-186">但是，現在保留期已過，訊息將在至少 1 天后 (通常在 1-7 天內) 被永久删除。</span><span class="sxs-lookup"><span data-stu-id="c4e94-186">However, now the retention period has expired, the message would be permanently deleted after the minimum of 1 day and then typically within 1-7 days.</span></span>

##### <a name="example-2-retain-for-30-days-and-then-delete"></a><span data-ttu-id="c4e94-187">範例 2：保留 30 天，然後删除</span><span class="sxs-lookup"><span data-stu-id="c4e94-187">Example 2: Retain for 30 days and then delete</span></span>

<span data-ttu-id="c4e94-188">在第 1 天，使用者建立一個聊天或頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-188">On day 1, a user creates a chat or channel message.</span></span>

<span data-ttu-id="c4e94-189">在第 10 天，使用者編輯該訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-189">On day 10, the user edits that message.</span></span>

<span data-ttu-id="c4e94-190">使用者不進行進一步編輯，也不删除訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-190">The user doesn't make further edits and doesn't delete the message.</span></span>

<span data-ttu-id="c4e94-191">保留結果：</span><span class="sxs-lookup"><span data-stu-id="c4e94-191">Retention outcomes:</span></span>

- <span data-ttu-id="c4e94-192">對於原始訊息：</span><span class="sxs-lookup"><span data-stu-id="c4e94-192">For the original message:</span></span>
    - <span data-ttu-id="c4e94-193">在第 10 天，將複製訊息至 [SubstrateHolds] 資料夾，在該資料夾中仍可使用電子文件探索工具對其進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="c4e94-193">On day 10, the message is copied to the SubstrateHolds folder, where it can still be searched with eDiscovery tools.</span></span>
    - <span data-ttu-id="c4e94-194">在保留期結束時 (第 1 天算起的第 30 天)，訊息通常會在 1 天后 (通常 1-7 天内) 被永久删除，然後不會隨電子文件探索搜尋一起退回。</span><span class="sxs-lookup"><span data-stu-id="c4e94-194">At the end of the retention period (30 days from day 1), the message is permanently deleted typically within 1-7 days after the minimum of 1 day, and then won't be returned with eDiscovery searches.</span></span>

- <span data-ttu-id="c4e94-195">對於目前 (已編輯) 訊息：</span><span class="sxs-lookup"><span data-stu-id="c4e94-195">For the current (edited) message:</span></span>
    - <span data-ttu-id="c4e94-196">在保留期結束時 (從第 1 天算起的第 30 天)，訊息通常在 1-7 天內移動到 [SubstrateHolds] 資料夾，在該處仍然可以使用電子文件探索工具進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="c4e94-196">At the end of the retention period (30 days from day 1), the message moves to the SubstrateHolds folder typically within 1-7 days, where it can still be searched with eDiscovery tools.</span></span>
    - <span data-ttu-id="c4e94-197">然後訊息通常會在 1 天后 (通常 1-7 天内) 被永久删除，然後不會隨電子文件探索搜尋一起退回。</span><span class="sxs-lookup"><span data-stu-id="c4e94-197">The message is then permanently deleted typically within 1-7 days after the minimum of 1 day, and then won't be returned with eDiscovery searches.</span></span>

##### <a name="example-3-delete-only-after-1-day"></a><span data-ttu-id="c4e94-198">範例 3：僅在 1 天后刪除</span><span class="sxs-lookup"><span data-stu-id="c4e94-198">Example 3: Delete-only after 1 day</span></span>

> [!NOTE]
> <span data-ttu-id="c4e94-199">由於此設定和保留流程僅持續短短一天的時間，在 1-7 天的時間段內執行，因此本節顯示了一般時間範圍內的範例計時。</span><span class="sxs-lookup"><span data-stu-id="c4e94-199">Because of the short one-day duration of this configuration and retention processes that operate within a time period of 1-7 days, this section shows example timings that are within the typical time ranges.</span></span>

<span data-ttu-id="c4e94-200">在第 1 天，使用者建立一個聊天或頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-200">On day 1, a user creates a chat or channel message.</span></span>

<span data-ttu-id="c4e94-201">如果使用者不編輯或删除訊息，則保留結果範例：</span><span class="sxs-lookup"><span data-stu-id="c4e94-201">Example retention outcome if the user doesn't edit or delete the message:</span></span>

- <span data-ttu-id="c4e94-202">第 5 天 (通常在第 2 天保留期開始後 1-7 天)：</span><span class="sxs-lookup"><span data-stu-id="c4e94-202">Day 5 (typically 1-7 days after the start of the retention period on day 2):</span></span>
    - <span data-ttu-id="c4e94-203">訊息將移動至 [SubstrateHolds] 資料夾，並在該資料夾中保留至少 1 天，在該資料夾中仍可使用電子文件探索工具進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="c4e94-203">The message moves to the SubstrateHolds folder and remains there for at least 1 day where it can still be searched with eDiscovery tools.</span></span>

- <span data-ttu-id="c4e94-204">第 9 天 (通常在 [SubstrateHolds] 資料夾中至少 1 天后算起的 1-7 天)：</span><span class="sxs-lookup"><span data-stu-id="c4e94-204">Day 9 (typically 1-7 days after a minimum of 1 day in the SubstrateHolds folder):</span></span>
    - <span data-ttu-id="c4e94-205">訊息將被永久删除，然後將不會隨電子文件探索搜尋退回。</span><span class="sxs-lookup"><span data-stu-id="c4e94-205">The message is permanently deleted and then won't be returned with eDiscovery searches.</span></span>

<span data-ttu-id="c4e94-206">如本例所示，儘管您可以將保留原則設定為僅在一天之後删除訊息，但該服務將經歷多個流程以確保合規的删除。</span><span class="sxs-lookup"><span data-stu-id="c4e94-206">As this example shows, although you can configure a retention policy to delete messages after just one day, the service undergoes multiple processes to ensure a compliant deletion.</span></span> <span data-ttu-id="c4e94-207">因此，1 天後執行的删除動作可能需要 16 天才能永久删除訊息，以便在電子文件探索搜尋中不再退回該訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-207">As a result, a delete action after 1 day could take 16 days before the message is permanently deleted so that it's no longer returned in eDiscovery searches.</span></span>

## <a name="skype-for-business-and-teams-interop-chats"></a><span data-ttu-id="c4e94-208">商務用 Skype 和 Teams Interop 聊天</span><span class="sxs-lookup"><span data-stu-id="c4e94-208">Skype for Business and Teams interop chats</span></span>

<span data-ttu-id="c4e94-209">商務用 Skype 聊天併入 Teams 後，會成為 Teams 聊天討論串中的訊息，並送到適當的信箱。</span><span class="sxs-lookup"><span data-stu-id="c4e94-209">When a Skype for Business chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="c4e94-210">Teams 保留原則將套用至來自 Teams 討論串的這些訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-210">Teams retention policies will apply to these messages from the Teams thread.</span></span> 

<span data-ttu-id="c4e94-p119">不過，如果商務用 Skype 的聊天歷程記錄已開啟，且商務用 Skype 用戶端將這些歷程記錄儲存到信箱，則 Teams 保留原則不會處理這些聊天資料。針對此內容，請使用為商務用 Skype 設定的保留原則。</span><span class="sxs-lookup"><span data-stu-id="c4e94-p119">However, if conversation history is turned on for Skype for Business and from the Skype for Business client side that history is being saved into a mailbox, that chat data isn't handled by a Teams retention policy. For this content, use a retention policy that's configured for Skype for Business.</span></span>

## <a name="meetings-and-external-users"></a><span data-ttu-id="c4e94-213">會議和外部使用者</span><span class="sxs-lookup"><span data-stu-id="c4e94-213">Meetings and external users</span></span>

<span data-ttu-id="c4e94-214">頻道會議訊息的儲存方式與頻道訊息相同，因此，在您設定保留原則時，請針對此資料選取 [Teams 頻道訊息] 位置。</span><span class="sxs-lookup"><span data-stu-id="c4e94-214">Channel meeting messages are stored the same way as channel messages, so for this data, select the **Teams channel messages** location when you configure your retention policy.</span></span>

<span data-ttu-id="c4e94-215">臨時和排程會議訊息的儲存方式與群組聊天相同，因此，在您設定保留原則時，請針對此資料選取 **Teams 聊天** 位置。</span><span class="sxs-lookup"><span data-stu-id="c4e94-215">Impromptu and scheduled meeting messages are stored in the same way as group chat messages, so for this data, select the **Teams chats** location when you configure your retention policy.</span></span>

<span data-ttu-id="c4e94-216">在您的組織管理的會議中包含外部使用者時：</span><span class="sxs-lookup"><span data-stu-id="c4e94-216">When external users are included in a meeting that your organization hosts:</span></span>

- <span data-ttu-id="c4e94-217">如果外部使用者是使用您的租用戶中的來賓帳戶加入，則受限於您組織的 Teams 保留原則，此使用者會有一個陰影信箱。</span><span class="sxs-lookup"><span data-stu-id="c4e94-217">If an external user joins by using a guest account in your tenant, this user has a shadow mailbox that can be subject to your organization's retention policy for Teams.</span></span> <span data-ttu-id="c4e94-218">來自會議的任何訊息都會同時儲存在使用者的信箱和陰影信箱中。</span><span class="sxs-lookup"><span data-stu-id="c4e94-218">Any messages from the meeting are stored in both your users' mailbox and the shadow mailbox.</span></span> 

- <span data-ttu-id="c4e94-p121">如果外部使用者是使用來自另一個 Microsoft 365 組織的帳戶加入，您的保留原則就無法刪除該使用者的訊息，因為訊息是儲存在該使用者在另一個租用戶的信箱中。不過，針對相同會議，您的保留原則可以為您的使用者刪除訊息。</span><span class="sxs-lookup"><span data-stu-id="c4e94-p121">If an external user joins by using an account from another Microsoft 365 organization, your retention policies can't delete messages for this user because they are stored in that user's mailbox in another tenant. For the same meeting however, your retention policies can delete messages for your users.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="c4e94-221">當使用者離開組織時</span><span class="sxs-lookup"><span data-stu-id="c4e94-221">When a user leaves the organization</span></span> 

<span data-ttu-id="c4e94-222">如果某位具有 Exchange Online 信箱的使用者離開您的組織，且其 Microsoft 365 帳戶被刪除，則其要保留的交談訊息會儲存在非作用中的信箱中。</span><span class="sxs-lookup"><span data-stu-id="c4e94-222">If a user who has a mailbox in Exchange Online leaves your organization and their Microsoft 365 account is deleted, their chat messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="c4e94-223">交談訊息在他們的信箱被設成非作用中信箱之前，仍會受置於使用者之任何保留原則的制約，並可供電子文件探索搜尋。</span><span class="sxs-lookup"><span data-stu-id="c4e94-223">The chat messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="c4e94-224">如需詳細資訊，請參閱 [Exchange Online 中的非作用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="c4e94-224">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="c4e94-225">如果使用者將所有檔案儲存在 Teams 中，請參閱適用于 SharePoint 和 OneDrive 的 [等效節](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。</span><span class="sxs-lookup"><span data-stu-id="c4e94-225">If the user stored any files in Teams, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="c4e94-226">限制</span><span class="sxs-lookup"><span data-stu-id="c4e94-226">Limitations</span></span>

<span data-ttu-id="c4e94-p123">我們持續努力最佳化 Teams 中的保留功能。同時，在對 Teams 頻道訊息和聊天使用保留原則時，請注意以下限制：</span><span class="sxs-lookup"><span data-stu-id="c4e94-p123">We're continuously working on optimizing retention functionality in Teams. In the meantime, be aware of the following limitation when you use retention policies for Teams channel messages and chats:</span></span>

- <span data-ttu-id="c4e94-229">**Outlook 中顯示不正確的問題**。</span><span class="sxs-lookup"><span data-stu-id="c4e94-229">**Incorrect display issue in Outlook**.</span></span> <span data-ttu-id="c4e94-230">如果您建立 Skype 或 Teams 位置的保留原則，當使用者在 Outlook 電腦版用戶端中檢視信箱資料夾的內容時，其中一個原則會顯示為預設資料夾原則。</span><span class="sxs-lookup"><span data-stu-id="c4e94-230">If you create retention policies for Skype or Teams locations, one of those policies is shown as the default folder policy when a user views the properties of a mailbox folder in the Outlook desktop client.</span></span> <span data-ttu-id="c4e94-231">這是 Outlook 中顯示不正確的問題，並且是[已知問題](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)。</span><span class="sxs-lookup"><span data-stu-id="c4e94-231">This is an incorrect display issue in Outlook and [a known issue](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies).</span></span> <span data-ttu-id="c4e94-232">相反，您應能看到套用至該資料夾的信箱保留原則。</span><span class="sxs-lookup"><span data-stu-id="c4e94-232">Instead, you should see the mailbox retention policy that's applied to the folder.</span></span> <span data-ttu-id="c4e94-233">Skype 或 Teams 保留原則不會套用至使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="c4e94-233">The Skype or Teams retention policy is not applied to the user's mailbox.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="c4e94-234">配置指導方針</span><span class="sxs-lookup"><span data-stu-id="c4e94-234">Configuration guidance</span></span>

<span data-ttu-id="c4e94-235">如果您才剛開始在 Microsoft 365 中進行設定保留，請參閱 [開始使用保留原則及保留標籤](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="c4e94-235">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="c4e94-236">如果您已準備好設定 Teams 保留原則，請參閱[建立及設定保留原則](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c4e94-236">If you're ready to configure a retention policy for Teams, see [Create and configure retention policies](create-retention-policies.md).</span></span>