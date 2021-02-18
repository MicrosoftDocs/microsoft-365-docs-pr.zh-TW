---
title: 威脅瀏覽器和即時偵測
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
description: 在安全性與合規性中心使用 Explorer 和即時偵測， &amp; 以有效地調查和回應威脅。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: daa7b4014d1302743578d79c2e1e0e1d2d5ac61f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288894"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="186e1-103">威脅瀏覽器和即時偵測</span><span class="sxs-lookup"><span data-stu-id="186e1-103">Threat Explorer and Real-time detections</span></span>


<span data-ttu-id="186e1-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="186e1-104">**Applies to**</span></span>
- [<span data-ttu-id="186e1-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="186e1-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="186e1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="186e1-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="186e1-107">如果您的組織有 [Microsoft Defender For Office 365](office-365-atp.md)，而您具有 [必要的許可權](#required-licenses-and-permissions)，則您 **的 Explorer** 或 **即時** 偵測 (以前的 *即時報告* -- [請參閱](#new-features-in-threat-explorer-and-real-time-detections)最近更新！ ) 。</span><span class="sxs-lookup"><span data-stu-id="186e1-107">If your organization has [Microsoft Defender for Office 365](office-365-atp.md), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **Real-time detections** (formerly *Real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="186e1-108">在 [安全性 & 規範中心] 中，移至 [ **威脅管理**]，然後選擇 [ **Explorer** ] _或_[ **即時** 偵測]。</span><span class="sxs-lookup"><span data-stu-id="186e1-108">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>


|<span data-ttu-id="186e1-109">使用 Microsoft Defender for Office 365 方案2，您會看到：</span><span class="sxs-lookup"><span data-stu-id="186e1-109">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="186e1-110">使用 Microsoft Defender for Office 365 方案1，您會看到：</span><span class="sxs-lookup"><span data-stu-id="186e1-110">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![威脅總管](../../media/threatmgmt-explorer.png)|![即時偵測](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="186e1-113">瀏覽器或即時偵測可協助您的安全性作業小組調查並有效地回應威脅。</span><span class="sxs-lookup"><span data-stu-id="186e1-113">Explorer or Real-time detections helps your security operations team investigate and respond to threats efficiently.</span></span> <span data-ttu-id="186e1-114">報告類似下列影像：</span><span class="sxs-lookup"><span data-stu-id="186e1-114">The report resembles the following image:</span></span>

![移至威脅管理 \> 總管](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="186e1-116">您可以使用此報告：</span><span class="sxs-lookup"><span data-stu-id="186e1-116">With this report, you can:</span></span>

- [<span data-ttu-id="186e1-117">查看 Microsoft 365 的安全性功能偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="186e1-117">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- <span data-ttu-id="186e1-118">[查看網路釣魚 URL，然後按一下 [已判定資料]](#view-phishing-url-and-click-verdict-data)</span><span class="sxs-lookup"><span data-stu-id="186e1-118">[View phishing URL and click verdict data](#view-phishing-url-and-click-verdict-data)</span></span>
- <span data-ttu-id="186e1-119">[從瀏覽器中的視圖開始自動調查和回應](#start-automated-investigation-and-response) 程式 (Office 365 的 Defender for Office 方案 2) </span><span class="sxs-lookup"><span data-stu-id="186e1-119">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (Defender for Office 365 Plan 2 only)</span></span>
- [<span data-ttu-id="186e1-120">調查惡意電子郵件及其他</span><span class="sxs-lookup"><span data-stu-id="186e1-120">Investigate malicious email, and more</span></span>](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-explorer-and-real-time-detections"></a><span data-ttu-id="186e1-121">威脅瀏覽器和即時偵測的增強功能</span><span class="sxs-lookup"><span data-stu-id="186e1-121">Improvements to Threat Explorer and Real-time detections</span></span>

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="186e1-122">威脅瀏覽器中的標記</span><span class="sxs-lookup"><span data-stu-id="186e1-122">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="186e1-123">使用者標記功能是在 *預覽* 中，並非所有人都可以使用，而且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="186e1-123">The user tags feature is in *Preview*, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="186e1-124">如需發行排程的相關資訊，請參閱 Microsoft 365 藍圖。</span><span class="sxs-lookup"><span data-stu-id="186e1-124">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="186e1-125">使用者標記識別 Microsoft Defender for Office 365 中的特定使用者群組。</span><span class="sxs-lookup"><span data-stu-id="186e1-125">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="186e1-126">如需標記的相關資訊（包括授權和設定），請參閱 [User tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="186e1-126">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="186e1-127">在威脅瀏覽器中，您可以在下列體驗中看到使用者標記的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="186e1-127">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="186e1-128">電子郵件格線視圖</span><span class="sxs-lookup"><span data-stu-id="186e1-128">Email grid view</span></span>

<span data-ttu-id="186e1-129">電子郵件窗格中的 [ **標記** ] 欄包含已套用至寄件者或收件者信箱的所有標記。</span><span class="sxs-lookup"><span data-stu-id="186e1-129">The **Tags** column in the email grid contains all the tags that have been applied to the sender or recipient mailboxes.</span></span> <span data-ttu-id="186e1-130">依預設，會先顯示「優先順序」帳戶之類的系統標記。</span><span class="sxs-lookup"><span data-stu-id="186e1-130">By default, system tags like priority accounts are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-131">![在電子郵件格線視圖中篩選標記](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-131">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="186e1-132">篩選</span><span class="sxs-lookup"><span data-stu-id="186e1-132">Filtering</span></span>

<span data-ttu-id="186e1-133">您可以使用標記做為篩選。</span><span class="sxs-lookup"><span data-stu-id="186e1-133">You can use tags as a filter.</span></span> <span data-ttu-id="186e1-134">只需在優先順序帳戶或特定使用者標記案例中尋找。</span><span class="sxs-lookup"><span data-stu-id="186e1-134">Hunt just across priority accounts or specific user tags scenarios.</span></span> <span data-ttu-id="186e1-135">您也可以排除包含某些標記的結果。</span><span class="sxs-lookup"><span data-stu-id="186e1-135">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="186e1-136">將此功能與其他篩選器結合，以縮小您的調查範圍。</span><span class="sxs-lookup"><span data-stu-id="186e1-136">Combine this functionality with other filters to narrow your scope of investigation.</span></span>

<span data-ttu-id="186e1-137">[![篩選標記](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="186e1-137">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-138">![不篩選標記](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-138">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="186e1-139">電子郵件詳細資料快顯視窗</span><span class="sxs-lookup"><span data-stu-id="186e1-139">Email detail flyout</span></span>
<span data-ttu-id="186e1-140">若要查看寄件者和收件者的個別標記，請選取 [主旨] 以開啟 [郵件詳細資料] 浮出。</span><span class="sxs-lookup"><span data-stu-id="186e1-140">To view the individual tags for sender and recipient, select the subject to open the message details flyout.</span></span> <span data-ttu-id="186e1-141">在 [ **摘要** ] 索引標籤上，[寄件者] 和 [收件者] 標記會分開顯示（如果它們是針對電子郵件）</span><span class="sxs-lookup"><span data-stu-id="186e1-141">On the **Summary** tab, the sender and recipient tags are shown separately, if they're present for an email.</span></span>
<span data-ttu-id="186e1-142">寄件者和收件者個別標記的相關資訊也會延伸至匯出的 CSV 資料，您可以在兩個不同的欄中查看這些詳細資料。</span><span class="sxs-lookup"><span data-stu-id="186e1-142">The information about individual tags for sender and recipient also extends to exported CSV data, where you can see these details in two separate columns.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-143">![電子郵件詳細資料標記](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-143">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="186e1-144">標記資訊也會顯示在 URL 中按一下 [飛入]。</span><span class="sxs-lookup"><span data-stu-id="186e1-144">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="186e1-145">若要查看，請移至 [網路釣魚] 或 [所有電子郵件] 視圖，然後按一下 [ **URLs** ] 或 [URL] [ **按一下** ]選取個別的 [URL] 浮出視窗，以查看有關該 URL 之按一下的其他詳細資料，包括與該按一下關聯的標記。</span><span class="sxs-lookup"><span data-stu-id="186e1-145">To view it, go to Phish or All Email view and then to the **URLs** or **URL Clicks** tab. Select an individual URL flyout to view additional details about clicks for that URL, including tags associated with that click.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-146">![URL 標記](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-146">![URL tags](../../media/tags-urls.png)</span></span>

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a><span data-ttu-id="186e1-147">對即將推出之威脅搜尋體驗的增強 () </span><span class="sxs-lookup"><span data-stu-id="186e1-147">Improvements to the threat hunting experience (upcoming)</span></span>

### <a name="updated-threat-information-for-emails"></a><span data-ttu-id="186e1-148">更新的電子郵件威脅資訊</span><span class="sxs-lookup"><span data-stu-id="186e1-148">Updated threat information for emails</span></span>

<span data-ttu-id="186e1-149">我們已著重于平臺和資料品質改進，以提升電子郵件記錄的資料準確性和一致性。</span><span class="sxs-lookup"><span data-stu-id="186e1-149">We've focused on platform and data-quality improvements to increase data accuracy and consistency for email records.</span></span> <span data-ttu-id="186e1-150">增強功能包括將預先傳遞和交付後資訊的整合，例如，將電子郵件上執行的動作當做處理成單一記錄。</span><span class="sxs-lookup"><span data-stu-id="186e1-150">Improvements include consolidation of pre-delivery and post-delivery information, such as actions executed on an email as part of the ZAP process, into a single record.</span></span> <span data-ttu-id="186e1-151">其他詳細資料，例如垃圾郵件決定、實體層級威脅 (例如，哪些 URL 為惡意) ，以及最近的傳遞位置也包含在內。</span><span class="sxs-lookup"><span data-stu-id="186e1-151">Additional details like spam verdict, entity-level threats (for example, which URL was malicious), and latest delivery locations are also included.</span></span>

<span data-ttu-id="186e1-152">在這些更新後，不論會影響郵件的不同傳遞事件為何，您都會看到每一封郵件的單一專案。</span><span class="sxs-lookup"><span data-stu-id="186e1-152">After these updates, you'll see a single entry for each message, regardless of the different post-delivery events that affect the message.</span></span> <span data-ttu-id="186e1-153">動作可包含 ZAP、手動修正 (，這表示系統管理動作) 、動態傳遞等等。</span><span class="sxs-lookup"><span data-stu-id="186e1-153">Actions can include ZAP, manual remediation (which means admin action), dynamic delivery, and so on.</span></span>

<span data-ttu-id="186e1-154">除了顯示惡意程式碼和網路釣魚威脅之外，您還會看到與電子郵件相關聯的垃圾郵件結論。</span><span class="sxs-lookup"><span data-stu-id="186e1-154">In addition to showing malware and phishing threats, you see the spam verdict associated with an email.</span></span> <span data-ttu-id="186e1-155">在電子郵件內，查看與電子郵件相關的所有威脅，以及對應的偵測技術。</span><span class="sxs-lookup"><span data-stu-id="186e1-155">Within the email, see all the threats associated with the email along with the corresponding detection technologies.</span></span> <span data-ttu-id="186e1-156">電子郵件可以有零個、一或多個威脅。</span><span class="sxs-lookup"><span data-stu-id="186e1-156">An email can have zero, one, or multiple threats.</span></span> <span data-ttu-id="186e1-157">您會在 [電子郵件] 浮出控制項的 [ **詳細資料** ] 區段中看到目前的威脅。</span><span class="sxs-lookup"><span data-stu-id="186e1-157">You'll see the current threats in the **Details** section of the email flyout.</span></span> <span data-ttu-id="186e1-158">針對多種威脅 (例如惡意程式碼和網路釣魚) ，「 **偵測技術** 」欄位會顯示威脅偵測對應，也就是識別威脅的偵測技術。</span><span class="sxs-lookup"><span data-stu-id="186e1-158">For multiple threats (such as malware and phishing), the **Detection tech** field shows the threat-detection mapping, which is the detection technology that identified the threat.</span></span>

<span data-ttu-id="186e1-159">一組偵測技術現在包含新的偵測方法，也包含垃圾郵件偵測技術。</span><span class="sxs-lookup"><span data-stu-id="186e1-159">The set of detection technologies now includes new detection methods, as well as spam-detection technologies.</span></span> <span data-ttu-id="186e1-160">您可以使用相同的偵測技術集合，在不同的電子郵件視圖中篩選結果， (惡意程式碼、網路釣魚程式、所有電子郵件) 。</span><span class="sxs-lookup"><span data-stu-id="186e1-160">You can use the same set of detection technologies to filter the results across the different email views (Malware, Phish, All Email).</span></span>

> [!NOTE]
> <span data-ttu-id="186e1-161">判定分析可能不一定要與實體關聯。</span><span class="sxs-lookup"><span data-stu-id="186e1-161">Verdict analysis might not necessarily be tied to entities.</span></span> <span data-ttu-id="186e1-162">舉例來說，電子郵件可能會分類為網路釣魚或垃圾郵件，但沒有以網路釣魚/垃圾郵件判定的 URLs。</span><span class="sxs-lookup"><span data-stu-id="186e1-162">As an example, an email might be classified as phish or spam, but there are no URLs that are stamped with a phish/spam verdict.</span></span> <span data-ttu-id="186e1-163">這是因為篩選器也會在指派判定之前，評估電子郵件的內容和其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="186e1-163">This is because the filters also evaluate content and other details for an email before assigning a verdict.</span></span>

#### <a name="threats-in-urls"></a><span data-ttu-id="186e1-164">URLs 中的威脅</span><span class="sxs-lookup"><span data-stu-id="186e1-164">Threats in URLs</span></span>

<span data-ttu-id="186e1-165">您現在可以在 [電子郵件彈出 **詳細資料** ] 索引標籤上看到 URL 的特定威脅。威脅可能是 *惡意* 代碼、 *網路釣魚*、 *垃圾郵件* 或 *無*。 ) </span><span class="sxs-lookup"><span data-stu-id="186e1-165">You can now see the specific threat for a URL on the email flyout **Details** tab. The threat can be *malware*, *phish*, *spam*, or *none*.)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-166">![URL 威脅](../../media/URL_Threats.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-166">![URL threats](../../media/URL_Threats.png)</span></span>

### <a name="updated-timeline-view-upcoming"></a><span data-ttu-id="186e1-167"> (即將開始的時程表視圖更新) </span><span class="sxs-lookup"><span data-stu-id="186e1-167">Updated timeline view (upcoming)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-168">![更新時程表視圖](../../media/Email_Timeline.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-168">![Updated Timeline View](../../media/Email_Timeline.png)</span></span>

<span data-ttu-id="186e1-169">時程表視圖會識別所有傳遞和傳遞投遞事件。</span><span class="sxs-lookup"><span data-stu-id="186e1-169">Timeline view identifies all delivery and post-delivery events.</span></span> <span data-ttu-id="186e1-170">它包含針對這些事件子集在該時間點所識別之威脅的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="186e1-170">It includes information about the threat identified at that point of time for a subset of these events.</span></span> <span data-ttu-id="186e1-171">時程表視圖也提供有關 (執行的任何其他動作（如 ZAP 或手動修正) ）的相關資訊，以及該動作的結果。</span><span class="sxs-lookup"><span data-stu-id="186e1-171">Timeline view also provides information about any additional action taken (such as ZAP or manual remediation), along with the result of that action.</span></span> <span data-ttu-id="186e1-172">時程表視圖資訊包含：</span><span class="sxs-lookup"><span data-stu-id="186e1-172">Timeline view information includes:</span></span>

- <span data-ttu-id="186e1-173">**來源：** 事件的來源。</span><span class="sxs-lookup"><span data-stu-id="186e1-173">**Source:** Source of the event.</span></span> <span data-ttu-id="186e1-174">可以是 admin/system/user。</span><span class="sxs-lookup"><span data-stu-id="186e1-174">It can be admin/system/user.</span></span>
- <span data-ttu-id="186e1-175">**事件：** 包含最上層的事件，例如原始傳遞、手動修復、ZAP、報送及動態傳遞。</span><span class="sxs-lookup"><span data-stu-id="186e1-175">**Event:** Includes top-level events like original delivery, manual remediation, ZAP, submissions, and dynamic delivery.</span></span>
- <span data-ttu-id="186e1-176">**動作：** 做為 ZAP 或 admin 動作一部分所採取的特定動作 (例如，soft delete) 。</span><span class="sxs-lookup"><span data-stu-id="186e1-176">**Action:** The specific action that was taken either as part of ZAP or admin action (for example, soft delete).</span></span>
- <span data-ttu-id="186e1-177">**威脅：** 涵蓋該時間點所識別的威脅 (惡意程式碼、網路釣魚和垃圾郵件) 。</span><span class="sxs-lookup"><span data-stu-id="186e1-177">**Threats:** Covers the threats (malware, phish, spam) identified at that point of time.</span></span>
- <span data-ttu-id="186e1-178">**結果/詳細資料：** 有關動作結果的詳細資訊，例如是否以 ZAP/系統管理動作的一部分執行。</span><span class="sxs-lookup"><span data-stu-id="186e1-178">**Result/Details:** More information about the result of the action, such as whether it was performed as part of ZAP/admin action.</span></span>

### <a name="original-and-latest-delivery-location"></a><span data-ttu-id="186e1-179">原始及最近的傳遞位置</span><span class="sxs-lookup"><span data-stu-id="186e1-179">Original and latest delivery location</span></span>

<span data-ttu-id="186e1-180">目前，我們在電子郵件格線和電子郵件飛入位置中呈現的方式。</span><span class="sxs-lookup"><span data-stu-id="186e1-180">Currently, we surface delivery location in the email grid and email flyout.</span></span> <span data-ttu-id="186e1-181">[**傳遞位置**] 欄位取得 [重新命名 **_原始傳遞位置_]*。我們正在引進另一個欄位，_*_最新的傳遞位置_**。</span><span class="sxs-lookup"><span data-stu-id="186e1-181">The **Delivery location** field is getting renamed **_Original delivery location_*_. And we're introducing another field, _*_Latest delivery location_**.</span></span>

<span data-ttu-id="186e1-182">**原始傳遞位置** 將會提供有關電子郵件最初傳遞位置的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="186e1-182">**Original delivery location** will give more information about where an email was delivered initially.</span></span> <span data-ttu-id="186e1-183">**最新的傳遞位置** 會在系統動作（如 *ZAP* 或系統動作）之後的電子郵件進入，例如 *移至 [刪除的專案*]。</span><span class="sxs-lookup"><span data-stu-id="186e1-183">**Latest delivery location** will state where an email landed after system actions like *ZAP* or admin actions like *Move to deleted items*.</span></span> <span data-ttu-id="186e1-184">最新的傳遞位置是用來告訴系統管理員郵件的最後一個已知位置後置或任何系統/系統管理員動作。</span><span class="sxs-lookup"><span data-stu-id="186e1-184">Latest delivery location is intended to tell admins the message's last-known location post-delivery or any system/admin actions.</span></span> <span data-ttu-id="186e1-185">它不會包含電子郵件上的任何使用者動作。</span><span class="sxs-lookup"><span data-stu-id="186e1-185">It doesn't include any end-user actions on the email.</span></span> <span data-ttu-id="186e1-186">例如，如果使用者刪除郵件或將郵件移至封存/pst，則不會更新郵件的 [傳遞] 位置。</span><span class="sxs-lookup"><span data-stu-id="186e1-186">For example, if a user deleted a message or moved the message to archive/pst, the message "delivery" location won't be updated.</span></span> <span data-ttu-id="186e1-187">不過，如果系統動作更新了位置 (例如，ZAP 產生的電子郵件移至隔離) 中，則 **最新的傳遞位置** 會顯示為「隔離」。</span><span class="sxs-lookup"><span data-stu-id="186e1-187">But if a system action updated the location (for example, ZAP resulting in an email moving to quarantine), **Latest delivery location** would show as "quarantine."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-188">![更新的傳遞位置](../../media/Updated_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-188">![Updated delivery locations](../../media/Updated_Delivery_Location.png)</span></span>

> [!NOTE]
> <span data-ttu-id="186e1-189">在某些情況下， **傳送位置** 和 **傳遞動作** 可能會顯示為「未知」：</span><span class="sxs-lookup"><span data-stu-id="186e1-189">There are a few cases where **Delivery location** and **Delivery action** may show as "unknown":</span></span>
>
> - <span data-ttu-id="186e1-190">如果郵件已傳遞，您可能 **會看到 [** 已傳遞] 和 [送達] **位置** 為 "Unknown"，但是收件匣規則會將郵件移至預設資料夾 (例如草稿或封存) ，而不是 [收件匣] 或 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="186e1-190">You might see **Delivery location** as "delivered" and **Delivery location** as "unknown" if the message was delivered, but an Inbox rule moved the message to a default folder (such as Draft or Archive) instead of to the Inbox or Junk Email folder.</span></span>
>
> - <span data-ttu-id="186e1-191">如果已嘗試使用系統管理員/系統動作 (（例如 ZAP) ），但找不到該郵件，則 **最新的傳遞位置** 可能是未知的。</span><span class="sxs-lookup"><span data-stu-id="186e1-191">**Latest delivery location** can be unknown if an admin/system action (such as ZAP) was attempted, but the message wasn't found.</span></span> <span data-ttu-id="186e1-192">通常動作會在使用者移動或刪除郵件之後發生。</span><span class="sxs-lookup"><span data-stu-id="186e1-192">Typically, the action happens after the user  moved or deleted the message.</span></span> <span data-ttu-id="186e1-193">在這種情況下，請在時程表視圖中驗證 [ **結果/詳細資料** ] 欄位。</span><span class="sxs-lookup"><span data-stu-id="186e1-193">In such cases, verify the **Result/Details** column in timeline view.</span></span> <span data-ttu-id="186e1-194">尋找 [使用者已移動或刪除的郵件] 語句。</span><span class="sxs-lookup"><span data-stu-id="186e1-194">Look for the statement "Message moved or deleted by the user."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-195">![時程表的傳遞位置](../../media/Updated_Timeline_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-195">![Delivery locations for timeline](../../media/Updated_Timeline_Delivery_Location.png)</span></span>

### <a name="additional-actions"></a><span data-ttu-id="186e1-196">其他動作</span><span class="sxs-lookup"><span data-stu-id="186e1-196">Additional actions</span></span>

<span data-ttu-id="186e1-197">在傳送電子郵件之後套用 *其他動作*。</span><span class="sxs-lookup"><span data-stu-id="186e1-197">*Additional actions* were applied after delivery of the email.</span></span> <span data-ttu-id="186e1-198">它們可以包含由系統管理員採取的 *ZAP*、 *手動修正* (動作（如虛刪除) 、 *動態傳遞*） *，以及重新處理 (（* 已偵測為良好) 的電子郵件）。</span><span class="sxs-lookup"><span data-stu-id="186e1-198">They can include *ZAP*, *manual remediation* (action taken by an Admin such as soft delete), *dynamic delivery*, and *reprocessed* (for an email that was retroactively detected as good).</span></span>

> [!NOTE]
> - <span data-ttu-id="186e1-199">在擱置中的變更中，目前出現在 [傳遞動作篩選] 中的「已移除的 ZAP」值將會不復存在。</span><span class="sxs-lookup"><span data-stu-id="186e1-199">As part of the pending changes, the "Removed by ZAP" value currently surfaced in the Delivery Action filter is going away.</span></span> <span data-ttu-id="186e1-200">您可以使用此方法，透過 **其他動作** 來搜尋所有 ZAP 嘗試的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="186e1-200">You'll have a way to search for all email with the ZAP attempt through **Additional actions**.</span></span>
>
> - <span data-ttu-id="186e1-201">**偵測技術** 和 **其他動作** 會有新的欄位和值，尤其是針對 ZAP 案例) 所做的 (。</span><span class="sxs-lookup"><span data-stu-id="186e1-201">There will be new fields and values for **Detection technologies** and **Additional actions** (especially for ZAP scenarios).</span></span> <span data-ttu-id="186e1-202">您將需要評估現有的已儲存查詢和追蹤的查詢，以確保它們能夠使用新的值。</span><span class="sxs-lookup"><span data-stu-id="186e1-202">You'll need to evaluate your existing saved queries and tracked queries to make sure they work with the new values.</span></span>

> [!div class="mx-imgBorder"]

> ![瀏覽器中的其他動作](../../media/Additional_Actions.png)

### <a name="system-overrides"></a><span data-ttu-id="186e1-204">系統覆寫</span><span class="sxs-lookup"><span data-stu-id="186e1-204">System overrides</span></span>

<span data-ttu-id="186e1-205">*系統覆寫* 可讓您對郵件的預定送達位置產生例外狀況。</span><span class="sxs-lookup"><span data-stu-id="186e1-205">*System overrides* enable you to make exceptions to the intended delivery location of a message.</span></span> <span data-ttu-id="186e1-206">您可以根據威脅及篩選堆疊所識別的其他偵測，覆寫系統所提供的傳遞位置。</span><span class="sxs-lookup"><span data-stu-id="186e1-206">You override the delivery location provided by the system, based on the threats and other detections identified by the filtering stack.</span></span> <span data-ttu-id="186e1-207">系統覆寫可透過租使用者或使用者原則加以設定，以依照原則所建議的方式傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="186e1-207">System overrides can be set through tenant or user policy to deliver the message as suggested by the policy.</span></span> <span data-ttu-id="186e1-208">覆寫可識別因設定缺口而無意間傳遞的惡意郵件，例如使用者設定的過於廣泛的安全寄件者原則。</span><span class="sxs-lookup"><span data-stu-id="186e1-208">Overrides can identify unintentional delivery of malicious messages due to configurations gaps, such as an overly broad Safe Sender policy set by a user.</span></span> <span data-ttu-id="186e1-209">這些覆寫值可以是：</span><span class="sxs-lookup"><span data-stu-id="186e1-209">These override values can be:</span></span>

- <span data-ttu-id="186e1-210">使用者原則允許：使用者在信箱層級建立原則，以允許網域或寄件者。</span><span class="sxs-lookup"><span data-stu-id="186e1-210">Allowed by user policy: A user creates policies at the mailbox level to allows domains or senders.</span></span>
- <span data-ttu-id="186e1-211">使用者原則封鎖：使用者會在信箱層級建立原則，以封鎖網域或寄件者。</span><span class="sxs-lookup"><span data-stu-id="186e1-211">Blocked by user policy: A user creates policies at the mail box level to block domains or senders.</span></span>
- <span data-ttu-id="186e1-212">組織原則允許：組織的安全小組設定原則或 Exchange 郵件流程規則 (也稱為傳輸規則) ，可允許寄件者和網域的組織中的使用者。</span><span class="sxs-lookup"><span data-stu-id="186e1-212">Allowed by org policy: The organization's security teams set policies or Exchange mail flow rules (also known as transport rules) to allow senders and domains for users in their organization.</span></span> <span data-ttu-id="186e1-213">這可供一組使用者或整個組織使用。</span><span class="sxs-lookup"><span data-stu-id="186e1-213">This can be for a set of users or the entire organization.</span></span>
- <span data-ttu-id="186e1-214">由組織原則封鎖：組織的安全小組會設定原則或郵件流程規則，以封鎖組織中使用者的寄件者、網域、郵件語言或來源 Ip。</span><span class="sxs-lookup"><span data-stu-id="186e1-214">Blocked by org policy: The organization's security teams set policies or mail flow rules to block senders, domains, message languages, or source IPs for users in their organization.</span></span> <span data-ttu-id="186e1-215">這可以套用到一組使用者或整個組織。</span><span class="sxs-lookup"><span data-stu-id="186e1-215">This can be applied to a set of users or the entire organization.</span></span>
- <span data-ttu-id="186e1-216">組織原則封鎖的檔案副檔名：組織的安全性小組會透過反惡意程式碼原則設定封鎖副檔名。</span><span class="sxs-lookup"><span data-stu-id="186e1-216">File extension blocked by org policy: An organization's security team blocks a file name extension through the anti-malware policy settings.</span></span> <span data-ttu-id="186e1-217">這些值現在會顯示在電子郵件詳細資料中，以協助調查。</span><span class="sxs-lookup"><span data-stu-id="186e1-217">These values will now be displayed in email details to help with investigations.</span></span> <span data-ttu-id="186e1-218">Secops 小組也可以使用 rtf 篩選功能來篩選封鎖的副檔名。</span><span class="sxs-lookup"><span data-stu-id="186e1-218">Secops teams can also use the rich-filtering capability to filter on blocked file extensions.</span></span>

<span data-ttu-id="186e1-219">[![瀏覽器中的系統覆寫](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="186e1-219">[![System Overrides in Explorer](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-220">![瀏覽器中的系統覆寫格線](../../media/System_Overrides_Grid.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-220">![System Overrides Grid in Explorer](../../media/System_Overrides_Grid.png)</span></span>

### <a name="improvements-for-the-url-and-clicks-experience"></a><span data-ttu-id="186e1-221">URL 及點擊體驗的增強功能</span><span class="sxs-lookup"><span data-stu-id="186e1-221">Improvements for the URL and clicks experience</span></span>

<span data-ttu-id="186e1-222">改進功能包括：</span><span class="sxs-lookup"><span data-stu-id="186e1-222">The improvements include:</span></span>

- <span data-ttu-id="186e1-223">顯示已完全按一下的 URL (包括 url 任何部分之 URL 的任何查詢參數) 在 URL 快顯視窗的 [ **點擊** ] 區段中。</span><span class="sxs-lookup"><span data-stu-id="186e1-223">Show the full clicked URL (including any query parameters that are part of the URL) in the **Clicks** section of the URL flyout.</span></span> <span data-ttu-id="186e1-224">目前，URL 網域和路徑會出現在標題列中。</span><span class="sxs-lookup"><span data-stu-id="186e1-224">Currently, the URL domain and path appear in the title bar.</span></span> <span data-ttu-id="186e1-225">我們正在擴充該資訊以顯示完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="186e1-225">We're extending that information to show the full URL.</span></span>

- <span data-ttu-id="186e1-226">跨 URL 篩選器的修正 (*url* 與 *url 網域* *，以及 url 網域和路徑*) ：更新會影響包含 URL/按一下判定之郵件的搜尋。</span><span class="sxs-lookup"><span data-stu-id="186e1-226">Fixes across URL filters (*URL* versus *URL domain* versus *URL domain and path*): The updates affect searching for messages that contain a URL/click verdict.</span></span> <span data-ttu-id="186e1-227">我們為通訊協定不可知的搜尋啟用支援，因此您可以在不使用的情況下搜尋 URL `http` 。</span><span class="sxs-lookup"><span data-stu-id="186e1-227">We enabled support for protocol-agnostic searches, so you can search for a URL without using `http`.</span></span> <span data-ttu-id="186e1-228">根據預設，URL 搜尋會對應至 HTTP，除非明確指定另一個值。</span><span class="sxs-lookup"><span data-stu-id="186e1-228">By default, the URL search maps to http, unless another value is explicitly specified.</span></span> <span data-ttu-id="186e1-229">例如：</span><span class="sxs-lookup"><span data-stu-id="186e1-229">For example:</span></span>

   -  <span data-ttu-id="186e1-230">`http://`在 [ **url**]、[ **url 網域**] 及 [ **url 網域] 和 [路徑** 篩選] 欄位中，使用或不使用前置詞進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="186e1-230">Search with and without the `http://` prefix in the **URL**, **URL Domain**, and **URL Domain and Path** filter fields.</span></span> <span data-ttu-id="186e1-231">搜尋應該會顯示相同的結果。</span><span class="sxs-lookup"><span data-stu-id="186e1-231">The searches should show the same results.</span></span>

   -  <span data-ttu-id="186e1-232">`https://`在 **URL** 中搜尋前置詞。</span><span class="sxs-lookup"><span data-stu-id="186e1-232">Search for the `https://` prefix in **URL**.</span></span> <span data-ttu-id="186e1-233">若未指定任何值，則 `http://` 會假設首碼。</span><span class="sxs-lookup"><span data-stu-id="186e1-233">When no value is specified, the `http://` prefix is assumed.</span></span>

   - <span data-ttu-id="186e1-234">`/` 會在 **url 路徑**、 **url 網域**、 **URL 網域及路徑** 欄位的開頭和結尾略過。</span><span class="sxs-lookup"><span data-stu-id="186e1-234">`/` is ignored at the beginning and end of the **URL path**, **URL Domain**, **URL domain and path** fields.</span></span> <span data-ttu-id="186e1-235">`/` 在 [ **URL** ] 欄位的結尾會被忽略。</span><span class="sxs-lookup"><span data-stu-id="186e1-235">`/` at the end of the **URL** field is ignored.</span></span>

### <a name="phish-confidence-level"></a><span data-ttu-id="186e1-236">網路釣魚信賴等級</span><span class="sxs-lookup"><span data-stu-id="186e1-236">Phish confidence level</span></span>

<span data-ttu-id="186e1-237">網路釣魚信賴等級可協助識別將電子郵件分類為 "網路釣魚" 的置信度。</span><span class="sxs-lookup"><span data-stu-id="186e1-237">Phish confidence level helps identify the degree of confidence with which an email was categorized as "phish."</span></span> <span data-ttu-id="186e1-238">這兩個可能的值為 *High* 和 *Normal*。</span><span class="sxs-lookup"><span data-stu-id="186e1-238">The two possible values are *High* and *Normal*.</span></span> <span data-ttu-id="186e1-239">在初始階段中，此篩選器只會在威脅瀏覽器的網路釣魚視圖中使用。</span><span class="sxs-lookup"><span data-stu-id="186e1-239">In the initial stages, this filter will be available only in the Phish view of Threat Explorer.</span></span>

<span data-ttu-id="186e1-240">[![瀏覽器中的網路釣魚信賴等級](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="186e1-240">[![Phish Confidence Level in Explorer](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span></span>

### <a name="zap-url-signal"></a><span data-ttu-id="186e1-241">ZAP URL 信號</span><span class="sxs-lookup"><span data-stu-id="186e1-241">ZAP URL signal</span></span>

<span data-ttu-id="186e1-242">ZAP URL 信號通常用於 ZAP 網路釣魚警示案例，其中的電子郵件已識別為網路釣魚並在傳遞後移除。</span><span class="sxs-lookup"><span data-stu-id="186e1-242">The ZAP URL signal is typically used for ZAP Phish alert scenarios where an email was identified as Phish and removed after delivery.</span></span> <span data-ttu-id="186e1-243">此信號會在瀏覽器中使用對應的結果來連接警示。</span><span class="sxs-lookup"><span data-stu-id="186e1-243">This signal connects the alert with the corresponding results in Explorer.</span></span> <span data-ttu-id="186e1-244">這是警示的其中一個 IOCs。</span><span class="sxs-lookup"><span data-stu-id="186e1-244">It's one of the IOCs for the alert.</span></span>

<span data-ttu-id="186e1-245">為了改進搜尋程式，我們已更新威脅瀏覽器和即時偵測，使搜尋體驗更為一致。</span><span class="sxs-lookup"><span data-stu-id="186e1-245">To improve the hunting process, we've updated Threat Explorer and Real-time detections to make the hunting experience more consistent.</span></span> <span data-ttu-id="186e1-246">這些變更如下所述：</span><span class="sxs-lookup"><span data-stu-id="186e1-246">The changes are outlined here:</span></span>

- [<span data-ttu-id="186e1-247">時區改進</span><span class="sxs-lookup"><span data-stu-id="186e1-247">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="186e1-248">重新整理程式中的更新</span><span class="sxs-lookup"><span data-stu-id="186e1-248">Update in the refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="186e1-249">新增至篩選的圖表深入分析</span><span class="sxs-lookup"><span data-stu-id="186e1-249">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="186e1-250">在產品資訊更新</span><span class="sxs-lookup"><span data-stu-id="186e1-250">In product information updates</span></span>](#in-product-information-updates)

### <a name="filter-by-user-tags"></a><span data-ttu-id="186e1-251">依使用者標記篩選</span><span class="sxs-lookup"><span data-stu-id="186e1-251">Filter by user tags</span></span>

<span data-ttu-id="186e1-252">您現在可以排序和篩選系統或自訂使用者標記，以快速抓住威脅的範圍。</span><span class="sxs-lookup"><span data-stu-id="186e1-252">You can now sort and filter on system or custom user tags to quickly grasp the scope of threats.</span></span> <span data-ttu-id="186e1-253">若要深入瞭解，請參閱 [使用者標記](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="186e1-253">To learn more, see [User tags](user-tags.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="186e1-254">依使用者標記篩選和排序目前是公開預覽。</span><span class="sxs-lookup"><span data-stu-id="186e1-254">Filtering and sorting by user tags is currently in public preview.</span></span> <span data-ttu-id="186e1-255">在正式發行之前，您可能會充分修改此功能。</span><span class="sxs-lookup"><span data-stu-id="186e1-255">This functionality may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="186e1-256">Microsoft 對本所提供的資訊不提供任何明示或默示的保證。</span><span class="sxs-lookup"><span data-stu-id="186e1-256">Microsoft makes no warranties, express or implied, with respect to the information provided about it.</span></span>

![瀏覽器中的標記欄](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a><span data-ttu-id="186e1-258">時區改進</span><span class="sxs-lookup"><span data-stu-id="186e1-258">Timezone improvements</span></span>

<span data-ttu-id="186e1-259">您會看到入口網站中的電子郵件記錄以及匯出資料的時區。</span><span class="sxs-lookup"><span data-stu-id="186e1-259">You'll see the time zone for the email records in the Portal as well as for Exported data.</span></span> <span data-ttu-id="186e1-260">透過電子郵件格線、[詳細資料] 飛出、電子郵件時程表及類似的電子郵件，它會在體驗上看到，所以結果集的時區也是清除的。</span><span class="sxs-lookup"><span data-stu-id="186e1-260">It will be visible across experiences like Email Grid, Details flyout, Email Timeline, and Similar Emails, so the time zone for the result set is clear.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-261">![在瀏覽器中查看時區](../../media/TimezoneImprovements.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-261">![View time zone in Explorer](../../media/TimezoneImprovements.png)</span></span>

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="186e1-262">重新整理程式中的更新</span><span class="sxs-lookup"><span data-stu-id="186e1-262">Update in the refresh process</span></span>

<span data-ttu-id="186e1-263">有些使用者對自動重新整理的混淆有批註 (例如，當您變更日期時，此頁面會立即重新整理) 和手動重新整理 (其他篩選) 。</span><span class="sxs-lookup"><span data-stu-id="186e1-263">Some users have commented about confusion with automatic refresh (for example, as soon as you change the date, the page refreshes) and manual refresh (for other filters).</span></span> <span data-ttu-id="186e1-264">同樣地，移除篩選器也會導致自動重新整理。</span><span class="sxs-lookup"><span data-stu-id="186e1-264">Similarly, removing filters leads to automatic refresh.</span></span> <span data-ttu-id="186e1-265">修改查詢時變更篩選可能會造成不一致的搜尋體驗。</span><span class="sxs-lookup"><span data-stu-id="186e1-265">Changing filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="186e1-266">若要解決這些問題，我們會移至手動篩選機制。</span><span class="sxs-lookup"><span data-stu-id="186e1-266">To resolve these issues, we're moving to a manual-filtering mechanism.</span></span>

<span data-ttu-id="186e1-267">從經驗的觀點來看，使用者可以從 [篩選器集和日期) 中，套用及移除不同的篩選範圍 (，然後選取 [重新整理] 按鈕，以在定義查詢之後篩選結果。</span><span class="sxs-lookup"><span data-stu-id="186e1-267">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set and date) and select the refresh button to filter the results after they've defined the query.</span></span> <span data-ttu-id="186e1-268">[重新整理] 按鈕現在也會在螢幕上強調。</span><span class="sxs-lookup"><span data-stu-id="186e1-268">The refresh button is also now emphasized on the screen.</span></span> <span data-ttu-id="186e1-269">我們也更新相關的工具提示及產品內檔。</span><span class="sxs-lookup"><span data-stu-id="186e1-269">We've also updated the related tooltips and in-product documentation.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-270">![選取 [重新整理] 以篩選結果](../../media/ManualRefresh.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-270">![Select Refresh to filter results](../../media/ManualRefresh.png)</span></span>

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="186e1-271">新增至篩選的圖表深入分析</span><span class="sxs-lookup"><span data-stu-id="186e1-271">Chart drilldown to add to filters</span></span>

<span data-ttu-id="186e1-272">您現在可以圖表圖例值新增為篩選器。</span><span class="sxs-lookup"><span data-stu-id="186e1-272">You can now chart legend values to add them as filters.</span></span> <span data-ttu-id="186e1-273">選取 [重新整理 **] 按鈕以** 篩選結果。</span><span class="sxs-lookup"><span data-stu-id="186e1-273">Select the **Refresh** button to filter the results.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-274">![深入查看圖表以進行篩選](../../media/ChartDrilldown.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-274">![Drill down through charts to Filter](../../media/ChartDrilldown.png)</span></span>

### <a name="in-product-information-updates"></a><span data-ttu-id="186e1-275">產品內資訊更新</span><span class="sxs-lookup"><span data-stu-id="186e1-275">In-product information updates</span></span>

<span data-ttu-id="186e1-276">產品內現在已提供其他詳細資料，例如格線內的搜尋結果總數 (請參閱) 。</span><span class="sxs-lookup"><span data-stu-id="186e1-276">Additional details are now available within the product, such as the total number of search results within the grid (see below).</span></span> <span data-ttu-id="186e1-277">我們已改進標籤、錯誤訊息及工具提示，以提供有關篩選、搜尋經驗及結果集的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="186e1-277">We've improved labels, error messages, and tooltips to provide more information about the filters, search experience, and result set.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-278">![View in 產品資訊](../../media/ProductInfo.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-278">![View in-product information](../../media/ProductInfo.png)</span></span>

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="186e1-279">威脅瀏覽器中的延伸功能</span><span class="sxs-lookup"><span data-stu-id="186e1-279">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="186e1-280">主要目標使用者</span><span class="sxs-lookup"><span data-stu-id="186e1-280">Top targeted users</span></span>

<span data-ttu-id="186e1-281">如今，我們會在惡意程式碼的 [ **主要惡意程式碼系列** ] 區段中，公開電子郵件的惡意程式碼視圖中主要目標使用者的清單。</span><span class="sxs-lookup"><span data-stu-id="186e1-281">Today we expose the list of the top targeted users in the Malware view for emails, in the **Top Malware Families** section.</span></span> <span data-ttu-id="186e1-282">我們也會在網路釣魚和所有電子郵件視圖中擴充此視圖。</span><span class="sxs-lookup"><span data-stu-id="186e1-282">We'll be extending this view in the Phish and All Email views as well.</span></span> <span data-ttu-id="186e1-283">您將可以查看前5位目標使用者，以及每位使用者對對應視圖的嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="186e1-283">You'll be able to see the top-five targeted users, along with the number of attempts for each user for the corresponding view.</span></span> <span data-ttu-id="186e1-284">例如，針對網路釣魚視圖，您會看到網路釣魚嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="186e1-284">For example, for Phish view, you'll see the number of Phish attempts.</span></span>

<span data-ttu-id="186e1-285">您可以將目標使用者的清單匯出至3000的限制，以及每個電子郵件 view 的離線分析嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="186e1-285">You'll be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="186e1-286">此外，選取 [嘗試次數] (例如，13在下一個影像嘗試) 會在威脅瀏覽器中開啟篩選的視圖，這樣您就能看到該使用者的電子郵件和威脅的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="186e1-286">In addition, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-287">![主要目標使用者](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-287">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="186e1-288">Exchange 傳輸規則</span><span class="sxs-lookup"><span data-stu-id="186e1-288">Exchange transport rules</span></span>

<span data-ttu-id="186e1-289">在 [資料豐富] 的一部分中，您將可以查看套用至郵件的所有不同 Exchange transport rules (ETR) 。</span><span class="sxs-lookup"><span data-stu-id="186e1-289">As part of data enrichment, you'll be able to see all the different Exchange transport rules (ETR) that were applied to a message.</span></span> <span data-ttu-id="186e1-290">此資訊將會出現在 [電子郵件格線] 視圖中。</span><span class="sxs-lookup"><span data-stu-id="186e1-290">This information will be available in the Email grid view.</span></span> <span data-ttu-id="186e1-291">若要進行查看，請選取格線中的 [ **欄選項** ]，然後從 [欄選項] 中 **新增 Exchange Transport Rule** 。</span><span class="sxs-lookup"><span data-stu-id="186e1-291">To view it,  select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="186e1-292">它也會顯示在電子郵件中的 [ **詳細資料** ] 快顯視窗中。</span><span class="sxs-lookup"><span data-stu-id="186e1-292">It will also be visible on the **Details** flyout in the email.</span></span>

<span data-ttu-id="186e1-293">您將能看到 GUID 及已套用至郵件的傳輸規則名稱。</span><span class="sxs-lookup"><span data-stu-id="186e1-293">You'll be able to see both the GUID and the name of the transport rules that were applied to the message.</span></span> <span data-ttu-id="186e1-294">您將能夠使用傳輸規則的名稱來搜尋郵件。</span><span class="sxs-lookup"><span data-stu-id="186e1-294">You'll be able to search for the messages by using the name of the transport rule.</span></span> <span data-ttu-id="186e1-295">這是「包含」搜尋，也就是您也可以進行部分搜尋。</span><span class="sxs-lookup"><span data-stu-id="186e1-295">This is a "Contains" search, which means you can do partial searches as well.</span></span>

#### <a name="important-note"></a><span data-ttu-id="186e1-296">重要注意事項：</span><span class="sxs-lookup"><span data-stu-id="186e1-296">Important note:</span></span>

<span data-ttu-id="186e1-297">ETR 搜尋和名稱可用性取決於指派給您的特定角色。</span><span class="sxs-lookup"><span data-stu-id="186e1-297">ETR search and name availability depend on the specific role that's assigned to you.</span></span> <span data-ttu-id="186e1-298">您必須具有下列其中一個角色/許可權，才能查看 ETR 名稱和搜尋。</span><span class="sxs-lookup"><span data-stu-id="186e1-298">You need to have one of the following roles/permissions to view the ETR names and search.</span></span> <span data-ttu-id="186e1-299">如果您未指派任何這些角色，您就無法看到傳輸規則的名稱，或使用 ETR 名稱來搜尋郵件。</span><span class="sxs-lookup"><span data-stu-id="186e1-299">If you don't have any of these roles assigned to you, you can't see the names of the transport rules or search for messages by using ETR names.</span></span> <span data-ttu-id="186e1-300">不過，您可以在電子郵件詳細資料中看到 ETR 標籤及 GUID 資訊。</span><span class="sxs-lookup"><span data-stu-id="186e1-300">However, you could see the ETR label and GUID information in the Email Details.</span></span> <span data-ttu-id="186e1-301">其他記錄流覽的電子郵件格線、電子郵件 flyouts、篩選和匯出不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="186e1-301">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>

- <span data-ttu-id="186e1-302">僅限 EXO-資料遺失防護：全部</span><span class="sxs-lookup"><span data-stu-id="186e1-302">EXO Only - Data Loss Prevention: All</span></span>
- <span data-ttu-id="186e1-303">僅限 EXO-O365SupportViewConfig： All</span><span class="sxs-lookup"><span data-stu-id="186e1-303">EXO Only - O365SupportViewConfig: All</span></span>
- <span data-ttu-id="186e1-304">Microsoft Azure Active Directory 或 EXO-安全性系統管理員： All</span><span class="sxs-lookup"><span data-stu-id="186e1-304">Microsoft Azure Active Directory or EXO - Security Admin: All</span></span>
- <span data-ttu-id="186e1-305">AAD 或 EXO-Security Reader： All</span><span class="sxs-lookup"><span data-stu-id="186e1-305">AAD or EXO - Security Reader: All</span></span>
- <span data-ttu-id="186e1-306">僅限 EXO-Transport Rules： All</span><span class="sxs-lookup"><span data-stu-id="186e1-306">EXO Only - Transport Rules: All</span></span>
- <span data-ttu-id="186e1-307">僅限 EXO-View-Only 設定： All</span><span class="sxs-lookup"><span data-stu-id="186e1-307">EXO Only - View-Only Configuration: All</span></span>

<span data-ttu-id="186e1-308">在電子郵件格線、詳細資料浮出和匯出的 CSV 中，ETRs 會以如下所示的名稱/GUID 呈現。</span><span class="sxs-lookup"><span data-stu-id="186e1-308">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-309">![Exchange 傳輸規則](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-309">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="186e1-310">輸入連接器</span><span class="sxs-lookup"><span data-stu-id="186e1-310">Inbound connectors</span></span>

<span data-ttu-id="186e1-311">連接器是一組指示，可自訂您的電子郵件流向和來源於您的 Microsoft 365 或 Office 365 組織的方式。</span><span class="sxs-lookup"><span data-stu-id="186e1-311">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="186e1-312">它們可讓您套用任何安全性限制或控制項。</span><span class="sxs-lookup"><span data-stu-id="186e1-312">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="186e1-313">在威脅瀏覽器內，您現在可以查看與電子郵件相關的連接器，並使用連接器名稱搜尋電子郵件。</span><span class="sxs-lookup"><span data-stu-id="186e1-313">Within Threat Explorer, you can now view the connectors that are related to an email and search for emails by using connector names.</span></span>

<span data-ttu-id="186e1-314">在 [自然] 中，連接器的搜尋是「包含」，這表示部分關鍵字搜尋也應該可以運作。</span><span class="sxs-lookup"><span data-stu-id="186e1-314">The search for connectors is "contains" in nature, which means partial keyword searches should work as well.</span></span> <span data-ttu-id="186e1-315">在主格線視圖中，[詳細資料] 飛入和匯出的 CSV，連接器會以如下所示的名稱/GUID 格式顯示：</span><span class="sxs-lookup"><span data-stu-id="186e1-315">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown here:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-316">![連接器詳細資料](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-316">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="186e1-317">威脅瀏覽器和即時偵測中的新功能</span><span class="sxs-lookup"><span data-stu-id="186e1-317">New features in Threat Explorer and Real-time detections</span></span>

<span data-ttu-id="186e1-318">威脅瀏覽器和即時偵測可使用三項新功能：</span><span class="sxs-lookup"><span data-stu-id="186e1-318">Three new features are available in Threat Explorer and Real-time detections:</span></span>

- [<span data-ttu-id="186e1-319">預覽電子郵件標頭和下載電子郵件內文</span><span class="sxs-lookup"><span data-stu-id="186e1-319">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="186e1-320">電子郵件時間表</span><span class="sxs-lookup"><span data-stu-id="186e1-320">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="186e1-321">匯出 URL 點擊資料</span><span class="sxs-lookup"><span data-stu-id="186e1-321">Export URL click data</span></span>](#export-url-click-data)

<span data-ttu-id="186e1-322">新功能如下所列。</span><span class="sxs-lookup"><span data-stu-id="186e1-322">These new features are outlined below.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="186e1-323">預覽電子郵件標頭和下載電子郵件內文</span><span class="sxs-lookup"><span data-stu-id="186e1-323">Preview email header and download email body</span></span>

<span data-ttu-id="186e1-324">您現在可以預覽電子郵件頭，並下載威脅瀏覽器管理員的電子郵件內文。系統管理員可以分析已下載的標頭/電子郵件，以取得威脅。</span><span class="sxs-lookup"><span data-stu-id="186e1-324">You can now preview an email header and download the email body in Threat Explorer Admins can analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="186e1-325">因為下載電子郵件可能會危及資訊的危險性，所以此程式是由以角色為基礎的存取控制 (RBAC) 所控制。</span><span class="sxs-lookup"><span data-stu-id="186e1-325">Because downloading email messages can risk exposure of information, this process is controlled by role-based access control (RBAC).</span></span> <span data-ttu-id="186e1-326">新的角色、 *預覽*，必須新增至其他角色群組 (例如安全作業或安全性系統管理員) ，以授與透過所有電子郵件消息查看下載郵件的能力。</span><span class="sxs-lookup"><span data-stu-id="186e1-326">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails in all-email messages view.</span></span> <span data-ttu-id="186e1-327">不過，若要在威脅瀏覽器) 中查看郵件所需的 (以外，查看電子郵件標頭並不需要任何其他角色。</span><span class="sxs-lookup"><span data-stu-id="186e1-327">However, viewing email header does not require any additional role (other than what is required to view messages in Threat Explorer).</span></span>

<span data-ttu-id="186e1-328">瀏覽器和即時偵測也會取得新的欄位，可提供您的電子郵件所在位置更完整的畫面。</span><span class="sxs-lookup"><span data-stu-id="186e1-328">Explorer and Real-time detections will also get new fields that provide a more complete picture of where your email messages land.</span></span> <span data-ttu-id="186e1-329">這些變更可使搜尋更輕鬆進行安全性 Op。</span><span class="sxs-lookup"><span data-stu-id="186e1-329">These changes  make hunting easier for Security Ops.</span></span> <span data-ttu-id="186e1-330">不過，主要結果是您可以快速知道問題電子郵件訊息的位置。</span><span class="sxs-lookup"><span data-stu-id="186e1-330">But the main result is you can know the location of problem email messages at a glance.</span></span>

<span data-ttu-id="186e1-331">這是如何達成？</span><span class="sxs-lookup"><span data-stu-id="186e1-331">How is this done?</span></span> <span data-ttu-id="186e1-332">傳遞狀態現在會分解成兩個欄：</span><span class="sxs-lookup"><span data-stu-id="186e1-332">Delivery status is now broken out into two columns:</span></span>

- <span data-ttu-id="186e1-333">**傳遞動作** -電子郵件的狀態。</span><span class="sxs-lookup"><span data-stu-id="186e1-333">**Delivery action** - Status of the email.</span></span>
- <span data-ttu-id="186e1-334">**傳遞位置** -傳送電子郵件的位置。</span><span class="sxs-lookup"><span data-stu-id="186e1-334">**Delivery location** - Where the email was routed.</span></span>

<span data-ttu-id="186e1-335">*傳遞動作* 是由於現有的原則或偵測，而對電子郵件採取的動作。</span><span class="sxs-lookup"><span data-stu-id="186e1-335">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="186e1-336">電子郵件可能的動作如下：</span><span class="sxs-lookup"><span data-stu-id="186e1-336">Here are the possible actions for an email:</span></span>

|<span data-ttu-id="186e1-337">已傳遞</span><span class="sxs-lookup"><span data-stu-id="186e1-337">Delivered</span></span>|<span data-ttu-id="186e1-338">已標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="186e1-338">Junked</span></span>|<span data-ttu-id="186e1-339">已封鎖</span><span class="sxs-lookup"><span data-stu-id="186e1-339">Blocked</span></span>|<span data-ttu-id="186e1-340">已取代</span><span class="sxs-lookup"><span data-stu-id="186e1-340">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="186e1-341">電子郵件已傳遞至使用者的收件匣或資料夾，而且使用者可以存取。</span><span class="sxs-lookup"><span data-stu-id="186e1-341">Email was delivered to the inbox or folder of a user, and the user can access it.</span></span>|<span data-ttu-id="186e1-342">電子郵件已傳送至使用者的 [垃圾郵件] 或 [已刪除] 資料夾，使用者可以存取它。</span><span class="sxs-lookup"><span data-stu-id="186e1-342">Email was sent to the user's Junk  or Deleted folder, and the user can access it.</span></span>|<span data-ttu-id="186e1-343">隔離、失敗或丟棄的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="186e1-343">Emails that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="186e1-344">使用者無法存取這些郵件。</span><span class="sxs-lookup"><span data-stu-id="186e1-344">These mails are inaccessible to the user.</span></span>|<span data-ttu-id="186e1-345">電子郵件有惡意附件取代 .txt 檔案，以表明附件是惡意的。</span><span class="sxs-lookup"><span data-stu-id="186e1-345">Email had malicious attachments replaced by .txt files that state the attachment was malicious.</span></span>|

<span data-ttu-id="186e1-346">以下是使用者可及無法看到的專案：</span><span class="sxs-lookup"><span data-stu-id="186e1-346">Here is what the user can and can't see:</span></span>

|<span data-ttu-id="186e1-347">使用者可以存取</span><span class="sxs-lookup"><span data-stu-id="186e1-347">Accessible to end users</span></span>|<span data-ttu-id="186e1-348">使用者無法存取 </span><span class="sxs-lookup"><span data-stu-id="186e1-348">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="186e1-349">已傳遞</span><span class="sxs-lookup"><span data-stu-id="186e1-349">Delivered</span></span>|<span data-ttu-id="186e1-350">已封鎖</span><span class="sxs-lookup"><span data-stu-id="186e1-350">Blocked</span></span>|
|<span data-ttu-id="186e1-351">已標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="186e1-351">Junked</span></span>|<span data-ttu-id="186e1-352">已取代</span><span class="sxs-lookup"><span data-stu-id="186e1-352">Replaced</span></span>|

<span data-ttu-id="186e1-353">**傳遞位置** 顯示執行後續傳遞的原則及偵測結果。</span><span class="sxs-lookup"><span data-stu-id="186e1-353">**Delivery location** shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="186e1-354">它會連結至 **_傳遞動作_**。</span><span class="sxs-lookup"><span data-stu-id="186e1-354">It's linked to **_Delivery action_**.</span></span> <span data-ttu-id="186e1-355">可能的值如下：</span><span class="sxs-lookup"><span data-stu-id="186e1-355">These are the possible values:</span></span>

- <span data-ttu-id="186e1-356">*收件匣或資料夾*：電子郵件的收件匣或資料夾 (會根據您的電子郵件規則) 。</span><span class="sxs-lookup"><span data-stu-id="186e1-356">*Inbox or folder*: The email is in the inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="186e1-357">*部署或外部*：信箱不存在於雲端上，但為內部部署。</span><span class="sxs-lookup"><span data-stu-id="186e1-357">*On-prem or external*: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="186e1-358">[垃圾郵件]*資料夾*：電子郵件位於使用者的 [垃圾郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="186e1-358">*Junk folder*: The email is in a user's Junk folder.</span></span>
- <span data-ttu-id="186e1-359">「*刪除的郵件」資料夾*：在使用者的 [刪除的郵件] 資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="186e1-359">*Deleted items folder*: The email in a user's Deleted items folder.</span></span>
- <span data-ttu-id="186e1-360">*隔離*：電子郵件是隔離的，而不是在使用者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="186e1-360">*Quarantine*: The email is in quarantine and not in a user's mailbox.</span></span>
- <span data-ttu-id="186e1-361">*失敗*；電子郵件無法傳遞至信箱。</span><span class="sxs-lookup"><span data-stu-id="186e1-361">*Failed*: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="186e1-362">*丟斷*：電子郵件在郵件流程中遺失。</span><span class="sxs-lookup"><span data-stu-id="186e1-362">*Dropped*: The email got lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="186e1-363">電子郵件時間表</span><span class="sxs-lookup"><span data-stu-id="186e1-363">Email timeline</span></span>

<span data-ttu-id="186e1-364">**電子郵件時程表** 是新的瀏覽器功能，可改善系統管理員的搜尋體驗。</span><span class="sxs-lookup"><span data-stu-id="186e1-364">The **Email timeline** is a new Explorer feature that improves the hunting experience for admins.</span></span> <span data-ttu-id="186e1-365">它會削減檢查不同位置所花費的時間，以嘗試瞭解該事件。</span><span class="sxs-lookup"><span data-stu-id="186e1-365">It cuts the time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="186e1-366">當電子郵件到達時，發生多個事件或接近該郵件時，這些事件會顯示在時程表視圖中。</span><span class="sxs-lookup"><span data-stu-id="186e1-366">When multiple events happen at or close to the same time an email arrives, those events are displayed in a timeline view.</span></span> <span data-ttu-id="186e1-367">您的電子郵件投遞之後所發生的某些事件會在 [ **特殊動作** ] 欄中捕獲。</span><span class="sxs-lookup"><span data-stu-id="186e1-367">Some events that happen to your email post-delivery are captured in the **Special action** column.</span></span> <span data-ttu-id="186e1-368">系統管理員可以合併時程表中的資訊，並在郵件投遞後採取特殊的動作，以深入瞭解其原則的運作方式（即最後一次路由傳送郵件的位置），而且在某些情況下，最後評估是什麼。</span><span class="sxs-lookup"><span data-stu-id="186e1-368">Admins can combine  information from the timeline with the special action taken on the mail post-delivery to get insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="186e1-369">如需詳細資訊，請參閱 [調查並修復 Office 365 中傳遞的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)。</span><span class="sxs-lookup"><span data-stu-id="186e1-369">For more information, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="186e1-370">匯出 URL 點擊資料</span><span class="sxs-lookup"><span data-stu-id="186e1-370">Export URL click data</span></span>

<span data-ttu-id="186e1-371">您現在可以將 URL 按一下的報告匯出至 Microsoft Excel 以查看其 **網路消息識別碼** ，並 **按一下**[判斷]，以協助說明您的 URL 按一下流量的來源。</span><span class="sxs-lookup"><span data-stu-id="186e1-371">You can now export reports for URL clicks to Microsoft Excel to view their **network message ID** and **click verdict**, which helps explain where your URL click traffic originated.</span></span> <span data-ttu-id="186e1-372">其運作方式如下：在「威脅管理」的 Office 365 快速啟動列上，請遵循下列連結：</span><span class="sxs-lookup"><span data-stu-id="186e1-372">Here's how it works: In Threat Management on the Office 365 quick-launch bar, follow this chain:</span></span>

<span data-ttu-id="186e1-373">**瀏覽器** \>**查看網路釣魚** \>**按一下** \>**Top URLs** Or **URL 上擊** \> 選取 [任何記錄] 以開啟 [URL] 浮出控制項。</span><span class="sxs-lookup"><span data-stu-id="186e1-373">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs** or **URL Top Clicks** \> select any record to open the URL flyout.</span></span>

<span data-ttu-id="186e1-374">當您在清單中選取 URL 時，您會在飛出面板上看到新的 [ **匯出** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="186e1-374">When you select a URL in the list, you'll see a new **Export** button on the fly-out panel.</span></span> <span data-ttu-id="186e1-375">使用此按鈕將資料移至 Excel 試算表，以便更輕鬆地進行報告。</span><span class="sxs-lookup"><span data-stu-id="186e1-375">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="186e1-376">請遵循此路徑，以取得即時偵測報告中的相同位置：</span><span class="sxs-lookup"><span data-stu-id="186e1-376">Follow this path to get to the same location in the Real-time detections report:</span></span>

<span data-ttu-id="186e1-377">**瀏覽器** \>**即時偵測** \>**查看網路釣魚** \>**URLs** \>**Top URLs** 或 **top 按一下** \> 選取 [任何記錄] 以開啟 [URL] 浮出 \> ] 流覽至 [**點擊**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="186e1-377">**Explorer** \> **Real-time detections** \> **View Phish** \> **URLs** \> **Top URLs** or **Top Clicks** \> Select any record to open the URL flyout \> navigate to the **Clicks** tab.</span></span>

> [!TIP]
> <span data-ttu-id="186e1-378">當您使用瀏覽器或關聯的協力廠商工具來搜尋識別碼時，網路郵件識別碼會對應按一下 [回復至特定郵件]。</span><span class="sxs-lookup"><span data-stu-id="186e1-378">The Network Message ID maps the click back to specific mails when you search on the ID through Explorer or associated third-party tools.</span></span> <span data-ttu-id="186e1-379">這類搜尋會識別與按一下結果關聯的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="186e1-379">Such searches identify the email associated with a click result.</span></span> <span data-ttu-id="186e1-380">讓相關網路郵件識別碼能夠更快速且更強大的分析。</span><span class="sxs-lookup"><span data-stu-id="186e1-380">Having the correlated Network Message ID makes for quicker and more powerful analysis.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="186e1-381">![瀏覽器中的按一下 tab 鍵](../../media/tp_ExportClickResultAndNetworkID.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-381">![Clicks tab in Explorer](../../media/tp_ExportClickResultAndNetworkID.png)</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="186e1-382">查看透過技術在電子郵件中偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="186e1-382">See malware detected in email by technology</span></span>

<span data-ttu-id="186e1-383">假設您想要查看透過 Microsoft 365 技術排序的電子郵件中偵測到惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="186e1-383">Suppose you want to see malware detected in email sorted by Microsoft 365 technology.</span></span> <span data-ttu-id="186e1-384">若要這麼做，請使用瀏覽器的 [電子郵件 > 惡意](threat-explorer-views.md#email--malware) 代碼視圖 (或即時偵測) 。</span><span class="sxs-lookup"><span data-stu-id="186e1-384">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="186e1-385">在安全性與合規性中心 (<https://protection.office.com>) 選擇 **[威脅管理]** \> **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="186e1-385">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="186e1-386">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="186e1-386">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="186e1-387">在 [ **視圖** ] 功能表中，選擇 [ **電子郵件** \> **惡意** 代碼]。</span><span class="sxs-lookup"><span data-stu-id="186e1-387">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="186e1-388">![總管的檢視功能表](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-388">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="186e1-389">按一下 [ **寄件者**]，然後選擇 [ **基本** \> **偵測技術**]。</span><span class="sxs-lookup"><span data-stu-id="186e1-389">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="186e1-390">您的偵測技術現在可做為報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="186e1-390">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="186e1-391">![惡意程式碼偵測技術](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-391">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="186e1-392">選擇 [選項]。</span><span class="sxs-lookup"><span data-stu-id="186e1-392">Choose an option.</span></span> <span data-ttu-id="186e1-393">然後選取 [重新整理] **按鈕，套用** 該篩選。</span><span class="sxs-lookup"><span data-stu-id="186e1-393">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="186e1-394">![選取的偵測技術](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-394">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

<span data-ttu-id="186e1-395">報告會進行重新整理，以顯示惡意程式碼在電子郵件中偵測到的結果，並使用您選取的技術選項。</span><span class="sxs-lookup"><span data-stu-id="186e1-395">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="186e1-396">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="186e1-396">From here, you can conduct further analysis.</span></span>

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="186e1-397">查看網路釣魚 URL，然後按一下 [已判定資料]</span><span class="sxs-lookup"><span data-stu-id="186e1-397">View phishing URL and click verdict data</span></span>

<span data-ttu-id="186e1-398">假設您想要查看透過電子郵件中的 URL 進行的網路釣魚攻擊，包括允許、封鎖及覆寫的 URL 清單。</span><span class="sxs-lookup"><span data-stu-id="186e1-398">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="186e1-399">若要識別所按一下的 URLs，必須設定 [安全連結](atp-safe-links.md) 。</span><span class="sxs-lookup"><span data-stu-id="186e1-399">To identify URLs that were clicked, [Safe Links](atp-safe-links.md) must be configured.</span></span> <span data-ttu-id="186e1-400">請確定您已設定 [安全連結原則](set-up-atp-safe-links-policies.md) 的 [保護] 和 [記錄] 按一下 [安全連結] 中的 [verdicts]。</span><span class="sxs-lookup"><span data-stu-id="186e1-400">Make sure that you set up [Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="186e1-401">若要查看郵件中的網路釣魚 URLs，並按一下網路釣魚郵件中 URLs，請使用瀏覽器或即時偵測的 [**電子郵件**  >  **網路釣魚**](threat-explorer-views.md#email--phish)視圖。</span><span class="sxs-lookup"><span data-stu-id="186e1-401">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="186e1-402">在安全性與合規性中心 (<https://protection.office.com>) 選擇 **[威脅管理]** \> **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="186e1-402">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="186e1-403">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="186e1-403">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="186e1-404">在 [ **視圖** ] 功能表中，選擇 [ **電子郵件** \> **釣魚網絡**]。</span><span class="sxs-lookup"><span data-stu-id="186e1-404">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="186e1-405">![網路釣魚內容中瀏覽器的視圖功能表](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-405">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="186e1-406">按一下 [ **寄件者**]，然後選擇 **URLs** \> **按一下 [判定**]。</span><span class="sxs-lookup"><span data-stu-id="186e1-406">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="186e1-407">選取一個或多個選項（例如 **封鎖** 和 **封鎖**），然後在與套用該篩選的選項相同的列上選取 [重新整理 **] 按鈕。**</span><span class="sxs-lookup"><span data-stu-id="186e1-407">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="186e1-408">(請勿重新整理瀏覽器視窗。)</span><span class="sxs-lookup"><span data-stu-id="186e1-408">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="186e1-409">![URL 和按一下結果](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-409">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="186e1-410">報告會重新整理以在報告下的 [URL] 索引標籤上顯示兩個不同的 URL 表格：</span><span class="sxs-lookup"><span data-stu-id="186e1-410">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="186e1-411">**Top URLs** 是您篩選的郵件中 URLs，以及每個 URL 的電子郵件傳遞動作計數。</span><span class="sxs-lookup"><span data-stu-id="186e1-411">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="186e1-412">在網路釣魚電子郵件視圖中，此清單通常包含合法的 URLs。</span><span class="sxs-lookup"><span data-stu-id="186e1-412">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="186e1-413">攻擊者會在其郵件中混合使用良好和不良的 URLs，以嘗試傳遞，但它們會使惡意連結看起來更有趣。</span><span class="sxs-lookup"><span data-stu-id="186e1-413">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="186e1-414">URLs 的表格依總的電子郵件總數排序，但是此欄位是隱藏的，以簡化視圖。</span><span class="sxs-lookup"><span data-stu-id="186e1-414">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="186e1-415">**上** 指按一下的安全連結-包裝 URLs，依總按一下計數排序。</span><span class="sxs-lookup"><span data-stu-id="186e1-415">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="186e1-416">此欄位也不會顯示，以簡化視圖。</span><span class="sxs-lookup"><span data-stu-id="186e1-416">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="186e1-417">依資料行的總計數表示每個點擊過的 URL 的安全連結按一下結果計數。</span><span class="sxs-lookup"><span data-stu-id="186e1-417">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="186e1-418">在網路釣魚電子郵件視圖中，這些通常是可疑或惡意的 URLs。</span><span class="sxs-lookup"><span data-stu-id="186e1-418">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="186e1-419">不過，此視圖可以包含不是威脅的 URLs，但位於網路釣魚郵件中。</span><span class="sxs-lookup"><span data-stu-id="186e1-419">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="186e1-420">在這裡未顯示 URL 按一下已開啟的連結。</span><span class="sxs-lookup"><span data-stu-id="186e1-420">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="186e1-421">這兩個 URL 表格會依照傳送動作和位置，顯示網路釣魚電子郵件中的最上層 URLs。</span><span class="sxs-lookup"><span data-stu-id="186e1-421">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="186e1-422">[！注意] 表格會顯示因警告而封鎖或訪問的 URL 按一下，因此您可以看到使用者的潛在不良連結，以及使用者已按一下的連結。</span><span class="sxs-lookup"><span data-stu-id="186e1-422">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the user's clicked.</span></span> <span data-ttu-id="186e1-423">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="186e1-423">From here, you can conduct further analysis.</span></span> <span data-ttu-id="186e1-424">例如，在圖表下方，您可以在組織環境中所封鎖的電子郵件訊息中看到最上層 URLs。</span><span class="sxs-lookup"><span data-stu-id="186e1-424">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="186e1-425">![已封鎖的總管 URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-425">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="186e1-426">選取 URL 以檢視更多詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="186e1-426">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="186e1-427">在 [URL 飛入] 對話方塊中，會移除電子郵件上的篩選，以顯示您環境中 URL 公開的完整視圖。</span><span class="sxs-lookup"><span data-stu-id="186e1-427">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="186e1-428">這可讓您在瀏覽器中篩選您關心的電子郵件訊息，找出潛在威脅的特定 URLs，然後透過 [URL 詳細資料] 對話方塊，展開您環境中的 URL 公開知識 () 而不必將 URL 篩選器新增至瀏覽器視圖本身。</span><span class="sxs-lookup"><span data-stu-id="186e1-428">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="186e1-429">按一下 verdicts 的轉譯</span><span class="sxs-lookup"><span data-stu-id="186e1-429">Interpretation of click verdicts</span></span>

<span data-ttu-id="186e1-430">在電子郵件或 URL flyouts 中，按一下上方和篩選體驗內，您會看到不同的按一下判定值：</span><span class="sxs-lookup"><span data-stu-id="186e1-430">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="186e1-431">**無：** 無法捕獲 URL 的判定。</span><span class="sxs-lookup"><span data-stu-id="186e1-431">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="186e1-432">使用者可能已按一下透過 URL。</span><span class="sxs-lookup"><span data-stu-id="186e1-432">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="186e1-433">**允許：** 允許使用者流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="186e1-433">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="186e1-434">**封鎖：** 已封鎖使用者流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="186e1-434">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="186e1-435">**擱置的判定：** 使用者呈現在引爆擱置的頁面上。</span><span class="sxs-lookup"><span data-stu-id="186e1-435">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="186e1-436">**封鎖已被取代：** 封鎖使用者直接流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="186e1-436">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="186e1-437">但使用者 overrode 區塊以流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="186e1-437">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="186e1-438">**擱置的判定略過：** 使用者呈現的是 [引爆] 頁面。</span><span class="sxs-lookup"><span data-stu-id="186e1-438">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="186e1-439">但使用者 overrode 郵件以存取 URL。</span><span class="sxs-lookup"><span data-stu-id="186e1-439">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="186e1-440">**錯誤：** 使用者呈現錯誤頁面，或捕獲判定結果時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="186e1-440">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="186e1-441">**失敗：** 捕獲判定時，發生未知的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="186e1-441">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="186e1-442">使用者可能已按一下透過 URL。</span><span class="sxs-lookup"><span data-stu-id="186e1-442">The user might have clicked through the URL.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="186e1-443">檢閱使用者回報的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="186e1-443">Review email messages reported by users</span></span>

<span data-ttu-id="186e1-444">假設您想要查看組織中的使用者已透過 [報告郵件增益集](enable-the-report-message-add-in.md)或 [報告網路釣魚增益集](enable-the-report-phish-add-in.md)舉報為 *垃圾* 郵件、*非垃圾* 郵件或 *網路釣魚* 的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="186e1-444">Suppose that you want to see email messages that users in your organization reported as *Junk*, *Not Junk*, or *Phishing* through the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span> <span data-ttu-id="186e1-445">若要查看，請使用瀏覽器的 [**電子郵件**  >  **提交**](threat-explorer-views.md#email--submissions)視圖 (或即時偵測) 。</span><span class="sxs-lookup"><span data-stu-id="186e1-445">To see them, use the [**Email** > **Submissions**](threat-explorer-views.md#email--submissions) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="186e1-446">在安全性與合規性中心 (<https://protection.office.com>) 選擇 **[威脅管理]** \> **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="186e1-446">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="186e1-447">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="186e1-447">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="186e1-448">在 [ **View** ] 功能表中，選擇 [ **電子郵件** \> **提交**]。</span><span class="sxs-lookup"><span data-stu-id="186e1-448">In the **View** menu, choose **Email** \> **Submissions**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="186e1-449">![電子郵件瀏覽器的視圖功能表](../../media/explorer-view-menu-email-user-reported.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-449">![View menu for Explorer for emails](../../media/explorer-view-menu-email-user-reported.png)</span></span>

3. <span data-ttu-id="186e1-450">按一下 [ **寄件者**]，然後選擇 [ **基本** \> **報表類型**]。</span><span class="sxs-lookup"><span data-stu-id="186e1-450">Click **Sender**, and then choose **Basic** \> **Report type**.</span></span>

4. <span data-ttu-id="186e1-451">選取選項，**例如 [** **網路釣魚**]，然後選取 [重新整理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="186e1-451">Select an option, such as **Phish**, and then select the **Refresh** button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="186e1-452">![使用者回報的網路釣魚](../../media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="186e1-452">![User-reported phish](../../media/EmailUserReportedReportType.png)</span></span>

<span data-ttu-id="186e1-453">報告會重新整理以顯示組織中的人員報告為網路釣魚企圖的電子郵件相關資料。</span><span class="sxs-lookup"><span data-stu-id="186e1-453">The report refreshes to show data about email messages that people in your organization reported as a phishing attempt.</span></span> <span data-ttu-id="186e1-454">您可以使用這項資訊進行進一步的分析，必要時，調整 [Microsoft Defender For Office 365 中的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="186e1-454">You can use this information to conduct further analysis, and, if necessary, adjust your [anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="186e1-455">啟動自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="186e1-455">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="186e1-456">*Microsoft Defender For Office 365 方案 2* 和 *Office 365 E5* 中提供自動調查和回應功能。</span><span class="sxs-lookup"><span data-stu-id="186e1-456">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="186e1-457">[自動化調查和回應](automated-investigation-response-office.md) 可儲存您的安全性運作小組時間和精力，以調查及緩解 cyberattacks。</span><span class="sxs-lookup"><span data-stu-id="186e1-457">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="186e1-458">除了設定會觸發安全性劇本的警示，您可以在總管中的檢視啟動自動化調查及回應程序。</span><span class="sxs-lookup"><span data-stu-id="186e1-458">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="186e1-459">如需詳細資訊，請參閱 [範例：安全性管理員會從瀏覽器觸發調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="186e1-459">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a><span data-ttu-id="186e1-460">更多使用 Explorer 和即時偵測的方式</span><span class="sxs-lookup"><span data-stu-id="186e1-460">More ways to use Explorer and Real-time detections</span></span>

<span data-ttu-id="186e1-461">除了本文所述的案例之外，您還可以使用更多報表選項，以供 Explorer (或即時偵測) 。</span><span class="sxs-lookup"><span data-stu-id="186e1-461">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or Real-time detections).</span></span> <span data-ttu-id="186e1-462">請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="186e1-462">See the following articles:</span></span>

- [<span data-ttu-id="186e1-463">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="186e1-463">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="186e1-464">檢視在 SharePoint Online、OneDrive 和 Microsoft Teams 中偵測到的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="186e1-464">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="186e1-465">取得威脅瀏覽器中的視圖 (和即時偵測的概覽) </span><span class="sxs-lookup"><span data-stu-id="186e1-465">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="186e1-466">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="186e1-466">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="186e1-467">Microsoft 威脅防護的自動化調查及回應</span><span class="sxs-lookup"><span data-stu-id="186e1-467">Automated investigation and response in Microsoft Threat Protection</span></span>](../mtp/mtp-autoir.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="186e1-468">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="186e1-468">Required licenses and permissions</span></span>

<span data-ttu-id="186e1-469">您必須擁有 [Microsoft Defender For Office 365](office-365-atp.md) ，才能使用 Explorer 或即時偵測。</span><span class="sxs-lookup"><span data-stu-id="186e1-469">You must have [Microsoft Defender for Office 365](office-365-atp.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="186e1-470">Explorer 會包含在 Office 365 的 Defender for Office 中方案2。</span><span class="sxs-lookup"><span data-stu-id="186e1-470">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="186e1-471">Office 365 方案1中包含即時偵測報告。</span><span class="sxs-lookup"><span data-stu-id="186e1-471">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="186e1-472">規劃為所有應受 Defender for Office 365 保護的使用者指派授權。</span><span class="sxs-lookup"><span data-stu-id="186e1-472">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="186e1-473">瀏覽器和即時偵測顯示已授權使用者的偵測資料。</span><span class="sxs-lookup"><span data-stu-id="186e1-473">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="186e1-474">若要查看和使用 Explorer 或即時偵測，您必須具有適當的許可權，例如授與安全性管理員或安全性讀者的許可權。</span><span class="sxs-lookup"><span data-stu-id="186e1-474">To view and use Explorer or Real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="186e1-475">針對安全性 & 合規性中心，您必須已指派下列角色之一：</span><span class="sxs-lookup"><span data-stu-id="186e1-475">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="186e1-476">組織管理</span><span class="sxs-lookup"><span data-stu-id="186e1-476">Organization Management</span></span>
  - <span data-ttu-id="186e1-477">安全性管理員 (可以在 Azure Active Directory 系統管理中心 (中指派 <https://aad.portal.azure.com>) </span><span class="sxs-lookup"><span data-stu-id="186e1-477">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="186e1-478">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="186e1-478">Security Reader</span></span>

- <span data-ttu-id="186e1-479">若為 Exchange Online，您必須在 Exchange 系統管理中心中指派下列其中一個角色 (<https://admin.protection.outlook.com/ecp/>) 或 [exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)：</span><span class="sxs-lookup"><span data-stu-id="186e1-479">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center (<https://admin.protection.outlook.com/ecp/>) or [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell):</span></span>

  - <span data-ttu-id="186e1-480">組織管理</span><span class="sxs-lookup"><span data-stu-id="186e1-480">Organization Management</span></span>
  - <span data-ttu-id="186e1-481">僅限檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="186e1-481">View-Only Organization Management</span></span>
  - <span data-ttu-id="186e1-482">僅限檢視收件者</span><span class="sxs-lookup"><span data-stu-id="186e1-482">View-Only Recipients</span></span>
  - <span data-ttu-id="186e1-483">合規性管理</span><span class="sxs-lookup"><span data-stu-id="186e1-483">Compliance Management</span></span>

<span data-ttu-id="186e1-484">若要深入了解角色和權限，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="186e1-484">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="186e1-485">安全性與合規性中心的權限</span><span class="sxs-lookup"><span data-stu-id="186e1-485">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="186e1-486">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="186e1-486">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="186e1-487">威脅瀏覽器與即時偵測的差異</span><span class="sxs-lookup"><span data-stu-id="186e1-487">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="186e1-488">您可以在 Office 365 的 Defender for Office 方案1中取得 *即時* 偵測報告。</span><span class="sxs-lookup"><span data-stu-id="186e1-488">The *Real-time detections* report is available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="186e1-489">*威脅瀏覽器* 適用于 Office 365 方案2的 Defender。</span><span class="sxs-lookup"><span data-stu-id="186e1-489">*Threat Explorer* is available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="186e1-490">即時偵測報告可讓您即時查看偵測。</span><span class="sxs-lookup"><span data-stu-id="186e1-490">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="186e1-491">威脅瀏覽器也會這麼做，但也會提供特定攻擊的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="186e1-491">Threat Explorer does this as well, but it also provides additional details for a given attack.</span></span>
- <span data-ttu-id="186e1-492">*所有的電子郵件* view 都可用於威脅瀏覽器，但不會出現在即時偵測報告中。</span><span class="sxs-lookup"><span data-stu-id="186e1-492">An *All email* view is available in Threat Explorer but not in the Real-time detections report.</span></span>
- <span data-ttu-id="186e1-493">威脅瀏覽器中包含更多篩選功能和可用的動作。</span><span class="sxs-lookup"><span data-stu-id="186e1-493">More filtering capabilities and available actions are included in Threat Explorer.</span></span> <span data-ttu-id="186e1-494">如需詳細資訊，請參閱 [Microsoft defender For office 365 服務說明：每個 Defender For office 365 方案中可用的功能](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="186e1-494">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>
