---
title: 系統管理報送
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用安全性 & 合規性中心內的提交入口網站，將可疑的電子郵件、可疑網路釣魚郵件、垃圾郵件和其他可能有害的郵件、URLs 和檔案提交至 Microsoft 進行掃描。
ms.openlocfilehash: 7327768780e5db16e09e2b709c9c11344573c404
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659822"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="1bcfc-103">使用系統管理提交，將可疑的垃圾郵件、網路釣魚詐騙、URL 和檔案提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bcfc-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1bcfc-104">在使用 Exchange Online 信箱的 Microsoft 365 組織中，系統管理員可以使用安全性 & 合規性中心內的提交入口網站，將電子郵件訊息、URLs 和附件提交給 Microsoft 以供掃描。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="1bcfc-105">當您提交電子郵件時，您會收到任何可能允許內送電子郵件進入租使用者的原則，以及對郵件中的任何 URLs 和附件進行檢查的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="1bcfc-106">可能允許郵件的原則包括個別使用者的安全寄件者清單，以及租使用者層級原則，例如 Exchange 郵件流程規則 (也稱為 transport rules) 。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="1bcfc-107">如需其他方式將電子郵件訊息、URLs 和附件提交給 Microsoft，請參閱 [向 Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1bcfc-108">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="1bcfc-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1bcfc-109">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1bcfc-110">若要直接移至 **提交** 頁面，請使用 <https://protection.office.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="1bcfc-111">若要將郵件和檔案提交給 Microsoft，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="1bcfc-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="1bcfc-112">**組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員**。 </span><span class="sxs-lookup"><span data-stu-id="1bcfc-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="1bcfc-113">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的 **組織管理**。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="1bcfc-114">請注意，此角色群組的成員資格是 [查看使用者送至自訂信箱的使用者](#view-user-submissions-to-the-custom-mailbox) ，如本文稍後所述。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="1bcfc-115">如需使用者如何提交郵件和檔案給 Microsoft 的詳細資訊，請參閱 [向 Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="1bcfc-116">向 Microsoft 報告可疑內容</span><span class="sxs-lookup"><span data-stu-id="1bcfc-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="1bcfc-117">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **提交**]，確認您在 [系統 **管理提交** ] 索引標籤上，然後按一下 [ **新增提交**]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="1bcfc-118">使用看似送出的 **新** 送出控制項，如下列各節所述提交郵件、URL 或附件。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="1bcfc-119">將可疑的電子郵件提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bcfc-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="1bcfc-120">在 [ **物件類型** ] 區段中，選取 [ **電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="1bcfc-121">在 [ **提交格式** ] 區段中，使用下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="1bcfc-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="1bcfc-122">**網路消息識別碼**：這是在郵件中 **X-MS-Exchange-Organization-網路 Message-Id** 標頭中可用的 GUID 值，或是隔離郵件中的 **X Office365-篩選關聯識別碼** 標頭中可用的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="1bcfc-123">檔案：按一下 **[選擇** 檔案]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="1bcfc-124">在開啟的對話方塊中，尋找並選取 .eml 或 .msg 檔案，然後按一下 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1bcfc-125">管理員搭配 Office 的 Defender for Office 365 方案1或計畫2可將郵件提交為30天的舊郵件。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-125">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="1bcfc-126">其他系統管理員只可以回復7天。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-126">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="1bcfc-127">**在 [收** 件者] 區段中，指定您想要執行原則檢查的一或多個收件者。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-127">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="1bcfc-128">原則檢查會決定是否因使用者或組織原則而略過掃描的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-128">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="1bcfc-129">在 [ **提交原因** ] 區段中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="1bcfc-129">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="1bcfc-130">**不應該封鎖**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-130">**Should not have been blocked**</span></span>

   - <span data-ttu-id="1bcfc-131">**應該已封鎖**：請選取 **[垃圾郵件**]、[ **網路釣魚**] 或 [ **惡意** 代碼]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-131">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="1bcfc-132">如果您不確定，請使用您的最佳判斷。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-132">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="1bcfc-133">完成作業後，請按一下 [ **提交** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-133">When you're finished, click the **Submit** button.</span></span>

![URL 提交範例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="1bcfc-135">將可疑 URL 傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bcfc-135">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="1bcfc-136">在 [ **物件類型** ] 區段中，選取 [ **URL**]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-136">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="1bcfc-137">在出現的方塊中，輸入完整的 URL (例如， `https://www.fabrikam.com/marketing.html`) 。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-137">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="1bcfc-138">在 [ **提交原因** ] 區段中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="1bcfc-138">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="1bcfc-139">**不應該封鎖**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-139">**Should not have been blocked**</span></span>

   - <span data-ttu-id="1bcfc-140">**應該已封鎖**：請選取 [ **網路釣魚** 或 **惡意** 代碼]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-140">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="1bcfc-141">完成作業後，請按一下 [ **提交** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-141">When you're finished, click the **Submit** button.</span></span>

![電子郵件提交範例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="1bcfc-143">將可疑檔提交至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bcfc-143">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="1bcfc-144">在 [ **物件類型** ] 區段中，選取 [ **附件**]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-144">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="1bcfc-145">按一下 **[選擇** 檔案]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-145">Click **Choose File**.</span></span> <span data-ttu-id="1bcfc-146">在開啟的對話方塊中，尋找並選取檔，然後按一下 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-146">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="1bcfc-147">在 [ **提交原因** ] 區段中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="1bcfc-147">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="1bcfc-148">**不應該封鎖**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-148">**Should not have been blocked**</span></span>

   - <span data-ttu-id="1bcfc-149">**應該已封鎖**： **惡意** 代碼是唯一的選擇，而且會自動加以選取。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-149">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="1bcfc-150">完成作業後，請按一下 [ **提交** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-150">When you're finished, click the **Submit** button.</span></span>

![附件提交範例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="1bcfc-152">查看系統管理員報送</span><span class="sxs-lookup"><span data-stu-id="1bcfc-152">View admin submissions</span></span>

<span data-ttu-id="1bcfc-153">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **提交**]，確認您在 [系統 **管理提交** ] 索引標籤上，然後按一下 [ **新增提交**]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-153">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="1bcfc-154">在頁面頂端附近，您可以輸入開始日期、結束日期和 (預設值) 您可以依 **提交識別碼** (指派給每個提交) 的 GUID 值進行篩選，方法是在方塊中輸入值，然後按一下 [重新整理] ![ 按鈕 ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-154">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="1bcfc-155">Update</span><span class="sxs-lookup"><span data-stu-id="1bcfc-155">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="1bcfc-156">若要變更篩選準則，請按一下 [ **提交識別碼** ] 按鈕，然後選擇下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="1bcfc-156">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="1bcfc-157">**Sender**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-157">**Sender**</span></span>
- <span data-ttu-id="1bcfc-158">**Subject/URL/檔案名**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-158">**Subject/URL/File name**</span></span>
- <span data-ttu-id="1bcfc-159">**提交者**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-159">**Submitted by**</span></span>
- <span data-ttu-id="1bcfc-160">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-160">**Submission type**</span></span>
- <span data-ttu-id="1bcfc-161">**狀態**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-161">**Status**</span></span>

![管理員報送的篩選選項](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="1bcfc-163">若要匯出結果，請按一下頁面頂端附近的 [ **匯出** ]，然後選取 [ **圖表資料** 或 **表格**]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-163">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="1bcfc-164">在出現的對話方塊中，儲存 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-164">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="1bcfc-165">在圖形下方有三個索引標籤： **電子郵件** (預設) 、 **URL** 及 **附件**。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-165">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="1bcfc-166">查看系統管理電子郵件報送</span><span class="sxs-lookup"><span data-stu-id="1bcfc-166">View admin email submissions</span></span>

<span data-ttu-id="1bcfc-167">按一下 [ **電子郵件** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-167">Click the **Email** tab.</span></span>

<span data-ttu-id="1bcfc-168">您可以按一下頁面底部附近的 [ **欄選項** ] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="1bcfc-168">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="1bcfc-169">**Date**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-169">**Date**</span></span>
- <span data-ttu-id="1bcfc-170">**提交識別碼**：指派給每個提交的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-170">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="1bcfc-171">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1bcfc-171">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="1bcfc-172">**主旨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1bcfc-172">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="1bcfc-173">**Sender**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-173">**Sender**</span></span>
- <span data-ttu-id="1bcfc-174">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1bcfc-174">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="1bcfc-175">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-175">**Submission type**</span></span>
- <span data-ttu-id="1bcfc-176">**傳遞原因**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-176">**Delivery reason**</span></span>
- <span data-ttu-id="1bcfc-177">**地位**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1bcfc-177">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="1bcfc-178"><sup>\*</sup> 如果您按一下此值，詳細資訊就會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-178"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="1bcfc-179">系統管理員提交重新掃描詳細資料</span><span class="sxs-lookup"><span data-stu-id="1bcfc-179">Admin submission rescan details</span></span>

<span data-ttu-id="1bcfc-180">在系統管理報送中送出的郵件會重新掃描，並顯示在 [詳細資料] 快顯視窗中的結果：</span><span class="sxs-lookup"><span data-stu-id="1bcfc-180">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="1bcfc-181">傳遞時，如果寄件者的電子郵件驗證失敗。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-181">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="1bcfc-182">有關可能影響或覆寫郵件之任何原則點擊內容的資訊。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-182">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="1bcfc-183">目前的引爆結果，以查看郵件中所包含的 URLs 或檔案是否惡意。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-183">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="1bcfc-184">Graders 的意見反應。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-184">Feedback from graders.</span></span>

<span data-ttu-id="1bcfc-185">如果找到覆寫，重新掃描應該會在幾分鐘內完成。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-185">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="1bcfc-186">如果電子郵件驗證或傳遞中沒有問題，則不會受到覆寫的影響，來自 graders 的意見反應可能需要一天。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-186">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="1bcfc-187">查看管理 URL 提交</span><span class="sxs-lookup"><span data-stu-id="1bcfc-187">View admin URL submissions</span></span>

<span data-ttu-id="1bcfc-188">按一下 [ **URL** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-188">Click the **URL** tab.</span></span>

<span data-ttu-id="1bcfc-189">您可以按一下頁面底部附近的 [ **欄選項** ] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="1bcfc-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="1bcfc-190">**Date**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-190">**Date**</span></span>
- <span data-ttu-id="1bcfc-191">**提交識別碼**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-191">**Submission ID**</span></span>
- <span data-ttu-id="1bcfc-192">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1bcfc-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="1bcfc-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1bcfc-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="1bcfc-194">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-194">**Submission type**</span></span>
- <span data-ttu-id="1bcfc-195">**地位**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1bcfc-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="1bcfc-196"><sup>\*</sup> 如果您按一下此值，詳細資訊就會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="1bcfc-197">View admin 附件提交</span><span class="sxs-lookup"><span data-stu-id="1bcfc-197">View admin attachment submissions</span></span>

<span data-ttu-id="1bcfc-198">按一下 [ **附件** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="1bcfc-199">您可以按一下頁面底部附近的 [ **欄選項** ] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="1bcfc-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="1bcfc-200">**Date**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-200">**Date**</span></span>
- <span data-ttu-id="1bcfc-201">**提交識別碼**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-201">**Submission ID**</span></span>
- <span data-ttu-id="1bcfc-202">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1bcfc-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="1bcfc-203">**檔案名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1bcfc-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="1bcfc-204">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-204">**Submission type**</span></span>
- <span data-ttu-id="1bcfc-205">**地位**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1bcfc-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="1bcfc-206"><sup>\*</sup> 如果您按一下此值，詳細資訊就會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="1bcfc-207">查看 Microsoft 的使用者報送</span><span class="sxs-lookup"><span data-stu-id="1bcfc-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="1bcfc-208">如果您已部署 [報表訊息增益集](enable-the-report-message-add-in.md)，或人員使用 [網頁型 Outlook 中內建的報表](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)，您可以在 [ **使用者報送** ] 索引標籤上看到使用者的報告。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="1bcfc-209">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **提交**]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="1bcfc-210">選取 [ **使用者報送** ] 索引標籤，然後按一下 [ **新增提交**]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="1bcfc-211">您可以按一下頁面底部附近的 [ **欄選項** ] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="1bcfc-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="1bcfc-212">**提交于**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-212">**Submitted on**</span></span>
- <span data-ttu-id="1bcfc-213">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1bcfc-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="1bcfc-214">**主旨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1bcfc-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="1bcfc-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-215">**Sender**</span></span>
- <span data-ttu-id="1bcfc-216">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1bcfc-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="1bcfc-217">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-217">**Submission type**</span></span>

<span data-ttu-id="1bcfc-218"><sup>\*</sup> 如果您按一下此值，詳細資訊就會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="1bcfc-219">在頁面頂端附近，您可以輸入開始日期、結束日期和 (預設值) 您可以在 [收件者] 方塊中輸入值，然後按一下 [重新整理] 按鈕，以篩選收 **件** 者 ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="1bcfc-220">Update</span><span class="sxs-lookup"><span data-stu-id="1bcfc-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="1bcfc-221">若要變更篩選準則，請按一下 [ **寄件者** ] 按鈕，然後選擇下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="1bcfc-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="1bcfc-222">**寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-222">**Sender domain**</span></span>
- <span data-ttu-id="1bcfc-223">**主旨**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-223">**Subject**</span></span>
- <span data-ttu-id="1bcfc-224">**提交者**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-224">**Submitted by**</span></span>
- <span data-ttu-id="1bcfc-225">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-225">**Submission type**</span></span>
- <span data-ttu-id="1bcfc-226">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-226">**Sender IP**</span></span>

![使用者提交的篩選選項](../../media/user-submissions-filter-options.png)

<span data-ttu-id="1bcfc-228">若要匯出結果，請按一下頁面頂端附近的 [ **匯出** ]，然後選取 [ **圖表資料** 或 **表格**]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="1bcfc-229">在出現的對話方塊中，儲存 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="1bcfc-230">查看自訂信箱的使用者報送</span><span class="sxs-lookup"><span data-stu-id="1bcfc-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="1bcfc-231">**如果** 您已 [將自訂信箱設定](user-submission.md) 為接收使用者報告的郵件，您可以查看並提交傳遞到報表信箱的郵件。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-231">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="1bcfc-232">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **提交**]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="1bcfc-233">選取 [ **自訂信箱** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="1bcfc-234">您可以按一下頁面底部附近的 [ **欄選項** ] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="1bcfc-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="1bcfc-235">**提交于**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-235">**Submitted on**</span></span>
- <span data-ttu-id="1bcfc-236">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1bcfc-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="1bcfc-237">**主旨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1bcfc-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="1bcfc-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-238">**Sender**</span></span>
- <span data-ttu-id="1bcfc-239">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1bcfc-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="1bcfc-240">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-240">**Submission type**</span></span>

<span data-ttu-id="1bcfc-241">在頁面頂端附近，您可以輸入開始日期、結束日期，也可以透過在方塊中輸入值，然後按一下 [重新整理] 按鈕 **來篩選** ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="1bcfc-242">Update</span><span class="sxs-lookup"><span data-stu-id="1bcfc-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="1bcfc-243">若要匯出結果，請按一下頁面頂端附近的 [ **匯出** ]，然後選取 [ **圖表資料** 或 **表格**]。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="1bcfc-244">在出現的對話方塊中，儲存 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-244">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="1bcfc-245">撤銷使用者報送</span><span class="sxs-lookup"><span data-stu-id="1bcfc-245">Undo user submissions</span></span>

<span data-ttu-id="1bcfc-246">一旦使用者將可疑的電子郵件提交至自訂信箱，使用者和系統管理員就沒有任何可復原提交的選項。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-246">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="1bcfc-247">如果使用者想要復原電子郵件，將可在 [刪除的郵件] 或 [垃圾郵件] 資料夾中復原。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-247">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="1bcfc-248">從自訂信箱將郵件提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bcfc-248">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="1bcfc-249">如果您已將自訂信箱設定為在未傳送郵件給 Microsoft 的情況下截獲使用者報告的郵件，您可以尋找特定郵件並將其傳送給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-249">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="1bcfc-250">這會有效地將使用者提交權移至系統管理員提交。</span><span class="sxs-lookup"><span data-stu-id="1bcfc-250">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="1bcfc-251">在 [ **自訂信箱** ] 索引標籤上，選取清單中的訊息，按一下 [ **動作** ] 按鈕，然後進行下列其中一項選擇：</span><span class="sxs-lookup"><span data-stu-id="1bcfc-251">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="1bcfc-252">**報告清理**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-252">**Report clean**</span></span>
- <span data-ttu-id="1bcfc-253">**報告網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-253">**Report phishing**</span></span>
- <span data-ttu-id="1bcfc-254">**報告惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-254">**Report malware**</span></span>
- <span data-ttu-id="1bcfc-255">**報告垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="1bcfc-255">**Report spam**</span></span>

![動作按鈕上的選項](../../media/user-submission-custom-mailbox-action-button.png)
