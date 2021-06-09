---
title: 資料外洩防護和 Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft Teams 聊天和頻道支援資料遺失防護 (DLP) 原則。
ms.openlocfilehash: fa7e0967e24d8fa5e64b84fbccf54ff8cf45d1d6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843539"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="1ab05-103">資料外洩防護和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ab05-103">Data loss prevention and Microsoft Teams</span></span>

<span data-ttu-id="1ab05-104">如果您的組織有資料遺失防護 (DLP) ，您可以定義原則，以防止人員在 Microsoft Teams 通道或聊天會話中共用機密資訊。</span><span class="sxs-lookup"><span data-stu-id="1ab05-104">If your organization has data loss prevention (DLP), you can define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="1ab05-105">以下是此保護運作方式的一些範例：</span><span class="sxs-lookup"><span data-stu-id="1ab05-105">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="1ab05-106">**範例1：保護郵件中的機密資訊**。</span><span class="sxs-lookup"><span data-stu-id="1ab05-106">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="1ab05-107">假設有人嘗試在 Teams 聊天室或頻道中共用機密資訊， (外部使用者) 的來賓。</span><span class="sxs-lookup"><span data-stu-id="1ab05-107">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="1ab05-108">如果您已定義 DLP 原則以避免發生這種情況，就會刪除郵件，其中包含傳送給外部使用者的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="1ab05-108">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="1ab05-109">這會根據您設定 DLP 原則的方式，自動進行，並在幾秒內進行。</span><span class="sxs-lookup"><span data-stu-id="1ab05-109">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1ab05-110">當與擁有下列專案的 Microsoft Teams 使用者共用時，Microsoft Teams 會封鎖機密內容的 DLP。</span><span class="sxs-lookup"><span data-stu-id="1ab05-110">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="1ab05-111">- 小組和頻道中的[來賓存取權](/MicrosoftTeams/guest-access);或</span><span class="sxs-lookup"><span data-stu-id="1ab05-111">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="1ab05-112">- 會議和聊天會話中的[外部存取](/MicrosoftTeams/manage-external-access)。</span><span class="sxs-lookup"><span data-stu-id="1ab05-112">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="1ab05-113">只有當寄件者和收件者都在僅 Teams 模式中，且使用[Microsoft Teams 原生同盟](/microsoftteams/manage-external-access)時，才能使用 DLP。</span><span class="sxs-lookup"><span data-stu-id="1ab05-113">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="1ab05-114">DLP for Teams 不會封鎖使用商務用 Skype 或非原生同盟聊天會話之[interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)的郵件。</span><span class="sxs-lookup"><span data-stu-id="1ab05-114">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="1ab05-115">**範例2：保護檔中的機密資訊**。</span><span class="sxs-lookup"><span data-stu-id="1ab05-115">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="1ab05-116">假設有人嘗試與 Microsoft Teams 通道或聊天中的客人共用檔，而且檔中包含機密資訊。</span><span class="sxs-lookup"><span data-stu-id="1ab05-116">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="1ab05-117">如果您定義了 DLP 原則以避免發生這種情況，則不會對這些使用者開啟檔。</span><span class="sxs-lookup"><span data-stu-id="1ab05-117">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="1ab05-118">DLP 原則必須包括 SharePoint 和 OneDrive，才能隨時提供保護。</span><span class="sxs-lookup"><span data-stu-id="1ab05-118">Your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="1ab05-119">這是 SharePoint 的 DLP 範例，會顯示在 Microsoft Teams 中，因此要求使用者已取得 Office 365 的 dlp (的授權，包含在 Office 365 E3) 中，但不需要使用者授權 Office 365 進階合規性。 ) </span><span class="sxs-lookup"><span data-stu-id="1ab05-119">This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="dlp-licensing-for-microsoft-teams"></a><span data-ttu-id="1ab05-120">Microsoft Teams 的 DLP 授權</span><span class="sxs-lookup"><span data-stu-id="1ab05-120">DLP Licensing for Microsoft Teams</span></span>

<span data-ttu-id="1ab05-121">[資料遺失防護](dlp-learn-about-dlp.md)功能已擴充，可納入 Microsoft Teams 聊天及通道訊息，包括下列專案的 **私人通道訊息**：</span><span class="sxs-lookup"><span data-stu-id="1ab05-121">[Data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages** for:</span></span>

- <span data-ttu-id="1ab05-122">Office 365E5/A5</span><span class="sxs-lookup"><span data-stu-id="1ab05-122">Office 365 E5/A5</span></span>
- <span data-ttu-id="1ab05-123">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="1ab05-123">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="1ab05-124">Microsoft 365資訊保護和控管</span><span class="sxs-lookup"><span data-stu-id="1ab05-124">Microsoft 365 Information Protection and Governance</span></span>
- <span data-ttu-id="1ab05-125">Office 365 進階合規性</span><span class="sxs-lookup"><span data-stu-id="1ab05-125">Office 365 Advanced Compliance</span></span>

<span data-ttu-id="1ab05-126">Office 365 和 Microsoft 365 E3 包含 SharePoint 線上、OneDrive 及 Exchange Online 的 DLP 保護。</span><span class="sxs-lookup"><span data-stu-id="1ab05-126">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="1ab05-127">這也包括透過 Teams 共用的檔案，因為 Teams 使用 SharePoint 線上及 OneDrive 來共用檔案。</span><span class="sxs-lookup"><span data-stu-id="1ab05-127">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>

<span data-ttu-id="1ab05-128">支援 Teams 聊天中的 DLP 保護需要 E5。</span><span class="sxs-lookup"><span data-stu-id="1ab05-128">Support for DLP protection in Teams Chat requires E5.</span></span>

<span data-ttu-id="1ab05-129">若要深入了解授權需求，請參閱 [Microsoft 365 租用戶層級服務授權指導方針](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span><span class="sxs-lookup"><span data-stu-id="1ab05-129">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ab05-130">DLP 只適用于聊天或通道執行緒中的實際郵件。</span><span class="sxs-lookup"><span data-stu-id="1ab05-130">DLP applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="1ab05-131">活動通知--其中包括簡短的訊息預覽，而且會根據使用者的通知設定出現--**不** 會包含在 Teams DLP 中。</span><span class="sxs-lookup"><span data-stu-id="1ab05-131">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP.</span></span> <span data-ttu-id="1ab05-132">預覽中出現的郵件部分中的任何敏感資訊，即使已套用 DLP 原則並移除郵件本身的機密資訊之後，也會在通知中看到。</span><span class="sxs-lookup"><span data-stu-id="1ab05-132">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

## <a name="scope-of-dlp-protection"></a><span data-ttu-id="1ab05-133">DLP 保護的範圍</span><span class="sxs-lookup"><span data-stu-id="1ab05-133">Scope of DLP protection</span></span>

<span data-ttu-id="1ab05-134">DLP 保護的套用方式不同于 Teams 的實體。</span><span class="sxs-lookup"><span data-stu-id="1ab05-134">DLP protection are applied differently to Teams entities.</span></span>

|<span data-ttu-id="1ab05-135">使用者帳戶/群組/清單</span><span class="sxs-lookup"><span data-stu-id="1ab05-135">User Accounts/Groups/List</span></span>  |<span data-ttu-id="1ab05-136">Teams實體</span><span class="sxs-lookup"><span data-stu-id="1ab05-136">Teams Entity</span></span> |<span data-ttu-id="1ab05-137">DLP 保護可用</span><span class="sxs-lookup"><span data-stu-id="1ab05-137">DLP protection available</span></span>|
|---------|---------|---------|
|<span data-ttu-id="1ab05-138">個別使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="1ab05-138">individual user accounts</span></span>     |<span data-ttu-id="1ab05-139">1： 1/n 聊天</span><span class="sxs-lookup"><span data-stu-id="1ab05-139">1:1/n chats</span></span>         |<span data-ttu-id="1ab05-140">是</span><span class="sxs-lookup"><span data-stu-id="1ab05-140">yes</span></span>         |
|     |<span data-ttu-id="1ab05-141">一般聊天</span><span class="sxs-lookup"><span data-stu-id="1ab05-141">general chats</span></span>         |<span data-ttu-id="1ab05-142">否</span><span class="sxs-lookup"><span data-stu-id="1ab05-142">no</span></span>         |
|     |<span data-ttu-id="1ab05-143">專用通道</span><span class="sxs-lookup"><span data-stu-id="1ab05-143">private channels</span></span>         |<span data-ttu-id="1ab05-144">是</span><span class="sxs-lookup"><span data-stu-id="1ab05-144">yes</span></span>         |
|<span data-ttu-id="1ab05-145">安全性群組/通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="1ab05-145">security groups/distribution lists</span></span>  | <span data-ttu-id="1ab05-146">1： 1/n 聊天</span><span class="sxs-lookup"><span data-stu-id="1ab05-146">1:1/n chats</span></span>         |<span data-ttu-id="1ab05-147">是</span><span class="sxs-lookup"><span data-stu-id="1ab05-147">yes</span></span>         |
|     |<span data-ttu-id="1ab05-148">一般聊天</span><span class="sxs-lookup"><span data-stu-id="1ab05-148">general chats</span></span>         |<span data-ttu-id="1ab05-149">否</span><span class="sxs-lookup"><span data-stu-id="1ab05-149">no</span></span>         |
|     |<span data-ttu-id="1ab05-150">專用通道</span><span class="sxs-lookup"><span data-stu-id="1ab05-150">private channels</span></span>         |<span data-ttu-id="1ab05-151">是</span><span class="sxs-lookup"><span data-stu-id="1ab05-151">yes</span></span>        |
|<span data-ttu-id="1ab05-152">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="1ab05-152">Microsoft 365 group</span></span>    |<span data-ttu-id="1ab05-153">1： 1/n 聊天</span><span class="sxs-lookup"><span data-stu-id="1ab05-153">1:1/n chats</span></span>          |<span data-ttu-id="1ab05-154">否</span><span class="sxs-lookup"><span data-stu-id="1ab05-154">no</span></span>         |
|     |<span data-ttu-id="1ab05-155">一般聊天</span><span class="sxs-lookup"><span data-stu-id="1ab05-155">general chats</span></span>          |<span data-ttu-id="1ab05-156">是</span><span class="sxs-lookup"><span data-stu-id="1ab05-156">yes</span></span>        |
|     |<span data-ttu-id="1ab05-157">專用通道</span><span class="sxs-lookup"><span data-stu-id="1ab05-157">private channels</span></span>|<span data-ttu-id="1ab05-158">否</span><span class="sxs-lookup"><span data-stu-id="1ab05-158">no</span></span>| 


## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="1ab05-159">原則提示有助於教育使用者</span><span class="sxs-lookup"><span data-stu-id="1ab05-159">Policy tips help educate users</span></span>

<span data-ttu-id="1ab05-160">與 dlp 在[Exchange、Outlook、Outlook 網頁](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)、 [SharePoint 線上、商務用 OneDrive 網站](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)及[Office 桌面用戶端](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)的運作方式類似，當使用 DLP 原則來觸發動作時，就會出現原則提示。</span><span class="sxs-lookup"><span data-stu-id="1ab05-160">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action triggers with a DLP policy.</span></span> <span data-ttu-id="1ab05-161">以下是原則提示的範例：</span><span class="sxs-lookup"><span data-stu-id="1ab05-161">Here's an example of a policy tip:</span></span>

![Teams 中封鎖的郵件通知](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="1ab05-163">在此，寄件者嘗試在 Microsoft Teams 通道中共用社會安全號碼。</span><span class="sxs-lookup"><span data-stu-id="1ab05-163">Here, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="1ab05-164">**我可以做什麼？** link 開啟對話方塊，為寄件者提供選項，以解決問題。</span><span class="sxs-lookup"><span data-stu-id="1ab05-164">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="1ab05-165">請注意，寄件者可以選擇覆寫原則，或通知系統管理員複查和解決該原則。</span><span class="sxs-lookup"><span data-stu-id="1ab05-165">Notice that, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![解析封鎖郵件的選項](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="1ab05-167">在您的組織中，您可以選擇允許使用者覆寫 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="1ab05-167">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="1ab05-168">當您設定 DLP 原則時，您可以使用預設原則提示，或 [自訂群組織的原則提示](#to-customize-policy-tips) 。</span><span class="sxs-lookup"><span data-stu-id="1ab05-168">When you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="1ab05-169">傳回我們的範例，其中寄件者在 Teams 通道中共用社會保險號碼，以下是收件者看到的功能：</span><span class="sxs-lookup"><span data-stu-id="1ab05-169">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1ab05-170">![封鎖郵件](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="1ab05-170">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="1ab05-171">自訂原則提示</span><span class="sxs-lookup"><span data-stu-id="1ab05-171">To customize policy tips</span></span>

<span data-ttu-id="1ab05-172">若要執行這項工作，您必須被指派為具有編輯 DLP 原則權限的角色。</span><span class="sxs-lookup"><span data-stu-id="1ab05-172">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="1ab05-173">若要深入瞭解，請參閱 [許可權](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="1ab05-173">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="1ab05-174">移至 [規範中心] ([https://compliance.microsoft.com](https://compliance.microsoft.com)) 並登入]。</span><span class="sxs-lookup"><span data-stu-id="1ab05-174">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="1ab05-175">按一下 \*\*\*\*[資料外洩防護]  > \*\*\*\*[原則]。</span><span class="sxs-lookup"><span data-stu-id="1ab05-175">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="1ab05-176">選取原則，然後按一下 [ **原則設定**] 旁的 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="1ab05-176">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="1ab05-177">請建立新的規則，或編輯原則的現有規則。</span><span class="sxs-lookup"><span data-stu-id="1ab05-177">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1ab05-178">![編輯原則的規則](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="1ab05-178">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="1ab05-179">在 [ **使用者通知** ] 索引標籤上，選取 [ **自訂電子郵件文字** 和/或 **自訂原則提示文字** 選項]。</span><span class="sxs-lookup"><span data-stu-id="1ab05-179">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1ab05-180">![自訂使用者通知和原則提示](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="1ab05-180">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="1ab05-181">指定您要用於電子郵件通知和/或原則提示的文字，然後選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1ab05-181">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="1ab05-182">在 [ **原則設定** ] 索引標籤上，選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1ab05-182">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="1ab05-183">針對您的變更，允許大約一小時以透過您的資料中心進行，並同步處理至使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="1ab05-183">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="1ab05-184">將 Microsoft Teams 新增為現有 DLP 政策的位置</span><span class="sxs-lookup"><span data-stu-id="1ab05-184">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="1ab05-185">若要執行這項工作，您必須被指派為具有編輯 DLP 原則權限的角色。</span><span class="sxs-lookup"><span data-stu-id="1ab05-185">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="1ab05-186">若要深入瞭解，請參閱 [許可權](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="1ab05-186">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="1ab05-187">移至 [規範中心] ([https://compliance.microsoft.com](https://compliance.microsoft.com)) 並登入]。</span><span class="sxs-lookup"><span data-stu-id="1ab05-187">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="1ab05-188">按一下 \*\*\*\*[資料外洩防護]  > \*\*\*\*[原則]。</span><span class="sxs-lookup"><span data-stu-id="1ab05-188">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="1ab05-189">選取原則，並查看 [ **位置**] 底下的值。</span><span class="sxs-lookup"><span data-stu-id="1ab05-189">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="1ab05-190">如果您看到 **Teams 聊天及通道郵件**，就會全部設定。</span><span class="sxs-lookup"><span data-stu-id="1ab05-190">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="1ab05-191">如果不是，請按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="1ab05-191">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1ab05-192">![現有原則的位置](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="1ab05-192">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="1ab05-193">在 [**狀態**] 欄中，為 **Teams 聊天及通道郵件** 開啟原則。</span><span class="sxs-lookup"><span data-stu-id="1ab05-193">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1ab05-194">![DLP for Teams 聊天和頻道](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="1ab05-194">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="1ab05-195">在 [ **選擇位置** ] 索引標籤上，保留 [所有帳戶] 的預設設定，或選取 **[讓我選擇特定位置**]。</span><span class="sxs-lookup"><span data-stu-id="1ab05-195">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="1ab05-196">您可以指定：</span><span class="sxs-lookup"><span data-stu-id="1ab05-196">You can specify:</span></span>

    1. <span data-ttu-id="1ab05-197">包含或排除的個別帳戶最多1000個</span><span class="sxs-lookup"><span data-stu-id="1ab05-197">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="1ab05-198">要包含或排除的通訊群組清單和安全性群組。</span><span class="sxs-lookup"><span data-stu-id="1ab05-198">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="1ab05-199">接著選擇 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="1ab05-199">Then choose **Next**.</span></span>

7. <span data-ttu-id="1ab05-200">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="1ab05-200">Click **Save**.</span></span>

<span data-ttu-id="1ab05-201">針對您的變更，允許大約一小時以透過您的資料中心進行，並同步處理至使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="1ab05-201">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="1ab05-202">定義 Microsoft Teams 的新 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="1ab05-202">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="1ab05-203">若要執行這項工作，您必須被指派為具有編輯 DLP 原則權限的角色。</span><span class="sxs-lookup"><span data-stu-id="1ab05-203">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="1ab05-204">若要深入瞭解，請參閱 [許可權](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="1ab05-204">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="1ab05-205">移至 [規範中心] ([https://compliance.microsoft.com](https://compliance.microsoft.com)) 並登入]。</span><span class="sxs-lookup"><span data-stu-id="1ab05-205">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="1ab05-206">選擇 \*\*\*\*[資料外洩防護]  > \*\*\*\*[原則]  > \*\*\*\*[+ 建立原則]。</span><span class="sxs-lookup"><span data-stu-id="1ab05-206">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="1ab05-207">選擇 [範本](data-loss-prevention-policies.md#dlp-policy-templates)，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1ab05-207">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="1ab05-208">在我們的範例中，我們選擇美國個人身分識別資訊資料範本。</span><span class="sxs-lookup"><span data-stu-id="1ab05-208">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1ab05-209">![DLP 原則的隱私權範本](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="1ab05-209">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="1ab05-210">在 [ **命名您的原則** ] 索引標籤上，指定原則的名稱和描述，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1ab05-210">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="1ab05-211">在 [ **選擇位置** ] 索引標籤上，保留 [所有帳戶] 的預設設定，或選取 **[讓我選擇特定位置**]。</span><span class="sxs-lookup"><span data-stu-id="1ab05-211">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="1ab05-212">您可以指定：</span><span class="sxs-lookup"><span data-stu-id="1ab05-212">You can specify:</span></span>

    1. <span data-ttu-id="1ab05-213">包含或排除的個別帳戶最多1000個</span><span class="sxs-lookup"><span data-stu-id="1ab05-213">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="1ab05-214">要包含或排除的通訊群組清單和安全性群組。</span><span class="sxs-lookup"><span data-stu-id="1ab05-214">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="1ab05-215">**這是公開預覽功能。**</span><span class="sxs-lookup"><span data-stu-id="1ab05-215">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP 原則位置](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="1ab05-217">如果您想要確定包含機密資訊的檔不會在 Teams 中不當共用，請確定已開啟 **SharePoint 網站** 和 **OneDrive 帳戶**，以及 **Teams 聊天及通道訊息**。</span><span class="sxs-lookup"><span data-stu-id="1ab05-217">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="1ab05-218">在 [ **原則設定** ] 索引標籤的 **[自訂您要保護的內容類型**] 底下，保留預設的簡單設定，或選擇 [ **使用高級設定**]，然後選擇 [ **下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1ab05-218">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="1ab05-219">如果您選擇 [高級設定]，您可以建立或編輯原則的規則。</span><span class="sxs-lookup"><span data-stu-id="1ab05-219">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="1ab05-220">若要取得此相關協助，請參閱 [簡易設定與高級設定](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)。</span><span class="sxs-lookup"><span data-stu-id="1ab05-220">To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).</span></span>

7.  <span data-ttu-id="1ab05-221">在 [ **原則設定** ] 索引標籤的 [ **如果偵測到機密資訊，您要做什麼？**] 中，複查設定。</span><span class="sxs-lookup"><span data-stu-id="1ab05-221">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="1ab05-222">您可以在這裡選擇保留預設 [原則提示和電子郵件通知](use-notifications-and-policy-tips.md)，或加以自訂。</span><span class="sxs-lookup"><span data-stu-id="1ab05-222">Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1ab05-223">![具有提示與通知的 DLP 原則設定](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="1ab05-223">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="1ab05-224">完成複查或編輯設定後，請選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1ab05-224">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="1ab05-225">在 [ **原則設定** ] 索引標籤上的 [ **您要先開啟原則或測試內容嗎？**] 中，選擇是否要開啟原則、 [先進行測試](dlp-overview-plan-for-dlp.md#policy-deployment)，或是現在保持關閉狀態，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1ab05-225">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1ab05-226">![指定是否要開啟原則](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="1ab05-226">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="1ab05-227">在 [ **複查您的設定** ] 索引標籤上，複查新原則的設定。</span><span class="sxs-lookup"><span data-stu-id="1ab05-227">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="1ab05-228">選擇 [ **編輯** ] 進行變更。</span><span class="sxs-lookup"><span data-stu-id="1ab05-228">Choose **Edit** to make changes.</span></span> <span data-ttu-id="1ab05-229">完成作業後，請選擇 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="1ab05-229">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="1ab05-230">針對您的新原則，允許大約一小時以透過您的資料中心進行，並同步處理至使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="1ab05-230">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="1ab05-231">防止外部存取敏感性文件</span><span class="sxs-lookup"><span data-stu-id="1ab05-231">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="1ab05-232">若要確保外部來賓無法存取包含機密資訊的 SharePoint 檔，請從 SharePoint 或 Teams 預設，選取下列各項：</span><span class="sxs-lookup"><span data-stu-id="1ab05-232">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="1ab05-233">您可以在 DLP 掃描時，確保檔受到保護，並將新的檔案標示 [為機密](/sharepoint/sensitive-by-default)，將其標記為安全可供共用。</span><span class="sxs-lookup"><span data-stu-id="1ab05-233">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="1ab05-234">建議的 DLP 原則結構</span><span class="sxs-lookup"><span data-stu-id="1ab05-234">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="1ab05-235">**Conditions**</span><span class="sxs-lookup"><span data-stu-id="1ab05-235">**Conditions**</span></span>
        - <span data-ttu-id="1ab05-236">內容包含下列任何敏感資訊類型： [選取所有適用專案]</span><span class="sxs-lookup"><span data-stu-id="1ab05-236">Content contains any of these sensitive information types: [Select all that apply]</span></span>
        
        - <span data-ttu-id="1ab05-237">內容共用自 Microsoft 365 與組織外部的人員</span><span class="sxs-lookup"><span data-stu-id="1ab05-237">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="1ab05-238">![偵測敏感內容的外部共用的 DLP 條件](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="1ab05-238">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="1ab05-239">**Actions**</span><span class="sxs-lookup"><span data-stu-id="1ab05-239">**Actions**</span></span>
        - <span data-ttu-id="1ab05-240">限制外部使用者對內容的存取</span><span class="sxs-lookup"><span data-stu-id="1ab05-240">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="1ab05-241">透過電子郵件和原則提示通知使用者</span><span class="sxs-lookup"><span data-stu-id="1ab05-241">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="1ab05-242">傳送事件報告給系統管理員</span><span class="sxs-lookup"><span data-stu-id="1ab05-242">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="1ab05-243">![DLP 巨集指令以封鎖敏感內容的外部共用](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="1ab05-243">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="1ab05-244">當嘗試在包含外部來賓的敏感資訊 SharePoint 中共用檔時，執行中的 DLP 原則：</span><span class="sxs-lookup"><span data-stu-id="1ab05-244">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1ab05-245">![封鎖外部共用](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="1ab05-245">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="1ab05-246">DLP 原則的動作當來賓嘗試在具有封鎖外部的 Teams 中開啟檔時：</span><span class="sxs-lookup"><span data-stu-id="1ab05-246">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1ab05-247">![封鎖外部存取](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="1ab05-247">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="1ab05-248">相關文章</span><span class="sxs-lookup"><span data-stu-id="1ab05-248">Related articles</span></span>

- [<span data-ttu-id="1ab05-249">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="1ab05-249">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="1ab05-250">針對 DLP 原則傳送電子郵件通知並顯示原則提示</span><span class="sxs-lookup"><span data-stu-id="1ab05-250">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
