---
title: 資料遺失防護和 Microsoft 團隊
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
description: 您現在可以將 DLP 原則套用至 Microsoft 團隊聊天和頻道。 請閱讀本文以深入瞭解其運作方式。
ms.openlocfilehash: 3a7b228292952bdba3c950b8ab67501c40e99238
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917919"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="481be-104">資料遺失防護和 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="481be-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="481be-105">資料遺失防護功能最近新增至 Microsoft 團隊聊天及通道訊息，供使用者授權的 Office 365 E5/A5、Microsoft 365 E5/A5、Microsoft 365 資訊保護和控管或 Office 365 高級規範。</span><span class="sxs-lookup"><span data-stu-id="481be-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance or Office 365 Advanced Compliance.</span></span> <span data-ttu-id="481be-106">Office 365 和 Microsoft 365 E3 包含 DLP protection，供 SharePoint 線上、OneDrive 和 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="481be-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="481be-107">這也包括透過團隊共用的檔案，因為小組會使用 SharePoint 線上及 OneDrive 共用檔案。</span><span class="sxs-lookup"><span data-stu-id="481be-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="481be-108">支援小組中的 DLP 保護聊天需要 E5。</span><span class="sxs-lookup"><span data-stu-id="481be-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="481be-109">若要深入了解授權需求，請參閱 [Microsoft 365 租用戶層級服務授權指導方針](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)</span><span class="sxs-lookup"><span data-stu-id="481be-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="481be-110">Microsoft 小組的 DLP 簡介</span><span class="sxs-lookup"><span data-stu-id="481be-110">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="481be-111">最近， [資料遺失防護](data-loss-prevention-policies.md) (DLP) 功能已擴充為包括 Microsoft 團隊聊天和通道訊息， **包括私人通道訊息**。</span><span class="sxs-lookup"><span data-stu-id="481be-111">Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span>

<span data-ttu-id="481be-112">如果您的組織有 DLP，您現在可以定義原則，以防止人員在 Microsoft 小組通道或聊天會話中共用機密資訊。</span><span class="sxs-lookup"><span data-stu-id="481be-112">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="481be-113">以下是此保護運作方式的一些範例：</span><span class="sxs-lookup"><span data-stu-id="481be-113">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="481be-114">**範例1：保護郵件中的機密資訊**。</span><span class="sxs-lookup"><span data-stu-id="481be-114">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="481be-115">假設有人嘗試在小組聊天或頻道中與來賓 (外部使用者) 共用機密資訊。</span><span class="sxs-lookup"><span data-stu-id="481be-115">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="481be-116">如果您已定義 DLP 原則以避免發生這種情況，就會刪除郵件，其中包含傳送給外部使用者的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="481be-116">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="481be-117">這會根據您設定 DLP 原則的方式，自動進行，並在幾秒內進行。</span><span class="sxs-lookup"><span data-stu-id="481be-117">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="481be-118">當與具有下列專案的 Microsoft 團隊使用者共用時，Microsoft 小組的 DLP 會封鎖機密內容：</span><span class="sxs-lookup"><span data-stu-id="481be-118">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="481be-119">- 小組和頻道中的[來賓存取權](/MicrosoftTeams/guest-access);或</span><span class="sxs-lookup"><span data-stu-id="481be-119">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="481be-120">- 會議和聊天會話中的[外部存取](/MicrosoftTeams/manage-external-access)。</span><span class="sxs-lookup"><span data-stu-id="481be-120">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="481be-121">如果寄件者和收件者都只是在 [僅限小組] 模式中，且使用 [Microsoft 團隊原生同盟](/microsoftteams/manage-external-access)，則僅適用于外部聊天會話。</span><span class="sxs-lookup"><span data-stu-id="481be-121">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="481be-122">當商務用 Skype 或非原生同盟聊天會話時，小組的 DLP 不會封鎖 [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) 中的郵件。</span><span class="sxs-lookup"><span data-stu-id="481be-122">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="481be-123">**範例2：保護檔中的機密資訊**。</span><span class="sxs-lookup"><span data-stu-id="481be-123">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="481be-124">假設有人嘗試與 Microsoft 小組通道或聊天中的客人共用檔，而且檔中包含機密資訊。</span><span class="sxs-lookup"><span data-stu-id="481be-124">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="481be-125">如果您定義了 DLP 原則以避免發生這種情況，則不會對這些使用者開啟檔。</span><span class="sxs-lookup"><span data-stu-id="481be-125">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="481be-126">請注意，在這種情況下，您的 DLP 原則必須包括 SharePoint 和 OneDrive，才可就地保護。</span><span class="sxs-lookup"><span data-stu-id="481be-126">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="481be-127"> (這是 DLP for DLP for office for SharePoint 的範例，此範例會顯示在 Microsoft 團隊中，因此要求使用者授權使用 office 365 E3) 中包含的 Office 365 DLP (，但不需要使用者授權 Office 365 的「高級規範」。 ) </span><span class="sxs-lookup"><span data-stu-id="481be-127">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="481be-128">原則提示有助於教育使用者</span><span class="sxs-lookup"><span data-stu-id="481be-128">Policy tips help educate users</span></span>

<span data-ttu-id="481be-129">與 DLP 在 Exchange 中的運作方式相同， [outlook、網頁上的 outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)、 [SharePoint Online、商務用 OneDrive](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)，以及 [Office 桌面用戶端](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)，當動作與 DLP 原則衝突時，就會出現原則提示。</span><span class="sxs-lookup"><span data-stu-id="481be-129">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="481be-130">以下是原則提示的範例：</span><span class="sxs-lookup"><span data-stu-id="481be-130">Here's an example of a policy tip:</span></span>

![小組中的封鎖郵件通知](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="481be-132">在此情況下，寄件者嘗試在 Microsoft 小組通道中共用社會安全號碼。</span><span class="sxs-lookup"><span data-stu-id="481be-132">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="481be-133">**我可以做什麼？** link 開啟對話方塊，為寄件者提供選項，以解決問題。</span><span class="sxs-lookup"><span data-stu-id="481be-133">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="481be-134">請注意，在此情況下，寄件者可以選擇覆寫原則，或通知系統管理員複查並解決。</span><span class="sxs-lookup"><span data-stu-id="481be-134">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![解析封鎖郵件的選項](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="481be-136">在您的組織中，您可以選擇允許使用者覆寫 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="481be-136">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="481be-137">而且，當您設定 DLP 原則時，您可以使用預設原則提示，或 [自訂群組織的原則提示](#to-customize-policy-tips) 。</span><span class="sxs-lookup"><span data-stu-id="481be-137">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="481be-138">傳回我們的範例（即寄件者在小組頻道中共用社會保險號碼），以下是收件者看到的功能：</span><span class="sxs-lookup"><span data-stu-id="481be-138">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

![封鎖郵件](../media/dlp-teams-blockedmessage-notification-to-user.png)

<span data-ttu-id="481be-140">[ **這是什麼？** ] 連結會開啟有關 DLP 原則的 [文章](data-loss-prevention-policies.md) ，協助說明郵件封鎖的原因。</span><span class="sxs-lookup"><span data-stu-id="481be-140">The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="481be-141">自訂原則提示</span><span class="sxs-lookup"><span data-stu-id="481be-141">To customize policy tips</span></span>

<span data-ttu-id="481be-142">若要執行這種工作，您必須被指派具有編輯 DLP 原則許可權的角色。</span><span class="sxs-lookup"><span data-stu-id="481be-142">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="481be-143">若要深入瞭解，請參閱 [許可權](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="481be-143">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="481be-144">請移至安全性 & 規範中心 ([https://protection.office.com](https://protection.office.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="481be-144">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="481be-145">選擇 [**資料遺失防護**]  >  **原則**。</span><span class="sxs-lookup"><span data-stu-id="481be-145">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="481be-146">選取原則，然後按一下 [ **原則設定**] 旁的 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="481be-146">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="481be-147">請建立新的規則，或編輯原則的現有規則。</span><span class="sxs-lookup"><span data-stu-id="481be-147">Either create a new rule, or edit an existing rule for the policy.</span></span><br/>![編輯原則的規則](../media/dlp-teams-editrule.png)<br/>

5. <span data-ttu-id="481be-149">在 [ **使用者通知** ] 索引標籤上，選取 [ **自訂電子郵件文字** 和/或 **自訂原則提示文字** 選項]。</span><span class="sxs-lookup"><span data-stu-id="481be-149">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span><br/><span data-ttu-id="481be-150">![自訂使用者通知和原則提示](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="481be-150">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="481be-151">指定您要用於電子郵件通知和/或原則提示的文字，然後選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="481be-151">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="481be-152">在 [ **原則設定** ] 索引標籤上，選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="481be-152">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="481be-153">針對您的變更，允許大約一小時以透過您的資料中心進行，並同步處理至使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="481be-153">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="481be-154">將 Microsoft 團隊新增為現有 DLP 原則的位置</span><span class="sxs-lookup"><span data-stu-id="481be-154">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="481be-155">若要執行這種工作，您必須被指派具有編輯 DLP 原則許可權的角色。</span><span class="sxs-lookup"><span data-stu-id="481be-155">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="481be-156">若要深入瞭解，請參閱 [許可權](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="481be-156">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="481be-157">請移至安全性 & 規範中心 ([https://protection.office.com](https://protection.office.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="481be-157">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="481be-158">選擇 [**資料遺失防護**]  >  **原則**。</span><span class="sxs-lookup"><span data-stu-id="481be-158">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="481be-159">選取原則，並查看 [ **位置**] 底下的值。</span><span class="sxs-lookup"><span data-stu-id="481be-159">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="481be-160">如果您看到 **小組聊天及通道訊息**，您就會全部設定。</span><span class="sxs-lookup"><span data-stu-id="481be-160">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="481be-161">如果不是，請按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="481be-161">If you don't, click **Edit**.</span></span><br/><span data-ttu-id="481be-162">![現有原則的位置](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="481be-162">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span><br/>

4. <span data-ttu-id="481be-163">在 [ **狀態** ] 欄中，為 **小組聊天和頻道訊息** 開啟原則。</span><span class="sxs-lookup"><span data-stu-id="481be-163">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span><br/><span data-ttu-id="481be-164">![適用于小組聊天和頻道的 DLP](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="481be-164">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span><br/>

5. <span data-ttu-id="481be-165">在 [ **選擇位置** ] 索引標籤上，保留 [所有帳戶] 的預設設定，或選取 **[讓我選擇特定位置**]。</span><span class="sxs-lookup"><span data-stu-id="481be-165">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="481be-166">您可以指定：</span><span class="sxs-lookup"><span data-stu-id="481be-166">You can specify:</span></span>
    1. <span data-ttu-id="481be-167">包含或排除的個別帳戶最多1000個</span><span class="sxs-lookup"><span data-stu-id="481be-167">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="481be-168">要包含或排除的通訊群組清單和安全性群組。</span><span class="sxs-lookup"><span data-stu-id="481be-168">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="481be-169">**這是公開預覽功能。**</span><span class="sxs-lookup"><span data-stu-id="481be-169">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="481be-170">接著選擇 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="481be-170">Then choose **Next**.</span></span>



6. <span data-ttu-id="481be-171">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="481be-171">Click **Save**.</span></span>

<span data-ttu-id="481be-172">針對您的變更，允許大約一小時以透過您的資料中心進行，並同步處理至使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="481be-172">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="481be-173">定義新的 Microsoft 團隊 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="481be-173">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="481be-174">若要執行這種工作，您必須被指派具有編輯 DLP 原則許可權的角色。</span><span class="sxs-lookup"><span data-stu-id="481be-174">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="481be-175">若要深入瞭解，請參閱 [許可權](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="481be-175">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="481be-176">請移至安全性 & 規範中心 ([https://protection.office.com](https://protection.office.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="481be-176">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="481be-177">選擇 [**資料遺失防護**  >  **原則**  >  **+ 建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="481be-177">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="481be-178">選擇 [範本](data-loss-prevention-policies.md#dlp-policy-templates)，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="481be-178">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span><br/><span data-ttu-id="481be-179">在我們的範例中，我們選擇美國個人身分識別資訊資料範本。</span><span class="sxs-lookup"><span data-stu-id="481be-179">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span><br/><span data-ttu-id="481be-180">![DLP 原則的隱私權範本](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="481be-180">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="481be-181">在 [ **命名您的原則** ] 索引標籤上，指定原則的名稱和描述，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="481be-181">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="481be-182">在 [ **選擇位置** ] 索引標籤上，保留 [所有帳戶] 的預設設定，或選取 **[讓我選擇特定位置**]。</span><span class="sxs-lookup"><span data-stu-id="481be-182">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="481be-183">您可以指定：</span><span class="sxs-lookup"><span data-stu-id="481be-183">You can specify:</span></span>
    1. <span data-ttu-id="481be-184">包含或排除的個別帳戶最多1000個</span><span class="sxs-lookup"><span data-stu-id="481be-184">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="481be-185">要包含或排除的通訊群組清單和安全性群組。</span><span class="sxs-lookup"><span data-stu-id="481be-185">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="481be-186">**這是公開預覽功能。**</span><span class="sxs-lookup"><span data-stu-id="481be-186">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

![DLP 原則位置](../media/dlp-teams-selectlocationsnewpolicy.png)

> [!NOTE]
> <span data-ttu-id="481be-188">如果您想要確定包含機密資訊的檔不會在小組中正確共用，請確定已開啟 **SharePoint 的網站** 和 **OneDrive 帳戶** ，以及 **小組聊天及通道訊息**。</span><span class="sxs-lookup"><span data-stu-id="481be-188">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>


6. <span data-ttu-id="481be-189">在 [ **原則設定** ] 索引標籤的 **[自訂您要保護的內容類型**] 底下，保留預設的簡單設定，或選擇 [ **使用高級設定**]，然後選擇 [ **下一步]**。</span><span class="sxs-lookup"><span data-stu-id="481be-189">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="481be-190">如果您選擇 [高級設定]，您可以建立或編輯原則的規則。</span><span class="sxs-lookup"><span data-stu-id="481be-190">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="481be-191"> (若要取得此相關協助，請參閱 [簡易設定與高級設定](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)。 ) </span><span class="sxs-lookup"><span data-stu-id="481be-191">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="481be-192">在 [ **原則設定** ] 索引標籤的 [ **如果偵測到機密資訊，您要做什麼？**] 中，複查設定。</span><span class="sxs-lookup"><span data-stu-id="481be-192">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="481be-193"> (這裡是您可以選擇保留預設 [原則提示和電子郵件通知](use-notifications-and-policy-tips.md)，或加以自訂的位置。 ) </span><span class="sxs-lookup"><span data-stu-id="481be-193">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span><br/><span data-ttu-id="481be-194">![具有提示與通知的 DLP 原則設定](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="481be-194">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span><br/><span data-ttu-id="481be-195">完成複查或編輯設定後，請選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="481be-195">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="481be-196">在 [ **原則設定** ] 索引標籤上的 [ **您要先開啟原則或測試內容嗎？**] 中，選擇是否要開啟原則、 [先進行測試](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)，或是現在保持關閉狀態，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="481be-196">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span><br/><span data-ttu-id="481be-197">![指定是否要開啟原則](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="481be-197">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span><br/>

9. <span data-ttu-id="481be-198">在 [ **複查您的設定** ] 索引標籤上，複查新原則的設定。</span><span class="sxs-lookup"><span data-stu-id="481be-198">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="481be-199">選擇 [ **編輯** ] 進行變更。</span><span class="sxs-lookup"><span data-stu-id="481be-199">Choose **Edit** to make changes.</span></span> <span data-ttu-id="481be-200">完成作業後，請選擇 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="481be-200">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="481be-201">針對您的新原則，允許大約一小時以透過您的資料中心進行，並同步處理至使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="481be-201">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="481be-202">防止對機密檔的外部存取</span><span class="sxs-lookup"><span data-stu-id="481be-202">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="481be-203">若要確定包含機密資訊的 SharePoint 檔預設不能由外部來賓存取 SharePoint 或小組，請選取下列各項：</span><span class="sxs-lookup"><span data-stu-id="481be-203">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="481be-204">您可以在 DLP 掃描時保證檔受到保護，並將新的檔案標記為可安全地加以共用。預設會將 [新的檔案標示為敏感](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="481be-204">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default)</span></span>
- <span data-ttu-id="481be-205">建議的 DLP 原則結構</span><span class="sxs-lookup"><span data-stu-id="481be-205">Recommended DLP policy structure</span></span>
    - <span data-ttu-id="481be-206">**Conditions**</span><span class="sxs-lookup"><span data-stu-id="481be-206">**Conditions**</span></span>
        - <span data-ttu-id="481be-207">內容包含下列任何敏感資訊類型： [選取所有套用專案]</span><span class="sxs-lookup"><span data-stu-id="481be-207">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        - <span data-ttu-id="481be-208">內容是從 Microsoft 365 與組織外部的人員共用</span><span class="sxs-lookup"><span data-stu-id="481be-208">Content is shared from Microsoft 365 with people outside my organization</span></span>
        <br/><span data-ttu-id="481be-209">![偵測敏感內容的外部共用的 DLP 條件](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="481be-209">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span><br/>


    - <span data-ttu-id="481be-210">**動作**</span><span class="sxs-lookup"><span data-stu-id="481be-210">**Actions**</span></span>
        - <span data-ttu-id="481be-211">限制外部使用者的內容存取權</span><span class="sxs-lookup"><span data-stu-id="481be-211">Restrict access to the content for external users</span></span>
        - <span data-ttu-id="481be-212">使用電子郵件和原則提示通知使用者</span><span class="sxs-lookup"><span data-stu-id="481be-212">Notify users with email and policy tips</span></span>
        - <span data-ttu-id="481be-213">將附隨報告傳送給系統管理員</span><span class="sxs-lookup"><span data-stu-id="481be-213">Send incident reports to the Administrator</span></span>    
        <br/>![DLP 巨集指令以封鎖敏感內容的外部共用](../media/dlp-teams-external-sharing/external-action.png)<br/>

<span data-ttu-id="481be-215">當嘗試在包含外部來賓的敏感資訊 SharePoint 中共用檔時，執行中的 DLP 原則：</span><span class="sxs-lookup"><span data-stu-id="481be-215">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>
<br/><span data-ttu-id="481be-216">![封鎖外部共用](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="481be-216">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span><br/>


<span data-ttu-id="481be-217">DLP 原則的動作當來賓嘗試在具有封鎖外部的小組中開啟檔時：</span><span class="sxs-lookup"><span data-stu-id="481be-217">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>
<br/><span data-ttu-id="481be-218">![封鎖外部存取](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="481be-218">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span><br/>

## <a name="related-articles"></a><span data-ttu-id="481be-219">相關文章</span><span class="sxs-lookup"><span data-stu-id="481be-219">Related articles</span></span>

[<span data-ttu-id="481be-220">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="481be-220">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="481be-221">針對 DLP 原則傳送電子郵件通知並顯示原則提示</span><span class="sxs-lookup"><span data-stu-id="481be-221">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)