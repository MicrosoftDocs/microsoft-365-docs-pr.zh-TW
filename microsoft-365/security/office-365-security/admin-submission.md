---
title: Office 365 的系統管理員提交
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何將可疑的電子郵件、可疑網路釣魚郵件、垃圾郵件和其他可能有害的郵件、URLs，以及您公司中的檔案提交至 Microsoft 進行掃描。
ms.openlocfilehash: 79f200963655e5fb07a04b686c1dd8cc3bbd0873
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034197"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="7c9de-103">使用系統管理提交，將可疑的垃圾郵件、網路釣魚詐騙、URL 和檔案提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="7c9de-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="7c9de-104">如果您是 Microsoft 365 組織中與 Exchange Online 中信箱的系統管理員，您可以使用安全性 & 合規性中心內的提交入口網站，將電子郵件訊息、URLs 和附件提交給 Microsoft 以進行掃描。</span><span class="sxs-lookup"><span data-stu-id="7c9de-104">If you're an admin in a Microsoft 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="7c9de-105">當您提交電子郵件時，您會收到任何可能允許內送電子郵件進入租使用者的原則，以及對郵件中的任何 URLs 和附件進行檢查的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7c9de-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="7c9de-106">可能允許郵件的原則包括個別使用者的安全寄件者清單，以及租使用者層級原則，例如 Exchange 郵件流程規則（也稱為傳輸規則）。</span><span class="sxs-lookup"><span data-stu-id="7c9de-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="7c9de-107">如需其他方式將電子郵件訊息、URLs 和附件提交給 Microsoft，請參閱[向 Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="7c9de-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7c9de-108">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="7c9de-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7c9de-109">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="7c9de-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7c9de-110">若要直接移至**提交**頁面，請<https://protection.office.com/reportsubmission>使用。</span><span class="sxs-lookup"><span data-stu-id="7c9de-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="7c9de-111">您必須已獲指派權限，才能執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="7c9de-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="7c9de-112">若要新增、修改和刪除反垃圾郵件原則，您必須是「**組織管理**」、「**安全性管理員**」或「**安全性讀者**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7c9de-112">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="7c9de-113">如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱[安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7c9de-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="7c9de-114">如需使用者如何提交郵件和檔案給 Microsoft 的詳細資訊，請參閱[向 Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="7c9de-114">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="7c9de-115">向 Microsoft 報告可疑內容</span><span class="sxs-lookup"><span data-stu-id="7c9de-115">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="7c9de-116">在 [安全性 & 規範中心] 中，移至 [**威脅管理** \> ] 以**查看** \>系統**管理員提交訊息**。</span><span class="sxs-lookup"><span data-stu-id="7c9de-116">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="7c9de-117">在出現的 [**提交**] 頁面上，按一下 [**新增提交**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7c9de-117">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="7c9de-118">使用看似送出的**新**送出控制項，如下列各節所述提交郵件、URL 或附件。</span><span class="sxs-lookup"><span data-stu-id="7c9de-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="7c9de-119">將可疑的電子郵件提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="7c9de-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="7c9de-120">在 [**物件類型**] 區段中，選取 [**電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="7c9de-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="7c9de-121">在 [**提交格式**] 區段中，使用下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="7c9de-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="7c9de-122">**網路消息識別碼**：這是在郵件中**X-MS-Exchange-Organization-網路 Message-Id**標頭中可用的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="7c9de-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="7c9de-123">**File**檔案：按一下 **[選擇**檔案]。</span><span class="sxs-lookup"><span data-stu-id="7c9de-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="7c9de-124">在開啟的對話方塊中，尋找並選取 .eml 或 .msg 檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7c9de-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="7c9de-125">**在 [收**件者] 區段中，指定您想要執行原則檢查的一或多個收件者。</span><span class="sxs-lookup"><span data-stu-id="7c9de-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="7c9de-126">原則檢查會決定是否因使用者或組織原則而略過掃描的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7c9de-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="7c9de-127">在 [**提交原因**] 區段中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="7c9de-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="7c9de-128">**不應該封鎖**</span><span class="sxs-lookup"><span data-stu-id="7c9de-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="7c9de-129">**應該已封鎖**：請選取 **[垃圾郵件**]、[**網路釣魚**] 或 [**惡意**代碼]。</span><span class="sxs-lookup"><span data-stu-id="7c9de-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="7c9de-130">如果您不確定，請使用您的最佳判斷。</span><span class="sxs-lookup"><span data-stu-id="7c9de-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="7c9de-131">如果篩選因提交原則而略過，您將會看到該原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7c9de-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="7c9de-132">如果篩選器因一或多個原則而略過，掃描將會在數分鐘內完成。</span><span class="sxs-lookup"><span data-stu-id="7c9de-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="7c9de-133">您可以按一下 [狀態] 連結，以查看有關提交的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="7c9de-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="7c9de-134">這包括原則檢查的結果和重新掃描判定。</span><span class="sxs-lookup"><span data-stu-id="7c9de-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="7c9de-135">請注意，這不會再透過 Office 365 ATP 完整篩選棧執行電子郵件，但會根據郵件、URL 或檔案的某些屬性執行部分重新掃描。</span><span class="sxs-lookup"><span data-stu-id="7c9de-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="7c9de-136">完成作業後，請按一下 [**提交**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7c9de-136">When you're finished, click the **Submit** button.</span></span>

![URL 提交範例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="7c9de-138">將可疑 URL 傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="7c9de-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="7c9de-139">在 [**物件類型**] 區段中，選取 [ **URL**]。</span><span class="sxs-lookup"><span data-stu-id="7c9de-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="7c9de-140">在出現的方塊中，輸入完整的 URL （例如<https://www.fabrikam.com/marketing.html>）。</span><span class="sxs-lookup"><span data-stu-id="7c9de-140">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="7c9de-141">在 [**提交原因**] 區段中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="7c9de-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="7c9de-142">**不應該封鎖**</span><span class="sxs-lookup"><span data-stu-id="7c9de-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="7c9de-143">**應該已封鎖**：請選取 [**網路釣魚**或**惡意**代碼]。</span><span class="sxs-lookup"><span data-stu-id="7c9de-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="7c9de-144">完成作業後，請按一下 [**提交**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7c9de-144">When you're finished, click the **Submit** button.</span></span>

![電子郵件提交範例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="7c9de-146">將可疑檔提交至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="7c9de-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="7c9de-147">在 [**物件類型**] 區段中，選取 [**附件**]。</span><span class="sxs-lookup"><span data-stu-id="7c9de-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="7c9de-148">按一下 **[選擇**檔案]。</span><span class="sxs-lookup"><span data-stu-id="7c9de-148">Click **Choose File**.</span></span> <span data-ttu-id="7c9de-149">在開啟的對話方塊中，尋找並選取檔，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7c9de-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="7c9de-150">在 [**提交原因**] 區段中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="7c9de-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="7c9de-151">**不應該封鎖**</span><span class="sxs-lookup"><span data-stu-id="7c9de-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="7c9de-152">**應該已封鎖**：**惡意**代碼是唯一的選擇，而且會自動加以選取。</span><span class="sxs-lookup"><span data-stu-id="7c9de-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="7c9de-153">完成作業後，請按一下 [**提交**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7c9de-153">When you're finished, click the **Submit** button.</span></span>

![附件提交範例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="7c9de-155">查看系統管理員報送</span><span class="sxs-lookup"><span data-stu-id="7c9de-155">View admin submissions</span></span>

1. <span data-ttu-id="7c9de-156">在 [安全性 & 規範中心] 中，移至 [**威脅管理** \> ] 以**查看** \>系統**管理員提交訊息**。</span><span class="sxs-lookup"><span data-stu-id="7c9de-156">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="7c9de-157">在出現的 [**提交**] 頁面上，確認已選取 [系統**管理提交**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="7c9de-157">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="7c9de-158">在頁面頂端附近，您可以輸入開始日期、結束日期及（預設值）您可以在此方塊中輸入值，然後按一下![[重新整理] 按鈕](../../media/scc-quarantine-refresh.png)，依**提交識別碼**篩選。</span><span class="sxs-lookup"><span data-stu-id="7c9de-158">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="7c9de-159">Update</span><span class="sxs-lookup"><span data-stu-id="7c9de-159">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="7c9de-160">若要變更篩選準則，請按一下 [**提交識別碼**] 按鈕，然後選擇下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="7c9de-160">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="7c9de-161">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7c9de-161">**Sender**</span></span>
- <span data-ttu-id="7c9de-162">**Subject/URL/檔案名**</span><span class="sxs-lookup"><span data-stu-id="7c9de-162">**Subject/URL/File name**</span></span>
- <span data-ttu-id="7c9de-163">**提交者**</span><span class="sxs-lookup"><span data-stu-id="7c9de-163">**Submitted by**</span></span>
- <span data-ttu-id="7c9de-164">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="7c9de-164">**Submission type**</span></span>
- <span data-ttu-id="7c9de-165">**狀態**</span><span class="sxs-lookup"><span data-stu-id="7c9de-165">**Status**</span></span>

![管理員報送的篩選選項](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="7c9de-167">若要匯出結果，請按一下頁面頂端附近的 [**匯出**]，然後選取 [**圖表資料**或**表格**]。</span><span class="sxs-lookup"><span data-stu-id="7c9de-167">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="7c9de-168">在出現的對話方塊中，儲存 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="7c9de-168">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="7c9de-169">在圖形下方有三個索引標籤：**電子郵件**（預設值）、 **URL**及**附件**。</span><span class="sxs-lookup"><span data-stu-id="7c9de-169">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="7c9de-170">查看系統管理電子郵件報送</span><span class="sxs-lookup"><span data-stu-id="7c9de-170">View admin email submissions</span></span>

<span data-ttu-id="7c9de-171">按一下 [**電子郵件**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="7c9de-171">Click the **Email** tab.</span></span>

<span data-ttu-id="7c9de-172">您可以按一下頁面底部附近的 [**欄選項**] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="7c9de-172">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7c9de-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="7c9de-173">**Date**</span></span>
- <span data-ttu-id="7c9de-174">**提交識別碼**</span><span class="sxs-lookup"><span data-stu-id="7c9de-174">**Submission ID**</span></span>
- <span data-ttu-id="7c9de-175">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c9de-175">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7c9de-176">**主旨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c9de-176">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="7c9de-177">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7c9de-177">**Sender**</span></span>
- <span data-ttu-id="7c9de-178">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c9de-178">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="7c9de-179">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="7c9de-179">**Submission type**</span></span>
- <span data-ttu-id="7c9de-180">**傳遞原因**</span><span class="sxs-lookup"><span data-stu-id="7c9de-180">**Delivery reason**</span></span>
- <span data-ttu-id="7c9de-181">**地位**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c9de-181">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="7c9de-182">**控制項類型**</span><span class="sxs-lookup"><span data-stu-id="7c9de-182">**Control type**</span></span>
- <span data-ttu-id="7c9de-183">**控制項來源**</span><span class="sxs-lookup"><span data-stu-id="7c9de-183">**Control source**</span></span>

  <span data-ttu-id="7c9de-184"><sup>\*</sup>如果您按一下此值，詳細資訊就會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="7c9de-184"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="7c9de-185">查看管理 URL 提交</span><span class="sxs-lookup"><span data-stu-id="7c9de-185">View admin URL submissions</span></span>

<span data-ttu-id="7c9de-186">按一下 [ **URL** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="7c9de-186">Click the **URL** tab.</span></span>

<span data-ttu-id="7c9de-187">您可以按一下頁面底部附近的 [**欄選項**] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="7c9de-187">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7c9de-188">**Date**</span><span class="sxs-lookup"><span data-stu-id="7c9de-188">**Date**</span></span>
- <span data-ttu-id="7c9de-189">**提交識別碼**</span><span class="sxs-lookup"><span data-stu-id="7c9de-189">**Submission ID**</span></span>
- <span data-ttu-id="7c9de-190">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c9de-190">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7c9de-191">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c9de-191">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="7c9de-192">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="7c9de-192">**Submission type**</span></span>
- <span data-ttu-id="7c9de-193">**地位**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c9de-193">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="7c9de-194"><sup>\*</sup>如果您按一下此值，詳細資訊就會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="7c9de-194"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="7c9de-195">View admin 附件提交</span><span class="sxs-lookup"><span data-stu-id="7c9de-195">View admin attachment submissions</span></span>

<span data-ttu-id="7c9de-196">按一下 [**附件**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="7c9de-196">Click the **Attachments** tab.</span></span>

<span data-ttu-id="7c9de-197">您可以按一下頁面底部附近的 [**欄選項**] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="7c9de-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7c9de-198">**Date**</span><span class="sxs-lookup"><span data-stu-id="7c9de-198">**Date**</span></span>
- <span data-ttu-id="7c9de-199">**提交識別碼**</span><span class="sxs-lookup"><span data-stu-id="7c9de-199">**Submission ID**</span></span>
- <span data-ttu-id="7c9de-200">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c9de-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7c9de-201">**檔案名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c9de-201">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="7c9de-202">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="7c9de-202">**Submission type**</span></span>
- <span data-ttu-id="7c9de-203">**地位**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c9de-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="7c9de-204"><sup>\*</sup>如果您按一下此值，詳細資訊就會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="7c9de-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="7c9de-205">查看 Microsoft 的使用者報送</span><span class="sxs-lookup"><span data-stu-id="7c9de-205">View user submissions to Microsoft</span></span>

<span data-ttu-id="7c9de-206">如果您已部署[報表訊息增益集](enable-the-report-message-add-in.md)，或人員使用[網頁型 Outlook 中內建的報表](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)，您可以在 [**使用者報送**] 索引標籤上看到使用者的報告。</span><span class="sxs-lookup"><span data-stu-id="7c9de-206">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="7c9de-207">在 [安全性 & 規範中心] 中，移至 [**威脅管理** \> ] 以**查看** \>系統**管理員提交訊息**。</span><span class="sxs-lookup"><span data-stu-id="7c9de-207">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="7c9de-208">在出現的 [**提交**] 頁面上，按一下 [**使用者報送**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="7c9de-208">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="7c9de-209">您可以按一下頁面底部附近的 [**欄選項**] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="7c9de-209">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7c9de-210">**提交于**</span><span class="sxs-lookup"><span data-stu-id="7c9de-210">**Submitted on**</span></span>
- <span data-ttu-id="7c9de-211">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c9de-211">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7c9de-212">**主旨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c9de-212">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="7c9de-213">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7c9de-213">**Sender**</span></span>
- <span data-ttu-id="7c9de-214">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c9de-214">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="7c9de-215">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="7c9de-215">**Submission type**</span></span>

<span data-ttu-id="7c9de-216"><sup>\*</sup>如果您按一下此值，詳細資訊就會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="7c9de-216"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="7c9de-217">在頁面頂端附近，您可以輸入開始日期、結束日期及（預設值）您可以在此方塊中輸入值，然後按一下![[重新整理] 按鈕](../../media/scc-quarantine-refresh.png)，以篩選**寄件者**。</span><span class="sxs-lookup"><span data-stu-id="7c9de-217">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="7c9de-218">Update</span><span class="sxs-lookup"><span data-stu-id="7c9de-218">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="7c9de-219">若要變更篩選準則，請按一下 [**寄件者**] 按鈕，然後選擇下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="7c9de-219">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="7c9de-220">**寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="7c9de-220">**Sender domain**</span></span>
- <span data-ttu-id="7c9de-221">**主旨**</span><span class="sxs-lookup"><span data-stu-id="7c9de-221">**Subject**</span></span>
- <span data-ttu-id="7c9de-222">**提交者**</span><span class="sxs-lookup"><span data-stu-id="7c9de-222">**Submitted by**</span></span>
- <span data-ttu-id="7c9de-223">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="7c9de-223">**Submission type**</span></span>
- <span data-ttu-id="7c9de-224">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="7c9de-224">**Sender IP**</span></span>

![使用者提交的篩選選項](../../media/user-submissions-filter-options.png)

<span data-ttu-id="7c9de-226">若要匯出結果，請按一下頁面頂端附近的 [**匯出**]，然後選取 [**圖表資料**或**表格**]。</span><span class="sxs-lookup"><span data-stu-id="7c9de-226">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="7c9de-227">在出現的對話方塊中，儲存 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="7c9de-227">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="7c9de-228">查看自訂信箱的使用者報送</span><span class="sxs-lookup"><span data-stu-id="7c9de-228">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="7c9de-229">如果您已[將自訂信箱設定](user-submission.md)為接收使用者報告的郵件，您可以查看並提交傳遞到報表信箱的郵件。</span><span class="sxs-lookup"><span data-stu-id="7c9de-229">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="7c9de-230">在 [安全性 & 規範中心] 中，移至 [**威脅管理** \> ] 以**查看** \>系統**管理員提交訊息**。</span><span class="sxs-lookup"><span data-stu-id="7c9de-230">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="7c9de-231">在出現的 [**提交**] 頁面上，按一下 [**自訂信箱**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="7c9de-231">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="7c9de-232">您可以按一下頁面底部附近的 [**欄選項**] 按鈕，從該視圖新增或移除欄：</span><span class="sxs-lookup"><span data-stu-id="7c9de-232">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7c9de-233">**提交于**</span><span class="sxs-lookup"><span data-stu-id="7c9de-233">**Submitted on**</span></span>
- <span data-ttu-id="7c9de-234">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c9de-234">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7c9de-235">**主旨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c9de-235">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="7c9de-236">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7c9de-236">**Sender**</span></span>
- <span data-ttu-id="7c9de-237">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c9de-237">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="7c9de-238">**提交類型**</span><span class="sxs-lookup"><span data-stu-id="7c9de-238">**Submission type**</span></span>

<span data-ttu-id="7c9de-239">在頁面頂端附近，您可以輸入開始日期、結束日期，也可以透過在方塊中輸入值，然後按一下![[重新整理]](../../media/scc-quarantine-refresh.png)**按鈕來篩選**。</span><span class="sxs-lookup"><span data-stu-id="7c9de-239">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="7c9de-240">Update</span><span class="sxs-lookup"><span data-stu-id="7c9de-240">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="7c9de-241">若要匯出結果，請按一下頁面頂端附近的 [**匯出**]，然後選取 [**圖表資料**或**表格**]。</span><span class="sxs-lookup"><span data-stu-id="7c9de-241">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="7c9de-242">在出現的對話方塊中，儲存 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="7c9de-242">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="7c9de-243">從自訂信箱將郵件提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="7c9de-243">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="7c9de-244">如果您已將自訂信箱設定為在未傳送郵件給 Microsoft 的情況下截獲使用者報告的郵件，您可以尋找特定郵件並將其傳送給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="7c9de-244">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="7c9de-245">這會有效地將使用者提交權移至系統管理員提交。</span><span class="sxs-lookup"><span data-stu-id="7c9de-245">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="7c9de-246">在 [**自訂信箱**] 索引標籤上，選取清單中的訊息，按一下 [**動作**] 按鈕，然後進行下列其中一項選擇：</span><span class="sxs-lookup"><span data-stu-id="7c9de-246">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="7c9de-247">**報告清理**</span><span class="sxs-lookup"><span data-stu-id="7c9de-247">**Report clean**</span></span>
- <span data-ttu-id="7c9de-248">**報告網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="7c9de-248">**Report phishing**</span></span>
- <span data-ttu-id="7c9de-249">**報告惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="7c9de-249">**Report malware**</span></span>
- <span data-ttu-id="7c9de-250">**報告垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="7c9de-250">**Report spam**</span></span>

![動作按鈕上的選項](../../media/user-submission-custom-mailbox-action-button.png)
