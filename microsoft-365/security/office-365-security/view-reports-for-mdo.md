---
title: 在報表儀表板中查看 Office 365 報表的 Defender
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
description: 在 Microsoft 365 Defender 入口網站中尋找及使用 Microsoft Defender for Office 365 的報表。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5c45f58ee83de11712b198c85a8e423314289bf
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930206"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="ad87d-103">在 Microsoft 365 Defender 入口網站的報表儀表板中查看 Office 365 報表的 Defender</span><span class="sxs-lookup"><span data-stu-id="ad87d-103">View Defender for Office 365 reports in the Reports dashboard in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ad87d-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="ad87d-104">**Applies to**</span></span>
- [<span data-ttu-id="ad87d-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="ad87d-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ad87d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad87d-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ad87d-107">適用于 Office 365 組織的 Microsoft Defender (例如，Microsoft 365 E5 訂閱或 microsoft defender for Office 365 plan 1 或 microsoft defender for Office 365 plan 2 附加元件) 包含各種安全性相關的報表。</span><span class="sxs-lookup"><span data-stu-id="ad87d-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="ad87d-108">如果您有 [必要的許可權](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)，可以前往 **報告** \> **電子郵件** 共同作業的電子郵件共同作業 \> **報告**，以在 Microsoft 365 Defender 入口網站中查看這些報告。</span><span class="sxs-lookup"><span data-stu-id="ad87d-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email collaboration** \> **Email collaboration reports**.</span></span> <span data-ttu-id="ad87d-109">若要直接移至 [報告] 儀表板，請開啟] <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="ad87d-109">To go directly to the Reports dashboard, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Microsoft 365 Defender 入口網站中的報表儀表板](../../media/user-reported-messages.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="ad87d-111">適用於 Office 365 的 Defender 檔案類型報告</span><span class="sxs-lookup"><span data-stu-id="ad87d-111">Defender for Office 365 file types report</span></span>

<span data-ttu-id="ad87d-112">**Office 365 檔案類型的 Defender 報告** 報告會向您顯示以 [安全附件](safe-attachments.md)方式偵測為惡意的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="ad87d-112">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](safe-attachments.md).</span></span>

 <span data-ttu-id="ad87d-113">報表的匯總視圖允許90天的篩選，而詳細資料檢視只允許10天的篩選。</span><span class="sxs-lookup"><span data-stu-id="ad87d-113">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="ad87d-114">若要查看報告，請開啟 [Microsoft 365 的 Defender 入口網站](https://security.microsoft.com)，移至 [**報告**] \> **儀表板**，然後選取 [ **Office 365 檔案類型的 Defender**]。</span><span class="sxs-lookup"><span data-stu-id="ad87d-114">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="ad87d-115">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=ATPFileReport> 。</span><span class="sxs-lookup"><span data-stu-id="ad87d-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![報表儀表板中 Office 365 檔案類型構件的 Defender](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="ad87d-117">您也可以在[Office 365 郵件處理報告的 Defender](#defender-for-office-365-message-disposition-report)中使用此報告中的資訊。</span><span class="sxs-lookup"><span data-stu-id="ad87d-117">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="ad87d-118">Office 365 檔案類型的 Defender 報表檢視報告</span><span class="sxs-lookup"><span data-stu-id="ad87d-118">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="ad87d-119">您可使用下列檢視：</span><span class="sxs-lookup"><span data-stu-id="ad87d-119">The following views are available:</span></span>

- <span data-ttu-id="ad87d-120">**資料查看依據：** 檔案：此圖表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="ad87d-120">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="ad87d-121">**惡意 Excel 附件**</span><span class="sxs-lookup"><span data-stu-id="ad87d-121">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="ad87d-122">**惡意的 Flash 附件**</span><span class="sxs-lookup"><span data-stu-id="ad87d-122">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="ad87d-123">**惡意的 PDF 附件**</span><span class="sxs-lookup"><span data-stu-id="ad87d-123">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="ad87d-124">**惡意 PowerPoint 附件**</span><span class="sxs-lookup"><span data-stu-id="ad87d-124">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="ad87d-125">**惡意 URLs**</span><span class="sxs-lookup"><span data-stu-id="ad87d-125">**Malicious URLs**</span></span>
  - <span data-ttu-id="ad87d-126">**惡意的 Word 附件**</span><span class="sxs-lookup"><span data-stu-id="ad87d-126">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="ad87d-127">**惡意可執行附件**</span><span class="sxs-lookup"><span data-stu-id="ad87d-127">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="ad87d-128">**別人**</span><span class="sxs-lookup"><span data-stu-id="ad87d-128">**Others**</span></span>

  <span data-ttu-id="ad87d-129">當您將滑鼠停留在特定日期 (資料點) 時，您可以看到 EOP 中 [安全附件](safe-attachments.md) 和 [反惡意程式碼保護](anti-malware-protection.md)偵測到的惡意檔案類型細目。</span><span class="sxs-lookup"><span data-stu-id="ad87d-129">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Office 365 檔案類型的 Defender 中的檔案查看報告](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="ad87d-131">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="ad87d-131">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ad87d-132">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="ad87d-132">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ad87d-133">圖表中顯示的相同檔案類型值。</span><span class="sxs-lookup"><span data-stu-id="ad87d-133">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="ad87d-134">**資料查看方式：訊息**：此圖表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="ad87d-134">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="ad87d-135">**封鎖存取**</span><span class="sxs-lookup"><span data-stu-id="ad87d-135">**Block access**</span></span>
  - <span data-ttu-id="ad87d-136">**取代郵件**</span><span class="sxs-lookup"><span data-stu-id="ad87d-136">**Messages replaced**</span></span>
  - <span data-ttu-id="ad87d-137">**監控的郵件**</span><span class="sxs-lookup"><span data-stu-id="ad87d-137">**Messages monitored**</span></span>
  - <span data-ttu-id="ad87d-138">以 **動態電子郵件傳遞取代**：如需詳細資訊，請參閱 [在安全附件原則中傳遞](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)。</span><span class="sxs-lookup"><span data-stu-id="ad87d-138">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Office 365 檔案類型的 Defender 中的郵件視圖報告](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="ad87d-140">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="ad87d-140">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ad87d-141">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="ad87d-141">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ad87d-142">圖表中可用的相同郵件處置值，以及已傳遞的其他 **郵件** 值。</span><span class="sxs-lookup"><span data-stu-id="ad87d-142">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="ad87d-143">Office 365 檔案類型的 Defender 的詳細資料表格視圖報告</span><span class="sxs-lookup"><span data-stu-id="ad87d-143">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="ad87d-144">如果您按一下 [ **查看詳細資料] 表格**，此報告可提供最近10天內所有按一下動作的近乎即時視圖。</span><span class="sxs-lookup"><span data-stu-id="ad87d-144">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="ad87d-145">顯示的資訊取決於您所看到的圖表：</span><span class="sxs-lookup"><span data-stu-id="ad87d-145">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="ad87d-146">**資料查看依據：** 檔案：</span><span class="sxs-lookup"><span data-stu-id="ad87d-146">**View data by: File**:</span></span>

  - <span data-ttu-id="ad87d-147">**Date**</span><span class="sxs-lookup"><span data-stu-id="ad87d-147">**Date**</span></span>
  - <span data-ttu-id="ad87d-148">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="ad87d-148">**Recipient address**</span></span>
  - <span data-ttu-id="ad87d-149">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="ad87d-149">**Sender address**</span></span>
  - <span data-ttu-id="ad87d-150">**郵件識別碼**：郵件頭的 **Message-ID** 標頭欄位中可用，且應該是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ad87d-150">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="ad87d-151">範例值 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (記下角括弧) 。</span><span class="sxs-lookup"><span data-stu-id="ad87d-151">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="ad87d-152">**檔案**</span><span class="sxs-lookup"><span data-stu-id="ad87d-152">**File**</span></span>

  <span data-ttu-id="ad87d-153">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="ad87d-153">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ad87d-154">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="ad87d-154">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ad87d-155">圖表中顯示的相同檔案類型值。</span><span class="sxs-lookup"><span data-stu-id="ad87d-155">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="ad87d-156">**資料查看依據：訊息**：</span><span class="sxs-lookup"><span data-stu-id="ad87d-156">**View data by: Message**:</span></span>

  - <span data-ttu-id="ad87d-157">**Date**</span><span class="sxs-lookup"><span data-stu-id="ad87d-157">**Date**</span></span>
  - <span data-ttu-id="ad87d-158">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="ad87d-158">**Recipient address**</span></span>
  - <span data-ttu-id="ad87d-159">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="ad87d-159">**Sender address**</span></span>
  - <span data-ttu-id="ad87d-160">**郵件識別碼**</span><span class="sxs-lookup"><span data-stu-id="ad87d-160">**Message ID**</span></span>
  - <span data-ttu-id="ad87d-161">**檔案**</span><span class="sxs-lookup"><span data-stu-id="ad87d-161">**File**</span></span>
  - <span data-ttu-id="ad87d-162">**主旨**</span><span class="sxs-lookup"><span data-stu-id="ad87d-162">**Subject**</span></span>

  <span data-ttu-id="ad87d-163">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="ad87d-163">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="ad87d-164">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="ad87d-164">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ad87d-165">圖表中可用的相同郵件處置值，以及已傳遞的其他 **郵件** 值。</span><span class="sxs-lookup"><span data-stu-id="ad87d-165">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="ad87d-166">若要回到 [報表] 視圖，請按一下 [ **view report**]。</span><span class="sxs-lookup"><span data-stu-id="ad87d-166">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="ad87d-167">適用於 Office 365 的 Defender 郵件處置報告</span><span class="sxs-lookup"><span data-stu-id="ad87d-167">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="ad87d-168">**ATP 郵件** 處理報告會顯示偵測到有惡意內容的電子郵件所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="ad87d-168">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="ad87d-169">若要查看報告，請開啟 [Microsoft 365 Defender 入口網站](https://security.microsoft.com)，然後移至 [**報告** \> **電子郵件 &** 共同作業 \> **電子郵件 &** 共同作業報告]，然後選取 [ **Office 365 郵件處理的 Defender**]。</span><span class="sxs-lookup"><span data-stu-id="ad87d-169">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="ad87d-170">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=ATPMessageReport> 。</span><span class="sxs-lookup"><span data-stu-id="ad87d-170">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![報表儀表板中 Office 365 郵件處置小工具的 Defender](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="ad87d-172">您也可以在[Office 365 檔案類型報告的 Defender](#defender-for-office-365-file-types-report)中使用此報告中的資訊。</span><span class="sxs-lookup"><span data-stu-id="ad87d-172">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="ad87d-173">Office 365 郵件處理報告的 Defender 報表檢視</span><span class="sxs-lookup"><span data-stu-id="ad87d-173">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="ad87d-174">您可使用下列檢視：</span><span class="sxs-lookup"><span data-stu-id="ad87d-174">The following views are available:</span></span>

- <span data-ttu-id="ad87d-175">**資料查看方式：訊息**：此圖表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="ad87d-175">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="ad87d-176">**封鎖存取**</span><span class="sxs-lookup"><span data-stu-id="ad87d-176">**Block access**</span></span>
  - <span data-ttu-id="ad87d-177">**取代郵件**</span><span class="sxs-lookup"><span data-stu-id="ad87d-177">**Messages replaced**</span></span>
  - <span data-ttu-id="ad87d-178">**監控的郵件**</span><span class="sxs-lookup"><span data-stu-id="ad87d-178">**Messages monitored**</span></span>
  - <span data-ttu-id="ad87d-179">以 **動態電子郵件傳遞取代**：如需詳細資訊，請參閱 [在安全附件原則中傳遞](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)。</span><span class="sxs-lookup"><span data-stu-id="ad87d-179">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Office 365 檔案類型的 Defender 中的郵件視圖報告](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="ad87d-181">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="ad87d-181">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ad87d-182">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="ad87d-182">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ad87d-183">圖表中可用的相同郵件處置值，以及已傳遞的其他 **郵件** 值。</span><span class="sxs-lookup"><span data-stu-id="ad87d-183">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="ad87d-184">**資料查看依據：** 檔案：此圖表包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="ad87d-184">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="ad87d-185">**惡意 Excel 附件**</span><span class="sxs-lookup"><span data-stu-id="ad87d-185">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="ad87d-186">**惡意的 Flash 附件**</span><span class="sxs-lookup"><span data-stu-id="ad87d-186">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="ad87d-187">**惡意的 PDF 附件**</span><span class="sxs-lookup"><span data-stu-id="ad87d-187">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="ad87d-188">**惡意 PowerPoint 附件**</span><span class="sxs-lookup"><span data-stu-id="ad87d-188">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="ad87d-189">**惡意 URLs**</span><span class="sxs-lookup"><span data-stu-id="ad87d-189">**Malicious URLs**</span></span>
  - <span data-ttu-id="ad87d-190">**惡意的 Word 附件**</span><span class="sxs-lookup"><span data-stu-id="ad87d-190">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="ad87d-191">**惡意可執行附件**</span><span class="sxs-lookup"><span data-stu-id="ad87d-191">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="ad87d-192">**別人**</span><span class="sxs-lookup"><span data-stu-id="ad87d-192">**Others**</span></span>

  <span data-ttu-id="ad87d-193">當您將滑鼠停留在特定日期 (資料點) 時，您可以看到 EOP 中 [安全附件](safe-attachments.md) 和 [反惡意程式碼保護](anti-malware-protection.md)偵測到的惡意檔案類型細目。</span><span class="sxs-lookup"><span data-stu-id="ad87d-193">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Office 365 檔案類型的 Defender 中的檔案查看報告](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="ad87d-195">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="ad87d-195">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ad87d-196">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="ad87d-196">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ad87d-197">圖表中顯示的相同檔案類型值。</span><span class="sxs-lookup"><span data-stu-id="ad87d-197">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="ad87d-198">Office 365 郵件處理報告的 Defender 的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="ad87d-198">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="ad87d-199">如果您按一下 [ **查看詳細資料] 表格**，此報告可提供最近10天內所有按一下動作的近乎即時視圖。</span><span class="sxs-lookup"><span data-stu-id="ad87d-199">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="ad87d-200">顯示的資訊取決於您所看到的圖表：</span><span class="sxs-lookup"><span data-stu-id="ad87d-200">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="ad87d-201">**資料查看依據：訊息**：</span><span class="sxs-lookup"><span data-stu-id="ad87d-201">**View data by: Message**:</span></span>

  - <span data-ttu-id="ad87d-202">**Date**</span><span class="sxs-lookup"><span data-stu-id="ad87d-202">**Date**</span></span>
  - <span data-ttu-id="ad87d-203">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="ad87d-203">**Recipient address**</span></span>
  - <span data-ttu-id="ad87d-204">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="ad87d-204">**Sender address**</span></span>
  - <span data-ttu-id="ad87d-205">**郵件識別碼**</span><span class="sxs-lookup"><span data-stu-id="ad87d-205">**Message ID**</span></span>
  - <span data-ttu-id="ad87d-206">**檔案**</span><span class="sxs-lookup"><span data-stu-id="ad87d-206">**File**</span></span>
  - <span data-ttu-id="ad87d-207">**主旨**</span><span class="sxs-lookup"><span data-stu-id="ad87d-207">**Subject**</span></span>

  <span data-ttu-id="ad87d-208">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="ad87d-208">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="ad87d-209">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="ad87d-209">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ad87d-210">圖表中可用的相同郵件處置值，以及已傳遞的其他 **郵件** 值。</span><span class="sxs-lookup"><span data-stu-id="ad87d-210">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="ad87d-211">**資料查看依據：** 檔案：</span><span class="sxs-lookup"><span data-stu-id="ad87d-211">**View data by: File**:</span></span>

  - <span data-ttu-id="ad87d-212">**Date**</span><span class="sxs-lookup"><span data-stu-id="ad87d-212">**Date**</span></span>
  - <span data-ttu-id="ad87d-213">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="ad87d-213">**Recipient address**</span></span>
  - <span data-ttu-id="ad87d-214">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="ad87d-214">**Sender address**</span></span>
  - <span data-ttu-id="ad87d-215">**郵件識別碼**</span><span class="sxs-lookup"><span data-stu-id="ad87d-215">**Message ID**</span></span>
  - <span data-ttu-id="ad87d-216">**檔案**</span><span class="sxs-lookup"><span data-stu-id="ad87d-216">**File**</span></span>

  <span data-ttu-id="ad87d-217">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="ad87d-217">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ad87d-218">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="ad87d-218">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ad87d-219">圖表中顯示的相同檔案類型值。</span><span class="sxs-lookup"><span data-stu-id="ad87d-219">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="ad87d-220">若要回到 [報表] 視圖，請按一下 [ **view report**]。</span><span class="sxs-lookup"><span data-stu-id="ad87d-220">To get back to the reports view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="ad87d-221">郵件延遲報告</span><span class="sxs-lookup"><span data-stu-id="ad87d-221">Mail latency report</span></span>

<span data-ttu-id="ad87d-222">**郵件延遲報告** 會向您顯示組織內的郵件傳遞和引爆延遲的匯總視圖。</span><span class="sxs-lookup"><span data-stu-id="ad87d-222">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="ad87d-223">服務中的郵件傳遞時間受到多種因素的影響，而且絕對傳遞時間（秒）通常不是成功或問題的明確指示。</span><span class="sxs-lookup"><span data-stu-id="ad87d-223">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="ad87d-224">在一天內的傳遞時間可能會被視為另一天的平均傳遞時間，或反過來。</span><span class="sxs-lookup"><span data-stu-id="ad87d-224">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="ad87d-225">**郵件延遲報告** 會嘗試根據觀察到的其他郵件傳遞時間的統計資料，以限定郵件傳遞：</span><span class="sxs-lookup"><span data-stu-id="ad87d-225">The **Mail latency report** tries to qualify message delivery based on statistical data about the observed delivery times of other messages:</span></span>

- <span data-ttu-id="ad87d-226">第 **50 個百分點**：這是郵件傳遞時間的中間部分。</span><span class="sxs-lookup"><span data-stu-id="ad87d-226">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="ad87d-227">您可以將此值視為平均傳遞時間。</span><span class="sxs-lookup"><span data-stu-id="ad87d-227">You can consider this value as an average delivery time.</span></span>
- <span data-ttu-id="ad87d-228">**90%**：這表示郵件傳遞的高延遲。</span><span class="sxs-lookup"><span data-stu-id="ad87d-228">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="ad87d-229">只有10% 的郵件花費的時間超過此值才能傳遞。</span><span class="sxs-lookup"><span data-stu-id="ad87d-229">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="ad87d-230">**99th 百分點**：這表示郵件傳遞的最高延遲。</span><span class="sxs-lookup"><span data-stu-id="ad87d-230">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="ad87d-231">不包括用戶端和網路延遲。</span><span class="sxs-lookup"><span data-stu-id="ad87d-231">Client side and network latency are not included.</span></span>

<span data-ttu-id="ad87d-232">若要查看報告，請開啟 [Microsoft 365 Defender 入口網站](https://security.microsoft.com)，移至 [**報告** \> **電子郵件 &** 共同作業 \> **電子郵件 & 共同報告**]，然後按一下 [**郵件延遲報告**] 底下的 [**詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="ad87d-232">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Mail latency report**.</span></span> <span data-ttu-id="ad87d-233">若要直接前往報表，請開啟 <https://security.microsoft.com/mailLatencyReport> 。</span><span class="sxs-lookup"><span data-stu-id="ad87d-233">To go directly to the report, open <https://security.microsoft.com/mailLatencyReport>.</span></span>

![報表儀表板中的郵件延遲報告構件](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a><span data-ttu-id="ad87d-235">郵件延遲報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="ad87d-235">Report view for the Mail latency report</span></span>

<span data-ttu-id="ad87d-236">當您開啟報表時，預設會選取 [ **50 百分位數** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ad87d-236">When you open the report, the **50th percentiles** tab is selected by default.</span></span>

<span data-ttu-id="ad87d-237">此視圖預設會包含以下列篩選設定的圖表：</span><span class="sxs-lookup"><span data-stu-id="ad87d-237">By default, this view contains a chart that's configured with the following filters:</span></span>

- <span data-ttu-id="ad87d-238">**日期**：過去7天</span><span class="sxs-lookup"><span data-stu-id="ad87d-238">**Date**: The last 7 days</span></span>
- <span data-ttu-id="ad87d-239">**郵件視圖**：</span><span class="sxs-lookup"><span data-stu-id="ad87d-239">**Message View**:</span></span>
  - <span data-ttu-id="ad87d-240">引爆郵件</span><span class="sxs-lookup"><span data-stu-id="ad87d-240">Detonated messages</span></span>

<span data-ttu-id="ad87d-241">此圖顯示組織成下列類別的郵件：</span><span class="sxs-lookup"><span data-stu-id="ad87d-241">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="ad87d-242">**郵件傳遞延遲**</span><span class="sxs-lookup"><span data-stu-id="ad87d-242">**Mail delivery latency**</span></span>
- <span data-ttu-id="ad87d-243">**引爆延遲**</span><span class="sxs-lookup"><span data-stu-id="ad87d-243">**Detonation latency**</span></span>

<span data-ttu-id="ad87d-244">當您將游標移到圖表中的某個類別時，您可以查看每個類別中的延遲明細。</span><span class="sxs-lookup"><span data-stu-id="ad87d-244">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![郵件延遲報告](../../media/mail-latency-report.png)

<span data-ttu-id="ad87d-246">如果您按一下報表檢視中的 [ **篩選** ]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="ad87d-246">If you click **Filter** in the report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="ad87d-247">所有郵件</span><span class="sxs-lookup"><span data-stu-id="ad87d-247">All messages</span></span>
- <span data-ttu-id="ad87d-248">包含附件或 URLs 的郵件</span><span class="sxs-lookup"><span data-stu-id="ad87d-248">Messages that contain attachments or URLs</span></span>

<span data-ttu-id="ad87d-249">如果您按一下 [ **90 百分位數** ] 索引標籤或 [ **99th 百分位數** ] 索引標籤，則會使用第 **50 個百分位數** 視圖中的相同預設篩選器。</span><span class="sxs-lookup"><span data-stu-id="ad87d-249">If you click the **90th percentiles** tab or the **99th percentiles** tab, the same default filters from the **50th percentiles** view are used.</span></span>

### <a name="details-table-view-for-the-mail-latency-report"></a><span data-ttu-id="ad87d-250">郵件延遲報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="ad87d-250">Details table view for the Mail latency report</span></span>

<span data-ttu-id="ad87d-251">[詳細資料] 表格視圖會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="ad87d-251">The following information is shown in the details table view:</span></span>

- <span data-ttu-id="ad87d-252">**Date**</span><span class="sxs-lookup"><span data-stu-id="ad87d-252">**Date**</span></span>
- <span data-ttu-id="ad87d-253">**百分位數**</span><span class="sxs-lookup"><span data-stu-id="ad87d-253">**Percentiles**</span></span>
- <span data-ttu-id="ad87d-254">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="ad87d-254">**Message count**</span></span>
- <span data-ttu-id="ad87d-255">**整體延遲**</span><span class="sxs-lookup"><span data-stu-id="ad87d-255">**Overall latency**</span></span>

![郵件延遲報告詳細資料](../../media/mail-latency-report-details.png)

<span data-ttu-id="ad87d-257">上述顯示于11月14日，所有傳遞和引爆的郵件所經歷的平均延遲為 **108.033** 秒。</span><span class="sxs-lookup"><span data-stu-id="ad87d-257">The above shows that on November 14 the average latency experienced for all messages delivered and detonated was **108.033** seconds.</span></span>

<span data-ttu-id="ad87d-258">[詳細資料] 表格包含每個索引標籤上的相同資訊。</span><span class="sxs-lookup"><span data-stu-id="ad87d-258">The details table contains the same information on each tab.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="ad87d-259">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="ad87d-259">Threat protection status report</span></span>

<span data-ttu-id="ad87d-260">「**威脅防護狀態** 報告」是單一的視圖，可透過 [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) 和 Microsoft Defender for Office 365，彙集惡意內容和惡意電子郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ad87d-260">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ad87d-261">如需詳細資訊，請參閱 [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="ad87d-261">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="ad87d-262">URL 威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="ad87d-262">URL threat protection report</span></span>

<span data-ttu-id="ad87d-263">**Url 威脅防護報告** 可提供偵測到之威脅的摘要和趨勢視圖，以及在 URL 按一下上做為 [安全連結](safe-links.md)的一部分所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="ad87d-263">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](safe-links.md).</span></span> <span data-ttu-id="ad87d-264">若已套用安全連結原則的使用者沒有選取 [不 **追蹤使用者點擊** ] 選項，則此報告將不會有按一下其資料的使用者。</span><span class="sxs-lookup"><span data-stu-id="ad87d-264">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="ad87d-265">若要查看報告，請開啟 [Microsoft 365 Defender 入口網站](https://security.microsoft.com)，移至 [**報告** \> **電子郵件 &** 共同作業 \> **電子郵件 & 共同報告**]，然後按一下 [ **URL 保護報告**] 底下的 [**查看詳細資料**]</span><span class="sxs-lookup"><span data-stu-id="ad87d-265">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **URL protection report**.</span></span> <span data-ttu-id="ad87d-266">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/URLProtectionActionReport> 。</span><span class="sxs-lookup"><span data-stu-id="ad87d-266">To go directly to the report, open <https://security.microsoft.com/reports/URLProtectionActionReport>.</span></span>

![報表儀表板中的 URL 保護報告構件](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="ad87d-268">這是一項 *保護趨勢報告*，表示資料代表較大資料集的趨勢。</span><span class="sxs-lookup"><span data-stu-id="ad87d-268">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="ad87d-269">因此，在這種情況下，不會即時提供匯總視圖中的資料，但 [詳細資料] 表格視圖中的資料則是如此，您可能會看到這兩種視圖之間稍有差異。</span><span class="sxs-lookup"><span data-stu-id="ad87d-269">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="ad87d-270">URL 威脅防護報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="ad87d-270">Report view for the URL threat protection report</span></span>

<span data-ttu-id="ad87d-271">**URL 威脅防護** 報告有兩個匯總的視圖，每四個小時都會重新整理一次，以顯示過去90天的資料：</span><span class="sxs-lookup"><span data-stu-id="ad87d-271">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="ad87d-272">**URL 按一下保護動作**：顯示組織中的使用者按下 URL 按一下數目及按一下的結果：</span><span class="sxs-lookup"><span data-stu-id="ad87d-272">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="ad87d-273">**封鎖** (禁止使用者流覽至 URL) </span><span class="sxs-lookup"><span data-stu-id="ad87d-273">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="ad87d-274">在使用者選擇繼續導覽 URL 的 (**封鎖和點擊**) </span><span class="sxs-lookup"><span data-stu-id="ad87d-274">**Blocked and clicked through** (the user has chosen to continue navigating to the URL)</span></span>
  - <span data-ttu-id="ad87d-275">在 **掃描期間按一下流覽** (使用者已在掃描完成之前按一下連結) </span><span class="sxs-lookup"><span data-stu-id="ad87d-275">**Clicked through during scan** (the user has clicked on the link before the scan was complete)</span></span>

  <span data-ttu-id="ad87d-276">按一下表示使用者已透過封鎖頁面按一下至惡意網站 (系統管理員可以停用 [安全連結) 原則] 中的 click。</span><span class="sxs-lookup"><span data-stu-id="ad87d-276">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="ad87d-277">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="ad87d-277">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ad87d-278">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="ad87d-278">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ad87d-279">可使用的 [保護動作]，加上 **允許 (使用者** 流覽至 URL) 的值。</span><span class="sxs-lookup"><span data-stu-id="ad87d-279">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![Url 威脅防護報告中的 URL 按一下保護動作視圖](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="ad87d-281">**依應用程式按一下 url**：會顯示支援安全連結之應用程式的 url 按一下數目：</span><span class="sxs-lookup"><span data-stu-id="ad87d-281">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="ad87d-282">**電子郵件用戶端**</span><span class="sxs-lookup"><span data-stu-id="ad87d-282">**Email client**</span></span>
  - <span data-ttu-id="ad87d-283">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="ad87d-283">**PowerPoint**</span></span>
  - <span data-ttu-id="ad87d-284">**Word**</span><span class="sxs-lookup"><span data-stu-id="ad87d-284">**Word**</span></span>
  - <span data-ttu-id="ad87d-285">**Excel**</span><span class="sxs-lookup"><span data-stu-id="ad87d-285">**Excel**</span></span>
  - <span data-ttu-id="ad87d-286">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="ad87d-286">**OneNote**</span></span>
  - <span data-ttu-id="ad87d-287">**Visio**</span><span class="sxs-lookup"><span data-stu-id="ad87d-287">**Visio**</span></span>
  - <span data-ttu-id="ad87d-288">**Teams**</span><span class="sxs-lookup"><span data-stu-id="ad87d-288">**Teams**</span></span>
  - <span data-ttu-id="ad87d-289">**其他**</span><span class="sxs-lookup"><span data-stu-id="ad87d-289">**Other**</span></span>

  <span data-ttu-id="ad87d-290">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="ad87d-290">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ad87d-291">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="ad87d-291">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ad87d-292">可用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="ad87d-292">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="ad87d-293">URL 威脅防護報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="ad87d-293">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="ad87d-294">如果您按一下 [ **查看詳細資料] 表格**，則報告會提供最近7天內組織內所有按一下動作的近乎即時視圖，其詳細資料如下：</span><span class="sxs-lookup"><span data-stu-id="ad87d-294">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="ad87d-295">**按一下 [時間]**</span><span class="sxs-lookup"><span data-stu-id="ad87d-295">**Click time**</span></span>
- <span data-ttu-id="ad87d-296">**使用者**</span><span class="sxs-lookup"><span data-stu-id="ad87d-296">**User**</span></span>
- <span data-ttu-id="ad87d-297">**URL**</span><span class="sxs-lookup"><span data-stu-id="ad87d-297">**URL**</span></span>
- <span data-ttu-id="ad87d-298">**Action**</span><span class="sxs-lookup"><span data-stu-id="ad87d-298">**Action**</span></span>
- <span data-ttu-id="ad87d-299">**應用程式**</span><span class="sxs-lookup"><span data-stu-id="ad87d-299">**App**</span></span>

<span data-ttu-id="ad87d-300">如果您按一下 [詳細資料] 表格視圖中的 [**篩選器**]，可以篩選與報表檢視中相同的準則，**以及以逗號分隔的\*\*\*\*網域** 或收件者。</span><span class="sxs-lookup"><span data-stu-id="ad87d-300">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

> [!NOTE]
> <span data-ttu-id="ad87d-301">**網域** 篩選器是指報告結果中所列的 URL 網域。</span><span class="sxs-lookup"><span data-stu-id="ad87d-301">The **Domains** filter refers to the URL domain listed in the report results.</span></span> 

<span data-ttu-id="ad87d-302">若要回到 [報表] 視圖，請按一下 [ **view report**]。</span><span class="sxs-lookup"><span data-stu-id="ad87d-302">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="ad87d-303">要查看的其他報告</span><span class="sxs-lookup"><span data-stu-id="ad87d-303">Additional reports to view</span></span>

<span data-ttu-id="ad87d-304">除了本文所述的報告之外，還有其他幾個報告可供使用，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="ad87d-304">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="ad87d-305">報告</span><span class="sxs-lookup"><span data-stu-id="ad87d-305">Report</span></span>|<span data-ttu-id="ad87d-306">主題</span><span class="sxs-lookup"><span data-stu-id="ad87d-306">Topic</span></span>|
|---|---|
|<span data-ttu-id="ad87d-307">**Explorer** (microsoft defender for Office 365 plan 2) 或 **即時** 偵測 (Microsoft defender for Office 365 Plan 1) </span><span class="sxs-lookup"><span data-stu-id="ad87d-307">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="ad87d-308">威脅總管 (及即時偵測)</span><span class="sxs-lookup"><span data-stu-id="ad87d-308">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="ad87d-309">**電子郵件安全性報告**，例如主要寄件者和收件者報告、冒名郵件報告和垃圾郵件偵測報告。</span><span class="sxs-lookup"><span data-stu-id="ad87d-309">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="ad87d-310">在 Microsoft 365 Defender 入口網站中查看電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="ad87d-310">View email security reports in the Microsoft 365 Defender portal</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="ad87d-311">**郵件流程報告**，例如轉寄報告、郵件流程狀態報表，以及主要寄件者和收件者報告。</span><span class="sxs-lookup"><span data-stu-id="ad87d-311">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="ad87d-312">在 Microsoft 365 Defender 入口網站中查看郵件流程報告</span><span class="sxs-lookup"><span data-stu-id="ad87d-312">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="ad87d-313">**安全連結的 URL 追蹤** (僅 PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="ad87d-313">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="ad87d-314">此 Cmdlet 的輸出會顯示過去7天中安全連結動作的結果。</span><span class="sxs-lookup"><span data-stu-id="ad87d-314">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="ad87d-315">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="ad87d-315">Get-UrlTrace</span></span>](/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="ad87d-316">僅 PowerShell) ， **EOP 和 Microsoft Defender for Office 365 (的郵件流量結果**。</span><span class="sxs-lookup"><span data-stu-id="ad87d-316">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="ad87d-317">此 Cmdlet 的輸出包含網域、日期、事件種類、方向、動作和郵件數目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ad87d-317">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="ad87d-318">MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="ad87d-318">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="ad87d-319">**EOP 和 Defender Office 365 偵測的郵件詳細資料包告** (僅 PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="ad87d-319">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="ad87d-320">此 Cmdlet 的輸出包含有關電子郵件或檔案中惡意檔案或 URLs、網路釣魚企圖、模仿及其他潛在威脅的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ad87d-320">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="ad87d-321">MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="ad87d-321">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="ad87d-322">流覽 Office 365 報表的 Defender 時，需要哪些許可權？</span><span class="sxs-lookup"><span data-stu-id="ad87d-322">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="ad87d-323">為了查看和使用本文所述的報表，您必須是 Microsoft 365 Defender 入口網站中下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="ad87d-323">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="ad87d-324">**組織管理**</span><span class="sxs-lookup"><span data-stu-id="ad87d-324">**Organization Management**</span></span>
- <span data-ttu-id="ad87d-325">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="ad87d-325">**Security Administrator**</span></span>
- <span data-ttu-id="ad87d-326">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="ad87d-326">**Security Reader**</span></span>
- <span data-ttu-id="ad87d-327">**全域讀取器**</span><span class="sxs-lookup"><span data-stu-id="ad87d-327">**Global Reader**</span></span>

<span data-ttu-id="ad87d-328">如需詳細資訊，請參閱[Microsoft 365 Defender 入口網站中的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ad87d-328">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="ad87d-329">**附注**：將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 Defender 入口網站中的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="ad87d-329">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ad87d-330">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="ad87d-330">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="ad87d-331">如果報告未顯示資料，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="ad87d-331">What if the reports aren't showing data?</span></span>

<span data-ttu-id="ad87d-332">如果您未在 Office 365 報告中看到您的 Defender 資料，請仔細檢查您的原則設定是否正確。</span><span class="sxs-lookup"><span data-stu-id="ad87d-332">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="ad87d-333">您的組織必須定義[安全連結原則](set-up-safe-links-policies.md)及[安全附件原則](set-up-safe-attachments-policies.md)，Office 365 防護功能才能進行。</span><span class="sxs-lookup"><span data-stu-id="ad87d-333">Your organization must have [Safe Links policies](set-up-safe-links-policies.md) and [Safe Attachments policies](set-up-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="ad87d-334">另請參閱 [反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="ad87d-334">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ad87d-335">相關主題</span><span class="sxs-lookup"><span data-stu-id="ad87d-335">Related topics</span></span>

[<span data-ttu-id="ad87d-336">Microsoft 365 Defender 入口網站中的智慧報告和洞察力</span><span class="sxs-lookup"><span data-stu-id="ad87d-336">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="ad87d-337">角色許可權 (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ad87d-337">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
