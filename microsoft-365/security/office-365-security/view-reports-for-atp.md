---
title: 查看高級威脅防護的報告
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
description: 在安全性與合規性中心尋找及使用 Office 365 的「高級威脅防護」報告 &amp; 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c1e1df0d4c1da228da1e09a626dd388d8d7cf7aa
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413445"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="5e4ed-103">檢視 Office 365 進階威脅防護的報告</span><span class="sxs-lookup"><span data-stu-id="5e4ed-103">View reports for Office 365 Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5e4ed-104">Office 365 Advanced 威脅防護 (ATP) 組織 (例如，Microsoft 365 E5 訂閱或 ATP Plan 1 或 ATP Plan 2 附加元件) 包含各種與安全性相關的報表。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-104">Office 365 Advanced Threat Protection (ATP) organizations (for example, Microsoft 365 E5 subscriptions or ATP Plan 1 or ATP Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="5e4ed-105">如果您有 [必要的許可權](#what-permissions-are-needed-to-view-the-atp-reports)，您可以移至 [ **報表**] \> **儀表板**，在安全性 & 規範中心中查看這些報告。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="5e4ed-106">若要直接移至 [報告] 儀表板，請開啟] <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![安全性 & 規範中心內的報告儀表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a><span data-ttu-id="5e4ed-108">進階威脅防護檔案類型報告</span><span class="sxs-lookup"><span data-stu-id="5e4ed-108">Advanced Threat Protection file types report</span></span>

<span data-ttu-id="5e4ed-109">「 **高級威脅防護檔案類型報告** 」報告會向您顯示以 [安全附件](atp-safe-attachments.md)偵測到的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-109">The **Advanced Threat Protection file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="5e4ed-110">報表的匯總視圖允許90天的篩選，而詳細資料檢視只允許10天的篩選。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="5e4ed-111">若要查看報告，請開啟 [安全性 & 合規性中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **Office ATP 檔案類型**]。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP file types**.</span></span> <span data-ttu-id="5e4ed-112">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=ATPFileReport> 。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![報表儀表板中的 Office ATP 檔案類型構件](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="5e4ed-114">您也可以在「 [高級威脅防護郵件](#advanced-threat-protection-message-disposition-report)處理」報告中使用此報告中的資訊。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-114">The information in this report is also available in the [Advanced Threat Protection message disposition report](#advanced-threat-protection-message-disposition-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="5e4ed-115">高級威脅防護檔案類型報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="5e4ed-115">Report view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="5e4ed-116">可供使用的視圖如下：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-116">The following views are available:</span></span>

- <span data-ttu-id="5e4ed-117">**資料查看依據：** 檔案：此圖表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="5e4ed-118">**惡意 Excel 附件**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="5e4ed-119">**惡意的 Flash 附件**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="5e4ed-120">**惡意的 PDF 附件**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="5e4ed-121">**惡意 PowerPoint 附件**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="5e4ed-122">**惡意 URLs**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="5e4ed-123">**惡意的 Word 附件**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="5e4ed-124">**惡意可執行附件**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="5e4ed-125">**別人**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-125">**Others**</span></span>

  <span data-ttu-id="5e4ed-126">當您將滑鼠停留在特定日期 (資料點) 時，您可以看到 EOP 中 [安全附件](atp-safe-attachments.md) 和 [反惡意程式碼保護](anti-malware-protection.md)偵測到的惡意檔案類型細目。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![ATP 檔案類型報告中的檔查看](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="5e4ed-128">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="5e4ed-129">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5e4ed-130">圖表中顯示的相同檔案類型值。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="5e4ed-131">**資料查看方式：訊息**：此圖表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="5e4ed-132">**封鎖存取**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-132">**Block access**</span></span>
  - <span data-ttu-id="5e4ed-133">**取代郵件**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-133">**Messages replaced**</span></span>
  - <span data-ttu-id="5e4ed-134">**監控的郵件**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-134">**Messages monitored**</span></span>
  - <span data-ttu-id="5e4ed-135">以**動態電子郵件傳遞取代**：如需詳細資訊，請參閱[在安全附件原則中傳遞](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![ATP 檔案類型報告中的郵件視圖](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="5e4ed-137">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="5e4ed-138">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5e4ed-139">圖表中可用的相同郵件處置值，以及已傳遞的其他 **郵件** 值。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="5e4ed-140">高級威脅防護檔案類型報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="5e4ed-140">Details table view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="5e4ed-141">如果您按一下 [ **查看詳細資料] 表格**，此報告可提供最近10天內所有按一下動作的近乎即時視圖。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="5e4ed-142">顯示的資訊取決於您所看到的圖表：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="5e4ed-143">**資料查看依據：** 檔案：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-143">**View data by: File**:</span></span>

  - <span data-ttu-id="5e4ed-144">**Date**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-144">**Date**</span></span>
  - <span data-ttu-id="5e4ed-145">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-145">**Recipient address**</span></span>
  - <span data-ttu-id="5e4ed-146">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-146">**Sender address**</span></span>
  - <span data-ttu-id="5e4ed-147">**郵件識別碼**：郵件頭的 **Message-ID** 標頭欄位中可用，且應該是唯一的。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="5e4ed-148">範例值 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (記下角括弧) 。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="5e4ed-149">**File**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-149">**File**</span></span>

  <span data-ttu-id="5e4ed-150">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="5e4ed-151">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5e4ed-152">圖表中顯示的相同檔案類型值。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="5e4ed-153">**資料查看依據：訊息**：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="5e4ed-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-154">**Date**</span></span>
  - <span data-ttu-id="5e4ed-155">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-155">**Recipient address**</span></span>
  - <span data-ttu-id="5e4ed-156">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-156">**Sender address**</span></span>
  - <span data-ttu-id="5e4ed-157">**郵件識別碼**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-157">**Message ID**</span></span>
  - <span data-ttu-id="5e4ed-158">**File**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-158">**File**</span></span>
  - <span data-ttu-id="5e4ed-159">**Subject**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-159">**Subject**</span></span>

  <span data-ttu-id="5e4ed-160">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="5e4ed-161">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5e4ed-162">圖表中可用的相同郵件處置值，以及已傳遞的其他 **郵件** 值。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="5e4ed-163">若要回到 [報表] 視圖，請按一下 [ **view report**]。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-163">To get back to the reports view, click **View report**.</span></span>

## <a name="advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="5e4ed-164">進階威脅防護郵件處置報告</span><span class="sxs-lookup"><span data-stu-id="5e4ed-164">Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="5e4ed-165">**ATP 郵件**處理報告會顯示偵測到有惡意內容的電子郵件所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="5e4ed-166">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **Office ATP 郵件**處理]。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP message disposition**.</span></span> <span data-ttu-id="5e4ed-167">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=ATPMessageReport> 。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![報表儀表板中的 Office 365 ATP 郵件處置小工具](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="5e4ed-169">您也可以在「 [高級威脅防護檔案類型」報告](#advanced-threat-protection-file-types-report)中使用此報告中的資訊。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-169">The information in this report is also available in the [Advanced Threat Protection file types report](#advanced-threat-protection-file-types-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="5e4ed-170">高級威脅防護郵件處理報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="5e4ed-170">Report view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="5e4ed-171">可供使用的視圖如下：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-171">The following views are available:</span></span>

- <span data-ttu-id="5e4ed-172">**資料查看方式：訊息**：此圖表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="5e4ed-173">**封鎖存取**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-173">**Block access**</span></span>
  - <span data-ttu-id="5e4ed-174">**取代郵件**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-174">**Messages replaced**</span></span>
  - <span data-ttu-id="5e4ed-175">**監控的郵件**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-175">**Messages monitored**</span></span>
  - <span data-ttu-id="5e4ed-176">以**動態電子郵件傳遞取代**：如需詳細資訊，請參閱[在安全附件原則中傳遞](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![ATP 檔案類型報告中的郵件視圖](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="5e4ed-178">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="5e4ed-179">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5e4ed-180">圖表中可用的相同郵件處置值，以及已傳遞的其他 **郵件** 值。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="5e4ed-181">**資料查看依據：** 檔案：此圖表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="5e4ed-182">**惡意 Excel 附件**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="5e4ed-183">**惡意的 Flash 附件**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="5e4ed-184">**惡意的 PDF 附件**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="5e4ed-185">**惡意 PowerPoint 附件**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="5e4ed-186">**惡意 URLs**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="5e4ed-187">**惡意的 Word 附件**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="5e4ed-188">**惡意可執行附件**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="5e4ed-189">**別人**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-189">**Others**</span></span>

  <span data-ttu-id="5e4ed-190">當您將滑鼠停留在特定日期 (資料點) 時，您可以看到 EOP 中 [安全附件](atp-safe-attachments.md) 和 [反惡意程式碼保護](anti-malware-protection.md)偵測到的惡意檔案類型細目。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![ATP 檔案類型報告中的檔查看](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="5e4ed-192">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="5e4ed-193">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5e4ed-194">圖表中顯示的相同檔案類型值。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="5e4ed-195">高級威脅防護郵件處理報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="5e4ed-195">Details table view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="5e4ed-196">如果您按一下 [ **查看詳細資料] 表格**，此報告可提供最近10天內所有按一下動作的近乎即時視圖。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="5e4ed-197">顯示的資訊取決於您所看到的圖表：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="5e4ed-198">**資料查看依據：訊息**：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="5e4ed-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-199">**Date**</span></span>
  - <span data-ttu-id="5e4ed-200">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-200">**Recipient address**</span></span>
  - <span data-ttu-id="5e4ed-201">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-201">**Sender address**</span></span>
  - <span data-ttu-id="5e4ed-202">**郵件識別碼**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-202">**Message ID**</span></span>
  - <span data-ttu-id="5e4ed-203">**File**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-203">**File**</span></span>
  - <span data-ttu-id="5e4ed-204">**Subject**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-204">**Subject**</span></span>

  <span data-ttu-id="5e4ed-205">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="5e4ed-206">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5e4ed-207">圖表中可用的相同郵件處置值，以及已傳遞的其他 **郵件** 值。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="5e4ed-208">**資料查看依據：** 檔案：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-208">**View data by: File**:</span></span>

  - <span data-ttu-id="5e4ed-209">**Date**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-209">**Date**</span></span>
  - <span data-ttu-id="5e4ed-210">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-210">**Recipient address**</span></span>
  - <span data-ttu-id="5e4ed-211">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-211">**Sender address**</span></span>
  - <span data-ttu-id="5e4ed-212">**郵件識別碼**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-212">**Message ID**</span></span>
  - <span data-ttu-id="5e4ed-213">**File**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-213">**File**</span></span>

  <span data-ttu-id="5e4ed-214">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="5e4ed-215">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5e4ed-216">圖表中顯示的相同檔案類型值。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="5e4ed-217">若要回到 [報表] 視圖，請按一下 [ **view report**]。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-217">To get back to the reports view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="5e4ed-218">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="5e4ed-218">Threat protection status report</span></span>

<span data-ttu-id="5e4ed-219">「 **威脅防護狀態** 報告」是單一的視圖，可彙集 [Exchange ONLINE protection](exchange-online-protection-overview.md) (EOP) 和 Office 365 ATP 所偵測到和封鎖的惡意內容和惡意電子郵件資訊。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-219">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Office 365 ATP.</span></span> <span data-ttu-id="5e4ed-220">如需詳細資訊，請參閱 [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-220">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="5e4ed-221">URL 威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="5e4ed-221">URL threat protection report</span></span>

<span data-ttu-id="5e4ed-222">**Url 威脅防護報告**可提供偵測到之威脅的摘要和趨勢視圖，以及在 URL 按一下上做為[安全連結](atp-safe-links.md)的一部分所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-222">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="5e4ed-223">若已套用安全連結原則的使用者沒有選取 [不 **追蹤使用者點擊** ] 選項，則此報告將不會有按一下其資料的使用者。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-223">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="5e4ed-224">若要查看報告，請開啟 [安全性 & 合規性中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **URL 保護報告**]。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-224">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="5e4ed-225">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=URLProtectionActionReport> 。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-225">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![報表儀表板中的 URL 保護報告構件](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="5e4ed-227">這是一項 *保護趨勢報告*，表示資料代表較大資料集的趨勢。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-227">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="5e4ed-228">因此，在這種情況下，不會即時提供匯總視圖中的資料，但 [詳細資料] 表格視圖中的資料則是如此，您可能會看到這兩種視圖之間稍有差異。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-228">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="5e4ed-229">URL 威脅防護報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="5e4ed-229">Report view for the URL threat protection report</span></span>

<span data-ttu-id="5e4ed-230">**URL 威脅防護**報告有兩個匯總的視圖，每四個小時都會重新整理一次，以顯示過去90天的資料：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-230">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="5e4ed-231">**URL 按一下保護動作**：顯示組織中的使用者按下 URL 按一下數目及按一下的結果：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-231">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="5e4ed-232">**封鎖** (禁止使用者流覽至 URL) </span><span class="sxs-lookup"><span data-stu-id="5e4ed-232">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="5e4ed-233">**封鎖並按一下**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-233">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="5e4ed-234">**在掃描期間按一下**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-234">**Clicked through during scan**</span></span>

  <span data-ttu-id="5e4ed-235">按一下表示使用者已透過封鎖頁面按一下至惡意網站 (系統管理員可以停用 [安全連結) 原則] 中的 click。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-235">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="5e4ed-236">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-236">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="5e4ed-237">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-237">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5e4ed-238">可使用的 [保護動作]，加上 **允許 (使用者** 流覽至 URL) 的值。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-238">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![Url 威脅防護報告中的 URL 按一下保護動作視圖](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="5e4ed-240">**依應用程式按一下 url**：會顯示支援安全連結之應用程式的 url 按一下數目：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-240">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="5e4ed-241">**電子郵件用戶端**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-241">**Email client**</span></span>
  - <span data-ttu-id="5e4ed-242">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-242">**PowerPoint**</span></span>
  - <span data-ttu-id="5e4ed-243">**Word**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-243">**Word**</span></span>
  - <span data-ttu-id="5e4ed-244">**Excel**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-244">**Excel**</span></span>
  - <span data-ttu-id="5e4ed-245">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-245">**OneNote**</span></span>
  - <span data-ttu-id="5e4ed-246">**Visio**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-246">**Visio**</span></span>
  - <span data-ttu-id="5e4ed-247">**Teams**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-247">**Teams**</span></span>
  - <span data-ttu-id="5e4ed-248">**其他**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-248">**Other**</span></span>

  <span data-ttu-id="5e4ed-249">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-249">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="5e4ed-250">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-250">**Start date** and **End date**</span></span>
  - <span data-ttu-id="5e4ed-251">可用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-251">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="5e4ed-252">URL 威脅防護報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="5e4ed-252">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="5e4ed-253">如果您按一下 [ **查看詳細資料] 表格**，則報告會提供最近7天內組織內所有按一下動作的近乎即時視圖，其詳細資料如下：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-253">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="5e4ed-254">**按一下 [時間]**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-254">**Click time**</span></span>
- <span data-ttu-id="5e4ed-255">**使用者**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-255">**User**</span></span>
- <span data-ttu-id="5e4ed-256">**URL**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-256">**URL**</span></span>
- <span data-ttu-id="5e4ed-257">**Action**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-257">**Action**</span></span>
- <span data-ttu-id="5e4ed-258">**App**</span><span class="sxs-lookup"><span data-stu-id="5e4ed-258">**App**</span></span>

<span data-ttu-id="5e4ed-259">如果您按一下 [詳細資料] 表格視圖中的 [**篩選器**]，可以篩選與報表檢視中相同的準則，**以及以逗號分隔的\*\*\*\*網域**或收件者。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-259">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="5e4ed-260">若要回到 [報表] 視圖，請按一下 [ **view report**]。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-260">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="5e4ed-261">要查看的其他報告</span><span class="sxs-lookup"><span data-stu-id="5e4ed-261">Additional reports to view</span></span>

<span data-ttu-id="5e4ed-262">除了本主題所述的 ATP 報告之外，還有其他幾個報告可供使用，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-262">In addition to the ATP reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="5e4ed-263">報告</span><span class="sxs-lookup"><span data-stu-id="5e4ed-263">Report</span></span>|<span data-ttu-id="5e4ed-264">主題</span><span class="sxs-lookup"><span data-stu-id="5e4ed-264">Topic</span></span>|
|---|---|
|<span data-ttu-id="5e4ed-265">**Explorer** (atp 方案 2) 或 **即時** 偵測 (ATP plan 1) </span><span class="sxs-lookup"><span data-stu-id="5e4ed-265">**Explorer** (ATP Plan 2) or **real-time detections** (ATP Plan 1)</span></span>|[<span data-ttu-id="5e4ed-266">威脅總管 (及即時偵測)</span><span class="sxs-lookup"><span data-stu-id="5e4ed-266">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="5e4ed-267">**電子郵件安全性報告**，例如主要寄件者和收件者報告、冒名郵件報告和垃圾郵件偵測報告。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-267">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="5e4ed-268">檢視安全性與合規性中心內的電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="5e4ed-268">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="5e4ed-269">**郵件流程報告**，例如轉寄報告、郵件流程狀態報表，以及主要寄件者和收件者報告。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-269">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="5e4ed-270">在安全性 & 規範中心內，查看郵件流程報告</span><span class="sxs-lookup"><span data-stu-id="5e4ed-270">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="5e4ed-271">**安全連結的 URL 追蹤** (僅 PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-271">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="5e4ed-272">此 Cmdlet 的輸出會顯示過去7天中安全連結動作的結果。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-272">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="5e4ed-273">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="5e4ed-273">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="5e4ed-274">**EOP 和 ATP (的郵件流量結果** 只 PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-274">**Mail traffic results for EOP and ATP** (PowerShell only).</span></span> <span data-ttu-id="5e4ed-275">此 Cmdlet 的輸出包含網域、日期、事件種類、方向、動作和郵件數目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-275">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="5e4ed-276">MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="5e4ed-276">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="5e4ed-277">**EOP 和 ATP 偵測的郵件詳細資料包告** (僅 PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-277">**Mail detail reports for EOP and ATP detections** (PowerShell only).</span></span> <span data-ttu-id="5e4ed-278">此 Cmdlet 的輸出包含有關電子郵件或檔案中惡意檔案或 URLs、網路釣魚企圖、模仿及其他潛在威脅的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-278">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="5e4ed-279">MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="5e4ed-279">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="5e4ed-280">查看 ATP 報表所需的許可權為何？</span><span class="sxs-lookup"><span data-stu-id="5e4ed-280">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="5e4ed-281">若要查看和使用本主題中所述的報表， **您必須為安全性與 &amp; 合規性中心和 Exchange 系統管理中心指派適當的角色**。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-281">In order to view and use the reports described in this topic, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="5e4ed-282">針對安全性 & 合規性中心，您必須已指派下列角色之一：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-282">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="5e4ed-283">組織管理</span><span class="sxs-lookup"><span data-stu-id="5e4ed-283">Organization Management</span></span>
  - <span data-ttu-id="5e4ed-284">安全性系統管理員 (這可以在 Azure Active Directory 系統管理中心指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="5e4ed-284">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="5e4ed-285">安全性操作員 (可以在 Azure Active Directory 系統管理中心中指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com)) # A3</span><span class="sxs-lookup"><span data-stu-id="5e4ed-285">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="5e4ed-286">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="5e4ed-286">Security Reader</span></span>

- <span data-ttu-id="5e4ed-287">針對 Exchange Online，您必須在 Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)) 受指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-287">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="5e4ed-288">組織管理</span><span class="sxs-lookup"><span data-stu-id="5e4ed-288">Organization Management</span></span>
  - <span data-ttu-id="5e4ed-289">僅檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="5e4ed-289">View-only Organization Management</span></span>
  - <span data-ttu-id="5e4ed-290">僅檢視收件者角色</span><span class="sxs-lookup"><span data-stu-id="5e4ed-290">View-Only Recipients role</span></span>
  - <span data-ttu-id="5e4ed-291">合規性管理</span><span class="sxs-lookup"><span data-stu-id="5e4ed-291">Compliance Management</span></span>

<span data-ttu-id="5e4ed-292">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="5e4ed-292">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="5e4ed-293">安全性與合規性中心的權限</span><span class="sxs-lookup"><span data-stu-id="5e4ed-293">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="5e4ed-294">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="5e4ed-294">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="5e4ed-295">如果報告未顯示資料，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="5e4ed-295">What if the reports aren't showing data?</span></span>

<span data-ttu-id="5e4ed-296">如果您未看到 ATP 報告中的資料，請仔細檢查您的原則設定是否正確。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-296">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="5e4ed-297">您的組織必須定義 [安全連結原則](set-up-atp-safe-links-policies.md) 及 [安全附件原則](set-up-atp-safe-attachments-policies.md) ，才能進行 ATP 保護。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-297">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="5e4ed-298">另請參閱 [反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="5e4ed-298">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5e4ed-299">相關主題</span><span class="sxs-lookup"><span data-stu-id="5e4ed-299">Related topics</span></span>

[<span data-ttu-id="5e4ed-300">安全性與合規性中心內的智慧型報表和深入解析</span><span class="sxs-lookup"><span data-stu-id="5e4ed-300">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="5e4ed-301"> (Azure Active Directory 的角色許可權</span><span class="sxs-lookup"><span data-stu-id="5e4ed-301">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
