---
title: Microsoft Defender AV 事件 IDs 和錯誤碼
description: 查詢 Microsoft Defender 防病毒事件的原因和解決方案 IDs 和錯誤
keywords: 事件、錯誤碼、siem、記錄、疑難排解、wef、windows 事件轉移
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f7e8d6428360e5fe45a377f3ed6611a76f0a7911
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765812"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="35125-104">檢查事件記錄檔和錯誤碼，以疑難排解 Microsoft Defender 防病毒的問題</span><span class="sxs-lookup"><span data-stu-id="35125-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="35125-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="35125-105">**Applies to:**</span></span>

- [<span data-ttu-id="35125-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="35125-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="35125-107">如果您遇到 Microsoft Defender 防病毒的問題，您可以搜尋本主題中的表格，以找出相符的問題和可能的解決方案。</span><span class="sxs-lookup"><span data-stu-id="35125-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="35125-108">[資料表] 清單：</span><span class="sxs-lookup"><span data-stu-id="35125-108">The tables list:</span></span>

- <span data-ttu-id="35125-109">[Microsoft Defender 防病毒事件 IDs](#windows-defender-av-ids) (這兩種都適用于 windows 10 和 windows Server 2016) </span><span class="sxs-lookup"><span data-stu-id="35125-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="35125-110">Microsoft Defender 防病毒用戶端錯誤碼</span><span class="sxs-lookup"><span data-stu-id="35125-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="35125-111">內部 Microsoft Defender 防病毒用戶端錯誤碼 (由 Microsoft 在開發和測試期間使用) </span><span class="sxs-lookup"><span data-stu-id="35125-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="35125-112">您也可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Microsoft Defender for Endpoint 示範網站，以確認下列功能正在運作：</span><span class="sxs-lookup"><span data-stu-id="35125-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="35125-113">雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="35125-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="35125-114">Fast 教學 (包括第一次看到區塊) </span><span class="sxs-lookup"><span data-stu-id="35125-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="35125-115">可能有害的應用程式封鎖</span><span class="sxs-lookup"><span data-stu-id="35125-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="35125-116">Microsoft Defender 防病毒事件 IDs</span><span class="sxs-lookup"><span data-stu-id="35125-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="35125-117">Windows 事件記錄檔中 IDs 的 Microsoft Defender 防病毒記錄事件。</span><span class="sxs-lookup"><span data-stu-id="35125-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="35125-118">您可以直接查看事件記錄檔，或者，如果您有協力廠商的安全性資訊和事件管理 (SIEM) 工具，也可以使用 [Microsoft Defender 防病毒用戶端事件 IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) 從您的終結點檢查特定的事件及錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="35125-119">本節中的表格列出主要 Microsoft Defender 防病毒事件 IDs，並在可能的情況下，提供修正或解決錯誤的建議解決方案。</span><span class="sxs-lookup"><span data-stu-id="35125-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="35125-120">若要查看 Microsoft Defender 防病毒事件</span><span class="sxs-lookup"><span data-stu-id="35125-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="35125-121">開啟 **事件檢視器**。</span><span class="sxs-lookup"><span data-stu-id="35125-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="35125-122">在主控台樹中，依次展開 [ **應用程式及服務記錄**]、[ **Microsoft**]、[ **Windows**] 及 [ **windows Defender**]。</span><span class="sxs-lookup"><span data-stu-id="35125-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="35125-123">按兩下 [ **操作**]。</span><span class="sxs-lookup"><span data-stu-id="35125-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="35125-124">在詳細資料窗格中，查看個別事件的清單，以尋找您的事件。</span><span class="sxs-lookup"><span data-stu-id="35125-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="35125-125">按一下該事件，在 [ **一般** ] 和 [ **詳細資料** ] 索引標籤底下的下部窗格中查看事件的特定詳細資料。</span><span class="sxs-lookup"><span data-stu-id="35125-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="35125-126">事件 ID: 1000</span><span class="sxs-lookup"><span data-stu-id="35125-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="35125-127">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="35125-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-129">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-129">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-130">
<b>已開始反惡意軟體掃描。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="35125-131">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="35125-132">
<dt>掃描 ID: &lt;相關掃描的識別碼 &gt; 號碼。</dt> 
<dt>掃描類型： &lt; 掃描類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-133">防毒</span><span class="sxs-lookup"><span data-stu-id="35125-133">Antivirus</span></span></li>
<li><span data-ttu-id="35125-134">間諜</span><span class="sxs-lookup"><span data-stu-id="35125-134">Antispyware</span></span></li>
<li><span data-ttu-id="35125-135">軟體</span><span class="sxs-lookup"><span data-stu-id="35125-135">Antimalware</span></span></li>
</ul><span data-ttu-id="35125-136">
</dt>
<dt>掃描參數： &lt; 掃描參數 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-137">完整掃描</span><span class="sxs-lookup"><span data-stu-id="35125-137">Full scan</span></span></li>
<li><span data-ttu-id="35125-138">快速掃描</span><span class="sxs-lookup"><span data-stu-id="35125-138">Quick scan</span></span></li>
<li><span data-ttu-id="35125-139">客戶掃描</span><span class="sxs-lookup"><span data-stu-id="35125-139">Customer scan</span></span></li>
</ul><span data-ttu-id="35125-140">
</dt>
<dt>掃描資源： &lt;資源 (例如已掃描的 files/directory/BHO) 。 &gt; </dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-141">事件 ID: 1001</span><span class="sxs-lookup"><span data-stu-id="35125-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-142">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-144">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-144">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-145">
<b>反惡意軟體掃描完成。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-146">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="35125-147">
<dt>掃描 ID: &lt;相關掃描的識別碼 &gt; 號碼。</dt> 
<dt>掃描類型： &lt; 掃描類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-148">防毒</span><span class="sxs-lookup"><span data-stu-id="35125-148">Antivirus</span></span></li>
<li><span data-ttu-id="35125-149">間諜</span><span class="sxs-lookup"><span data-stu-id="35125-149">Antispyware</span></span></li>
<li><span data-ttu-id="35125-150">軟體</span><span class="sxs-lookup"><span data-stu-id="35125-150">Antimalware</span></span></li>
</ul><span data-ttu-id="35125-151">
</dt>
<dt>掃描參數： &lt; 掃描參數 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-152">完整掃描</span><span class="sxs-lookup"><span data-stu-id="35125-152">Full scan</span></span></li>
<li><span data-ttu-id="35125-153">快速掃描</span><span class="sxs-lookup"><span data-stu-id="35125-153">Quick scan</span></span></li>
<li><span data-ttu-id="35125-154">客戶掃描</span><span class="sxs-lookup"><span data-stu-id="35125-154">Customer scan</span></span></li>
</ul><span data-ttu-id="35125-155">
</dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
<dt>掃描時間： &lt; 掃描的持續時間。 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-156">事件 ID: 1002</span><span class="sxs-lookup"><span data-stu-id="35125-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-157">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-159">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-159">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-160">
<b>反惡意軟體掃描在完成前已停止。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-161">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="35125-162">
<dt>掃描 ID: &lt;相關掃描的識別碼 &gt; 號碼。</dt> 
<dt>掃描類型： &lt; 掃描類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-163">防毒</span><span class="sxs-lookup"><span data-stu-id="35125-163">Antivirus</span></span></li>
<li><span data-ttu-id="35125-164">間諜</span><span class="sxs-lookup"><span data-stu-id="35125-164">Antispyware</span></span></li>
<li><span data-ttu-id="35125-165">軟體</span><span class="sxs-lookup"><span data-stu-id="35125-165">Antimalware</span></span></li>
</ul><span data-ttu-id="35125-166">
</dt>
<dt>掃描參數： &lt; 掃描參數 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-167">完整掃描</span><span class="sxs-lookup"><span data-stu-id="35125-167">Full scan</span></span></li>
<li><span data-ttu-id="35125-168">快速掃描</span><span class="sxs-lookup"><span data-stu-id="35125-168">Quick scan</span></span></li>
<li><span data-ttu-id="35125-169">客戶掃描</span><span class="sxs-lookup"><span data-stu-id="35125-169">Customer scan</span></span></li>
</ul><span data-ttu-id="35125-170">
</dt>
<dt>使用者： &lt;網域 &gt; &amp; lt;使用者 &gt; </dt>
<dt>掃描時間： &lt; 掃描的持續時間。 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-171">事件 ID: 1003</span><span class="sxs-lookup"><span data-stu-id="35125-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-172">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-174">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-174">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-175">
<b>已暫停反惡意程式碼掃描。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-176">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="35125-177">
<dt>掃描 ID: &lt;相關掃描的識別碼 &gt; 號碼。</dt> 
<dt>掃描類型： &lt; 掃描類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-178">防毒</span><span class="sxs-lookup"><span data-stu-id="35125-178">Antivirus</span></span></li>
<li><span data-ttu-id="35125-179">間諜</span><span class="sxs-lookup"><span data-stu-id="35125-179">Antispyware</span></span></li>
<li><span data-ttu-id="35125-180">軟體</span><span class="sxs-lookup"><span data-stu-id="35125-180">Antimalware</span></span></li>
</ul><span data-ttu-id="35125-181">
</dt>
<dt>掃描參數： &lt; 掃描參數 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-182">完整掃描</span><span class="sxs-lookup"><span data-stu-id="35125-182">Full scan</span></span></li>
<li><span data-ttu-id="35125-183">快速掃描</span><span class="sxs-lookup"><span data-stu-id="35125-183">Quick scan</span></span></li>
<li><span data-ttu-id="35125-184">客戶掃描</span><span class="sxs-lookup"><span data-stu-id="35125-184">Customer scan</span></span></li>
</ul><span data-ttu-id="35125-185">
</dt>
<dt>使用者： &lt; 網域 &gt; \& lt;使用者&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-186">事件 ID: 1004</span><span class="sxs-lookup"><span data-stu-id="35125-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-187">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-189">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-189">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-190">
<b>已繼續反惡意程式碼掃描。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-191">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="35125-192">
<dt>掃描 ID: &lt;相關掃描的識別碼 &gt; 號碼。</dt> 
<dt>掃描類型： &lt; 掃描類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-193">防毒</span><span class="sxs-lookup"><span data-stu-id="35125-193">Antivirus</span></span></li>
<li><span data-ttu-id="35125-194">間諜</span><span class="sxs-lookup"><span data-stu-id="35125-194">Antispyware</span></span></li>
<li><span data-ttu-id="35125-195">軟體</span><span class="sxs-lookup"><span data-stu-id="35125-195">Antimalware</span></span></li>
</ul><span data-ttu-id="35125-196">
</dt>
<dt>掃描參數： &lt; 掃描參數 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-197">完整掃描</span><span class="sxs-lookup"><span data-stu-id="35125-197">Full scan</span></span></li>
<li><span data-ttu-id="35125-198">快速掃描</span><span class="sxs-lookup"><span data-stu-id="35125-198">Quick scan</span></span></li>
<li><span data-ttu-id="35125-199">客戶掃描</span><span class="sxs-lookup"><span data-stu-id="35125-199">Customer scan</span></span></li>
</ul><span data-ttu-id="35125-200">
</dt>
<dt>使用者： &lt; 網域 &gt; \& lt;使用者&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-201">事件 ID: 1005</span><span class="sxs-lookup"><span data-stu-id="35125-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-202">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-204">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-204">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-205">
<b>反惡意軟體掃描失敗。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-206">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="35125-207">
<dt>掃描 ID: &lt;相關掃描的識別碼 &gt; 號碼。</dt> 
<dt>掃描類型： &lt; 掃描類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-208">防毒</span><span class="sxs-lookup"><span data-stu-id="35125-208">Antivirus</span></span></li>
<li><span data-ttu-id="35125-209">間諜</span><span class="sxs-lookup"><span data-stu-id="35125-209">Antispyware</span></span></li>
<li><span data-ttu-id="35125-210">軟體</span><span class="sxs-lookup"><span data-stu-id="35125-210">Antimalware</span></span></li>
</ul><span data-ttu-id="35125-211">
</dt>
<dt>掃描參數： &lt; 掃描參數 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-212">完整掃描</span><span class="sxs-lookup"><span data-stu-id="35125-212">Full scan</span></span></li>
<li><span data-ttu-id="35125-213">快速掃描</span><span class="sxs-lookup"><span data-stu-id="35125-213">Quick scan</span></span></li>
<li><span data-ttu-id="35125-214">客戶掃描</span><span class="sxs-lookup"><span data-stu-id="35125-214">Customer scan</span></span></li>
</ul><span data-ttu-id="35125-215">
</dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-216">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-217">防病毒用戶端發生錯誤，目前的掃描已停止。</span><span class="sxs-lookup"><span data-stu-id="35125-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="35125-218">掃描可能會因為用戶端問題而失敗。</span><span class="sxs-lookup"><span data-stu-id="35125-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="35125-219">此事件記錄包含掃描識別碼、掃描類型 (Microsoft Defender 防毒程式、反間諜軟體、反惡意程式碼) 、掃描參數、啟動掃描的使用者、錯誤碼，以及錯誤的描述。</span><span class="sxs-lookup"><span data-stu-id="35125-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="35125-220">若要疑難排解此事件：</span><span class="sxs-lookup"><span data-stu-id="35125-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="35125-221">再次執行掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="35125-222">若失敗，請移至 [ <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支援網站</a>]，然後在 <b>搜尋</b> 方塊中輸入錯誤號碼，以尋找錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="35125-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="35125-223">連絡 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技術支援</a>。</span><span class="sxs-lookup"><span data-stu-id="35125-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-224">事件 ID: 1006</span><span class="sxs-lookup"><span data-stu-id="35125-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-225">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-227">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-227">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-228">
<b>反惡意軟體引擎找到惡意程式碼或其他可能不需要的軟體。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-229">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-230">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="35125-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="35125-231">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-232">低</span><span class="sxs-lookup"><span data-stu-id="35125-232">Low</span></span></li>
<li><span data-ttu-id="35125-233">中等</span><span class="sxs-lookup"><span data-stu-id="35125-233">Moderate</span></span></li>
<li><span data-ttu-id="35125-234">高</span><span class="sxs-lookup"><span data-stu-id="35125-234">High</span></span></li>
<li><span data-ttu-id="35125-235">嚴重</span><span class="sxs-lookup"><span data-stu-id="35125-235">Severe</span></span></li>
</ul><span data-ttu-id="35125-236">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt> 
<dt> 偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-237">Unknown</span><span class="sxs-lookup"><span data-stu-id="35125-237">Unknown</span></span></li>
<li><span data-ttu-id="35125-238">本機電腦</span><span class="sxs-lookup"><span data-stu-id="35125-238">Local computer</span></span></li>
<li><span data-ttu-id="35125-239">網路共用</span><span class="sxs-lookup"><span data-stu-id="35125-239">Network share</span></span></li>
<li><span data-ttu-id="35125-240">網際網路</span><span class="sxs-lookup"><span data-stu-id="35125-240">Internet</span></span></li>
<li><span data-ttu-id="35125-241">傳入流量</span><span class="sxs-lookup"><span data-stu-id="35125-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="35125-242">外寄流量</span><span class="sxs-lookup"><span data-stu-id="35125-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="35125-243">
</dt>
<dt>偵測類型： &lt; 偵測類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-244">啟發式</span><span class="sxs-lookup"><span data-stu-id="35125-244">Heuristics</span></span></li>
<li><span data-ttu-id="35125-245">Generic</span><span class="sxs-lookup"><span data-stu-id="35125-245">Generic</span></span></li>
<li><span data-ttu-id="35125-246">混凝土</span><span class="sxs-lookup"><span data-stu-id="35125-246">Concrete</span></span></li>
<li><span data-ttu-id="35125-247">動態簽名</span><span class="sxs-lookup"><span data-stu-id="35125-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="35125-248">
</dt>
<dt>偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="35125-249">使用者：使用者已啟動</span><span class="sxs-lookup"><span data-stu-id="35125-249">User: user initiated</span></span></li>
<li><span data-ttu-id="35125-250">系統：系統啟動</span><span class="sxs-lookup"><span data-stu-id="35125-250">System: system initiated</span></span></li>
<li><span data-ttu-id="35125-251">即時：啟動即時元件</span><span class="sxs-lookup"><span data-stu-id="35125-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="35125-252">IOAV：已啟動 IE 下載和 Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="35125-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="35125-253">NIS：網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="35125-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="35125-254">IEPROTECT： IE-IExtensionValidation;這可防止惡意的網頁控制項</span><span class="sxs-lookup"><span data-stu-id="35125-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="35125-255">ELAM) 上的初期啟動反惡意軟體 (。</span><span class="sxs-lookup"><span data-stu-id="35125-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="35125-256">這包括由啟動順序偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="35125-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="35125-257">遠端證明</span><span class="sxs-lookup"><span data-stu-id="35125-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="35125-258">反惡意軟體掃描介面 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="35125-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="35125-259">主要是用來保護 (PS、VBS) 的腳本，不過也可由協力廠商呼叫。</span><span class="sxs-lookup"><span data-stu-id="35125-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="35125-260">UAC </dt> 
<dt>狀態： &lt; 狀態 &gt; </dt>
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>進程名稱： &lt; PID &gt; 簽章版本中的處理</dt>程式版本
<dt>： &lt; 定義版本 &gt; </dt>引擎版本
<dt>： &lt; 反惡意程式碼引擎版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-261">事件 ID: 1007</span><span class="sxs-lookup"><span data-stu-id="35125-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-262">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-264">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-264">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-265">
<b>反惡意軟體平臺會執行動作，以保護您的系統免受惡意軟體或其他可能不需要的軟體的攻擊。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-266">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-267">Microsoft Defender 防病毒已採取動作，以保護此機器免受惡意程式碼或其他可能不需要的軟體的攻擊。</span><span class="sxs-lookup"><span data-stu-id="35125-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="35125-268">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="35125-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="35125-269">
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
<dt>名稱： &lt; 威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-270">低</span><span class="sxs-lookup"><span data-stu-id="35125-270">Low</span></span></li>
<li><span data-ttu-id="35125-271">中等</span><span class="sxs-lookup"><span data-stu-id="35125-271">Moderate</span></span></li>
<li><span data-ttu-id="35125-272">高</span><span class="sxs-lookup"><span data-stu-id="35125-272">High</span></span></li>
<li><span data-ttu-id="35125-273">嚴重</span><span class="sxs-lookup"><span data-stu-id="35125-273">Severe</span></span></li>
</ul><span data-ttu-id="35125-274">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt> 
<dt>動作： &lt; 動作 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-275">清理：已清除資源</span><span class="sxs-lookup"><span data-stu-id="35125-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="35125-276">隔離：已隔離資源</span><span class="sxs-lookup"><span data-stu-id="35125-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="35125-277">移除：已刪除資源</span><span class="sxs-lookup"><span data-stu-id="35125-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="35125-278">允許：允許執行/存在資源</span><span class="sxs-lookup"><span data-stu-id="35125-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="35125-279">使用者定義：使用者定義的動作，通常是從使用者已指定之動作清單中的一個專案。</span><span class="sxs-lookup"><span data-stu-id="35125-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="35125-280">無動作：無動作</span><span class="sxs-lookup"><span data-stu-id="35125-280">No action: No action</span></span></li>
<li><span data-ttu-id="35125-281">封鎖：資源遭到封鎖，無法執行</span><span class="sxs-lookup"><span data-stu-id="35125-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="35125-282">
</dt>
<dt>狀態： &lt;狀態 &gt; </dt>
<dt>簽名版本： &lt; 定義版本 &gt; </dt>
<dt>引擎版本： &lt; 反惡意程式碼 &gt; 引擎版本</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-283">事件 ID: 1008</span><span class="sxs-lookup"><span data-stu-id="35125-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-284">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-286">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-286">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-287">
<b>反惡意程式碼平臺嘗試執行動作，以保護您的系統免受惡意軟體或其他可能不需要的軟體的攻擊，但動作失敗。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-288">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-289">Microsoft Defender 防毒程式在對惡意程式碼或其他可能不需要的軟體採取動作時，發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="35125-290">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="35125-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="35125-291">
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
<dt>名稱： &lt; 威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-292">低</span><span class="sxs-lookup"><span data-stu-id="35125-292">Low</span></span></li>
<li><span data-ttu-id="35125-293">中等</span><span class="sxs-lookup"><span data-stu-id="35125-293">Moderate</span></span></li>
<li><span data-ttu-id="35125-294">高</span><span class="sxs-lookup"><span data-stu-id="35125-294">High</span></span></li>
<li><span data-ttu-id="35125-295">嚴重</span><span class="sxs-lookup"><span data-stu-id="35125-295">Severe</span></span></li>
</ul><span data-ttu-id="35125-296">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt> 
<dt> 動作： &lt; 動作 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-297">清理：已清除資源</span><span class="sxs-lookup"><span data-stu-id="35125-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="35125-298">隔離：已隔離資源</span><span class="sxs-lookup"><span data-stu-id="35125-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="35125-299">移除：已刪除資源</span><span class="sxs-lookup"><span data-stu-id="35125-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="35125-300">允許：允許執行/存在資源</span><span class="sxs-lookup"><span data-stu-id="35125-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="35125-301">使用者定義：使用者定義的動作，通常是從使用者已指定之動作清單中的一個專案。</span><span class="sxs-lookup"><span data-stu-id="35125-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="35125-302">無動作：無動作</span><span class="sxs-lookup"><span data-stu-id="35125-302">No action: No action</span></span></li>
<li><span data-ttu-id="35125-303">封鎖：資源遭到封鎖，無法執行</span><span class="sxs-lookup"><span data-stu-id="35125-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="35125-304">
</dt>
<dt>錯誤碼： &lt;&gt;與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述：錯誤 &lt; 描述 &gt; 錯誤的描述。</dt>
<dt>狀態： &lt;狀態 &gt; </dt>
<dt>簽名版本： &lt; 定義版本 &gt; </dt>
<dt>引擎版本： &lt; 反惡意程式碼 &gt; 引擎版本</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-304">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-305">事件 ID: 1009</span><span class="sxs-lookup"><span data-stu-id="35125-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-306">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-308">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-308">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-309">
<b>反惡意軟體平臺已從隔離區還原專案。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-310">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-311">Microsoft Defender 防病毒已從隔離區還原專案。</span><span class="sxs-lookup"><span data-stu-id="35125-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="35125-312">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="35125-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="35125-313">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-314">低</span><span class="sxs-lookup"><span data-stu-id="35125-314">Low</span></span></li>
<li><span data-ttu-id="35125-315">中等</span><span class="sxs-lookup"><span data-stu-id="35125-315">Moderate</span></span></li>
<li><span data-ttu-id="35125-316">高</span><span class="sxs-lookup"><span data-stu-id="35125-316">High</span></span></li>
<li><span data-ttu-id="35125-317">嚴重</span><span class="sxs-lookup"><span data-stu-id="35125-317">Severe</span></span></li>
</ul><span data-ttu-id="35125-318">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt>
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>簽名版本： &lt; 定義版本 &gt; </dt>
<dt>引擎版本： &lt; 反惡意程式碼 &gt; 引擎版本</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-318">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-319">事件 ID: 1010</span><span class="sxs-lookup"><span data-stu-id="35125-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-320">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-322">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-322">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-323">
<b>反惡意軟體平臺無法從隔離區還原專案。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-324">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-325">Microsoft Defender 防毒軟體嘗試從隔離區還原專案時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="35125-326">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="35125-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="35125-327">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-328">低</span><span class="sxs-lookup"><span data-stu-id="35125-328">Low</span></span></li>
<li><span data-ttu-id="35125-329">中等</span><span class="sxs-lookup"><span data-stu-id="35125-329">Moderate</span></span></li>
<li><span data-ttu-id="35125-330">高</span><span class="sxs-lookup"><span data-stu-id="35125-330">High</span></span></li>
<li><span data-ttu-id="35125-331">嚴重</span><span class="sxs-lookup"><span data-stu-id="35125-331">Severe</span></span></li>
</ul><span data-ttu-id="35125-332">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt>
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述：錯誤 &lt; 描述 &gt; 錯誤的描述。</dt>簽章
<dt>版本： &lt;定義版本 &gt; </dt>
<dt>引擎版本： &lt; 反惡意引擎 &gt; 版本</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-332">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-333">事件 ID: 1011</span><span class="sxs-lookup"><span data-stu-id="35125-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-334">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-336">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-336">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-337">
<b>反惡意軟體平臺已從隔離區中刪除專案。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-338">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-339">Microsoft Defender 防病毒已從隔離區中刪除專案。</span><span class="sxs-lookup"><span data-stu-id="35125-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="35125-340">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="35125-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="35125-341">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-342">低</span><span class="sxs-lookup"><span data-stu-id="35125-342">Low</span></span></li>
<li><span data-ttu-id="35125-343">中等</span><span class="sxs-lookup"><span data-stu-id="35125-343">Moderate</span></span></li>
<li><span data-ttu-id="35125-344">高</span><span class="sxs-lookup"><span data-stu-id="35125-344">High</span></span></li>
<li><span data-ttu-id="35125-345">嚴重</span><span class="sxs-lookup"><span data-stu-id="35125-345">Severe</span></span></li>
</ul><span data-ttu-id="35125-346">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt>
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>簽名版本： &lt; 定義版本 &gt; </dt>
<dt>引擎版本： &lt; 反惡意程式碼 &gt; 引擎版本</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-346">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-347">事件 ID: 1012</span><span class="sxs-lookup"><span data-stu-id="35125-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-348">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-350">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-350">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-351">
<b>反惡意軟體平臺無法從隔離區刪除專案。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-352">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-353">Microsoft Defender 防毒軟體嘗試從隔離區刪除專案時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="35125-354">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="35125-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="35125-355">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-356">低</span><span class="sxs-lookup"><span data-stu-id="35125-356">Low</span></span></li>
<li><span data-ttu-id="35125-357">中等</span><span class="sxs-lookup"><span data-stu-id="35125-357">Moderate</span></span></li>
<li><span data-ttu-id="35125-358">高</span><span class="sxs-lookup"><span data-stu-id="35125-358">High</span></span></li>
<li><span data-ttu-id="35125-359">嚴重</span><span class="sxs-lookup"><span data-stu-id="35125-359">Severe</span></span></li>
</ul><span data-ttu-id="35125-360">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt>
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述：錯誤 &lt; 描述 &gt; 錯誤的描述。</dt>簽章
<dt>版本： &lt;定義版本 &gt; </dt>
<dt>引擎版本： &lt; 反惡意引擎 &gt; 版本</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-360">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-361">事件 ID: 1013</span><span class="sxs-lookup"><span data-stu-id="35125-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-362">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-364">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-364">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-365">
<b>惡意程式碼平臺已刪除惡意程式碼和其他可能不需要的軟體的歷程記錄。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-366">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-367">Microsoft Defender 防病毒已移除惡意程式碼和其他可能不需要的軟體的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="35125-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="35125-368">
<dt>時間：事件發生的時間，例如清除的史。此參數不會用於威脅事件，所以不會混淆是否為修正時間或感染時間。在這些情況下，我們特別是以動作時間或偵測時間的方式呼叫它們。</dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-369">事件 ID: 1014</span><span class="sxs-lookup"><span data-stu-id="35125-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-370">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-372">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="35125-373">反惡意軟體平臺無法刪除惡意程式碼和其他可能不需要的軟體的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="35125-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-374">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-375">Microsoft Defender 防毒程式嘗試移除惡意程式碼與其他可能不需要的軟體的記錄時，發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="35125-376">
<dt>時間：事件發生的時間，例如清除的史。此參數不會用於威脅事件，所以不會混淆是否為修正時間或感染時間。在這些情況下，我們特別是以動作時間或偵測時間的方式呼叫它們。</dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述：錯誤 &lt; 描述 &gt; 錯誤的描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-377">事件 ID: 1015</span><span class="sxs-lookup"><span data-stu-id="35125-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-378">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-380">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-380">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-381">
<b>反惡意軟體平臺偵測到可疑行為。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-382">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-383">Microsoft Defender 防病毒已偵測到可疑行為。</span><span class="sxs-lookup"><span data-stu-id="35125-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="35125-384">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="35125-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="35125-385">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-386">低</span><span class="sxs-lookup"><span data-stu-id="35125-386">Low</span></span></li>
<li><span data-ttu-id="35125-387">中等</span><span class="sxs-lookup"><span data-stu-id="35125-387">Moderate</span></span></li>
<li><span data-ttu-id="35125-388">高</span><span class="sxs-lookup"><span data-stu-id="35125-388">High</span></span></li>
<li><span data-ttu-id="35125-389">嚴重</span><span class="sxs-lookup"><span data-stu-id="35125-389">Severe</span></span></li>
</ul><span data-ttu-id="35125-390">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt> 
<dt> 偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="35125-391">Unknown</span><span class="sxs-lookup"><span data-stu-id="35125-391">Unknown</span></span></li>
<li><span data-ttu-id="35125-392">本機電腦</span><span class="sxs-lookup"><span data-stu-id="35125-392">Local computer</span></span></li>
<li><span data-ttu-id="35125-393">網路共用</span><span class="sxs-lookup"><span data-stu-id="35125-393">Network share</span></span></li>
<li><span data-ttu-id="35125-394">網際網路</span><span class="sxs-lookup"><span data-stu-id="35125-394">Internet</span></span></li>
<li><span data-ttu-id="35125-395">傳入流量</span><span class="sxs-lookup"><span data-stu-id="35125-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="35125-396">外寄流量</span><span class="sxs-lookup"><span data-stu-id="35125-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="35125-397">
</dt>
<dt>偵測類型： &lt; 偵測類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-398">啟發式</span><span class="sxs-lookup"><span data-stu-id="35125-398">Heuristics</span></span></li>
<li><span data-ttu-id="35125-399">Generic</span><span class="sxs-lookup"><span data-stu-id="35125-399">Generic</span></span></li>
<li><span data-ttu-id="35125-400">混凝土</span><span class="sxs-lookup"><span data-stu-id="35125-400">Concrete</span></span></li>
<li><span data-ttu-id="35125-401">動態簽名</span><span class="sxs-lookup"><span data-stu-id="35125-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="35125-402">
</dt>
<dt>偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="35125-403">使用者：使用者已啟動</span><span class="sxs-lookup"><span data-stu-id="35125-403">User: user initiated</span></span></li>
<li><span data-ttu-id="35125-404">系統：系統啟動</span><span class="sxs-lookup"><span data-stu-id="35125-404">System: system initiated</span></span></li>
<li><span data-ttu-id="35125-405">即時：啟動即時元件</span><span class="sxs-lookup"><span data-stu-id="35125-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="35125-406">IOAV：已啟動 IE 下載和 Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="35125-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="35125-407">NIS：網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="35125-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="35125-408">IEPROTECT： IE-IExtensionValidation;這可防止惡意的網頁控制項</span><span class="sxs-lookup"><span data-stu-id="35125-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="35125-409">ELAM) 上的初期啟動反惡意軟體 (。</span><span class="sxs-lookup"><span data-stu-id="35125-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="35125-410">這包括由啟動順序偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="35125-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="35125-411">遠端證明</span><span class="sxs-lookup"><span data-stu-id="35125-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="35125-412">反惡意軟體掃描介面 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="35125-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="35125-413">主要是用來保護 (PS、VBS) 的腳本，不過也可由協力廠商呼叫。</span><span class="sxs-lookup"><span data-stu-id="35125-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="35125-414">UAC </dt> 
<dt>狀態： &lt; 狀態 &gt; </dt>
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>進程名稱： &lt; PID &gt; 簽章中的處理</dt>程式
<dt>ID: 列舉比對嚴重性。</dt>簽章
<dt>版本： &lt;定義版本 &gt; </dt>
<dt>引擎版本： &lt; 反惡意程式碼 &gt; 引擎版本</dt>
<dt>逼真度標籤：</dt>
<dt>目的檔案名：檔案名 &lt; 的檔案名 &gt; 。</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-414">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature ID: Enumeration matching severity.</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Fidelity Label:</dt>
<dt>Target File Name: &lt;File name&gt; Name of the file.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-415">事件 ID: 1116</span><span class="sxs-lookup"><span data-stu-id="35125-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-416">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-418">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-418">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-419">
<b>反惡意軟體平臺偵測到惡意程式碼或其他可能不需要的軟體。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-420">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-421">Microsoft Defender 防毒程式偵測到惡意程式碼或其他可能不需要的軟體。</span><span class="sxs-lookup"><span data-stu-id="35125-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="35125-422">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="35125-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="35125-423">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-424">低</span><span class="sxs-lookup"><span data-stu-id="35125-424">Low</span></span></li>
<li><span data-ttu-id="35125-425">中等</span><span class="sxs-lookup"><span data-stu-id="35125-425">Moderate</span></span></li>
<li><span data-ttu-id="35125-426">高</span><span class="sxs-lookup"><span data-stu-id="35125-426">High</span></span></li>
<li><span data-ttu-id="35125-427">嚴重</span><span class="sxs-lookup"><span data-stu-id="35125-427">Severe</span></span></li>
</ul><span data-ttu-id="35125-428">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt> 
<dt> 偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="35125-429">Unknown</span><span class="sxs-lookup"><span data-stu-id="35125-429">Unknown</span></span></li>
<li><span data-ttu-id="35125-430">本機電腦</span><span class="sxs-lookup"><span data-stu-id="35125-430">Local computer</span></span></li>
<li><span data-ttu-id="35125-431">網路共用</span><span class="sxs-lookup"><span data-stu-id="35125-431">Network share</span></span></li>
<li><span data-ttu-id="35125-432">網際網路</span><span class="sxs-lookup"><span data-stu-id="35125-432">Internet</span></span></li>
<li><span data-ttu-id="35125-433">傳入流量</span><span class="sxs-lookup"><span data-stu-id="35125-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="35125-434">外寄流量</span><span class="sxs-lookup"><span data-stu-id="35125-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="35125-435">
</dt>
<dt>偵測類型： &lt; 偵測類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-436">啟發式</span><span class="sxs-lookup"><span data-stu-id="35125-436">Heuristics</span></span></li>
<li><span data-ttu-id="35125-437">Generic</span><span class="sxs-lookup"><span data-stu-id="35125-437">Generic</span></span></li>
<li><span data-ttu-id="35125-438">混凝土</span><span class="sxs-lookup"><span data-stu-id="35125-438">Concrete</span></span></li>
<li><span data-ttu-id="35125-439">動態簽名</span><span class="sxs-lookup"><span data-stu-id="35125-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="35125-440">
</dt>
<dt>偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="35125-441">使用者：使用者已啟動</span><span class="sxs-lookup"><span data-stu-id="35125-441">User: user initiated</span></span></li>
<li><span data-ttu-id="35125-442">系統：系統啟動</span><span class="sxs-lookup"><span data-stu-id="35125-442">System: system initiated</span></span></li>
<li><span data-ttu-id="35125-443">即時：啟動即時元件</span><span class="sxs-lookup"><span data-stu-id="35125-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="35125-444">IOAV：已啟動 IE 下載和 Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="35125-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="35125-445">NIS：網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="35125-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="35125-446">IEPROTECT： IE-IExtensionValidation;這可防止惡意的網頁控制項</span><span class="sxs-lookup"><span data-stu-id="35125-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="35125-447">ELAM) 上的初期啟動反惡意軟體 (。</span><span class="sxs-lookup"><span data-stu-id="35125-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="35125-448">這包括由啟動順序偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="35125-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="35125-449">遠端證明</span><span class="sxs-lookup"><span data-stu-id="35125-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="35125-450">反惡意軟體掃描介面 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="35125-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="35125-451">主要是用來保護 (PS、VBS) 的腳本，不過也可由協力廠商呼叫。</span><span class="sxs-lookup"><span data-stu-id="35125-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="35125-452">UAC </dt> 
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>進程名稱： &lt; PID &gt; 簽章版本中的處理</dt>程式版本
<dt>： &lt; 定義版本 &gt; </dt>引擎版本
<dt>： &lt; 反惡意程式碼引擎版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-453">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-454">不用執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="35125-454">No action is required.</span></span> <span data-ttu-id="35125-455">Microsoft Defender 防毒程式可能會暫停，並對此威脅採取例行動作。</span><span class="sxs-lookup"><span data-stu-id="35125-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="35125-456">如果您想要手動移除威脅，請在 Microsoft Defender 防病毒介面中，按一下 [ <b>清理電腦</b>]。</span><span class="sxs-lookup"><span data-stu-id="35125-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-457">事件 ID: 1117</span><span class="sxs-lookup"><span data-stu-id="35125-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-458">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-460">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-460">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-461">
<b>反惡意軟體平臺會執行動作，以保護您的系統免受惡意軟體或其他可能不需要的軟體的攻擊。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-462">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-463">Microsoft Defender 防病毒已採取動作，以保護此機器免受惡意程式碼或其他可能不需要的軟體的攻擊。</span><span class="sxs-lookup"><span data-stu-id="35125-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="35125-464">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="35125-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="35125-465">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-466">低</span><span class="sxs-lookup"><span data-stu-id="35125-466">Low</span></span></li>
<li><span data-ttu-id="35125-467">中等</span><span class="sxs-lookup"><span data-stu-id="35125-467">Moderate</span></span></li>
<li><span data-ttu-id="35125-468">高</span><span class="sxs-lookup"><span data-stu-id="35125-468">High</span></span></li>
<li><span data-ttu-id="35125-469">嚴重</span><span class="sxs-lookup"><span data-stu-id="35125-469">Severe</span></span></li>
</ul><span data-ttu-id="35125-470">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt> 
<dt> 偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="35125-471">Unknown</span><span class="sxs-lookup"><span data-stu-id="35125-471">Unknown</span></span></li>
<li><span data-ttu-id="35125-472">本機電腦</span><span class="sxs-lookup"><span data-stu-id="35125-472">Local computer</span></span></li>
<li><span data-ttu-id="35125-473">網路共用</span><span class="sxs-lookup"><span data-stu-id="35125-473">Network share</span></span></li>
<li><span data-ttu-id="35125-474">網際網路</span><span class="sxs-lookup"><span data-stu-id="35125-474">Internet</span></span></li>
<li><span data-ttu-id="35125-475">傳入流量</span><span class="sxs-lookup"><span data-stu-id="35125-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="35125-476">外寄流量</span><span class="sxs-lookup"><span data-stu-id="35125-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="35125-477">
</dt>
<dt>偵測類型： &lt; 偵測類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-478">啟發式</span><span class="sxs-lookup"><span data-stu-id="35125-478">Heuristics</span></span></li>
<li><span data-ttu-id="35125-479">Generic</span><span class="sxs-lookup"><span data-stu-id="35125-479">Generic</span></span></li>
<li><span data-ttu-id="35125-480">混凝土</span><span class="sxs-lookup"><span data-stu-id="35125-480">Concrete</span></span></li>
<li><span data-ttu-id="35125-481">動態簽名</span><span class="sxs-lookup"><span data-stu-id="35125-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="35125-482">
</dt>
<dt>偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="35125-483">使用者：使用者已啟動</span><span class="sxs-lookup"><span data-stu-id="35125-483">User: user initiated</span></span></li>
<li><span data-ttu-id="35125-484">系統：系統啟動</span><span class="sxs-lookup"><span data-stu-id="35125-484">System: system initiated</span></span></li>
<li><span data-ttu-id="35125-485">即時：啟動即時元件</span><span class="sxs-lookup"><span data-stu-id="35125-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="35125-486">IOAV：已啟動 IE 下載和 Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="35125-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="35125-487">NIS：網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="35125-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="35125-488">IEPROTECT： IE-IExtensionValidation;這可防止惡意的網頁控制項</span><span class="sxs-lookup"><span data-stu-id="35125-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="35125-489">ELAM) 上的初期啟動反惡意軟體 (。</span><span class="sxs-lookup"><span data-stu-id="35125-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="35125-490">這包括由啟動順序偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="35125-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="35125-491">遠端證明</span><span class="sxs-lookup"><span data-stu-id="35125-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="35125-492">反惡意軟體掃描介面 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="35125-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="35125-493">主要是用來保護 (PS、VBS) 的腳本，不過也可由協力廠商呼叫。</span><span class="sxs-lookup"><span data-stu-id="35125-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="35125-494">UAC </dt> 
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>進程名稱： &lt; PID &gt; 動作中的處理</dt> 
<dt> &lt; 程式：動作 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-495">清理：已清除資源</span><span class="sxs-lookup"><span data-stu-id="35125-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="35125-496">隔離：已隔離資源</span><span class="sxs-lookup"><span data-stu-id="35125-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="35125-497">移除：已刪除資源</span><span class="sxs-lookup"><span data-stu-id="35125-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="35125-498">允許：允許執行/存在資源</span><span class="sxs-lookup"><span data-stu-id="35125-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="35125-499">使用者定義：使用者定義的動作，通常是從使用者已指定之動作清單中的一個專案。</span><span class="sxs-lookup"><span data-stu-id="35125-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="35125-500">無動作：無動作</span><span class="sxs-lookup"><span data-stu-id="35125-500">No action: No action</span></span></li>
<li><span data-ttu-id="35125-501">封鎖：資源遭到封鎖，無法執行</span><span class="sxs-lookup"><span data-stu-id="35125-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="35125-502">
</dt>
<dt>動作狀態： &lt;其他動作 &gt; 的描述</dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤碼的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>簽章
<dt>版本： &lt;定義版本 &gt; </dt>
<dt>引擎版本： &lt; 反惡意引擎 &gt; 版本</dt>請注意：每當 microsoft Defender 防毒程式、microsoft Security Essentials、惡意軟體移除工具或 System Center Endpoint Protection 偵測到惡意程式碼時，會還原下列系統設定和服務，惡意程式碼可能已變更：</span><span class="sxs-lookup"><span data-stu-id="35125-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="35125-503">預設 Internet Explorer 或 Microsoft Edge 設定</span><span class="sxs-lookup"><span data-stu-id="35125-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="35125-504">使用者存取控制設定</span><span class="sxs-lookup"><span data-stu-id="35125-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="35125-505">Chrome 設定</span><span class="sxs-lookup"><span data-stu-id="35125-505">Chrome settings</span></span></li>
<li><span data-ttu-id="35125-506">引導控制資料</span><span class="sxs-lookup"><span data-stu-id="35125-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="35125-507">Regedit 和工作管理員登錄設定</span><span class="sxs-lookup"><span data-stu-id="35125-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="35125-508">Windows 更新、背景智慧傳送服務和遠端過程呼叫服務</span><span class="sxs-lookup"><span data-stu-id="35125-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="35125-509">Windows 作業系統檔</span><span class="sxs-lookup"><span data-stu-id="35125-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="35125-510">上述內容適用于下列用戶端和伺服器版本：</span><span class="sxs-lookup"><span data-stu-id="35125-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="35125-511">作業系統</span><span class="sxs-lookup"><span data-stu-id="35125-511">Operating system</span></span></th>
<th><span data-ttu-id="35125-512">作業系統版本</span><span class="sxs-lookup"><span data-stu-id="35125-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="35125-513">用戶端作業系統</span><span class="sxs-lookup"><span data-stu-id="35125-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="35125-514">Windows Vista (Service Pack 1 或 Service Pack 2) ，Windows 7 和更新版本</span><span class="sxs-lookup"><span data-stu-id="35125-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-515">伺服器作業系統</span><span class="sxs-lookup"><span data-stu-id="35125-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="35125-516">Windows Server 2008、Windows Server 2008 R2、Windows Server 2012 及 Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="35125-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-517">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-518">不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="35125-518">No action is necessary.</span></span> <span data-ttu-id="35125-519">Microsoft Defender 防病毒已移除或隔離威脅。</span><span class="sxs-lookup"><span data-stu-id="35125-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-520">事件 ID: 1118</span><span class="sxs-lookup"><span data-stu-id="35125-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-521">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-523">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-523">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-524">
<b>反惡意程式碼平臺嘗試執行動作，以保護您的系統免受惡意軟體或其他可能不需要的軟體的攻擊，但動作失敗。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-525">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-526">當對惡意程式碼或其他可能不需要的軟體採取動作時，Microsoft Defender 防毒軟體會遇到非嚴重的錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="35125-527">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="35125-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="35125-528">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-529">低</span><span class="sxs-lookup"><span data-stu-id="35125-529">Low</span></span></li>
<li><span data-ttu-id="35125-530">中等</span><span class="sxs-lookup"><span data-stu-id="35125-530">Moderate</span></span></li>
<li><span data-ttu-id="35125-531">高</span><span class="sxs-lookup"><span data-stu-id="35125-531">High</span></span></li>
<li><span data-ttu-id="35125-532">嚴重</span><span class="sxs-lookup"><span data-stu-id="35125-532">Severe</span></span></li>
</ul><span data-ttu-id="35125-533">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt> 
<dt> 偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="35125-534">Unknown</span><span class="sxs-lookup"><span data-stu-id="35125-534">Unknown</span></span></li>
<li><span data-ttu-id="35125-535">本機電腦</span><span class="sxs-lookup"><span data-stu-id="35125-535">Local computer</span></span></li>
<li><span data-ttu-id="35125-536">網路共用</span><span class="sxs-lookup"><span data-stu-id="35125-536">Network share</span></span></li>
<li><span data-ttu-id="35125-537">網際網路</span><span class="sxs-lookup"><span data-stu-id="35125-537">Internet</span></span></li>
<li><span data-ttu-id="35125-538">傳入流量</span><span class="sxs-lookup"><span data-stu-id="35125-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="35125-539">外寄流量</span><span class="sxs-lookup"><span data-stu-id="35125-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="35125-540">
</dt>
<dt>偵測類型： &lt; 偵測類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-541">啟發式</span><span class="sxs-lookup"><span data-stu-id="35125-541">Heuristics</span></span></li>
<li><span data-ttu-id="35125-542">Generic</span><span class="sxs-lookup"><span data-stu-id="35125-542">Generic</span></span></li>
<li><span data-ttu-id="35125-543">混凝土</span><span class="sxs-lookup"><span data-stu-id="35125-543">Concrete</span></span></li>
<li><span data-ttu-id="35125-544">動態簽名</span><span class="sxs-lookup"><span data-stu-id="35125-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="35125-545">
</dt>
<dt>偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="35125-546">使用者：使用者已啟動</span><span class="sxs-lookup"><span data-stu-id="35125-546">User: user initiated</span></span></li>
<li><span data-ttu-id="35125-547">系統：系統啟動</span><span class="sxs-lookup"><span data-stu-id="35125-547">System: system initiated</span></span></li>
<li><span data-ttu-id="35125-548">即時：啟動即時元件</span><span class="sxs-lookup"><span data-stu-id="35125-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="35125-549">IOAV：已啟動 IE 下載和 Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="35125-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="35125-550">NIS：網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="35125-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="35125-551">IEPROTECT： IE-IExtensionValidation;這可防止惡意的網頁控制項</span><span class="sxs-lookup"><span data-stu-id="35125-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="35125-552">ELAM) 上的初期啟動反惡意軟體 (。</span><span class="sxs-lookup"><span data-stu-id="35125-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="35125-553">這包括由啟動順序偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="35125-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="35125-554">遠端證明</span><span class="sxs-lookup"><span data-stu-id="35125-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="35125-555">反惡意軟體掃描介面 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="35125-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="35125-556">主要是用來保護 (PS、VBS) 的腳本，不過也可由協力廠商呼叫。</span><span class="sxs-lookup"><span data-stu-id="35125-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="35125-557">UAC </dt> 
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>進程名稱： &lt; PID &gt; 動作中的處理</dt> 
<dt> &lt; 程式：動作 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-558">清理：已清除資源</span><span class="sxs-lookup"><span data-stu-id="35125-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="35125-559">隔離：已隔離資源</span><span class="sxs-lookup"><span data-stu-id="35125-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="35125-560">移除：已刪除資源</span><span class="sxs-lookup"><span data-stu-id="35125-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="35125-561">允許：允許執行/存在資源</span><span class="sxs-lookup"><span data-stu-id="35125-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="35125-562">使用者定義：使用者定義的動作，通常是從使用者已指定之動作清單中的一個專案。</span><span class="sxs-lookup"><span data-stu-id="35125-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="35125-563">無動作：無動作</span><span class="sxs-lookup"><span data-stu-id="35125-563">No action: No action</span></span></li>
<li><span data-ttu-id="35125-564">封鎖：資源遭到封鎖，無法執行</span><span class="sxs-lookup"><span data-stu-id="35125-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="35125-565">
</dt>
<dt>動作狀態： &lt;其他動作 &gt; 的描述</dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤碼的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>簽章
<dt>版本： &lt;定義版本 &gt; </dt>
<dt>引擎版本： &lt; 反惡意引擎 &gt; 版本</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-565">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-566">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-567">不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="35125-567">No action is necessary.</span></span> <span data-ttu-id="35125-568">Microsoft Defender 防毒程式無法完成與惡意程式碼修復相關的工作。</span><span class="sxs-lookup"><span data-stu-id="35125-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="35125-569">這不是嚴重失敗。</span><span class="sxs-lookup"><span data-stu-id="35125-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-570">事件 ID: 1119</span><span class="sxs-lookup"><span data-stu-id="35125-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-571">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-573">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-573">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-574">
<b>反惡意程式碼平臺嘗試對惡意程式碼或其他可能不需要的軟體採取動作時，發生嚴重錯誤。事件訊息中有更多的詳細資料。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-575">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-576">Microsoft Defender 防毒程式在對惡意程式碼或其他可能不需要的軟體採取動作時，發生嚴重錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="35125-577">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="35125-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="35125-578">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-579">低</span><span class="sxs-lookup"><span data-stu-id="35125-579">Low</span></span></li>
<li><span data-ttu-id="35125-580">中等</span><span class="sxs-lookup"><span data-stu-id="35125-580">Moderate</span></span></li>
<li><span data-ttu-id="35125-581">高</span><span class="sxs-lookup"><span data-stu-id="35125-581">High</span></span></li>
<li><span data-ttu-id="35125-582">嚴重</span><span class="sxs-lookup"><span data-stu-id="35125-582">Severe</span></span></li>
</ul><span data-ttu-id="35125-583">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt> 
<dt> 偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="35125-584">Unknown</span><span class="sxs-lookup"><span data-stu-id="35125-584">Unknown</span></span></li>
<li><span data-ttu-id="35125-585">本機電腦</span><span class="sxs-lookup"><span data-stu-id="35125-585">Local computer</span></span></li>
<li><span data-ttu-id="35125-586">網路共用</span><span class="sxs-lookup"><span data-stu-id="35125-586">Network share</span></span></li>
<li><span data-ttu-id="35125-587">網際網路</span><span class="sxs-lookup"><span data-stu-id="35125-587">Internet</span></span></li>
<li><span data-ttu-id="35125-588">傳入流量</span><span class="sxs-lookup"><span data-stu-id="35125-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="35125-589">外寄流量</span><span class="sxs-lookup"><span data-stu-id="35125-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="35125-590">
</dt>
<dt>偵測類型： &lt; 偵測類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-591">啟發式</span><span class="sxs-lookup"><span data-stu-id="35125-591">Heuristics</span></span></li>
<li><span data-ttu-id="35125-592">Generic</span><span class="sxs-lookup"><span data-stu-id="35125-592">Generic</span></span></li>
<li><span data-ttu-id="35125-593">混凝土</span><span class="sxs-lookup"><span data-stu-id="35125-593">Concrete</span></span></li>
<li><span data-ttu-id="35125-594">動態簽名</span><span class="sxs-lookup"><span data-stu-id="35125-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="35125-595">
</dt>
<dt>偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="35125-596">使用者：使用者已啟動</span><span class="sxs-lookup"><span data-stu-id="35125-596">User: user initiated</span></span></li>
<li><span data-ttu-id="35125-597">系統：系統啟動</span><span class="sxs-lookup"><span data-stu-id="35125-597">System: system initiated</span></span></li>
<li><span data-ttu-id="35125-598">即時：啟動即時元件</span><span class="sxs-lookup"><span data-stu-id="35125-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="35125-599">IOAV：已啟動 IE 下載和 Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="35125-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="35125-600">NIS：網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="35125-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="35125-601">IEPROTECT： IE-IExtensionValidation;這可防止惡意的網頁控制項</span><span class="sxs-lookup"><span data-stu-id="35125-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="35125-602">ELAM) 上的初期啟動反惡意軟體 (。</span><span class="sxs-lookup"><span data-stu-id="35125-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="35125-603">這包括由啟動順序偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="35125-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="35125-604">遠端證明</span><span class="sxs-lookup"><span data-stu-id="35125-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="35125-605">反惡意軟體掃描介面 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="35125-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="35125-606">主要是用來保護 (PS、VBS) 的腳本，不過也可由協力廠商呼叫。</span><span class="sxs-lookup"><span data-stu-id="35125-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="35125-607">UAC </dt> 
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>進程名稱： &lt; PID &gt; 動作中的處理</dt> 
<dt> &lt; 程式：動作 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="35125-608">清理：已清除資源</span><span class="sxs-lookup"><span data-stu-id="35125-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="35125-609">隔離：已隔離資源</span><span class="sxs-lookup"><span data-stu-id="35125-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="35125-610">移除：已刪除資源</span><span class="sxs-lookup"><span data-stu-id="35125-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="35125-611">允許：允許執行/存在資源</span><span class="sxs-lookup"><span data-stu-id="35125-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="35125-612">使用者定義：使用者定義的動作，通常是從使用者已指定之動作清單中的一個專案。</span><span class="sxs-lookup"><span data-stu-id="35125-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="35125-613">無動作：無動作</span><span class="sxs-lookup"><span data-stu-id="35125-613">No action: No action</span></span></li>
<li><span data-ttu-id="35125-614">封鎖：資源遭到封鎖，無法執行</span><span class="sxs-lookup"><span data-stu-id="35125-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="35125-615">
</dt>
<dt>動作狀態： &lt;其他動作 &gt; 的描述</dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤碼的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>簽章
<dt>版本： &lt;定義版本 &gt; </dt>
<dt>引擎版本： &lt; 反惡意引擎 &gt; 版本</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-615">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-616">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-617">Microsoft Defender 防病毒用戶端因嚴重問題而遇到此錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="35125-618">端點可能不受保護。</span><span class="sxs-lookup"><span data-stu-id="35125-618">The endpoint might not be protected.</span></span> <span data-ttu-id="35125-619">請複查錯誤描述，然後依照下列相關的 <b>使用者動作</b> 步驟進行。</span><span class="sxs-lookup"><span data-stu-id="35125-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="35125-620">動作</span><span class="sxs-lookup"><span data-stu-id="35125-620">Action</span></span></th>
<th><span data-ttu-id="35125-621">使用者動作</span><span class="sxs-lookup"><span data-stu-id="35125-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="35125-622">
<b>刪除</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="35125-623">更新定義，然後驗證是否已成功移除。</span><span class="sxs-lookup"><span data-stu-id="35125-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="35125-624">
<b>清潔</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="35125-625">更新定義，然後確認修復成功。</span><span class="sxs-lookup"><span data-stu-id="35125-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="35125-626">
<b>檢疫</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="35125-627">更新定義，並確認使用者具有存取必要資源的許可權。</span><span class="sxs-lookup"><span data-stu-id="35125-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="35125-628">
<b>允許</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="35125-629">確認使用者具有存取必要資源的許可權。</span><span class="sxs-lookup"><span data-stu-id="35125-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="35125-630">如果此事件仍然存在：</span><span class="sxs-lookup"><span data-stu-id="35125-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="35125-631">再次執行掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="35125-632">若失敗，請移至 [ <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支援網站</a>]，然後在 <b>搜尋</b> 方塊中輸入錯誤號碼，以尋找錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="35125-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="35125-633">連絡 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技術支援</a>。</span><span class="sxs-lookup"><span data-stu-id="35125-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-634">事件 ID: 1120</span><span class="sxs-lookup"><span data-stu-id="35125-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-635">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-637">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-637">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-638">
<b>Microsoft Defender 防病毒已推匯出威脅資源的雜湊。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-639">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-640">Microsoft Defender 防病毒用戶端已啟動並以健全的狀態運作。</span><span class="sxs-lookup"><span data-stu-id="35125-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="35125-641">
<dt>目前平臺版本： &lt;目前平臺版本 &gt; </dt>
<dt>威脅資源路徑： &lt; 路徑 &gt; </dt>
<dt>雜湊 &lt; ： &gt; 雜湊</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="35125-642"><b>注意：只有在設定下列原則時，才會記錄此事件： <b>ThreatFileHashLogging 未簽署</b>。</span><span class="sxs-lookup"><span data-stu-id="35125-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-643">事件 ID: 1150</span><span class="sxs-lookup"><span data-stu-id="35125-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-644">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-646">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-646">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-647">
<b>如果您的反惡意程式碼平臺報告狀態為監控平臺，此事件表示反惡意軟體平臺正在執行中且狀態良好。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-648">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-649">Microsoft Defender 防病毒用戶端已啟動並以健全的狀態運作。</span><span class="sxs-lookup"><span data-stu-id="35125-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="35125-650">
<dt>平臺版本： &lt;目前平臺版本 &gt; </dt>
<dt>簽名版本： &lt; 定義版本 &gt; </dt>
<dt>引擎版本： &lt; 反惡意程式碼 &gt; 引擎版本</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-651">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-652">不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="35125-652">No action is necessary.</span></span> <span data-ttu-id="35125-653">Microsoft Defender 防病毒用戶端的狀態良好。</span><span class="sxs-lookup"><span data-stu-id="35125-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="35125-654">此事件每小時報告一次。</span><span class="sxs-lookup"><span data-stu-id="35125-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="35125-655">事件 ID: 1151</span><span class="sxs-lookup"><span data-stu-id="35125-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-656">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-658">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-658">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-659">
<b>Endpoint Protection 用戶端狀況報告 (以 UTC) 的時間 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-660">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-661">防病毒用戶端狀況報告。</span><span class="sxs-lookup"><span data-stu-id="35125-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="35125-662">
<dt>平臺版本： &lt;目前平臺版本 &gt; </dt>
<dt>引擎版本： &lt; 反惡意引擎 &gt; 版本</dt>
<dt>網路即時檢查引擎版本： &lt; 網路即時檢查引擎 &gt; 版本</dt>
<dt>防病毒碼碼版本： &lt; 防毒軟體 &gt; </dt>簽章版本反間諜軟體簽章版本：
<dt> &lt; 反間諜軟體 &gt; </dt>簽章版本
<dt>網路即時檢查簽章版本： &lt; 網路即時檢查特徵碼 &gt; </dt>版本
<dt>RTP 狀態 &lt; &gt;)  (：</dt> 
<dt> &lt; 在 Access (狀態上啟用或 &gt; 停用) </dt> 
<dt>IOAV 狀態： &lt; IE 下載和 Outlook Express 附件狀態 &gt; (已啟用或已停用) </dt> 
<dt>BM 狀態： &lt; 行為監控狀態 &gt; (啟用或停用) </dt>防病毒簽名保留時間： 
<dt> &lt; 防病毒 &gt; </dt>軟體簽名保留天數 (
<dt>最近一次 &lt; &gt; 的快速掃描</dt>保留天數：上次的快速掃描保留天數) 
<dt>上次完整掃描保留 &lt; &gt; 天數：上次</dt>完整掃描保留天數 (的
<dt> &lt; &gt; </dt>
<dt>防病毒簽名建立時間) : ?&lt;防病毒簽名建立 &gt; 時間</dt>
<dt>反間諜軟體簽名建立時間：？ &lt;反間諜軟體簽名 &gt; 建立時間</dt>
<dt>上次快速掃描開始時間：？ &lt;上次快速掃描開始時間 &gt; </dt>
<dt>上次快速掃描結束時間：？ &lt;上次快速掃描結束時間 &gt; </dt>
<dt>上次快速掃描來源： &lt; 上次快速掃描來源 &gt; (0&#39;= 未執行、1 = 使用者啟動、2 = 系統起始) </dt>
<dt>上次完整掃描開始時間：？ &lt;上次完整掃描的開始 &gt; 時間</dt>
<dt>上次完整掃描結束時間：？ &lt;上次完整掃描結束時間 &gt; </dt>
<dt>上次完整掃描來源： &lt; 上次完整掃描來源 &gt; (0&#39;= 未執行、1 = 使用者啟動、2 = 系統起始) </dt> 
<dt> 產品狀態：用於內部疑難排解</span><span class="sxs-lookup"><span data-stu-id="35125-662">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Network Realtime Inspection engine version: &lt;Network Realtime Inspection engine version&gt;</dt>
<dt>Antivirus signature version: &lt;Antivirus signature version&gt;</dt>
<dt>Antispyware signature version: &lt;Antispyware signature version&gt;</dt>
<dt>Network Realtime Inspection signature version: &lt;Network Realtime Inspection signature version&gt;</dt>
<dt>RTP state: &lt;Realtime protection state&gt; (Enabled or Disabled)</dt>
<dt>OA state: &lt;On Access state&gt; (Enabled or Disabled)</dt>
<dt>IOAV state: &lt;IE Downloads and Outlook Express Attachments state&gt; (Enabled or Disabled)</dt>
<dt>BM state: &lt;Behavior Monitoring state&gt; (Enabled or Disabled)</dt>
<dt>Antivirus signature age: &lt;Antivirus signature age&gt; (in days)</dt>
<dt>Antispyware signature age: &lt;Antispyware signature age&gt; (in days)</dt>
<dt>Last quick scan age: &lt;Last quick scan age&gt; (in days)</dt>
<dt>Last full scan age: &lt;Last full scan age&gt; (in days)</dt>
<dt>Antivirus signature creation time: ?&lt;Antivirus signature creation time&gt;</dt>
<dt>Antispyware signature creation time: ?&lt;Antispyware signature creation time&gt;</dt>
<dt>Last quick scan start time: ?&lt;Last quick scan start time&gt;</dt>
<dt>Last quick scan end time: ?&lt;Last quick scan end time&gt;</dt>
<dt>Last quick scan source: &lt;Last quick scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Last full scan start time: ?&lt;Last full scan start time&gt;</dt>
<dt>Last full scan end time: ?&lt;Last full scan end time&gt;</dt>
<dt>Last full scan source: &lt;Last full scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Product status: For internal troubleshooting</span></span>
</dl>
</td>
</tr>

<tr><span data-ttu-id="35125-663">
<th colspan="2">事件 ID: 2000</span><span class="sxs-lookup"><span data-stu-id="35125-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-664">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-666">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-666">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-667">
<b>已成功更新反惡意程式碼定義。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-668">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-669">防病毒碼碼版本已更新。</span><span class="sxs-lookup"><span data-stu-id="35125-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="35125-670">
<dt>目前的特徵碼版本： &lt;&gt;目前</dt>的簽章版本先前的簽章
<dt>版本： &lt; 上一個 &gt; </dt>簽章版本簽章 
<dt> 類型： &lt; 簽名類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="35125-671">防毒</span><span class="sxs-lookup"><span data-stu-id="35125-671">Antivirus</span></span></li>
<li><span data-ttu-id="35125-672">間諜</span><span class="sxs-lookup"><span data-stu-id="35125-672">Antispyware</span></span></li>
<li><span data-ttu-id="35125-673">軟體</span><span class="sxs-lookup"><span data-stu-id="35125-673">Antimalware</span></span></li>
<li><span data-ttu-id="35125-674">網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="35125-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="35125-675">
</dt>
<dt>更新類型： &lt;更新類型 &gt; （完整或 Delta）。</dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
<dt>目前引擎版本： &lt; &gt; 目前引擎</dt>版本
<dt>先前 &lt; &gt; 引擎版本：舊</dt>引擎版本
</span><span class="sxs-lookup"><span data-stu-id="35125-675">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-676">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-677">不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="35125-677">No action is necessary.</span></span> <span data-ttu-id="35125-678">Microsoft Defender 防病毒用戶端的狀態良好。</span><span class="sxs-lookup"><span data-stu-id="35125-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="35125-679">成功更新特徵碼時會報告此事件。</span><span class="sxs-lookup"><span data-stu-id="35125-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-680">事件 ID: 2001</span><span class="sxs-lookup"><span data-stu-id="35125-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-681">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-683">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-683">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-684">
<b>安全性智慧更新失敗。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-685">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-686">Microsoft Defender 防毒軟體嘗試更新簽名時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="35125-687">
<dt>新的安全性情報版本： &lt;新的版本 &gt; 號碼</dt>
<dt>先前的安全性情報版本： &lt; 舊版本 &gt; </dt> 
<dt> 更新來源： &lt; 更新來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="35125-688">安全性智慧更新資料夾</span><span class="sxs-lookup"><span data-stu-id="35125-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="35125-689">內部安全性智慧補救伺服器</span><span class="sxs-lookup"><span data-stu-id="35125-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="35125-690">Microsoft 補救伺服器</span><span class="sxs-lookup"><span data-stu-id="35125-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="35125-691">檔案共用</span><span class="sxs-lookup"><span data-stu-id="35125-691">File share</span></span></li>
<li><span data-ttu-id="35125-692">Microsoft 惡意程式碼防護中心 (MMPC) </span><span class="sxs-lookup"><span data-stu-id="35125-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="35125-693">
</dt>
<dt>更新階段： &lt; 更新階段 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="35125-694">搜尋</span><span class="sxs-lookup"><span data-stu-id="35125-694">Search</span></span></li>
<li><span data-ttu-id="35125-695">下載</span><span class="sxs-lookup"><span data-stu-id="35125-695">Download</span></span></li>
<li><span data-ttu-id="35125-696">安裝</span><span class="sxs-lookup"><span data-stu-id="35125-696">Install</span></span></li>
</ul><span data-ttu-id="35125-697">
</dt>
<dt>來源路徑：通用命名慣例的檔案共用名稱稱 (UNC) ，Windows Server Update Services 的伺服器名稱 (WSUS) /Microsoft Update/ADL。</dt> 
<dt>簽章類型： &lt; 簽名類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="35125-698">防毒</span><span class="sxs-lookup"><span data-stu-id="35125-698">Antivirus</span></span></li>
<li><span data-ttu-id="35125-699">間諜</span><span class="sxs-lookup"><span data-stu-id="35125-699">Antispyware</span></span></li>
<li><span data-ttu-id="35125-700">軟體</span><span class="sxs-lookup"><span data-stu-id="35125-700">Antimalware</span></span></li>
<li><span data-ttu-id="35125-701">網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="35125-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="35125-702">
</dt>
<dt>更新類型： &lt;更新類型 &gt; （完整或 Delta）。</dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
<dt>目前引擎版本： &lt; &gt; 目前引擎</dt>版本
<dt>先前 &lt; &gt; 引擎版本：舊</dt>引擎版本
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤碼錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-702">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-703">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-704">當更新定義時發生問題，便會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="35125-705">若要疑難排解此事件：</span><span class="sxs-lookup"><span data-stu-id="35125-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="35125-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">更新定義</a> ，並直接在端點上強制重新掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="35125-707">如需此錯誤的詳細資訊，請參閱%Windir%\WindowsUpdate.log 檔案中的專案。</span><span class="sxs-lookup"><span data-stu-id="35125-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="35125-708">連絡 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技術支援</a>。</span><span class="sxs-lookup"><span data-stu-id="35125-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-709">事件 ID: 2002</span><span class="sxs-lookup"><span data-stu-id="35125-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-710">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-712">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-712">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-713">
<b>已成功更新反惡意程式碼引擎。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-714">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-715">Microsoft Defender 防病毒引擎版本已更新。</span><span class="sxs-lookup"><span data-stu-id="35125-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="35125-716">
<dt>目前引擎版本： &lt;目前引擎版本 &gt; </dt>舊版引擎版本
<dt>： &lt; 舊引擎版本 &gt; </dt>
<dt>引擎類型： &lt; 引擎類型 &gt; ，反惡意程式碼引擎或網路檢查系統引擎。</dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-717">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-718">不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="35125-718">No action is necessary.</span></span> <span data-ttu-id="35125-719">Microsoft Defender 防病毒用戶端的狀態良好。</span><span class="sxs-lookup"><span data-stu-id="35125-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="35125-720">當反惡意程式碼引擎成功更新時會報告此事件。</span><span class="sxs-lookup"><span data-stu-id="35125-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-721">事件 ID: 2003</span><span class="sxs-lookup"><span data-stu-id="35125-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-722">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-724">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-724">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-725">
<b>反惡意程式碼引擎更新失敗。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-726">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-727">Microsoft Defender 防毒軟體嘗試更新引擎時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="35125-728">
<dt>新引擎版本：</dt>
<dt>舊引擎版本： &lt; &gt; 舊</dt>引擎版本
<dt>引擎類型： &lt; 引擎類型 &gt; ，反惡意軟體引擎或網路檢查系統引擎。</dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-728">
<dt>New Engine Version:</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-729">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-730">Microsoft Defender 防病毒用戶端更新失敗。</span><span class="sxs-lookup"><span data-stu-id="35125-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="35125-731">當用戶端無法自行更新時，就會發生此事件。</span><span class="sxs-lookup"><span data-stu-id="35125-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="35125-732">此事件通常是因為更新期間網路連線中斷所造成。</span><span class="sxs-lookup"><span data-stu-id="35125-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="35125-733">若要疑難排解此事件：</span><span class="sxs-lookup"><span data-stu-id="35125-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="35125-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">更新定義</a> ，並直接在端點上強制重新掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="35125-735">連絡 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技術支援</a>。</span><span class="sxs-lookup"><span data-stu-id="35125-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-736">事件 ID: 2004</span><span class="sxs-lookup"><span data-stu-id="35125-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-737">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-739">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-739">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-740">
<b>載入反惡意程式碼定義時發生問題。反惡意程式碼引擎會嘗試載入最後一組已知良好的定義。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-741">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-742">Microsoft Defender 防毒程式嘗試載入簽章時發生錯誤，並會嘗試回復回已知良好的簽名集。</span><span class="sxs-lookup"><span data-stu-id="35125-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="35125-743">
<dt>嘗試的簽名：</dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>簽章
<dt>版本： &lt;定義版本 &gt; </dt>
<dt>引擎版本： &lt; 反惡意引擎 &gt; 版本</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-743">
<dt>Signatures Attempted:</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-744">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-745">Microsoft Defender 防病毒用戶端嘗試下載並安裝最新的定義檔，但失敗。</span><span class="sxs-lookup"><span data-stu-id="35125-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="35125-746">當用戶端嘗試載入定義時遇到錯誤，或檔案損毀時，可能會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="35125-747">Microsoft Defender 防毒程式會嘗試回復回已知良好的定義集。</span><span class="sxs-lookup"><span data-stu-id="35125-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="35125-748">若要疑難排解此事件：</span><span class="sxs-lookup"><span data-stu-id="35125-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="35125-749">重新開機電腦，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="35125-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="35125-750">從 <a href="https://aka.ms/wdsi">Microsoft 安全性情報網站</a>下載最新的定義。</span><span class="sxs-lookup"><span data-stu-id="35125-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="35125-751">附注：從網站下載的定義檔案大小可超過 60 MB，不應做為更新定義的長期方案。</span><span class="sxs-lookup"><span data-stu-id="35125-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="35125-752">連絡 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技術支援</a>。</span><span class="sxs-lookup"><span data-stu-id="35125-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-753">事件 ID: 2005</span><span class="sxs-lookup"><span data-stu-id="35125-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-754">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-756">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-756">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-757">
<b>由於反惡意軟體平臺已過時，反惡意程式碼引擎載入失敗。反惡意軟體平臺會載入最後一個已知良好的反惡意程式碼引擎，並嘗試更新。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-758">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-759">Microsoft Defender 防毒程式無法載入反惡意程式碼引擎，因為目前的平臺版本不受支援。</span><span class="sxs-lookup"><span data-stu-id="35125-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="35125-760">Microsoft Defender 防病毒會回復回最後一個已知良好的引擎，並且會嘗試平臺更新。</span><span class="sxs-lookup"><span data-stu-id="35125-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="35125-761">
<dt>目前平臺版本： &lt; 目前平臺版本&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-762">事件 ID: 2006</span><span class="sxs-lookup"><span data-stu-id="35125-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-763">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-765">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-765">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-766">
<b>平臺更新失敗。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-767">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-768">Microsoft Defender 防毒軟體嘗試更新平臺時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="35125-769">
<dt>目前平臺版本： &lt;目前的平臺 &gt; 版本</dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤碼錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-770">事件 ID: 2007</span><span class="sxs-lookup"><span data-stu-id="35125-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-771">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-773">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-773">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-774">
<b>此平臺很快就會過期。下載最新的平臺，以維護最新的保護。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-775">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-776">Microsoft Defender 防毒軟體會很快需要更新平臺版本，以支援未來版本的反惡意程式碼引擎。</span><span class="sxs-lookup"><span data-stu-id="35125-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="35125-777">下載最新的 Microsoft Defender 防病毒平臺，以維持最佳的保護層級。</span><span class="sxs-lookup"><span data-stu-id="35125-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="35125-778">
<dt>目前平臺版本： &lt; 目前平臺版本&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-779">事件 ID: 2010</span><span class="sxs-lookup"><span data-stu-id="35125-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-780">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-782">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-782">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-783">
<b>反惡意程式碼引擎使用動態特徵碼服務來取得其他定義。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-784">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-785">Microsoft Defender 防毒程式使用動態簽章 <i>服務</i> 來取得其他簽名，以協助保護您的電腦。</span><span class="sxs-lookup"><span data-stu-id="35125-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="35125-786">
<dt>目前的特徵碼版本： &lt;目前 &gt; </dt>的簽章版本 
<dt> 簽名類型： &lt; 簽名類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="35125-787">防毒</span><span class="sxs-lookup"><span data-stu-id="35125-787">Antivirus</span></span></li>
<li><span data-ttu-id="35125-788">間諜</span><span class="sxs-lookup"><span data-stu-id="35125-788">Antispyware</span></span></li>
<li><span data-ttu-id="35125-789">軟體</span><span class="sxs-lookup"><span data-stu-id="35125-789">Antimalware</span></span></li>
<li><span data-ttu-id="35125-790">網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="35125-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="35125-791">
</dt>
<dt>目前引擎版本： &lt;目前引擎版本 &gt; </dt>動態簽章 
<dt> 類型： &lt; 動態簽名類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="35125-792">版本</span><span class="sxs-lookup"><span data-stu-id="35125-792">Version</span></span></li>
<li><span data-ttu-id="35125-793">時間 戳</span><span class="sxs-lookup"><span data-stu-id="35125-793">Timestamp</span></span></li>
<li><span data-ttu-id="35125-794">無限制</span><span class="sxs-lookup"><span data-stu-id="35125-794">No limit</span></span></li>
<li><span data-ttu-id="35125-795">持續時間</span><span class="sxs-lookup"><span data-stu-id="35125-795">Duration</span></span></li>
</ul><span data-ttu-id="35125-796">
</dt>
<dt>持久性路徑： &lt;路徑 &gt; </dt>動態簽章
<dt>版本： &lt; 版本 &gt; 號碼</dt>動態簽章
<dt>編譯時間戳： &lt; timestamp &gt; </dt> 
<dt> 持續性限制類型：持續性 &lt; 限制類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="35125-797">VDM 版本</span><span class="sxs-lookup"><span data-stu-id="35125-797">VDM version</span></span></li>
<li><span data-ttu-id="35125-798">時間 戳</span><span class="sxs-lookup"><span data-stu-id="35125-798">Timestamp</span></span></li>
<li><span data-ttu-id="35125-799">無限制</span><span class="sxs-lookup"><span data-stu-id="35125-799">No limit</span></span></li>
</ul><span data-ttu-id="35125-800">
</dt>
<dt>持續性限制： fastpath 簽章的持續限制。</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-801">事件 ID: 2011</span><span class="sxs-lookup"><span data-stu-id="35125-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-802">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-804">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-804">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-805">
<b>動態簽章服務刪除了到期動態定義。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-806">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-807">Microsoft Defender 防毒程式使用動態簽章 <i>服務</i> 捨棄過時的簽名。</span><span class="sxs-lookup"><span data-stu-id="35125-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="35125-808">
<dt>目前的特徵碼版本： &lt;目前 &gt; </dt>的簽章版本 
<dt> 簽名類型： &lt; 簽名類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="35125-809">防毒</span><span class="sxs-lookup"><span data-stu-id="35125-809">Antivirus</span></span></li>
<li><span data-ttu-id="35125-810">間諜</span><span class="sxs-lookup"><span data-stu-id="35125-810">Antispyware</span></span></li>
<li><span data-ttu-id="35125-811">軟體</span><span class="sxs-lookup"><span data-stu-id="35125-811">Antimalware</span></span></li>
<li><span data-ttu-id="35125-812">網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="35125-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="35125-813">
</dt>
<dt>目前引擎版本： &lt;目前引擎版本 &gt; </dt>動態簽章 
<dt> 類型： &lt; 動態簽名類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="35125-814">版本</span><span class="sxs-lookup"><span data-stu-id="35125-814">Version</span></span></li>
<li><span data-ttu-id="35125-815">時間 戳</span><span class="sxs-lookup"><span data-stu-id="35125-815">Timestamp</span></span></li>
<li><span data-ttu-id="35125-816">無限制</span><span class="sxs-lookup"><span data-stu-id="35125-816">No limit</span></span></li>
<li><span data-ttu-id="35125-817">持續時間</span><span class="sxs-lookup"><span data-stu-id="35125-817">Duration</span></span></li>
</ul><span data-ttu-id="35125-818">
</dt>
<dt>持久性路徑： &lt;路徑 &gt; </dt>動態簽章
<dt>版本： &lt; 版本 &gt; 號碼</dt>動態簽章
<dt>編譯時間戳： &lt; 時間戳記 &gt; </dt>
<dt>移除原因：</dt> 
<dt> 持續性限制類型：持續性 &lt; 限制類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="35125-819">VDM 版本</span><span class="sxs-lookup"><span data-stu-id="35125-819">VDM version</span></span></li>
<li><span data-ttu-id="35125-820">時間 戳</span><span class="sxs-lookup"><span data-stu-id="35125-820">Timestamp</span></span></li>
<li><span data-ttu-id="35125-821">無限制</span><span class="sxs-lookup"><span data-stu-id="35125-821">No limit</span></span></li>
</ul><span data-ttu-id="35125-822">
</dt>
<dt>持續性限制： fastpath 簽章的持續限制。</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-823">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-824">不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="35125-824">No action is necessary.</span></span> <span data-ttu-id="35125-825">Microsoft Defender 防病毒用戶端的狀態良好。</span><span class="sxs-lookup"><span data-stu-id="35125-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="35125-826">當動態簽章服務成功刪除過期動態定義時，便會報告此事件。</span><span class="sxs-lookup"><span data-stu-id="35125-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-827">事件 ID: 2012</span><span class="sxs-lookup"><span data-stu-id="35125-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-828">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-830">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-830">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-831">
<b>反惡意程式碼引擎在嘗試使用動態簽章服務時發生錯誤。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-832">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-833">Microsoft Defender 防毒程式嘗試使用動態簽章 <i>服務</i>時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="35125-834">
<dt>目前的特徵碼版本： &lt;目前 &gt; </dt>的簽章版本 
<dt> 簽名類型： &lt; 簽名類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="35125-835">防毒</span><span class="sxs-lookup"><span data-stu-id="35125-835">Antivirus</span></span></li>
<li><span data-ttu-id="35125-836">間諜</span><span class="sxs-lookup"><span data-stu-id="35125-836">Antispyware</span></span></li>
<li><span data-ttu-id="35125-837">軟體</span><span class="sxs-lookup"><span data-stu-id="35125-837">Antimalware</span></span></li>
<li><span data-ttu-id="35125-838">網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="35125-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="35125-839">
</dt>
<dt>目前引擎版本： &lt;目前引擎版本 &gt; </dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤碼錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt> 
<dt>動態特徵碼類型：動態簽章 &lt; 類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="35125-840">版本</span><span class="sxs-lookup"><span data-stu-id="35125-840">Version</span></span></li>
<li><span data-ttu-id="35125-841">時間 戳</span><span class="sxs-lookup"><span data-stu-id="35125-841">Timestamp</span></span></li>
<li><span data-ttu-id="35125-842">無限制</span><span class="sxs-lookup"><span data-stu-id="35125-842">No limit</span></span></li>
<li><span data-ttu-id="35125-843">持續時間</span><span class="sxs-lookup"><span data-stu-id="35125-843">Duration</span></span></li>
</ul><span data-ttu-id="35125-844">
</dt>
<dt>持久性路徑： &lt;路徑 &gt; </dt>動態簽章
<dt>版本： &lt; 版本 &gt; 號碼</dt>動態簽章
<dt>編譯時間戳： &lt; timestamp &gt; </dt> 
<dt> 持續性限制類型：持續性 &lt; 限制類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="35125-845">VDM 版本</span><span class="sxs-lookup"><span data-stu-id="35125-845">VDM version</span></span></li>
<li><span data-ttu-id="35125-846">時間 戳</span><span class="sxs-lookup"><span data-stu-id="35125-846">Timestamp</span></span></li>
<li><span data-ttu-id="35125-847">無限制</span><span class="sxs-lookup"><span data-stu-id="35125-847">No limit</span></span></li>
</ul><span data-ttu-id="35125-848">
</dt>
<dt>持續性限制： fastpath 簽章的持續限制。</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-849">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-850">檢查您的網際網路連線設定。</span><span class="sxs-lookup"><span data-stu-id="35125-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-851">事件 ID: 2013</span><span class="sxs-lookup"><span data-stu-id="35125-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-852">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-854">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-854">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-855">
<b>動態特徵碼服務刪除所有動態定義。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-856">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-857">Microsoft Defender 防毒程式已捨棄所有動態簽章 <i>服務</i> 的簽名。</span><span class="sxs-lookup"><span data-stu-id="35125-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="35125-858">
<dt>目前的特徵碼版本： &lt; 目前的特徵碼版本&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-859">事件 ID: 2020</span><span class="sxs-lookup"><span data-stu-id="35125-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-860">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-862">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-862">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-863">
<b>反惡意程式碼引擎下載乾淨的檔案。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-864">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-865">Microsoft Defender 防病毒已下載乾淨的檔案。</span><span class="sxs-lookup"><span data-stu-id="35125-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="35125-866">
<dt>檔案名： &lt;檔案名 &gt; 的檔案名。</dt>
<dt>目前的特徵碼版本： &lt;目前的特徵 &gt; 碼版本</dt>
<dt>目前引擎版本： &lt; 目前 &gt; 引擎版本</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-867">事件 ID: 2021</span><span class="sxs-lookup"><span data-stu-id="35125-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-868">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-870">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-870">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-871">
<b>反惡意程式碼引擎無法下載乾淨的檔案。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-872">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-873">Microsoft Defender 防毒程式嘗試下載乾淨檔案時，發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="35125-874">
<dt>檔案名： &lt;檔案名 &gt; 的檔案名。</dt>
<dt>目前的特徵碼版本： &lt;&gt;目前</dt>的簽章版本
<dt>目前引擎版本： &lt; 目前 &gt; 引擎版本</dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤碼錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-874">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-875">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-876">檢查您的網際網路連線設定。</span><span class="sxs-lookup"><span data-stu-id="35125-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="35125-877">Microsoft Defender 防病毒用戶端在使用動態簽章服務，將最新的定義下載至特定威脅時，發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="35125-878">這種錯誤可能是網路連線問題所造成。</span><span class="sxs-lookup"><span data-stu-id="35125-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-879">事件 ID: 2030</span><span class="sxs-lookup"><span data-stu-id="35125-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-880">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-882">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-882">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-883">
<b>反惡意程式碼引擎已下載，並設定為在下一個系統重新開機時離線執行。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-884">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-885">在下一次重新開機時，Microsoft Defender 防病毒已下載並設定離線防病毒以執行。</span><span class="sxs-lookup"><span data-stu-id="35125-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-886">事件 ID: 2031</span><span class="sxs-lookup"><span data-stu-id="35125-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-887">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-889">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-889">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-890">
<b>反惡意程式碼引擎無法下載和設定離線掃描。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-891">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-892">Microsoft Defender 防毒程式嘗試下載及設定離線防病毒時，發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="35125-893">
<dt>錯誤碼： &lt;&gt;與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-894">事件 ID: 2040</span><span class="sxs-lookup"><span data-stu-id="35125-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-895">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-897">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-897">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-898">
<b>此作業系統版本的反惡意軟體支援很快就會結束。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-899">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-900">您的作業系統支援即將到期。</span><span class="sxs-lookup"><span data-stu-id="35125-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="35125-901">在不支援的作業系統上執行 Microsoft Defender 防毒程式，不是適當的解決方案來防禦威脅。</span><span class="sxs-lookup"><span data-stu-id="35125-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-902">事件 ID: 2041</span><span class="sxs-lookup"><span data-stu-id="35125-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-903">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-905">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-905">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-906">
<b>此作業系統的反惡意軟體支援已結束。您必須升級作業系統以繼續支援。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-907">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-908">您的作業系統支援已過期。</span><span class="sxs-lookup"><span data-stu-id="35125-908">The support for your operating system has expired.</span></span> <span data-ttu-id="35125-909">在不支援的作業系統上執行 Microsoft Defender 防毒程式，不是適當的解決方案來防禦威脅。</span><span class="sxs-lookup"><span data-stu-id="35125-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-910">事件 ID: 2042</span><span class="sxs-lookup"><span data-stu-id="35125-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-911">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-913">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-913">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-914">
<b>反惡意軟體引擎不再支援此作業系統，而且不再從惡意程式碼保護您的系統。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-915">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-916">您的作業系統支援已過期。</span><span class="sxs-lookup"><span data-stu-id="35125-916">The support for your operating system has expired.</span></span> <span data-ttu-id="35125-917">您的作業系統不再支援 Microsoft Defender 防病毒，已停止運作，而且無法防範惡意程式碼威脅。</span><span class="sxs-lookup"><span data-stu-id="35125-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-918">事件 ID: 3002</span><span class="sxs-lookup"><span data-stu-id="35125-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-919">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-921">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-921">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-922">
<b>即時保護發生錯誤，失敗。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-923">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-924">Microsoft Defender 防病毒 Real-Time 保護功能發生錯誤，失敗。</span><span class="sxs-lookup"><span data-stu-id="35125-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="35125-925">
<dt>Feature： &lt; feature &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="35125-926">存取</span><span class="sxs-lookup"><span data-stu-id="35125-926">On Access</span></span></li>
<li><span data-ttu-id="35125-927">Internet Explorer 下載和 Microsoft Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="35125-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="35125-928">行為監控</span><span class="sxs-lookup"><span data-stu-id="35125-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="35125-929">網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="35125-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="35125-930">
</dt>
<dt>錯誤碼： &lt;&gt;與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>
<dt>原因： Microsoft Defender 防病毒即時防護已重新開機某項功能的原因。</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-931">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-932">您應該重新開機系統，然後執行完整掃描，因為它&#39;可能一段時間沒有保護系統。</span><span class="sxs-lookup"><span data-stu-id="35125-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="35125-933">Microsoft Defender 防病毒用戶端&#39;即時保護功能發生錯誤，因為其中一個服務無法啟動。</span><span class="sxs-lookup"><span data-stu-id="35125-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="35125-934">如果後面接著是3007事件識別碼，表示失敗為暫時的，反惡意軟體用戶端已從失敗中復原。</span><span class="sxs-lookup"><span data-stu-id="35125-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-935">事件 ID: 3007</span><span class="sxs-lookup"><span data-stu-id="35125-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-936">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-938">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-938">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-939">
<b>即時保護已從失敗中復原。當您看到此錯誤時，建議執行完整系統掃描。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-940">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-941">Microsoft Defender 防病毒即時保護已重新開機功能。</span><span class="sxs-lookup"><span data-stu-id="35125-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="35125-942">建議您執行完整系統掃描，以偵測此代理程式中斷時可能錯過的任何專案。</span><span class="sxs-lookup"><span data-stu-id="35125-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="35125-943">
<dt>Feature： &lt; feature &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="35125-944">存取</span><span class="sxs-lookup"><span data-stu-id="35125-944">On Access</span></span></li>
<li><span data-ttu-id="35125-945">IE 下載和 Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="35125-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="35125-946">行為監控</span><span class="sxs-lookup"><span data-stu-id="35125-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="35125-947">網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="35125-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="35125-948">
</dt>
<dt>原因： Microsoft Defender 防病毒即時防護已重新開機某項功能的原因。</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-949">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-950">已重新開機即時保護功能。</span><span class="sxs-lookup"><span data-stu-id="35125-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="35125-951">如果發生此事件，請與 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技術支援</a>人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="35125-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-952">事件 ID: 5000</span><span class="sxs-lookup"><span data-stu-id="35125-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-953">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-955">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-955">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-956">
<b>已啟用即時保護。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-957">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-958">已啟用針對惡意程式碼和其他可能有害軟體的 Microsoft Defender 防病毒即時防護掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-959">事件 ID: 5001</span><span class="sxs-lookup"><span data-stu-id="35125-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-960">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-962">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-962">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-963">
<b>已停用即時保護。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-964">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-965">已停用 Microsoft Defender 防毒軟體和其他可能有害軟體的即時防護掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-966">事件 ID: 5004</span><span class="sxs-lookup"><span data-stu-id="35125-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-967">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-969">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-969">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-970">
<b>已變更即時保護設定。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-971">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-972">Microsoft Defender 防病毒即時保護功能設定已經變更。</span><span class="sxs-lookup"><span data-stu-id="35125-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="35125-973">
<dt>Feature： &lt; feature &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="35125-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="35125-974">存取</span><span class="sxs-lookup"><span data-stu-id="35125-974">On Access</span></span></li>
<li><span data-ttu-id="35125-975">IE 下載和 Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="35125-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="35125-976">行為監控</span><span class="sxs-lookup"><span data-stu-id="35125-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="35125-977">網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="35125-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="35125-978">
</dt>
<dt>配置： </dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-979">事件 ID: 5007</span><span class="sxs-lookup"><span data-stu-id="35125-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-980">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-982">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-982">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-983">
<b>已變更反惡意軟體平臺設定。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-984">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-985">Microsoft Defender 防病毒設定已經變更。</span><span class="sxs-lookup"><span data-stu-id="35125-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="35125-986">如果這是未預期的事件，您應該檢查設定，因為這可能是惡意程式碼的結果。</span><span class="sxs-lookup"><span data-stu-id="35125-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="35125-987">
<dt>舊值： &lt;舊值號碼 &gt; 舊的防病毒設定值。</dt>
<dt>新值： &lt;新值號碼 &gt; 新的防病毒設定值。</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-988">事件 ID: 5008</span><span class="sxs-lookup"><span data-stu-id="35125-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-989">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-991">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-991">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-992">
<b>反惡意軟體引擎發生錯誤，失敗。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-993">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-994">Microsoft Defender 防病毒引擎因未預期的錯誤而終止。</span><span class="sxs-lookup"><span data-stu-id="35125-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="35125-995">
<dt>失敗類型： &lt;失敗類型 &gt; ，例如：損毀或懸掛</dt>
<dt>例外狀況碼： &lt; 錯誤碼 &gt; </dt> 
<dt>resource： &lt; resource &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-996">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-997">若要疑難排解此事件：</span><span class="sxs-lookup"><span data-stu-id="35125-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="35125-998">嘗試重新開機服務。</span><span class="sxs-lookup"><span data-stu-id="35125-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="35125-999">若為反惡意軟體、防病毒和間諜軟體，請在提升許可權的命令提示字元處，輸入 <b>net stop msmpsvc</b>，然後輸入 <b>net start msmpsvc</b> 以重新開機反惡意程式碼引擎。</span><span class="sxs-lookup"><span data-stu-id="35125-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="35125-1000">針對 <i>網路檢查系統</i>，在提升許可權的命令提示字元處，輸入 <b>net start nissrv</b>，然後輸入 <b>net start nissrv</b> ，以使用 NiSSRV.exe 檔案重新開機 <i>網路檢查系統</i> 引擎。</span><span class="sxs-lookup"><span data-stu-id="35125-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="35125-1001">若失敗，請存取 <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支援網站</a>  ，並在 <b>搜尋</b> 方塊中輸入錯誤號碼，以查詢錯誤碼，並與 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技術支援</a>人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="35125-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1002">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="35125-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="35125-1003">Microsoft Defender 防病毒用戶端引擎因未預期的錯誤而停止。</span><span class="sxs-lookup"><span data-stu-id="35125-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="35125-1004">若要疑難排解此事件：</span><span class="sxs-lookup"><span data-stu-id="35125-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="35125-1005">再次執行掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="35125-1006">若失敗，請移至 [ <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支援網站</a>]，然後在 <b>搜尋</b> 方塊中輸入錯誤號碼，以尋找錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="35125-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="35125-1007">連絡 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技術支援</a>。</span><span class="sxs-lookup"><span data-stu-id="35125-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1008">事件 ID: 5009</span><span class="sxs-lookup"><span data-stu-id="35125-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-1009">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1011">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-1012">
<b>已啟用對惡意程式碼和其他可能有害軟體的掃描。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1013">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-1014">已啟用 Microsoft Defender 防毒軟體和其他可能有害軟體的掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1015">事件 ID: 5010</span><span class="sxs-lookup"><span data-stu-id="35125-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-1016">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1018">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-1019">
<b>已停用針對惡意程式碼和其他可能有害軟體的掃描。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1020">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-1021">已停用 Microsoft Defender 防毒軟體和其他可能有害軟體的掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1022">事件 ID: 5011</span><span class="sxs-lookup"><span data-stu-id="35125-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-1023">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1025">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-1026">
<b>已啟用病毒掃描。</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1027">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-1028">已啟用適用于病毒的 Microsoft Defender 防病毒掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1029">事件 ID: 5012</span><span class="sxs-lookup"><span data-stu-id="35125-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-1030">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1032">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-1033">
<b>已停用掃描病毒。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1034">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-1035">已停用 Microsoft Defender 防病毒掃描防病毒功能。</span><span class="sxs-lookup"><span data-stu-id="35125-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1036">事件 ID: 5100</span><span class="sxs-lookup"><span data-stu-id="35125-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-1037">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1039">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-1040">
<b>反惡意程式碼平臺即將到期。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1041">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-1042">Microsoft Defender 防病毒已輸入寬限期，很快就會到期。</span><span class="sxs-lookup"><span data-stu-id="35125-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="35125-1043">到期後，此程式會停用防護病毒、間諜軟體和其他可能不需要的軟體。</span><span class="sxs-lookup"><span data-stu-id="35125-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="35125-1044">
<dt>到期原因： Microsoft Defender 防毒程式會到期的原因。</dt>
<dt>到期日： Microsoft Defender 防毒程式會到期的日期。</dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1045">事件 ID: 5101</span><span class="sxs-lookup"><span data-stu-id="35125-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="35125-1046">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="35125-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="35125-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1048">消息：</span><span class="sxs-lookup"><span data-stu-id="35125-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="35125-1049">
<b>反惡意程式碼平臺已過期。 </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1050">描述：</span><span class="sxs-lookup"><span data-stu-id="35125-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="35125-1051">Microsoft Defender 防病毒寬限時間已到期。</span><span class="sxs-lookup"><span data-stu-id="35125-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="35125-1052">停用防護病毒、間諜軟體和其他可能不需要的軟體。</span><span class="sxs-lookup"><span data-stu-id="35125-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="35125-1053">
<dt>到期原因：</dt>
<dt>終止日期： </dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。 </dt>
</span><span class="sxs-lookup"><span data-stu-id="35125-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="35125-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender 防病毒用戶端錯誤碼如果 Microsoft Defender 防毒程式遇到任何問題，它通常會提供錯誤代碼來協助您進行問題的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="35125-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="35125-1055">最常見的錯誤是表示安裝更新時發生問題。</span><span class="sxs-lookup"><span data-stu-id="35125-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="35125-1056">本節提供下列有關 Microsoft Defender 防病毒用戶端錯誤的資訊。</span><span class="sxs-lookup"><span data-stu-id="35125-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="35125-1057">-   錯誤碼的 -   可能原因為錯誤 -   通知的現在原因</span><span class="sxs-lookup"><span data-stu-id="35125-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="35125-1058">使用這些表格中的資訊，協助疑難排解 Microsoft Defender 防毒程式錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="35125-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="35125-1059">錯誤碼：0x80508007</span><span class="sxs-lookup"><span data-stu-id="35125-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="35125-1060">訊息</span><span class="sxs-lookup"><span data-stu-id="35125-1060">Message</span></span></td>
<td><span data-ttu-id="35125-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1062">可能的原因</span><span class="sxs-lookup"><span data-stu-id="35125-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="35125-1063">此錯誤表示您的記憶體可能不足。</span><span class="sxs-lookup"><span data-stu-id="35125-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="35125-1064">解決方案</span><span class="sxs-lookup"><span data-stu-id="35125-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="35125-1065">檢查裝置上可用的記憶體。</span><span class="sxs-lookup"><span data-stu-id="35125-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="35125-1066">關閉任何未使用的應用程式，以釋放裝置上的記憶體。</span><span class="sxs-lookup"><span data-stu-id="35125-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="35125-1067">重新開機裝置，然後再次執行掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1068">錯誤碼：0x8050800C</span><span class="sxs-lookup"><span data-stu-id="35125-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="35125-1069">訊息</span><span class="sxs-lookup"><span data-stu-id="35125-1069">Message</span></span></td>
<td><span data-ttu-id="35125-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="35125-1071">可能的原因</span><span class="sxs-lookup"><span data-stu-id="35125-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="35125-1072">此錯誤表示您的安全性產品可能有問題。</span><span class="sxs-lookup"><span data-stu-id="35125-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="35125-1073">解決方案</span><span class="sxs-lookup"><span data-stu-id="35125-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="35125-1074">更新定義。</span><span class="sxs-lookup"><span data-stu-id="35125-1074">Update the definitions.</span></span> <span data-ttu-id="35125-1075">可</span><span class="sxs-lookup"><span data-stu-id="35125-1075">Either:</span></span><ol>
<li><span data-ttu-id="35125-1076">在 Microsoft Defender 防毒軟體的 [<b>更新</b>] 索引標籤上，按一下 [<b>更新定義</b>] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="35125-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="35125-1077">或是，</span><span class="sxs-lookup"><span data-stu-id="35125-1077">Or,</span></span>
</li>
<li><span data-ttu-id="35125-1078">從 <a href="https://aka.ms/wdsi">Microsoft 安全性情報網站</a>下載最新的定義。</span><span class="sxs-lookup"><span data-stu-id="35125-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="35125-1079">附注：從網站下載的定義檔案大小可超過 60 MB，不應做為更新定義的長期方案。</span><span class="sxs-lookup"><span data-stu-id="35125-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="35125-1080">執行完整掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="35125-1081">重新開機裝置，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="35125-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1082">錯誤碼：0x80508020</span><span class="sxs-lookup"><span data-stu-id="35125-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="35125-1083">訊息</span><span class="sxs-lookup"><span data-stu-id="35125-1083">Message</span></span></td>
<td><span data-ttu-id="35125-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="35125-1085">可能的原因</span><span class="sxs-lookup"><span data-stu-id="35125-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="35125-1086">此錯誤表示可能存在引擎設定錯誤;這通常與不允許引擎正確運作的輸入資料相關。</span><span class="sxs-lookup"><span data-stu-id="35125-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1087">錯誤碼：0x805080211</span><span class="sxs-lookup"><span data-stu-id="35125-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="35125-1088">訊息</span><span class="sxs-lookup"><span data-stu-id="35125-1088">Message</span></span></td>
<td><span data-ttu-id="35125-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="35125-1090">可能的原因</span><span class="sxs-lookup"><span data-stu-id="35125-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="35125-1091">此錯誤表示 Microsoft Defender 防毒程式無法隔離威脅。</span><span class="sxs-lookup"><span data-stu-id="35125-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1092">錯誤碼：0x80508022</span><span class="sxs-lookup"><span data-stu-id="35125-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="35125-1093">訊息</span><span class="sxs-lookup"><span data-stu-id="35125-1093">Message</span></span></td>
<td><span data-ttu-id="35125-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="35125-1095">可能的原因</span><span class="sxs-lookup"><span data-stu-id="35125-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="35125-1096">此錯誤指出需要重新開機以完成威脅移除。</span><span class="sxs-lookup"><span data-stu-id="35125-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="35125-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="35125-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="35125-1098">訊息</span><span class="sxs-lookup"><span data-stu-id="35125-1098">Message</span></span></td>
<td><span data-ttu-id="35125-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="35125-1100">可能的原因</span><span class="sxs-lookup"><span data-stu-id="35125-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="35125-1101">此錯誤表示此威脅可能不再出現在媒體上，或惡意程式碼可能會停止您掃描裝置。</span><span class="sxs-lookup"><span data-stu-id="35125-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="35125-1102">解決方案</span><span class="sxs-lookup"><span data-stu-id="35125-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="35125-1103">請先執行 <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft 安全掃描器</a> 更新您的安全性軟體，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="35125-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1104">錯誤碼：0x80508024</span><span class="sxs-lookup"><span data-stu-id="35125-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="35125-1105">訊息</span><span class="sxs-lookup"><span data-stu-id="35125-1105">Message</span></span></td>
<td><span data-ttu-id="35125-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="35125-1107">可能的原因</span><span class="sxs-lookup"><span data-stu-id="35125-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="35125-1108">此錯誤表示可能需要進行完整系統掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="35125-1109">解決方案</span><span class="sxs-lookup"><span data-stu-id="35125-1109">Resolution</span></span></td><td>
<span data-ttu-id="35125-1110">執行完整系統掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1111">錯誤碼：0x80508025</span><span class="sxs-lookup"><span data-stu-id="35125-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="35125-1112">訊息</span><span class="sxs-lookup"><span data-stu-id="35125-1112">Message</span></span></td>
<td><span data-ttu-id="35125-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="35125-1114">可能的原因</span><span class="sxs-lookup"><span data-stu-id="35125-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="35125-1115">此錯誤指出需要手動步驟以完成威脅移除。</span><span class="sxs-lookup"><span data-stu-id="35125-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="35125-1116">解決方案</span><span class="sxs-lookup"><span data-stu-id="35125-1116">Resolution</span></span></td><td>
<span data-ttu-id="35125-1117">遵循 <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft 惡意程式碼保護百科全書</a>中所述的手動修正步驟。</span><span class="sxs-lookup"><span data-stu-id="35125-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="35125-1118">您可以在事件歷程記錄中尋找威脅特有的連結。</span><span class="sxs-lookup"><span data-stu-id="35125-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1119">錯誤碼：0x80508026</span><span class="sxs-lookup"><span data-stu-id="35125-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="35125-1120">訊息</span><span class="sxs-lookup"><span data-stu-id="35125-1120">Message</span></span></td>
<td><span data-ttu-id="35125-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="35125-1122">可能的原因</span><span class="sxs-lookup"><span data-stu-id="35125-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="35125-1123">此錯誤表示可能不支援在容器類型中移除。</span><span class="sxs-lookup"><span data-stu-id="35125-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="35125-1124">解決方案</span><span class="sxs-lookup"><span data-stu-id="35125-1124">Resolution</span></span></td><td>
<span data-ttu-id="35125-1125">Microsoft Defender 防病毒無法修正在封存中偵測到的威脅。</span><span class="sxs-lookup"><span data-stu-id="35125-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="35125-1126">請考慮手動移除偵測到的資源。</span><span class="sxs-lookup"><span data-stu-id="35125-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1127">錯誤碼：0x80508027</span><span class="sxs-lookup"><span data-stu-id="35125-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="35125-1128">訊息</span><span class="sxs-lookup"><span data-stu-id="35125-1128">Message</span></span></td>
<td><span data-ttu-id="35125-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="35125-1130">可能的原因</span><span class="sxs-lookup"><span data-stu-id="35125-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="35125-1131">此錯誤表示可能停用刪除低和中威脅的移除。</span><span class="sxs-lookup"><span data-stu-id="35125-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="35125-1132">解決方案</span><span class="sxs-lookup"><span data-stu-id="35125-1132">Resolution</span></span></td><td>
<span data-ttu-id="35125-1133">檢查偵測到的威脅，並視需要加以解決。</span><span class="sxs-lookup"><span data-stu-id="35125-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1134">錯誤碼：0x80508029</span><span class="sxs-lookup"><span data-stu-id="35125-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="35125-1135">訊息</span><span class="sxs-lookup"><span data-stu-id="35125-1135">Message</span></span></td>
<td><span data-ttu-id="35125-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="35125-1137">可能的原因</span><span class="sxs-lookup"><span data-stu-id="35125-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="35125-1138">此錯誤表示需要重新掃描威脅。</span><span class="sxs-lookup"><span data-stu-id="35125-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="35125-1139">解決方案</span><span class="sxs-lookup"><span data-stu-id="35125-1139">Resolution</span></span></td><td>
<span data-ttu-id="35125-1140">執行完整系統掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1141">錯誤碼：0x80508030</span><span class="sxs-lookup"><span data-stu-id="35125-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="35125-1142">訊息</span><span class="sxs-lookup"><span data-stu-id="35125-1142">Message</span></span></td>
<td><span data-ttu-id="35125-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="35125-1144">可能的原因</span><span class="sxs-lookup"><span data-stu-id="35125-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="35125-1145">此錯誤表示需要離線掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="35125-1146">解決方案</span><span class="sxs-lookup"><span data-stu-id="35125-1146">Resolution</span></span></td><td>
<span data-ttu-id="35125-1147">執行離線的 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="35125-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="35125-1148">您可以在 <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">離線的 Microsoft Defender 防病毒文章</a>中閱讀如何執行此動作的資訊。</span><span class="sxs-lookup"><span data-stu-id="35125-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="35125-1149">錯誤碼：0x80508031</span><span class="sxs-lookup"><span data-stu-id="35125-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="35125-1150">訊息</span><span class="sxs-lookup"><span data-stu-id="35125-1150">Message</span></span></td>
<td><span data-ttu-id="35125-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="35125-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="35125-1152">可能的原因</span><span class="sxs-lookup"><span data-stu-id="35125-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="35125-1153">此錯誤表示 Microsoft Defender 防毒軟體不支援目前版本的平臺，且需要新版本的平臺。</span><span class="sxs-lookup"><span data-stu-id="35125-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="35125-1154">解決方案</span><span class="sxs-lookup"><span data-stu-id="35125-1154">Resolution</span></span></td><td>
<span data-ttu-id="35125-1155">在 Windows 10 中您只能使用 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="35125-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="35125-1156">若為 Windows 8、Windows 7 和 Windows Vista，您可以使用 <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>。</span><span class="sxs-lookup"><span data-stu-id="35125-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="35125-1157">

<a id="internal-error-codes"></a> 在 Microsoft Defender 防病毒的內部測試期間會使用下列錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="35125-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="35125-1158">如果您看到這些錯誤，您可以嘗試 [更新定義](manage-updates-baselines-microsoft-defender-antivirus.md) ，並直接在端點上強制重新掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="35125-1159">內部錯誤碼</span><span class="sxs-lookup"><span data-stu-id="35125-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="35125-1160"><b>錯誤碼</b></span><span class="sxs-lookup"><span data-stu-id="35125-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="35125-1161">顯示的訊息</span><span class="sxs-lookup"><span data-stu-id="35125-1161">Message displayed</span></span></th>
<th><span data-ttu-id="35125-1162">錯誤和解決的可能原因</span><span class="sxs-lookup"><span data-stu-id="35125-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="35125-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="35125-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="35125-1165">請檢查您的網際網路連線，然後再次執行掃描。</span><span class="sxs-lookup"><span data-stu-id="35125-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="35125-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="35125-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>發送</span><span class="sxs-lookup"><span data-stu-id="35125-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="35125-1168">這是內部錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-1168">This is an internal error.</span></span> <span data-ttu-id="35125-1169">原因並未明確定義。</span><span class="sxs-lookup"><span data-stu-id="35125-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="35125-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="35125-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="35125-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="35125-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="35125-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="35125-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="35125-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="35125-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="35125-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="35125-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="35125-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="35125-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="35125-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="35125-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="35125-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="35125-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="35125-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="35125-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="35125-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="35125-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="35125-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="35125-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="35125-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="35125-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="35125-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="35125-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="35125-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="35125-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="35125-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="35125-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="35125-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="35125-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="35125-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="35125-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="35125-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="35125-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="35125-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="35125-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="35125-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="35125-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="35125-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="35125-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="35125-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="35125-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="35125-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="35125-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="35125-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="35125-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="35125-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="35125-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="35125-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="35125-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="35125-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="35125-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="35125-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="35125-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="35125-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="35125-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="35125-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="35125-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="35125-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="35125-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="35125-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="35125-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="35125-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="35125-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="35125-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="35125-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="35125-1238">這是內部錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-1238">This is an internal error.</span></span> <span data-ttu-id="35125-1239">當惡意程式碼移除失敗時，可能會觸發此情況。</span><span class="sxs-lookup"><span data-stu-id="35125-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="35125-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="35125-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="35125-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="35125-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="35125-1242">這是內部錯誤。</span><span class="sxs-lookup"><span data-stu-id="35125-1242">This is an internal error.</span></span> <span data-ttu-id="35125-1243">它可能會在掃描無法完成時觸發。</span><span class="sxs-lookup"><span data-stu-id="35125-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="35125-1244">相關主題</span><span class="sxs-lookup"><span data-stu-id="35125-1244">Related topics</span></span>

- [<span data-ttu-id="35125-1245">報告 Microsoft Defender 防防毒保護</span><span class="sxs-lookup"><span data-stu-id="35125-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="35125-1246">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="35125-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)