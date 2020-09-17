---
title: 系統管理報送
f1.keywords:
- NOCSH
ms.author: chrisda
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
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用安全性 & 合規性中心內的提交入口網站，將可疑的電子郵件、可疑網路釣魚郵件、垃圾郵件和其他可能有害的郵件、URLs 和檔案提交至 Microsoft 進行掃描。
ms.openlocfilehash: ef401f34bb0bc7a9a9718443101924ad09bca8a0
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47947969"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="c7e29-103">使用系統管理提交，將可疑的垃圾郵件、網路釣魚詐騙、URL 和檔案提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="c7e29-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="c7e29-104">在使用 Exchange Online 信箱的 Microsoft 365 組織中，系統管理員可以使用安全性 & 合規性中心內的提交入口網站，將電子郵件訊息、URLs 和附件提交給 Microsoft 以供掃描。</span><span class="sxs-lookup"><span data-stu-id="c7e29-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="c7e29-105">當您提交電子郵件時，您會收到任何可能允許內送電子郵件進入租使用者的原則，以及對郵件中的任何 URLs 和附件進行檢查的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c7e29-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="c7e29-106">可能允許郵件的原則包括個別使用者的安全寄件者清單，以及租使用者層級原則，例如 Exchange 郵件流程規則 (也稱為 transport rules) 。</span><span class="sxs-lookup"><span data-stu-id="c7e29-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="c7e29-107">如需其他方式將電子郵件訊息、URLs 和附件提交給 Microsoft，請參閱 [向 Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="c7e29-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c7e29-108">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="c7e29-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c7e29-109">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="c7e29-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c7e29-110">若要直接移至 **提交** 頁面，請使用 <https://protection.office.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="c7e29-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="c7e29-111">若要將郵件和檔案提交給 Microsoft，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="c7e29-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="c7e29-112">**組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員**。 </span><span class="sxs-lookup"><span data-stu-id="c7e29-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="c7e29-113">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的**組織管理**。</span><span class="sxs-lookup"><span data-stu-id="c7e29-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="c7e29-114">請注意，此角色群組的成員資格是 [查看使用者送至自訂信箱的使用者](#view-user-submissions-to-the-custom-mailbox) ，如本主題稍後所述。</span><span class="sxs-lookup"><span data-stu-id="c7e29-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="c7e29-115">如需使用者如何提交郵件和檔案給 Microsoft 的詳細資訊，請參閱 [向 Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="c7e29-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="c7e29-116">向 Microsoft 報告可疑內容</span><span class="sxs-lookup"><span data-stu-id="c7e29-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="c7e29-117">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **提交**]，確認您在 [系統 **管理提交** ] 索引標籤上，然後按一下 [ **新增提交**]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="c7e29-118">使用看似送出的 **新** 送出控制項，如下列各節所述提交郵件、URL 或附件。</span><span class="sxs-lookup"><span data-stu-id="c7e29-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="c7e29-119">將可疑的電子郵件提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="c7e29-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="c7e29-120">在 [ **物件類型** ] 區段中，選取 [ **電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="c7e29-121">在 [ **提交格式** ] 區段中，使用下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="c7e29-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="c7e29-122">**網路消息識別碼**：這是在郵件中 **X-MS-Exchange-Organization-網路 Message-Id** 標頭中可用的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="c7e29-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="c7e29-123">**File**檔案：按一下 **[選擇**檔案]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="c7e29-124">在開啟的對話方塊中，尋找並選取 .eml 或 .msg 檔案，然後按一下 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="c7e29-125">**在 [收**件者] 區段中，指定您想要執行原則檢查的一或多個收件者。</span><span class="sxs-lookup"><span data-stu-id="c7e29-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="c7e29-126">原則檢查會決定是否因使用者或組織原則而略過掃描的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c7e29-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="c7e29-127">在 [ **提交原因** ] 區段中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="c7e29-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="c7e29-128">**不應該封鎖**</span><span class="sxs-lookup"><span data-stu-id="c7e29-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="c7e29-129">**應該已封鎖**：請選取 **[垃圾郵件**]、[ **網路釣魚**] 或 [ **惡意**代碼]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="c7e29-130">如果您不確定，請使用您的最佳判斷。</span><span class="sxs-lookup"><span data-stu-id="c7e29-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="c7e29-131">如果篩選因提交原則而略過，您將會看到該原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c7e29-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="c7e29-132">如果篩選器因一或多個原則而略過，掃描將會在數分鐘內完成。</span><span class="sxs-lookup"><span data-stu-id="c7e29-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="c7e29-133">您可以按一下 [狀態] 連結，以查看有關提交的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="c7e29-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="c7e29-134">這包括原則檢查的結果和重新掃描判定。</span><span class="sxs-lookup"><span data-stu-id="c7e29-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="c7e29-135">請注意，這不會再透過 Office 365 ATP 完整篩選棧執行電子郵件，但會根據郵件、URL 或檔案的某些屬性執行部分重新掃描。</span><span class="sxs-lookup"><span data-stu-id="c7e29-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="c7e29-136">完成作業後，請按一下 [ **提交** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c7e29-136">When you're finished, click the **Submit** button.</span></span>

![URL 提交範例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="c7e29-138">將可疑 URL 傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="c7e29-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="c7e29-139">在 [ **物件類型** ] 區段中，選取 [ **URL**]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="c7e29-140">在出現的方塊中，輸入完整的 URL (例如， `https://www.fabrikam.com/marketing.html`) 。</span><span class="sxs-lookup"><span data-stu-id="c7e29-140">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="c7e29-141">在 [ **提交原因** ] 區段中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="c7e29-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="c7e29-142">**不應該封鎖**</span><span class="sxs-lookup"><span data-stu-id="c7e29-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="c7e29-143">**應該已封鎖**：請選取 [ **網路釣魚** 或 **惡意**代碼]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="c7e29-144">完成作業後，請按一下 [ **提交** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c7e29-144">When you're finished, click the **Submit** button.</span></span>

![電子郵件提交範例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="c7e29-146">將可疑檔提交至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="c7e29-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="c7e29-147">在 [ **物件類型** ] 區段中，選取 [ **附件**]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="c7e29-148">按一下 **[選擇**檔案]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-148">Click **Choose File**.</span></span> <span data-ttu-id="c7e29-149">在開啟的對話方塊中，尋找並選取檔，然後按一下 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="c7e29-150">在 [ **提交原因** ] 區段中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="c7e29-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="c7e29-151">**不應該封鎖**</span><span class="sxs-lookup"><span data-stu-id="c7e29-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="c7e29-152">**應該已封鎖**： **惡意** 代碼是唯一的選擇，而且會自動加以選取。</span><span class="sxs-lookup"><span data-stu-id="c7e29-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="c7e29-153">完成作業後，請按一下 [ **提交** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c7e29-153">When you're finished, click the **Submit** button.</span></span>

![附件提交範例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="c7e29-155">查看系統管理員報送</span><span class="sxs-lookup"><span data-stu-id="c7e29-155">View admin submissions</span></span>

<span data-ttu-id="c7e29-156">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **提交**]，確認您在 [系統 **管理提交** ] 索引標籤上，然後按一下 [ **新增提交**]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-156">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="c7e29-157">在頁面頂端附近，您可以輸入開始日期、結束日期和 (預設值) 您可以依 **提交識別碼** (指派給每個提交) 的 GUID 值進行篩選，方法是在方塊中輸入值，然後按一下 [重新整理] ![ 按鈕 ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="c7e29-157">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="c7e29-158">Update</span><span class="sxs-lookup"><span data-stu-id="c7e29-158">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="c7e29-159">若要變更篩選準則，請按一下 [ **提交識別碼** ] 按鈕，然後選擇下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="c7e29-159">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="c7e29-160">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c7e29-160">**Sender**</span></span>
- <span data-ttu-id="c7e29-161">**Subject/URL/檔案名**</span><span class="sxs-lookup"><span data-stu-id="c7e29-161">**Subject/URL/File name**</span></span>
- <span data-ttu-id="c7e29-162">**提交者**</span><span class="sxs-lookup"><span data-stu-id="c7e29-162">**Submitted by**</span></span>
- <span data-ttu-id="c7e29-163">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="c7e29-163">**Submission type**</span></span>
- <span data-ttu-id="c7e29-164">**狀態**</span><span class="sxs-lookup"><span data-stu-id="c7e29-164">**Status**</span></span>

![管理員報送的篩選選項](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="c7e29-166">若要匯出結果，請按一下頁面頂端附近的 [ **匯出** ]，然後選取 [ **圖表資料** 或 **表格**]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-166">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="c7e29-167">在出現的對話方塊中，儲存 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="c7e29-167">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="c7e29-168">在圖形下方有三個索引標籤： **電子郵件** (預設) 、 **URL**及 **附件**。</span><span class="sxs-lookup"><span data-stu-id="c7e29-168">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="c7e29-169">查看系統管理電子郵件報送</span><span class="sxs-lookup"><span data-stu-id="c7e29-169">View admin email submissions</span></span>

<span data-ttu-id="c7e29-170">按一下 [ **電子郵件** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c7e29-170">Click the **Email** tab.</span></span>

<span data-ttu-id="c7e29-171">您可以按一下頁面底部附近的 [ **欄選項** ] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="c7e29-171">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c7e29-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="c7e29-172">**Date**</span></span>
- <span data-ttu-id="c7e29-173">**提交識別碼**：指派給每個提交的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="c7e29-173">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="c7e29-174">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7e29-174">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c7e29-175">**主旨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7e29-175">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="c7e29-176">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c7e29-176">**Sender**</span></span>
- <span data-ttu-id="c7e29-177">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7e29-177">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="c7e29-178">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="c7e29-178">**Submission type**</span></span>
- <span data-ttu-id="c7e29-179">**傳遞原因**</span><span class="sxs-lookup"><span data-stu-id="c7e29-179">**Delivery reason**</span></span>
- <span data-ttu-id="c7e29-180">**地位**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7e29-180">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="c7e29-181">**控制項類型**</span><span class="sxs-lookup"><span data-stu-id="c7e29-181">**Control type**</span></span>
- <span data-ttu-id="c7e29-182">**控制項來源**</span><span class="sxs-lookup"><span data-stu-id="c7e29-182">**Control source**</span></span>

  <span data-ttu-id="c7e29-183"><sup>\*</sup> 如果您按一下此值，詳細資訊就會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="c7e29-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="c7e29-184">查看管理 URL 提交</span><span class="sxs-lookup"><span data-stu-id="c7e29-184">View admin URL submissions</span></span>

<span data-ttu-id="c7e29-185">按一下 [ **URL** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c7e29-185">Click the **URL** tab.</span></span>

<span data-ttu-id="c7e29-186">您可以按一下頁面底部附近的 [ **欄選項** ] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="c7e29-186">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c7e29-187">**Date**</span><span class="sxs-lookup"><span data-stu-id="c7e29-187">**Date**</span></span>
- <span data-ttu-id="c7e29-188">**提交識別碼**</span><span class="sxs-lookup"><span data-stu-id="c7e29-188">**Submission ID**</span></span>
- <span data-ttu-id="c7e29-189">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7e29-189">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c7e29-190">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7e29-190">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="c7e29-191">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="c7e29-191">**Submission type**</span></span>
- <span data-ttu-id="c7e29-192">**地位**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7e29-192">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="c7e29-193"><sup>\*</sup> 如果您按一下此值，詳細資訊就會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="c7e29-193"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="c7e29-194">View admin 附件提交</span><span class="sxs-lookup"><span data-stu-id="c7e29-194">View admin attachment submissions</span></span>

<span data-ttu-id="c7e29-195">按一下 [ **附件** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c7e29-195">Click the **Attachments** tab.</span></span>

<span data-ttu-id="c7e29-196">您可以按一下頁面底部附近的 [ **欄選項** ] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="c7e29-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c7e29-197">**Date**</span><span class="sxs-lookup"><span data-stu-id="c7e29-197">**Date**</span></span>
- <span data-ttu-id="c7e29-198">**提交識別碼**</span><span class="sxs-lookup"><span data-stu-id="c7e29-198">**Submission ID**</span></span>
- <span data-ttu-id="c7e29-199">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7e29-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c7e29-200">**檔案名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7e29-200">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="c7e29-201">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="c7e29-201">**Submission type**</span></span>
- <span data-ttu-id="c7e29-202">**地位**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7e29-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="c7e29-203"><sup>\*</sup> 如果您按一下此值，詳細資訊就會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="c7e29-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="c7e29-204">查看 Microsoft 的使用者報送</span><span class="sxs-lookup"><span data-stu-id="c7e29-204">View user submissions to Microsoft</span></span>

<span data-ttu-id="c7e29-205">如果您已部署 [報表訊息增益集](enable-the-report-message-add-in.md)，或人員使用 [網頁型 Outlook 中內建的報表](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)，您可以在 [ **使用者報送** ] 索引標籤上看到使用者的報告。</span><span class="sxs-lookup"><span data-stu-id="c7e29-205">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="c7e29-206">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **提交**]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-206">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="c7e29-207">選取 [ **使用者報送** ] 索引標籤，然後按一下 [ **新增提交**]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-207">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="c7e29-208">您可以按一下頁面底部附近的 [ **欄選項** ] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="c7e29-208">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c7e29-209">**提交于**</span><span class="sxs-lookup"><span data-stu-id="c7e29-209">**Submitted on**</span></span>
- <span data-ttu-id="c7e29-210">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7e29-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c7e29-211">**主旨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7e29-211">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="c7e29-212">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c7e29-212">**Sender**</span></span>
- <span data-ttu-id="c7e29-213">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7e29-213">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="c7e29-214">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="c7e29-214">**Submission type**</span></span>

<span data-ttu-id="c7e29-215"><sup>\*</sup> 如果您按一下此值，詳細資訊就會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="c7e29-215"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="c7e29-216">在頁面頂端附近，您可以輸入開始日期、結束日期和 (預設值) 您可以在 [收件者] 方塊中輸入值，然後按一下 [重新整理] 按鈕，以篩選收 **件** 者 ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="c7e29-216">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="c7e29-217">Update</span><span class="sxs-lookup"><span data-stu-id="c7e29-217">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="c7e29-218">若要變更篩選準則，請按一下 [ **寄件者** ] 按鈕，然後選擇下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="c7e29-218">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="c7e29-219">**寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="c7e29-219">**Sender domain**</span></span>
- <span data-ttu-id="c7e29-220">**主旨**</span><span class="sxs-lookup"><span data-stu-id="c7e29-220">**Subject**</span></span>
- <span data-ttu-id="c7e29-221">**提交者**</span><span class="sxs-lookup"><span data-stu-id="c7e29-221">**Submitted by**</span></span>
- <span data-ttu-id="c7e29-222">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="c7e29-222">**Submission type**</span></span>
- <span data-ttu-id="c7e29-223">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="c7e29-223">**Sender IP**</span></span>

![使用者提交的篩選選項](../../media/user-submissions-filter-options.png)

<span data-ttu-id="c7e29-225">若要匯出結果，請按一下頁面頂端附近的 [ **匯出** ]，然後選取 [ **圖表資料** 或 **表格**]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-225">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="c7e29-226">在出現的對話方塊中，儲存 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="c7e29-226">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="c7e29-227">查看自訂信箱的使用者報送</span><span class="sxs-lookup"><span data-stu-id="c7e29-227">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="c7e29-228">**如果** 您已 [將自訂信箱設定](user-submission.md) 為接收使用者報告的郵件，您可以查看並提交傳遞到報表信箱的郵件。</span><span class="sxs-lookup"><span data-stu-id="c7e29-228">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="c7e29-229">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **提交**]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-229">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="c7e29-230">選取 [ **自訂信箱** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c7e29-230">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="c7e29-231">您可以按一下頁面底部附近的 [ **欄選項** ] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="c7e29-231">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c7e29-232">**提交于**</span><span class="sxs-lookup"><span data-stu-id="c7e29-232">**Submitted on**</span></span>
- <span data-ttu-id="c7e29-233">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7e29-233">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c7e29-234">**主旨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7e29-234">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="c7e29-235">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c7e29-235">**Sender**</span></span>
- <span data-ttu-id="c7e29-236">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7e29-236">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="c7e29-237">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="c7e29-237">**Submission type**</span></span>

<span data-ttu-id="c7e29-238">在頁面頂端附近，您可以輸入開始日期、結束日期，也可以透過在方塊中輸入值，然後按一下 [重新整理] 按鈕 **來篩選** ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="c7e29-238">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="c7e29-239">Update</span><span class="sxs-lookup"><span data-stu-id="c7e29-239">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="c7e29-240">若要匯出結果，請按一下頁面頂端附近的 [ **匯出** ]，然後選取 [ **圖表資料** 或 **表格**]。</span><span class="sxs-lookup"><span data-stu-id="c7e29-240">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="c7e29-241">在出現的對話方塊中，儲存 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="c7e29-241">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="c7e29-242">從自訂信箱將郵件提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="c7e29-242">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="c7e29-243">如果您已將自訂信箱設定為在未傳送郵件給 Microsoft 的情況下截獲使用者報告的郵件，您可以尋找特定郵件並將其傳送給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="c7e29-243">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="c7e29-244">這會有效地將使用者提交權移至系統管理員提交。</span><span class="sxs-lookup"><span data-stu-id="c7e29-244">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="c7e29-245">在 [ **自訂信箱** ] 索引標籤上，選取清單中的訊息，按一下 [ **動作** ] 按鈕，然後進行下列其中一項選擇：</span><span class="sxs-lookup"><span data-stu-id="c7e29-245">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="c7e29-246">**報告清理**</span><span class="sxs-lookup"><span data-stu-id="c7e29-246">**Report clean**</span></span>
- <span data-ttu-id="c7e29-247">**報告網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="c7e29-247">**Report phishing**</span></span>
- <span data-ttu-id="c7e29-248">**報告惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="c7e29-248">**Report malware**</span></span>
- <span data-ttu-id="c7e29-249">**報告垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="c7e29-249">**Report spam**</span></span>

![動作按鈕上的選項](../../media/user-submission-custom-mailbox-action-button.png)
