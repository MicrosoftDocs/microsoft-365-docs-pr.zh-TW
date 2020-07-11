---
title: 以系統管理員身分管理被隔離的郵件與檔案
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
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何針對 Exchange Online Protection (EOP) 中的所有使用者，查看及管理隔離的郵件。 使用 Office 365 Advanced 威脅防護的組織中的系統管理員 (Office 365 ATP) 也可管理 SharePoint 線上、OneDrive 商務和 Microsoft 小組的隔離檔案。
ms.openlocfilehash: 5e7c594669cf910404badd85c35671c284d4d91e
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101678"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="cfc66-104">在 EOP 中管理隔離的郵件與檔案</span><span class="sxs-lookup"><span data-stu-id="cfc66-104">Manage quarantined messages and files as an admin in EOP</span></span>

<span data-ttu-id="cfc66-105">在擁有 Exchange Online 信箱的 Microsoft 365 組織中或是沒有 Exchange Online 信箱的獨立 Exchange Online Protection (EOP) 組織中，隔離區會保存可能有害或垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="cfc66-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="cfc66-106">如需詳細資訊，請參閱[在 EOP 中隔離的電子郵件訊息](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="cfc66-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="cfc66-107">系統管理員可以針對所有使用者，查看、發行和刪除所有類型的隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="cfc66-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="cfc66-108">只有系統管理員可以管理被隔離為惡意程式碼、高可信度網路釣魚的郵件，或郵件流程規則的結果 (也稱為傳輸規則) 。</span><span class="sxs-lookup"><span data-stu-id="cfc66-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="cfc66-109">系統管理員也可以將誤報報告給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="cfc66-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="cfc66-110">使用 Office 365 高級威脅防護的組織中的系統管理員 (Office 365 ATP) 也可以在 SharePoint 線上、商務用 OneDrive，以及 Microsoft 小組中查看、下載和刪除隔離的檔案。</span><span class="sxs-lookup"><span data-stu-id="cfc66-110">Admins in organizations with Office 365 Advance Threat Protection (Office 365 ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="cfc66-111">您可以使用 Exchange Online 中的信箱，在安全性 & 合規性中心或 PowerShell (Exchange Online 365 PowerShell 中查看及管理隔離的郵件;沒有 Exchange Online 信箱) 之組織的獨立 EOP PowerShell。</span><span class="sxs-lookup"><span data-stu-id="cfc66-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cfc66-112">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="cfc66-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cfc66-113">若要開啟安全性與合規性中心，請移至 <https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="cfc66-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="cfc66-114">若要直接開啟 [隔離區] 頁面，請移至 <https://protection.office.com/quarantine>。</span><span class="sxs-lookup"><span data-stu-id="cfc66-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="cfc66-115">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="cfc66-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="cfc66-116">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="cfc66-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="cfc66-117">您必須已獲指派許可權，才可以系統管理員身分管理隔離。許可權是由安全性 & 合規性中心內的**隔離**角色所控制。</span><span class="sxs-lookup"><span data-stu-id="cfc66-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="cfc66-118">根據預設，此角色會指派給 [安全性 & 規範中心] 中的 [**組織管理** (全域管理員]) 、[**隔離管理員**] 和 [**安全性管理員**] 角色群組。</span><span class="sxs-lookup"><span data-stu-id="cfc66-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="cfc66-119">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="cfc66-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="cfc66-120">隔離的郵件會在自動刪除之前保留在預設時間段內：</span><span class="sxs-lookup"><span data-stu-id="cfc66-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="cfc66-121">反垃圾郵件原則隔離的郵件 (的垃圾郵件、網路釣魚和大量電子郵件) ：30天。</span><span class="sxs-lookup"><span data-stu-id="cfc66-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="cfc66-122">這是預設值和最大值。</span><span class="sxs-lookup"><span data-stu-id="cfc66-122">This is the default and maximum value.</span></span> <span data-ttu-id="cfc66-123">若要設定此值，請參閱[設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cfc66-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="cfc66-124">包含惡意程式碼的郵件：15天。</span><span class="sxs-lookup"><span data-stu-id="cfc66-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="cfc66-125">當郵件從隔離區到期時，您無法復原。</span><span class="sxs-lookup"><span data-stu-id="cfc66-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="cfc66-126">使用安全性 & 合規性中心管理隔離的電子郵件</span><span class="sxs-lookup"><span data-stu-id="cfc66-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="cfc66-127">查看隔離的電子郵件</span><span class="sxs-lookup"><span data-stu-id="cfc66-127">View quarantined email</span></span>

1. <span data-ttu-id="cfc66-128">在「安全性與合規性中心」內，移至 [威脅管理]\*\*\*\* \> [檢閱]\*\*\*\* \> [隔離]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfc66-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="cfc66-129">確認 [被**隔離的視圖**] 設定為預設值**電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="cfc66-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="cfc66-130">您可以按一下可用資料行標題來排序結果。</span><span class="sxs-lookup"><span data-stu-id="cfc66-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="cfc66-131">按一下 [修改資料行]\*\*\*\* 可顯示最多七個資料行。</span><span class="sxs-lookup"><span data-stu-id="cfc66-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="cfc66-132">預設值會標上星號 (<sup>\*</sup>)：</span><span class="sxs-lookup"><span data-stu-id="cfc66-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="cfc66-133">**收到日期**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfc66-133">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="cfc66-134">**寄件者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfc66-134">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="cfc66-135">**主旨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfc66-135">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="cfc66-136">**隔離原因**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfc66-136">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="cfc66-137">**已釋出？**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfc66-137">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="cfc66-138">**原則類型**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfc66-138">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="cfc66-139">**收件者**</span><span class="sxs-lookup"><span data-stu-id="cfc66-139">**Recipient**</span></span>

   - <span data-ttu-id="cfc66-140">**郵件識別碼**</span><span class="sxs-lookup"><span data-stu-id="cfc66-140">**Message ID**</span></span>

   - <span data-ttu-id="cfc66-141">**原則名稱**</span><span class="sxs-lookup"><span data-stu-id="cfc66-141">**Policy name**</span></span>

   - <span data-ttu-id="cfc66-142">**大小**</span><span class="sxs-lookup"><span data-stu-id="cfc66-142">**Size**</span></span>

   - <span data-ttu-id="cfc66-143">**方向**</span><span class="sxs-lookup"><span data-stu-id="cfc66-143">**Direction**</span></span>

   <span data-ttu-id="cfc66-144">完成時，請按一下 [儲存]\*\*\*\*，或按一下 [設為預設值]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfc66-144">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="cfc66-145">若要篩選結果，請按一下 [篩選]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfc66-145">To filter the results, click **Filter**.</span></span> <span data-ttu-id="cfc66-146">可用的篩選條件如下：</span><span class="sxs-lookup"><span data-stu-id="cfc66-146">The available filters are:</span></span>

   - <span data-ttu-id="cfc66-147">**到期時間**：依郵件將於隔離區中到期的時間進行篩選：</span><span class="sxs-lookup"><span data-stu-id="cfc66-147">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="cfc66-148">**今天**</span><span class="sxs-lookup"><span data-stu-id="cfc66-148">**Today**</span></span>

     - <span data-ttu-id="cfc66-149">**未來 2 天**</span><span class="sxs-lookup"><span data-stu-id="cfc66-149">**Next 2 days**</span></span>

     - <span data-ttu-id="cfc66-150">**未來 7 天**</span><span class="sxs-lookup"><span data-stu-id="cfc66-150">**Next 7 days**</span></span>

     - <span data-ttu-id="cfc66-151">**自訂**：輸入 [開始日期]\*\*\*\* 和 [結束日期]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfc66-151">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="cfc66-152">**收到時間**：輸入 [開始日期]\*\*\*\* 和 [結束日期]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfc66-152">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="cfc66-153">**隔離原因**：</span><span class="sxs-lookup"><span data-stu-id="cfc66-153">**Quarantine reason**:</span></span>

     - <span data-ttu-id="cfc66-154">**原則**：郵件符合郵件流程規則的條件 (也稱為傳輸規則) 。</span><span class="sxs-lookup"><span data-stu-id="cfc66-154">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="cfc66-155">**大量郵件**</span><span class="sxs-lookup"><span data-stu-id="cfc66-155">**Bulk**</span></span>

     - <span data-ttu-id="cfc66-156">**網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="cfc66-156">**Phish**</span></span>

     - <span data-ttu-id="cfc66-157">**惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="cfc66-157">**Malware**</span></span>

     - <span data-ttu-id="cfc66-158">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="cfc66-158">**Spam**</span></span>

     - <span data-ttu-id="cfc66-159">**高信賴網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="cfc66-159">**High Confidence Phish**</span></span>

   - <span data-ttu-id="cfc66-160">**電子郵件收件**者：所有使用者或僅傳送給您的郵件。</span><span class="sxs-lookup"><span data-stu-id="cfc66-160">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="cfc66-161">使用者只能管理傳送給他們的隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="cfc66-161">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="cfc66-162">若要清除篩選，按一下 [清除]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfc66-162">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="cfc66-163">若要隱藏 [篩選] 飛出視窗，再按一下 [篩選]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfc66-163">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="cfc66-164">使用 [結果排序依據]\*\*\*\* (預設為 [郵件識別碼]\*\*\*\* 按鈕) 和對應值來尋找特定郵件。</span><span class="sxs-lookup"><span data-stu-id="cfc66-164">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="cfc66-165">不支援萬用字元。</span><span class="sxs-lookup"><span data-stu-id="cfc66-165">Wildcards aren't supported.</span></span> <span data-ttu-id="cfc66-166">您可以依下列值進行搜尋：</span><span class="sxs-lookup"><span data-stu-id="cfc66-166">You can search by the following values:</span></span>

   - <span data-ttu-id="cfc66-167">**郵件識別碼**：郵件的全域唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="cfc66-167">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="cfc66-168">例如，您使用[郵件追蹤](message-trace-scc.md)尋找傳送給組織中使用者的郵件，而您判斷郵件已被隔離而非傳遞。</span><span class="sxs-lookup"><span data-stu-id="cfc66-168">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="cfc66-169">請務必包含完整的郵件識別碼值，其中可能包含角括弧 (\<\>) 。</span><span class="sxs-lookup"><span data-stu-id="cfc66-169">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="cfc66-170">例如：`<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。</span><span class="sxs-lookup"><span data-stu-id="cfc66-170">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="cfc66-171">**寄件者電子郵件地址**：單一寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="cfc66-171">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="cfc66-172">**收件者電子郵件地址**：單一收件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="cfc66-172">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="cfc66-173">**主旨**：使用郵件的完整主旨。</span><span class="sxs-lookup"><span data-stu-id="cfc66-173">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="cfc66-174">搜尋時不會區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="cfc66-174">The search is not case-sensitive.</span></span>

   <span data-ttu-id="cfc66-175">輸入搜尋準則後，請按一下![重新整理按鈕](../../media/scc-quarantine-refresh.png) [重新整理]\*\*\*\* 來篩選結果。</span><span class="sxs-lookup"><span data-stu-id="cfc66-175">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="cfc66-176">當您找到特定隔離郵件後，選取該郵件即可檢視其詳細資料，並對其採取動作 (例如檢視、釋出、下載或刪除郵件)。</span><span class="sxs-lookup"><span data-stu-id="cfc66-176">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="cfc66-177">匯出郵件結果</span><span class="sxs-lookup"><span data-stu-id="cfc66-177">Export message results</span></span>

1. <span data-ttu-id="cfc66-178">選取您感興趣的郵件，然後按一下 [匯出結果]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfc66-178">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="cfc66-179">在提醒您讓瀏覽器視窗保持開啟的確認訊息中，按一下 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfc66-179">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="cfc66-180">匯出作業準備就緒時，便可為 .csv 檔案命名並選擇下載位置。</span><span class="sxs-lookup"><span data-stu-id="cfc66-180">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="cfc66-181">檢視隔離郵件詳細資料</span><span class="sxs-lookup"><span data-stu-id="cfc66-181">View quarantined message details</span></span>

<span data-ttu-id="cfc66-182">當您選取清單中的電子郵件訊息時，[詳細資料]\*\*\*\* 飛出窗格中會出現下列郵件詳細資料：</span><span class="sxs-lookup"><span data-stu-id="cfc66-182">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="cfc66-183">**郵件識別碼**：郵件的全域唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="cfc66-183">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="cfc66-184">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="cfc66-184">**Sender address**</span></span>

- <span data-ttu-id="cfc66-185">**收到日期**：收到郵件的日期/時間。</span><span class="sxs-lookup"><span data-stu-id="cfc66-185">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="cfc66-186">**主旨**</span><span class="sxs-lookup"><span data-stu-id="cfc66-186">**Subject**</span></span>

- <span data-ttu-id="cfc66-187">**隔離原因**：顯示郵件是否已識別為**垃圾**郵件、**大量**、**網路釣魚詐騙**、符合郵件流程規則 (**傳輸規則**) 或已識別為包含**惡意**代碼。</span><span class="sxs-lookup"><span data-stu-id="cfc66-187">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="cfc66-188">**收件者**：如果郵件包含多個收件者，則必須按一下 [預覽郵件]\*\*\*\* 或 [檢視郵件標頭]\*\*\*\* 以查看完整的收件者清單。</span><span class="sxs-lookup"><span data-stu-id="cfc66-188">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="cfc66-189">**到期**：郵件會自動從隔離區永久刪除的日期/時間。</span><span class="sxs-lookup"><span data-stu-id="cfc66-189">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="cfc66-190">**已釋出給**：該封郵件曾釋出至的所有電子郵件地址 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="cfc66-190">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="cfc66-191">**尚未釋出給**：該封郵件尚未釋出至的所有電子郵件地址 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="cfc66-191">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="cfc66-192">對隔離的電子郵件採取動作</span><span class="sxs-lookup"><span data-stu-id="cfc66-192">Take action on quarantined email</span></span>

<span data-ttu-id="cfc66-193">選取郵件後，您可以在 [**詳細資料**] 彈出窗格中，針對郵件執行的動作有好幾個選項：</span><span class="sxs-lookup"><span data-stu-id="cfc66-193">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="cfc66-194">**Release message**：在出現的飛入窗格中，選擇下列選項：</span><span class="sxs-lookup"><span data-stu-id="cfc66-194">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="cfc66-195">**將郵件報告給 Microsoft 進行分析**：預設會選取此選項，並將錯誤隔離的郵件以誤報形式報告給 microsoft。</span><span class="sxs-lookup"><span data-stu-id="cfc66-195">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="cfc66-196">如果郵件被隔離為垃圾郵件、大量、網路釣魚或包含惡意程式碼，則也會向 Microsoft 垃圾郵件分析小組報告該郵件。</span><span class="sxs-lookup"><span data-stu-id="cfc66-196">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="cfc66-197">視其分析而定，可能會調整全服務垃圾郵件篩選規則，以允許郵件通過。</span><span class="sxs-lookup"><span data-stu-id="cfc66-197">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="cfc66-198">選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="cfc66-198">Choose one of the following options:</span></span>

    - <span data-ttu-id="cfc66-199">**放開郵件給所有收件者**</span><span class="sxs-lookup"><span data-stu-id="cfc66-199">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="cfc66-200">**將郵件發佈給特定的收件者**</span><span class="sxs-lookup"><span data-stu-id="cfc66-200">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="cfc66-201">**放開其他人員的訊息**</span><span class="sxs-lookup"><span data-stu-id="cfc66-201">**Release messages to other people**</span></span>

  <span data-ttu-id="cfc66-202">完成時，請按一下 [釋出郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfc66-202">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="cfc66-203">關於釋放郵件的附注：</span><span class="sxs-lookup"><span data-stu-id="cfc66-203">Notes about releasing messages:</span></span>

  - <span data-ttu-id="cfc66-204">您無法將郵件多次發佈到相同的收件者。</span><span class="sxs-lookup"><span data-stu-id="cfc66-204">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="cfc66-205">只有尚未收到郵件的收件者會出現在可能的收件者清單中。</span><span class="sxs-lookup"><span data-stu-id="cfc66-205">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="cfc66-206">**檢視郵件標頭**：選擇此連結來查看郵件標頭文字。</span><span class="sxs-lookup"><span data-stu-id="cfc66-206">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="cfc66-207">若要深入分析標頭欄位和值，請將郵件標頭文字複製到您的剪貼簿，然後選擇 [Microsoft 郵件標頭分析器]\*\*\*\* 來移至遠端連線分析程式 (如果您想在不離開 Microsoft 365 的情況下完成這項工作，請按一下滑鼠右鍵並選擇 [在新索引標籤中開啟]\*\*\*\*)。</span><span class="sxs-lookup"><span data-stu-id="cfc66-207">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="cfc66-208">將郵件標頭貼至 [郵件標頭分析器] 區段的頁面上，並選擇 [分析標頭]\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="cfc66-208">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="cfc66-209">**預覽郵件**：在出現的飛出窗格中，選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="cfc66-209">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="cfc66-210">**原始碼檢視**：顯示已停用所有連結的郵件內文 HTML 版本。</span><span class="sxs-lookup"><span data-stu-id="cfc66-210">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="cfc66-211">**文字檢視**：以純文字顯示郵件內文。</span><span class="sxs-lookup"><span data-stu-id="cfc66-211">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="cfc66-212">**從隔離區移除**：在出現的警告中，按一下 [**是]** 之後，就會立即刪除郵件，而不會傳送至原始收件者。</span><span class="sxs-lookup"><span data-stu-id="cfc66-212">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="cfc66-213">**下載郵件**：在出現的飛出窗格中，選取 [我了解下載此郵件的風險]\*\*\*\* 以使用 .eml 格式儲存郵件的本機複本。</span><span class="sxs-lookup"><span data-stu-id="cfc66-213">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="cfc66-214">**Submit message**：在出現的飛入窗格中，選擇下列選項：</span><span class="sxs-lookup"><span data-stu-id="cfc66-214">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="cfc66-215">**物件類型**：**電子郵件** (預設) 、 **URL**或**附件**。</span><span class="sxs-lookup"><span data-stu-id="cfc66-215">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="cfc66-216">**提交格式**：**網路郵件識別碼** (預設值，並在 [**網路消息識別碼**] 方塊中顯示對應的值) 或**檔案 (流覽**至本地 .eml 或 .msg 檔案) 。</span><span class="sxs-lookup"><span data-stu-id="cfc66-216">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="cfc66-217">請注意，如果您**選取 [檔案]，然後**選取 [**網路消息識別碼**]，初始值便會消失。</span><span class="sxs-lookup"><span data-stu-id="cfc66-217">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="cfc66-218">收件**者：輸入**郵件的原始收件者，或按一下 [全**選**] 識別所有收件者。</span><span class="sxs-lookup"><span data-stu-id="cfc66-218">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="cfc66-219">您也可以按一下 [**全選**]，然後選擇性地移除個別收件者。</span><span class="sxs-lookup"><span data-stu-id="cfc66-219">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="cfc66-220">**提交原因**：**應該不會封鎖** (預設) 或**應該封鎖**。</span><span class="sxs-lookup"><span data-stu-id="cfc66-220">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="cfc66-221">當您完成時，按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="cfc66-221">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="cfc66-222">如果您未釋出或移除郵件，則郵件會在預設的隔離保留期間到期後遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="cfc66-222">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="cfc66-223">對多個隔離的電子郵件採取動作</span><span class="sxs-lookup"><span data-stu-id="cfc66-223">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="cfc66-224">當您選取清單中的多個隔離郵件 (最多 100 個) 時，隨即會出現 [大量動作]\*\*\*\* 飛出窗格供您採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="cfc66-224">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="cfc66-225">**釋出郵件**：這些選項與您釋出單一郵件時的選項相同，差別只在您無法選取 [將郵件釋出給特定收件者]\*\*\*\*；您只能選取 [將郵件釋出給所有收件者]\*\*\*\* 或 [將郵件釋出給其他人]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfc66-225">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="cfc66-226">請考慮下列案例： john@gmail.com 會將郵件傳送至 faith@contoso.com 和 john@subsidiary.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="cfc66-226">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="cfc66-227">Gmail 會將此郵件 bifurcates 成兩個副本，以在 Microsoft 中路由傳送至隔離區。</span><span class="sxs-lookup"><span data-stu-id="cfc66-227">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="cfc66-228">系統管理員會將這兩封郵件都發行至 admin@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="cfc66-228">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="cfc66-229">傳遞到達系統管理員信箱的第一個已發佈郵件。</span><span class="sxs-lookup"><span data-stu-id="cfc66-229">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="cfc66-230">第二個發行的郵件會被識別為重複傳遞，而且會略過。</span><span class="sxs-lookup"><span data-stu-id="cfc66-230">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="cfc66-231">如果郵件有相同的郵件識別碼和接收時間，便會將它識別為重複郵件。</span><span class="sxs-lookup"><span data-stu-id="cfc66-231">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="cfc66-232">**刪除郵件**：在出現的警告中按一下 [是]\*\*\*\* 之後，郵件就會立即遭到刪除，而不會傳送給原始收件者。</span><span class="sxs-lookup"><span data-stu-id="cfc66-232">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="cfc66-233">完成時，請按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfc66-233">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="cfc66-234">僅 ATP：使用安全性 & 合規性中心管理隔離的檔案</span><span class="sxs-lookup"><span data-stu-id="cfc66-234">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="cfc66-235">本節中隔離檔的程式僅適用于 ATP 方案1和 Plan 2 訂閱者。</span><span class="sxs-lookup"><span data-stu-id="cfc66-235">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="cfc66-236">在具有 ATP 的組織中，系統管理員可以在 SharePoint Online、商務 OneDrive 商務和 Microsoft 小組中管理隔離的檔案。</span><span class="sxs-lookup"><span data-stu-id="cfc66-236">In organizations with ATP, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="cfc66-237">查看隔離的檔案</span><span class="sxs-lookup"><span data-stu-id="cfc66-237">View quarantined files</span></span>

1. <span data-ttu-id="cfc66-238">在「安全性與合規性中心」內，移至 [威脅管理]\*\*\*\* \> [檢閱]\*\*\*\* \> [隔離]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfc66-238">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="cfc66-239">變更**隔離**為**預設值檔的**視圖。</span><span class="sxs-lookup"><span data-stu-id="cfc66-239">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="cfc66-240">您可以按一下可用的欄標題，依序排序欄位。</span><span class="sxs-lookup"><span data-stu-id="cfc66-240">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="cfc66-241">您可以按一下可用資料行標題來排序結果。</span><span class="sxs-lookup"><span data-stu-id="cfc66-241">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="cfc66-242">按一下 [修改資料行]\*\*\*\* 可顯示最多七個資料行。</span><span class="sxs-lookup"><span data-stu-id="cfc66-242">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="cfc66-243">預設的欄會以星號 () 標示 <sup>\*</sup> ：</span><span class="sxs-lookup"><span data-stu-id="cfc66-243">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="cfc66-244">**使用者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfc66-244">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="cfc66-245">**位置**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfc66-245">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="cfc66-246">**檔案名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfc66-246">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="cfc66-247">**檔案 URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfc66-247">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="cfc66-248">**檔案大小**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfc66-248">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="cfc66-249">**到期**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfc66-249">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="cfc66-250">**已釋出？**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfc66-250">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="cfc66-251">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="cfc66-251">**Detected by**</span></span>

   - <span data-ttu-id="cfc66-252">**修改時間**</span><span class="sxs-lookup"><span data-stu-id="cfc66-252">**Modified by time**</span></span>

4. <span data-ttu-id="cfc66-253">若要篩選結果，請按一下 [篩選]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfc66-253">To filter the results, click **Filter**.</span></span> <span data-ttu-id="cfc66-254">可用的篩選條件如下：</span><span class="sxs-lookup"><span data-stu-id="cfc66-254">The available filters are:</span></span>

   - <span data-ttu-id="cfc66-255">**到期時間**：依郵件將於隔離區中到期的時間進行篩選：</span><span class="sxs-lookup"><span data-stu-id="cfc66-255">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="cfc66-256">**今天**</span><span class="sxs-lookup"><span data-stu-id="cfc66-256">**Today**</span></span>

     - <span data-ttu-id="cfc66-257">**未來 2 天**</span><span class="sxs-lookup"><span data-stu-id="cfc66-257">**Next 2 days**</span></span>

     - <span data-ttu-id="cfc66-258">**未來 7 天**</span><span class="sxs-lookup"><span data-stu-id="cfc66-258">**Next 7 days**</span></span>

     - <span data-ttu-id="cfc66-259">自訂的日期/時間範圍。</span><span class="sxs-lookup"><span data-stu-id="cfc66-259">A custom date/time range.</span></span>

   - <span data-ttu-id="cfc66-260">**接收時間**</span><span class="sxs-lookup"><span data-stu-id="cfc66-260">**Received time**</span></span>

   - <span data-ttu-id="cfc66-261">**隔離原因**：唯一可用的值為**惡意**代碼。</span><span class="sxs-lookup"><span data-stu-id="cfc66-261">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="cfc66-262">找到特定隔離的檔案之後，請選取檔案以查看其詳細資料，並對其採取動作 (例如，view、release、下載中心或 delete message) 。</span><span class="sxs-lookup"><span data-stu-id="cfc66-262">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="cfc66-263">匯出檔結果</span><span class="sxs-lookup"><span data-stu-id="cfc66-263">Export file results</span></span>

1. <span data-ttu-id="cfc66-264">選取您想要的檔，然後按一下 [**匯出結果**]。</span><span class="sxs-lookup"><span data-stu-id="cfc66-264">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="cfc66-265">在提醒您讓瀏覽器視窗保持開啟的確認訊息中，按一下 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfc66-265">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="cfc66-266">匯出作業準備就緒時，便可為 .csv 檔案命名並選擇下載位置。</span><span class="sxs-lookup"><span data-stu-id="cfc66-266">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="cfc66-267">查看隔離檔詳細資料</span><span class="sxs-lookup"><span data-stu-id="cfc66-267">View quarantined file details</span></span>

<span data-ttu-id="cfc66-268">當您選取清單中的檔案時，[**詳細資料**] 彈出窗格中會顯示下列檔案詳細資料：</span><span class="sxs-lookup"><span data-stu-id="cfc66-268">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="cfc66-269">**檔案名稱**</span><span class="sxs-lookup"><span data-stu-id="cfc66-269">**File Name**</span></span>

- <span data-ttu-id="cfc66-270">檔案**url**：定義檔案位置的 url (例如，在 SharePoint 線上) 中。</span><span class="sxs-lookup"><span data-stu-id="cfc66-270">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="cfc66-271">**在上偵測到惡意內容**隔離檔的日期/時間。</span><span class="sxs-lookup"><span data-stu-id="cfc66-271">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="cfc66-272">**Expires**：將從隔離區中刪除檔案的日期。</span><span class="sxs-lookup"><span data-stu-id="cfc66-272">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="cfc66-273">偵測**者**： ATP (高級威脅防護) 或 Microsoft 的反惡意程式碼引擎。</span><span class="sxs-lookup"><span data-stu-id="cfc66-273">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="cfc66-274">**已釋出？**</span><span class="sxs-lookup"><span data-stu-id="cfc66-274">**Released?**</span></span>

- <span data-ttu-id="cfc66-275">**惡意軟體名稱**</span><span class="sxs-lookup"><span data-stu-id="cfc66-275">**Malware Name**</span></span>

- <span data-ttu-id="cfc66-276">**檔識別碼**：檔的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="cfc66-276">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="cfc66-277">**檔案大小**： KB (kb) 。</span><span class="sxs-lookup"><span data-stu-id="cfc66-277">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="cfc66-278">**組織**您組織的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="cfc66-278">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="cfc66-279">**上次修改日期**</span><span class="sxs-lookup"><span data-stu-id="cfc66-279">**Last modified**</span></span>

- <span data-ttu-id="cfc66-280">**修改者**：上次修改檔案的使用者。</span><span class="sxs-lookup"><span data-stu-id="cfc66-280">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="cfc66-281">**安全雜湊演算法 256-位 (SHA-256) 值**：您可以使用此雜湊值，在其他信譽存放區或您環境中的其他位置識別檔案。</span><span class="sxs-lookup"><span data-stu-id="cfc66-281">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="cfc66-282">對隔離的檔案採取動作</span><span class="sxs-lookup"><span data-stu-id="cfc66-282">Take action on quarantined files</span></span>

<span data-ttu-id="cfc66-283">當您選取清單中的檔案時，您可以對 [**詳細資料**] 彈出窗格中的檔案採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="cfc66-283">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="cfc66-284">**版本**檔案：選取 [ (預設值]) 或取消選取 [ **Microsoft for Analysis] 的報表**檔案，然後按一下 [**釋放檔**]。</span><span class="sxs-lookup"><span data-stu-id="cfc66-284">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="cfc66-285">**下載檔案**</span><span class="sxs-lookup"><span data-stu-id="cfc66-285">**Download file**</span></span>

- <span data-ttu-id="cfc66-286">**從隔離區移除檔案**</span><span class="sxs-lookup"><span data-stu-id="cfc66-286">**Remove file from quarantine**</span></span>

<span data-ttu-id="cfc66-287">如果您未放開或移除檔案，則會在預設的隔離保留期間到期時刪除這些檔案。</span><span class="sxs-lookup"><span data-stu-id="cfc66-287">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="cfc66-288">對多個隔離檔的動作</span><span class="sxs-lookup"><span data-stu-id="cfc66-288">Actions on multiple quarantined files</span></span>

<span data-ttu-id="cfc66-289">當您在清單中選取多個隔離的檔案 (直到 100) 時，會出現 [**大量動作**] 彈出窗格，您可以在其中採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="cfc66-289">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="cfc66-290">**發行檔**</span><span class="sxs-lookup"><span data-stu-id="cfc66-290">**Release files**</span></span>

- <span data-ttu-id="cfc66-291">**刪除**檔案：在出現的警告中，按一下 [**是]** 後，就會立即刪除檔案。</span><span class="sxs-lookup"><span data-stu-id="cfc66-291">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="cfc66-292">使用具有全域管理員許可權的工作或學校帳戶 (或適當的安全性 & 合規性中心角色) 在組織中，登入並[移至安全性 & 規範中心](../../compliance/go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="cfc66-292">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="cfc66-293">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 來查看及管理隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="cfc66-293">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="cfc66-294">您用來在隔離區中查看及管理郵件和檔案的 Cmdlet 如下：</span><span class="sxs-lookup"><span data-stu-id="cfc66-294">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="cfc66-295">Delete-Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="cfc66-295">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="cfc66-296">Export-Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="cfc66-296">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="cfc66-297">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="cfc66-297">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="cfc66-298">[預覽-get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)：請注意，此 Cmdlet 只適用于 SharePoint Online、商務 OneDrive 或小組的 ATP 中的電子郵件，而非惡意程式碼檔案。</span><span class="sxs-lookup"><span data-stu-id="cfc66-298">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="cfc66-299">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="cfc66-299">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
