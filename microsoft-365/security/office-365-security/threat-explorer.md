---
title: 威脅總管和即時偵測
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: 瞭解如何在安全性與合規性中心使用 Explorer 和即時偵測， &amp; 以有效且有效地調查威脅並加以回應。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cf932db30feb3210b8980b95e666972cd3436dd0
ms.sourcegitcommit: 9ee1261c405f82b49c62390a25dfdea23340d644
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/06/2020
ms.locfileid: "45039520"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="93022-103">威脅總管和即時偵測</span><span class="sxs-lookup"><span data-stu-id="93022-103">Threat Explorer and real-time detections</span></span>

<span data-ttu-id="93022-104">如果貴組織具有 [Office 365 進階威脅防護](office-365-atp.md) (Office 365 ATP)，而且您具有[必要的權限](#required-licenses-and-permissions)，您具有**總管**或**即時偵測** (先前的*即時報告* — [查看新增功能](#new-features-in-threat-explorer-and-real-time-detections)！)。</span><span class="sxs-lookup"><span data-stu-id="93022-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **real-time detections** (formerly *real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="93022-105">在 [安全性 & 規範中心] 中，移至 [**威脅管理**]，然後選擇 [ **Explorer** ]_或_[**即時**偵測]。</span><span class="sxs-lookup"><span data-stu-id="93022-105">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

| <span data-ttu-id="93022-106">在 ATP 方案 2，您會看到：</span><span class="sxs-lookup"><span data-stu-id="93022-106">With ATP Plan 2, you see:</span></span> | <span data-ttu-id="93022-107">在 ATP 方案 1，您會看到：</span><span class="sxs-lookup"><span data-stu-id="93022-107">With ATP Plan 1, you see:</span></span> |
|---|---|
|![威脅總管](../../media/threatmgmt-explorer.png)|![即時偵測](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="93022-110">總管 (或即時偵測) 提供您強大的報告，讓您的安全性作業小組以有效的方式調查及回應威脅。</span><span class="sxs-lookup"><span data-stu-id="93022-110">With Explorer (or real-time detections), you have a powerful report that enables your Security Operations team to investigate and respond to threats effectively and efficiently.</span></span> <span data-ttu-id="93022-111">報告類似下列影像：</span><span class="sxs-lookup"><span data-stu-id="93022-111">The report resembles the following image:</span></span>

![移至威脅管理 \> 總管](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="93022-113">您可以使用此報告：</span><span class="sxs-lookup"><span data-stu-id="93022-113">With this report, you can:</span></span>

- [<span data-ttu-id="93022-114">查看 Microsoft 365 的安全性功能偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="93022-114">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="93022-115">檢視網路釣魚 URL 並按一下結果</span><span class="sxs-lookup"><span data-stu-id="93022-115">View data about phishing URLs and click verdict</span></span>](#view-data-about-phishing-urls-and-click-verdict)
- <span data-ttu-id="93022-116">[從總管中的檢視啟動自動化的調查和回應程序](#start-automated-investigation-and-response) (僅限 ATP 方案 2)</span><span class="sxs-lookup"><span data-stu-id="93022-116">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (ATP Plan 2 only)</span></span>
- <span data-ttu-id="93022-117">... [調查惡意電子郵件等功能](#more-ways-to-use-explorer-or-real-time-detections)！</span><span class="sxs-lookup"><span data-stu-id="93022-117">... [Investigate malicious email, and more](#more-ways-to-use-explorer-or-real-time-detections)!</span></span>

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a><span data-ttu-id="93022-118">豐富威脅瀏覽器和即時偵測的增強功能</span><span class="sxs-lookup"><span data-stu-id="93022-118">Experience Improvements to Threat Explorer and Real-Time Detections</span></span>

<span data-ttu-id="93022-119">在改進搜尋程式的過程中，我們對威脅瀏覽器和即時偵測進行一些更新。</span><span class="sxs-lookup"><span data-stu-id="93022-119">As part of improving the hunting process, we have made a few updates to Threat Explorer and Real-Time Detections.</span></span> <span data-ttu-id="93022-120">這些是「經驗」的改善，其重點是讓搜尋體驗更為一致。</span><span class="sxs-lookup"><span data-stu-id="93022-120">These are ‘experience’ improvements, with the focus on making the hunting experience more consistent.</span></span> <span data-ttu-id="93022-121">這些變更如下所示：</span><span class="sxs-lookup"><span data-stu-id="93022-121">These changes are outlined below:</span></span> 

- [<span data-ttu-id="93022-122">時區改進</span><span class="sxs-lookup"><span data-stu-id="93022-122">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="93022-123">重新整理程式中的更新</span><span class="sxs-lookup"><span data-stu-id="93022-123">Update in the Refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="93022-124">新增至篩選的圖表深入分析</span><span class="sxs-lookup"><span data-stu-id="93022-124">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="93022-125">在產品資訊更新</span><span class="sxs-lookup"><span data-stu-id="93022-125">In product information updates</span></span>](#in-product-information-updates)

### <a name="timezone-improvements"></a><span data-ttu-id="93022-126">時區改進</span><span class="sxs-lookup"><span data-stu-id="93022-126">Timezone improvements</span></span> 

<span data-ttu-id="93022-127">我們會顯示入口網站中的電子郵件記錄以及匯出資料的時區。</span><span class="sxs-lookup"><span data-stu-id="93022-127">We will show the timezone for the email records within the Portal, as well as for Exported data.</span></span> <span data-ttu-id="93022-128">您可以透過電子郵件格線、詳細資料行中的電子郵件時程表及類似的電子郵件，在體驗上看到時區，這樣就不會為使用者提供明確的結果集時區。</span><span class="sxs-lookup"><span data-stu-id="93022-128">The timezone will be visible across experiences like Email Grid, Details Flyout, Email Timeline, and Similar Emails, so that the timezone for the result set is clear to the user.</span></span> 

![在瀏覽器中查看時區](../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="93022-130">重新整理程式中的更新</span><span class="sxs-lookup"><span data-stu-id="93022-130">Update in the Refresh process</span></span> 

<span data-ttu-id="93022-131">我們聽說過與自動重新整理有關之混淆的意見反應（例如，當您變更日期、頁面會重新整理時）和手動重新整理（適用于其他篩選器）。</span><span class="sxs-lookup"><span data-stu-id="93022-131">We have heard feedback around confusion with automatic refresh (e.g. for date, as soon as you change the date, the page would refresh) and manual refresh (for other filters).</span></span> <span data-ttu-id="93022-132">同樣地，移除篩選器會導致自動重新整理，這會導致在修改查詢時變更不同篩選的情況可能會造成不一致的搜尋體驗。</span><span class="sxs-lookup"><span data-stu-id="93022-132">Similarly, removing filters leads to automatic refresh, this causes situations where changing the different filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="93022-133">若要解決此情況，我們會移至手動篩選機制。</span><span class="sxs-lookup"><span data-stu-id="93022-133">To solve this, we are moving to a manual filtering mechanism.</span></span>
<span data-ttu-id="93022-134">從經驗的觀點來看，使用者可以套用和移除不同的篩選範圍（從 filter set 和 date），然後按下 [重新整理] 按鈕，以在完成定義查詢之後篩選結果。</span><span class="sxs-lookup"><span data-stu-id="93022-134">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set, and date), and press the refresh button to filter the results once they are done with defining the query.</span></span> <span data-ttu-id="93022-135">重新整理按鈕也已更新，可在螢幕上清晰地呼叫。</span><span class="sxs-lookup"><span data-stu-id="93022-135">The refresh button has also been updated to call it out clearly on the screen.</span></span> <span data-ttu-id="93022-136">我們也針對這項變更，更新工具提示及產品中的檔。</span><span class="sxs-lookup"><span data-stu-id="93022-136">We have also updated tooltips and in-product documentation around this change.</span></span> 

![按一下 [重新整理] 以篩選結果](../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="93022-138">新增至篩選的圖表深入分析</span><span class="sxs-lookup"><span data-stu-id="93022-138">Chart drilldown to add to filters</span></span>

<span data-ttu-id="93022-139">您現在可以按一下圖表圖例值，將該值新增為篩選。</span><span class="sxs-lookup"><span data-stu-id="93022-139">You will now be able to click on the chart legend values to add that value as a filter.</span></span> <span data-ttu-id="93022-140">請注意，您仍然需要按一下 [重新整理] 按鈕，以在上述變更中篩選結果。</span><span class="sxs-lookup"><span data-stu-id="93022-140">Note that you will still have to click on the refresh button to filter the results as part of the change described above.</span></span>

![透過圖表深入篩選](../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a><span data-ttu-id="93022-142">在產品資訊更新</span><span class="sxs-lookup"><span data-stu-id="93022-142">In product information updates</span></span> 

<span data-ttu-id="93022-143">您也應該會看到產品中的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="93022-143">You should also see additional details within the product.</span></span> <span data-ttu-id="93022-144">例如，格線內的搜尋結果總數（請參閱下文）及標籤、錯誤訊息及工具提示的增強功能，可提供更多關於篩選、搜尋經驗及結果集的資訊。</span><span class="sxs-lookup"><span data-stu-id="93022-144">For example, the total number of search results within grid (see below), as well as improvements around labels, error messages and tooltips, to give more information around filters, search experience, and result set.</span></span> 

![View In 產品資訊](../media/ProductInfo.png)


## <a name="new-features-in-real-time-detections"></a><span data-ttu-id="93022-146">即時偵測中的新功能</span><span class="sxs-lookup"><span data-stu-id="93022-146">New features in real-time detections</span></span>

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="93022-147">威脅總管和即時偵測的新功能</span><span class="sxs-lookup"><span data-stu-id="93022-147">New features in Threat Explorer and real-time detections</span></span>

<span data-ttu-id="93022-148">威脅總管和即時偵測新增了三個新功能：</span><span class="sxs-lookup"><span data-stu-id="93022-148">Three new features added into Threat Explorer and real-time detections:</span></span>

- [<span data-ttu-id="93022-149">預覽電子郵件標頭和下載電子郵件內文</span><span class="sxs-lookup"><span data-stu-id="93022-149">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="93022-150">電子郵件時間表</span><span class="sxs-lookup"><span data-stu-id="93022-150">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="93022-151">匯出 URL 點擊資料</span><span class="sxs-lookup"><span data-stu-id="93022-151">Export URL click data</span></span>](#export-url-click-data)

<span data-ttu-id="93022-152">新功能如下所列。</span><span class="sxs-lookup"><span data-stu-id="93022-152">These new features are outlined below.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="93022-153">預覽電子郵件標頭和下載電子郵件內文</span><span class="sxs-lookup"><span data-stu-id="93022-153">Preview email header and download email body</span></span>

<span data-ttu-id="93022-154">預覽電子郵件標頭和下載電子郵件內文能力為威脅總管提供的新功能。</span><span class="sxs-lookup"><span data-stu-id="93022-154">The ability to preview an email header and download the email body are new features available in Threat Explorer.</span></span> <span data-ttu-id="93022-155">系統管理員將能分析下載的標頭/電子郵件訊息是否存在威脅。</span><span class="sxs-lookup"><span data-stu-id="93022-155">Admins will be able to analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="93022-156">由於下載電子郵件訊息可能有資訊暴露的風險，此程序是由角色型存取控制 (RBAC) 來控制。</span><span class="sxs-lookup"><span data-stu-id="93022-156">Because downloading email messages can risk the exposure of information, this process is controlled by roles-based access control (RBAC).</span></span> <span data-ttu-id="93022-157">新的角色（*預覽*）必須新增至其他角色群組（例如，安全性作業或安全性管理員），以授與在所有電子郵件訊息中下載郵件和預覽標頭的能力。</span><span class="sxs-lookup"><span data-stu-id="93022-157">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails and preview headers in all-email messages view.</span></span>

<span data-ttu-id="93022-158">但總管 (和即時偵測) 也會新增新欄位，設計用於提供您更完整的電子郵件訊息目標位置資訊。</span><span class="sxs-lookup"><span data-stu-id="93022-158">But Explorer (and real-time detections) also adds fresh new fields designed to give you a more complete picture of where your email messages land.</span></span> <span data-ttu-id="93022-159">這項變更的部分目標是讓安全性作業人員更容易搜捕，但最後的結果在於對問題電子郵件訊息的位置一目了然。</span><span class="sxs-lookup"><span data-stu-id="93022-159">Part of the goal of this change is to make hunting easier for Security Ops people, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="93022-160">這是如何達成？</span><span class="sxs-lookup"><span data-stu-id="93022-160">How is this done?</span></span> <span data-ttu-id="93022-161">傳遞狀態現在劃分為兩個資料行：</span><span class="sxs-lookup"><span data-stu-id="93022-161">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="93022-162">**傳遞動作** - 這封電子郵件的狀態為何？</span><span class="sxs-lookup"><span data-stu-id="93022-162">**Delivery Action** - What is the status of this email?</span></span>
- <span data-ttu-id="93022-163">**傳遞位置** - 結果這封電子郵件是如何路由傳送？</span><span class="sxs-lookup"><span data-stu-id="93022-163">**Delivery Location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="93022-164">「傳遞動作」是基於現有原則或偵測對電子郵件所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="93022-164">Delivery Action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="93022-165">以下是電子郵件可能採取的動作：</span><span class="sxs-lookup"><span data-stu-id="93022-165">Here are the possible actions an email can take:</span></span>

|<span data-ttu-id="93022-166">已傳遞</span><span class="sxs-lookup"><span data-stu-id="93022-166">Delivered</span></span>  |<span data-ttu-id="93022-167">已標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="93022-167">Junked</span></span>  |<span data-ttu-id="93022-168">已封鎖</span><span class="sxs-lookup"><span data-stu-id="93022-168">Blocked</span></span>  |<span data-ttu-id="93022-169">已取代</span><span class="sxs-lookup"><span data-stu-id="93022-169">Replaced</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="93022-170">電子郵件已傳送至使用者的收件匣或資料夾，而且使用者可以直接存取。</span><span class="sxs-lookup"><span data-stu-id="93022-170">Email was delivered to Inbox or folder of a user and the user can directly access it.</span></span>    | <span data-ttu-id="93022-171">電子郵件會傳送至使用者的垃圾郵件資料夾或已刪除的資料夾，而且使用者可以存取這些資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="93022-171">Email was sent to either user’s Junk folder or Deleted folder, and the user has access to emails in those folders.</span></span>       | <span data-ttu-id="93022-172">任何隔離、失敗或丟棄的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="93022-172">Any emails that are quarantined, that  failed, or were dropped.</span></span> <span data-ttu-id="93022-173">這完全無法由使用者存取！</span><span class="sxs-lookup"><span data-stu-id="93022-173">This is completely inaccessible by the user!</span></span>     | <span data-ttu-id="93022-174">任何電子郵件，惡意附件會以表示附件惡意的 .txt 檔取代。</span><span class="sxs-lookup"><span data-stu-id="93022-174">Any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>     |
    

| <span data-ttu-id="93022-175">已傳遞</span><span class="sxs-lookup"><span data-stu-id="93022-175">Delivered</span></span> | <span data-ttu-id="93022-176">已標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="93022-176">Junked</span></span> | <span data-ttu-id="93022-177">已封鎖</span><span class="sxs-lookup"><span data-stu-id="93022-177">Blocked</span></span> | <span data-ttu-id="93022-178">已取代</span><span class="sxs-lookup"><span data-stu-id="93022-178">Replaced</span></span> |
|---|---|---|---|
|<span data-ttu-id="93022-179">電子郵件已傳遞至使用者的收件匣或其他資料夾，使用者可以直接存取。</span><span class="sxs-lookup"><span data-stu-id="93022-179">Email was delivered to the user's inbox or another folder, and the user can directly access it.</span></span>| <span data-ttu-id="93022-180">電子郵件會傳送至使用者的垃圾郵件資料夾或已刪除的資料夾，而且使用者可以存取這些資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="93022-180">Email was sent to either user's Junk folder or Deleted folder, and the user has access to email messages in those folders.</span></span>| <span data-ttu-id="93022-181">任何已隔離、傳遞失敗或已捨棄的電子郵件，使用者均無法存取。</span><span class="sxs-lookup"><span data-stu-id="93022-181">Any email messages that are quarantined, that failed, or were dropped, and are not accessible by the user.</span></span>| <span data-ttu-id="93022-182">以 .txt 檔案替換為惡意附件的任何電子郵件訊息，均指出附件是惡意的。</span><span class="sxs-lookup"><span data-stu-id="93022-182">Any email messages where malicious attachments were replaced by .txt files that state the attachments were malicious.</span></span>|
|

<span data-ttu-id="93022-183">以下是使用者可以查看及無法查看的內容：</span><span class="sxs-lookup"><span data-stu-id="93022-183">And here is what the user can see, and what they can't:</span></span>

| <span data-ttu-id="93022-184">使用者可以存取</span><span class="sxs-lookup"><span data-stu-id="93022-184">Accessible to end users</span></span> | <span data-ttu-id="93022-185">使用者無法存取 </span><span class="sxs-lookup"><span data-stu-id="93022-185">Inaccessible to end users</span></span> |
|---|---|
|<span data-ttu-id="93022-186">已傳遞</span><span class="sxs-lookup"><span data-stu-id="93022-186">Delivered</span></span>|<span data-ttu-id="93022-187">已封鎖</span><span class="sxs-lookup"><span data-stu-id="93022-187">Blocked</span></span>|
|<span data-ttu-id="93022-188">已標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="93022-188">Junked</span></span>|<span data-ttu-id="93022-189">已取代</span><span class="sxs-lookup"><span data-stu-id="93022-189">Replaced</span></span>|

<span data-ttu-id="93022-190">傳遞位置顯示原則和執行傳遞後偵測的結果。</span><span class="sxs-lookup"><span data-stu-id="93022-190">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="93022-191">其連結到「傳遞動作」。</span><span class="sxs-lookup"><span data-stu-id="93022-191">It's linked to a Delivery Action.</span></span> <span data-ttu-id="93022-192">已新增此欄位，以深入了解找到問題電子郵件時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="93022-192">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="93022-193">以下是傳遞位置可能的值：</span><span class="sxs-lookup"><span data-stu-id="93022-193">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="93022-194">**收件匣或資料夾**：電子郵件位於收件匣或資料夾中 (根據您的電子郵件規則)。</span><span class="sxs-lookup"><span data-stu-id="93022-194">**Inbox or folder**: The email is in inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="93022-195">**部署或外部**：信箱不存在於雲端上，但為內部部署。</span><span class="sxs-lookup"><span data-stu-id="93022-195">**On-prem or external**: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="93022-196">**垃圾郵件資料夾**：電子郵件位於使用者的 [垃圾郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="93022-196">**Junk folder**: The email is in the Junk folder of a user.</span></span>
- <span data-ttu-id="93022-197">**刪除的郵件資料夾**：電子郵件位於使用者的 [刪除的郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="93022-197">**Deleted items folder**: The email in the Deleted items folder of a user.</span></span>
- <span data-ttu-id="93022-198">**隔離**：隔離中的電子郵件，而不是使用者信箱中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="93022-198">**Quarantine**: The email in quarantine, and is not in a user's mailbox.</span></span>
- <span data-ttu-id="93022-199">**失敗**；電子郵件無法傳遞至信箱。</span><span class="sxs-lookup"><span data-stu-id="93022-199">**Failed**: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="93022-200">**已捨棄**：電子郵件在郵件流程的某處遺失。</span><span class="sxs-lookup"><span data-stu-id="93022-200">**Dropped**: The email gets lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="93022-201">電子郵件時間表</span><span class="sxs-lookup"><span data-stu-id="93022-201">Email timeline</span></span>

<span data-ttu-id="93022-202">**電子郵件時間表**是總管的另一個新功能，目標是提升系統管理員的搜捕體驗。</span><span class="sxs-lookup"><span data-stu-id="93022-202">The **Email Timeline** is another new Explorer feature aimed at making the hunting experience better for admins.</span></span> <span data-ttu-id="93022-203">這可減少不規則性，因為花較少的時間檢查不同位置以嘗試了解事件。</span><span class="sxs-lookup"><span data-stu-id="93022-203">It cuts down on randomization because there is less time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="93022-204">當多個事件同時或接近同時發生在某電子郵件時，這些事件會出現在時刻表檢視。</span><span class="sxs-lookup"><span data-stu-id="93022-204">When multiple events happen at, or close to, the same time on an email, those events will show up in a timeline view.</span></span> <span data-ttu-id="93022-205">事實上，某些在傳遞郵件後發生的事件會由「特殊動作」欄擷取。</span><span class="sxs-lookup"><span data-stu-id="93022-205">In fact, some events that happen post-delivery to your mail will be captured in the 'Special action' column.</span></span> <span data-ttu-id="93022-206">透過結合該郵件在時間表的資訊和傳遞郵件後採取的特殊動作，能讓系統管理員深入了解其原則的運作方式、郵件最後路由傳送的位置，以及在某些情況下最終評估的內容。</span><span class="sxs-lookup"><span data-stu-id="93022-206">Combining the information from the timeline of that mail with the special action taken on the mail post-delivery will give admins insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="93022-207">如需有關調查惡意電子郵件訊息的詳細討論，請參閱[調查並修復 Office 365 中傳遞的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)。</span><span class="sxs-lookup"><span data-stu-id="93022-207">For more discussion about investigating malicious email messages, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="93022-208">匯出 URL 點擊資料</span><span class="sxs-lookup"><span data-stu-id="93022-208">Export URL click data</span></span>

<span data-ttu-id="93022-209">此外，您現在可以將 URL 點選的報告匯出到 Microsoft Excel 中，以便檢視其 [網路郵件識別碼] 以及 [按一下結果]，從而更容易了解 URL 點擊流量的來源。</span><span class="sxs-lookup"><span data-stu-id="93022-209">Also, you will now be able to export reports for URL clicks to Microsoft Excel in order to view both their Network Message ID, and their Click Verdict, making the task of understanding where your URL click traffic originated easier.</span></span> <span data-ttu-id="93022-210">以下說明運作方式。</span><span class="sxs-lookup"><span data-stu-id="93022-210">Here's how it works.</span></span> <span data-ttu-id="93022-211">在 Office 365 的威脅管理快速啟動中開啟，按一下此鏈結：</span><span class="sxs-lookup"><span data-stu-id="93022-211">Starting in Threat Management on the Office 365 quick-launch, click through this chain:</span></span>

<span data-ttu-id="93022-212">**瀏覽器** \>**查看網路釣魚** \>**按一下** \>Top **URLs 或 URL 上擊** \>**按一下任一筆記錄開啟 URL 彈出**視窗</span><span class="sxs-lookup"><span data-stu-id="93022-212">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs or URL Top Clicks** \> **Click on any record to open URL flyout**</span></span>

<span data-ttu-id="93022-213">當您按一下清單中的 URL 時，將會在飛出面版上看到新的 [匯出] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="93022-213">When you click on a URL in the list, you'll see a new Export button on the fly-out panel.</span></span> <span data-ttu-id="93022-214">使用此按鈕將資料移至 Excel 試算表，以便更輕鬆地進行報告。</span><span class="sxs-lookup"><span data-stu-id="93022-214">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="93022-215">您可以在即時偵測報告中取得相同的位置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="93022-215">You can get to the same location in the real-time detections report as follows:</span></span>

<span data-ttu-id="93022-216">**瀏覽器** \>**即時偵測** \>**查看網路釣魚** \>**URLs** \>**上 URLs 或上按一下** \>**按一下任一筆記錄開啟 URL 彈出** \> 視窗**流覽至 [點擊]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="93022-216">**Explorer** \> **Real-time Detections** \> **View Phish** \> **URLs** \> **Top URLs or Top Clicks** \> **Click on any record to open URL flyout** \> **Navigate to the Clicks Tab.**</span></span>

> [!TIP]
> <span data-ttu-id="93022-217">當您透過網路郵件識別碼在總管或關聯的協力廠商工具中進行搜尋時，網路郵件識別碼會將點擊返回對應到特定的郵件。</span><span class="sxs-lookup"><span data-stu-id="93022-217">Network Message ID maps the click back to specific mails when you search through Explorer or associated 3rd party tools via Network Message ID.</span></span> <span data-ttu-id="93022-218">搜尋網路郵件識別碼時，系統會提供系統管理員與點擊結果相關聯的特定電子郵件。</span><span class="sxs-lookup"><span data-stu-id="93022-218">Searching through the Network Message ID will give admins the specific email associated with a click result.</span></span> <span data-ttu-id="93022-219">匯出時，網路郵件識別碼的關聯識別可提供更快且更強大的分析。</span><span class="sxs-lookup"><span data-stu-id="93022-219">On export having, the correlating identification of Network Message ID makes for quicker and more powerful analysis.</span></span>

![tp_ExportClickResultAndNetworkID.png](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="93022-221">查看透過技術在電子郵件中偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="93022-221">See malware detected in email by technology</span></span>

<span data-ttu-id="93022-222">假設您想要查看 Microsoft 365 技術在電子郵件中偵測到惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="93022-222">Suppose you want to see malware detected in email, by Microsoft 365 technology.</span></span> <span data-ttu-id="93022-223">若要這麼做，請使用總管 (或即時偵測) 的 [[電子郵件] > [惡意程式碼]](threat-explorer-views.md#email--malware) 檢視。</span><span class="sxs-lookup"><span data-stu-id="93022-223">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="93022-224">在安全性與合規性中心 ([https://protection.office.com](https://protection.office.com)) 選擇 **[威脅管理]** > **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="93022-224">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="93022-225">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="93022-225">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="93022-226">在 **[檢視]** 功能表中，選擇 **[電子郵件]** > **[惡意程式碼 ]**。</span><span class="sxs-lookup"><span data-stu-id="93022-226">In the **View** menu, choose **Email** > **Malware**.</span></span>

   ![總管的檢視功能表](../../media/ExplorerViewEmailMalwareMenu.png)

3. <span data-ttu-id="93022-228">按一下 **[寄件者]**，然後選擇 **[基本]** > **[偵測技術]**。</span><span class="sxs-lookup"><span data-stu-id="93022-228">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span>

   <span data-ttu-id="93022-229">您的偵測技術現在可做為報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="93022-229">Your detection technologies are now available as filters for the report.</span></span>

   ![惡意程式碼偵測技術](../../media/ExplorerEmailMalwareDetectionTech.png)

4. <span data-ttu-id="93022-231">選取一個選項，然後按一下 **[重新整理]** 按鈕來套用該篩選器。</span><span class="sxs-lookup"><span data-stu-id="93022-231">Select an option, and then click the **Refresh** button to apply that filter.</span></span>

   ![選取的偵測技術](../../media/ExplorerEmailMalwareDetectionTechATP.png)

<span data-ttu-id="93022-233">報告會使用您所選取的技術選項重新整理，以顯示在電子郵件中偵測到的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="93022-233">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="93022-234">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="93022-234">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="93022-235">檢視網路釣魚 URL 並按一下結果</span><span class="sxs-lookup"><span data-stu-id="93022-235">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="93022-236">假設您想要查看透過電子郵件中的 URL 進行的網路釣魚攻擊，包括允許、封鎖及覆寫的 URL 清單。</span><span class="sxs-lookup"><span data-stu-id="93022-236">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="93022-237">若要識別已按過的 URL，則必須設定 [ATP 安全連結](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="93022-237">Identifying URLs that were clicked requires [ATP Safe links](atp-safe-links.md) to be configured.</span></span> <span data-ttu-id="93022-238">請確認您已針對點擊時保護和 ATP 安全連結的按一下結果記錄設定 [ATP 安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="93022-238">Make sure that you have set up [ATP Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by ATP Safe Links.</span></span>

<span data-ttu-id="93022-239">若要檢閱郵件中的網路釣魚 URL 和網路釣魚郵件中的 URL 點擊，請使用總管 (或即時偵測) 的 [[電子郵件] > [網路釣魚]](threat-explorer-views.md#email--phish) 檢視。</span><span class="sxs-lookup"><span data-stu-id="93022-239">To review phish URLs in messages and clicks on URLs in phish messages, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="93022-240">在安全性與合規性中心 ([https://protection.office.com](https://protection.office.com)) 選擇 **[威脅管理]** > **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="93022-240">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="93022-241">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="93022-241">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="93022-242">在 **[檢視]** 功能表中，選擇 **[電子郵件]** > **[網路釣魚]**。</span><span class="sxs-lookup"><span data-stu-id="93022-242">In the **View** menu, choose **Email** > **Phish**.</span></span>

   ![總管的檢視功能表](../../media/ExplorerViewEmailPhishMenu.png)

3. <span data-ttu-id="93022-244">按一下 **[寄件者]**，然後選擇 **[URL]** > **按一下結果**。</span><span class="sxs-lookup"><span data-stu-id="93022-244">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>

4. <span data-ttu-id="93022-245">選取一或多個選項，例如 **[已封鎖]** 和 **[封鎖覆寫]**，然後按一下要套用該篩選器的選項同一行上的 **[重新整理]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="93022-245">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button that is on the same line as the options to apply that filter.</span></span> <span data-ttu-id="93022-246">(請勿重新整理瀏覽器視窗。)</span><span class="sxs-lookup"><span data-stu-id="93022-246">(Don't refresh your browser window.)</span></span>

   ![URL 和按一下結果](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

    <span data-ttu-id="93022-248">報告會重新整理以在報告下的 [URL] 索引標籤上顯示兩個不同的 URL 表格：</span><span class="sxs-lookup"><span data-stu-id="93022-248">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="93022-249">**[熱門 URL]** 為已篩選的郵件中的 URL，而電子郵件傳送動作會計算每個 URL。</span><span class="sxs-lookup"><span data-stu-id="93022-249">**Top URLs** are the URLs contained in the messages you have filtered down to, and the email delivery action counts for each URL.</span></span> <span data-ttu-id="93022-250">在網路釣魚電子郵件檢視中，此清單通常會包含合法的 URL。</span><span class="sxs-lookup"><span data-stu-id="93022-250">In the phish email view, this list typically will contain legitimate URLs.</span></span> <span data-ttu-id="93022-251">攻擊者會在這些郵件中混雜善意和惡意的 URL，以試圖傳遞這些郵件，但他們會讓惡意連結看起來更加有趣，以誘使使用者點擊。</span><span class="sxs-lookup"><span data-stu-id="93022-251">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they will make the malicious links more interesting for the user to click.</span></span> <span data-ttu-id="93022-252">URLs 的表格依電子郵件總數排序（不過請注意，此欄會隱藏以簡化視圖）。</span><span class="sxs-lookup"><span data-stu-id="93022-252">The table of URLs is sorted by total email count (but note that this column is hidden to simplify the view).</span></span>

   - <span data-ttu-id="93022-253">**[熱門點擊]** 為點擊過的包含在安全連結中的 URL，並依總點擊數排序 (為了簡化檢視，此欄也不會顯示)。</span><span class="sxs-lookup"><span data-stu-id="93022-253">**Top clicks** are the Safe Links wrapped URLs that were clicked, sorted by total click count (this column is also not shown to simplify the view).</span></span> <span data-ttu-id="93022-254">依資料行的總計數表示每個點擊過的 URL 的安全連結按一下結果計數。</span><span class="sxs-lookup"><span data-stu-id="93022-254">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="93022-255">在網路釣魚電子郵件視圖中，這些都很經常是可疑或惡意的 URLs，但可能包含不具威脅但位於網路釣魚郵件中的 URLs。</span><span class="sxs-lookup"><span data-stu-id="93022-255">In the phish email view, these are more often suspicious or malicious URLs, but could include URLs that are not threats but are in phish messages.</span></span> <span data-ttu-id="93022-256">已開啟的連結 URL 點擊不會顯示在這裡。</span><span class="sxs-lookup"><span data-stu-id="93022-256">URL clicks on unwrapped links will not show up here.</span></span>

   <span data-ttu-id="93022-257">兩個 URL 表格依傳遞動作和位置顯示網路釣魚電子郵件訊息熱門 URL，並顯示已封鎖的 URL 點擊 (或儘管已警告卻仍造訪的 URL)，讓您了解使用者接收到及互動的潛在惡意連結。</span><span class="sxs-lookup"><span data-stu-id="93022-257">The two URL tables show top URLs in phishing email messages by delivery action and location, and they show URL clicks that were blocked (or visited despite a warning) so that you can understand what potential bad links were received by users and interacted with by users.</span></span> <span data-ttu-id="93022-258">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="93022-258">From here, you can conduct further analysis.</span></span> <span data-ttu-id="93022-259">例如，在圖表的下方，您可以查看貴組織環境中封鎖的電子郵件訊息熱門 URL。</span><span class="sxs-lookup"><span data-stu-id="93022-259">For example, below the chart, you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   ![已封鎖的總管 URL](../../media/ExplorerPhishClickVerdictURLs.png)

   <span data-ttu-id="93022-261">選取 URL 以檢視更多詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="93022-261">Select a URL to view more detailed information.</span></span>
   
   > [!NOTE]
   > <span data-ttu-id="93022-262">在 [URL 飛入] 對話方塊中，會移除電子郵件上的篩選，以顯示您環境中 URL 公開的完整視圖。</span><span class="sxs-lookup"><span data-stu-id="93022-262">In the URL flyout dialog, the filtering on email messages is removed to show you the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="93022-263">這能讓您在總管中篩選出擔心的電子郵件訊息，找出具有潛在威脅的特定 URL，然後了解暴露於環境 (經由 URL 詳細資料對話方塊) 中的 URL，而不需要將 URL 篩選新增至總管檢視本身。</span><span class="sxs-lookup"><span data-stu-id="93022-263">This lets you filter down email messages in Explorer to ones you are concerned about, find specific URLs that are potential threats, then expand your understanding of the URL exposure in your environment (via the URL details dialog) without having to add URL filters to the Explorer view itself.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="93022-264">檢閱使用者回報的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="93022-264">Review email messages reported by users</span></span>

<span data-ttu-id="93022-265">假設您想透過使用 [Outlook 和 Outlook 網頁版的回報郵件增益集](enable-the-report-message-add-in.md)來查看貴組織使用者回報為「垃圾郵件」、「非垃圾郵件」或「網路釣魚」的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="93022-265">Suppose that you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="93022-266">若要這麼做，請使用總管 (或即時偵測) 的 [[電子郵件] > [提交]](threat-explorer-views.md#email--submissions) 檢視。</span><span class="sxs-lookup"><span data-stu-id="93022-266">To do this, use the [Email > Submissions](threat-explorer-views.md#email--submissions) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="93022-267">在安全性與合規性中心 ([https://protection.office.com](https://protection.office.com)) 選擇 **[威脅管理]** > **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="93022-267">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="93022-268">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="93022-268">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="93022-269">在 **[檢視]** 功能表中，選擇 **[電子郵件]** > **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="93022-269">In the **View** menu, choose **Email** > **Submissions**.</span></span>

   ![總管的檢視功能表](../../media/explorer-view-menu-email-user-reported.png)

3. <span data-ttu-id="93022-271">按一下 **[寄件者]**，然後選擇 **[基本]** > **[回報類型]**。</span><span class="sxs-lookup"><span data-stu-id="93022-271">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>

4. <span data-ttu-id="93022-272">選取一個選項，例如 **[網路釣魚]**，然後按一下 **[重新整理]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="93022-272">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span>

   ![使用者回報的網路釣魚](../../media/EmailUserReportedReportType.png)

<span data-ttu-id="93022-274">報告會重新整理，顯示貴組織中的人員回報為網路釣魚攻擊的電子郵件相關資料。</span><span class="sxs-lookup"><span data-stu-id="93022-274">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="93022-275">您可以使用此資訊來進行進一步分析，並視需要調整 [ATP 防網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="93022-275">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="93022-276">啟動自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="93022-276">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="93022-277">**Office 365 ATP 方案 2** 和 **Office 365 E5** 提供自動化調查及回應功能。</span><span class="sxs-lookup"><span data-stu-id="93022-277">Automated investigation and response capabilities are available in **Office 365 ATP Plan 2** and **Office 365 E5**.</span></span>

<span data-ttu-id="93022-278">(新增！) [自動化調查及回應](automated-investigation-response-office.md)能為您的安全性作業小組節省許多時間和精力來調查及降低網路攻擊。</span><span class="sxs-lookup"><span data-stu-id="93022-278">(NEW!) [Automated investigation and response](automated-investigation-response-office.md) can save your security operations team much time and effort in investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="93022-279">除了設定會觸發安全性劇本的警示，您可以在總管中的檢視啟動自動化調查及回應程序。</span><span class="sxs-lookup"><span data-stu-id="93022-279">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span>

<span data-ttu-id="93022-280">如需這方面的詳細資訊，請參閱[範例：安全性系統管理員從總管觸發調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="93022-280">For details on this, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a><span data-ttu-id="93022-281">更多使用總管 (或即時偵測) 的方法</span><span class="sxs-lookup"><span data-stu-id="93022-281">More ways to use Explorer (or real-time detections)</span></span>

<span data-ttu-id="93022-282">除了這篇文章所述的案例，總管 (或即時偵測) 還有更多回報選項。</span><span class="sxs-lookup"><span data-stu-id="93022-282">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or real-time detections).</span></span>

- [<span data-ttu-id="93022-283">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="93022-283">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="93022-284">檢視在 SharePoint Online、OneDrive 和 Microsoft Teams 中偵測到的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="93022-284">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="93022-285">取得威脅總管 (和即時偵測) 檢視的概觀</span><span class="sxs-lookup"><span data-stu-id="93022-285">Get an overview of the views in Threat Explorer (and real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="93022-286">Microsoft 威脅防護的自動化調查及回應</span><span class="sxs-lookup"><span data-stu-id="93022-286">Automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="93022-287">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="93022-287">Required licenses and permissions</span></span>

<span data-ttu-id="93022-288">您必須具備 [Office 365 ATP](office-365-atp.md) 才能取得總管或即時偵測。</span><span class="sxs-lookup"><span data-stu-id="93022-288">You must have [Office 365 ATP](office-365-atp.md) to get Explorer or real-time detections.</span></span>

- <span data-ttu-id="93022-289">總管會包含在 Office 365 ATP 方案 2。</span><span class="sxs-lookup"><span data-stu-id="93022-289">Explorer is included in Office 365 ATP Plan 2.</span></span>
- <span data-ttu-id="93022-290">即時偵測報告會包含在 Office 365 ATP 方案 1。</span><span class="sxs-lookup"><span data-stu-id="93022-290">The real-time detections report is included in Office 365 ATP Plan 1.</span></span>
- <span data-ttu-id="93022-291">請計劃指派授權給所有應受 Office 365 ATP 保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="93022-291">Plan to assign licenses for all users who should be protected by Office 365 ATP.</span></span> <span data-ttu-id="93022-292">(總管或即時偵測會為經過授權的使用者顯示偵測資料。)</span><span class="sxs-lookup"><span data-stu-id="93022-292">(Explorer or real-time detections shows detection data for licensed users.)</span></span>

<span data-ttu-id="93022-293">若要檢視及使用總管或即時偵測，您必須具有適當的權限，例如授與安全性系統管理員或安全性讀取者的權限。</span><span class="sxs-lookup"><span data-stu-id="93022-293">To view and use Explorer or real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="93022-294">針對「安全性與合規性中心」，您必須受指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="93022-294">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="93022-295">組織管理</span><span class="sxs-lookup"><span data-stu-id="93022-295">Organization Management</span></span>
  - <span data-ttu-id="93022-296">安全性系統管理員 (這可以在 Azure Active Directory 系統管理中心指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="93022-296">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="93022-297">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="93022-297">Security Reader</span></span>

- <span data-ttu-id="93022-298">針對 Exchange Online，您必須在 Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)) 受指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="93022-298">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="93022-299">組織管理</span><span class="sxs-lookup"><span data-stu-id="93022-299">Organization Management</span></span>
  - <span data-ttu-id="93022-300">僅檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="93022-300">View-only Organization Management</span></span>
  - <span data-ttu-id="93022-301">僅檢視收件者角色</span><span class="sxs-lookup"><span data-stu-id="93022-301">View-Only Recipients role</span></span>
  - <span data-ttu-id="93022-302">合規性管理</span><span class="sxs-lookup"><span data-stu-id="93022-302">Compliance Management</span></span>

<span data-ttu-id="93022-303">若要深入了解角色和權限，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="93022-303">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="93022-304">安全性與 &amp; 合規性中心的許可權</span><span class="sxs-lookup"><span data-stu-id="93022-304">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="93022-305">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="93022-305">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="93022-306">威脅瀏覽器與即時偵測的某些差異</span><span class="sxs-lookup"><span data-stu-id="93022-306">Some differences between Threat Explorer and real-time detections</span></span>

- <span data-ttu-id="93022-307">Office 365 ATP 方案 1 提供**即時偵測**報告，而 Office 365 ATP 方案 2 提供**威脅總管**。</span><span class="sxs-lookup"><span data-stu-id="93022-307">The **real-time detections** report is available in Office 365 ATP Plan 1, whereas **Threat Explorer** is available in Office 365 ATP Plan 2.</span></span>
- <span data-ttu-id="93022-308">**即時偵測**報告可讓您即時檢視偵測。</span><span class="sxs-lookup"><span data-stu-id="93022-308">The **real-time detections** report allows you to view detections in real-time.</span></span> <span data-ttu-id="93022-309">**威脅總管**也有這個功能，但也能讓您檢視特定攻擊的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="93022-309">**Threat Explorer** does this as well, but also allows you to view additional details for a given attack.</span></span>
- <span data-ttu-id="93022-310">**所有的電子郵件**view 都可用於**威脅瀏覽器**（而不是**即時**的偵測報告中）。</span><span class="sxs-lookup"><span data-stu-id="93022-310">An **All email** view is available in **Threat Explorer** (and is not in the **real-time detections** report).</span></span>
- <span data-ttu-id="93022-311">**威脅瀏覽器**中包含更多篩選功能和可用的動作。</span><span class="sxs-lookup"><span data-stu-id="93022-311">More filtering capabilities and available actions are included in **Threat Explorer**.</span></span>

<span data-ttu-id="93022-312">如需詳細資訊，請參閱[Office 365 ATP 服務說明：各高級威脅防護（ATP）方案中的功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="93022-312">For more details, see [Office 365 ATP Service Description: Feature availability across Advanced Threat Protection (ATP) plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

