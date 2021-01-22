---
title: 威脅管和即時偵測
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 使用安全性合規性中心的 Explorer 和即時偵測來調查 &amp; 並有效回應威脅。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: caf795b421ac8e1e6785abff2fc49f0e49c391ca
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931707"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="7a90f-103">威脅管和即時偵測</span><span class="sxs-lookup"><span data-stu-id="7a90f-103">Threat Explorer and Real-time detections</span></span>

<span data-ttu-id="7a90f-104">如果貴組織擁有 [Office 365](office-365-atp.md)的 Microsoft Defender，而且您擁有必要許可權，就有權存取 Explorer 或即時偵測功能，這些前稱是 *即時報告*。 [](#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="7a90f-104">If your organization has [Microsoft Defender for Office 365](office-365-atp.md) and you have the [necessary permissions](#required-licenses-and-permissions), you have access to *Explorer* or *Real-time detections*, which were formerly *Real-time reports*.</span></span> <span data-ttu-id="7a90f-105"> (新功能。) [](#new-features-in-threat-explorer-and-real-time-detections)安全性&，請前往威脅管理，然後選取 Explorer 或 **即時偵測**。 </span><span class="sxs-lookup"><span data-stu-id="7a90f-105">([See what's new.](#new-features-in-threat-explorer-and-real-time-detections)) In the Security & Compliance Center, go to **Threat management**, and then select **Explorer** _or_ **Real-time detections**.</span></span>

|<span data-ttu-id="7a90f-106">使用 Microsoft Defender for Office 365 方案 2，您會看到：</span><span class="sxs-lookup"><span data-stu-id="7a90f-106">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="7a90f-107">使用適用于 Office 365 方案 1 的 Microsoft Defender，您會看到：</span><span class="sxs-lookup"><span data-stu-id="7a90f-107">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![威脅總管](../../media/threatmgmt-explorer.png)|![即時偵測](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="7a90f-110">Explorer 或即時偵測可協助您的安全性作業小組有效率地調查及回應威脅。</span><span class="sxs-lookup"><span data-stu-id="7a90f-110">Explorer or Real-time detections helps your security operations team investigate and respond to threats efficiently.</span></span> <span data-ttu-id="7a90f-111">報告類似下列影像：</span><span class="sxs-lookup"><span data-stu-id="7a90f-111">The report resembles the following image:</span></span>

![移至威脅管理 \> 總管](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="7a90f-113">您可以使用此報告：</span><span class="sxs-lookup"><span data-stu-id="7a90f-113">With this report, you can:</span></span>

- [<span data-ttu-id="7a90f-114">查看 Microsoft 365 安全性功能偵測到的惡意攻擊</span><span class="sxs-lookup"><span data-stu-id="7a90f-114">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- <span data-ttu-id="7a90f-115">[查看網路釣魚 URL 並按一下 [網路釣魚資料](#view-phishing-url-and-click-verdict-data)</span><span class="sxs-lookup"><span data-stu-id="7a90f-115">[View phishing URL and click verdict data](#view-phishing-url-and-click-verdict-data)</span></span>
- <span data-ttu-id="7a90f-116">[從適用于](#start-automated-investigation-and-response) Office 365 方案 2 的 Explorer (Defender 的一個) </span><span class="sxs-lookup"><span data-stu-id="7a90f-116">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (Defender for Office 365 Plan 2 only)</span></span>
- [<span data-ttu-id="7a90f-117">調查惡意電子郵件等</span><span class="sxs-lookup"><span data-stu-id="7a90f-117">Investigate malicious email, and more</span></span>](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-explorer-and-real-time-detections"></a><span data-ttu-id="7a90f-118">改善威脅管和即時偵測</span><span class="sxs-lookup"><span data-stu-id="7a90f-118">Improvements to Threat Explorer and Real-time detections</span></span>

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="7a90f-119">威脅管中的標記</span><span class="sxs-lookup"><span data-stu-id="7a90f-119">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="7a90f-120">使用者標記功能為預覽 *版*，不適用於所有人，且可能會有所變更。</span><span class="sxs-lookup"><span data-stu-id="7a90f-120">The user tags feature is in *Preview*, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="7a90f-121">有關發行排程的資訊，請參閱 Microsoft 365 藍圖。</span><span class="sxs-lookup"><span data-stu-id="7a90f-121">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="7a90f-122">使用者標記可識別 Microsoft Defender for Office 365 中的特定使用者群組。</span><span class="sxs-lookup"><span data-stu-id="7a90f-122">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="7a90f-123">有關標記的資訊，包括授權和組組，請參閱使用者 [標記](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="7a90f-123">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="7a90f-124">在威脅管中，您可以在下列體驗中查看使用者標記相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7a90f-124">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="7a90f-125">電子郵件格線視圖</span><span class="sxs-lookup"><span data-stu-id="7a90f-125">Email grid view</span></span>

<span data-ttu-id="7a90f-126">電子郵件 **網格** 線中的標記欄包含所有已適用于寄件者或收件者信箱的標記。</span><span class="sxs-lookup"><span data-stu-id="7a90f-126">The **Tags** column in the email grid contains all the tags that have been applied to the sender or recipient mailboxes.</span></span> <span data-ttu-id="7a90f-127">根據預設，優先顯示優先順序帳戶等系統標記。</span><span class="sxs-lookup"><span data-stu-id="7a90f-127">By default, system tags like priority accounts are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-128">![在電子郵件格線視圖中篩選標記](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-128">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="7a90f-129">篩選</span><span class="sxs-lookup"><span data-stu-id="7a90f-129">Filtering</span></span>

<span data-ttu-id="7a90f-130">您可以使用標記做為篩選。</span><span class="sxs-lookup"><span data-stu-id="7a90f-130">You can use tags as a filter.</span></span> <span data-ttu-id="7a90f-131">只搜尋優先順序帳戶或特定使用者標記案例。</span><span class="sxs-lookup"><span data-stu-id="7a90f-131">Hunt just across priority accounts or specific user tags scenarios.</span></span> <span data-ttu-id="7a90f-132">您也可以排除具有特定標記的結果。</span><span class="sxs-lookup"><span data-stu-id="7a90f-132">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="7a90f-133">將此功能與其他篩選結合以縮小您的調查範圍。</span><span class="sxs-lookup"><span data-stu-id="7a90f-133">Combine this functionality with other filters to narrow your scope of investigation.</span></span>

<span data-ttu-id="7a90f-134">[![篩選標記](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="7a90f-134">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-135">![未篩選標記](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-135">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="7a90f-136">電子郵件詳細資料飛出</span><span class="sxs-lookup"><span data-stu-id="7a90f-136">Email detail flyout</span></span>
<span data-ttu-id="7a90f-137">若要查看寄件者和收件者的個別標記，請選取要開啟郵件詳細資料飛出區的主題。</span><span class="sxs-lookup"><span data-stu-id="7a90f-137">To view the individual tags for sender and recipient, select the subject to open the message details flyout.</span></span> <span data-ttu-id="7a90f-138">如果寄件者 **和收** 件者有顯示電子郵件，則這些寄件者和收件者標記會分開顯示。</span><span class="sxs-lookup"><span data-stu-id="7a90f-138">On the **Summary** tab, the sender and recipient tags are shown separately, if they're present for an email.</span></span>
<span data-ttu-id="7a90f-139">寄件者和收件者個別標記的資訊也會延伸至匯出的 CSV 資料，您可以在兩個個別的欄看到這些詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7a90f-139">The information about individual tags for sender and recipient also extends to exported CSV data, where you can see these details in two separate columns.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-140">![電子郵件詳細資料標記](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-140">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="7a90f-141">URL 按一下飛出區也會顯示標記資訊。</span><span class="sxs-lookup"><span data-stu-id="7a90f-141">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="7a90f-142">若要進行查看，請前往網路釣魚或所有電子郵件的視圖，然後前往 **URL** 或 URL 的 **按一下** 按鈕。選取個別的 URL 飛出，以查看該 URL 的按一下相關詳細資料，包括與該按一下相關的標記。</span><span class="sxs-lookup"><span data-stu-id="7a90f-142">To view it, go to Phish or All Email view and then to the **URLs** or **URL Clicks** tab. Select an individual URL flyout to view additional details about clicks for that URL, including tags associated with that click.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-143">![URL 標記](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-143">![URL tags](../../media/tags-urls.png)</span></span>

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a><span data-ttu-id="7a90f-144">在近期新推出的威脅搜尋體驗 (改善) </span><span class="sxs-lookup"><span data-stu-id="7a90f-144">Improvements to the threat hunting experience (upcoming)</span></span>

### <a name="updated-threat-information-for-emails"></a><span data-ttu-id="7a90f-145">已更新電子郵件的威脅資訊</span><span class="sxs-lookup"><span data-stu-id="7a90f-145">Updated threat information for emails</span></span>

<span data-ttu-id="7a90f-146">我們著重于改善平臺和資料品質，提高電子郵件記錄的資料正確性與一致性。</span><span class="sxs-lookup"><span data-stu-id="7a90f-146">We've focused on platform and data-quality improvements to increase data accuracy and consistency for email records.</span></span> <span data-ttu-id="7a90f-147">改進包括將傳遞前和傳遞後的資訊合併成單一記錄，例如，在電子郵件上執行的動作是 ZAP 程式一部分。</span><span class="sxs-lookup"><span data-stu-id="7a90f-147">Improvements include consolidation of pre-delivery and post-delivery information, such as actions executed on an email as part of the ZAP process, into a single record.</span></span> <span data-ttu-id="7a90f-148">包含其他詳細資料，例如垃圾郵件垃圾郵件 (，例如哪些 URL 是惡意) ，以及最新的傳遞位置。</span><span class="sxs-lookup"><span data-stu-id="7a90f-148">Additional details like spam verdict, entity-level threats (for example, which URL was malicious), and latest delivery locations are also included.</span></span>

<span data-ttu-id="7a90f-149">這些更新之後，無論影響郵件的不同傳遞後事件，您都會看到每封郵件的單一專案。</span><span class="sxs-lookup"><span data-stu-id="7a90f-149">After these updates, you'll see a single entry for each message, regardless of the different post-delivery events that affect the message.</span></span> <span data-ttu-id="7a90f-150">動作可能包括 ZAP、手動修復 (，這表示系統管理員) 行動、動態傳遞等等。</span><span class="sxs-lookup"><span data-stu-id="7a90f-150">Actions can include ZAP, manual remediation (which means admin action), dynamic delivery, and so on.</span></span>

<span data-ttu-id="7a90f-151">除了顯示惡意攻擊和網路釣魚威脅，您看到與電子郵件相關聯的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="7a90f-151">In addition to showing malware and phishing threats, you see the spam verdict associated with an email.</span></span> <span data-ttu-id="7a90f-152">在電子郵件內，查看與電子郵件相關聯的所有威脅，以及對應的偵測技術。</span><span class="sxs-lookup"><span data-stu-id="7a90f-152">Within the email, see all the threats associated with the email along with the corresponding detection technologies.</span></span> <span data-ttu-id="7a90f-153">電子郵件可能擁有零、一或多個威脅。</span><span class="sxs-lookup"><span data-stu-id="7a90f-153">An email can have zero, one, or multiple threats.</span></span> <span data-ttu-id="7a90f-154">您將在電子郵件飛出區之詳細 **資料區** 段看到目前的威脅。</span><span class="sxs-lookup"><span data-stu-id="7a90f-154">You'll see the current threats in the **Details** section of the email flyout.</span></span> <span data-ttu-id="7a90f-155">針對惡意 (網路釣魚) 等多種威脅，偵測技術欄位會顯示威脅偵測地圖，這是識別威脅的偵測技術。</span><span class="sxs-lookup"><span data-stu-id="7a90f-155">For multiple threats (such as malware and phishing), the **Detection tech** field shows the threat-detection mapping, which is the detection technology that identified the threat.</span></span>

<span data-ttu-id="7a90f-156">這組偵測技術現在包含新的偵測方法，以及垃圾郵件偵測技術。</span><span class="sxs-lookup"><span data-stu-id="7a90f-156">The set of detection technologies now includes new detection methods, as well as spam-detection technologies.</span></span> <span data-ttu-id="7a90f-157">您可以使用同一組偵測技術，在不同的電子郵件視圖中篩選結果，例如惡意 (、網路釣魚、所有電子郵件) 。</span><span class="sxs-lookup"><span data-stu-id="7a90f-157">You can use the same set of detection technologies to filter the results across the different email views (Malware, Phish, All Email).</span></span>

> [!NOTE]
> <span data-ttu-id="7a90f-158">分析不一定與實體綁定。</span><span class="sxs-lookup"><span data-stu-id="7a90f-158">Verdict analysis might not necessarily be tied to entities.</span></span> <span data-ttu-id="7a90f-159">例如，電子郵件可能分類為網路釣魚或垃圾郵件，但沒有標記網路釣魚/垃圾郵件垃圾郵件的 URL。</span><span class="sxs-lookup"><span data-stu-id="7a90f-159">As an example, an email might be classified as phish or spam, but there are no URLs that are stamped with a phish/spam verdict.</span></span> <span data-ttu-id="7a90f-160">這是因為篩選也會先評估電子郵件的內容和其他詳細資料，然後再指派電子郵件的篩選準則。</span><span class="sxs-lookup"><span data-stu-id="7a90f-160">This is because the filters also evaluate content and other details for an email before assigning a verdict.</span></span>

#### <a name="threats-in-urls"></a><span data-ttu-id="7a90f-161">URL 中的威脅</span><span class="sxs-lookup"><span data-stu-id="7a90f-161">Threats in URLs</span></span>

<span data-ttu-id="7a90f-162">現在，您可以在電子郵件飛出視窗的飛出詳細資料標籤上看到 URL **的特定** 威脅。威脅可能是惡意 *攻擊*、 *網路釣魚*、 *垃圾郵件*，或 *無*.) </span><span class="sxs-lookup"><span data-stu-id="7a90f-162">You can now see the specific threat for a URL on the email flyout **Details** tab. The threat can be *malware*, *phish*, *spam*, or *none*.)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-163">![URL 威脅](../../media/URL_Threats.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-163">![URL threats](../../media/URL_Threats.png)</span></span>

### <a name="updated-timeline-view-upcoming"></a><span data-ttu-id="7a90f-164">已更新時程表 (近期) </span><span class="sxs-lookup"><span data-stu-id="7a90f-164">Updated timeline view (upcoming)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-165">![已更新的時程表視圖](../../media/Email_Timeline.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-165">![Updated Timeline View](../../media/Email_Timeline.png)</span></span>

<span data-ttu-id="7a90f-166">時程表視圖可識別所有傳遞和傳遞後的事件。</span><span class="sxs-lookup"><span data-stu-id="7a90f-166">Timeline view identifies all delivery and post-delivery events.</span></span> <span data-ttu-id="7a90f-167">其中會包含此時所識別威脅的資訊，以用於這些事件的子集。</span><span class="sxs-lookup"><span data-stu-id="7a90f-167">It includes information about the threat identified at that point of time for a subset of these events.</span></span> <span data-ttu-id="7a90f-168">時程表視圖也會提供對所採取之任何額外動作的資訊 (例如 ZAP 或手動補救) ，以及該動作的結果。</span><span class="sxs-lookup"><span data-stu-id="7a90f-168">Timeline view also provides information about any additional action taken (such as ZAP or manual remediation), along with the result of that action.</span></span> <span data-ttu-id="7a90f-169">時程表的視圖資訊包括：</span><span class="sxs-lookup"><span data-stu-id="7a90f-169">Timeline view information includes:</span></span>

- <span data-ttu-id="7a90f-170">**來源：** 事件的來源。</span><span class="sxs-lookup"><span data-stu-id="7a90f-170">**Source:** Source of the event.</span></span> <span data-ttu-id="7a90f-171">它可以是系統管理員/系統/使用者。</span><span class="sxs-lookup"><span data-stu-id="7a90f-171">It can be admin/system/user.</span></span>
- <span data-ttu-id="7a90f-172">**活動：** 包括原始傳遞、手動修復、ZAP、提交和動態傳遞等頂層事件。</span><span class="sxs-lookup"><span data-stu-id="7a90f-172">**Event:** Includes top-level events like original delivery, manual remediation, ZAP, submissions, and dynamic delivery.</span></span>
- <span data-ttu-id="7a90f-173">**動作：** 做為 ZAP 或系統管理動作之一部分 (執行的特定動作，例如，) 。</span><span class="sxs-lookup"><span data-stu-id="7a90f-173">**Action:** The specific action that was taken either as part of ZAP or admin action (for example, soft delete).</span></span>
- <span data-ttu-id="7a90f-174">**威脅：** 涵蓋此時 (識別的惡意) 、網路釣魚、垃圾郵件等威脅。</span><span class="sxs-lookup"><span data-stu-id="7a90f-174">**Threats:** Covers the threats (malware, phish, spam) identified at that point of time.</span></span>
- <span data-ttu-id="7a90f-175">**結果/詳細資料：** 有關動作結果詳細資訊，例如該動作是否做為 ZAP/系統管理員動作的一部分執行。</span><span class="sxs-lookup"><span data-stu-id="7a90f-175">**Result/Details:** More information about the result of the action, such as whether it was performed as part of ZAP/admin action.</span></span>

### <a name="original-and-latest-delivery-location"></a><span data-ttu-id="7a90f-176">原始且最新的送貨位置</span><span class="sxs-lookup"><span data-stu-id="7a90f-176">Original and latest delivery location</span></span>

<span data-ttu-id="7a90f-177">目前，我們已在電子郵件格線和電子郵件飛出區中顯示傳遞位置。</span><span class="sxs-lookup"><span data-stu-id="7a90f-177">Currently, we surface delivery location in the email grid and email flyout.</span></span> <span data-ttu-id="7a90f-178">正在 **重新命名傳送** 位置欄位 \**_原始的送貨位置_* _。</span><span class="sxs-lookup"><span data-stu-id="7a90f-178">The **Delivery location** field is getting renamed \**_Original delivery location_* _.</span></span> <span data-ttu-id="7a90f-179">此外，我們引進了另一個欄位： _\*_最新送貨位置_\*_。</span><span class="sxs-lookup"><span data-stu-id="7a90f-179">And we're introducing another field, _*_Latest delivery location_*_.</span></span>

<span data-ttu-id="7a90f-180">_ *原始的傳遞位置*\* 會提供有關電子郵件一開始遞送位置的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="7a90f-180">_ *Original delivery location*\* will give more information about where an email was delivered initially.</span></span> <span data-ttu-id="7a90f-181">**最新的傳遞位置** 會指出電子郵件在像 *ZAP* 這樣的系統動作或系統管理動作後送達的位置，例如移至 *已刪除的專案*。</span><span class="sxs-lookup"><span data-stu-id="7a90f-181">**Latest delivery location** will state where an email landed after system actions like *ZAP* or admin actions like *Move to deleted items*.</span></span> <span data-ttu-id="7a90f-182">最新的傳遞位置旨在通知系統管理員郵件在傳遞後的最後已知位置或任何系統/系統管理員動作。</span><span class="sxs-lookup"><span data-stu-id="7a90f-182">Latest delivery location is intended to tell admins the message's last-known location post-delivery or any system/admin actions.</span></span> <span data-ttu-id="7a90f-183">這不包含電子郵件上的任何使用者動作。</span><span class="sxs-lookup"><span data-stu-id="7a90f-183">It doesn't include any end-user actions on the email.</span></span> <span data-ttu-id="7a90f-184">例如，如果使用者刪除郵件或將郵件移至 archive/pst，郵件的「傳遞」位置將不會更新。</span><span class="sxs-lookup"><span data-stu-id="7a90f-184">For example, if a user deleted a message or moved the message to archive/pst, the message "delivery" location won't be updated.</span></span> <span data-ttu-id="7a90f-185">但如果系統動作更新郵件的位置，例如，ZAP (電子郵件移往隔離區) ，最新傳遞位置會顯示為「隔離」。 </span><span class="sxs-lookup"><span data-stu-id="7a90f-185">But if a system action updated the location (for example, ZAP resulting in an email moving to quarantine), **Latest delivery location** would show as "quarantine."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-186">![更新的送貨位置](../../media/Updated_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-186">![Updated delivery locations](../../media/Updated_Delivery_Location.png)</span></span>

> [!NOTE]
> <span data-ttu-id="7a90f-187">在某些情況下，傳遞位置和 **傳遞** 動作可能會顯示成「未知」： </span><span class="sxs-lookup"><span data-stu-id="7a90f-187">There are a few cases where **Delivery location** and **Delivery action** may show as "unknown":</span></span>
>
> - <span data-ttu-id="7a90f-188">如果郵件已送達，您可能會將傳遞位置視為「送達」和「未知」，但郵件已移至預設資料夾 (例如「草稿」或「封存」) ，而不是移至 「信箱」或「垃圾郵件」資料夾。</span><span class="sxs-lookup"><span data-stu-id="7a90f-188">You might see **Delivery location** as "delivered" and **Delivery location** as "unknown" if the message was delivered, but an Inbox rule moved the message to a default folder (such as Draft or Archive) instead of to the Inbox or Junk Email folder.</span></span>
>
> - <span data-ttu-id="7a90f-189">**如果系統管理員** /系統執行例如 ZAP (，) 傳送位置不明，但找不到訊息。</span><span class="sxs-lookup"><span data-stu-id="7a90f-189">**Latest delivery location** can be unknown if an admin/system action (such as ZAP) was attempted, but the message wasn't found.</span></span> <span data-ttu-id="7a90f-190">一般來說，動作會發生在使用者移動或刪除郵件之後。</span><span class="sxs-lookup"><span data-stu-id="7a90f-190">Typically, the action happens after the user  moved or deleted the message.</span></span> <span data-ttu-id="7a90f-191">在這種情況下，請驗證時程表 **視圖中的結果/** 詳細資料欄。</span><span class="sxs-lookup"><span data-stu-id="7a90f-191">In such cases, verify the **Result/Details** column in timeline view.</span></span> <span data-ttu-id="7a90f-192">尋找「使用者移動或刪除訊息」的陳述。</span><span class="sxs-lookup"><span data-stu-id="7a90f-192">Look for the statement "Message moved or deleted by the user."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-193">![時程表的傳遞位置](../../media/Updated_Timeline_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-193">![Delivery locations for timeline](../../media/Updated_Timeline_Delivery_Location.png)</span></span>

### <a name="additional-actions"></a><span data-ttu-id="7a90f-194">其他動作</span><span class="sxs-lookup"><span data-stu-id="7a90f-194">Additional actions</span></span>

<span data-ttu-id="7a90f-195">*傳送電子郵件* 之後，已執行其他動作。</span><span class="sxs-lookup"><span data-stu-id="7a90f-195">*Additional actions* were applied after delivery of the email.</span></span> <span data-ttu-id="7a90f-196">他們可以包括 *ZAP、* 手動修復 *(* 系統管理員採取的動作，例如，對經回溯偵測為良好電子郵件的) 、動態傳遞和 () 。</span><span class="sxs-lookup"><span data-stu-id="7a90f-196">They can include *ZAP*, *manual remediation* (action taken by an Admin such as soft delete), *dynamic delivery*, and *reprocessed* (for an email that was retroactively detected as good).</span></span>

> [!NOTE]
> - <span data-ttu-id="7a90f-197">在擱置變更中，目前顯示于傳遞動作篩選中的 「由 ZAP 移除」值會消失。</span><span class="sxs-lookup"><span data-stu-id="7a90f-197">As part of the pending changes, the "Removed by ZAP" value currently surfaced in the Delivery Action filter is going away.</span></span> <span data-ttu-id="7a90f-198">在 ZAP 嘗試執行其他動作時，您將可以搜尋所有 **電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="7a90f-198">You'll have a way to search for all email with the ZAP attempt through **Additional actions**.</span></span>
>
> - <span data-ttu-id="7a90f-199">偵測技術將會有新的欄位和值，以及其他動作 (尤其是 ZAP 案例和) 。</span><span class="sxs-lookup"><span data-stu-id="7a90f-199">There will be new fields and values for **Detection technologies** and **Additional actions** (especially for ZAP scenarios).</span></span> <span data-ttu-id="7a90f-200">您必須評估現有的已儲存查詢和追蹤查詢，以確保它們能使用新的值。</span><span class="sxs-lookup"><span data-stu-id="7a90f-200">You'll need to evaluate your existing saved queries and tracked queries to make sure they work with the new values.</span></span>

> [!div class="mx-imgBorder"]

> ![在 Explorer 中執行其他動作](../../media/Additional_Actions.png)

### <a name="system-overrides"></a><span data-ttu-id="7a90f-202">系統覆蓋</span><span class="sxs-lookup"><span data-stu-id="7a90f-202">System overrides</span></span>

<span data-ttu-id="7a90f-203">*系統替代* 功能可讓您將郵件的預定傳遞位置做為例外。</span><span class="sxs-lookup"><span data-stu-id="7a90f-203">*System overrides* enable you to make exceptions to the intended delivery location of a message.</span></span> <span data-ttu-id="7a90f-204">您根據篩選堆疊所識別的威脅與其他偵測，來取代系統提供的傳遞位置。</span><span class="sxs-lookup"><span data-stu-id="7a90f-204">You override the delivery location provided by the system, based on the threats and other detections identified by the filtering stack.</span></span> <span data-ttu-id="7a90f-205">您可以透過租使用者或使用者政策設定系統覆蓋，以根據該政策的建議傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="7a90f-205">System overrides can be set through tenant or user policy to deliver the message as suggested by the policy.</span></span> <span data-ttu-id="7a90f-206">因設定間有差異 ，例如使用者設定過於廣泛的安全寄件者政策，所以您能夠識別不小心傳送的惡意郵件。</span><span class="sxs-lookup"><span data-stu-id="7a90f-206">Overrides can identify unintentional delivery of malicious messages due to configurations gaps, such as an overly broad Safe Sender policy set by a user.</span></span> <span data-ttu-id="7a90f-207">這些替代值可以是：</span><span class="sxs-lookup"><span data-stu-id="7a90f-207">These override values can be:</span></span>

- <span data-ttu-id="7a90f-208">使用者策略允許：使用者會以信箱層級建立策略，以允許網域或寄件者。</span><span class="sxs-lookup"><span data-stu-id="7a90f-208">Allowed by user policy: A user creates policies at the mailbox level to allows domains or senders.</span></span>
- <span data-ttu-id="7a90f-209">被使用者策略封鎖：使用者以郵件方塊層級建立策略來封鎖網域或寄件者。</span><span class="sxs-lookup"><span data-stu-id="7a90f-209">Blocked by user policy: A user creates policies at the mail box level to block domains or senders.</span></span>
- <span data-ttu-id="7a90f-210">組織原則允許：組織的安全性小組會設定原則或 Exchange 郵件流程規則 (也稱為傳輸規則) ，為組織中的使用者允許寄件者和網域。</span><span class="sxs-lookup"><span data-stu-id="7a90f-210">Allowed by org policy: The organization's security teams set policies or Exchange mail flow rules (also known as transport rules) to allow senders and domains for users in their organization.</span></span> <span data-ttu-id="7a90f-211">這適用于一組使用者或整個組織。</span><span class="sxs-lookup"><span data-stu-id="7a90f-211">This can be for a set of users or the entire organization.</span></span>
- <span data-ttu-id="7a90f-212">被組織原則封鎖：組織的安全性小組會設定原則或郵件流程規則，以封鎖寄件者、網域、郵件語言或組織中使用者的來源 IP。</span><span class="sxs-lookup"><span data-stu-id="7a90f-212">Blocked by org policy: The organization's security teams set policies or mail flow rules to block senders, domains, message languages, or source IPs for users in their organization.</span></span> <span data-ttu-id="7a90f-213">這可套用至一組使用者或整個組織。</span><span class="sxs-lookup"><span data-stu-id="7a90f-213">This can be applied to a set of users or the entire organization.</span></span>
- <span data-ttu-id="7a90f-214">組織政策封鎖的副檔名：組織的安全性小組會透過反惡意程式碼政策設定封鎖副檔名。</span><span class="sxs-lookup"><span data-stu-id="7a90f-214">File extension blocked by org policy: An organization's security team blocks a file name extension through the anti-malware policy settings.</span></span> <span data-ttu-id="7a90f-215">這些值現在會顯示在電子郵件詳細資料中，協助調查。</span><span class="sxs-lookup"><span data-stu-id="7a90f-215">These values will now be displayed in email details to help with investigations.</span></span> <span data-ttu-id="7a90f-216">Secops 團隊也可使用豐富的篩選功能來篩選封鎖的副檔名。</span><span class="sxs-lookup"><span data-stu-id="7a90f-216">Secops teams can also use the rich-filtering capability to filter on blocked file extensions.</span></span>

<span data-ttu-id="7a90f-217">[![在 Explorer 中的系統覆蓋](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="7a90f-217">[![System Overrides in Explorer](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-218">![在 Explorer 中的系統覆蓋格線](../../media/System_Overrides_Grid.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-218">![System Overrides Grid in Explorer](../../media/System_Overrides_Grid.png)</span></span>

### <a name="improvements-for-the-url-and-clicks-experience"></a><span data-ttu-id="7a90f-219">改善 URL 和點擊體驗</span><span class="sxs-lookup"><span data-stu-id="7a90f-219">Improvements for the URL and clicks experience</span></span>

<span data-ttu-id="7a90f-220">這些改良專案包括：</span><span class="sxs-lookup"><span data-stu-id="7a90f-220">The improvements include:</span></span>

- <span data-ttu-id="7a90f-221">在 URL 飛出區段 (包含屬於 URL 連結一部分的任何查詢參數) 按一下的 URL連結。</span><span class="sxs-lookup"><span data-stu-id="7a90f-221">Show the full clicked URL (including any query parameters that are part of the URL) in the **Clicks** section of the URL flyout.</span></span> <span data-ttu-id="7a90f-222">目前，URL 網域和路徑會顯示在標題列中。</span><span class="sxs-lookup"><span data-stu-id="7a90f-222">Currently, the URL domain and path appear in the title bar.</span></span> <span data-ttu-id="7a90f-223">我們正在延伸該資訊以顯示完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="7a90f-223">We're extending that information to show the full URL.</span></span>

- <span data-ttu-id="7a90f-224">URL 篩選的修正 (*URL* 與 *URL* 網域 *、URL* 網域和路徑的修正) ：更新會影響搜尋包含 URL/click) 的郵件。</span><span class="sxs-lookup"><span data-stu-id="7a90f-224">Fixes across URL filters (*URL* versus *URL domain* versus *URL domain and path*): The updates affect searching for messages that contain a URL/click verdict.</span></span> <span data-ttu-id="7a90f-225">我們已啟用通訊協定診斷搜尋的支援，因此您可以搜尋 URL 而不使用 `http` 。</span><span class="sxs-lookup"><span data-stu-id="7a90f-225">We enabled support for protocol-agnostic searches, so you can search for a URL without using `http`.</span></span> <span data-ttu-id="7a90f-226">根據預設，除非明確指定其他值，否則 URL 搜尋會連結至 HTTP。</span><span class="sxs-lookup"><span data-stu-id="7a90f-226">By default, the URL search maps to http, unless another value is explicitly specified.</span></span> <span data-ttu-id="7a90f-227">例如：</span><span class="sxs-lookup"><span data-stu-id="7a90f-227">For example:</span></span>

   -  <span data-ttu-id="7a90f-228">搜尋 URL、URL 網域和 URL 網域和路徑篩選欄位中包含或 `http://` **不含** 首碼。  </span><span class="sxs-lookup"><span data-stu-id="7a90f-228">Search with and without the `http://` prefix in the **URL**, **URL Domain**, and **URL Domain and Path** filter fields.</span></span> <span data-ttu-id="7a90f-229">搜尋應該會顯示相同的結果。</span><span class="sxs-lookup"><span data-stu-id="7a90f-229">The searches should show the same results.</span></span>

   -  <span data-ttu-id="7a90f-230">在 `https://` **URL** 中搜尋首碼。</span><span class="sxs-lookup"><span data-stu-id="7a90f-230">Search for the `https://` prefix in **URL**.</span></span> <span data-ttu-id="7a90f-231">未指定值時，會 `http://` 假設首碼。</span><span class="sxs-lookup"><span data-stu-id="7a90f-231">When no value is specified, the `http://` prefix is assumed.</span></span>

   - <span data-ttu-id="7a90f-232">`/` URL 路徑 **、URL** 網域 **、URL** 網域和 **路徑欄位的開頭和** 結尾將被忽略。</span><span class="sxs-lookup"><span data-stu-id="7a90f-232">`/` is ignored at the beginning and end of the **URL path**, **URL Domain**, **URL domain and path** fields.</span></span> <span data-ttu-id="7a90f-233">`/` URL 欄位的 **結尾** 會被忽略。</span><span class="sxs-lookup"><span data-stu-id="7a90f-233">`/` at the end of the **URL** field is ignored.</span></span>

### <a name="phish-confidence-level"></a><span data-ttu-id="7a90f-234">網路釣魚信賴等級</span><span class="sxs-lookup"><span data-stu-id="7a90f-234">Phish confidence level</span></span>

<span data-ttu-id="7a90f-235">網路釣魚信賴等級可協助識別將電子郵件分類為「網路釣魚」的信賴度。</span><span class="sxs-lookup"><span data-stu-id="7a90f-235">Phish confidence level helps identify the degree of confidence with which an email was categorized as "phish."</span></span> <span data-ttu-id="7a90f-236">這兩個可能的值為 *High 和* *Normal。*</span><span class="sxs-lookup"><span data-stu-id="7a90f-236">The two possible values are *High* and *Normal*.</span></span> <span data-ttu-id="7a90f-237">在初始階段，只有威脅防護工具的網路釣魚視圖中才能使用此篩選器。</span><span class="sxs-lookup"><span data-stu-id="7a90f-237">In the initial stages, this filter will be available only in the Phish view of Threat Explorer.</span></span>

<span data-ttu-id="7a90f-238">[![Explorer 中的網路釣魚信賴等級](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="7a90f-238">[![Phish Confidence Level in Explorer](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span></span>

### <a name="zap-url-signal"></a><span data-ttu-id="7a90f-239">ZAP URL 訊號</span><span class="sxs-lookup"><span data-stu-id="7a90f-239">ZAP URL signal</span></span>

<span data-ttu-id="7a90f-240">ZAP URL 訊號通常是用於 ZAP 網路釣魚警示案例，當電子郵件被識別為網路釣魚，且在傳遞後即移除。</span><span class="sxs-lookup"><span data-stu-id="7a90f-240">The ZAP URL signal is typically used for ZAP Phish alert scenarios where an email was identified as Phish and removed after delivery.</span></span> <span data-ttu-id="7a90f-241">這個訊號將警示與 Explorer 中的對應結果連接。</span><span class="sxs-lookup"><span data-stu-id="7a90f-241">This signal connects the alert with the corresponding results in Explorer.</span></span> <span data-ttu-id="7a90f-242">它是警示的其中一個 IOC。</span><span class="sxs-lookup"><span data-stu-id="7a90f-242">It's one of the IOCs for the alert.</span></span>

<span data-ttu-id="7a90f-243">為了改善尋找流程，我們已更新威脅搜尋和即時偵測，讓尋找體驗更加一致。</span><span class="sxs-lookup"><span data-stu-id="7a90f-243">To improve the hunting process, we've updated Threat Explorer and Real-time detections to make the hunting experience more consistent.</span></span> <span data-ttu-id="7a90f-244">變更概述如下：</span><span class="sxs-lookup"><span data-stu-id="7a90f-244">The changes are outlined here:</span></span>

- [<span data-ttu-id="7a90f-245">時區的改良功能</span><span class="sxs-lookup"><span data-stu-id="7a90f-245">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="7a90f-246">重新更新程式中的更新</span><span class="sxs-lookup"><span data-stu-id="7a90f-246">Update in the refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="7a90f-247">要新進到篩選的圖表向下切入</span><span class="sxs-lookup"><span data-stu-id="7a90f-247">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="7a90f-248">在產品資訊更新中</span><span class="sxs-lookup"><span data-stu-id="7a90f-248">In product information updates</span></span>](#in-product-information-updates)

### <a name="filter-by-user-tags"></a><span data-ttu-id="7a90f-249">根據使用者標記篩選</span><span class="sxs-lookup"><span data-stu-id="7a90f-249">Filter by user tags</span></span>

<span data-ttu-id="7a90f-250">現在，您可以排序及篩選系統或自訂使用者標記，以快速掌握威脅的範圍。</span><span class="sxs-lookup"><span data-stu-id="7a90f-250">You can now sort and filter on system or custom user tags to quickly grasp the scope of threats.</span></span> <span data-ttu-id="7a90f-251">若要深入瞭解，請參閱使用者 [標記](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="7a90f-251">To learn more, see [User tags](user-tags.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a90f-252">篩選及排序使用者標記目前處於公開預覽。</span><span class="sxs-lookup"><span data-stu-id="7a90f-252">Filtering and sorting by user tags is currently in public preview.</span></span> <span data-ttu-id="7a90f-253">這項功能可能在正式發行前大幅修改。</span><span class="sxs-lookup"><span data-stu-id="7a90f-253">This functionality may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7a90f-254">Microsoft 對所提供的資訊，不提供明確或隱含的擔保。</span><span class="sxs-lookup"><span data-stu-id="7a90f-254">Microsoft makes no warranties, express or implied, with respect to the information provided about it.</span></span>

![在 Explorer 中的標記欄](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a><span data-ttu-id="7a90f-256">時區的改良功能</span><span class="sxs-lookup"><span data-stu-id="7a90f-256">Timezone improvements</span></span>

<span data-ttu-id="7a90f-257">您將在入口網站中查看電子郵件記錄以及匯出資料的時區。</span><span class="sxs-lookup"><span data-stu-id="7a90f-257">You'll see the time zone for the email records in the Portal as well as for Exported data.</span></span> <span data-ttu-id="7a90f-258">它會在電子郵件格線、詳細資料飛出視窗、電子郵件時程表和類似電子郵件等體驗中顯示，因此結果集的時區是明確的。</span><span class="sxs-lookup"><span data-stu-id="7a90f-258">It will be visible across experiences like Email Grid, Details flyout, Email Timeline, and Similar Emails, so the time zone for the result set is clear.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-259">![在 Explorer 中查看時區](../../media/TimezoneImprovements.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-259">![View time zone in Explorer](../../media/TimezoneImprovements.png)</span></span>

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="7a90f-260">重新更新程式中的更新</span><span class="sxs-lookup"><span data-stu-id="7a90f-260">Update in the refresh process</span></span>

<span data-ttu-id="7a90f-261">有些使用者針對自動重新 (工作造成混淆，例如，一旦變更日期，頁面就會重新) ，針對其他篩選或 (重新) 。</span><span class="sxs-lookup"><span data-stu-id="7a90f-261">Some users have commented about confusion with automatic refresh (for example, as soon as you change the date, the page refreshes) and manual refresh (for other filters).</span></span> <span data-ttu-id="7a90f-262">同樣地，移除篩選會導致自動重新組織。</span><span class="sxs-lookup"><span data-stu-id="7a90f-262">Similarly, removing filters leads to automatic refresh.</span></span> <span data-ttu-id="7a90f-263">在修改查詢時變更篩選可能會導致不一致的搜尋體驗。</span><span class="sxs-lookup"><span data-stu-id="7a90f-263">Changing filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="7a90f-264">為解決這些問題，我們正在移往手動篩選機制。</span><span class="sxs-lookup"><span data-stu-id="7a90f-264">To resolve these issues, we're moving to a manual-filtering mechanism.</span></span>

<span data-ttu-id="7a90f-265">從體驗中，使用者可以從篩選集和日期 (套用並移除不同的篩選範圍) 並選取重新更新按鈕，以在定義查詢後篩選結果。</span><span class="sxs-lookup"><span data-stu-id="7a90f-265">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set and date) and select the refresh button to filter the results after they've defined the query.</span></span> <span data-ttu-id="7a90f-266">現在在螢幕上也會強調重新管理按鈕。</span><span class="sxs-lookup"><span data-stu-id="7a90f-266">The refresh button is also now emphasized on the screen.</span></span> <span data-ttu-id="7a90f-267">我們也更新了相關的工具提示和產品內檔。</span><span class="sxs-lookup"><span data-stu-id="7a90f-267">We've also updated the related tooltips and in-product documentation.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-268">![選取重新更新以篩選結果](../../media/ManualRefresh.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-268">![Select Refresh to filter results](../../media/ManualRefresh.png)</span></span>

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="7a90f-269">要新進到篩選的圖表向下切入</span><span class="sxs-lookup"><span data-stu-id="7a90f-269">Chart drilldown to add to filters</span></span>

<span data-ttu-id="7a90f-270">您現在可以使用圖表圖例值，將其新增為篩選。</span><span class="sxs-lookup"><span data-stu-id="7a90f-270">You can now chart legend values to add them as filters.</span></span> <span data-ttu-id="7a90f-271">選取重新 **更新** 按鈕以篩選結果。</span><span class="sxs-lookup"><span data-stu-id="7a90f-271">Select the **Refresh** button to filter the results.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-272">![向下切入圖表以篩選](../../media/ChartDrilldown.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-272">![Drill down through charts to Filter](../../media/ChartDrilldown.png)</span></span>

### <a name="in-product-information-updates"></a><span data-ttu-id="7a90f-273">產品內資訊更新</span><span class="sxs-lookup"><span data-stu-id="7a90f-273">In-product information updates</span></span>

<span data-ttu-id="7a90f-274">產品現在提供其他詳細資料，例如格線中的搜尋結果 (如下所示) 。</span><span class="sxs-lookup"><span data-stu-id="7a90f-274">Additional details are now available within the product, such as the total number of search results within the grid (see below).</span></span> <span data-ttu-id="7a90f-275">我們改善了標籤、錯誤訊息和工具提示，以提供篩選、搜尋體驗和結果集的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="7a90f-275">We've improved labels, error messages, and tooltips to provide more information about the filters, search experience, and result set.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-276">![查看產品內資訊](../../media/ProductInfo.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-276">![View in-product information](../../media/ProductInfo.png)</span></span>

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="7a90f-277">威脅管中的擴充功能</span><span class="sxs-lookup"><span data-stu-id="7a90f-277">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="7a90f-278">主要目標使用者</span><span class="sxs-lookup"><span data-stu-id="7a90f-278">Top targeted users</span></span>

<span data-ttu-id="7a90f-279">今天，我們已在電子郵件的惡意攻擊系列區段的惡意惡意攻擊視圖中公開最主要目標 **使用者** 的清單。</span><span class="sxs-lookup"><span data-stu-id="7a90f-279">Today we expose the list of the top targeted users in the Malware view for emails, in the **Top Malware Families** section.</span></span> <span data-ttu-id="7a90f-280">我們也會在網路釣魚和所有電子郵件的視圖中延伸此視圖。</span><span class="sxs-lookup"><span data-stu-id="7a90f-280">We'll be extending this view in the Phish and All Email views as well.</span></span> <span data-ttu-id="7a90f-281">您將可查看前五名的目標使用者，以及對應視圖每個使用者的嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="7a90f-281">You'll be able to see the top-five targeted users, along with the number of attempts for each user for the corresponding view.</span></span> <span data-ttu-id="7a90f-282">例如，如果是網路釣魚視圖，則會看到網路釣魚嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="7a90f-282">For example, for Phish view, you'll see the number of Phish attempts.</span></span>

<span data-ttu-id="7a90f-283">您可以匯出目標使用者清單 ，最多 3，000 個，以及每個電子郵件視圖的離線分析嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="7a90f-283">You'll be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="7a90f-284">此外，選取嘗試次數 (例如，在下方影像中嘗試 13 次) 就會在威脅管理器中開啟篩選的畫面，好讓您可以查看該使用者的電子郵件和威脅的更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7a90f-284">In addition, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-285">![主要目標使用者](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-285">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="7a90f-286">Exchange 傳輸規則</span><span class="sxs-lookup"><span data-stu-id="7a90f-286">Exchange transport rules</span></span>

<span data-ttu-id="7a90f-287">在資料擴充作業中，您將能看到所有不同的 Exchange 傳輸規則 (ETR) 已適用于郵件。</span><span class="sxs-lookup"><span data-stu-id="7a90f-287">As part of data enrichment, you'll be able to see all the different Exchange transport rules (ETR) that were applied to a message.</span></span> <span data-ttu-id="7a90f-288">此資訊將在電子郵件格線中提供。</span><span class="sxs-lookup"><span data-stu-id="7a90f-288">This information will be available in the Email grid view.</span></span> <span data-ttu-id="7a90f-289">若要進行查看，請選取網格 **線中的欄** 選項，然後從資料行選項新增 **Exchange** 傳輸規則。</span><span class="sxs-lookup"><span data-stu-id="7a90f-289">To view it,  select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="7a90f-290">它也會顯示在電子郵件 **的詳細資料** 飛出區上。</span><span class="sxs-lookup"><span data-stu-id="7a90f-290">It will also be visible on the **Details** flyout in the email.</span></span>

<span data-ttu-id="7a90f-291">您將能看到 GUID 以及已適用于郵件的傳輸規則名稱。</span><span class="sxs-lookup"><span data-stu-id="7a90f-291">You'll be able to see both the GUID and the name of the transport rules that were applied to the message.</span></span> <span data-ttu-id="7a90f-292">您可以使用傳輸規則的名稱搜尋郵件。</span><span class="sxs-lookup"><span data-stu-id="7a90f-292">You'll be able to search for the messages by using the name of the transport rule.</span></span> <span data-ttu-id="7a90f-293">這是「包含」搜尋，這表示您也可以執行部分搜尋。</span><span class="sxs-lookup"><span data-stu-id="7a90f-293">This is a "Contains" search, which means you can do partial searches as well.</span></span>

#### <a name="important-note"></a><span data-ttu-id="7a90f-294">重要注意事項：</span><span class="sxs-lookup"><span data-stu-id="7a90f-294">Important note:</span></span>

<span data-ttu-id="7a90f-295">ETR 搜尋和名稱可用性取決於指派給您的特定角色。</span><span class="sxs-lookup"><span data-stu-id="7a90f-295">ETR search and name availability depend on the specific role that's assigned to you.</span></span> <span data-ttu-id="7a90f-296">您需要有下列其中一個角色/許可權才能查看 ETR 名稱和搜尋。</span><span class="sxs-lookup"><span data-stu-id="7a90f-296">You need to have one of the following roles/permissions to view the ETR names and search.</span></span> <span data-ttu-id="7a90f-297">如果您沒有指派任何這些角色給您，則看不到傳輸規則的名稱，或是使用 ETR 名稱搜尋郵件。</span><span class="sxs-lookup"><span data-stu-id="7a90f-297">If you don't have any of these roles assigned to you, you can't see the names of the transport rules or search for messages by using ETR names.</span></span> <span data-ttu-id="7a90f-298">不過，您可以在電子郵件詳細資料中查看 ETR 標籤和 GUID 資訊。</span><span class="sxs-lookup"><span data-stu-id="7a90f-298">However, you could see the ETR label and GUID information in the Email Details.</span></span> <span data-ttu-id="7a90f-299">電子郵件格線、電子郵件飛出視窗、篩選和匯出中其他記錄檢視體驗則不受影響。</span><span class="sxs-lookup"><span data-stu-id="7a90f-299">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>

- <span data-ttu-id="7a90f-300">僅適用于 EXO - 資料外泄防護：全部</span><span class="sxs-lookup"><span data-stu-id="7a90f-300">EXO Only - Data Loss Prevention: All</span></span>
- <span data-ttu-id="7a90f-301">僅 EXO - O365SupportViewConfig：全部</span><span class="sxs-lookup"><span data-stu-id="7a90f-301">EXO Only - O365SupportViewConfig: All</span></span>
- <span data-ttu-id="7a90f-302">Microsoft Azure Active Directory 或 EXO - 安全性系統管理員：全部</span><span class="sxs-lookup"><span data-stu-id="7a90f-302">Microsoft Azure Active Directory or EXO - Security Admin: All</span></span>
- <span data-ttu-id="7a90f-303">AAD 或 EXO - 安全性讀取程式：全部</span><span class="sxs-lookup"><span data-stu-id="7a90f-303">AAD or EXO - Security Reader: All</span></span>
- <span data-ttu-id="7a90f-304">僅適用于 EXO - 傳輸規則：全部</span><span class="sxs-lookup"><span data-stu-id="7a90f-304">EXO Only - Transport Rules: All</span></span>
- <span data-ttu-id="7a90f-305">僅 EXO - View-Only組式：全部</span><span class="sxs-lookup"><span data-stu-id="7a90f-305">EXO Only - View-Only Configuration: All</span></span>

<span data-ttu-id="7a90f-306">在電子郵件方格、詳細資料飛出和匯出 CSV 內，ETRs 會以名稱/GUID 呈現，如下所示。</span><span class="sxs-lookup"><span data-stu-id="7a90f-306">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-307">![Exchange 傳輸規則](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-307">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="7a90f-308">輸入連接器</span><span class="sxs-lookup"><span data-stu-id="7a90f-308">Inbound connectors</span></span>

<span data-ttu-id="7a90f-309">連接器是一組指示集合，可自訂電子郵件往來于 Microsoft 365 或 Office 365 組織之間的流程。</span><span class="sxs-lookup"><span data-stu-id="7a90f-309">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="7a90f-310">它們可啟用任何安全性限制或控制項。</span><span class="sxs-lookup"><span data-stu-id="7a90f-310">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="7a90f-311">在威脅管中，您現在能查看與電子郵件相關的連接器，以及使用連接器名稱搜尋電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7a90f-311">Within Threat Explorer, you can now view the connectors that are related to an email and search for emails by using connector names.</span></span>

<span data-ttu-id="7a90f-312">連接器的搜尋在本質上是「包含」的，這表示部分關鍵字搜尋應該也一樣。</span><span class="sxs-lookup"><span data-stu-id="7a90f-312">The search for connectors is "contains" in nature, which means partial keyword searches should work as well.</span></span> <span data-ttu-id="7a90f-313">在主格線視圖、詳細資料飛出區以及匯出的 CSV 中，連接器會以名稱/GUID 格式顯示，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7a90f-313">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown here:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-314">![連接器詳細資料](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-314">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="7a90f-315">威脅管和即時偵測中的新功能</span><span class="sxs-lookup"><span data-stu-id="7a90f-315">New features in Threat Explorer and Real-time detections</span></span>

<span data-ttu-id="7a90f-316">威脅管和即時偵測有三個新功能可用：</span><span class="sxs-lookup"><span data-stu-id="7a90f-316">Three new features are available in Threat Explorer and Real-time detections:</span></span>

- [<span data-ttu-id="7a90f-317">預覽電子郵件標頭和下載電子郵件內文</span><span class="sxs-lookup"><span data-stu-id="7a90f-317">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="7a90f-318">電子郵件時間表</span><span class="sxs-lookup"><span data-stu-id="7a90f-318">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="7a90f-319">匯出 URL 點擊資料</span><span class="sxs-lookup"><span data-stu-id="7a90f-319">Export URL click data</span></span>](#export-url-click-data)

<span data-ttu-id="7a90f-320">新功能如下所列。</span><span class="sxs-lookup"><span data-stu-id="7a90f-320">These new features are outlined below.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="7a90f-321">預覽電子郵件標頭和下載電子郵件內文</span><span class="sxs-lookup"><span data-stu-id="7a90f-321">Preview email header and download email body</span></span>

<span data-ttu-id="7a90f-322">現在，您可以預覽電子郵件標題，並下載威脅中心系統管理員的電子郵件內文，以分析下載的標題/電子郵件訊息以尋找威脅。</span><span class="sxs-lookup"><span data-stu-id="7a90f-322">You can now preview an email header and download the email body in Threat Explorer Admins can analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="7a90f-323">由於下載電子郵件訊息可能會風險曝光資訊，因此此程式是由角色型存取控制 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="7a90f-323">Because downloading email messages can risk exposure of information, this process is controlled by role-based access control (RBAC).</span></span> <span data-ttu-id="7a90f-324">您必須將新角色預覽新增到另一個角色群組 (例如安全性作業或安全性系統管理員) ，才能在全電子郵件訊息視圖中下載郵件及預覽標題。</span><span class="sxs-lookup"><span data-stu-id="7a90f-324">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails and preview headers in all-email messages view.</span></span>

<span data-ttu-id="7a90f-325">Explorer 和即時偵測也會取得新欄位，提供您電子郵件訊息位置的完整畫面。</span><span class="sxs-lookup"><span data-stu-id="7a90f-325">Explorer and Real-time detections will also get new fields that provide a more complete picture of where your email messages land.</span></span> <span data-ttu-id="7a90f-326">這些變更讓尋找安全性活動變得更容易。</span><span class="sxs-lookup"><span data-stu-id="7a90f-326">These changes  make hunting easier for Security Ops.</span></span> <span data-ttu-id="7a90f-327">但主要結果還是您可以一目了然地知道問題電子郵件訊息的位置。</span><span class="sxs-lookup"><span data-stu-id="7a90f-327">But the main result is you can know the location of problem email messages at a glance.</span></span>

<span data-ttu-id="7a90f-328">這是如何達成？</span><span class="sxs-lookup"><span data-stu-id="7a90f-328">How is this done?</span></span> <span data-ttu-id="7a90f-329">傳遞狀態現在分成兩欄：</span><span class="sxs-lookup"><span data-stu-id="7a90f-329">Delivery status is now broken out into two columns:</span></span>

- <span data-ttu-id="7a90f-330">**傳遞動作** - 電子郵件的狀態。</span><span class="sxs-lookup"><span data-stu-id="7a90f-330">**Delivery action** - Status of the email.</span></span>
- <span data-ttu-id="7a90f-331">**傳遞位置** - 電子郵件的路由位置。</span><span class="sxs-lookup"><span data-stu-id="7a90f-331">**Delivery location** - Where the email was routed.</span></span>

<span data-ttu-id="7a90f-332">*傳遞動作* 是因現有政策或偵測對電子郵件採取的動作。</span><span class="sxs-lookup"><span data-stu-id="7a90f-332">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="7a90f-333">以下是電子郵件的可能動作：</span><span class="sxs-lookup"><span data-stu-id="7a90f-333">Here are the possible actions for an email:</span></span>

|<span data-ttu-id="7a90f-334">已傳遞</span><span class="sxs-lookup"><span data-stu-id="7a90f-334">Delivered</span></span>|<span data-ttu-id="7a90f-335">已標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="7a90f-335">Junked</span></span>|<span data-ttu-id="7a90f-336">已封鎖</span><span class="sxs-lookup"><span data-stu-id="7a90f-336">Blocked</span></span>|<span data-ttu-id="7a90f-337">已取代</span><span class="sxs-lookup"><span data-stu-id="7a90f-337">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="7a90f-338">電子郵件已傳送到使用者的信箱或資料夾，使用者可以存取。</span><span class="sxs-lookup"><span data-stu-id="7a90f-338">Email was delivered to the inbox or folder of a user, and the user can access it.</span></span>|<span data-ttu-id="7a90f-339">電子郵件已送到使用者的垃圾郵件或已刪除資料夾，使用者可以存取。</span><span class="sxs-lookup"><span data-stu-id="7a90f-339">Email was sent to the user's Junk  or Deleted folder, and the user can access it.</span></span>|<span data-ttu-id="7a90f-340">受到隔離、失敗或已中斷的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7a90f-340">Emails that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="7a90f-341">使用者無法使用這些郵件。</span><span class="sxs-lookup"><span data-stu-id="7a90f-341">These mails are inaccessible to the user.</span></span>|<span data-ttu-id="7a90f-342">電子郵件已由 .txt 檔案取代為惡意附件，而該檔案會指出附件為惡意。</span><span class="sxs-lookup"><span data-stu-id="7a90f-342">Email had malicious attachments replaced by .txt files that state the attachment was malicious.</span></span>|

<span data-ttu-id="7a90f-343">以下是使用者無法及無法看到哪些專案：</span><span class="sxs-lookup"><span data-stu-id="7a90f-343">Here is what the user can and can't see:</span></span>

|<span data-ttu-id="7a90f-344">使用者可以存取</span><span class="sxs-lookup"><span data-stu-id="7a90f-344">Accessible to end users</span></span>|<span data-ttu-id="7a90f-345">使用者無法存取 </span><span class="sxs-lookup"><span data-stu-id="7a90f-345">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="7a90f-346">已傳遞</span><span class="sxs-lookup"><span data-stu-id="7a90f-346">Delivered</span></span>|<span data-ttu-id="7a90f-347">已封鎖</span><span class="sxs-lookup"><span data-stu-id="7a90f-347">Blocked</span></span>|
|<span data-ttu-id="7a90f-348">已標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="7a90f-348">Junked</span></span>|<span data-ttu-id="7a90f-349">已取代</span><span class="sxs-lookup"><span data-stu-id="7a90f-349">Replaced</span></span>|

<span data-ttu-id="7a90f-350">**傳遞位置** 會顯示在傳遞後執行之策略和偵測的結果。</span><span class="sxs-lookup"><span data-stu-id="7a90f-350">**Delivery location** shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="7a90f-351">它連結至 \**_傳遞動作_* _。</span><span class="sxs-lookup"><span data-stu-id="7a90f-351">It's linked to \**_Delivery action_* _.</span></span> <span data-ttu-id="7a90f-352">這些可能是值：</span><span class="sxs-lookup"><span data-stu-id="7a90f-352">These are the possible values:</span></span>

- <span data-ttu-id="7a90f-353">_Inbox資料夾\*：電子郵件會依據您的電子郵件規則或資料夾 (在郵件) 。</span><span class="sxs-lookup"><span data-stu-id="7a90f-353">_Inbox or folder\*: The email is in the inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="7a90f-354">*內部部署或外部*：信箱不存在於雲端，但位於內部部署。</span><span class="sxs-lookup"><span data-stu-id="7a90f-354">*On-prem or external*: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="7a90f-355">*垃圾郵件資料夾*：電子郵件位於使用者的垃圾郵件資料夾中。</span><span class="sxs-lookup"><span data-stu-id="7a90f-355">*Junk folder*: The email is in a user's Junk folder.</span></span>
- <span data-ttu-id="7a90f-356">*刪除的郵件資料夾*：使用者的刪除專案資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7a90f-356">*Deleted items folder*: The email in a user's Deleted items folder.</span></span>
- <span data-ttu-id="7a90f-357">*隔離*：電子郵件是在隔離中，而不是在使用者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="7a90f-357">*Quarantine*: The email is in quarantine and not in a user's mailbox.</span></span>
- <span data-ttu-id="7a90f-358">*失敗*；電子郵件無法傳遞至信箱。</span><span class="sxs-lookup"><span data-stu-id="7a90f-358">*Failed*: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="7a90f-359">*已* 刪除：電子郵件在郵件流程的某處遺失。</span><span class="sxs-lookup"><span data-stu-id="7a90f-359">*Dropped*: The email got lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="7a90f-360">電子郵件時間表</span><span class="sxs-lookup"><span data-stu-id="7a90f-360">Email timeline</span></span>

<span data-ttu-id="7a90f-361">電子郵件 **時程表** 是新的 Explorer 功能，可改善系統管理員的搜尋體驗。</span><span class="sxs-lookup"><span data-stu-id="7a90f-361">The **Email timeline** is a new Explorer feature that improves the hunting experience for admins.</span></span> <span data-ttu-id="7a90f-362">它會減少檢查不同位置以嘗試瞭解活動所花費的時間。</span><span class="sxs-lookup"><span data-stu-id="7a90f-362">It cuts the time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="7a90f-363">當多個事件在電子郵件送達的同一時間發生或接近時，這些事件會顯示在時程表視圖中。</span><span class="sxs-lookup"><span data-stu-id="7a90f-363">When multiple events happen at or close to the same time an email arrives, those events are displayed in a timeline view.</span></span> <span data-ttu-id="7a90f-364">傳送電子郵件後會發生一些事件，會記錄在特殊動作 **欄中** 。</span><span class="sxs-lookup"><span data-stu-id="7a90f-364">Some events that happen to your email post-delivery are captured in the **Special action** column.</span></span> <span data-ttu-id="7a90f-365">系統管理員可以將時程表的資訊與郵件傳遞後採取的特殊動作結合，以深入瞭解其政策如何執行、郵件最後路由在哪裡，以及在某些情況下，最後評定的內容。</span><span class="sxs-lookup"><span data-stu-id="7a90f-365">Admins can combine  information from the timeline with the special action taken on the mail post-delivery to get insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="7a90f-366">詳細資訊請參閱調查 [並修復 Office 365 中傳遞的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)。</span><span class="sxs-lookup"><span data-stu-id="7a90f-366">For more information, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="7a90f-367">匯出 URL 點擊資料</span><span class="sxs-lookup"><span data-stu-id="7a90f-367">Export URL click data</span></span>

<span data-ttu-id="7a90f-368">現在，您可以將 URL 點擊的報告匯出至 Microsoft Excel，以查看其網路訊息 **識別碼**，然後按一下位址，這有助於說明 URL 按一下流量的起始位置。</span><span class="sxs-lookup"><span data-stu-id="7a90f-368">You can now export reports for URL clicks to Microsoft Excel to view their **network message ID** and **click verdict**, which helps explain where your URL click traffic originated.</span></span> <span data-ttu-id="7a90f-369">運作方式如下：在 Office 365 快速啟動工具列上的威脅管理中，遵循此鏈：</span><span class="sxs-lookup"><span data-stu-id="7a90f-369">Here's how it works: In Threat Management on the Office 365 quick-launch bar, follow this chain:</span></span>

<span data-ttu-id="7a90f-370">**Explorer** \>**查看網路釣魚** \>**按一下** \>**熱門 URL 或** **URL Top Clicks 會** 選取 \> 任何記錄以開啟 URL 飛出。</span><span class="sxs-lookup"><span data-stu-id="7a90f-370">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs** or **URL Top Clicks** \> select any record to open the URL flyout.</span></span>

<span data-ttu-id="7a90f-371">當您在清單中選取 URL 時，就會在飛出面板上看到新的匯出按鈕。</span><span class="sxs-lookup"><span data-stu-id="7a90f-371">When you select a URL in the list, you'll see a new **Export** button on the fly-out panel.</span></span> <span data-ttu-id="7a90f-372">使用此按鈕將資料移至 Excel 試算表，以便更輕鬆地進行報告。</span><span class="sxs-lookup"><span data-stu-id="7a90f-372">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="7a90f-373">請遵循此路徑，在即時偵測報告中找到相同的位置：</span><span class="sxs-lookup"><span data-stu-id="7a90f-373">Follow this path to get to the same location in the Real-time detections report:</span></span>

<span data-ttu-id="7a90f-374">**Explorer** \>**即時偵測** \>**查看網路釣魚** \>**URL** \>**熱門 URL** 或 **熱門滑鼠按鍵選取** \> 任何記錄以開啟 URL 飛出視窗 \> ，流覽至按一下 **按鈕。**</span><span class="sxs-lookup"><span data-stu-id="7a90f-374">**Explorer** \> **Real-time detections** \> **View Phish** \> **URLs** \> **Top URLs** or **Top Clicks** \> Select any record to open the URL flyout \> navigate to the **Clicks** tab.</span></span>

> [!TIP]
> <span data-ttu-id="7a90f-375">當您透過 Explorer 或相關聯的協力廠商工具搜尋識別碼時，網路訊息識別碼會將您按一下的內容重新連結至特定郵件。</span><span class="sxs-lookup"><span data-stu-id="7a90f-375">The Network Message ID maps the click back to specific mails when you search on the ID through Explorer or associated third-party tools.</span></span> <span data-ttu-id="7a90f-376">這類搜尋會識別與按一下結果相關聯的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7a90f-376">Such searches identify the email associated with a click result.</span></span> <span data-ttu-id="7a90f-377">擁有相關的網路訊息識別碼，可更快速且更功能強大的分析。</span><span class="sxs-lookup"><span data-stu-id="7a90f-377">Having the correlated Network Message ID makes for quicker and more powerful analysis.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a90f-378">![在 Explorer 中按滑鼠按鍵](../../media/tp_ExportClickResultAndNetworkID.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-378">![Clicks tab in Explorer](../../media/tp_ExportClickResultAndNetworkID.png)</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="7a90f-379">查看透過技術在電子郵件中偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="7a90f-379">See malware detected in email by technology</span></span>

<span data-ttu-id="7a90f-380">假設您想要在 Microsoft 365 技術排序的電子郵件中查看偵測到的惡意攻擊。</span><span class="sxs-lookup"><span data-stu-id="7a90f-380">Suppose you want to see malware detected in email sorted by Microsoft 365 technology.</span></span> <span data-ttu-id="7a90f-381">若要這麼做，請使用 Explorer [>](threat-explorer-views.md#email--malware) 的電子郵件和惡意 (或即時偵測) 。</span><span class="sxs-lookup"><span data-stu-id="7a90f-381">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="7a90f-382">在安全性與合規性中心 (<https://protection.office.com>) 選擇 **[威脅管理]** \> **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="7a90f-382">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="7a90f-383">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="7a90f-383">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="7a90f-384">在視圖 **功能表中**，選擇電子郵件 \> **惡意攻擊**。</span><span class="sxs-lookup"><span data-stu-id="7a90f-384">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7a90f-385">![總管的檢視功能表](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-385">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="7a90f-386">按一下 **[寄件者**，然後選擇基本 \> **偵測技術**。</span><span class="sxs-lookup"><span data-stu-id="7a90f-386">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="7a90f-387">您的偵測技術現在可做為報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="7a90f-387">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7a90f-388">![惡意程式碼偵測技術](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-388">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="7a90f-389">選擇一個選項。</span><span class="sxs-lookup"><span data-stu-id="7a90f-389">Choose an option.</span></span> <span data-ttu-id="7a90f-390">然後選取重新 **更新** 按鈕來申請該篩選。</span><span class="sxs-lookup"><span data-stu-id="7a90f-390">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7a90f-391">![選取的偵測技術](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-391">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

<span data-ttu-id="7a90f-392">報告會重新顯示您選取的技術選項，顯示電子郵件中偵測到的惡意攻擊結果。</span><span class="sxs-lookup"><span data-stu-id="7a90f-392">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="7a90f-393">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="7a90f-393">From here, you can conduct further analysis.</span></span>

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="7a90f-394">查看網路釣魚 URL 並按一下 [網路釣魚資料</span><span class="sxs-lookup"><span data-stu-id="7a90f-394">View phishing URL and click verdict data</span></span>

<span data-ttu-id="7a90f-395">假設您想要查看透過電子郵件中的 URL 進行的網路釣魚攻擊，包括允許、封鎖及覆寫的 URL 清單。</span><span class="sxs-lookup"><span data-stu-id="7a90f-395">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="7a90f-396">若要識別按一下的 URL， [必須](atp-safe-links.md) 安裝 [安全連結。</span><span class="sxs-lookup"><span data-stu-id="7a90f-396">To identify URLs that were clicked, [Safe Links](atp-safe-links.md) must be configured.</span></span> <span data-ttu-id="7a90f-397">請務必針對安全連結 [的](set-up-atp-safe-links-policies.md) 按一下時間保護及記錄按一下的裝置設定安全連結政策。</span><span class="sxs-lookup"><span data-stu-id="7a90f-397">Make sure that you set up [Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="7a90f-398">若要檢閱郵件中的網路釣魚 URL，並按一下網路釣魚郵件中的 URL，請使用 [\*\*\*\*  >  \*\*\*\*](threat-explorer-views.md#email--phish)Explorer 的電子郵件網路釣魚視圖或即時偵測。</span><span class="sxs-lookup"><span data-stu-id="7a90f-398">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="7a90f-399">在安全性與合規性中心 (<https://protection.office.com>) 選擇 **[威脅管理]** \> **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="7a90f-399">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="7a90f-400">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="7a90f-400">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="7a90f-401">在視圖 **功能表中**，選擇電子郵件 \> **網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="7a90f-401">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7a90f-402">![網路釣魚內容中的 Explorer 的查看功能表](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-402">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="7a90f-403">按一下 **[寄件者**，然後選擇 **URL** \> **Click 寄件人**。</span><span class="sxs-lookup"><span data-stu-id="7a90f-403">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="7a90f-404">選取一或多個選項 ，例如已封鎖和已封鎖，然後選取與要申請該篩選之選項位於同一行的重新更新按鈕。 </span><span class="sxs-lookup"><span data-stu-id="7a90f-404">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="7a90f-405">(請勿重新整理瀏覽器視窗。)</span><span class="sxs-lookup"><span data-stu-id="7a90f-405">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7a90f-406">![URL 和按一下結果](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-406">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="7a90f-407">報告會重新整理以在報告下的 [URL] 索引標籤上顯示兩個不同的 URL 表格：</span><span class="sxs-lookup"><span data-stu-id="7a90f-407">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="7a90f-408">**最上方 URL** 是篩選到郵件中的 URL，以及每個 URL 的電子郵件傳遞動作計數。</span><span class="sxs-lookup"><span data-stu-id="7a90f-408">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="7a90f-409">在網路釣魚電子郵件的視圖中，此清單通常包含合法的 URL。</span><span class="sxs-lookup"><span data-stu-id="7a90f-409">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="7a90f-410">攻擊者在郵件中混合了良好和錯誤的 URL 以嘗試傳遞，但會使惡意連結看起來更有趣。</span><span class="sxs-lookup"><span data-stu-id="7a90f-410">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="7a90f-411">URL 表格是按照電子郵件總數排序，但此欄為隱藏狀態以簡化顯示方式。</span><span class="sxs-lookup"><span data-stu-id="7a90f-411">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="7a90f-412">**熱門點擊** 數是已按過的安全連結換行 URL，按總點擊數排序。</span><span class="sxs-lookup"><span data-stu-id="7a90f-412">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="7a90f-413">系統不會顯示此欄，以簡化您的視圖。</span><span class="sxs-lookup"><span data-stu-id="7a90f-413">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="7a90f-414">依資料行的總計數表示每個點擊過的 URL 的安全連結按一下結果計數。</span><span class="sxs-lookup"><span data-stu-id="7a90f-414">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="7a90f-415">在網路釣魚電子郵件的視圖中，這些通常是可疑或惡意的 URL。</span><span class="sxs-lookup"><span data-stu-id="7a90f-415">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="7a90f-416">但該視圖可能包含不是威脅，而是網路釣魚郵件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="7a90f-416">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="7a90f-417">URL 按一下未顯示的連結不會顯示在這裡。</span><span class="sxs-lookup"><span data-stu-id="7a90f-417">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="7a90f-418">這兩個 URL 表格會根據傳遞動作和位置，顯示網路釣魚電子郵件訊息中的熱門 URL。</span><span class="sxs-lookup"><span data-stu-id="7a90f-418">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="7a90f-419">表格顯示儘管警告仍封鎖或流覽的 URL 點擊次數，因此您可以查看使用者看到哪些潛在錯誤連結，以及使用者按一下了哪些連結。</span><span class="sxs-lookup"><span data-stu-id="7a90f-419">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the user's clicked.</span></span> <span data-ttu-id="7a90f-420">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="7a90f-420">From here, you can conduct further analysis.</span></span> <span data-ttu-id="7a90f-421">例如，在圖表下方，您可以看見電子郵件訊息中，在貴組織環境中封鎖的熱門 URL。</span><span class="sxs-lookup"><span data-stu-id="7a90f-421">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7a90f-422">![已封鎖的總管 URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-422">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="7a90f-423">選取 URL 以檢視更多詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="7a90f-423">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7a90f-424">在 URL 彈出對話方塊中，電子郵件訊息的篩選會移除，以顯示您環境中 URL 曝光的完整視圖。</span><span class="sxs-lookup"><span data-stu-id="7a90f-424">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="7a90f-425">這可讓您在 [Explorer> 中篩選您關心的電子郵件訊息、尋找潛在威脅的特定 URL，然後透過 URL 詳細資料對話方塊 (擴展您對於您環境中 URL 公開的理解程度) 而不需要將 URL 篩選新到 [Explorer 視圖本身。</span><span class="sxs-lookup"><span data-stu-id="7a90f-425">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="7a90f-426">滑鼠按鍵的解譯</span><span class="sxs-lookup"><span data-stu-id="7a90f-426">Interpretation of click verdicts</span></span>

<span data-ttu-id="7a90f-427">在電子郵件或 URL 飛出區、[按前點擊數時， 以及在我們的篩選體驗中，您看到不同的按一下結果值：</span><span class="sxs-lookup"><span data-stu-id="7a90f-427">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="7a90f-428">**無：** 無法捕捉 URL 的當做資訊。</span><span class="sxs-lookup"><span data-stu-id="7a90f-428">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="7a90f-429">使用者可能已經按一下 URL。</span><span class="sxs-lookup"><span data-stu-id="7a90f-429">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="7a90f-430">**已允許：** 已允許使用者流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="7a90f-430">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="7a90f-431">**已封鎖：** 使用者已封鎖，因此沒有流覽到 URL。</span><span class="sxs-lookup"><span data-stu-id="7a90f-431">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="7a90f-432">**擱置中：** 使用者被呈現在擱置中頁面。</span><span class="sxs-lookup"><span data-stu-id="7a90f-432">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="7a90f-433">**已封鎖：** 使用者已被封鎖，因此不能直接流覽到 URL。</span><span class="sxs-lookup"><span data-stu-id="7a90f-433">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="7a90f-434">但使用者超過封鎖，流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="7a90f-434">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="7a90f-435">**擱置中已跳過：** 使用者隨即被呈現在查看頁面。</span><span class="sxs-lookup"><span data-stu-id="7a90f-435">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="7a90f-436">但使用者過度控制訊息以存取 URL。</span><span class="sxs-lookup"><span data-stu-id="7a90f-436">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="7a90f-437">**錯誤：** 使用者收到錯誤頁面，或是在拍攝結果時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="7a90f-437">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="7a90f-438">**失敗：** 捕捉事件時，發生未知的例外。</span><span class="sxs-lookup"><span data-stu-id="7a90f-438">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="7a90f-439">使用者可能已經按一下 URL。</span><span class="sxs-lookup"><span data-stu-id="7a90f-439">The user might have clicked through the URL.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="7a90f-440">檢閱使用者回報的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="7a90f-440">Review email messages reported by users</span></span>

<span data-ttu-id="7a90f-441">假設您想查看貴組織使用者透過報告郵件附加元件或報告網路釣魚附加元件，被系統報告為垃圾郵件、非垃圾郵件[](enable-the-report-message-add-in.md)或網路釣魚[的電子郵件訊息](enable-the-report-phish-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="7a90f-441">Suppose that you want to see email messages that users in your organization reported as *Junk*, *Not Junk*, or *Phishing* through the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span> <span data-ttu-id="7a90f-442">若要查看它們，請使用 Explorer [ \*\*\*\*  >  **的**](threat-explorer-views.md#email--submissions)電子郵件提交 (或即時偵測) 。</span><span class="sxs-lookup"><span data-stu-id="7a90f-442">To see them, use the [**Email** > **Submissions**](threat-explorer-views.md#email--submissions) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="7a90f-443">在安全性與合規性中心 (<https://protection.office.com>) 選擇 **[威脅管理]** \> **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="7a90f-443">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="7a90f-444">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="7a90f-444">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="7a90f-445">在視圖 **功能表中\*\*\*\*，選擇電子郵件** \> **提交**。</span><span class="sxs-lookup"><span data-stu-id="7a90f-445">In the **View** menu, choose **Email** \> **Submissions**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7a90f-446">![電子郵件的 Explorer 的查看功能表](../../media/explorer-view-menu-email-user-reported.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-446">![View menu for Explorer for emails](../../media/explorer-view-menu-email-user-reported.png)</span></span>

3. <span data-ttu-id="7a90f-447">按一下 **[寄件者**，然後選擇基本 \> **報表類型**。</span><span class="sxs-lookup"><span data-stu-id="7a90f-447">Click **Sender**, and then choose **Basic** \> **Report type**.</span></span>

4. <span data-ttu-id="7a90f-448">選取某個選項 ，例如 **網路釣魚，** 然後選取重新 **組織按鈕** 。</span><span class="sxs-lookup"><span data-stu-id="7a90f-448">Select an option, such as **Phish**, and then select the **Refresh** button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7a90f-449">![使用者回報的網路釣魚](../../media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="7a90f-449">![User-reported phish](../../media/EmailUserReportedReportType.png)</span></span>

<span data-ttu-id="7a90f-450">報表會重新顯示貴組織中人員報告為網路釣魚之電子郵件訊息的資料類型。</span><span class="sxs-lookup"><span data-stu-id="7a90f-450">The report refreshes to show data about email messages that people in your organization reported as a phishing attempt.</span></span> <span data-ttu-id="7a90f-451">您可以使用此資訊進行進一步分析，並視需要調整 Microsoft Defender [for Office 365](configure-atp-anti-phishing-policies.md)中的防網路釣魚政策。</span><span class="sxs-lookup"><span data-stu-id="7a90f-451">You can use this information to conduct further analysis, and, if necessary, adjust your [anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="7a90f-452">啟動自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="7a90f-452">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="7a90f-453">Microsoft Defender for *Office 365 方案 2* 和 Office *365 E5* 提供自動化調查與回應功能。</span><span class="sxs-lookup"><span data-stu-id="7a90f-453">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="7a90f-454">[自動化調查與回應](automated-investigation-response-office.md) 可節省安全性作業小組花費在調查與減少網路攻擊上的時間與精力。</span><span class="sxs-lookup"><span data-stu-id="7a90f-454">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="7a90f-455">除了設定會觸發安全性劇本的警示，您可以在總管中的檢視啟動自動化調查及回應程序。</span><span class="sxs-lookup"><span data-stu-id="7a90f-455">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="7a90f-456">詳情請參閱 [範例：安全性系統管理員會觸發](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)來自 Explorer 進行調查。</span><span class="sxs-lookup"><span data-stu-id="7a90f-456">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a><span data-ttu-id="7a90f-457">更多使用 Explorer 和即時偵測的方式</span><span class="sxs-lookup"><span data-stu-id="7a90f-457">More ways to use Explorer and Real-time detections</span></span>

<span data-ttu-id="7a90f-458">除了本文所述的案例之外，您還可以使用更多適用于 Explorer 的報告選項 (或即時偵測) 。</span><span class="sxs-lookup"><span data-stu-id="7a90f-458">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or Real-time detections).</span></span> <span data-ttu-id="7a90f-459">請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="7a90f-459">See the following articles:</span></span>

- [<span data-ttu-id="7a90f-460">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="7a90f-460">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="7a90f-461">檢視在 SharePoint Online、OneDrive 和 Microsoft Teams 中偵測到的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="7a90f-461">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="7a90f-462">概觀威脅總管中的 (和即時偵測) </span><span class="sxs-lookup"><span data-stu-id="7a90f-462">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="7a90f-463">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="7a90f-463">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="7a90f-464">Microsoft 威脅防護的自動化調查及回應</span><span class="sxs-lookup"><span data-stu-id="7a90f-464">Automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="7a90f-465">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="7a90f-465">Required licenses and permissions</span></span>

<span data-ttu-id="7a90f-466">您必須擁有 [適用于 Office 365](office-365-atp.md) 的 Microsoft Defender，以使用 Explorer 或即時偵測。</span><span class="sxs-lookup"><span data-stu-id="7a90f-466">You must have [Microsoft Defender for Office 365](office-365-atp.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="7a90f-467">總管包含在 Office 365 方案 2 的 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="7a90f-467">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="7a90f-468">即時偵測報告包含在 Office 365 方案 1 的 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="7a90f-468">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="7a90f-469">規劃指派授權給應該受 Office 365 Defender 保護的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="7a90f-469">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="7a90f-470">Explorer 和即時偵測會顯示授權使用者的偵測資料。</span><span class="sxs-lookup"><span data-stu-id="7a90f-470">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="7a90f-471">若要查看及使用 Explorer 或即時偵測，您必須擁有適當的許可權，例如授予安全性系統管理員或安全性讀取者的許可權。</span><span class="sxs-lookup"><span data-stu-id="7a90f-471">To view and use Explorer or Real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="7a90f-472">針對安全性&規範中心，您必須有指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="7a90f-472">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="7a90f-473">組織管理</span><span class="sxs-lookup"><span data-stu-id="7a90f-473">Organization Management</span></span>
  - <span data-ttu-id="7a90f-474">安全性系統管理員 (可以在 Azure Active Directory 系統管理中心 <https://aad.portal.azure.com> () </span><span class="sxs-lookup"><span data-stu-id="7a90f-474">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="7a90f-475">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="7a90f-475">Security Reader</span></span>

- <span data-ttu-id="7a90f-476">對於 Exchange Online，您必須在 Exchange 系統管理中心或 Exchange Online PowerShell 中指派下列其中一 <https://admin.protection.outlook.com/ecp/> () 角色： [](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="7a90f-476">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center (<https://admin.protection.outlook.com/ecp/>) or [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell):</span></span>

  - <span data-ttu-id="7a90f-477">組織管理</span><span class="sxs-lookup"><span data-stu-id="7a90f-477">Organization Management</span></span>
  - <span data-ttu-id="7a90f-478">僅限檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="7a90f-478">View-Only Organization Management</span></span>
  - <span data-ttu-id="7a90f-479">僅限檢視收件者</span><span class="sxs-lookup"><span data-stu-id="7a90f-479">View-Only Recipients</span></span>
  - <span data-ttu-id="7a90f-480">合規性管理</span><span class="sxs-lookup"><span data-stu-id="7a90f-480">Compliance Management</span></span>

<span data-ttu-id="7a90f-481">若要深入了解角色和權限，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="7a90f-481">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="7a90f-482">安全性與合規性中心的權限</span><span class="sxs-lookup"><span data-stu-id="7a90f-482">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="7a90f-483">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="7a90f-483">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="7a90f-484">威脅管理與即時偵測之間的差異</span><span class="sxs-lookup"><span data-stu-id="7a90f-484">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="7a90f-485">即時 *偵測報告可在* Office 365 方案 1 的 Defender 中提供。</span><span class="sxs-lookup"><span data-stu-id="7a90f-485">The *Real-time detections* report is available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="7a90f-486">*威脅總* 管位於 Office 365 方案 2 的 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="7a90f-486">*Threat Explorer* is available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="7a90f-487">即時偵測報告可讓您即時查看偵測。</span><span class="sxs-lookup"><span data-stu-id="7a90f-487">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="7a90f-488">威脅管也會執行這項功能，但也提供特定攻擊的額外詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7a90f-488">Threat Explorer does this as well, but it also provides additional details for a given attack.</span></span>
- <span data-ttu-id="7a90f-489">在 *威脅管* 中提供所有電子郵件的查看，但即時偵測報告則沒有提供。</span><span class="sxs-lookup"><span data-stu-id="7a90f-489">An *All email* view is available in Threat Explorer but not in the Real-time detections report.</span></span>
- <span data-ttu-id="7a90f-490">威脅管中包含更多篩選功能和可用的動作。</span><span class="sxs-lookup"><span data-stu-id="7a90f-490">More filtering capabilities and available actions are included in Threat Explorer.</span></span> <span data-ttu-id="7a90f-491">詳細資訊請參閱 Office [365 服務描述的 Microsoft Defender：Office 365 方案之 Defender 的功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="7a90f-491">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>
