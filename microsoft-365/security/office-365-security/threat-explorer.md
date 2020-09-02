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
ms.openlocfilehash: 4220c850e5ef7f830f7fc6ec57bb220cca29eaf4
ms.sourcegitcommit: 4ac96855d7c269a0055ca8943000b762a70ca4ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/01/2020
ms.locfileid: "47322010"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="91249-103">威脅總管和即時偵測</span><span class="sxs-lookup"><span data-stu-id="91249-103">Threat Explorer and real-time detections</span></span>

<span data-ttu-id="91249-104">如果貴組織具有 [Office 365 進階威脅防護](office-365-atp.md) (Office 365 ATP)，而且您具有[必要的權限](#required-licenses-and-permissions)，您具有**總管**或**即時偵測** (先前的*即時報告* — [查看新增功能](#new-features-in-threat-explorer-and-real-time-detections)！)。</span><span class="sxs-lookup"><span data-stu-id="91249-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **real-time detections** (formerly *real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="91249-105">在 [安全性 & 規範中心] 中，移至 [ **威脅管理**]，然後選擇 [ **Explorer** ] _或_[ **即時**偵測]。</span><span class="sxs-lookup"><span data-stu-id="91249-105">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

|<span data-ttu-id="91249-106">在 ATP 方案 2，您會看到：</span><span class="sxs-lookup"><span data-stu-id="91249-106">With ATP Plan 2, you see:</span></span>|<span data-ttu-id="91249-107">在 ATP 方案 1，您會看到：</span><span class="sxs-lookup"><span data-stu-id="91249-107">With ATP Plan 1, you see:</span></span>|
|---|---|
|![威脅總管](../../media/threatmgmt-explorer.png)|![即時偵測](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="91249-110">總管 (或即時偵測) 提供您強大的報告，讓您的安全性作業小組以有效的方式調查及回應威脅。</span><span class="sxs-lookup"><span data-stu-id="91249-110">With Explorer (or real-time detections), you have a powerful report that enables your Security Operations team to investigate and respond to threats effectively and efficiently.</span></span> <span data-ttu-id="91249-111">報告類似下列影像：</span><span class="sxs-lookup"><span data-stu-id="91249-111">The report resembles the following image:</span></span>

![移至威脅管理 \> 總管](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="91249-113">您可以使用此報告：</span><span class="sxs-lookup"><span data-stu-id="91249-113">With this report, you can:</span></span>

- [<span data-ttu-id="91249-114">查看 Microsoft 365 的安全性功能偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="91249-114">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="91249-115">檢視網路釣魚 URL 並按一下結果</span><span class="sxs-lookup"><span data-stu-id="91249-115">View data about phishing URLs and click verdict</span></span>](#view-data-about-phishing-urls-and-click-verdict)
- <span data-ttu-id="91249-116">[從總管中的檢視啟動自動化的調查和回應程序](#start-automated-investigation-and-response) (僅限 ATP 方案 2)</span><span class="sxs-lookup"><span data-stu-id="91249-116">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (ATP Plan 2 only)</span></span>
- <span data-ttu-id="91249-117">... [調查惡意電子郵件等功能](#more-ways-to-use-explorer-or-real-time-detections)！</span><span class="sxs-lookup"><span data-stu-id="91249-117">... [Investigate malicious email, and more](#more-ways-to-use-explorer-or-real-time-detections)!</span></span>

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a><span data-ttu-id="91249-118">豐富威脅瀏覽器和即時偵測的增強功能</span><span class="sxs-lookup"><span data-stu-id="91249-118">Experience Improvements to Threat Explorer and Real-Time Detections</span></span>

<span data-ttu-id="91249-119">在改進搜尋程式的過程中，我們對威脅瀏覽器和即時偵測進行一些更新。</span><span class="sxs-lookup"><span data-stu-id="91249-119">As part of improving the hunting process, we have made a few updates to Threat Explorer and Real-Time Detections.</span></span> <span data-ttu-id="91249-120">這些是「經驗」的改善，其重點是讓搜尋體驗更為一致。</span><span class="sxs-lookup"><span data-stu-id="91249-120">These are ‘experience’ improvements, with the focus on making the hunting experience more consistent.</span></span> <span data-ttu-id="91249-121">這些變更如下所示：</span><span class="sxs-lookup"><span data-stu-id="91249-121">These changes are outlined below:</span></span>

- [<span data-ttu-id="91249-122">時區改進</span><span class="sxs-lookup"><span data-stu-id="91249-122">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="91249-123">重新整理程式中的更新</span><span class="sxs-lookup"><span data-stu-id="91249-123">Update in the Refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="91249-124">新增至篩選的圖表深入分析</span><span class="sxs-lookup"><span data-stu-id="91249-124">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="91249-125">在產品資訊更新</span><span class="sxs-lookup"><span data-stu-id="91249-125">In product information updates</span></span>](#in-product-information-updates)

### <a name="timezone-improvements"></a><span data-ttu-id="91249-126">時區改進</span><span class="sxs-lookup"><span data-stu-id="91249-126">Timezone improvements</span></span>

<span data-ttu-id="91249-127">我們會顯示入口網站中的電子郵件記錄以及匯出資料的時區。</span><span class="sxs-lookup"><span data-stu-id="91249-127">We will show the timezone for the email records within the Portal, as well as for Exported data.</span></span> <span data-ttu-id="91249-128">您可以透過電子郵件格線、詳細資料行中的電子郵件時程表及類似的電子郵件，在體驗上看到時區，這樣就不會為使用者提供明確的結果集時區。</span><span class="sxs-lookup"><span data-stu-id="91249-128">The timezone will be visible across experiences like Email Grid, Details Flyout, Email Timeline, and Similar Emails, so that the timezone for the result set is clear to the user.</span></span>

![在瀏覽器中查看時區](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="91249-130">重新整理程式中的更新</span><span class="sxs-lookup"><span data-stu-id="91249-130">Update in the Refresh process</span></span>

<span data-ttu-id="91249-131">我們已聽說過與自動重新整理有關之混淆的回饋 (例如，當您變更日期時，此頁面會重新整理) 和手動重新整理 (其他篩選) 。</span><span class="sxs-lookup"><span data-stu-id="91249-131">We have heard feedback around confusion with automatic refresh (e.g. for date, as soon as you change the date, the page would refresh) and manual refresh (for other filters).</span></span> <span data-ttu-id="91249-132">同樣地，移除篩選器會導致自動重新整理，這會導致在修改查詢時變更不同篩選的情況可能會造成不一致的搜尋體驗。</span><span class="sxs-lookup"><span data-stu-id="91249-132">Similarly, removing filters leads to automatic refresh, this causes situations where changing the different filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="91249-133">若要解決此情況，我們會移至手動篩選機制。</span><span class="sxs-lookup"><span data-stu-id="91249-133">To solve this, we are moving to a manual filtering mechanism.</span></span>
<span data-ttu-id="91249-134">從經驗的觀點來看，使用者可以從 filter set 和 date) 套用及移除不同的篩選範圍 (，然後按下 [重新整理] 按鈕，以在完成定義查詢之後篩選結果。</span><span class="sxs-lookup"><span data-stu-id="91249-134">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set, and date), and press the refresh button to filter the results once they are done with defining the query.</span></span> <span data-ttu-id="91249-135">重新整理按鈕也已更新，可在螢幕上清晰地呼叫。</span><span class="sxs-lookup"><span data-stu-id="91249-135">The refresh button has also been updated to call it out clearly on the screen.</span></span> <span data-ttu-id="91249-136">我們也針對這項變更，更新工具提示及產品中的檔。</span><span class="sxs-lookup"><span data-stu-id="91249-136">We have also updated tooltips and in-product documentation around this change.</span></span>

![按一下 [重新整理] 以篩選結果](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="91249-138">新增至篩選的圖表深入分析</span><span class="sxs-lookup"><span data-stu-id="91249-138">Chart drilldown to add to filters</span></span>

<span data-ttu-id="91249-139">您現在可以按一下圖表圖例值，將該值新增為篩選。</span><span class="sxs-lookup"><span data-stu-id="91249-139">You will now be able to click on the chart legend values to add that value as a filter.</span></span> <span data-ttu-id="91249-140">請注意，您仍然需要按一下 [重新整理] 按鈕，以在上述變更中篩選結果。</span><span class="sxs-lookup"><span data-stu-id="91249-140">Note that you will still have to click on the refresh button to filter the results as part of the change described above.</span></span>

![透過圖表深入篩選](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a><span data-ttu-id="91249-142">在產品資訊更新</span><span class="sxs-lookup"><span data-stu-id="91249-142">In product information updates</span></span>

<span data-ttu-id="91249-143">您也應該會看到產品中的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="91249-143">You should also see additional details within the product.</span></span> <span data-ttu-id="91249-144">例如，在 [格線] 中的搜尋結果總數 (請參閱下列) ，以及標籤、錯誤訊息及工具提示等方面的增強功能，以提供有關篩選、搜尋經驗及結果集的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="91249-144">For example, the total number of search results within grid (see below), as well as improvements around labels, error messages and tooltips, to give more information around filters, search experience, and result set.</span></span>

![View In 產品資訊](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="91249-146">威脅瀏覽器中的延伸功能</span><span class="sxs-lookup"><span data-stu-id="91249-146">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="91249-147">主要目標使用者</span><span class="sxs-lookup"><span data-stu-id="91249-147">Top targeted users</span></span>

<span data-ttu-id="91249-148">如今，我們會在惡意程式碼系列 (內的主要惡意程式碼) 區段中，公開主要目標使用者的清單。</span><span class="sxs-lookup"><span data-stu-id="91249-148">Today we expose the list of the top targeted users in the Malware View for Emails (within the Top Malware Families section).</span></span> <span data-ttu-id="91249-149">我們也會在網路釣魚和所有電子郵件視圖中擴充此視圖，您可以在其中看到前五個目標使用者，以及每位使用者對對應 (view 的嘗試次數。例如，針對 [網路釣魚視圖]，您將能夠看到) 的網路釣魚嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="91249-149">We will be extending this view within Phish and All Email views as well, where you will be able to see the top five targeted users along with the number of attempts for each user for the corresponding view (for example, for Phish view you will be able to see the number of Phish attempts).</span></span>
<span data-ttu-id="91249-150">您也可以將目標使用者的清單匯出為3000的限制，以及每個電子郵件 view 的離線分析嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="91249-150">You will also be able to export the list of targeted users up to a limit of 3000 along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="91249-151">除此之外，選取 [否]。</span><span class="sxs-lookup"><span data-stu-id="91249-151">In addition to that, selecting No.</span></span> <span data-ttu-id="91249-152">嘗試 (例如，下列 13) 會在威脅瀏覽器中開啟篩選的視圖，這樣您就可以深入瞭解該使用者的電子郵件和威脅。</span><span class="sxs-lookup"><span data-stu-id="91249-152">of attempts (for example, 13 attempts below) would open a filtered view in Threat Explorer, so that you can look at more details across emails and threats for that user.</span></span> 

![主要目標使用者](../../media/Top_Targeted_Users.png)


### <a name="exchange-transport-rules"></a><span data-ttu-id="91249-154">Exchange 傳輸規則</span><span class="sxs-lookup"><span data-stu-id="91249-154">Exchange transport rules</span></span>
<span data-ttu-id="91249-155">在資料豐富中，您也應該可以查看已套用至郵件的所有不同傳輸規則。</span><span class="sxs-lookup"><span data-stu-id="91249-155">As part of data enrichment, you should also be able to see all the different transport rules which were applied to a message.</span></span> <span data-ttu-id="91249-156">此資訊將會出現在 [電子郵件格線] 視圖中 (以進行查看，請選取 [格線] 中的 [欄選項]，然後在 [格線] 的 [欄] 選項中新增 Exchange Transport Rule) 以及電子郵件中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="91249-156">This information will be present within the Email grid view (to view this, select Column options in the grid and add Exchange Transport Rule from the Column options in the grid) as well as Details flyout in the email.</span></span>
<span data-ttu-id="91249-157">您可以同時看到 GUID，以及已套用至郵件的傳輸規則名稱。</span><span class="sxs-lookup"><span data-stu-id="91249-157">You would be able to see both the GUID as well as the name of the transport rules which were applied to the message.</span></span> <span data-ttu-id="91249-158">此外，您也可以使用傳輸規則的名稱來搜尋郵件。</span><span class="sxs-lookup"><span data-stu-id="91249-158">Additionally, you would be able to search for the messages using the name of the transport rule.</span></span> <span data-ttu-id="91249-159">這會是「包含」搜尋，這表示您也可以使用部分搜尋進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="91249-159">This would be a ‘Contains’ search which means you will be able to search using partial searches as well.</span></span> 

#### <a name="important-note"></a><span data-ttu-id="91249-160">重要注意事項：</span><span class="sxs-lookup"><span data-stu-id="91249-160">Important Note:</span></span> 
<span data-ttu-id="91249-161">ETR 搜尋和名稱可用性取決於指派給您的特定角色。</span><span class="sxs-lookup"><span data-stu-id="91249-161">ETR search and name availability would depend on the specific role that has been assigned to you.</span></span> <span data-ttu-id="91249-162">您必須具有下列其中一個角色/許可權，才能查看 ETR 名稱和搜尋。</span><span class="sxs-lookup"><span data-stu-id="91249-162">You will need to have one of the following roles/permissions in order to view the ETR names and search.</span></span>  <span data-ttu-id="91249-163">如果您未指派任何下列角色，您將無法看到傳輸規則的名稱，並使用 ETR 名稱來搜尋郵件。。</span><span class="sxs-lookup"><span data-stu-id="91249-163">If you do not have any of the following roles assigned to you, you will not be able to see the names of the transport rules, and search for the messages using the ETR names.</span></span> <span data-ttu-id="91249-164">不過，您將可以在電子郵件詳細資料中看到 ETR 標籤及 GUID 資訊。</span><span class="sxs-lookup"><span data-stu-id="91249-164">However, you will be able to see the ETR label and GUID information within the Email Details.</span></span> <span data-ttu-id="91249-165">在電子郵件網格、電子郵件 flyouts、篩選和匯出等中查看記錄的其他體驗不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="91249-165">Your other experiences around viewing records in Email Grids, Email flyouts, Filters, and Export are not impacted.</span></span> 
 
- <span data-ttu-id="91249-166">僅限 EXO-資料遺失防護：全部</span><span class="sxs-lookup"><span data-stu-id="91249-166">EXO Only - Data Loss Prevention: All</span></span>
- <span data-ttu-id="91249-167">僅限 EXO-O365SupportViewConfig： All</span><span class="sxs-lookup"><span data-stu-id="91249-167">EXO Only - O365SupportViewConfig: All</span></span>
- <span data-ttu-id="91249-168">AAD 或 EXO-安全性系統管理員： All</span><span class="sxs-lookup"><span data-stu-id="91249-168">AAD or EXO - Security Admin: All</span></span>
- <span data-ttu-id="91249-169">AAD 或 EXO-Security Reader： All</span><span class="sxs-lookup"><span data-stu-id="91249-169">AAD or EXO - Security Reader: All</span></span>
- <span data-ttu-id="91249-170">僅限 EXO-Transport Rules： All</span><span class="sxs-lookup"><span data-stu-id="91249-170">EXO Only - Transport Rules: All</span></span>
- <span data-ttu-id="91249-171">僅限 EXO-View-Only 設定： All</span><span class="sxs-lookup"><span data-stu-id="91249-171">EXO Only - View-Only Configuration: All</span></span>

<span data-ttu-id="91249-172">在電子郵件格線、詳細資料浮出和匯出的 CSV 中，ETRs 會以如下所示的名稱/GUID 呈現。</span><span class="sxs-lookup"><span data-stu-id="91249-172">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span> 

![Exchange 傳輸規則](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a><span data-ttu-id="91249-174">輸入連接器</span><span class="sxs-lookup"><span data-stu-id="91249-174">Inbound connectors</span></span> 

<span data-ttu-id="91249-175">連接器是一組指示，可自訂您的電子郵件流向和來源於您的 Microsoft 365 或 Office 365 組織的方式，以及套用任何安全性限制或控制措施的功能。</span><span class="sxs-lookup"><span data-stu-id="91249-175">Connectors are a collection of instructions that customize the way your email flows to and from your Microsoft 365 or Office 365 organization, with the ability to apply any security restriction or controls.</span></span> <span data-ttu-id="91249-176">在威脅瀏覽器內，您現在可以查看與電子郵件相關的連接器，也能使用連接器名稱搜尋電子郵件。</span><span class="sxs-lookup"><span data-stu-id="91249-176">Within Threat Explorer, you will now have the ability to view the connectors which are related to an email as well as search for emails using the connector names.</span></span> <span data-ttu-id="91249-177">連接器的搜尋是「包含」，其性質表示部分關鍵字搜尋應該也會運作。</span><span class="sxs-lookup"><span data-stu-id="91249-177">The search for connectors is ‘Contains’ in nature which means partial keyword searches should work as well.</span></span> <span data-ttu-id="91249-178">在主格線視圖中，[詳細資料] 飛入和匯出的 CSV，連接器會以如下所示的名稱/GUID 格式顯示：</span><span class="sxs-lookup"><span data-stu-id="91249-178">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown below:</span></span> 

![連接器詳細資料](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="91249-180">威脅總管和即時偵測的新功能</span><span class="sxs-lookup"><span data-stu-id="91249-180">New features in Threat Explorer and real-time detections</span></span>

<span data-ttu-id="91249-181">威脅總管和即時偵測新增了三個新功能：</span><span class="sxs-lookup"><span data-stu-id="91249-181">Three new features added into Threat Explorer and real-time detections:</span></span>

- [<span data-ttu-id="91249-182">預覽電子郵件標頭和下載電子郵件內文</span><span class="sxs-lookup"><span data-stu-id="91249-182">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="91249-183">電子郵件時間表</span><span class="sxs-lookup"><span data-stu-id="91249-183">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="91249-184">匯出 URL 點擊資料</span><span class="sxs-lookup"><span data-stu-id="91249-184">Export URL click data</span></span>](#export-url-click-data)

<span data-ttu-id="91249-185">新功能如下所列。</span><span class="sxs-lookup"><span data-stu-id="91249-185">These new features are outlined below.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="91249-186">預覽電子郵件標頭和下載電子郵件內文</span><span class="sxs-lookup"><span data-stu-id="91249-186">Preview email header and download email body</span></span>

<span data-ttu-id="91249-187">預覽電子郵件標頭和下載電子郵件內文能力為威脅總管提供的新功能。</span><span class="sxs-lookup"><span data-stu-id="91249-187">The ability to preview an email header and download the email body are new features available in Threat Explorer.</span></span> <span data-ttu-id="91249-188">系統管理員將能分析下載的標頭/電子郵件訊息是否存在威脅。</span><span class="sxs-lookup"><span data-stu-id="91249-188">Admins will be able to analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="91249-189">由於下載電子郵件訊息可能有資訊暴露的風險，此程序是由角色型存取控制 (RBAC) 來控制。</span><span class="sxs-lookup"><span data-stu-id="91249-189">Because downloading email messages can risk the exposure of information, this process is controlled by roles-based access control (RBAC).</span></span> <span data-ttu-id="91249-190">新的角色， *預覽*必須新增至另一個角色群組 (例如安全作業或安全性系統管理員) ，授與可在 [所有電子郵件] 視圖中下載郵件和預覽標頭的能力。</span><span class="sxs-lookup"><span data-stu-id="91249-190">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails and preview headers in all-email messages view.</span></span>

<span data-ttu-id="91249-191">但總管 (和即時偵測) 也會新增新欄位，設計用於提供您更完整的電子郵件訊息目標位置資訊。</span><span class="sxs-lookup"><span data-stu-id="91249-191">But Explorer (and real-time detections) also adds fresh new fields designed to give you a more complete picture of where your email messages land.</span></span> <span data-ttu-id="91249-192">這項變更的部分目標是讓安全性作業人員更容易搜捕，但最後的結果在於對問題電子郵件訊息的位置一目了然。</span><span class="sxs-lookup"><span data-stu-id="91249-192">Part of the goal of this change is to make hunting easier for Security Ops people, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="91249-193">這是如何達成？</span><span class="sxs-lookup"><span data-stu-id="91249-193">How is this done?</span></span> <span data-ttu-id="91249-194">傳遞狀態現在劃分為兩個資料行：</span><span class="sxs-lookup"><span data-stu-id="91249-194">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="91249-195">**傳遞動作** - 這封電子郵件的狀態為何？</span><span class="sxs-lookup"><span data-stu-id="91249-195">**Delivery Action** - What is the status of this email?</span></span>
- <span data-ttu-id="91249-196">**傳遞位置** - 結果這封電子郵件是如何路由傳送？</span><span class="sxs-lookup"><span data-stu-id="91249-196">**Delivery Location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="91249-197">「傳遞動作」是基於現有原則或偵測對電子郵件所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="91249-197">Delivery Action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="91249-198">以下是電子郵件可能採取的動作：</span><span class="sxs-lookup"><span data-stu-id="91249-198">Here are the possible actions an email can take:</span></span>

|<span data-ttu-id="91249-199">已傳遞</span><span class="sxs-lookup"><span data-stu-id="91249-199">Delivered</span></span>|<span data-ttu-id="91249-200">已標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="91249-200">Junked</span></span>|<span data-ttu-id="91249-201">已封鎖</span><span class="sxs-lookup"><span data-stu-id="91249-201">Blocked</span></span>|<span data-ttu-id="91249-202">已取代</span><span class="sxs-lookup"><span data-stu-id="91249-202">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="91249-203">電子郵件已傳送至使用者的收件匣或資料夾，而且使用者可以直接存取。</span><span class="sxs-lookup"><span data-stu-id="91249-203">Email was delivered to Inbox or folder of a user and the user can directly access it.</span></span>|<span data-ttu-id="91249-204">電子郵件會傳送至使用者的垃圾郵件資料夾或已刪除的資料夾，而且使用者可以存取這些資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="91249-204">Email was sent to either user’s Junk folder or Deleted folder, and the user has access to emails in those folders.</span></span>|<span data-ttu-id="91249-205">任何隔離、失敗或丟棄的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="91249-205">Any emails that are quarantined, that  failed, or were dropped.</span></span> <span data-ttu-id="91249-206">這完全無法由使用者存取！</span><span class="sxs-lookup"><span data-stu-id="91249-206">This is completely inaccessible by the user!</span></span>|<span data-ttu-id="91249-207">任何電子郵件，惡意附件會以表示附件惡意的 .txt 檔取代。</span><span class="sxs-lookup"><span data-stu-id="91249-207">Any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>|

|<span data-ttu-id="91249-208">已傳遞</span><span class="sxs-lookup"><span data-stu-id="91249-208">Delivered</span></span>|<span data-ttu-id="91249-209">已標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="91249-209">Junked</span></span>|<span data-ttu-id="91249-210">已封鎖</span><span class="sxs-lookup"><span data-stu-id="91249-210">Blocked</span></span>|<span data-ttu-id="91249-211">已取代</span><span class="sxs-lookup"><span data-stu-id="91249-211">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="91249-212">電子郵件已傳遞至使用者的收件匣或其他資料夾，使用者可以直接存取。</span><span class="sxs-lookup"><span data-stu-id="91249-212">Email was delivered to the user's inbox or another folder, and the user can directly access it.</span></span>|<span data-ttu-id="91249-213">電子郵件會傳送至使用者的垃圾郵件資料夾或已刪除的資料夾，而且使用者可以存取這些資料夾中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="91249-213">Email was sent to either user's Junk folder or Deleted folder, and the user has access to email messages in those folders.</span></span>|<span data-ttu-id="91249-214">任何已隔離、傳遞失敗或已捨棄的電子郵件，使用者均無法存取。</span><span class="sxs-lookup"><span data-stu-id="91249-214">Any email messages that are quarantined, that failed, or were dropped, and are not accessible by the user.</span></span>|<span data-ttu-id="91249-215">以 .txt 檔案替換為惡意附件的任何電子郵件訊息，均指出附件是惡意的。</span><span class="sxs-lookup"><span data-stu-id="91249-215">Any email messages where malicious attachments were replaced by .txt files that state the attachments were malicious.</span></span>|
|

<span data-ttu-id="91249-216">以下是使用者可以查看及無法查看的內容：</span><span class="sxs-lookup"><span data-stu-id="91249-216">And here is what the user can see, and what they can't:</span></span>

|<span data-ttu-id="91249-217">使用者可以存取</span><span class="sxs-lookup"><span data-stu-id="91249-217">Accessible to end users</span></span>|<span data-ttu-id="91249-218">使用者無法存取 </span><span class="sxs-lookup"><span data-stu-id="91249-218">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="91249-219">已傳遞</span><span class="sxs-lookup"><span data-stu-id="91249-219">Delivered</span></span>|<span data-ttu-id="91249-220">已封鎖</span><span class="sxs-lookup"><span data-stu-id="91249-220">Blocked</span></span>|
|<span data-ttu-id="91249-221">已標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="91249-221">Junked</span></span>|<span data-ttu-id="91249-222">已取代</span><span class="sxs-lookup"><span data-stu-id="91249-222">Replaced</span></span>|

<span data-ttu-id="91249-223">傳遞位置顯示原則和執行傳遞後偵測的結果。</span><span class="sxs-lookup"><span data-stu-id="91249-223">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="91249-224">其連結到「傳遞動作」。</span><span class="sxs-lookup"><span data-stu-id="91249-224">It's linked to a Delivery Action.</span></span> <span data-ttu-id="91249-225">已新增此欄位，以深入了解找到問題電子郵件時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="91249-225">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="91249-226">以下是傳遞位置可能的值：</span><span class="sxs-lookup"><span data-stu-id="91249-226">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="91249-227">**收件匣或資料夾**：電子郵件位於收件匣或資料夾中 (根據您的電子郵件規則)。</span><span class="sxs-lookup"><span data-stu-id="91249-227">**Inbox or folder**: The email is in inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="91249-228">**部署或外部**：信箱不存在於雲端上，但為內部部署。</span><span class="sxs-lookup"><span data-stu-id="91249-228">**On-prem or external**: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="91249-229">**垃圾郵件資料夾**：電子郵件位於使用者的 [垃圾郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="91249-229">**Junk folder**: The email is in the Junk folder of a user.</span></span>
- <span data-ttu-id="91249-230">**刪除的郵件資料夾**：電子郵件位於使用者的 [刪除的郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="91249-230">**Deleted items folder**: The email in the Deleted items folder of a user.</span></span>
- <span data-ttu-id="91249-231">**隔離**：隔離中的電子郵件，而不是使用者信箱中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="91249-231">**Quarantine**: The email in quarantine, and is not in a user's mailbox.</span></span>
- <span data-ttu-id="91249-232">**失敗**；電子郵件無法傳遞至信箱。</span><span class="sxs-lookup"><span data-stu-id="91249-232">**Failed**: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="91249-233">**已捨棄**：電子郵件在郵件流程的某處遺失。</span><span class="sxs-lookup"><span data-stu-id="91249-233">**Dropped**: The email gets lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="91249-234">電子郵件時間表</span><span class="sxs-lookup"><span data-stu-id="91249-234">Email timeline</span></span>

<span data-ttu-id="91249-235">**電子郵件時間表**是總管的另一個新功能，目標是提升系統管理員的搜捕體驗。</span><span class="sxs-lookup"><span data-stu-id="91249-235">The **Email Timeline** is another new Explorer feature aimed at making the hunting experience better for admins.</span></span> <span data-ttu-id="91249-236">這可減少不規則性，因為花較少的時間檢查不同位置以嘗試了解事件。</span><span class="sxs-lookup"><span data-stu-id="91249-236">It cuts down on randomization because there is less time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="91249-237">當多個事件同時或接近同時發生在某電子郵件時，這些事件會出現在時刻表檢視。</span><span class="sxs-lookup"><span data-stu-id="91249-237">When multiple events happen at, or close to, the same time on an email, those events will show up in a timeline view.</span></span> <span data-ttu-id="91249-238">事實上，某些在傳遞郵件後發生的事件會由「特殊動作」欄擷取。</span><span class="sxs-lookup"><span data-stu-id="91249-238">In fact, some events that happen post-delivery to your mail will be captured in the 'Special action' column.</span></span> <span data-ttu-id="91249-239">透過結合該郵件在時間表的資訊和傳遞郵件後採取的特殊動作，能讓系統管理員深入了解其原則的運作方式、郵件最後路由傳送的位置，以及在某些情況下最終評估的內容。</span><span class="sxs-lookup"><span data-stu-id="91249-239">Combining the information from the timeline of that mail with the special action taken on the mail post-delivery will give admins insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="91249-240">如需有關調查惡意電子郵件訊息的詳細討論，請參閱 [調查並修復 Office 365 中傳遞的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)。</span><span class="sxs-lookup"><span data-stu-id="91249-240">For more discussion about investigating malicious email messages, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="91249-241">匯出 URL 點擊資料</span><span class="sxs-lookup"><span data-stu-id="91249-241">Export URL click data</span></span>

<span data-ttu-id="91249-242">此外，您現在可以將 URL 點選的報告匯出到 Microsoft Excel 中，以便檢視其 [網路郵件識別碼] 以及 [按一下結果]，從而更容易了解 URL 點擊流量的來源。</span><span class="sxs-lookup"><span data-stu-id="91249-242">Also, you will now be able to export reports for URL clicks to Microsoft Excel in order to view both their Network Message ID, and their Click Verdict, making the task of understanding where your URL click traffic originated easier.</span></span> <span data-ttu-id="91249-243">以下說明運作方式。</span><span class="sxs-lookup"><span data-stu-id="91249-243">Here's how it works.</span></span> <span data-ttu-id="91249-244">在 Office 365 的威脅管理快速啟動中開啟，按一下此鏈結：</span><span class="sxs-lookup"><span data-stu-id="91249-244">Starting in Threat Management on the Office 365 quick-launch, click through this chain:</span></span>

<span data-ttu-id="91249-245">**瀏覽器** \>**查看網路釣魚** \>**按一下** \>Top **URLs 或 URL 上擊** \>**按一下任一筆記錄開啟 URL 彈出**視窗</span><span class="sxs-lookup"><span data-stu-id="91249-245">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs or URL Top Clicks** \> **Click on any record to open URL flyout**</span></span>

<span data-ttu-id="91249-246">當您按一下清單中的 URL 時，將會在飛出面版上看到新的 [匯出] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="91249-246">When you click on a URL in the list, you'll see a new Export button on the fly-out panel.</span></span> <span data-ttu-id="91249-247">使用此按鈕將資料移至 Excel 試算表，以便更輕鬆地進行報告。</span><span class="sxs-lookup"><span data-stu-id="91249-247">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="91249-248">您可以在即時偵測報告中取得相同的位置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="91249-248">You can get to the same location in the real-time detections report as follows:</span></span>

<span data-ttu-id="91249-249">**瀏覽器** \>**即時偵測** \>**查看網路釣魚** \>**URLs** \>**上 URLs 或上按一下** \>**按一下任一筆記錄開啟 URL 彈出** \> 視窗**流覽至 [點擊]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="91249-249">**Explorer** \> **Real-time Detections** \> **View Phish** \> **URLs** \> **Top URLs or Top Clicks** \> **Click on any record to open URL flyout** \> **Navigate to the Clicks Tab.**</span></span>

> [!TIP]
> <span data-ttu-id="91249-250">當您透過網路郵件識別碼在總管或關聯的協力廠商工具中進行搜尋時，網路郵件識別碼會將點擊返回對應到特定的郵件。</span><span class="sxs-lookup"><span data-stu-id="91249-250">Network Message ID maps the click back to specific mails when you search through Explorer or associated 3rd party tools via Network Message ID.</span></span> <span data-ttu-id="91249-251">搜尋網路郵件識別碼時，系統會提供系統管理員與點擊結果相關聯的特定電子郵件。</span><span class="sxs-lookup"><span data-stu-id="91249-251">Searching through the Network Message ID will give admins the specific email associated with a click result.</span></span> <span data-ttu-id="91249-252">匯出時，網路郵件識別碼的關聯識別可提供更快且更強大的分析。</span><span class="sxs-lookup"><span data-stu-id="91249-252">On export having, the correlating identification of Network Message ID makes for quicker and more powerful analysis.</span></span>

![tp_ExportClickResultAndNetworkID.png](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="91249-254">查看透過技術在電子郵件中偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="91249-254">See malware detected in email by technology</span></span>

<span data-ttu-id="91249-255">假設您想要查看 Microsoft 365 技術在電子郵件中偵測到惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="91249-255">Suppose you want to see malware detected in email, by Microsoft 365 technology.</span></span> <span data-ttu-id="91249-256">若要這麼做，請使用總管 (或即時偵測) 的 [[電子郵件] > [惡意程式碼]](threat-explorer-views.md#email--malware) 檢視。</span><span class="sxs-lookup"><span data-stu-id="91249-256">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="91249-257">在安全性與合規性中心 ([https://protection.office.com](https://protection.office.com)) 選擇 **[威脅管理]** > **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="91249-257">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="91249-258">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="91249-258">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="91249-259">在 **[檢視]** 功能表中，選擇 **[電子郵件]** > **[惡意程式碼 ]**。</span><span class="sxs-lookup"><span data-stu-id="91249-259">In the **View** menu, choose **Email** > **Malware**.</span></span>

   ![總管的檢視功能表](../../media/ExplorerViewEmailMalwareMenu.png)

3. <span data-ttu-id="91249-261">按一下 **[寄件者]**，然後選擇 **[基本]** > **[偵測技術]**。</span><span class="sxs-lookup"><span data-stu-id="91249-261">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span>

   <span data-ttu-id="91249-262">您的偵測技術現在可做為報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="91249-262">Your detection technologies are now available as filters for the report.</span></span>

   ![惡意程式碼偵測技術](../../media/ExplorerEmailMalwareDetectionTech.png)

4. <span data-ttu-id="91249-264">選取一個選項，然後按一下 **[重新整理]** 按鈕來套用該篩選器。</span><span class="sxs-lookup"><span data-stu-id="91249-264">Select an option, and then click the **Refresh** button to apply that filter.</span></span>

   ![選取的偵測技術](../../media/ExplorerEmailMalwareDetectionTechATP.png)

<span data-ttu-id="91249-266">報告會使用您所選取的技術選項重新整理，以顯示在電子郵件中偵測到的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="91249-266">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="91249-267">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="91249-267">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="91249-268">檢視網路釣魚 URL 並按一下結果</span><span class="sxs-lookup"><span data-stu-id="91249-268">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="91249-269">假設您想要查看透過電子郵件中的 URL 進行的網路釣魚攻擊，包括允許、封鎖及覆寫的 URL 清單。</span><span class="sxs-lookup"><span data-stu-id="91249-269">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="91249-270">若要識別已按過的 URL，則必須設定 [ATP 安全連結](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="91249-270">Identifying URLs that were clicked requires [ATP Safe links](atp-safe-links.md) to be configured.</span></span> <span data-ttu-id="91249-271">請確認您已針對點擊時保護和 ATP 安全連結的按一下結果記錄設定 [ATP 安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="91249-271">Make sure that you have set up [ATP Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by ATP Safe Links.</span></span>

<span data-ttu-id="91249-272">若要檢閱郵件中的網路釣魚 URL 和網路釣魚郵件中的 URL 點擊，請使用總管 (或即時偵測) 的 [[電子郵件] > [網路釣魚]](threat-explorer-views.md#email--phish) 檢視。</span><span class="sxs-lookup"><span data-stu-id="91249-272">To review phish URLs in messages and clicks on URLs in phish messages, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="91249-273">在安全性與合規性中心 ([https://protection.office.com](https://protection.office.com)) 選擇 **[威脅管理]** > **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="91249-273">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="91249-274">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="91249-274">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="91249-275">在 **[檢視]** 功能表中，選擇 **[電子郵件]** > **[網路釣魚]**。</span><span class="sxs-lookup"><span data-stu-id="91249-275">In the **View** menu, choose **Email** > **Phish**.</span></span>

   ![總管的檢視功能表](../../media/ExplorerViewEmailPhishMenu.png)

3. <span data-ttu-id="91249-277">按一下 **[寄件者]**，然後選擇 **[URL]** > **按一下結果**。</span><span class="sxs-lookup"><span data-stu-id="91249-277">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>

4. <span data-ttu-id="91249-278">選取一或多個選項，例如 **[已封鎖]** 和 **[封鎖覆寫]**，然後按一下要套用該篩選器的選項同一行上的 **[重新整理]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="91249-278">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button that is on the same line as the options to apply that filter.</span></span> <span data-ttu-id="91249-279">(請勿重新整理瀏覽器視窗。)</span><span class="sxs-lookup"><span data-stu-id="91249-279">(Don't refresh your browser window.)</span></span>

   ![URL 和按一下結果](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

    <span data-ttu-id="91249-281">報告會重新整理以在報告下的 [URL] 索引標籤上顯示兩個不同的 URL 表格：</span><span class="sxs-lookup"><span data-stu-id="91249-281">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="91249-282">**[熱門 URL]** 為已篩選的郵件中的 URL，而電子郵件傳送動作會計算每個 URL。</span><span class="sxs-lookup"><span data-stu-id="91249-282">**Top URLs** are the URLs contained in the messages you have filtered down to, and the email delivery action counts for each URL.</span></span> <span data-ttu-id="91249-283">在網路釣魚電子郵件檢視中，此清單通常會包含合法的 URL。</span><span class="sxs-lookup"><span data-stu-id="91249-283">In the phish email view, this list typically will contain legitimate URLs.</span></span> <span data-ttu-id="91249-284">攻擊者會在這些郵件中混雜善意和惡意的 URL，以試圖傳遞這些郵件，但他們會讓惡意連結看起來更加有趣，以誘使使用者點擊。</span><span class="sxs-lookup"><span data-stu-id="91249-284">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they will make the malicious links more interesting for the user to click.</span></span> <span data-ttu-id="91249-285">URLs 的表格依電子郵件總數 (排序，但是請注意，此欄位是隱藏的，可簡化 view) 。</span><span class="sxs-lookup"><span data-stu-id="91249-285">The table of URLs is sorted by total email count (but note that this column is hidden to simplify the view).</span></span>

   - <span data-ttu-id="91249-286">**[熱門點擊]** 為點擊過的包含在安全連結中的 URL，並依總點擊數排序 (為了簡化檢視，此欄也不會顯示)。</span><span class="sxs-lookup"><span data-stu-id="91249-286">**Top clicks** are the Safe Links wrapped URLs that were clicked, sorted by total click count (this column is also not shown to simplify the view).</span></span> <span data-ttu-id="91249-287">依資料行的總計數表示每個點擊過的 URL 的安全連結按一下結果計數。</span><span class="sxs-lookup"><span data-stu-id="91249-287">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="91249-288">在網路釣魚電子郵件視圖中，這些都很經常是可疑或惡意的 URLs，但可能包含不具威脅但位於網路釣魚郵件中的 URLs。</span><span class="sxs-lookup"><span data-stu-id="91249-288">In the phish email view, these are more often suspicious or malicious URLs, but could include URLs that are not threats but are in phish messages.</span></span> <span data-ttu-id="91249-289">已開啟的連結 URL 點擊不會顯示在這裡。</span><span class="sxs-lookup"><span data-stu-id="91249-289">URL clicks on unwrapped links will not show up here.</span></span>

   <span data-ttu-id="91249-290">兩個 URL 表格依傳遞動作和位置顯示網路釣魚電子郵件訊息熱門 URL，並顯示已封鎖的 URL 點擊 (或儘管已警告卻仍造訪的 URL)，讓您了解使用者接收到及互動的潛在惡意連結。</span><span class="sxs-lookup"><span data-stu-id="91249-290">The two URL tables show top URLs in phishing email messages by delivery action and location, and they show URL clicks that were blocked (or visited despite a warning) so that you can understand what potential bad links were received by users and interacted with by users.</span></span> <span data-ttu-id="91249-291">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="91249-291">From here, you can conduct further analysis.</span></span> <span data-ttu-id="91249-292">例如，在圖表的下方，您可以查看貴組織環境中封鎖的電子郵件訊息熱門 URL。</span><span class="sxs-lookup"><span data-stu-id="91249-292">For example, below the chart, you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   ![已封鎖的總管 URL](../../media/ExplorerPhishClickVerdictURLs.png)

   <span data-ttu-id="91249-294">選取 URL 以檢視更多詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="91249-294">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="91249-295">在 [URL 飛入] 對話方塊中，會移除電子郵件上的篩選，以顯示您環境中 URL 公開的完整視圖。</span><span class="sxs-lookup"><span data-stu-id="91249-295">In the URL flyout dialog, the filtering on email messages is removed to show you the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="91249-296">這能讓您在總管中篩選出擔心的電子郵件訊息，找出具有潛在威脅的特定 URL，然後了解暴露於環境 (經由 URL 詳細資料對話方塊) 中的 URL，而不需要將 URL 篩選新增至總管檢視本身。</span><span class="sxs-lookup"><span data-stu-id="91249-296">This lets you filter down email messages in Explorer to ones you are concerned about, find specific URLs that are potential threats, then expand your understanding of the URL exposure in your environment (via the URL details dialog) without having to add URL filters to the Explorer view itself.</span></span>


<span data-ttu-id="91249-297">**不同按一下 verdicts 的轉譯**</span><span class="sxs-lookup"><span data-stu-id="91249-297">**Interpretation of different click verdicts**</span></span>

<span data-ttu-id="91249-298">在電子郵件或 URL flyouts 中，按一下上方和篩選體驗內，您會在搜尋體驗的一部分看到不同的按一下值。</span><span class="sxs-lookup"><span data-stu-id="91249-298">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you will see different click values as part of your hunting experience.</span></span> <span data-ttu-id="91249-299">以下是按一下 Verdicts 及其轉譯的可能值：</span><span class="sxs-lookup"><span data-stu-id="91249-299">Below are the possible values of Click Verdicts and their interpretation:</span></span>

- <span data-ttu-id="91249-300">**無**：我們無法捕獲 URL 的判定。</span><span class="sxs-lookup"><span data-stu-id="91249-300">**None**: We were unable to capture the verdict for the URL.</span></span> <span data-ttu-id="91249-301">使用者可能已按一下透過 URL。</span><span class="sxs-lookup"><span data-stu-id="91249-301">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="91249-302">**允許**：允許使用者流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="91249-302">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="91249-303">已**封鎖**：已封鎖使用者流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="91249-303">**Blocked**: The User was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="91249-304">**擱置的判定**：使用者已呈現「引爆擱置」頁面。</span><span class="sxs-lookup"><span data-stu-id="91249-304">**Pending verdict**: The user was presented with the detonation pending page.</span></span>
- <span data-ttu-id="91249-305">**封鎖已封鎖**：已封鎖使用者流覽至 URL;不過，使用者 overrode 區塊以流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="91249-305">**Blocked overridden**: The user was blocked from navigating to the URL; however, the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="91249-306">**擱置的判定略過**：使用者呈現的是引爆頁面;不過，使用者 overrode 頁面以流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="91249-306">**Pending verdict bypassed**: The user was presented with the detonation page; however, the user overrode the page to navigate to the URL.</span></span>
- <span data-ttu-id="91249-307">**錯誤**：使用者已呈現錯誤頁面。</span><span class="sxs-lookup"><span data-stu-id="91249-307">**Error**: The user was presented with the error page.</span></span> <span data-ttu-id="91249-308">這也可能表示在捕獲判定時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="91249-308">This can also mean there was an error in capturing the verdict.</span></span>
- <span data-ttu-id="91249-309">**失敗**：捕獲判定時，發生未知的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="91249-309">**Failure**: There was unknown exception while capturing the verdict.</span></span> <span data-ttu-id="91249-310">使用者可能已按一下透過 URL。</span><span class="sxs-lookup"><span data-stu-id="91249-310">The user might have clicked through the URL.</span></span> 

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="91249-311">檢閱使用者回報的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="91249-311">Review email messages reported by users</span></span>

<span data-ttu-id="91249-312">假設您想透過使用 [Outlook 和 Outlook 網頁版的回報郵件增益集](enable-the-report-message-add-in.md)來查看貴組織使用者回報為「垃圾郵件」、「非垃圾郵件」或「網路釣魚」的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="91249-312">Suppose that you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="91249-313">若要這麼做，請使用總管 (或即時偵測) 的 [[電子郵件] > [提交]](threat-explorer-views.md#email--submissions) 檢視。</span><span class="sxs-lookup"><span data-stu-id="91249-313">To do this, use the [Email > Submissions](threat-explorer-views.md#email--submissions) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="91249-314">在安全性與合規性中心 ([https://protection.office.com](https://protection.office.com)) 選擇 **[威脅管理]** > **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="91249-314">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="91249-315">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="91249-315">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="91249-316">在 **[檢視]** 功能表中，選擇 **[電子郵件]** > **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="91249-316">In the **View** menu, choose **Email** > **Submissions**.</span></span>

   ![總管的檢視功能表](../../media/explorer-view-menu-email-user-reported.png)

3. <span data-ttu-id="91249-318">按一下 **[寄件者]**，然後選擇 **[基本]** > **[回報類型]**。</span><span class="sxs-lookup"><span data-stu-id="91249-318">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>

4. <span data-ttu-id="91249-319">選取一個選項，例如 **[網路釣魚]**，然後按一下 **[重新整理]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="91249-319">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span>

   ![使用者回報的網路釣魚](../../media/EmailUserReportedReportType.png)

<span data-ttu-id="91249-321">報告會重新整理，顯示貴組織中的人員回報為網路釣魚攻擊的電子郵件相關資料。</span><span class="sxs-lookup"><span data-stu-id="91249-321">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="91249-322">您可以使用此資訊來進行進一步分析，並視需要調整 [ATP 防網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="91249-322">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="91249-323">啟動自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="91249-323">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="91249-324">**Office 365 ATP 方案 2** 和 **Office 365 E5** 提供自動化調查及回應功能。</span><span class="sxs-lookup"><span data-stu-id="91249-324">Automated investigation and response capabilities are available in **Office 365 ATP Plan 2** and **Office 365 E5**.</span></span>

<span data-ttu-id="91249-325">(新增！) [自動化調查及回應](automated-investigation-response-office.md)能為您的安全性作業小組節省許多時間和精力來調查及降低網路攻擊。</span><span class="sxs-lookup"><span data-stu-id="91249-325">(NEW!) [Automated investigation and response](automated-investigation-response-office.md) can save your security operations team much time and effort in investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="91249-326">除了設定會觸發安全性劇本的警示，您可以在總管中的檢視啟動自動化調查及回應程序。</span><span class="sxs-lookup"><span data-stu-id="91249-326">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span>

<span data-ttu-id="91249-327">如需這方面的詳細資訊，請參閱[範例：安全性系統管理員從總管觸發調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="91249-327">For details on this, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a><span data-ttu-id="91249-328">更多使用總管 (或即時偵測) 的方法</span><span class="sxs-lookup"><span data-stu-id="91249-328">More ways to use Explorer (or real-time detections)</span></span>

<span data-ttu-id="91249-329">除了這篇文章所述的案例，總管 (或即時偵測) 還有更多回報選項。</span><span class="sxs-lookup"><span data-stu-id="91249-329">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or real-time detections).</span></span>

- [<span data-ttu-id="91249-330">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="91249-330">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="91249-331">檢視在 SharePoint Online、OneDrive 和 Microsoft Teams 中偵測到的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="91249-331">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="91249-332">取得威脅總管 (和即時偵測) 檢視的概觀</span><span class="sxs-lookup"><span data-stu-id="91249-332">Get an overview of the views in Threat Explorer (and real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="91249-333">Microsoft 威脅防護的自動化調查及回應</span><span class="sxs-lookup"><span data-stu-id="91249-333">Automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="91249-334">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="91249-334">Required licenses and permissions</span></span>

<span data-ttu-id="91249-335">您必須具備 [Office 365 ATP](office-365-atp.md) 才能取得總管或即時偵測。</span><span class="sxs-lookup"><span data-stu-id="91249-335">You must have [Office 365 ATP](office-365-atp.md) to get Explorer or real-time detections.</span></span>

- <span data-ttu-id="91249-336">總管會包含在 Office 365 ATP 方案 2。</span><span class="sxs-lookup"><span data-stu-id="91249-336">Explorer is included in Office 365 ATP Plan 2.</span></span>
- <span data-ttu-id="91249-337">即時偵測報告會包含在 Office 365 ATP 方案 1。</span><span class="sxs-lookup"><span data-stu-id="91249-337">The real-time detections report is included in Office 365 ATP Plan 1.</span></span>
- <span data-ttu-id="91249-338">請計劃指派授權給所有應受 Office 365 ATP 保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="91249-338">Plan to assign licenses for all users who should be protected by Office 365 ATP.</span></span> <span data-ttu-id="91249-339">(總管或即時偵測會為經過授權的使用者顯示偵測資料。)</span><span class="sxs-lookup"><span data-stu-id="91249-339">(Explorer or real-time detections shows detection data for licensed users.)</span></span>

<span data-ttu-id="91249-340">若要檢視及使用總管或即時偵測，您必須具有適當的權限，例如授與安全性系統管理員或安全性讀取者的權限。</span><span class="sxs-lookup"><span data-stu-id="91249-340">To view and use Explorer or real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="91249-341">針對「安全性與合規性中心」，您必須受指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="91249-341">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="91249-342">組織管理</span><span class="sxs-lookup"><span data-stu-id="91249-342">Organization Management</span></span>
  - <span data-ttu-id="91249-343">安全性系統管理員 (這可以在 Azure Active Directory 系統管理中心指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="91249-343">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="91249-344">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="91249-344">Security Reader</span></span>

- <span data-ttu-id="91249-345">針對 Exchange Online，您必須在 Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)) 受指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="91249-345">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="91249-346">組織管理</span><span class="sxs-lookup"><span data-stu-id="91249-346">Organization Management</span></span>
  - <span data-ttu-id="91249-347">僅檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="91249-347">View-only Organization Management</span></span>
  - <span data-ttu-id="91249-348">僅檢視收件者角色</span><span class="sxs-lookup"><span data-stu-id="91249-348">View-Only Recipients role</span></span>
  - <span data-ttu-id="91249-349">合規性管理</span><span class="sxs-lookup"><span data-stu-id="91249-349">Compliance Management</span></span>

<span data-ttu-id="91249-350">若要深入了解角色和權限，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="91249-350">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="91249-351">安全性與 &amp; 合規性中心的許可權</span><span class="sxs-lookup"><span data-stu-id="91249-351">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="91249-352">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="91249-352">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="91249-353">威脅瀏覽器與即時偵測的某些差異</span><span class="sxs-lookup"><span data-stu-id="91249-353">Some differences between Threat Explorer and real-time detections</span></span>

- <span data-ttu-id="91249-354">Office 365 ATP 方案 1 提供**即時偵測**報告，而 Office 365 ATP 方案 2 提供**威脅總管**。</span><span class="sxs-lookup"><span data-stu-id="91249-354">The **real-time detections** report is available in Office 365 ATP Plan 1, whereas **Threat Explorer** is available in Office 365 ATP Plan 2.</span></span>
- <span data-ttu-id="91249-355">**即時偵測**報告可讓您即時檢視偵測。</span><span class="sxs-lookup"><span data-stu-id="91249-355">The **real-time detections** report allows you to view detections in real-time.</span></span> <span data-ttu-id="91249-356">**威脅總管**也有這個功能，但也能讓您檢視特定攻擊的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="91249-356">**Threat Explorer** does this as well, but also allows you to view additional details for a given attack.</span></span>
- <span data-ttu-id="91249-357">**所有的電子郵件**view 均可在**威脅瀏覽器**中 (，而不會在**即時**偵測報告) 中。</span><span class="sxs-lookup"><span data-stu-id="91249-357">An **All email** view is available in **Threat Explorer** (and is not in the **real-time detections** report).</span></span>
- <span data-ttu-id="91249-358">**威脅瀏覽器**中包含更多篩選功能和可用的動作。</span><span class="sxs-lookup"><span data-stu-id="91249-358">More filtering capabilities and available actions are included in **Threat Explorer**.</span></span>

<span data-ttu-id="91249-359">如需詳細資訊，請參閱 [Office 365 ATP 服務說明：各高級威脅防護的功能可用性 (ATP) 方案](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="91249-359">For more details, see [Office 365 ATP Service Description: Feature availability across Advanced Threat Protection (ATP) plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>
