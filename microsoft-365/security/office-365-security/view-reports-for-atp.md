---
title: 在報告儀表板中查看 Office 365 報告的 Defender
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 在安全性 & 合規性中心尋找及使用 Microsoft Defender for Office 365 的報告。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1bc9b31a804507ee303f237f453dabe7da28a538
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908193"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a><span data-ttu-id="c46ce-103">在安全性 & 規範中心的報表儀表板中，查看 Office 365 報表的 Defender</span><span class="sxs-lookup"><span data-stu-id="c46ce-103">View Defender for Office 365 reports in the Reports dashboard in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c46ce-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="c46ce-104">**Applies to**</span></span>
- [<span data-ttu-id="c46ce-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="c46ce-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c46ce-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c46ce-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c46ce-107">Microsoft Defender for Office 365 組織 (例如，Microsoft 365 E5 訂閱或 Microsoft Defender for Office 365 Plan 1 或 Microsoft Defender for Office 365 方案2增益集) 包含各種安全性相關的報告。</span><span class="sxs-lookup"><span data-stu-id="c46ce-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="c46ce-108">如果您有 [必要的許可權](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)，您可以移至 [ **報表**] \> **儀表板**，在安全性 & 規範中心中查看這些報告。</span><span class="sxs-lookup"><span data-stu-id="c46ce-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="c46ce-109">若要直接移至 [報告] 儀表板，請開啟] <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="c46ce-109">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![安全性 & 規範中心內的報告儀表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="c46ce-111">適用於 Office 365 的 Defender 檔案類型報告</span><span class="sxs-lookup"><span data-stu-id="c46ce-111">Defender for Office 365 file types report</span></span>

<span data-ttu-id="c46ce-112">[ **Office 365 的 Defender] 檔案類型報告** 報告會顯示偵測為 [安全附件](atp-safe-attachments.md)的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="c46ce-112">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="c46ce-113">報表的匯總視圖允許90天的篩選，而詳細資料檢視只允許10天的篩選。</span><span class="sxs-lookup"><span data-stu-id="c46ce-113">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="c46ce-114">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **Office 365 檔案類型的 Defender**]。</span><span class="sxs-lookup"><span data-stu-id="c46ce-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="c46ce-115">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=ATPFileReport> 。</span><span class="sxs-lookup"><span data-stu-id="c46ce-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![報表儀表板中的 Office 365 檔案類型構件](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="c46ce-117">您也可以在 [Office 365 的 [Defender For Office 郵件](#defender-for-office-365-message-disposition-report)處理] 報告中取得此報告中的資訊。</span><span class="sxs-lookup"><span data-stu-id="c46ce-117">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="c46ce-118">適用于 Office 365 檔案類型的報表檢視報告</span><span class="sxs-lookup"><span data-stu-id="c46ce-118">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="c46ce-119">可供使用的視圖如下：</span><span class="sxs-lookup"><span data-stu-id="c46ce-119">The following views are available:</span></span>

- <span data-ttu-id="c46ce-120">**資料查看依據：** 檔案：此圖表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c46ce-120">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="c46ce-121">**惡意 Excel 附件**</span><span class="sxs-lookup"><span data-stu-id="c46ce-121">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="c46ce-122">**惡意的 Flash 附件**</span><span class="sxs-lookup"><span data-stu-id="c46ce-122">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="c46ce-123">**惡意的 PDF 附件**</span><span class="sxs-lookup"><span data-stu-id="c46ce-123">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="c46ce-124">**惡意 PowerPoint 附件**</span><span class="sxs-lookup"><span data-stu-id="c46ce-124">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="c46ce-125">**惡意 URLs**</span><span class="sxs-lookup"><span data-stu-id="c46ce-125">**Malicious URLs**</span></span>
  - <span data-ttu-id="c46ce-126">**惡意的 Word 附件**</span><span class="sxs-lookup"><span data-stu-id="c46ce-126">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="c46ce-127">**惡意可執行附件**</span><span class="sxs-lookup"><span data-stu-id="c46ce-127">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="c46ce-128">**別人**</span><span class="sxs-lookup"><span data-stu-id="c46ce-128">**Others**</span></span>

  <span data-ttu-id="c46ce-129">當您將滑鼠停留在特定日期 (資料點) 時，您可以看到 EOP 中 [安全附件](atp-safe-attachments.md) 和 [反惡意程式碼保護](anti-malware-protection.md)偵測到的惡意檔案類型細目。</span><span class="sxs-lookup"><span data-stu-id="c46ce-129">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Office 365 中的檔案視圖檔案類型報告](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="c46ce-131">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="c46ce-131">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="c46ce-132">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c46ce-132">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c46ce-133">圖表中顯示的相同檔案類型值。</span><span class="sxs-lookup"><span data-stu-id="c46ce-133">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="c46ce-134">**資料查看方式：訊息**：此圖表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c46ce-134">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="c46ce-135">**封鎖存取**</span><span class="sxs-lookup"><span data-stu-id="c46ce-135">**Block access**</span></span>
  - <span data-ttu-id="c46ce-136">**取代郵件**</span><span class="sxs-lookup"><span data-stu-id="c46ce-136">**Messages replaced**</span></span>
  - <span data-ttu-id="c46ce-137">**監控的郵件**</span><span class="sxs-lookup"><span data-stu-id="c46ce-137">**Messages monitored**</span></span>
  - <span data-ttu-id="c46ce-138">以 **動態電子郵件傳遞取代**：如需詳細資訊，請參閱 [在安全附件原則中傳遞](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)。</span><span class="sxs-lookup"><span data-stu-id="c46ce-138">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Office 365 的 Defender for Office 檔案類型報告中的郵件視圖](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="c46ce-140">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="c46ce-140">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="c46ce-141">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c46ce-141">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c46ce-142">圖表中可用的相同郵件處置值，以及已傳遞的其他 **郵件** 值。</span><span class="sxs-lookup"><span data-stu-id="c46ce-142">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="c46ce-143">Defender for Office 365 檔案類型報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="c46ce-143">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="c46ce-144">如果您按一下 [ **查看詳細資料] 表格**，此報告可提供最近10天內所有按一下動作的近乎即時視圖。</span><span class="sxs-lookup"><span data-stu-id="c46ce-144">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="c46ce-145">顯示的資訊取決於您所看到的圖表：</span><span class="sxs-lookup"><span data-stu-id="c46ce-145">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="c46ce-146">**資料查看依據：** 檔案：</span><span class="sxs-lookup"><span data-stu-id="c46ce-146">**View data by: File**:</span></span>

  - <span data-ttu-id="c46ce-147">**Date**</span><span class="sxs-lookup"><span data-stu-id="c46ce-147">**Date**</span></span>
  - <span data-ttu-id="c46ce-148">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="c46ce-148">**Recipient address**</span></span>
  - <span data-ttu-id="c46ce-149">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="c46ce-149">**Sender address**</span></span>
  - <span data-ttu-id="c46ce-150">**郵件識別碼**：郵件頭的 **Message-ID** 標頭欄位中可用，且應該是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c46ce-150">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="c46ce-151">範例值 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (記下角括弧) 。</span><span class="sxs-lookup"><span data-stu-id="c46ce-151">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="c46ce-152">**File**</span><span class="sxs-lookup"><span data-stu-id="c46ce-152">**File**</span></span>

  <span data-ttu-id="c46ce-153">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="c46ce-153">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="c46ce-154">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c46ce-154">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c46ce-155">圖表中顯示的相同檔案類型值。</span><span class="sxs-lookup"><span data-stu-id="c46ce-155">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="c46ce-156">**資料查看依據：訊息**：</span><span class="sxs-lookup"><span data-stu-id="c46ce-156">**View data by: Message**:</span></span>

  - <span data-ttu-id="c46ce-157">**Date**</span><span class="sxs-lookup"><span data-stu-id="c46ce-157">**Date**</span></span>
  - <span data-ttu-id="c46ce-158">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="c46ce-158">**Recipient address**</span></span>
  - <span data-ttu-id="c46ce-159">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="c46ce-159">**Sender address**</span></span>
  - <span data-ttu-id="c46ce-160">**郵件識別碼**</span><span class="sxs-lookup"><span data-stu-id="c46ce-160">**Message ID**</span></span>
  - <span data-ttu-id="c46ce-161">**File**</span><span class="sxs-lookup"><span data-stu-id="c46ce-161">**File**</span></span>
  - <span data-ttu-id="c46ce-162">**主旨**</span><span class="sxs-lookup"><span data-stu-id="c46ce-162">**Subject**</span></span>

  <span data-ttu-id="c46ce-163">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="c46ce-163">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="c46ce-164">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c46ce-164">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c46ce-165">圖表中可用的相同郵件處置值，以及已傳遞的其他 **郵件** 值。</span><span class="sxs-lookup"><span data-stu-id="c46ce-165">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="c46ce-166">若要回到 [報表] 視圖，請按一下 [ **view report**]。</span><span class="sxs-lookup"><span data-stu-id="c46ce-166">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="c46ce-167">適用於 Office 365 的 Defender 郵件處置報告</span><span class="sxs-lookup"><span data-stu-id="c46ce-167">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="c46ce-168">**ATP 郵件** 處理報告會顯示偵測到有惡意內容的電子郵件所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="c46ce-168">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="c46ce-169">若要查看報告，請開啟 [安全性 & 合規性中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **Office 365 的 Defender] 進行郵件** 處理。</span><span class="sxs-lookup"><span data-stu-id="c46ce-169">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="c46ce-170">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=ATPMessageReport> 。</span><span class="sxs-lookup"><span data-stu-id="c46ce-170">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![報表儀表板中的 Office 365 郵件處置小工具](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="c46ce-172">您也可以在 [Office 365 檔案類型報告](#defender-for-office-365-file-types-report)中使用此報告中的資訊。</span><span class="sxs-lookup"><span data-stu-id="c46ce-172">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="c46ce-173">適用于 Office 365 的 Defender for Office 郵件處理報告</span><span class="sxs-lookup"><span data-stu-id="c46ce-173">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="c46ce-174">可供使用的視圖如下：</span><span class="sxs-lookup"><span data-stu-id="c46ce-174">The following views are available:</span></span>

- <span data-ttu-id="c46ce-175">**資料查看方式：訊息**：此圖表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c46ce-175">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="c46ce-176">**封鎖存取**</span><span class="sxs-lookup"><span data-stu-id="c46ce-176">**Block access**</span></span>
  - <span data-ttu-id="c46ce-177">**取代郵件**</span><span class="sxs-lookup"><span data-stu-id="c46ce-177">**Messages replaced**</span></span>
  - <span data-ttu-id="c46ce-178">**監控的郵件**</span><span class="sxs-lookup"><span data-stu-id="c46ce-178">**Messages monitored**</span></span>
  - <span data-ttu-id="c46ce-179">以 **動態電子郵件傳遞取代**：如需詳細資訊，請參閱 [在安全附件原則中傳遞](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)。</span><span class="sxs-lookup"><span data-stu-id="c46ce-179">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Office 365 的 Defender for Office 檔案類型報告中的郵件視圖](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="c46ce-181">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="c46ce-181">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="c46ce-182">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c46ce-182">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c46ce-183">圖表中可用的相同郵件處置值，以及已傳遞的其他 **郵件** 值。</span><span class="sxs-lookup"><span data-stu-id="c46ce-183">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="c46ce-184">**資料查看依據：** 檔案：此圖表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c46ce-184">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="c46ce-185">**惡意 Excel 附件**</span><span class="sxs-lookup"><span data-stu-id="c46ce-185">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="c46ce-186">**惡意的 Flash 附件**</span><span class="sxs-lookup"><span data-stu-id="c46ce-186">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="c46ce-187">**惡意的 PDF 附件**</span><span class="sxs-lookup"><span data-stu-id="c46ce-187">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="c46ce-188">**惡意 PowerPoint 附件**</span><span class="sxs-lookup"><span data-stu-id="c46ce-188">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="c46ce-189">**惡意 URLs**</span><span class="sxs-lookup"><span data-stu-id="c46ce-189">**Malicious URLs**</span></span>
  - <span data-ttu-id="c46ce-190">**惡意的 Word 附件**</span><span class="sxs-lookup"><span data-stu-id="c46ce-190">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="c46ce-191">**惡意可執行附件**</span><span class="sxs-lookup"><span data-stu-id="c46ce-191">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="c46ce-192">**別人**</span><span class="sxs-lookup"><span data-stu-id="c46ce-192">**Others**</span></span>

  <span data-ttu-id="c46ce-193">當您將滑鼠停留在特定日期 (資料點) 時，您可以看到 EOP 中 [安全附件](atp-safe-attachments.md) 和 [反惡意程式碼保護](anti-malware-protection.md)偵測到的惡意檔案類型細目。</span><span class="sxs-lookup"><span data-stu-id="c46ce-193">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Office 365 中的檔案視圖檔案類型報告](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="c46ce-195">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="c46ce-195">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="c46ce-196">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c46ce-196">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c46ce-197">圖表中顯示的相同檔案類型值。</span><span class="sxs-lookup"><span data-stu-id="c46ce-197">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="c46ce-198">Defender for Office 365 郵件處理報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="c46ce-198">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="c46ce-199">如果您按一下 [ **查看詳細資料] 表格**，此報告可提供最近10天內所有按一下動作的近乎即時視圖。</span><span class="sxs-lookup"><span data-stu-id="c46ce-199">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="c46ce-200">顯示的資訊取決於您所看到的圖表：</span><span class="sxs-lookup"><span data-stu-id="c46ce-200">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="c46ce-201">**資料查看依據：訊息**：</span><span class="sxs-lookup"><span data-stu-id="c46ce-201">**View data by: Message**:</span></span>

  - <span data-ttu-id="c46ce-202">**Date**</span><span class="sxs-lookup"><span data-stu-id="c46ce-202">**Date**</span></span>
  - <span data-ttu-id="c46ce-203">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="c46ce-203">**Recipient address**</span></span>
  - <span data-ttu-id="c46ce-204">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="c46ce-204">**Sender address**</span></span>
  - <span data-ttu-id="c46ce-205">**郵件識別碼**</span><span class="sxs-lookup"><span data-stu-id="c46ce-205">**Message ID**</span></span>
  - <span data-ttu-id="c46ce-206">**File**</span><span class="sxs-lookup"><span data-stu-id="c46ce-206">**File**</span></span>
  - <span data-ttu-id="c46ce-207">**主旨**</span><span class="sxs-lookup"><span data-stu-id="c46ce-207">**Subject**</span></span>

  <span data-ttu-id="c46ce-208">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="c46ce-208">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="c46ce-209">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c46ce-209">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c46ce-210">圖表中可用的相同郵件處置值，以及已傳遞的其他 **郵件** 值。</span><span class="sxs-lookup"><span data-stu-id="c46ce-210">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="c46ce-211">**資料查看依據：** 檔案：</span><span class="sxs-lookup"><span data-stu-id="c46ce-211">**View data by: File**:</span></span>

  - <span data-ttu-id="c46ce-212">**Date**</span><span class="sxs-lookup"><span data-stu-id="c46ce-212">**Date**</span></span>
  - <span data-ttu-id="c46ce-213">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="c46ce-213">**Recipient address**</span></span>
  - <span data-ttu-id="c46ce-214">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="c46ce-214">**Sender address**</span></span>
  - <span data-ttu-id="c46ce-215">**郵件識別碼**</span><span class="sxs-lookup"><span data-stu-id="c46ce-215">**Message ID**</span></span>
  - <span data-ttu-id="c46ce-216">**File**</span><span class="sxs-lookup"><span data-stu-id="c46ce-216">**File**</span></span>

  <span data-ttu-id="c46ce-217">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="c46ce-217">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="c46ce-218">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c46ce-218">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c46ce-219">圖表中顯示的相同檔案類型值。</span><span class="sxs-lookup"><span data-stu-id="c46ce-219">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="c46ce-220">若要回到 [報表] 視圖，請按一下 [ **view report**]。</span><span class="sxs-lookup"><span data-stu-id="c46ce-220">To get back to the reports view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="c46ce-221">郵件延遲報告</span><span class="sxs-lookup"><span data-stu-id="c46ce-221">Mail latency report</span></span>

<span data-ttu-id="c46ce-222">**郵件延遲報告** 會向您顯示組織內的郵件傳遞和引爆延遲的匯總視圖。</span><span class="sxs-lookup"><span data-stu-id="c46ce-222">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="c46ce-223">服務中的郵件傳遞時間受到多種因素的影響，而且絕對傳遞時間（秒）通常不是成功或問題的明確指示。</span><span class="sxs-lookup"><span data-stu-id="c46ce-223">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="c46ce-224">在一天內的傳遞時間可能會被視為另一天的平均傳遞時間，或反過來。</span><span class="sxs-lookup"><span data-stu-id="c46ce-224">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="c46ce-225">**郵件延遲報告** 會嘗試根據觀察到的其他郵件傳遞時間的統計資料，以限定郵件傳遞：</span><span class="sxs-lookup"><span data-stu-id="c46ce-225">The **Mail latency report** tries to qualify message delivery based on statistical data about the observed delivery times of other messages:</span></span>

- <span data-ttu-id="c46ce-226">第 **50 個百分點**：這是郵件傳遞時間的中間部分。</span><span class="sxs-lookup"><span data-stu-id="c46ce-226">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="c46ce-227">您可以將此值視為平均傳遞時間。</span><span class="sxs-lookup"><span data-stu-id="c46ce-227">You can consider this value as an average delivery time.</span></span>
- <span data-ttu-id="c46ce-228">**90%**：這表示郵件傳遞的高延遲。</span><span class="sxs-lookup"><span data-stu-id="c46ce-228">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="c46ce-229">只有10% 的郵件花費的時間超過此值才能傳遞。</span><span class="sxs-lookup"><span data-stu-id="c46ce-229">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="c46ce-230">**99th 百分點**：這表示郵件傳遞的最高延遲。</span><span class="sxs-lookup"><span data-stu-id="c46ce-230">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="c46ce-231">不包括用戶端和網路延遲。</span><span class="sxs-lookup"><span data-stu-id="c46ce-231">Client side and network latency are not included.</span></span>

<span data-ttu-id="c46ce-232">若要查看報告，請開啟 [安全性 & 合規性中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **郵件延遲報告**]。</span><span class="sxs-lookup"><span data-stu-id="c46ce-232">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mail latency report**.</span></span> <span data-ttu-id="c46ce-233">若要直接前往報表，請開啟 <https://protection.office.com/mailLatencyReport?viewid=P50> 。</span><span class="sxs-lookup"><span data-stu-id="c46ce-233">To go directly to the report, open <https://protection.office.com/mailLatencyReport?viewid=P50>.</span></span>

![報表儀表板中的郵件延遲報告構件](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a><span data-ttu-id="c46ce-235">郵件延遲報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="c46ce-235">Report view for the Mail latency report</span></span>

<span data-ttu-id="c46ce-236">當您開啟報表時，預設會選取 [ **50 百分位數** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c46ce-236">When you open the report, the **50th percentiles** tab is selected by default.</span></span>

<span data-ttu-id="c46ce-237">此視圖預設會包含以下列篩選設定的圖表：</span><span class="sxs-lookup"><span data-stu-id="c46ce-237">By default, this view contains a chart that's configured with the following filters:</span></span>

- <span data-ttu-id="c46ce-238">**日期**：過去7天</span><span class="sxs-lookup"><span data-stu-id="c46ce-238">**Date**: The last 7 days</span></span>
- <span data-ttu-id="c46ce-239">**郵件視圖**：</span><span class="sxs-lookup"><span data-stu-id="c46ce-239">**Message View**:</span></span>
  - <span data-ttu-id="c46ce-240">引爆郵件</span><span class="sxs-lookup"><span data-stu-id="c46ce-240">Detonated messages</span></span>

<span data-ttu-id="c46ce-241">此圖顯示組織成下列類別的郵件：</span><span class="sxs-lookup"><span data-stu-id="c46ce-241">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="c46ce-242">**郵件傳遞延遲**</span><span class="sxs-lookup"><span data-stu-id="c46ce-242">**Mail delivery latency**</span></span>
- <span data-ttu-id="c46ce-243">**引爆延遲**</span><span class="sxs-lookup"><span data-stu-id="c46ce-243">**Detonation latency**</span></span>

<span data-ttu-id="c46ce-244">當您將游標移到圖表中的某個類別時，您可以查看每個類別中的延遲明細。</span><span class="sxs-lookup"><span data-stu-id="c46ce-244">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![郵件延遲報告](../../media/mail-latency-report.png)

<span data-ttu-id="c46ce-246">如果您按一下報表檢視中的 [ **篩選** ]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="c46ce-246">If you click **Filter** in the report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="c46ce-247">所有郵件</span><span class="sxs-lookup"><span data-stu-id="c46ce-247">All messages</span></span>
- <span data-ttu-id="c46ce-248">包含附件或 URLs 的郵件</span><span class="sxs-lookup"><span data-stu-id="c46ce-248">Messages that contain attachments or URLs</span></span>

<span data-ttu-id="c46ce-249">如果您按一下 [ **90 百分位數** ] 索引標籤或 [ **99th 百分位數** ] 索引標籤，則會使用第 **50 個百分位數** 視圖中的相同預設篩選器。</span><span class="sxs-lookup"><span data-stu-id="c46ce-249">If you click the **90th percentiles** tab or the **99th percentiles** tab, the same default filters from the **50th percentiles** view are used.</span></span>

### <a name="details-table-view-for-the-mail-latency-report"></a><span data-ttu-id="c46ce-250">郵件延遲報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="c46ce-250">Details table view for the Mail latency report</span></span>

<span data-ttu-id="c46ce-251">[詳細資料] 表格視圖會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c46ce-251">The following information is shown in the details table view:</span></span>

- <span data-ttu-id="c46ce-252">**Date**</span><span class="sxs-lookup"><span data-stu-id="c46ce-252">**Date**</span></span>
- <span data-ttu-id="c46ce-253">**百分位數**</span><span class="sxs-lookup"><span data-stu-id="c46ce-253">**Percentiles**</span></span>
- <span data-ttu-id="c46ce-254">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="c46ce-254">**Message count**</span></span>
- <span data-ttu-id="c46ce-255">**整體延遲**</span><span class="sxs-lookup"><span data-stu-id="c46ce-255">**Overall latency**</span></span>

![郵件延遲報告詳細資料](../../media/mail-latency-report-details.png)

<span data-ttu-id="c46ce-257">上述顯示于11月14日，所有傳遞和引爆的郵件所經歷的平均延遲為 **108.033** 秒。</span><span class="sxs-lookup"><span data-stu-id="c46ce-257">The above shows that on November 14 the average latency experienced for all messages delivered and detonated was **108.033** seconds.</span></span>

<span data-ttu-id="c46ce-258">[詳細資料] 表格包含每個索引標籤上的相同資訊。</span><span class="sxs-lookup"><span data-stu-id="c46ce-258">The details table contains the same information on each tab.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="c46ce-259">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="c46ce-259">Threat protection status report</span></span>

<span data-ttu-id="c46ce-260">「 **威脅防護狀態** 報告」是一種單一的視圖，可透過 [Exchange ONLINE protection](exchange-online-protection-overview.md) (EOP) 和 Microsoft Defender for Office 365，彙集惡意內容和惡意電子郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c46ce-260">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="c46ce-261">如需詳細資訊，請參閱 [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="c46ce-261">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="c46ce-262">URL 威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="c46ce-262">URL threat protection report</span></span>

<span data-ttu-id="c46ce-263">**Url 威脅防護報告** 可提供偵測到之威脅的摘要和趨勢視圖，以及在 URL 按一下上做為 [安全連結](atp-safe-links.md)的一部分所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="c46ce-263">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="c46ce-264">若已套用安全連結原則的使用者沒有選取 [不 **追蹤使用者點擊** ] 選項，則此報告將不會有按一下其資料的使用者。</span><span class="sxs-lookup"><span data-stu-id="c46ce-264">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="c46ce-265">若要查看報告，請開啟 [安全性 & 合規性中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **URL 保護報告**]。</span><span class="sxs-lookup"><span data-stu-id="c46ce-265">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="c46ce-266">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=URLProtectionActionReport> 。</span><span class="sxs-lookup"><span data-stu-id="c46ce-266">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![報表儀表板中的 URL 保護報告構件](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="c46ce-268">這是一項 *保護趨勢報告*，表示資料代表較大資料集的趨勢。</span><span class="sxs-lookup"><span data-stu-id="c46ce-268">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="c46ce-269">因此，在這種情況下，不會即時提供匯總視圖中的資料，但 [詳細資料] 表格視圖中的資料則是如此，您可能會看到這兩種視圖之間稍有差異。</span><span class="sxs-lookup"><span data-stu-id="c46ce-269">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="c46ce-270">URL 威脅防護報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="c46ce-270">Report view for the URL threat protection report</span></span>

<span data-ttu-id="c46ce-271">**URL 威脅防護** 報告有兩個匯總的視圖，每四個小時都會重新整理一次，以顯示過去90天的資料：</span><span class="sxs-lookup"><span data-stu-id="c46ce-271">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="c46ce-272">**URL 按一下保護動作**：顯示組織中的使用者按下 URL 按一下數目及按一下的結果：</span><span class="sxs-lookup"><span data-stu-id="c46ce-272">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="c46ce-273">**封鎖** (禁止使用者流覽至 URL) </span><span class="sxs-lookup"><span data-stu-id="c46ce-273">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="c46ce-274">**封鎖並按一下**</span><span class="sxs-lookup"><span data-stu-id="c46ce-274">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="c46ce-275">**在掃描期間按一下**</span><span class="sxs-lookup"><span data-stu-id="c46ce-275">**Clicked through during scan**</span></span>

  <span data-ttu-id="c46ce-276">按一下表示使用者已透過封鎖頁面按一下至惡意網站 (系統管理員可以停用 [安全連結) 原則] 中的 click。</span><span class="sxs-lookup"><span data-stu-id="c46ce-276">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="c46ce-277">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="c46ce-277">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="c46ce-278">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c46ce-278">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c46ce-279">可使用的 [保護動作]，加上 **允許 (使用者** 流覽至 URL) 的值。</span><span class="sxs-lookup"><span data-stu-id="c46ce-279">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![Url 威脅防護報告中的 URL 按一下保護動作視圖](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="c46ce-281">**依應用程式按一下 url**：會顯示支援安全連結之應用程式的 url 按一下數目：</span><span class="sxs-lookup"><span data-stu-id="c46ce-281">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="c46ce-282">**電子郵件用戶端**</span><span class="sxs-lookup"><span data-stu-id="c46ce-282">**Email client**</span></span>
  - <span data-ttu-id="c46ce-283">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="c46ce-283">**PowerPoint**</span></span>
  - <span data-ttu-id="c46ce-284">**Word**</span><span class="sxs-lookup"><span data-stu-id="c46ce-284">**Word**</span></span>
  - <span data-ttu-id="c46ce-285">**Excel**</span><span class="sxs-lookup"><span data-stu-id="c46ce-285">**Excel**</span></span>
  - <span data-ttu-id="c46ce-286">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="c46ce-286">**OneNote**</span></span>
  - <span data-ttu-id="c46ce-287">**Visio**</span><span class="sxs-lookup"><span data-stu-id="c46ce-287">**Visio**</span></span>
  - <span data-ttu-id="c46ce-288">**Teams**</span><span class="sxs-lookup"><span data-stu-id="c46ce-288">**Teams**</span></span>
  - <span data-ttu-id="c46ce-289">**其他**</span><span class="sxs-lookup"><span data-stu-id="c46ce-289">**Other**</span></span>

  <span data-ttu-id="c46ce-290">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="c46ce-290">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="c46ce-291">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c46ce-291">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c46ce-292">可用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c46ce-292">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="c46ce-293">URL 威脅防護報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="c46ce-293">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="c46ce-294">如果您按一下 [ **查看詳細資料] 表格**，則報告會提供最近7天內組織內所有按一下動作的近乎即時視圖，其詳細資料如下：</span><span class="sxs-lookup"><span data-stu-id="c46ce-294">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="c46ce-295">**按一下 [時間]**</span><span class="sxs-lookup"><span data-stu-id="c46ce-295">**Click time**</span></span>
- <span data-ttu-id="c46ce-296">**使用者**</span><span class="sxs-lookup"><span data-stu-id="c46ce-296">**User**</span></span>
- <span data-ttu-id="c46ce-297">**URL**</span><span class="sxs-lookup"><span data-stu-id="c46ce-297">**URL**</span></span>
- <span data-ttu-id="c46ce-298">**動作**</span><span class="sxs-lookup"><span data-stu-id="c46ce-298">**Action**</span></span>
- <span data-ttu-id="c46ce-299">**App**</span><span class="sxs-lookup"><span data-stu-id="c46ce-299">**App**</span></span>

<span data-ttu-id="c46ce-300">如果您按一下 [詳細資料] 表格視圖中的 [**篩選器**]，可以篩選與報表檢視中相同的準則，**以及以逗號分隔的\*\*\*\*網域** 或收件者。</span><span class="sxs-lookup"><span data-stu-id="c46ce-300">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

> [!NOTE]
> <span data-ttu-id="c46ce-301">**網域** 篩選器是指報告結果中所列的 URL 網域。</span><span class="sxs-lookup"><span data-stu-id="c46ce-301">The **Domains** filter refers to the URL domain listed in the report results.</span></span> 

<span data-ttu-id="c46ce-302">若要回到 [報表] 視圖，請按一下 [ **view report**]。</span><span class="sxs-lookup"><span data-stu-id="c46ce-302">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="c46ce-303">要查看的其他報告</span><span class="sxs-lookup"><span data-stu-id="c46ce-303">Additional reports to view</span></span>

<span data-ttu-id="c46ce-304">除了本文所述的報告之外，還有其他幾個報告可供使用，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="c46ce-304">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="c46ce-305">報告</span><span class="sxs-lookup"><span data-stu-id="c46ce-305">Report</span></span>|<span data-ttu-id="c46ce-306">主題</span><span class="sxs-lookup"><span data-stu-id="c46ce-306">Topic</span></span>|
|---|---|
|<span data-ttu-id="c46ce-307">**Explorer** (microsoft Defender for Office 365 plan 2) 或 **即時** 偵測， (Microsoft Defender for office 365 plan 1) </span><span class="sxs-lookup"><span data-stu-id="c46ce-307">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="c46ce-308">威脅總管 (及即時偵測)</span><span class="sxs-lookup"><span data-stu-id="c46ce-308">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="c46ce-309">**電子郵件安全性報告**，例如主要寄件者和收件者報告、冒名郵件報告和垃圾郵件偵測報告。</span><span class="sxs-lookup"><span data-stu-id="c46ce-309">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="c46ce-310">檢視安全性與合規性中心內的電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="c46ce-310">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="c46ce-311">**郵件流程報告**，例如轉寄報告、郵件流程狀態報表，以及主要寄件者和收件者報告。</span><span class="sxs-lookup"><span data-stu-id="c46ce-311">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="c46ce-312">在安全性 & 規範中心內，查看郵件流程報告</span><span class="sxs-lookup"><span data-stu-id="c46ce-312">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="c46ce-313">**安全連結的 URL 追蹤** (僅 PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="c46ce-313">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="c46ce-314">此 Cmdlet 的輸出會顯示過去7天中安全連結動作的結果。</span><span class="sxs-lookup"><span data-stu-id="c46ce-314">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="c46ce-315">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="c46ce-315">Get-UrlTrace</span></span>](/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="c46ce-316">**EOP 和 Microsoft Defender For Office 365 (的郵件流量結果，** 只 PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="c46ce-316">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="c46ce-317">此 Cmdlet 的輸出包含網域、日期、事件種類、方向、動作和郵件數目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c46ce-317">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="c46ce-318">MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="c46ce-318">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="c46ce-319">**EOP 和 Defender For Office 365 偵測的郵件詳細資料包告** (僅 PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="c46ce-319">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="c46ce-320">此 Cmdlet 的輸出包含有關電子郵件或檔案中惡意檔案或 URLs、網路釣魚企圖、模仿及其他潛在威脅的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c46ce-320">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="c46ce-321">MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="c46ce-321">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="c46ce-322">查看 Office 365 的 Defender 時，需要哪些許可權？</span><span class="sxs-lookup"><span data-stu-id="c46ce-322">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="c46ce-323">為了查看和使用本文所述的報表，您必須是安全性 & 合規性中心之一的下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="c46ce-323">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="c46ce-324">**組織管理**</span><span class="sxs-lookup"><span data-stu-id="c46ce-324">**Organization Management**</span></span>
- <span data-ttu-id="c46ce-325">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="c46ce-325">**Security Administrator**</span></span>
- <span data-ttu-id="c46ce-326">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="c46ce-326">**Security Reader**</span></span>
- <span data-ttu-id="c46ce-327">**全域讀取者**</span><span class="sxs-lookup"><span data-stu-id="c46ce-327">**Global Reader**</span></span>

<span data-ttu-id="c46ce-328">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="c46ce-328">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="c46ce-329">**附注**：將使用者新增至 microsoft 365 系統管理中心的對應 Azure Active Directory 角色，可讓使用者具備安全性 & 合規性中心的許可權 _，以及_ Microsoft 365 中其他功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="c46ce-329">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c46ce-330">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="c46ce-330">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="c46ce-331">如果報告未顯示資料，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="c46ce-331">What if the reports aren't showing data?</span></span>

<span data-ttu-id="c46ce-332">如果您未看到您的 Office 365 報告中的資料，請仔細檢查您的原則設定是否正確。</span><span class="sxs-lookup"><span data-stu-id="c46ce-332">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="c46ce-333">您的組織必須已定義 [安全連結原則](set-up-atp-safe-links-policies.md) 及 [安全附件原則](set-up-atp-safe-attachments-policies.md) ，Office 365 防護功能才能就地使用。</span><span class="sxs-lookup"><span data-stu-id="c46ce-333">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="c46ce-334">另請參閱 [反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="c46ce-334">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c46ce-335">相關主題</span><span class="sxs-lookup"><span data-stu-id="c46ce-335">Related topics</span></span>

[<span data-ttu-id="c46ce-336">安全性與合規性中心內的智慧型報表和深入解析</span><span class="sxs-lookup"><span data-stu-id="c46ce-336">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="c46ce-337"> (Azure Active Directory 的角色許可權</span><span class="sxs-lookup"><span data-stu-id="c46ce-337">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)