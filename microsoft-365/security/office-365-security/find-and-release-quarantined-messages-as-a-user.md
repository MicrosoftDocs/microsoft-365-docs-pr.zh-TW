---
title: 以使用者身分找到並釋放被隔離的郵件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 使用者可以了解如何在 Exchange Online Protection (EOP) 中查看和管理收到的隔離郵件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e9a9da170dc0d3effba495c29672fb8f6bb02031
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599932"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="1798e-103">在 EOP 尋找及釋出隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="1798e-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1798e-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="1798e-104">**Applies to**</span></span>
- [<span data-ttu-id="1798e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1798e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1798e-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="1798e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1798e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1798e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1798e-108">在擁有 Exchange Online 信箱的 Microsoft 365 組織中或是沒有 Exchange Online 信箱的獨立 Exchange Online Protection (EOP) 組織中，隔離區會保存可能有害或垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="1798e-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="1798e-109">如需詳細資訊，請參閱 [EOP 中的隔離區](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="1798e-109">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="1798e-110">身為使用者，您可以檢視、釋出、刪除隔離郵件 (收件者是您，且經系統認定為是垃圾郵件或大量電子郵件而加以隔離的郵件)。</span><span class="sxs-lookup"><span data-stu-id="1798e-110">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam or bulk email.</span></span> <span data-ttu-id="1798e-111">自 2020 年 4 月起，您可以查看或刪除收件者是您的已隔離網路釣魚 (不是高信賴度網路釣魚) 郵件。</span><span class="sxs-lookup"><span data-stu-id="1798e-111">As of April 2020, you can view or delete quarantined phishing (not high confidence phishing) messages where you are a recipient.</span></span> <span data-ttu-id="1798e-112">您可以在安全性與合規性中心 (如果系統管理員已設定) 或[使用者垃圾郵件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)中查看和管理您的隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="1798e-112">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1798e-113">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="1798e-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1798e-114">若要開啟安全性與合規性中心，請移至 <https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="1798e-114">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="1798e-115">若要直接開啟 [隔離區] 頁面，請移至 <https://protection.office.com/quarantine>。</span><span class="sxs-lookup"><span data-stu-id="1798e-115">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="1798e-116">系統管理員可以設定郵件要先保留在隔離區中多久，然後才永久刪除 (反垃圾郵件原則)。</span><span class="sxs-lookup"><span data-stu-id="1798e-116">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="1798e-117">已在隔離區中到期的郵件將無法還原。</span><span class="sxs-lookup"><span data-stu-id="1798e-117">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="1798e-118">如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1798e-118">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="1798e-119">系統管理員也可以在反垃圾郵件原則中[啟用使用者垃圾郵件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)。</span><span class="sxs-lookup"><span data-stu-id="1798e-119">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="1798e-120">使用者可以直接從這些通知釋出垃圾郵件隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="1798e-120">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="1798e-121">使用者可以直接從這些通知檢閱垃圾郵件隔離郵件 (非高信賴度網路釣魚郵件)。</span><span class="sxs-lookup"><span data-stu-id="1798e-121">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="1798e-122">如需詳細資訊，請參閱 [EOP 中的使用者垃圾郵件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="1798e-122">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="1798e-123">經郵件流程規則 (又稱為傳輸規則) 認為是高信賴度網路釣魚或惡意程式碼而遭到隔離的郵件，只有系統管理員能看到，使用者看不到。</span><span class="sxs-lookup"><span data-stu-id="1798e-123">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="1798e-124">如需詳細資訊，請參閱[在 EOP 中管理隔離的郵件和檔案](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="1798e-124">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="1798e-125">您只能釋出郵件並將其報告為誤判 (非垃圾郵件) 一次。</span><span class="sxs-lookup"><span data-stu-id="1798e-125">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="1798e-126">檢視隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="1798e-126">View your quarantined messages</span></span>

1. <span data-ttu-id="1798e-127">在「安全性與合規性中心」內，移至 [威脅管理] \> [檢閱] \> [隔離]。</span><span class="sxs-lookup"><span data-stu-id="1798e-127">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="1798e-128">您可以按一下可用資料行標題來排序結果。</span><span class="sxs-lookup"><span data-stu-id="1798e-128">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="1798e-129">按一下 [修改資料行] 可顯示最多七個資料行。</span><span class="sxs-lookup"><span data-stu-id="1798e-129">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="1798e-130">預設值會標上星號 (<sup>\*</sup>)：</span><span class="sxs-lookup"><span data-stu-id="1798e-130">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="1798e-131">**收到日期**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1798e-131">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="1798e-132">**寄件者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1798e-132">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="1798e-133">**主旨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1798e-133">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="1798e-134">**隔離原因**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1798e-134">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="1798e-135">**已釋出？**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1798e-135">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="1798e-136">**原則類型**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1798e-136">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="1798e-137">**到期**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1798e-137">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="1798e-138">**收件者**</span><span class="sxs-lookup"><span data-stu-id="1798e-138">**Recipient**</span></span>
   - <span data-ttu-id="1798e-139">**郵件識別碼**</span><span class="sxs-lookup"><span data-stu-id="1798e-139">**Message ID**</span></span>
   - <span data-ttu-id="1798e-140">**原則名稱**</span><span class="sxs-lookup"><span data-stu-id="1798e-140">**Policy name**</span></span>
   - <span data-ttu-id="1798e-141">**大小**</span><span class="sxs-lookup"><span data-stu-id="1798e-141">**Size**</span></span>
   - <span data-ttu-id="1798e-142">**方向**</span><span class="sxs-lookup"><span data-stu-id="1798e-142">**Direction**</span></span>

   <span data-ttu-id="1798e-143">完成時，請按一下 [儲存]，或按一下 [設為預設值]。</span><span class="sxs-lookup"><span data-stu-id="1798e-143">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="1798e-144">若要篩選結果，請按一下 [篩選]。</span><span class="sxs-lookup"><span data-stu-id="1798e-144">To filter the results, click **Filter**.</span></span> <span data-ttu-id="1798e-145">可用的篩選條件如下：</span><span class="sxs-lookup"><span data-stu-id="1798e-145">The available filters are:</span></span>

   - <span data-ttu-id="1798e-146">**到期時間**：依郵件將於隔離區中到期的時間進行篩選：</span><span class="sxs-lookup"><span data-stu-id="1798e-146">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="1798e-147">**今天**</span><span class="sxs-lookup"><span data-stu-id="1798e-147">**Today**</span></span>
     - <span data-ttu-id="1798e-148">**未來 2 天**</span><span class="sxs-lookup"><span data-stu-id="1798e-148">**Next 2 days**</span></span>
     - <span data-ttu-id="1798e-149">**未來 7 天**</span><span class="sxs-lookup"><span data-stu-id="1798e-149">**Next 7 days**</span></span>
     - <span data-ttu-id="1798e-150">**自訂**：輸入 [開始日期] 和 [結束日期]。</span><span class="sxs-lookup"><span data-stu-id="1798e-150">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="1798e-151">**收到時間**：輸入 [開始日期] 和 [結束日期]。</span><span class="sxs-lookup"><span data-stu-id="1798e-151">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="1798e-152">**隔離原因**：</span><span class="sxs-lookup"><span data-stu-id="1798e-152">**Quarantine reason**:</span></span>
     - <span data-ttu-id="1798e-153">**大量郵件**</span><span class="sxs-lookup"><span data-stu-id="1798e-153">**Bulk**</span></span>
     - <span data-ttu-id="1798e-154">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="1798e-154">**Spam**</span></span>
     - <span data-ttu-id="1798e-155">**網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="1798e-155">**Phish**</span></span>

   - <span data-ttu-id="1798e-156">**原則類型**：依原則類型篩選郵件：</span><span class="sxs-lookup"><span data-stu-id="1798e-156">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="1798e-157">**反網路釣魚原則**</span><span class="sxs-lookup"><span data-stu-id="1798e-157">**Anti-phish policy**</span></span>
     - <span data-ttu-id="1798e-158">**託管的內容篩選原則** (反網路釣魚原則)</span><span class="sxs-lookup"><span data-stu-id="1798e-158">**Hosted content filter policy** (anti-spam policy)</span></span>

   <span data-ttu-id="1798e-159">若要清除篩選，按一下 [清除]。</span><span class="sxs-lookup"><span data-stu-id="1798e-159">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="1798e-160">若要隱藏 [篩選] 飛出視窗，再按一下 [篩選]。</span><span class="sxs-lookup"><span data-stu-id="1798e-160">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="1798e-161">使用 [結果排序依據] (預設為 [郵件識別碼] 按鈕) 和對應值來尋找特定郵件。</span><span class="sxs-lookup"><span data-stu-id="1798e-161">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="1798e-162">不支援萬用字元。</span><span class="sxs-lookup"><span data-stu-id="1798e-162">Wildcards aren't supported.</span></span> <span data-ttu-id="1798e-163">您可以依下列值進行搜尋：</span><span class="sxs-lookup"><span data-stu-id="1798e-163">You can search by the following values:</span></span>

   - <span data-ttu-id="1798e-164">**郵件識別碼**：郵件的全域唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="1798e-164">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="1798e-165">如果您在清單中選取某個郵件，出現的 [詳細資料] 飛出窗格中就會出現 [郵件識別碼] 值。</span><span class="sxs-lookup"><span data-stu-id="1798e-165">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="1798e-166">系統管理員可以使用 [郵件追蹤][](message-trace-scc.md) 來尋找郵件及其對應的郵件識別碼值。</span><span class="sxs-lookup"><span data-stu-id="1798e-166">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="1798e-167">**寄件者電子郵件地址**：單一寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="1798e-167">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="1798e-168">**原則名稱**：使用郵件的整個原則名稱。</span><span class="sxs-lookup"><span data-stu-id="1798e-168">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="1798e-169">搜尋時不會區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="1798e-169">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="1798e-170">**收件者電子郵件地址**：單一收件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="1798e-170">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="1798e-171">**主旨**：使用郵件的完整主旨。</span><span class="sxs-lookup"><span data-stu-id="1798e-171">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="1798e-172">搜尋時不會區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="1798e-172">The search is not case-sensitive.</span></span>

   <span data-ttu-id="1798e-173">輸入搜尋準則後，請按一下![重新整理按鈕](../../media/scc-quarantine-refresh.png) [重新整理] 來篩選結果。</span><span class="sxs-lookup"><span data-stu-id="1798e-173">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="1798e-174">當您找到特定隔離郵件後，選取該郵件即可檢視其詳細資料，並對其採取動作 (例如檢視、釋出、下載或刪除郵件)。</span><span class="sxs-lookup"><span data-stu-id="1798e-174">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="1798e-175">匯出郵件結果</span><span class="sxs-lookup"><span data-stu-id="1798e-175">Export message results</span></span>

1. <span data-ttu-id="1798e-176">選取您感興趣的郵件，然後按一下 [匯出結果]。</span><span class="sxs-lookup"><span data-stu-id="1798e-176">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="1798e-177">在提醒您讓瀏覽器視窗保持開啟的確認訊息中，按一下 [是]。</span><span class="sxs-lookup"><span data-stu-id="1798e-177">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="1798e-178">匯出作業準備就緒時，便可為 .csv 檔案命名並選擇下載位置。</span><span class="sxs-lookup"><span data-stu-id="1798e-178">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="1798e-179">檢視隔離郵件詳細資料</span><span class="sxs-lookup"><span data-stu-id="1798e-179">View quarantined message details</span></span>

<span data-ttu-id="1798e-180">當您選取清單中的電子郵件訊息時，[詳細資料] 飛出窗格中會出現下列郵件詳細資料：</span><span class="sxs-lookup"><span data-stu-id="1798e-180">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="1798e-181">**郵件識別碼**：郵件的全域唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="1798e-181">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="1798e-182">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="1798e-182">**Sender address**</span></span>

- <span data-ttu-id="1798e-183">**收到日期**：收到郵件的日期/時間。</span><span class="sxs-lookup"><span data-stu-id="1798e-183">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="1798e-184">**主旨**</span><span class="sxs-lookup"><span data-stu-id="1798e-184">**Subject**</span></span>

- <span data-ttu-id="1798e-185">**隔離原因**：顯示是否將郵件識別為 [垃圾郵件] 或 [大量] 或 [網路釣魚]。</span><span class="sxs-lookup"><span data-stu-id="1798e-185">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>

- <span data-ttu-id="1798e-186">**收件者**：如果郵件包含多個收件者，則必須按一下 [預覽郵件] 或 [檢視郵件標頭] 以查看完整的收件者清單。</span><span class="sxs-lookup"><span data-stu-id="1798e-186">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="1798e-187">**到期**：郵件會自動從隔離區永久刪除的日期/時間。</span><span class="sxs-lookup"><span data-stu-id="1798e-187">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="1798e-188">**已釋出給**：該封郵件曾釋出至的所有電子郵件地址 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="1798e-188">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="1798e-189">**尚未釋出給**：該封郵件尚未釋出至的所有電子郵件地址 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="1798e-189">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="1798e-190">對隔離的電子郵件採取動作</span><span class="sxs-lookup"><span data-stu-id="1798e-190">Take action on quarantined email</span></span>

<span data-ttu-id="1798e-191">選取郵件之後，便可以在 [詳細資料] 飛出窗格中選擇要如何處理郵件：</span><span class="sxs-lookup"><span data-stu-id="1798e-191">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="1798e-192">**釋出郵件**：在出現的飛出窗格中，選擇是否要 [向 Microsoft 回報郵件以便分析]。</span><span class="sxs-lookup"><span data-stu-id="1798e-192">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="1798e-193">預設會選取此選項，並向 Microsoft 回報錯誤隔離的郵件屬於誤判。</span><span class="sxs-lookup"><span data-stu-id="1798e-193">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="1798e-194">完成時，請按一下 [釋出郵件]。</span><span class="sxs-lookup"><span data-stu-id="1798e-194">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="1798e-195">**檢視郵件標頭**：選擇此連結來查看郵件標頭文字。</span><span class="sxs-lookup"><span data-stu-id="1798e-195">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="1798e-196">若要深入分析標頭欄位和值，請將郵件標頭文字複製到您的剪貼簿，然後選擇 [Microsoft 郵件標頭分析器] 來移至遠端連線分析程式 (如果您想在不離開 Microsoft 365 的情況下完成這項工作，請按一下滑鼠右鍵並選擇 [在新索引標籤中開啟])。</span><span class="sxs-lookup"><span data-stu-id="1798e-196">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="1798e-197">將郵件標頭貼至 [郵件標頭分析器] 區段的頁面上，並選擇 [分析標頭]：</span><span class="sxs-lookup"><span data-stu-id="1798e-197">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="1798e-198">**預覽郵件**：在出現的飛出窗格中，選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="1798e-198">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="1798e-199">**原始碼檢視**：顯示已停用所有連結的郵件內文 HTML 版本。</span><span class="sxs-lookup"><span data-stu-id="1798e-199">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="1798e-200">**文字檢視**：以純文字顯示郵件內文。</span><span class="sxs-lookup"><span data-stu-id="1798e-200">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="1798e-201">**從隔離區中移除**：當您在出現的警告中按一下 [是] 之後，郵件就會立即遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="1798e-201">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

- <span data-ttu-id="1798e-202">**封鎖寄件者**：防止寄件者傳送郵件給您。</span><span class="sxs-lookup"><span data-stu-id="1798e-202">**Block Sender**: Prevents the sender from sending messages to you.</span></span>

<span data-ttu-id="1798e-203">完成時，請按一下 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="1798e-203">When you're finished, click **Close**.</span></span>

<span data-ttu-id="1798e-204">如果您未釋出或移除郵件，則郵件會在預設的隔離保留期間到期後遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="1798e-204">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="1798e-205">對多個隔離的電子郵件採取動作</span><span class="sxs-lookup"><span data-stu-id="1798e-205">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="1798e-206">當您選取清單中的多個隔離郵件 (最多 100 個) 時，隨即會出現 [大量動作] 飛出窗格供您採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="1798e-206">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="1798e-207">**釋出郵件**：這些選項與您釋出單一郵件時的選項相同，差別只在您無法選取 [將郵件釋出給特定收件者]；您只能選取 [將郵件釋出給所有收件者] 或 [將郵件釋出給其他人]。</span><span class="sxs-lookup"><span data-stu-id="1798e-207">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="1798e-208">**刪除郵件**：在出現的警告中按一下 [是] 之後，郵件就會立即遭到刪除，而不會傳送給原始收件者。</span><span class="sxs-lookup"><span data-stu-id="1798e-208">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="1798e-209">完成時，請按一下 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="1798e-209">When you're finished, click **Close**.</span></span>
