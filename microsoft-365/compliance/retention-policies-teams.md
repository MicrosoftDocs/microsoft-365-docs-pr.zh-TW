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
ms.openlocfilehash: 2541519ad9082383c5381452722d023f23760798
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242709"
---
# <a name="learn-about-retention-for-microsoft-teams"></a><span data-ttu-id="8ebb2-103">了解 Microsoft Teams 的保留</span><span class="sxs-lookup"><span data-stu-id="8ebb2-103">Learn about retention for Microsoft Teams</span></span>

><span data-ttu-id="8ebb2-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="8ebb2-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="8ebb2-105">本文中的資訊可補充 [了解保留原則](retention.md)，因為其包含 Microsoft Teams 訊息專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-105">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Microsoft Teams messages.</span></span>

<span data-ttu-id="8ebb2-106">若為其他工作負載，請參閱：</span><span class="sxs-lookup"><span data-stu-id="8ebb2-106">For other workloads, see:</span></span>

- [<span data-ttu-id="8ebb2-107">了解 SharePoint 和 OneDrive 的保留功能</span><span class="sxs-lookup"><span data-stu-id="8ebb2-107">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="8ebb2-108">了解 Yammer 的保留</span><span class="sxs-lookup"><span data-stu-id="8ebb2-108">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)
- [<span data-ttu-id="8ebb2-109">了解 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="8ebb2-109">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="8ebb2-110">保留與刪除包含的內容</span><span class="sxs-lookup"><span data-stu-id="8ebb2-110">What's included for retention and deletion</span></span>

<span data-ttu-id="8ebb2-111">使用 Teams 保留原則可以保留和删除以下 Teams 項目：聊天訊息和頻道訊息 (包括内嵌影像、表格、超文字連結、指向其他 Teasm 訊息和檔案的連結以及[卡片内容](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards))。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-111">The following Teams items can be retained and deleted by using retention policies for Teams: Chat messages and channel messages, including embedded images, tables, hypertext links and links to other Teams messages and files, and [card content](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards).</span></span> <span data-ttu-id="8ebb2-112">聊天訊息包括聊天中所有人的姓名，頻道訊息包括小組名稱和訊息標題 (如有)。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-112">Chat messages include all the names of the people in the chat, and channel messages include the team name and the message title (if supplied).</span></span> 

> [!NOTE]
> <span data-ttu-id="8ebb2-113">包括卡片內容是最近新增的，目前正在向租用戶推出。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-113">Including card content is a recent addition and currently rolling out to tenants.</span></span> <span data-ttu-id="8ebb2-114">有關更多資訊，請參閱[透過 Teams 中應用程式之針對調適型卡片內容的 Microsoft 365 合規性功能已上線](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869)。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-114">For more information, see [Microsoft 365 compliance capabilities for Adaptive Card content through apps in Teams now available](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869).</span></span>

<span data-ttu-id="8ebb2-115">保留原則目前不支援私人頻道中的 Teams 訊息。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-115">Teams messages in private channels are currently not supported for retention policies.</span></span> <span data-ttu-id="8ebb2-116">當您對 Teams 使用保留原則時，系統不會包含來自 Teams 行動用戶端的程式碼片段、錄製的語音備忘錄，以及來自其他人表情符號形式的反應。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-116">Code snippets, recorded voice memos from the Teams mobile client, and reactions from others in the form of emoticons are not included when you use retention policies for Teams.</span></span>

<span data-ttu-id="8ebb2-117">Teams 保留原則中不包括與 Teams 一起使用的電子郵件和檔案。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-117">Emails and files that you use with Teams aren't included in retention policies for Teams.</span></span> <span data-ttu-id="8ebb2-118">這些項目有各自的保留原則。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-118">These items have their own retention policies.</span></span>

## <a name="how-retention-works-with-microsoft-teams"></a><span data-ttu-id="8ebb2-119">保留如何與 Microsoft Teams 搭配使用</span><span class="sxs-lookup"><span data-stu-id="8ebb2-119">How retention works with Microsoft Teams</span></span>

<span data-ttu-id="8ebb2-120">您可以使用保留原則來保留和刪除 Teams 中的聊天與頻道訊息之資料。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-120">You can use a retention policy to retain and delete data from chats and channel messages in Teams.</span></span> <span data-ttu-id="8ebb2-121">在幕後，會使用 Exchange 信箱來儲存這些訊息。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-121">Behind the scenes, Exchange mailboxes are used to store these messages.</span></span> <span data-ttu-id="8ebb2-122">來自 Teams 聊天的資料會儲存在聊天內包含的每個使用者信箱的隱藏資料夾中，且會將群組信箱中的一個類似的隱藏資料夾用於 Teams 頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-122">Data from Teams chats is stored in a hidden folder in the mailbox of each user included in the chat, and a similar hidden folder in a group mailbox is used for Teams channel messages.</span></span>

<span data-ttu-id="8ebb2-123">這些信箱是依其 RecipientTypeDetails 屬性列出：</span><span class="sxs-lookup"><span data-stu-id="8ebb2-123">These mailboxes are, listed by their RecipientTypeDetails attribute:</span></span>

- <span data-ttu-id="8ebb2-124">**UserMailbox**：這些信箱會儲存擁有 Exchange Online 信箱的 Teams 使用者的訊息。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-124">**UserMailbox**: These mailboxes store messages for Teams users who have an Exchange Online mailbox.</span></span>
- <span data-ttu-id="8ebb2-125">**MailUser**：這些信箱會儲存擁有內部部署 Exchange 伺服器而非 Exchange Online 信箱的 Teams 使用者訊息。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-125">**MailUser**: These mailboxes store messages for Teams users who have a mailbox for an on-premises Exchange server and not Exchange Online.</span></span>
- <span data-ttu-id="8ebb2-126">**使用者**：這些信箱會儲存沒有 Exchange Online 或內部部署 Exchange 伺服器信箱的 Teams 使用者的訊息。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-126">**User**: These mailboxes store messages for Teams users who don’t have a mailbox for Exchange Online or on-premise Exchange servers.</span></span>
- <span data-ttu-id="8ebb2-127">**GroupMailbox**：這些信箱會儲存 Teams 頻道的訊息。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-127">**GroupMailbox**: These mailboxes store messages for Teams channels.</span></span>

<span data-ttu-id="8ebb2-128">Teams 保留原則不支援的其他信箱類型，例如用於 Teams 會議室的 RoomMailbox。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-128">Other mailbox types, such as RoomMailbox that is used for Teams conference rooms, are not supported for Teams retention policies.</span></span>

<span data-ttu-id="8ebb2-129">請務必了解 Teams 使用的聊天服務是由 Azure 所提供，此服務也會儲存 Teams 的資料，且會根據預設永久保存。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-129">It's important to understand that Teams uses an Azure-powered chat service that also stores this data, and by default this service stores the data indefinitely.</span></span> <span data-ttu-id="8ebb2-130">因此，如果您因合規性原因而需要刪除 Teams 訊息，建議您使用能夠永久從 Exchange 信箱和基礎 Azure 提供的交談服務中刪除該資料的 Teams 保留原則。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-130">For this reason, if you need to delete Teams messages for compliance reasons, we recommend that you use retention policies for Teams that can permanently delete this data from both the Exchange mailboxes and the underlying Azure-powered chat service.</span></span> <span data-ttu-id="8ebb2-131">如需詳細資訊，請參閱 [Microsoft Teams 中的安全性與合規性](https://go.microsoft.com/fwlink/?linkid=871258)，特別是[資訊保護架構](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture)一節。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-131">For more information about the underlying architecture, see [Security and compliance in Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258) and specifically, the [Information Protection Architecture](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture) section.</span></span>

<span data-ttu-id="8ebb2-132">儘管 Teams 聊天和頻道訊息會儲存在信箱中，此 Teams 資料只會透過針對 **Teams 頻道訊息** 和 **Teams 聊天** 位置設定的保留原則包含。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-132">Although Teams chats and channel messages are stored in mailboxes, this Teams data is included only by a retention policy that's configured for the **Teams channel messages** and **Teams chats** locations.</span></span> <span data-ttu-id="8ebb2-133">Teams 聊天和頻道訊息不受針對 Exchange 使用者或群組信箱設定的保留原則影響。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-133">Teams chats and channel messages are not affected by retention policies that are configured for Exchange user or group mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="8ebb2-134">如果使用者包含在保留 Teams 資料的作用中保留原則中，且您刪除了包含在此原則中使用者的信箱，若要保留此 Teams 資料，該信箱會轉換成[非作用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-134">If a user is included in an active retention policy that retains Teams data and you a delete a mailbox of a user who is included in this policy, to retain the Teams data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="8ebb2-135">如果您不需要為使用者保留此 Teams 資料，請在刪除其信箱之前先將該使用者帳戶從保留原則排除。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-135">If you don't need to retain this Teams data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="8ebb2-136">將保留原則設定為聊天和頻道訊息之後，Exchange 服務中的計時器工作就會針對儲存這些 Teams 訊息的隱藏資料夾，定期評估其中項目。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-136">After a retention policy is configured for chat and channel messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Teams messages are stored.</span></span> <span data-ttu-id="8ebb2-137">計時器工作最多需要七天的時間來執行。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-137">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="8ebb2-138">當這些項目超過其保留期間時，就會移至 [SubstrateHolds] 資料夾 (進行永久刪除前，每個使用者或群組信箱中用來儲存「虛刪除」項目的另一個隱藏資料夾)。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-138">When these items have expired their retention period, they are moved to the SubstrateHolds folder—another hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

<span data-ttu-id="8ebb2-139">針對聊天和頻道訊息設定保留原則後，內容的路徑會取決於保留原則為保留然後刪除、僅保留或僅刪除。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-139">After a retention policy is configured for chat and channel messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="8ebb2-140">當保留原則為保留然後刪除時：</span><span class="sxs-lookup"><span data-stu-id="8ebb2-140">When the retention policy is to retain and then delete:</span></span>

![Teams 聊天和頻道訊息的保留流程圖](../media/teamsretentionlifecycle.png)

<span data-ttu-id="8ebb2-142">針對圖表中的兩個路徑：</span><span class="sxs-lookup"><span data-stu-id="8ebb2-142">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="8ebb2-143">如果在保留期間有使用者 **編輯或刪除某個聊天或頻道訊息**，系統就會在 21 天内複製原始訊息 (如果是編輯) 或將其移動 (如果是刪除) 到 [SubstrateHolds] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-143">**If a chat or channel message is edited or deleted** by the user during the retention period, the original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder within 21 days.</span></span> <span data-ttu-id="8ebb2-144">訊息會在那裡儲存到保留期間到期為止，然後在 24 小時內永久刪除訊息。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-144">The message is stored there until the retention period expires and then the message is permanently deleted within 24 hours.</span></span>

2. <span data-ttu-id="8ebb2-145">**如果不刪除聊天或頻道訊息**，以及目前訊息經過編輯後，則會在保留期間到期後，將訊息移至 [SubstrateHolds] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-145">**If a chat or channel message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="8ebb2-146">此動作最多可在到期日起 7 天內完成。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-146">This action takes up to 7 days from the expiry date.</span></span> <span data-ttu-id="8ebb2-147">當訊息位於 [SubstrateHolds] 資料夾時，其會在 24 小時內永久刪除。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-147">When the message is in the SubstrateHolds folder, it is then permanently deleted within 24 hours.</span></span> 

> [!NOTE]
> <span data-ttu-id="8ebb2-148">SubstrateHolds 資料夾中的訊息可供電子文件探索工具搜尋。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-148">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="8ebb2-149">在 [SubstrateHolds] 資料夾中訊息遭到永久刪除前，電子文件探索工具都可以搜尋到這些訊息。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-149">Until messages are permanently deleted from this SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="8ebb2-150">當保留原則為僅保留或僅刪除時，內容路徑為保留和刪除的變化。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-150">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="8ebb2-151">「僅保留」保留原則的內容路徑</span><span class="sxs-lookup"><span data-stu-id="8ebb2-151">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="8ebb2-152">**如果聊天或頻道訊息為 [已編輯] 或 [已刪除]**：系統會在 21 天内在 [SubstrateHolds] 資料夾中建立原始訊息的複本，並保留在該處，直到保留期間到期為止。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-152">**If a chat or channel message is edited or deleted**: A copy of the original message is created in the SubstrateHolds folder within 21 days, and retained there until the retention period expires.</span></span> <span data-ttu-id="8ebb2-153">然後訊息會在 24 小時內從 [SubstrateHolds] 資料夾中永久刪除。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-153">Then the message is permanently deleted from the SubstrateHolds folder within 24 hours.</span></span>

2. <span data-ttu-id="8ebb2-154">**如果未在保留期間修改或刪除項目**，以及目前訊息經過編輯後：保留期間前後沒有任何變化；訊息仍會保留在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-154">**If the item is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="8ebb2-155">僅刪除保留原則的內容路徑</span><span class="sxs-lookup"><span data-stu-id="8ebb2-155">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="8ebb2-156">**如果未在保留期間刪除訊息**：在保留期間結束時，系統會將訊息移至 SubstrateHolds 資料夾。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-156">**If the message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="8ebb2-157">此動作最多可在到期日起七天內完成。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-157">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="8ebb2-158">然後訊息會在 24 小時內從 [SubstrateHolds] 資料夾中永久刪除。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-158">Then the message is permanently deleted from the SubstrateHolds folder within 24 hours.</span></span>

2. <span data-ttu-id="8ebb2-159">**如果使用者在保留期間刪除項目**，系統會在 21 天内將項目移至 [SubstrateHolds] 資料夾，並在 24 小時內永久刪除該項目。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-159">**If the item is deleted by the user** during the period, the item is moved to the SubstrateHolds folder within 21 days where it is then permanently deleted within 24 hours.</span></span>


## <a name="skype-for-business-and-teams-interop-chats"></a><span data-ttu-id="8ebb2-160">商務用 Skype 和 Teams Interop 聊天</span><span class="sxs-lookup"><span data-stu-id="8ebb2-160">Skype for Business and Teams interop chats</span></span>

<span data-ttu-id="8ebb2-161">商務用 Skype 聊天併入 Teams 後，會成為 Teams 聊天討論串中的訊息，並送到適當的信箱。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-161">When a Skype for Business chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="8ebb2-162">Teams 保留原則將套用至來自 Teams 討論串的這些訊息。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-162">Teams retention policies will apply to these messages from the Teams thread.</span></span> 

<span data-ttu-id="8ebb2-163">不過，如果商務用 Skype 的聊天歷程記錄已開啟，且商務用 Skype 用戶端將這些歷程記錄儲存到信箱，則 Teams 保留原則不會處理這些聊天資料。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-163">However, if conversation history is turned on for Skype for Business and from the Skype for Business client side that history is being saved into a mailbox, that chat data isn't handled by a Teams retention policy.</span></span> <span data-ttu-id="8ebb2-164">針對此內容，請使用為商務用 Skype 設定的保留原則。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-164">For this content, use a retention policy that's configured for Skype for Business.</span></span>

## <a name="meetings-and-external-users"></a><span data-ttu-id="8ebb2-165">會議和外部使用者</span><span class="sxs-lookup"><span data-stu-id="8ebb2-165">Meetings and external users</span></span>

<span data-ttu-id="8ebb2-166">頻道會議訊息的儲存方式與頻道訊息相同，因此，在您設定保留原則時，請針對此資料選取 [Teams 頻道訊息] 位置。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-166">Channel meeting messages are stored the same way as channel messages, so for this data, select the **Teams channel messages** location when you configure your retention policy.</span></span>

<span data-ttu-id="8ebb2-167">臨時和排程會議訊息的儲存方式與群組聊天相同，因此，在您設定保留原則時，請針對此資料選取 **Teams 聊天** 位置。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-167">Impromptu and scheduled meeting messages are stored in the same way as group chat messages, so for this data, select the **Teams chats** location when you configure your retention policy.</span></span>

<span data-ttu-id="8ebb2-168">在您的組織管理的會議中包含外部使用者時：</span><span class="sxs-lookup"><span data-stu-id="8ebb2-168">When external users are included in a meeting that your organization hosts:</span></span>

- <span data-ttu-id="8ebb2-169">如果外部使用者是使用您的租用戶中的來賓帳戶加入，則受限於您組織的 Teams 保留原則，此使用者會有一個陰影信箱。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-169">If an external user joins by using a guest account in your tenant, this user has a shadow mailbox that can be subject to your organization's retention policy for Teams.</span></span> <span data-ttu-id="8ebb2-170">來自會議的任何訊息都會同時儲存在使用者的信箱和陰影信箱中。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-170">Any messages from the meeting are stored in both your users' mailbox and the shadow mailbox.</span></span> 

- <span data-ttu-id="8ebb2-171">如果外部使用者是使用來自另一個 Microsoft 365 組織的帳戶加入，您的保留原則就無法刪除該使用者的訊息，因為訊息是儲存在該使用者在另一個租用戶的信箱中。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-171">If an external user joins by using an account from another Microsoft 365 organization, your retention policies can't delete messages for this user because they are stored in that user's mailbox in another tenant.</span></span> <span data-ttu-id="8ebb2-172">不過，針對相同會議，您的保留原則可以為您的使用者刪除訊息。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-172">For the same meeting however, your retention policies can delete messages for your users.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="8ebb2-173">當使用者離開組織時</span><span class="sxs-lookup"><span data-stu-id="8ebb2-173">When a user leaves the organization</span></span> 

<span data-ttu-id="8ebb2-174">如果某位具有 Exchange Online 信箱的使用者離開您的組織，且其 Microsoft 365 帳戶被刪除，則其要保留的交談訊息會儲存在非作用中的信箱中。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-174">If a user who has a mailbox in Exchange Online leaves your organization and their Microsoft 365 account is deleted, their chat messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="8ebb2-175">交談訊息在他們的信箱被設成非作用中信箱之前，仍會受置於使用者之任何保留原則的制約，並可供電子文件探索搜尋。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-175">The chat messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="8ebb2-176">如需詳細資訊，請參閱 [Exchange Online 中的非作用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-176">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="8ebb2-177">如果使用者將所有檔案儲存在 Teams 中，請參閱適用于 SharePoint 和 OneDrive 的 [等效節](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-177">If the user stored any files in Teams, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="8ebb2-178">限制</span><span class="sxs-lookup"><span data-stu-id="8ebb2-178">Limitations</span></span>

<span data-ttu-id="8ebb2-179">我們持續努力將 Teams 中的保留功能最佳化。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-179">We're continuously working on optimizing retention functionality in Teams.</span></span> <span data-ttu-id="8ebb2-180">在此同時，當您使用保留 Teams 頻道訊息和交談時，請注意以下幾個限制：</span><span class="sxs-lookup"><span data-stu-id="8ebb2-180">In the meantime, here are a few limitations to be aware of when you use retention for Teams channel messages and chats:</span></span>

- <span data-ttu-id="8ebb2-181">**Outlook 中顯示不正確的問題**。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-181">**Incorrect display issue in Outlook**.</span></span> <span data-ttu-id="8ebb2-182">如果您建立 Skype 或 Teams 位置的保留原則，當使用者在 Outlook 電腦版用戶端中檢視信箱資料夾的內容時，其中一個原則會顯示為預設資料夾原則。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-182">If you create retention policies for Skype or Teams locations, one of those policies is shown as the default folder policy when a user views the properties of a mailbox folder in the Outlook desktop client.</span></span> <span data-ttu-id="8ebb2-183">這是 Outlook 中顯示不正確的問題，並且是[已知問題](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-183">This is an incorrect display issue in Outlook and [a known issue](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies).</span></span> <span data-ttu-id="8ebb2-184">應顯示為預設資料夾原則的是套用至資料夾的信箱保留原則。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-184">What should be displayed as the default folder policy is the mailbox retention policy that's applied to the folder.</span></span> <span data-ttu-id="8ebb2-185">Skype 或 Teams 保留原則不會套用至使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-185">The Skype or Teams retention policy is not applied to the user's mailbox.</span></span>

- <span data-ttu-id="8ebb2-186">**設定問題**：</span><span class="sxs-lookup"><span data-stu-id="8ebb2-186">**Configuration issues**:</span></span> 
    - <span data-ttu-id="8ebb2-187">當您針對 [Teams 頻道訊息] 位置選取 [選擇小組] 時，您可能會看到也不是小組的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-187">When you select **Choose teams** for the **Teams channel messages** location, you might see Microsoft 365 groups that aren't also teams.</span></span> <span data-ttu-id="8ebb2-188">請勿選取這些群組。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-188">Don't select these groups.</span></span>
    
    - <span data-ttu-id="8ebb2-189">當您針對 [Teams 聊天] 位置選取 [選擇使用者] 時，您可能會看到來賓和非信箱使用者。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-189">When you select **Choose users** for the **Teams chats** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="8ebb2-190">保留原則並非為這些使用者設計，因此請不要選取他們。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-190">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="8ebb2-191">配置指導方針</span><span class="sxs-lookup"><span data-stu-id="8ebb2-191">Configuration guidance</span></span>

<span data-ttu-id="8ebb2-192">如果您才剛開始在 Microsoft 365 中進行設定保留，請參閱 [開始使用保留原則及保留標籤](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-192">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="8ebb2-193">如果您已準備好設定 Teams 保留原則，請參閱[建立及設定保留原則](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8ebb2-193">If you're ready to configure a retention policy for Teams, see [Create and configure retention policies](create-retention-policies.md).</span></span>
