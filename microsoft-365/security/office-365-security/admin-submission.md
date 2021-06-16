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
description: 系統管理員可以瞭解如何使用 Microsoft 365 Defender 入口網站中的提交入口網站，將可疑的電子郵件、可疑網路釣魚郵件、垃圾郵件和其他可能有害的郵件、URLs 和電子郵件附件傳送給 Microsoft 以重新掃描。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b671ce5a44c7be61331a121b49e96658cf14bab1
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964798"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="5be0c-103">使用系統管理提交，將可疑的垃圾郵件、網路釣魚詐騙、URL 和檔案提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="5be0c-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5be0c-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="5be0c-104">**Applies to**</span></span>
- [<span data-ttu-id="5be0c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5be0c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5be0c-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="5be0c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="5be0c-107">在 Microsoft 365 具有 Exchange Online 信箱的組織中，系統管理員可以使用 Microsoft 365 Defender 入口網站中的提交入口網站，將電子郵件訊息、URLs 及附件提交給 Microsoft 以進行掃描。</span><span class="sxs-lookup"><span data-stu-id="5be0c-107">In Microsoft 365 organizations with Exchange Online mailboxes, admins can use the Submissions portal in the Microsoft 365 Defender portal to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="5be0c-108">當您提交電子郵件訊息時，您會收到：</span><span class="sxs-lookup"><span data-stu-id="5be0c-108">When you submit an email message, you will get:</span></span>

- <span data-ttu-id="5be0c-109">**電子郵件驗證檢查**：傳送電子郵件時的驗證是否已通過或失敗的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5be0c-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
- <span data-ttu-id="5be0c-110">**原則點擊**：有關任何可能允許或封鎖內送電子郵件進入您租使用者之原則的資訊，請覆寫我們的服務篩選 verdicts。</span><span class="sxs-lookup"><span data-stu-id="5be0c-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
- <span data-ttu-id="5be0c-111">「**負載信譽/引爆**：檢查郵件中的任何 URLs 和附件。</span><span class="sxs-lookup"><span data-stu-id="5be0c-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
- <span data-ttu-id="5be0c-112">**評分分析**：檢查是否有惡意的「人工 graders 完成」。</span><span class="sxs-lookup"><span data-stu-id="5be0c-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5be0c-113">在所有承租人中都不會進行負載信譽/引爆和評分分析。</span><span class="sxs-lookup"><span data-stu-id="5be0c-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="5be0c-114">當資料不應該保留租使用者界限以符合合規性目的時，就會封鎖資訊，避免進入組織外部。</span><span class="sxs-lookup"><span data-stu-id="5be0c-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="5be0c-115">如需其他方式將電子郵件訊息、URLs 和附件提交給 Microsoft，請參閱 [向 Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="5be0c-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5be0c-116">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="5be0c-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5be0c-117">您於 <https://security.microsoft.com/> 開啟 Microsoft 365 Defender 入口網站。</span><span class="sxs-lookup"><span data-stu-id="5be0c-117">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="5be0c-118">若要直接移至 [ **提交** ] 頁面，請使用 <https://security.microsoft.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="5be0c-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="5be0c-119">若要將郵件和檔案提交給 Microsoft，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="5be0c-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="5be0c-120">[Microsoft 365 Defender 入口網站](permissions-microsoft-365-security-center.md)中的 **組織管理** 或 **安全性讀者**。</span><span class="sxs-lookup"><span data-stu-id="5be0c-120">**Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="5be0c-121">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)中的 **組織管理**。</span><span class="sxs-lookup"><span data-stu-id="5be0c-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="5be0c-122">請注意，此角色群組的成員資格是 [查看使用者送至自訂信箱的使用者](#view-user-submissions-to-microsoft) ，如本文稍後所述。</span><span class="sxs-lookup"><span data-stu-id="5be0c-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-microsoft) as described later in this article.</span></span>

- <span data-ttu-id="5be0c-123">如需使用者如何提交郵件和檔案給 Microsoft 的詳細資訊，請參閱 [向 Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="5be0c-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="5be0c-124">向 Microsoft 報告可疑內容</span><span class="sxs-lookup"><span data-stu-id="5be0c-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="5be0c-125">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **提交**]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-125">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="5be0c-126">在 [ **提交** ] 頁面上，確認已選取 [已 **提交的分析** ] 索引標籤，然後按一下 [ ![ Ad 圖示 ](../../media/m365-cc-sc-create-icon.png) **提交至 Microsoft 進行分析**]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-126">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected, and then click ![Ad icon](../../media/m365-cc-sc-create-icon.png) **Submit to Microsoft for analysis**.</span></span>

3. <span data-ttu-id="5be0c-127">使用送出 **至 Microsoft 來審閱** 浮出的浮出的浮出方式，如下列各節所述提交郵件、URL 或電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="5be0c-127">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="5be0c-128">將可疑的電子郵件提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="5be0c-128">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="5be0c-129">在 [ **選取提交類型** ] 方塊中，確認下拉式清單中已選取 [ **電子郵件** ]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-129">In the **Select the submission type** box, verify that **Email** is selected in the drop down list.</span></span>

2. <span data-ttu-id="5be0c-130">在 [ **新增網路消息識別碼] 或 [上傳電子郵件** 檔案] 區段中，使用下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="5be0c-130">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>
   - <span data-ttu-id="5be0c-131">**新增電子郵件網路郵件識別碼**：此為 GUID 值，可在郵件中的 **X-MS-Exchange-Organization-網路 Message-Id** 標頭中，或在 Office365 中的 **X-** ----------------------------</span><span class="sxs-lookup"><span data-stu-id="5be0c-131">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>
   - <span data-ttu-id="5be0c-132">**Upload 電子郵件檔 ( .msg 或 .eml)**：按一下 **[流覽檔案]**。</span><span class="sxs-lookup"><span data-stu-id="5be0c-132">**Upload the email file (.msg or .eml)**: Click **Browse files**.</span></span> <span data-ttu-id="5be0c-133">在開啟的對話方塊中，尋找並選取 .eml 或 .msg 檔案，然後按一下 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-133">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5be0c-134">將郵件送出多久30天，已暫時為 Office 365 客戶的 Defender 停用。</span><span class="sxs-lookup"><span data-stu-id="5be0c-134">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="5be0c-135">系統管理員只可以回復7天。</span><span class="sxs-lookup"><span data-stu-id="5be0c-135">Admins will only be able to go back 7 days.</span></span>

3. <span data-ttu-id="5be0c-136">在 [ **選擇有問題的收件者** ] 方塊中，指定您想要執行原則檢查的收件者。</span><span class="sxs-lookup"><span data-stu-id="5be0c-136">In the **Choose a recipient who had an issue** box, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="5be0c-137">原則檢查會決定是否因使用者或組織原則而略過掃描的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="5be0c-137">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

4. <span data-ttu-id="5be0c-138">在 [ **選取要提交給 Microsoft 的原因** ] 區段中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="5be0c-138">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="5be0c-139">**不應該封鎖 (誤報)**</span><span class="sxs-lookup"><span data-stu-id="5be0c-139">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="5be0c-140">**應該已封鎖**：在 [ **電子郵件應該已分類成** ] 區段中，選取下列其中一個值 (如果您不確定，請使用您的最佳 judgement) ：</span><span class="sxs-lookup"><span data-stu-id="5be0c-140">**Should have been blocked**: In the **The email should have been categorized as** section that appears, select one of the following values (if you're not sure, use your best judgement):</span></span>
     - <span data-ttu-id="5be0c-141">**網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="5be0c-141">**Phish**</span></span>
     - <span data-ttu-id="5be0c-142">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="5be0c-142">**Spam**</span></span>
     - <span data-ttu-id="5be0c-143">**惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="5be0c-143">**Malware**</span></span>

5. <span data-ttu-id="5be0c-144">完成作業後，請按一下 [ **提交** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5be0c-144">When you're finished, click the **Submit** button.</span></span>

   ![新的 URL 提交範例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="5be0c-146">將可疑 URL 傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="5be0c-146">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="5be0c-147">在 [ **選取提交類型** ] 方塊中，從下拉式清單中選取 [ **URL** ]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-147">In the **Select the submission type** box, select **URL** from the drop down list.</span></span>

2. <span data-ttu-id="5be0c-148">在出現的 [ **url** ] 方塊中，輸入完整的 URL (例如， `https://www.fabrikam.com/marketing.html`) 。</span><span class="sxs-lookup"><span data-stu-id="5be0c-148">In the **URL** box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

3. <span data-ttu-id="5be0c-149">在 [ **選取要提交給 Microsoft 的原因** ] 區段中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="5be0c-149">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="5be0c-150">**不應該封鎖 (誤報)**</span><span class="sxs-lookup"><span data-stu-id="5be0c-150">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="5be0c-151">**應該已封鎖**：在 **此 URL 中，應該已分類為** 所出現的區段，請選取 [ **網路釣魚** 或 **惡意** 代碼]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-151">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, select **Phish** or **Malware**.</span></span>

4. <span data-ttu-id="5be0c-152">完成作業後，請按一下 [ **提交** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5be0c-152">When you're finished, click the **Submit** button.</span></span>

   ![新的電子郵件提交範例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="5be0c-154">將可疑的電子郵件附件提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="5be0c-154">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="5be0c-155">在 [ **選取提交類型** ] 方塊中， **從下拉式清單中選取** [檔案]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-155">In the **Select the submission type** box, select **File** from the drop down list.</span></span>

2. <span data-ttu-id="5be0c-156">在出現的 [ **檔** ] 區段中，按一下 **[流覽檔案]**。</span><span class="sxs-lookup"><span data-stu-id="5be0c-156">In the **File** section that appears, click **Browse files**.</span></span> <span data-ttu-id="5be0c-157">在開啟的對話方塊中，尋找並選取檔，然後按一下 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-157">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="5be0c-158">在 [ **選取要提交給 Microsoft 的原因** ] 區段中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="5be0c-158">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="5be0c-159">**不應該封鎖 (誤報)**</span><span class="sxs-lookup"><span data-stu-id="5be0c-159">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="5be0c-160">**應該已封鎖**：在 **此 URL 中，應該已分類為** 所出現的區段， **惡意** 代碼是唯一的選擇，而且會自動加以選取。</span><span class="sxs-lookup"><span data-stu-id="5be0c-160">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="5be0c-161">完成作業後，請按一下 [ **提交** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5be0c-161">When you're finished, click the **Submit** button.</span></span>

   ![新附件提交範例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions-to-microsoft"></a><span data-ttu-id="5be0c-163">查看對 Microsoft 的系統管理員報送</span><span class="sxs-lookup"><span data-stu-id="5be0c-163">View admin submissions to Microsoft</span></span>

1. <span data-ttu-id="5be0c-164">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **提交**]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-164">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="5be0c-165">在 [ **提交** ] 頁面上，確認已選取 [已 **提交進行分析** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5be0c-165">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected.</span></span>

   - <span data-ttu-id="5be0c-166">您可以按一下可用的欄標題，排序專案。</span><span class="sxs-lookup"><span data-stu-id="5be0c-166">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="5be0c-167">按一下 [ **自訂欄** ] 以顯示最多7欄。</span><span class="sxs-lookup"><span data-stu-id="5be0c-167">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="5be0c-168">預設值會標上星號 (<sup>\*</sup>)：</span><span class="sxs-lookup"><span data-stu-id="5be0c-168">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>
     - <span data-ttu-id="5be0c-169">**提交名稱**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5be0c-169">**Submission name**<sup>\*</sup></span></span>
     - <span data-ttu-id="5be0c-170">**寄件者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5be0c-170">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="5be0c-171">**提交日期**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5be0c-171">**Date submitted**<sup>\*</sup></span></span>
     - <span data-ttu-id="5be0c-172">**提交類型**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5be0c-172">**Submission type**<sup>\*</sup></span></span>
     - <span data-ttu-id="5be0c-173">**提交原因**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5be0c-173">**Reason for submitting**<sup>\*</sup></span></span>
     - <span data-ttu-id="5be0c-174">**重新掃描狀態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5be0c-174">**Rescan status**<sup>\*</sup></span></span>
     - <span data-ttu-id="5be0c-175">**重新掃描結果**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5be0c-175">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="5be0c-176">**篩選判定**</span><span class="sxs-lookup"><span data-stu-id="5be0c-176">**Filter verdict**</span></span>
     - <span data-ttu-id="5be0c-177">**傳遞/封鎖原因**</span><span class="sxs-lookup"><span data-stu-id="5be0c-177">**Delivery/Block reason**</span></span>
     - <span data-ttu-id="5be0c-178">**提交識別碼**</span><span class="sxs-lookup"><span data-stu-id="5be0c-178">**Submission ID**</span></span>
     - <span data-ttu-id="5be0c-179">**網路消息識別碼/物件識別碼**</span><span class="sxs-lookup"><span data-stu-id="5be0c-179">**Network Message ID/Object ID**</span></span>
     - <span data-ttu-id="5be0c-180">**方向**</span><span class="sxs-lookup"><span data-stu-id="5be0c-180">**Direction**</span></span>
     - <span data-ttu-id="5be0c-181">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="5be0c-181">**Sender IP**</span></span>
     - <span data-ttu-id="5be0c-182">**大量相容層級 (BCL)**</span><span class="sxs-lookup"><span data-stu-id="5be0c-182">**Bulk compliant level (BCL)**</span></span>
     - <span data-ttu-id="5be0c-183">**目的地**</span><span class="sxs-lookup"><span data-stu-id="5be0c-183">**Destination**</span></span>
     - <span data-ttu-id="5be0c-184">**原則動作**</span><span class="sxs-lookup"><span data-stu-id="5be0c-184">**Policy action**</span></span>
     - <span data-ttu-id="5be0c-185">**提交者**</span><span class="sxs-lookup"><span data-stu-id="5be0c-185">**Submitted by**</span></span>

     <span data-ttu-id="5be0c-186">當您完成時 **，按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-186">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="5be0c-187">若要篩選項目，請按一下 [ **篩選**]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-187">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="5be0c-188">可用的篩選條件如下：</span><span class="sxs-lookup"><span data-stu-id="5be0c-188">The available filters are:</span></span>
     - <span data-ttu-id="5be0c-189">**提交日期**： **開始日期** 和 **結束日期**。</span><span class="sxs-lookup"><span data-stu-id="5be0c-189">**Date submitted**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="5be0c-190">**提交類型**： **電子郵件**、 **URL** 或 **檔案**。</span><span class="sxs-lookup"><span data-stu-id="5be0c-190">**Submission type**: **Email**, **URL**, or **File**.</span></span>
     - <span data-ttu-id="5be0c-191">**提交識別碼**：指派給每個提交的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="5be0c-191">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
     - <span data-ttu-id="5be0c-192">**網路消息識別碼**</span><span class="sxs-lookup"><span data-stu-id="5be0c-192">**Network Message ID**</span></span>
     - <span data-ttu-id="5be0c-193">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5be0c-193">**Sender**</span></span>

     <span data-ttu-id="5be0c-194">當您完成時 **，按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-194">When you're finished, click **Apply**.</span></span>

     ![管理員報送的新篩選選項](../../media/admin-submission-email-filter-options.png)

   - <span data-ttu-id="5be0c-196">若要群組專案，請按一下 [ **群組** ]，然後從下拉式清單中選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="5be0c-196">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="5be0c-197">**無**</span><span class="sxs-lookup"><span data-stu-id="5be0c-197">**None**</span></span>
     - <span data-ttu-id="5be0c-198">**類型**</span><span class="sxs-lookup"><span data-stu-id="5be0c-198">**Type**</span></span>
     - <span data-ttu-id="5be0c-199">**原因**</span><span class="sxs-lookup"><span data-stu-id="5be0c-199">**Reason**</span></span>
     - <span data-ttu-id="5be0c-200">**狀態**</span><span class="sxs-lookup"><span data-stu-id="5be0c-200">**Status**</span></span>
     - <span data-ttu-id="5be0c-201">**重新掃描結果**</span><span class="sxs-lookup"><span data-stu-id="5be0c-201">**Rescan result**</span></span>

   - <span data-ttu-id="5be0c-202">若要匯出專案，請按一下 [ **匯出**]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-202">To export the entries, click **Export**.</span></span> <span data-ttu-id="5be0c-203">在出現的對話方塊中，儲存 .csv 檔。</span><span class="sxs-lookup"><span data-stu-id="5be0c-203">In the dialog that appears, save the .csv file.</span></span>

### <a name="admin-submission-rescan-details"></a><span data-ttu-id="5be0c-204">系統管理員提交重新掃描詳細資料</span><span class="sxs-lookup"><span data-stu-id="5be0c-204">Admin submission rescan details</span></span>

<span data-ttu-id="5be0c-205">在系統管理提交中送出的郵件會重新掃描，並顯示在提交詳細資料浮出控制項中的結果：</span><span class="sxs-lookup"><span data-stu-id="5be0c-205">Messages that are submitted in admin submissions are rescanned and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="5be0c-206">寄件者在傳遞電子郵件時，電子郵件驗證是否失敗。</span><span class="sxs-lookup"><span data-stu-id="5be0c-206">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="5be0c-207">任何有關可能會影響或覆寫郵件決策的原則點擊的資訊。</span><span class="sxs-lookup"><span data-stu-id="5be0c-207">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="5be0c-208">目前的引爆結果，查看郵件中所含的 URL 或檔案是否惡意。</span><span class="sxs-lookup"><span data-stu-id="5be0c-208">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="5be0c-209">Graders 的意見反應。</span><span class="sxs-lookup"><span data-stu-id="5be0c-209">Feedback from graders.</span></span>

<span data-ttu-id="5be0c-210">如果發現覆寫，則應該會在幾分鐘內完成重新掃描。</span><span class="sxs-lookup"><span data-stu-id="5be0c-210">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="5be0c-211">如果電子郵件驗證或傳遞中沒有問題，則不會受到覆寫的影響，來自 graders 的意見反應可能需要一天。</span><span class="sxs-lookup"><span data-stu-id="5be0c-211">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="5be0c-212">查看 Microsoft 的使用者報送</span><span class="sxs-lookup"><span data-stu-id="5be0c-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="5be0c-213">如果您已部署 [報表訊息增益集](enable-the-report-message-add-in.md)、[報告網路釣魚增益集](enable-the-report-phish-add-in.md)或人員在 [Outlook 網頁版中使用內建報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)，您可以在 [**使用者報告的郵件**] 索引標籤上看到要報告的使用者。</span><span class="sxs-lookup"><span data-stu-id="5be0c-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User reported message** tab.</span></span>

1. <span data-ttu-id="5be0c-214">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **提交**]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-214">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="5be0c-215">在 [ **提交** ] 頁面上，選取 [ **使用者報告的郵件** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5be0c-215">On the **Submissions** page, select the **User reported messages** tab.</span></span>

   - <span data-ttu-id="5be0c-216">您可以按一下可用的欄標題，排序專案。</span><span class="sxs-lookup"><span data-stu-id="5be0c-216">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="5be0c-217">按一下 [ **自訂欄** ] 以顯示最多7欄。</span><span class="sxs-lookup"><span data-stu-id="5be0c-217">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="5be0c-218">預設值會標上星號 (<sup>\*</sup>)：</span><span class="sxs-lookup"><span data-stu-id="5be0c-218">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

     - <span data-ttu-id="5be0c-219">**電子郵件主題**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5be0c-219">**Email subject**<sup>\*</sup></span></span>
     - <span data-ttu-id="5be0c-220">**報告者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5be0c-220">**Reported by**<sup>\*</sup></span></span>
     - <span data-ttu-id="5be0c-221">**報告日期**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5be0c-221">**Date reported**<sup>\*</sup></span></span>
     - <span data-ttu-id="5be0c-222">**寄件者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5be0c-222">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="5be0c-223">**報告原因**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5be0c-223">**Reported reason**<sup>\*</sup></span></span>
     - <span data-ttu-id="5be0c-224">**重新掃描結果**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5be0c-224">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="5be0c-225">**訊息報告識別碼**</span><span class="sxs-lookup"><span data-stu-id="5be0c-225">**Message reported ID**</span></span>
     - <span data-ttu-id="5be0c-226">**網路消息識別碼**</span><span class="sxs-lookup"><span data-stu-id="5be0c-226">**Network Message ID**</span></span>
     - <span data-ttu-id="5be0c-227">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="5be0c-227">**Sender IP**</span></span>
     - <span data-ttu-id="5be0c-228">**網路釣魚模擬模擬**</span><span class="sxs-lookup"><span data-stu-id="5be0c-228">**Phish simulation**</span></span>

     <span data-ttu-id="5be0c-229">當您完成時 **，按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-229">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="5be0c-230">若要篩選項目，請按一下 [ **篩選**]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-230">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="5be0c-231">可用的篩選條件如下：</span><span class="sxs-lookup"><span data-stu-id="5be0c-231">The available filters are:</span></span>
     - <span data-ttu-id="5be0c-232">**報告日期**： **開始日期** 和 **結束日期**。</span><span class="sxs-lookup"><span data-stu-id="5be0c-232">**Date reported**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="5be0c-233">**報告者**</span><span class="sxs-lookup"><span data-stu-id="5be0c-233">**Reported by**</span></span>
     - <span data-ttu-id="5be0c-234">**電子郵件主旨**</span><span class="sxs-lookup"><span data-stu-id="5be0c-234">**Email subject**</span></span>
     - <span data-ttu-id="5be0c-235">**訊息報告識別碼**</span><span class="sxs-lookup"><span data-stu-id="5be0c-235">**Message reported ID**</span></span>
     - <span data-ttu-id="5be0c-236">**網路消息識別碼**</span><span class="sxs-lookup"><span data-stu-id="5be0c-236">**Network Message ID**</span></span>
     - <span data-ttu-id="5be0c-237">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5be0c-237">**Sender**</span></span>
     - <span data-ttu-id="5be0c-238">已 **報告原因**：**非垃圾郵件**、**網路釣魚** 或 **垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="5be0c-238">**Reported reason**: **Not junk**, **Phish**, or **Spam**.</span></span>
     - <span data-ttu-id="5be0c-239">**網路釣魚模擬**： **是** 或 **否**</span><span class="sxs-lookup"><span data-stu-id="5be0c-239">**Phish simulation**: **Yes** or **No**</span></span>

     <span data-ttu-id="5be0c-240">當您完成時 **，按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-240">When you're finished, click **Apply**.</span></span>

    ![使用者提交的新篩選選項](../../media/user-submissions-filter-options.png)

   - <span data-ttu-id="5be0c-242">若要群組專案，請按一下 [ **群組** ]，然後從下拉式清單中選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="5be0c-242">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="5be0c-243">**無**</span><span class="sxs-lookup"><span data-stu-id="5be0c-243">**None**</span></span>
     - <span data-ttu-id="5be0c-244">**原因**</span><span class="sxs-lookup"><span data-stu-id="5be0c-244">**Reason**</span></span>
     - <span data-ttu-id="5be0c-245">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5be0c-245">**Sender**</span></span>
     - <span data-ttu-id="5be0c-246">**報告者**</span><span class="sxs-lookup"><span data-stu-id="5be0c-246">**Reported by**</span></span>
     - <span data-ttu-id="5be0c-247">**重新掃描結果**</span><span class="sxs-lookup"><span data-stu-id="5be0c-247">**Rescan result**</span></span>
     - <span data-ttu-id="5be0c-248">**網路釣魚模擬模擬**</span><span class="sxs-lookup"><span data-stu-id="5be0c-248">**Phish simulation**</span></span>

   - <span data-ttu-id="5be0c-249">若要匯出專案，請按一下 [ **匯出**]。</span><span class="sxs-lookup"><span data-stu-id="5be0c-249">To export the entries, click **Export**.</span></span> <span data-ttu-id="5be0c-250">在出現的對話方塊中，儲存 .csv 檔。</span><span class="sxs-lookup"><span data-stu-id="5be0c-250">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="5be0c-251">如果組織已設定為將使用者報告的郵件傳送至自訂信箱，則不會傳送報告的郵件進行重新掃描，而且 **使用者報告的訊息** 中的結果將永遠為空。</span><span class="sxs-lookup"><span data-stu-id="5be0c-251">If organizations are configured to send user reported messages to the custom mailbox only, reported messages will not be sent for rescan and the results in **User reported messages** will always be empty.</span></span>

### <a name="undo-user-submissions"></a><span data-ttu-id="5be0c-252">撤銷使用者報送</span><span class="sxs-lookup"><span data-stu-id="5be0c-252">Undo user submissions</span></span>

<span data-ttu-id="5be0c-253">一旦使用者將可疑的電子郵件提交至自訂信箱，使用者和系統管理員就沒有任何可復原提交的選項。</span><span class="sxs-lookup"><span data-stu-id="5be0c-253">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="5be0c-254">如果使用者想要復原電子郵件，將可在 [刪除的郵件] 或 [垃圾郵件] 資料夾中復原。</span><span class="sxs-lookup"><span data-stu-id="5be0c-254">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="5be0c-255">從自訂信箱將郵件提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="5be0c-255">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="5be0c-256">如果您已將自訂信箱設定為在未傳送郵件給 Microsoft 的情況下截獲使用者報告的郵件，您可以尋找特定郵件並將其傳送給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="5be0c-256">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="5be0c-257">這會有效地將使用者提交權移至系統管理員提交。</span><span class="sxs-lookup"><span data-stu-id="5be0c-257">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="5be0c-258">在 [ **使用者報告的郵件** ] 索引標籤上，選取清單中的訊息，按一下 [ **提交給 Microsoft 進行分析**]，然後從下拉式清單中選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="5be0c-258">On the **User reported messages** tab, select a message in the list, click **Submit to Microsoft for analysis**, and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="5be0c-259">**報告清理**</span><span class="sxs-lookup"><span data-stu-id="5be0c-259">**Report clean**</span></span>
- <span data-ttu-id="5be0c-260">**報告網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="5be0c-260">**Report phishing**</span></span>
- <span data-ttu-id="5be0c-261">**報告惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="5be0c-261">**Report malware**</span></span>
- <span data-ttu-id="5be0c-262">**報告垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="5be0c-262">**Report spam**</span></span>
- <span data-ttu-id="5be0c-263">**觸發調查**</span><span class="sxs-lookup"><span data-stu-id="5be0c-263">**Trigger investigation**</span></span>

![動作按鈕上的新選項](../../media/user-submission-custom-mailbox-action-button.png)
