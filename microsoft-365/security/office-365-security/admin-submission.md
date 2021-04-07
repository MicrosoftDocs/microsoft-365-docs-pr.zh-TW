---
title: 系統管理報送
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用安全性 & 合規性中心內的提交入口網站，將可疑的電子郵件、可疑網路釣魚郵件、垃圾郵件和其他可能有害的郵件、URLs 和檔案提交至 Microsoft 進行掃描。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e0975d5b6c2d29c94a30f7bbc703221b80217761
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599872"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="d13a0-103">使用系統管理提交，將可疑的垃圾郵件、網路釣魚詐騙、URL 和檔案提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="d13a0-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d13a0-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="d13a0-104">**Applies to**</span></span>
- [<span data-ttu-id="d13a0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d13a0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d13a0-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="d13a0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="d13a0-107">在使用 Exchange Online 信箱的 Microsoft 365 組織中，系統管理員可以使用安全性 & 合規性中心內的提交入口網站，將電子郵件訊息、URLs 和附件提交給 Microsoft 以供掃描。</span><span class="sxs-lookup"><span data-stu-id="d13a0-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="d13a0-108">當您提交電子郵件訊息時，您會收到：</span><span class="sxs-lookup"><span data-stu-id="d13a0-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="d13a0-109">**電子郵件驗證檢查**：傳送電子郵件時的驗證是否已通過或失敗的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d13a0-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="d13a0-110">**原則點擊**：有關任何可能允許或封鎖內送電子郵件進入您租使用者之原則的資訊，請覆寫我們的服務篩選 verdicts。</span><span class="sxs-lookup"><span data-stu-id="d13a0-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="d13a0-111">「**負載信譽/引爆**：檢查郵件中的任何 URLs 和附件。</span><span class="sxs-lookup"><span data-stu-id="d13a0-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="d13a0-112">**評分分析**：檢查是否有惡意的「人工 graders 完成」。</span><span class="sxs-lookup"><span data-stu-id="d13a0-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d13a0-113">在所有承租人中都不會進行負載信譽/引爆和評分分析。</span><span class="sxs-lookup"><span data-stu-id="d13a0-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="d13a0-114">當資料不應該保留租使用者界限以符合合規性目的時，就會封鎖資訊，避免進入組織外部。</span><span class="sxs-lookup"><span data-stu-id="d13a0-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="d13a0-115">如需其他方式將電子郵件訊息、URLs 和附件提交給 Microsoft，請參閱 [向 Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="d13a0-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d13a0-116">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="d13a0-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d13a0-117">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="d13a0-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d13a0-118">若要直接移至 **提交** 頁面，請使用 <https://protection.office.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="d13a0-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="d13a0-119">若要將郵件和檔案提交給 Microsoft，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="d13a0-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="d13a0-120">在 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md)內的 **組織管理** 或 **安全性讀者**。</span><span class="sxs-lookup"><span data-stu-id="d13a0-120">**Organization Management** or **Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="d13a0-121">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)中的 **組織管理**。</span><span class="sxs-lookup"><span data-stu-id="d13a0-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="d13a0-122">請注意，此角色群組的成員資格是 [查看使用者送至自訂信箱的使用者](#view-user-submissions-to-the-custom-mailbox) ，如本文稍後所述。</span><span class="sxs-lookup"><span data-stu-id="d13a0-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="d13a0-123">如需使用者如何提交郵件和檔案給 Microsoft 的詳細資訊，請參閱 [向 Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="d13a0-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="d13a0-124">向 Microsoft 報告可疑內容</span><span class="sxs-lookup"><span data-stu-id="d13a0-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="d13a0-125">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **提交**]，確認您在 [系統 **管理提交** ] 索引標籤上，然後按一下 [ **新增提交**]。</span><span class="sxs-lookup"><span data-stu-id="d13a0-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="d13a0-126">使用看似送出的 **新** 送出控制項，如下列各節所述提交郵件、URL 或附件。</span><span class="sxs-lookup"><span data-stu-id="d13a0-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="d13a0-127">將可疑的電子郵件提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="d13a0-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="d13a0-128">在 [ **物件類型** ] 區段中，選取 [ **電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="d13a0-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="d13a0-129">在 [ **提交格式** ] 區段中，使用下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="d13a0-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="d13a0-130">**網路消息識別碼**：這是在郵件中 **X-MS-Exchange-Organization-網路 Message-Id** 標頭中可用的 GUID 值，或是隔離郵件中的 **X Office365-篩選關聯識別碼** 標頭中可用的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="d13a0-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="d13a0-131">檔案：按一下 **[選擇** 檔案]。</span><span class="sxs-lookup"><span data-stu-id="d13a0-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="d13a0-132">在開啟的對話方塊中，尋找並選取 .eml 或 .msg 檔案，然後按一下 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="d13a0-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d13a0-133">將郵件送出多久30天，已暫時為 Office 365 客戶的 Defender 停用。</span><span class="sxs-lookup"><span data-stu-id="d13a0-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="d13a0-134">系統管理員只可以回復7天。</span><span class="sxs-lookup"><span data-stu-id="d13a0-134">Admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="d13a0-135">**在 [收** 件者] 區段中，指定您想要執行原則檢查的一或多個收件者。</span><span class="sxs-lookup"><span data-stu-id="d13a0-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="d13a0-136">原則檢查會決定是否因使用者或組織原則而略過掃描的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d13a0-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="d13a0-137">在 [ **提交原因** ] 區段中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="d13a0-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="d13a0-138">**不應該封鎖**</span><span class="sxs-lookup"><span data-stu-id="d13a0-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="d13a0-139">**應該已封鎖**：請選取 **[垃圾郵件**]、[ **網路釣魚**] 或 [ **惡意** 代碼]。</span><span class="sxs-lookup"><span data-stu-id="d13a0-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="d13a0-140">如果您不確定，請使用您的最佳判斷。</span><span class="sxs-lookup"><span data-stu-id="d13a0-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="d13a0-141">完成作業後，請按一下 [ **提交** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d13a0-141">When you're finished, click the **Submit** button.</span></span>

   ![URL 提交範例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="d13a0-143">將可疑 URL 傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="d13a0-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="d13a0-144">在 [ **物件類型** ] 區段中，選取 [ **URL**]。</span><span class="sxs-lookup"><span data-stu-id="d13a0-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="d13a0-145">在出現的方塊中，輸入完整的 URL (例如， `https://www.fabrikam.com/marketing.html`) 。</span><span class="sxs-lookup"><span data-stu-id="d13a0-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="d13a0-146">在 [ **提交原因** ] 區段中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="d13a0-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="d13a0-147">**不應該封鎖**</span><span class="sxs-lookup"><span data-stu-id="d13a0-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="d13a0-148">**應該已封鎖**：請選取 [ **網路釣魚** 或 **惡意** 代碼]。</span><span class="sxs-lookup"><span data-stu-id="d13a0-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="d13a0-149">完成作業後，請按一下 [ **提交** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d13a0-149">When you're finished, click the **Submit** button.</span></span>

   ![電子郵件提交範例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="d13a0-151">將可疑檔提交至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="d13a0-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="d13a0-152">在 [ **物件類型** ] 區段中，選取 [ **附件**]。</span><span class="sxs-lookup"><span data-stu-id="d13a0-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="d13a0-153">按一下 **[選擇** 檔案]。</span><span class="sxs-lookup"><span data-stu-id="d13a0-153">Click **Choose File**.</span></span> <span data-ttu-id="d13a0-154">在開啟的對話方塊中，尋找並選取檔，然後按一下 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="d13a0-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="d13a0-155">在 [ **提交原因** ] 區段中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="d13a0-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="d13a0-156">**不應該封鎖**</span><span class="sxs-lookup"><span data-stu-id="d13a0-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="d13a0-157">**應該已封鎖**： **惡意** 代碼是唯一的選擇，而且會自動加以選取。</span><span class="sxs-lookup"><span data-stu-id="d13a0-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="d13a0-158">完成作業後，請按一下 [ **提交** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d13a0-158">When you're finished, click the **Submit** button.</span></span>

   ![附件提交範例](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="d13a0-160">查看提交進行分析的專案</span><span class="sxs-lookup"><span data-stu-id="d13a0-160">View items Submitted for analysis</span></span>

<span data-ttu-id="d13a0-161">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **報送**]，確認您已在 [已 **提交進行分析** ] 索引標籤上</span><span class="sxs-lookup"><span data-stu-id="d13a0-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="d13a0-162">在頁面頂端附近，您可以輸入開始日期、結束日期和 (預設值) 您可以依 **提交識別碼** (指派給每個提交) 的 GUID 值進行篩選，方法是在方塊中輸入值，然後按一下 [重新整理] ![ 按鈕 ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="d13a0-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="d13a0-163">Update</span><span class="sxs-lookup"><span data-stu-id="d13a0-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="d13a0-164">若要變更篩選準則，請按一下 [ **提交識別碼** ] 按鈕，然後選擇下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="d13a0-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="d13a0-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d13a0-165">**Sender**</span></span>
- <span data-ttu-id="d13a0-166">**Subject/URL/檔案名**</span><span class="sxs-lookup"><span data-stu-id="d13a0-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="d13a0-167">**提交者**</span><span class="sxs-lookup"><span data-stu-id="d13a0-167">**Submitted by**</span></span>
- <span data-ttu-id="d13a0-168">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="d13a0-168">**Submission type**</span></span>
- <span data-ttu-id="d13a0-169">**狀態**</span><span class="sxs-lookup"><span data-stu-id="d13a0-169">**Status**</span></span>

![管理員報送的篩選選項](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="d13a0-171">若要匯出結果，請按一下頁面頂端附近的 [ **匯出** ]，然後選取 [ **圖表資料** 或 **表格**]。</span><span class="sxs-lookup"><span data-stu-id="d13a0-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="d13a0-172">在出現的對話方塊中，儲存 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="d13a0-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="d13a0-173">在圖形下方有三個索引標籤： **電子郵件** (預設) 、 **URL** 及 **附件**。</span><span class="sxs-lookup"><span data-stu-id="d13a0-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="d13a0-174">查看系統管理電子郵件報送</span><span class="sxs-lookup"><span data-stu-id="d13a0-174">View admin email submissions</span></span>

<span data-ttu-id="d13a0-175">按一下 [ **電子郵件** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d13a0-175">Click the **Email** tab.</span></span>

<span data-ttu-id="d13a0-176">您可以按一下頁面底部附近的 [ **欄選項** ] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="d13a0-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d13a0-177">**Date**</span><span class="sxs-lookup"><span data-stu-id="d13a0-177">**Date**</span></span>
- <span data-ttu-id="d13a0-178">**提交識別碼**：指派給每個提交的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="d13a0-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="d13a0-179">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d13a0-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d13a0-180">**主旨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d13a0-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="d13a0-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d13a0-181">**Sender**</span></span>
- <span data-ttu-id="d13a0-182">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d13a0-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="d13a0-183">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="d13a0-183">**Submission type**</span></span>
- <span data-ttu-id="d13a0-184">**傳遞原因**</span><span class="sxs-lookup"><span data-stu-id="d13a0-184">**Delivery reason**</span></span>
- <span data-ttu-id="d13a0-185">**地位**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d13a0-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="d13a0-186"><sup>\*</sup> 如果您按一下此值，詳細資訊就會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="d13a0-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="d13a0-187">系統管理員提交重新掃描詳細資料</span><span class="sxs-lookup"><span data-stu-id="d13a0-187">Admin submission rescan details</span></span>

<span data-ttu-id="d13a0-188">在系統管理報送中送出的郵件會重新掃描，並顯示在 [詳細資料] 快顯視窗中的結果：</span><span class="sxs-lookup"><span data-stu-id="d13a0-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="d13a0-189">寄件者在傳遞電子郵件時，電子郵件驗證是否失敗。</span><span class="sxs-lookup"><span data-stu-id="d13a0-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="d13a0-190">任何有關可能會影響或覆寫郵件決策的原則點擊的資訊。</span><span class="sxs-lookup"><span data-stu-id="d13a0-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="d13a0-191">目前的引爆結果，查看郵件中所含的 URL 或檔案是否惡意。</span><span class="sxs-lookup"><span data-stu-id="d13a0-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="d13a0-192">Graders 的意見反應。</span><span class="sxs-lookup"><span data-stu-id="d13a0-192">Feedback from graders.</span></span>

<span data-ttu-id="d13a0-193">如果發現覆寫，則應該會在幾分鐘內完成重新掃描。</span><span class="sxs-lookup"><span data-stu-id="d13a0-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="d13a0-194">如果電子郵件驗證或傳遞中沒有問題，則不會受到覆寫的影響，來自 graders 的意見反應可能需要一天。</span><span class="sxs-lookup"><span data-stu-id="d13a0-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="d13a0-195">查看管理 URL 提交</span><span class="sxs-lookup"><span data-stu-id="d13a0-195">View admin URL submissions</span></span>

<span data-ttu-id="d13a0-196">按一下 [ **URL** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d13a0-196">Click the **URL** tab.</span></span>

<span data-ttu-id="d13a0-197">您可以按一下頁面底部附近的 [ **欄選項** ] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="d13a0-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d13a0-198">**Date**</span><span class="sxs-lookup"><span data-stu-id="d13a0-198">**Date**</span></span>
- <span data-ttu-id="d13a0-199">**提交識別碼**</span><span class="sxs-lookup"><span data-stu-id="d13a0-199">**Submission ID**</span></span>
- <span data-ttu-id="d13a0-200">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d13a0-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d13a0-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d13a0-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="d13a0-202">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="d13a0-202">**Submission type**</span></span>
- <span data-ttu-id="d13a0-203">**地位**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d13a0-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="d13a0-204"><sup>\*</sup> 如果您按一下此值，詳細資訊就會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="d13a0-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="d13a0-205">View admin 附件提交</span><span class="sxs-lookup"><span data-stu-id="d13a0-205">View admin attachment submissions</span></span>

<span data-ttu-id="d13a0-206">按一下 [ **附件** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d13a0-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="d13a0-207">您可以按一下頁面底部附近的 [ **欄選項** ] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="d13a0-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d13a0-208">**Date**</span><span class="sxs-lookup"><span data-stu-id="d13a0-208">**Date**</span></span>
- <span data-ttu-id="d13a0-209">**提交識別碼**</span><span class="sxs-lookup"><span data-stu-id="d13a0-209">**Submission ID**</span></span>
- <span data-ttu-id="d13a0-210">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d13a0-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d13a0-211">**檔案名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d13a0-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="d13a0-212">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="d13a0-212">**Submission type**</span></span>
- <span data-ttu-id="d13a0-213">**地位**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d13a0-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="d13a0-214"><sup>\*</sup> 如果您按一下此值，詳細資訊就會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="d13a0-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="d13a0-215">查看 Microsoft 的使用者報送</span><span class="sxs-lookup"><span data-stu-id="d13a0-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="d13a0-216">如果您已部署 [報表訊息增益集](enable-the-report-message-add-in.md)、 [報告網路釣魚增益集](enable-the-report-phish-add-in.md)或人員使用 [網頁型 Outlook 中內建的報表](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)，您可以在 [ **使用者報送** ] 索引標籤上看到要報告的使用者。</span><span class="sxs-lookup"><span data-stu-id="d13a0-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="d13a0-217">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **提交**]。</span><span class="sxs-lookup"><span data-stu-id="d13a0-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="d13a0-218">選取 [ **使用者報送** ] 索引標籤，然後按一下 [ **新增提交**]。</span><span class="sxs-lookup"><span data-stu-id="d13a0-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="d13a0-219">您可以按一下頁面底部附近的 [ **欄選項** ] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="d13a0-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d13a0-220">**提交于**</span><span class="sxs-lookup"><span data-stu-id="d13a0-220">**Submitted on**</span></span>
- <span data-ttu-id="d13a0-221">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d13a0-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d13a0-222">**主旨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d13a0-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="d13a0-223">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d13a0-223">**Sender**</span></span>
- <span data-ttu-id="d13a0-224">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d13a0-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="d13a0-225">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="d13a0-225">**Submission type**</span></span>

<span data-ttu-id="d13a0-226"><sup>\*</sup> 如果您按一下此值，詳細資訊就會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="d13a0-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="d13a0-227">在頁面頂端附近，您可以輸入開始日期、結束日期和 (預設值) 您可以在 [收件者] 方塊中輸入值，然後按一下 [重新整理] 按鈕，以篩選收 **件** 者 ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="d13a0-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="d13a0-228">Update</span><span class="sxs-lookup"><span data-stu-id="d13a0-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="d13a0-229">若要變更篩選準則，請按一下 [ **寄件者** ] 按鈕，然後選擇下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="d13a0-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="d13a0-230">**寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="d13a0-230">**Sender domain**</span></span>
- <span data-ttu-id="d13a0-231">**主旨**</span><span class="sxs-lookup"><span data-stu-id="d13a0-231">**Subject**</span></span>
- <span data-ttu-id="d13a0-232">**提交者**</span><span class="sxs-lookup"><span data-stu-id="d13a0-232">**Submitted by**</span></span>
- <span data-ttu-id="d13a0-233">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="d13a0-233">**Submission type**</span></span>
- <span data-ttu-id="d13a0-234">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="d13a0-234">**Sender IP**</span></span>

![使用者提交的篩選選項](../../media/user-submissions-filter-options.png)

<span data-ttu-id="d13a0-236">若要匯出結果，請按一下頁面頂端附近的 [ **匯出** ]，然後選取 [ **圖表資料** 或 **表格**]。</span><span class="sxs-lookup"><span data-stu-id="d13a0-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="d13a0-237">在出現的對話方塊中，儲存 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="d13a0-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="d13a0-238">查看自訂信箱的使用者報送</span><span class="sxs-lookup"><span data-stu-id="d13a0-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="d13a0-239">**如果** 您已 [將自訂信箱設定](user-submission.md) 為接收使用者報告的郵件，您可以查看並提交傳遞到報表信箱的郵件。</span><span class="sxs-lookup"><span data-stu-id="d13a0-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="d13a0-240">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **提交**]。</span><span class="sxs-lookup"><span data-stu-id="d13a0-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="d13a0-241">選取 [ **自訂信箱** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d13a0-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="d13a0-242">您可以按一下頁面底部附近的 [ **欄選項** ] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="d13a0-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d13a0-243">**提交于**</span><span class="sxs-lookup"><span data-stu-id="d13a0-243">**Submitted on**</span></span>
- <span data-ttu-id="d13a0-244">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d13a0-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d13a0-245">**主旨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d13a0-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="d13a0-246">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d13a0-246">**Sender**</span></span>
- <span data-ttu-id="d13a0-247">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d13a0-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="d13a0-248">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="d13a0-248">**Submission type**</span></span>

<span data-ttu-id="d13a0-249">在頁面頂端附近，您可以輸入開始日期、結束日期，也可以透過在方塊中輸入值，然後按一下 [重新整理] 按鈕 **來篩選** ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="d13a0-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="d13a0-250">Update</span><span class="sxs-lookup"><span data-stu-id="d13a0-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="d13a0-251">若要匯出結果，請按一下頁面頂端附近的 [ **匯出** ]，然後選取 [ **圖表資料** 或 **表格**]。</span><span class="sxs-lookup"><span data-stu-id="d13a0-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="d13a0-252">在出現的對話方塊中，儲存 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="d13a0-252">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="d13a0-253">如果組織已設定為僅傳送至自訂信箱，將不會傳送報告的郵件以進行重新掃描，而且使用者報告的郵件入口網站將永遠會是空的。</span><span class="sxs-lookup"><span data-stu-id="d13a0-253">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="d13a0-254">撤銷使用者報送</span><span class="sxs-lookup"><span data-stu-id="d13a0-254">Undo user submissions</span></span>

<span data-ttu-id="d13a0-255">一旦使用者將可疑的電子郵件提交至自訂信箱，使用者和系統管理員就沒有任何可復原提交的選項。</span><span class="sxs-lookup"><span data-stu-id="d13a0-255">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="d13a0-256">如果使用者想要復原電子郵件，將可在 [刪除的郵件] 或 [垃圾郵件] 資料夾中復原。</span><span class="sxs-lookup"><span data-stu-id="d13a0-256">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="d13a0-257">從自訂信箱將郵件提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="d13a0-257">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="d13a0-258">如果您已將自訂信箱設定為在未傳送郵件給 Microsoft 的情況下截獲使用者報告的郵件，您可以尋找特定郵件並將其傳送給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="d13a0-258">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="d13a0-259">這會有效地將使用者提交權移至系統管理員提交。</span><span class="sxs-lookup"><span data-stu-id="d13a0-259">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="d13a0-260">在 [ **自訂信箱** ] 索引標籤上，選取清單中的訊息，按一下 [ **動作** ] 按鈕，然後進行下列其中一項選擇：</span><span class="sxs-lookup"><span data-stu-id="d13a0-260">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="d13a0-261">**報告清理**</span><span class="sxs-lookup"><span data-stu-id="d13a0-261">**Report clean**</span></span>
- <span data-ttu-id="d13a0-262">**報告網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="d13a0-262">**Report phishing**</span></span>
- <span data-ttu-id="d13a0-263">**報告惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="d13a0-263">**Report malware**</span></span>
- <span data-ttu-id="d13a0-264">**報告垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="d13a0-264">**Report spam**</span></span>

![動作按鈕上的選項](../../media/user-submission-custom-mailbox-action-button.png)
