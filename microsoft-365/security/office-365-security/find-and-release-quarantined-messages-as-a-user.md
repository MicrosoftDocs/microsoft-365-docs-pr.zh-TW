---
title: 以 Office 365 使用者身分尋找及釋出隔離的郵件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: 身為 Office 365 使用者，您可以檢視、釋出、刪除隔離郵件 (收件者是您，且經垃圾郵件篩選功能認為是垃圾郵件或大量電子郵件而加以隔離的郵件)。 您可以在「安全性與合規性中心」檢視和管理隔離郵件。
ms.openlocfilehash: 04f04cfddb123bf176f3c71568789c77d225a601
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893667"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a><span data-ttu-id="2dc09-104">以 Office 365 使用者身分尋找及釋出隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="2dc09-104">Find and release quarantined messages as a user in Office 365</span></span>

<span data-ttu-id="2dc09-105">在擁有 Exchange Online 信箱的 Office 365 組織中或是沒有 Exchange Online 信箱的獨立 Exchange Online Protection (EOP) 組織中，隔離區會保存可能有害或不想要的郵件。</span><span class="sxs-lookup"><span data-stu-id="2dc09-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="2dc09-106">如需詳細資訊，請參閱 [Office 365 中的隔離區](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="2dc09-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="2dc09-107">身為使用者，您可以檢視、釋出、刪除收件者是您的隔離郵件，郵件之所以會遭到隔離，是因為系統認為這些郵件是垃圾郵件、大量電子郵件或 (2020 年 4 月起) 網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="2dc09-107">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="2dc09-108">您也可以向 Microsoft 回報誤判的郵件。</span><span class="sxs-lookup"><span data-stu-id="2dc09-108">You can also report false positives to Microsoft.</span></span>

<span data-ttu-id="2dc09-109">您可以在「安全性與合規性中心」檢視和管理隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="2dc09-109">You view and manage your quarantined messages in the Security & Compliance Center.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2dc09-110">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="2dc09-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2dc09-111">若要開啟 Office 365 的「安全性與合規性中心」，請移至 <https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="2dc09-111">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="2dc09-112">若要直接開啟 [隔離區] 頁面，請移至 <https://protection.office.com/quarantine>。</span><span class="sxs-lookup"><span data-stu-id="2dc09-112">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="2dc09-113">系統管理員可以設定郵件要先保留在隔離區中多久，然後才永久刪除 (反垃圾郵件原則)。</span><span class="sxs-lookup"><span data-stu-id="2dc09-113">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="2dc09-114">已在隔離區中到期的郵件將無法還原。</span><span class="sxs-lookup"><span data-stu-id="2dc09-114">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="2dc09-115">如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2dc09-115">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="2dc09-116">系統管理員也可以在反垃圾郵件原則中[啟用使用者垃圾郵件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)。</span><span class="sxs-lookup"><span data-stu-id="2dc09-116">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="2dc09-117">2019 年 10 月起，您已無法再從這些通知中直接釋出隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="2dc09-117">As of October 2019, you can no longer release quarantined messages directly from these notifications.</span></span> <span data-ttu-id="2dc09-118">您可以按一下通知中的 [檢閱]\*\*\*\*，以前往「安全性與合規性中心」內的隔離區。</span><span class="sxs-lookup"><span data-stu-id="2dc09-118">You can click **Review** in the notification, which will take you to Quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="2dc09-119">如需有關通知的詳細資訊，請參閱 [Office 365 中的使用者垃圾郵件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="2dc09-119">For more information about the notifications, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="2dc09-120">經系統或郵件流程規則 (又稱為傳輸規則) 認為是高信賴度網路釣魚或惡意程式碼而遭到隔離的郵件，只會交給系統管理員處理。</span><span class="sxs-lookup"><span data-stu-id="2dc09-120">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="2dc09-121">如需詳細資訊，請參閱[以 Office 365 系統管理員身分管理隔離的郵件和檔案](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="2dc09-121">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="2dc09-122">您只能釋出郵件並將其報告為誤判 (非垃圾郵件) 一次。</span><span class="sxs-lookup"><span data-stu-id="2dc09-122">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="2dc09-123">檢視隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="2dc09-123">View your quarantined messages</span></span>

1. <span data-ttu-id="2dc09-124">在「安全性與合規性中心」內，移至 [威脅管理]\*\*\*\* \> [檢閱]\*\*\*\* \> [隔離]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2dc09-124">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="2dc09-125">您可以按一下可用資料行標題來排序結果。</span><span class="sxs-lookup"><span data-stu-id="2dc09-125">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="2dc09-126">按一下 [修改資料行]\*\*\*\* 可顯示最多七個資料行。</span><span class="sxs-lookup"><span data-stu-id="2dc09-126">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="2dc09-127">預設值會標上星號 (<sup>\*</sup>)：</span><span class="sxs-lookup"><span data-stu-id="2dc09-127">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="2dc09-128">**收到日期**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2dc09-128">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="2dc09-129">**寄件者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2dc09-129">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="2dc09-130">**主旨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2dc09-130">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="2dc09-131">**隔離原因**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2dc09-131">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="2dc09-132">**已釋出？**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2dc09-132">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="2dc09-133">**原則類型**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2dc09-133">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="2dc09-134">**到期**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2dc09-134">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="2dc09-135">**收件者**</span><span class="sxs-lookup"><span data-stu-id="2dc09-135">**Recipient**</span></span>

   - <span data-ttu-id="2dc09-136">**郵件識別碼**</span><span class="sxs-lookup"><span data-stu-id="2dc09-136">**Message ID**</span></span>

   - <span data-ttu-id="2dc09-137">**原則名稱**</span><span class="sxs-lookup"><span data-stu-id="2dc09-137">**Policy name**</span></span>

   - <span data-ttu-id="2dc09-138">**大小**</span><span class="sxs-lookup"><span data-stu-id="2dc09-138">**Size**</span></span>

   - <span data-ttu-id="2dc09-139">**方向**</span><span class="sxs-lookup"><span data-stu-id="2dc09-139">**Direction**</span></span>

   <span data-ttu-id="2dc09-140">完成時，請按一下 [儲存]\*\*\*\*，或按一下 [設為預設值]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2dc09-140">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="2dc09-141">若要篩選結果，請按一下 [篩選]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2dc09-141">To filter the results, click **Filter**.</span></span> <span data-ttu-id="2dc09-142">可用的篩選條件如下：</span><span class="sxs-lookup"><span data-stu-id="2dc09-142">The available filters are:</span></span>

   - <span data-ttu-id="2dc09-143">**到期時間**：依郵件將於隔離區中到期的時間進行篩選：</span><span class="sxs-lookup"><span data-stu-id="2dc09-143">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="2dc09-144">**今天**</span><span class="sxs-lookup"><span data-stu-id="2dc09-144">**Today**</span></span>

     - <span data-ttu-id="2dc09-145">**未來 2 天**</span><span class="sxs-lookup"><span data-stu-id="2dc09-145">**Next 2 days**</span></span>

     - <span data-ttu-id="2dc09-146">**未來 7 天**</span><span class="sxs-lookup"><span data-stu-id="2dc09-146">**Next 7 days**</span></span>

     - <span data-ttu-id="2dc09-147">**自訂**：輸入 [開始日期]\*\*\*\* 和 [結束日期]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2dc09-147">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="2dc09-148">**收到時間**：輸入 [開始日期]\*\*\*\* 和 [結束日期]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2dc09-148">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="2dc09-149">**隔離原因**：</span><span class="sxs-lookup"><span data-stu-id="2dc09-149">**Quarantine reason**:</span></span>

     - <span data-ttu-id="2dc09-150">**大量郵件**</span><span class="sxs-lookup"><span data-stu-id="2dc09-150">**Bulk**</span></span>

     - <span data-ttu-id="2dc09-151">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="2dc09-151">**Spam**</span></span>

     - <span data-ttu-id="2dc09-152">**網路釣魚** (2020 年 4 月起)</span><span class="sxs-lookup"><span data-stu-id="2dc09-152">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="2dc09-153">若要清除篩選，按一下 [清除]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2dc09-153">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="2dc09-154">若要隱藏 [篩選] 飛出視窗，再按一下 [篩選]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2dc09-154">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="2dc09-155">使用 [結果排序依據]\*\*\*\* (預設為 [郵件識別碼]\*\*\*\* 按鈕) 和對應值來尋找特定郵件。</span><span class="sxs-lookup"><span data-stu-id="2dc09-155">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="2dc09-156">不支援萬用字元。</span><span class="sxs-lookup"><span data-stu-id="2dc09-156">Wildcards aren't supported.</span></span> <span data-ttu-id="2dc09-157">您可以依下列值進行搜尋：</span><span class="sxs-lookup"><span data-stu-id="2dc09-157">You can search by the following values:</span></span>

   - <span data-ttu-id="2dc09-158">**郵件識別碼**：郵件的全域唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="2dc09-158">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="2dc09-159">如果您在清單中選取某個郵件，出現的 [詳細資料]\*\*\*\* 飛出窗格中就會出現 [郵件識別碼]\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="2dc09-159">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="2dc09-160">系統管理員可以使用 [郵件追蹤][](message-trace-scc.md) 來尋找郵件及其對應的郵件識別碼值。</span><span class="sxs-lookup"><span data-stu-id="2dc09-160">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="2dc09-161">**寄件者電子郵件地址**：單一寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="2dc09-161">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="2dc09-162">**收件者電子郵件地址**：單一收件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="2dc09-162">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="2dc09-163">**主旨**：使用郵件的完整主旨。</span><span class="sxs-lookup"><span data-stu-id="2dc09-163">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="2dc09-164">搜尋時不會區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="2dc09-164">The search is not case-sensitive.</span></span>

   <span data-ttu-id="2dc09-165">輸入搜尋準則後，請按一下![重新整理按鈕](../media/scc-quarantine-refresh.png) [重新整理]\*\*\*\* 來篩選結果。</span><span class="sxs-lookup"><span data-stu-id="2dc09-165">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="2dc09-166">當您找到特定隔離郵件後，選取該郵件即可檢視其詳細資料，並對其採取動作 (例如檢視、釋出、下載或刪除郵件)。</span><span class="sxs-lookup"><span data-stu-id="2dc09-166">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="2dc09-167">匯出郵件結果</span><span class="sxs-lookup"><span data-stu-id="2dc09-167">Export message results</span></span>

1. <span data-ttu-id="2dc09-168">選取您感興趣的郵件，然後按一下 [匯出結果]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2dc09-168">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="2dc09-169">在提醒您讓瀏覽器視窗保持開啟的確認訊息中，按一下 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2dc09-169">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="2dc09-170">匯出作業準備就緒時，便可為 .csv 檔案命名並選擇下載位置。</span><span class="sxs-lookup"><span data-stu-id="2dc09-170">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="2dc09-171">檢視隔離郵件詳細資料</span><span class="sxs-lookup"><span data-stu-id="2dc09-171">View quarantined message details</span></span>

<span data-ttu-id="2dc09-172">當您選取清單中的電子郵件訊息時，[詳細資料]\*\*\*\* 飛出窗格中會出現下列郵件詳細資料：</span><span class="sxs-lookup"><span data-stu-id="2dc09-172">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="2dc09-173">**郵件識別碼**：郵件的全域唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="2dc09-173">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="2dc09-174">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="2dc09-174">**Sender address**</span></span>

- <span data-ttu-id="2dc09-175">**收到日期**：收到郵件的日期/時間。</span><span class="sxs-lookup"><span data-stu-id="2dc09-175">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="2dc09-176">**主旨**</span><span class="sxs-lookup"><span data-stu-id="2dc09-176">**Subject**</span></span>

- <span data-ttu-id="2dc09-177">**隔離原因**：顯示是否已將郵件視為**垃圾郵件**、**大量郵件**或 (2020 年 4 月起) **網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="2dc09-177">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="2dc09-178">**收件者**：如果郵件包含多個收件者，則必須按一下 [預覽郵件]\*\*\*\* 或 [檢視郵件標頭]\*\*\*\* 以查看完整的收件者清單。</span><span class="sxs-lookup"><span data-stu-id="2dc09-178">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="2dc09-179">**到期**：郵件會自動從隔離區永久刪除的日期/時間。</span><span class="sxs-lookup"><span data-stu-id="2dc09-179">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="2dc09-180">**已釋出給**：該封郵件曾釋出至的所有電子郵件地址 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="2dc09-180">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="2dc09-181">**尚未釋出給**：該封郵件尚未釋出至的所有電子郵件地址 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="2dc09-181">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="2dc09-182">對隔離的電子郵件採取動作</span><span class="sxs-lookup"><span data-stu-id="2dc09-182">Take action on quarantined email</span></span>

<span data-ttu-id="2dc09-183">選取郵件之後，便可以在 [詳細資料]\*\*\*\* 飛出窗格中選擇要如何處理郵件：</span><span class="sxs-lookup"><span data-stu-id="2dc09-183">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="2dc09-184">**釋出郵件**：在出現的飛出窗格中，選擇是否要 [向 Microsoft 回報郵件以便分析]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2dc09-184">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="2dc09-185">預設會選取此選項，並向 Microsoft 回報錯誤隔離的郵件屬於誤判。</span><span class="sxs-lookup"><span data-stu-id="2dc09-185">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="2dc09-186">完成時，請按一下 [釋出郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2dc09-186">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="2dc09-187">**檢視郵件標頭**：選擇此連結來查看郵件標頭文字。</span><span class="sxs-lookup"><span data-stu-id="2dc09-187">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="2dc09-188">若要深入分析標頭欄位和值，請將郵件標頭文字複製到您的剪貼簿，然後選擇 [Microsoft 郵件標頭分析器]\*\*\*\* 來移至遠端連線分析程式 (如果您想在不離開 Office 365 的情況下完成這項工作，請按一下滑鼠右鍵並選擇 [在新索引標籤中開啟]\*\*\*\*)。</span><span class="sxs-lookup"><span data-stu-id="2dc09-188">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="2dc09-189">將郵件標頭貼至 [郵件標頭分析器] 區段的頁面上，並選擇 [分析標頭]\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="2dc09-189">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="2dc09-190">**預覽郵件**：在出現的飛出窗格中，選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="2dc09-190">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="2dc09-191">**原始碼檢視**：顯示已停用所有連結的郵件內文 HTML 版本。</span><span class="sxs-lookup"><span data-stu-id="2dc09-191">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="2dc09-192">**文字檢視**：以純文字顯示郵件內文。</span><span class="sxs-lookup"><span data-stu-id="2dc09-192">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="2dc09-193">**下載郵件**：在出現的飛出窗格中，選取 [我了解下載此郵件的風險]\*\*\*\* 以使用 .eml 格式儲存郵件的本機複本。</span><span class="sxs-lookup"><span data-stu-id="2dc09-193">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="2dc09-194">**從隔離區中移除**：當您在出現的警告中按一下 [是]\*\*\*\* 之後，郵件就會立即遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="2dc09-194">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="2dc09-195">完成時，請按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2dc09-195">When you're finished, click **Close**.</span></span>

<span data-ttu-id="2dc09-196">如果您未釋出或移除郵件，則郵件會在預設的隔離保留期間到期後遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="2dc09-196">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="2dc09-197">對多個隔離的電子郵件採取動作</span><span class="sxs-lookup"><span data-stu-id="2dc09-197">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="2dc09-198">當您選取清單中的多個隔離郵件 (最多 100 個) 時，隨即會出現 [大量動作]\*\*\*\* 飛出窗格供您採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="2dc09-198">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="2dc09-199">**釋出郵件**：這些選項與您釋出單一郵件時的選項相同，差別只在您無法選取 [將郵件釋出給特定收件者]\*\*\*\*；您只能選取 [將郵件釋出給所有收件者]\*\*\*\* 或 [將郵件釋出給其他人]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2dc09-199">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="2dc09-200">**刪除郵件**：在出現的警告中按一下 [是]\*\*\*\* 之後，郵件就會立即遭到刪除，而不會傳送給原始收件者。</span><span class="sxs-lookup"><span data-stu-id="2dc09-200">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="2dc09-201">完成時，請按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2dc09-201">When you're finished, click **Close**.</span></span>
