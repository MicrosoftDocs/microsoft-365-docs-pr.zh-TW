---
title: 在 Office 365 中以系統管理員身分管理被隔離的郵件和檔案
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: 系統管理員可以針對所有使用者，查看、發行和刪除所有類型的隔離郵件。 只有系統管理員可以管理被隔離為惡意程式碼、高可信度網路釣魚或郵件流程規則（傳輸規則）結果的郵件。
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857070"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a><span data-ttu-id="a1e02-104">在 Office 365 中以系統管理員身分管理被隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="a1e02-104">Manage quarantined messages and files as an admin in Office 365</span></span>

<span data-ttu-id="a1e02-105">在沒有 Exchange Online 信箱的 Exchange Online 或獨立 Exchange Online Protection （EOP）組織中，隔離區會在 Office 365 組織中包含可能有害或有害的郵件。</span><span class="sxs-lookup"><span data-stu-id="a1e02-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="a1e02-106">如需詳細資訊，請參閱[Office 365 中的隔離](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="a1e02-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="a1e02-107">系統管理員可以針對所有使用者，查看、發行和刪除所有類型的隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="a1e02-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="a1e02-108">只有系統管理員可以管理被隔離為惡意程式碼、高可信度網路釣魚或郵件流程規則（也稱為傳輸規則）結果的郵件。</span><span class="sxs-lookup"><span data-stu-id="a1e02-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="a1e02-109">系統管理員也可以將誤報報告給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="a1e02-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="a1e02-110">使用 Office 365 高級威脅防護（ATP）的組織中的系統管理員，也可以在 SharePoint Online、商務 OneDrive 商務和 Microsoft 小組中，查看、下載和刪除隔離的檔案。</span><span class="sxs-lookup"><span data-stu-id="a1e02-110">Admins in organizations with Office 365 Advance Threat Protection (ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="a1e02-111">您可以在安全性 & 規範中心或 PowerShell （Office 365 客戶的 Exchange Online PowerShell）中查看及管理隔離的郵件;Exchange Online Protection PowerShell 適用于獨立 EOP 客戶）。</span><span class="sxs-lookup"><span data-stu-id="a1e02-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a1e02-112">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="a1e02-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a1e02-113">若要開啟 Office 365 安全性 & 規範中心，請移<https://protection.office.com>至。</span><span class="sxs-lookup"><span data-stu-id="a1e02-113">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="a1e02-114">若要直接開啟 [隔離] 頁面， <https://protection.office.com/quarantine>請移至。</span><span class="sxs-lookup"><span data-stu-id="a1e02-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="a1e02-115">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a1e02-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a1e02-116">若要連接至 Exchange Online Protection PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a1e02-116">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a1e02-117">您必須已獲指派許可權，才可以系統管理員身分管理隔離。許可權是由安全性 & 合規性中心內的**隔離**角色所控制。</span><span class="sxs-lookup"><span data-stu-id="a1e02-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="a1e02-118">根據預設，此角色會指派給安全性 & 合規性中心內的**組織管理**（全域管理員）、**隔離系統管理員**和**安全性管理員**角色群組。</span><span class="sxs-lookup"><span data-stu-id="a1e02-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="a1e02-119">如需詳細資訊，請參閱[Office 365 Security & 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="a1e02-119">For more information, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="a1e02-120">隔離的郵件會在自動刪除之前保留在預設時間段內：</span><span class="sxs-lookup"><span data-stu-id="a1e02-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="a1e02-121">反垃圾郵件原則（垃圾郵件、網路釣魚和大量電子郵件）隔離的郵件：30天。</span><span class="sxs-lookup"><span data-stu-id="a1e02-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="a1e02-122">這是預設值和最大值。</span><span class="sxs-lookup"><span data-stu-id="a1e02-122">This is the default and maximum value.</span></span> <span data-ttu-id="a1e02-123">若要設定此值，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a1e02-123">To configure this value, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="a1e02-124">郵件流程規則隔離的郵件（規則動作會將**郵件傳遞至主控隔離區**）：30天。</span><span class="sxs-lookup"><span data-stu-id="a1e02-124">Messages quarantined by mail flow rules (the rule action is **Deliver the message to the hosted quarantine**): 30 days.</span></span> <span data-ttu-id="a1e02-125">您無法變更此值。</span><span class="sxs-lookup"><span data-stu-id="a1e02-125">You can't change this value.</span></span>

  - <span data-ttu-id="a1e02-126">包含惡意程式碼的郵件：15天。</span><span class="sxs-lookup"><span data-stu-id="a1e02-126">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="a1e02-127">當郵件從隔離區到期時，您無法復原。</span><span class="sxs-lookup"><span data-stu-id="a1e02-127">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="a1e02-128">使用安全性 & 合規性中心管理隔離的電子郵件</span><span class="sxs-lookup"><span data-stu-id="a1e02-128">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="a1e02-129">查看隔離的電子郵件</span><span class="sxs-lookup"><span data-stu-id="a1e02-129">View quarantined email</span></span>

1. <span data-ttu-id="a1e02-130">在 [安全性與合規性中心] 中，移至「**威脅管理** \> 」**檢查** \> **隔離**。</span><span class="sxs-lookup"><span data-stu-id="a1e02-130">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="a1e02-131">確認 [被**隔離的視圖**] 設定為預設值**電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="a1e02-131">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="a1e02-132">您可以按一下可用的欄標題，排序結果。</span><span class="sxs-lookup"><span data-stu-id="a1e02-132">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="a1e02-133">按一下 [**修改欄**] 以顯示最多7欄。</span><span class="sxs-lookup"><span data-stu-id="a1e02-133">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="a1e02-134">預設值會以星號（<sup>\*</sup>）標示：</span><span class="sxs-lookup"><span data-stu-id="a1e02-134">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="a1e02-135">**收到**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a1e02-135">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="a1e02-136">**發送**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a1e02-136">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="a1e02-137">**主題**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a1e02-137">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="a1e02-138">**隔離原因**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a1e02-138">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="a1e02-139">**釋放？**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a1e02-139">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="a1e02-140">**原則類型**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a1e02-140">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="a1e02-141">**到期**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a1e02-141">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="a1e02-142">**收件者**</span><span class="sxs-lookup"><span data-stu-id="a1e02-142">**Recipient**</span></span>

   - <span data-ttu-id="a1e02-143">**郵件識別碼**</span><span class="sxs-lookup"><span data-stu-id="a1e02-143">**Message ID**</span></span>

   - <span data-ttu-id="a1e02-144">**原則名稱**</span><span class="sxs-lookup"><span data-stu-id="a1e02-144">**Policy name**</span></span>

   - <span data-ttu-id="a1e02-145">**大小**</span><span class="sxs-lookup"><span data-stu-id="a1e02-145">**Size**</span></span>

   - <span data-ttu-id="a1e02-146">**Direction**</span><span class="sxs-lookup"><span data-stu-id="a1e02-146">**Direction**</span></span>

   <span data-ttu-id="a1e02-147">當您完成時，按一下 [**儲存**]，或按一下 [**設為預設**]。</span><span class="sxs-lookup"><span data-stu-id="a1e02-147">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="a1e02-148">若要篩選結果，請按一下 [**篩選**]。</span><span class="sxs-lookup"><span data-stu-id="a1e02-148">To filter the results, click **Filter**.</span></span> <span data-ttu-id="a1e02-149">可用的篩選包括：</span><span class="sxs-lookup"><span data-stu-id="a1e02-149">The available filters are:</span></span>

   - <span data-ttu-id="a1e02-150">**到期時間**：篩選郵件會從隔離區到期：</span><span class="sxs-lookup"><span data-stu-id="a1e02-150">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="a1e02-151">**今天**</span><span class="sxs-lookup"><span data-stu-id="a1e02-151">**Today**</span></span>

     - <span data-ttu-id="a1e02-152">**今後2天**</span><span class="sxs-lookup"><span data-stu-id="a1e02-152">**Next 2 days**</span></span>

     - <span data-ttu-id="a1e02-153">**未來7天**</span><span class="sxs-lookup"><span data-stu-id="a1e02-153">**Next 7 days**</span></span>

     - <span data-ttu-id="a1e02-154">**自訂**：輸入**開始日期**和**結束日期**。</span><span class="sxs-lookup"><span data-stu-id="a1e02-154">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="a1e02-155">**接收時間**：輸入**開始日期**和**結束日期**。</span><span class="sxs-lookup"><span data-stu-id="a1e02-155">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="a1e02-156">**隔離原因**：</span><span class="sxs-lookup"><span data-stu-id="a1e02-156">**Quarantine reason**:</span></span>

     - <span data-ttu-id="a1e02-157">**原則**：郵件符合郵件流程規則（也稱為傳輸規則）的條件。</span><span class="sxs-lookup"><span data-stu-id="a1e02-157">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="a1e02-158">**大量郵件**</span><span class="sxs-lookup"><span data-stu-id="a1e02-158">**Bulk**</span></span>

     - <span data-ttu-id="a1e02-159">**釣魚**</span><span class="sxs-lookup"><span data-stu-id="a1e02-159">**Phish**</span></span>

     - <span data-ttu-id="a1e02-160">**惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="a1e02-160">**Malware**</span></span>

     - <span data-ttu-id="a1e02-161">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="a1e02-161">**Spam**</span></span>

     - <span data-ttu-id="a1e02-162">**高信賴網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="a1e02-162">**High Confidence Phish**</span></span>

   - <span data-ttu-id="a1e02-163">**電子郵件收件**者：所有使用者或僅傳送給您的郵件。</span><span class="sxs-lookup"><span data-stu-id="a1e02-163">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="a1e02-164">使用者只能管理傳送給他們的隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="a1e02-164">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="a1e02-165">若要清除篩選，請按一下 [**清除**]。</span><span class="sxs-lookup"><span data-stu-id="a1e02-165">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="a1e02-166">若要隱藏 [篩選] 浮出控制項，請再次按一下 [**篩選**]。</span><span class="sxs-lookup"><span data-stu-id="a1e02-166">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="a1e02-167">使用**排序結果**（預設為**郵件識別碼**按鈕）和對應值以尋找特定郵件。</span><span class="sxs-lookup"><span data-stu-id="a1e02-167">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="a1e02-168">不支援萬用字元。</span><span class="sxs-lookup"><span data-stu-id="a1e02-168">Wildcards aren't supported.</span></span> <span data-ttu-id="a1e02-169">您可以依下列值進行搜尋：</span><span class="sxs-lookup"><span data-stu-id="a1e02-169">You can search by the following values:</span></span>

   - <span data-ttu-id="a1e02-170">**郵件識別碼**：郵件的全域唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="a1e02-170">**Message ID**: The globally unique identifier of the message.</span></span>

        <span data-ttu-id="a1e02-171">例如，您使用[郵件追蹤](message-trace-scc.md)尋找傳送給組織中使用者的郵件，而您判斷郵件已被隔離而非傳遞。</span><span class="sxs-lookup"><span data-stu-id="a1e02-171">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="a1e02-172">請務必包含完整的郵件識別碼值，其中可能包含角括弧（\<\>）。</span><span class="sxs-lookup"><span data-stu-id="a1e02-172">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="a1e02-173">例如：`<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。</span><span class="sxs-lookup"><span data-stu-id="a1e02-173">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="a1e02-174">**寄件者電子郵件地址**：單一寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a1e02-174">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="a1e02-175">**收件者電子郵件地址**：單一收件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a1e02-175">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="a1e02-176">主旨 **：使用**整個郵件主題。</span><span class="sxs-lookup"><span data-stu-id="a1e02-176">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="a1e02-177">搜尋不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="a1e02-177">The search is not case-sensitive.</span></span>

   <span data-ttu-id="a1e02-178">輸入搜尋準則之後，請按一下![[重新整理按鈕](../media/scc-quarantine-refresh.png) **重新**整理] 以篩選結果。</span><span class="sxs-lookup"><span data-stu-id="a1e02-178">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="a1e02-179">找到特定隔離郵件之後，請選取該郵件以查看其詳細資料，並對其採取動作（例如，view、release、下載中心或 delete the message）。</span><span class="sxs-lookup"><span data-stu-id="a1e02-179">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="a1e02-180">匯出郵件結果</span><span class="sxs-lookup"><span data-stu-id="a1e02-180">Export message results</span></span>

1. <span data-ttu-id="a1e02-181">選取您想要的訊息，然後按一下 [**匯出結果**]。</span><span class="sxs-lookup"><span data-stu-id="a1e02-181">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="a1e02-182">在確認訊息中按一下 **[是]** ，警告您保持瀏覽器視窗的開啟狀態。</span><span class="sxs-lookup"><span data-stu-id="a1e02-182">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="a1e02-183">當您匯出準備好時，您可以命名並選擇 .csv 檔案的下載位置。</span><span class="sxs-lookup"><span data-stu-id="a1e02-183">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="a1e02-184">查看隔離的郵件詳細資料</span><span class="sxs-lookup"><span data-stu-id="a1e02-184">View quarantined message details</span></span>

<span data-ttu-id="a1e02-185">當您在清單中選取一封電子郵件時，[**詳細資料**] 彈出窗格中會顯示下列郵件詳細資料：</span><span class="sxs-lookup"><span data-stu-id="a1e02-185">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a1e02-186">**郵件識別碼**：郵件的全域唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="a1e02-186">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="a1e02-187">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="a1e02-187">**Sender address**</span></span>

- <span data-ttu-id="a1e02-188">**已接收**：收到郵件的日期/時間。</span><span class="sxs-lookup"><span data-stu-id="a1e02-188">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="a1e02-189">**Subject**</span><span class="sxs-lookup"><span data-stu-id="a1e02-189">**Subject**</span></span>

- <span data-ttu-id="a1e02-190">**隔離原因**：顯示郵件是否已被識別為**垃圾**郵件、**大量**、**網路釣魚詐騙**、符合郵件流程規則（**傳輸規則**），或被識別為包含**惡意**代碼。</span><span class="sxs-lookup"><span data-stu-id="a1e02-190">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="a1e02-191">收件**者：如果**郵件包含多個收件者，則需要按一下 [**預覽郵件**] 或 [ **View message header** ]，以查看完整的收件者清單。</span><span class="sxs-lookup"><span data-stu-id="a1e02-191">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="a1e02-192">**Expires**：從隔離區中自動和永久刪除郵件的日期/時間。</span><span class="sxs-lookup"><span data-stu-id="a1e02-192">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="a1e02-193">**已釋出給**：該封郵件曾釋出至的所有電子郵件地址 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="a1e02-193">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="a1e02-194">尚未**發行至**：郵件尚未發行的所有電子郵件地址（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="a1e02-194">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="a1e02-195">對隔離的電子郵件採取動作</span><span class="sxs-lookup"><span data-stu-id="a1e02-195">Take action on quarantined email</span></span>

<span data-ttu-id="a1e02-196">選取郵件後，您可以在 [**詳細資料**] 彈出窗格中，針對郵件執行的動作有好幾個選項：</span><span class="sxs-lookup"><span data-stu-id="a1e02-196">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a1e02-197">**Release message**：在出現的飛入窗格中，選擇下列選項：</span><span class="sxs-lookup"><span data-stu-id="a1e02-197">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="a1e02-198">**將郵件報告給 Microsoft 進行分析**：預設會選取此選項，並將錯誤隔離的郵件以誤報形式報告給 microsoft。</span><span class="sxs-lookup"><span data-stu-id="a1e02-198">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="a1e02-199">如果郵件被隔離為垃圾郵件、大量、網路釣魚或包含惡意程式碼，則也會向 Microsoft 垃圾郵件分析小組報告該郵件。</span><span class="sxs-lookup"><span data-stu-id="a1e02-199">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="a1e02-200">視其分析而定，可能會調整全服務垃圾郵件篩選規則，以允許郵件通過。</span><span class="sxs-lookup"><span data-stu-id="a1e02-200">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="a1e02-201">選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="a1e02-201">Choose one of the following options:</span></span>

    - <span data-ttu-id="a1e02-202">**放開郵件給所有收件者**</span><span class="sxs-lookup"><span data-stu-id="a1e02-202">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="a1e02-203">**將郵件發佈給特定的收件者**</span><span class="sxs-lookup"><span data-stu-id="a1e02-203">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="a1e02-204">**放開其他人員的訊息**</span><span class="sxs-lookup"><span data-stu-id="a1e02-204">**Release messages to other people**</span></span>

  <span data-ttu-id="a1e02-205">當您完成時，按一下 [**放開郵件**]。</span><span class="sxs-lookup"><span data-stu-id="a1e02-205">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="a1e02-206">關於釋放郵件的附注：</span><span class="sxs-lookup"><span data-stu-id="a1e02-206">Notes about releasing messages:</span></span>

  - <span data-ttu-id="a1e02-207">您無法將郵件多次發佈到相同的收件者。</span><span class="sxs-lookup"><span data-stu-id="a1e02-207">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="a1e02-208">只有尚未收到郵件的收件者會出現在可能的收件者清單中。</span><span class="sxs-lookup"><span data-stu-id="a1e02-208">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="a1e02-209">**View message header**：選擇此連結以查看郵件頭文字。</span><span class="sxs-lookup"><span data-stu-id="a1e02-209">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="a1e02-210">若要深入分析標頭欄位及值，請將郵件頭文字複製到您的剪貼簿，然後選擇 [ **Microsoft Message Header analyzer** ] 移至遠端連線分析程式（按一下滑鼠右鍵，然後選擇 [在新索引標籤**中開啟]** ，如果您不想讓 Office 365 完成這項工作）。</span><span class="sxs-lookup"><span data-stu-id="a1e02-210">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="a1e02-211">將郵件頭貼到 [郵件頭分析器] 區段的頁面上，然後選擇 [**分析標頭**：]</span><span class="sxs-lookup"><span data-stu-id="a1e02-211">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="a1e02-212">**預覽郵件**：在出現的飛入窗格中，選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="a1e02-212">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="a1e02-213">**來源視圖**：顯示已停用所有連結的郵件內文的 HTML 版本。</span><span class="sxs-lookup"><span data-stu-id="a1e02-213">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="a1e02-214">**文字視圖**：以純文字顯示郵件內文。</span><span class="sxs-lookup"><span data-stu-id="a1e02-214">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="a1e02-215">**從隔離區移除**：在出現的警告中，按一下 [**是]** 之後，就會立即刪除郵件，而不會傳送至原始收件者。</span><span class="sxs-lookup"><span data-stu-id="a1e02-215">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="a1e02-216">**下載郵件**：在出現的快顯視窗中，選取 [**我瞭解下載此郵件的風險**]，以以 .eml 格式儲存郵件的本機複本。</span><span class="sxs-lookup"><span data-stu-id="a1e02-216">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="a1e02-217">**Submit message**：在出現的飛入窗格中，選擇下列選項：</span><span class="sxs-lookup"><span data-stu-id="a1e02-217">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="a1e02-218">**物件類型**：**電子郵件**（預設值）、 **URL**或**附件**。</span><span class="sxs-lookup"><span data-stu-id="a1e02-218">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="a1e02-219">**提交格式**：**網路消息識別碼**（預設值，具有 [**網路消息識別碼**] 方塊中的對應值 **）或檔案**（流覽至 [本地 .eml] 或 [.msg] 檔案）。</span><span class="sxs-lookup"><span data-stu-id="a1e02-219">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="a1e02-220">請注意，如果您**選取 [檔案]，然後**選取 [**網路消息識別碼**]，初始值便會消失。</span><span class="sxs-lookup"><span data-stu-id="a1e02-220">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="a1e02-221">收件**者：輸入**郵件的原始收件者，或按一下 [全**選**] 識別所有收件者。</span><span class="sxs-lookup"><span data-stu-id="a1e02-221">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="a1e02-222">您也可以按一下 [**全選**]，然後選擇性地移除個別收件者。</span><span class="sxs-lookup"><span data-stu-id="a1e02-222">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="a1e02-223">**提交原因**：**應該未封鎖**（預設）或**應該封鎖**。</span><span class="sxs-lookup"><span data-stu-id="a1e02-223">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="a1e02-224">當您完成時，按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="a1e02-224">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="a1e02-225">如果您未放開或移除郵件，當預設的隔離保留期間到期時，它會被刪除。</span><span class="sxs-lookup"><span data-stu-id="a1e02-225">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="a1e02-226">對多個隔離的電子郵件採取動作</span><span class="sxs-lookup"><span data-stu-id="a1e02-226">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="a1e02-227">當您在清單中選取多個隔離郵件（最多100）時，會出現 [**大量動作**] 飛入窗格，您可以在其中採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="a1e02-227">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="a1e02-228">**放開郵件**：這些選項與您發佈單一郵件時的選項相同，只是您不能選取 [將**郵件發佈給特定**的收件者]。您只能選取 [**發行訊息給所有**收件者] 或 [**向其他人發佈郵件**]。</span><span class="sxs-lookup"><span data-stu-id="a1e02-228">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="a1e02-229">**刪除郵件**：在出現的警告中，按一下 [**是]** 之後，就會立即刪除郵件，而不會傳送至原始收件者。</span><span class="sxs-lookup"><span data-stu-id="a1e02-229">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="a1e02-230">完成後，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="a1e02-230">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="a1e02-231">僅 ATP：使用安全性 & 合規性中心管理隔離的檔案</span><span class="sxs-lookup"><span data-stu-id="a1e02-231">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="a1e02-232">本節中隔離檔的程式僅適用于 ATP 方案1和 Plan 2 訂閱者。</span><span class="sxs-lookup"><span data-stu-id="a1e02-232">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="a1e02-233">在具有 ATP 的組織中，系統管理員可以在 SharePoint Online、商務 OneDrive 商務和 Microsoft 小組中管理隔離的檔案。</span><span class="sxs-lookup"><span data-stu-id="a1e02-233">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="a1e02-234">查看隔離的檔案</span><span class="sxs-lookup"><span data-stu-id="a1e02-234">View quarantined files</span></span>

1. <span data-ttu-id="a1e02-235">在 [安全性與合規性中心] 中，移至「**威脅管理** \> 」**檢查** \> **隔離**。</span><span class="sxs-lookup"><span data-stu-id="a1e02-235">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="a1e02-236">變更**隔離**為**預設值檔的**視圖。</span><span class="sxs-lookup"><span data-stu-id="a1e02-236">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="a1e02-237">您可以按一下可用的欄標題，依序排序欄位。</span><span class="sxs-lookup"><span data-stu-id="a1e02-237">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="a1e02-238">您可以按一下可用的欄標題，排序結果。</span><span class="sxs-lookup"><span data-stu-id="a1e02-238">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="a1e02-239">按一下 [**修改欄**] 以顯示最多7欄。</span><span class="sxs-lookup"><span data-stu-id="a1e02-239">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="a1e02-240">預設欄會以星號（<sup>\*</sup>）標示：</span><span class="sxs-lookup"><span data-stu-id="a1e02-240">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="a1e02-241">**使用者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a1e02-241">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="a1e02-242">**位置**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a1e02-242">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="a1e02-243">**檔案名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a1e02-243">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="a1e02-244">**檔案 URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a1e02-244">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="a1e02-245">**檔案大小**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a1e02-245">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="a1e02-246">**到期**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a1e02-246">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="a1e02-247">**釋放？**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a1e02-247">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="a1e02-248">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="a1e02-248">**Detected by**</span></span>

   - <span data-ttu-id="a1e02-249">**修改時間**</span><span class="sxs-lookup"><span data-stu-id="a1e02-249">**Modified by time**</span></span>

4. <span data-ttu-id="a1e02-250">若要篩選結果，請按一下 [**篩選**]。</span><span class="sxs-lookup"><span data-stu-id="a1e02-250">To filter the results, click **Filter**.</span></span> <span data-ttu-id="a1e02-251">可用的篩選包括：</span><span class="sxs-lookup"><span data-stu-id="a1e02-251">The available filters are:</span></span>

   - <span data-ttu-id="a1e02-252">**到期時間**：篩選郵件會從隔離區到期：</span><span class="sxs-lookup"><span data-stu-id="a1e02-252">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="a1e02-253">**今天**</span><span class="sxs-lookup"><span data-stu-id="a1e02-253">**Today**</span></span>

     - <span data-ttu-id="a1e02-254">**今後2天**</span><span class="sxs-lookup"><span data-stu-id="a1e02-254">**Next 2 days**</span></span>

     - <span data-ttu-id="a1e02-255">**未來7天**</span><span class="sxs-lookup"><span data-stu-id="a1e02-255">**Next 7 days**</span></span>

     - <span data-ttu-id="a1e02-256">自訂的日期/時間範圍。</span><span class="sxs-lookup"><span data-stu-id="a1e02-256">A custom date/time range.</span></span>

   - <span data-ttu-id="a1e02-257">**接收時間**</span><span class="sxs-lookup"><span data-stu-id="a1e02-257">**Received time**</span></span>

   - <span data-ttu-id="a1e02-258">**隔離原因**：唯一可用的值為**惡意**代碼。</span><span class="sxs-lookup"><span data-stu-id="a1e02-258">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="a1e02-259">找到特定隔離的檔案之後，請選取檔案以查看其詳細資料，並對其採取動作（例如，view、release、下載中心或 delete message）。</span><span class="sxs-lookup"><span data-stu-id="a1e02-259">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="a1e02-260">匯出檔結果</span><span class="sxs-lookup"><span data-stu-id="a1e02-260">Export file results</span></span>

1. <span data-ttu-id="a1e02-261">選取您想要的檔，然後按一下 [**匯出結果**]。</span><span class="sxs-lookup"><span data-stu-id="a1e02-261">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="a1e02-262">在確認訊息中按一下 **[是]** ，警告您保持瀏覽器視窗的開啟狀態。</span><span class="sxs-lookup"><span data-stu-id="a1e02-262">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="a1e02-263">當您匯出準備好時，您可以命名並選擇 .csv 檔案的下載位置。</span><span class="sxs-lookup"><span data-stu-id="a1e02-263">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="a1e02-264">查看隔離檔詳細資料</span><span class="sxs-lookup"><span data-stu-id="a1e02-264">View quarantined file details</span></span>

<span data-ttu-id="a1e02-265">當您選取清單中的檔案時，[**詳細資料**] 彈出窗格中會顯示下列檔案詳細資料：</span><span class="sxs-lookup"><span data-stu-id="a1e02-265">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a1e02-266">**檔案名稱**</span><span class="sxs-lookup"><span data-stu-id="a1e02-266">**File Name**</span></span>

- <span data-ttu-id="a1e02-267">檔案**url**：定義檔案位置的 url （例如，在 SharePoint Online 中）。</span><span class="sxs-lookup"><span data-stu-id="a1e02-267">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="a1e02-268">**在上偵測到惡意內容**隔離檔的日期/時間。</span><span class="sxs-lookup"><span data-stu-id="a1e02-268">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="a1e02-269">**Expires**：將從隔離區中刪除檔案的日期。</span><span class="sxs-lookup"><span data-stu-id="a1e02-269">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="a1e02-270">偵測**者**： ATP （高級威脅防護）或 Microsoft 的反惡意程式碼引擎。</span><span class="sxs-lookup"><span data-stu-id="a1e02-270">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="a1e02-271">**釋放？**</span><span class="sxs-lookup"><span data-stu-id="a1e02-271">**Released?**</span></span>

- <span data-ttu-id="a1e02-272">**惡意軟體名稱**</span><span class="sxs-lookup"><span data-stu-id="a1e02-272">**Malware Name**</span></span>

- <span data-ttu-id="a1e02-273">**檔識別碼**：檔的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="a1e02-273">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="a1e02-274">**檔案大小**：以 kb 為單位。</span><span class="sxs-lookup"><span data-stu-id="a1e02-274">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="a1e02-275">**組織**您組織的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="a1e02-275">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="a1e02-276">**上次修改日期**</span><span class="sxs-lookup"><span data-stu-id="a1e02-276">**Last modified**</span></span>

- <span data-ttu-id="a1e02-277">**修改者**：上次修改檔案的使用者。</span><span class="sxs-lookup"><span data-stu-id="a1e02-277">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="a1e02-278">**安全雜湊演算法 256-位（SHA-256）值**：您可以使用此雜湊值，在其他信譽存放區或您環境中的其他位置識別檔案。</span><span class="sxs-lookup"><span data-stu-id="a1e02-278">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="a1e02-279">對隔離的檔案採取動作</span><span class="sxs-lookup"><span data-stu-id="a1e02-279">Take action on quarantined files</span></span>

<span data-ttu-id="a1e02-280">當您選取清單中的檔案時，您可以對 [**詳細資料**] 彈出窗格中的檔案採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="a1e02-280">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a1e02-281">**發行**檔案：選取（預設值）或取消選取 [ **Microsoft for analysis**]，然後按一下 [**發行**檔案]。</span><span class="sxs-lookup"><span data-stu-id="a1e02-281">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="a1e02-282">**下載檔案**</span><span class="sxs-lookup"><span data-stu-id="a1e02-282">**Download file**</span></span>

- <span data-ttu-id="a1e02-283">**從隔離區移除檔案**</span><span class="sxs-lookup"><span data-stu-id="a1e02-283">**Remove file from quarantine**</span></span>

<span data-ttu-id="a1e02-284">如果您未放開或移除檔案，則會在預設的隔離保留期間到期時刪除這些檔案。</span><span class="sxs-lookup"><span data-stu-id="a1e02-284">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="a1e02-285">對多個隔離檔的動作</span><span class="sxs-lookup"><span data-stu-id="a1e02-285">Actions on multiple quarantined files</span></span>

<span data-ttu-id="a1e02-286">當您在清單中選取多個隔離的檔案（最多100個）時，會出現 [**大量動作**] 飛入窗格，您可以在其中採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="a1e02-286">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="a1e02-287">**發行檔**</span><span class="sxs-lookup"><span data-stu-id="a1e02-287">**Release files**</span></span>

- <span data-ttu-id="a1e02-288">**刪除**檔案：在出現的警告中，按一下 [**是]** 後，就會立即刪除檔案。</span><span class="sxs-lookup"><span data-stu-id="a1e02-288">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

<span data-ttu-id="a1e02-289">完成後，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="a1e02-289">When you're finished, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="a1e02-290">使用 Exchange Online PowerShell 或獨立 Exchange Online Protection PowerShell 來查看及管理隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="a1e02-290">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="a1e02-291">您用來在隔離區中查看及管理郵件和檔案的 Cmdlet 如下：</span><span class="sxs-lookup"><span data-stu-id="a1e02-291">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="a1e02-292">Delete-Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="a1e02-292">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="a1e02-293">Export-Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="a1e02-293">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="a1e02-294">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="a1e02-294">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="a1e02-295">[預覽-get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage)：請注意，此 Cmdlet 只適用于 SharePoint Online、商務 OneDrive 或小組的 ATP 中的電子郵件，而非惡意程式碼檔案。</span><span class="sxs-lookup"><span data-stu-id="a1e02-295">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="a1e02-296">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="a1e02-296">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
