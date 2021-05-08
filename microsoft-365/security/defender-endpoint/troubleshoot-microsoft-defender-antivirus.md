---
title: Microsoft Defender AV 事件 IDs 和錯誤碼
description: 查詢 Microsoft Defender 防毒軟體事件 IDs 和錯誤的原因和解決方案
keywords: 事件、錯誤碼、siem、記錄、疑難排解、wef、windows 事件轉移
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: cd222760f3a5cc005c679bf28365237cc70e8950
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275345"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="6cfd5-104">檢查事件記錄和錯誤碼以疑難排解 Microsoft Defender 防毒軟體的問題</span><span class="sxs-lookup"><span data-stu-id="6cfd5-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6cfd5-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="6cfd5-105">**Applies to:**</span></span>

- [<span data-ttu-id="6cfd5-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6cfd5-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="6cfd5-107">如果您遇到 Microsoft Defender 防毒軟體的問題，可搜尋本主題中的表格，以找出相符的問題和可能的解決方案。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="6cfd5-108">[資料表] 清單：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-108">The tables list:</span></span>

- <span data-ttu-id="6cfd5-109">[Microsoft Defender 防毒軟體事件 IDs](#windows-defender-av-ids) (都會套用 Windows 10 及 Windows Server 2016) </span><span class="sxs-lookup"><span data-stu-id="6cfd5-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="6cfd5-110">Microsoft Defender 防毒軟體用戶端錯誤碼</span><span class="sxs-lookup"><span data-stu-id="6cfd5-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="6cfd5-111">內部 Microsoft Defender 防毒軟體用戶端錯誤碼 (在開發及測試期間由 Microsoft 使用) </span><span class="sxs-lookup"><span data-stu-id="6cfd5-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="6cfd5-112">您也可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Microsoft Defender for Endpoint 示範網站，以確認下列功能正在運作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="6cfd5-113">雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="6cfd5-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="6cfd5-114">Fast 教學 (包括第一次看到區塊) </span><span class="sxs-lookup"><span data-stu-id="6cfd5-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="6cfd5-115">可能有害的應用程式封鎖</span><span class="sxs-lookup"><span data-stu-id="6cfd5-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="6cfd5-116">Microsoft Defender 防毒軟體事件 IDs</span><span class="sxs-lookup"><span data-stu-id="6cfd5-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="6cfd5-117">Windows 事件記錄檔中 Microsoft Defender 防毒軟體的記錄事件 IDs。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="6cfd5-118">您可以直接查看事件記錄檔，或者，如果您有協力廠商的安全性資訊和事件管理 (SIEM) 工具，也可以使用[Microsoft Defender 防毒軟體用戶端事件 IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids)以檢查您的端點中的特定事件及錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="6cfd5-119">本節中的表格列出主 Microsoft Defender 防毒軟體事件 IDs，盡可能在可能的情況下，提供修正或解決錯誤的建議解決方案。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="6cfd5-120">若要查看 Microsoft Defender 防毒軟體事件</span><span class="sxs-lookup"><span data-stu-id="6cfd5-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="6cfd5-121">開啟 **事件檢視器**。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="6cfd5-122">在主控台樹中，展開 [**應用程式及服務記錄**] **，** 然後 **Windows**，再 **Windows Defender**]。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="6cfd5-123">按兩下 [ **操作**]。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="6cfd5-124">在詳細資料窗格中，查看個別事件的清單，以尋找您的事件。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="6cfd5-125">按一下該事件，在 [ **一般** ] 和 [ **詳細資料** ] 索引標籤底下的下部窗格中查看事件的特定詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="6cfd5-126">事件 ID: 1000</span><span class="sxs-lookup"><span data-stu-id="6cfd5-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-127">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="6cfd5-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-129">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-129">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-130">
<b>已開始反惡意軟體掃描。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="6cfd5-131">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="6cfd5-132">
<dt>掃描 ID: &lt;相關掃描的識別碼 &gt; 號碼。</dt> 
<dt>掃描類型： &lt; 掃描類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-133">防毒</span><span class="sxs-lookup"><span data-stu-id="6cfd5-133">Antivirus</span></span></li>
<li><span data-ttu-id="6cfd5-134">間諜</span><span class="sxs-lookup"><span data-stu-id="6cfd5-134">Antispyware</span></span></li>
<li><span data-ttu-id="6cfd5-135">軟體</span><span class="sxs-lookup"><span data-stu-id="6cfd5-135">Antimalware</span></span></li>
</ul><span data-ttu-id="6cfd5-136">
</dt>
<dt>掃描參數： &lt; 掃描參數 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-137">完整掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-137">Full scan</span></span></li>
<li><span data-ttu-id="6cfd5-138">快速掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-138">Quick scan</span></span></li>
<li><span data-ttu-id="6cfd5-139">客戶掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-139">Customer scan</span></span></li>
</ul><span data-ttu-id="6cfd5-140">
</dt>
<dt>掃描資源： &lt;資源 (例如已掃描的 files/directory/BHO) 。 &gt; </dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-141">事件 ID: 1001</span><span class="sxs-lookup"><span data-stu-id="6cfd5-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-142">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-144">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-144">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-145">
<b>反惡意軟體掃描完成。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-146">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="6cfd5-147">
<dt>掃描 ID: &lt;相關掃描的識別碼 &gt; 號碼。</dt> 
<dt>掃描類型： &lt; 掃描類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-148">防毒</span><span class="sxs-lookup"><span data-stu-id="6cfd5-148">Antivirus</span></span></li>
<li><span data-ttu-id="6cfd5-149">間諜</span><span class="sxs-lookup"><span data-stu-id="6cfd5-149">Antispyware</span></span></li>
<li><span data-ttu-id="6cfd5-150">軟體</span><span class="sxs-lookup"><span data-stu-id="6cfd5-150">Antimalware</span></span></li>
</ul><span data-ttu-id="6cfd5-151">
</dt>
<dt>掃描參數： &lt; 掃描參數 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-152">完整掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-152">Full scan</span></span></li>
<li><span data-ttu-id="6cfd5-153">快速掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-153">Quick scan</span></span></li>
<li><span data-ttu-id="6cfd5-154">客戶掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-154">Customer scan</span></span></li>
</ul><span data-ttu-id="6cfd5-155">
</dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
<dt>掃描時間： &lt; 掃描的持續時間。 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-156">事件 ID: 1002</span><span class="sxs-lookup"><span data-stu-id="6cfd5-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-157">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-159">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-159">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-160">
<b>反惡意軟體掃描在完成前已停止。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-161">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="6cfd5-162">
<dt>掃描 ID: &lt;相關掃描的識別碼 &gt; 號碼。</dt> 
<dt>掃描類型： &lt; 掃描類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-163">防毒</span><span class="sxs-lookup"><span data-stu-id="6cfd5-163">Antivirus</span></span></li>
<li><span data-ttu-id="6cfd5-164">間諜</span><span class="sxs-lookup"><span data-stu-id="6cfd5-164">Antispyware</span></span></li>
<li><span data-ttu-id="6cfd5-165">軟體</span><span class="sxs-lookup"><span data-stu-id="6cfd5-165">Antimalware</span></span></li>
</ul><span data-ttu-id="6cfd5-166">
</dt>
<dt>掃描參數： &lt; 掃描參數 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-167">完整掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-167">Full scan</span></span></li>
<li><span data-ttu-id="6cfd5-168">快速掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-168">Quick scan</span></span></li>
<li><span data-ttu-id="6cfd5-169">客戶掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-169">Customer scan</span></span></li>
</ul><span data-ttu-id="6cfd5-170">
</dt>
<dt>使用者： &lt;網域 &gt; &amp; lt;使用者 &gt; </dt>
<dt>掃描時間： &lt; 掃描的持續時間。 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-171">事件 ID: 1003</span><span class="sxs-lookup"><span data-stu-id="6cfd5-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-172">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-174">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-174">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-175">
<b>已暫停反惡意程式碼掃描。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-176">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="6cfd5-177">
<dt>掃描 ID: &lt;相關掃描的識別碼 &gt; 號碼。</dt> 
<dt>掃描類型： &lt; 掃描類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-178">防毒</span><span class="sxs-lookup"><span data-stu-id="6cfd5-178">Antivirus</span></span></li>
<li><span data-ttu-id="6cfd5-179">間諜</span><span class="sxs-lookup"><span data-stu-id="6cfd5-179">Antispyware</span></span></li>
<li><span data-ttu-id="6cfd5-180">軟體</span><span class="sxs-lookup"><span data-stu-id="6cfd5-180">Antimalware</span></span></li>
</ul><span data-ttu-id="6cfd5-181">
</dt>
<dt>掃描參數： &lt; 掃描參數 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-182">完整掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-182">Full scan</span></span></li>
<li><span data-ttu-id="6cfd5-183">快速掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-183">Quick scan</span></span></li>
<li><span data-ttu-id="6cfd5-184">客戶掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-184">Customer scan</span></span></li>
</ul><span data-ttu-id="6cfd5-185">
</dt>
<dt>使用者： &lt; 網域 &gt; \& lt;使用者&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-186">事件 ID: 1004</span><span class="sxs-lookup"><span data-stu-id="6cfd5-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-187">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-189">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-189">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-190">
<b>已繼續反惡意程式碼掃描。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-191">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="6cfd5-192">
<dt>掃描 ID: &lt;相關掃描的識別碼 &gt; 號碼。</dt> 
<dt>掃描類型： &lt; 掃描類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-193">防毒</span><span class="sxs-lookup"><span data-stu-id="6cfd5-193">Antivirus</span></span></li>
<li><span data-ttu-id="6cfd5-194">間諜</span><span class="sxs-lookup"><span data-stu-id="6cfd5-194">Antispyware</span></span></li>
<li><span data-ttu-id="6cfd5-195">軟體</span><span class="sxs-lookup"><span data-stu-id="6cfd5-195">Antimalware</span></span></li>
</ul><span data-ttu-id="6cfd5-196">
</dt>
<dt>掃描參數： &lt; 掃描參數 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-197">完整掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-197">Full scan</span></span></li>
<li><span data-ttu-id="6cfd5-198">快速掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-198">Quick scan</span></span></li>
<li><span data-ttu-id="6cfd5-199">客戶掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-199">Customer scan</span></span></li>
</ul><span data-ttu-id="6cfd5-200">
</dt>
<dt>使用者： &lt; 網域 &gt; \& lt;使用者&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-201">事件 ID: 1005</span><span class="sxs-lookup"><span data-stu-id="6cfd5-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-202">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-204">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-204">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-205">
<b>反惡意軟體掃描失敗。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-206">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="6cfd5-207">
<dt>掃描 ID: &lt;相關掃描的識別碼 &gt; 號碼。</dt> 
<dt>掃描類型： &lt; 掃描類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-208">防毒</span><span class="sxs-lookup"><span data-stu-id="6cfd5-208">Antivirus</span></span></li>
<li><span data-ttu-id="6cfd5-209">間諜</span><span class="sxs-lookup"><span data-stu-id="6cfd5-209">Antispyware</span></span></li>
<li><span data-ttu-id="6cfd5-210">軟體</span><span class="sxs-lookup"><span data-stu-id="6cfd5-210">Antimalware</span></span></li>
</ul><span data-ttu-id="6cfd5-211">
</dt>
<dt>掃描參數： &lt; 掃描參數 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-212">完整掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-212">Full scan</span></span></li>
<li><span data-ttu-id="6cfd5-213">快速掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-213">Quick scan</span></span></li>
<li><span data-ttu-id="6cfd5-214">客戶掃描</span><span class="sxs-lookup"><span data-stu-id="6cfd5-214">Customer scan</span></span></li>
</ul><span data-ttu-id="6cfd5-215">
</dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-216">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-217">防病毒用戶端發生錯誤，目前的掃描已停止。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="6cfd5-218">掃描可能會因為用戶端問題而失敗。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="6cfd5-219">此事件記錄包含掃描識別碼、掃描類型 (Microsoft Defender 防毒軟體、反間諜軟體、反惡意程式碼) 、掃描參數、啟動掃描的使用者、錯誤碼，以及錯誤的描述。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="6cfd5-220">若要疑難排解此事件：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="6cfd5-221">再次執行掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="6cfd5-222">若失敗，請移至 [ <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支援網站</a>]，然後在 <b>搜尋</b> 方塊中輸入錯誤號碼，以尋找錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="6cfd5-223">連絡 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技術支援</a>。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-224">事件 ID: 1006</span><span class="sxs-lookup"><span data-stu-id="6cfd5-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-225">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-227">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-227">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-228">
<b>反惡意軟體引擎找到惡意程式碼或其他可能不需要的軟體。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-229">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-230">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="6cfd5-231">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-232">低</span><span class="sxs-lookup"><span data-stu-id="6cfd5-232">Low</span></span></li>
<li><span data-ttu-id="6cfd5-233">中等</span><span class="sxs-lookup"><span data-stu-id="6cfd5-233">Moderate</span></span></li>
<li><span data-ttu-id="6cfd5-234">高</span><span class="sxs-lookup"><span data-stu-id="6cfd5-234">High</span></span></li>
<li><span data-ttu-id="6cfd5-235">嚴重</span><span class="sxs-lookup"><span data-stu-id="6cfd5-235">Severe</span></span></li>
</ul><span data-ttu-id="6cfd5-236">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt> 
<dt> 偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-237">Unknown</span><span class="sxs-lookup"><span data-stu-id="6cfd5-237">Unknown</span></span></li>
<li><span data-ttu-id="6cfd5-238">本機電腦</span><span class="sxs-lookup"><span data-stu-id="6cfd5-238">Local computer</span></span></li>
<li><span data-ttu-id="6cfd5-239">網路共用</span><span class="sxs-lookup"><span data-stu-id="6cfd5-239">Network share</span></span></li>
<li><span data-ttu-id="6cfd5-240">網際網路</span><span class="sxs-lookup"><span data-stu-id="6cfd5-240">Internet</span></span></li>
<li><span data-ttu-id="6cfd5-241">傳入流量</span><span class="sxs-lookup"><span data-stu-id="6cfd5-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="6cfd5-242">外寄流量</span><span class="sxs-lookup"><span data-stu-id="6cfd5-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="6cfd5-243">
</dt>
<dt>偵測類型： &lt; 偵測類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-244">啟發式</span><span class="sxs-lookup"><span data-stu-id="6cfd5-244">Heuristics</span></span></li>
<li><span data-ttu-id="6cfd5-245">Generic</span><span class="sxs-lookup"><span data-stu-id="6cfd5-245">Generic</span></span></li>
<li><span data-ttu-id="6cfd5-246">混凝土</span><span class="sxs-lookup"><span data-stu-id="6cfd5-246">Concrete</span></span></li>
<li><span data-ttu-id="6cfd5-247">動態簽名</span><span class="sxs-lookup"><span data-stu-id="6cfd5-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="6cfd5-248">
</dt>
<dt>偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-249">使用者：使用者已啟動</span><span class="sxs-lookup"><span data-stu-id="6cfd5-249">User: user initiated</span></span></li>
<li><span data-ttu-id="6cfd5-250">系統：系統啟動</span><span class="sxs-lookup"><span data-stu-id="6cfd5-250">System: system initiated</span></span></li>
<li><span data-ttu-id="6cfd5-251">即時：啟動即時元件</span><span class="sxs-lookup"><span data-stu-id="6cfd5-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="6cfd5-252">IOAV： IE 下載和 Outlook Express 附件已初始化</span><span class="sxs-lookup"><span data-stu-id="6cfd5-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="6cfd5-253">NIS：網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="6cfd5-254">IEPROTECT： IE-IExtensionValidation;這可防止惡意的網頁控制項</span><span class="sxs-lookup"><span data-stu-id="6cfd5-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="6cfd5-255">ELAM) 上的初期啟動反惡意軟體 (。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="6cfd5-256">這包括由啟動順序偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="6cfd5-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="6cfd5-257">遠端證明</span><span class="sxs-lookup"><span data-stu-id="6cfd5-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="6cfd5-258">反惡意軟體掃描介面 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="6cfd5-259">主要是用來保護 (PS、VBS) 的腳本，不過也可由協力廠商呼叫。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="6cfd5-260">UAC </dt> 
<dt>狀態： &lt; 狀態 &gt; </dt>
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>進程名稱： &lt; PID &gt; 簽章版本中的處理</dt>程式版本
<dt>： &lt; 定義版本 &gt; </dt>
<dt>引擎版本： &lt; Antimalware Engine 版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-261">事件 ID: 1007</span><span class="sxs-lookup"><span data-stu-id="6cfd5-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-262">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-264">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-264">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-265">
<b>反惡意軟體平臺會執行動作，以保護您的系統免受惡意軟體或其他可能不需要的軟體的攻擊。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-266">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-267">Microsoft Defender 防毒軟體已採取動作來保護此機器免受惡意程式碼或其他可能不需要的軟體的攻擊。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="6cfd5-268">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="6cfd5-269">
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
<dt>名稱： &lt; 威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-270">低</span><span class="sxs-lookup"><span data-stu-id="6cfd5-270">Low</span></span></li>
<li><span data-ttu-id="6cfd5-271">中等</span><span class="sxs-lookup"><span data-stu-id="6cfd5-271">Moderate</span></span></li>
<li><span data-ttu-id="6cfd5-272">高</span><span class="sxs-lookup"><span data-stu-id="6cfd5-272">High</span></span></li>
<li><span data-ttu-id="6cfd5-273">嚴重</span><span class="sxs-lookup"><span data-stu-id="6cfd5-273">Severe</span></span></li>
</ul><span data-ttu-id="6cfd5-274">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt> 
<dt>動作： &lt; 動作 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-275">清理：已清除資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="6cfd5-276">隔離：已隔離資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="6cfd5-277">移除：已刪除資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="6cfd5-278">允許：允許執行/存在資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="6cfd5-279">使用者定義：使用者定義的動作，通常是從使用者已指定之動作清單中的一個專案。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="6cfd5-280">無動作：無動作</span><span class="sxs-lookup"><span data-stu-id="6cfd5-280">No action: No action</span></span></li>
<li><span data-ttu-id="6cfd5-281">封鎖：資源遭到封鎖，無法執行</span><span class="sxs-lookup"><span data-stu-id="6cfd5-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="6cfd5-282">
</dt>
<dt>狀態： &lt;狀態 &gt; </dt>
<dt>簽名版本： &lt; 定義版本 &gt; </dt>
<dt>引擎版本： &lt; Antimalware Engine 版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-283">事件 ID: 1008</span><span class="sxs-lookup"><span data-stu-id="6cfd5-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-284">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-286">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-286">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-287">
<b>反惡意程式碼平臺嘗試執行動作，以保護您的系統免受惡意軟體或其他可能不需要的軟體的攻擊，但動作失敗。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-288">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-289">Microsoft Defender 防毒軟體對惡意程式碼或其他可能不需要的軟體採取動作時，發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="6cfd5-290">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="6cfd5-291">
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
<dt>名稱： &lt; 威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-292">低</span><span class="sxs-lookup"><span data-stu-id="6cfd5-292">Low</span></span></li>
<li><span data-ttu-id="6cfd5-293">中等</span><span class="sxs-lookup"><span data-stu-id="6cfd5-293">Moderate</span></span></li>
<li><span data-ttu-id="6cfd5-294">高</span><span class="sxs-lookup"><span data-stu-id="6cfd5-294">High</span></span></li>
<li><span data-ttu-id="6cfd5-295">嚴重</span><span class="sxs-lookup"><span data-stu-id="6cfd5-295">Severe</span></span></li>
</ul><span data-ttu-id="6cfd5-296">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt> 
<dt> 動作： &lt; 動作 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-297">清理：已清除資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="6cfd5-298">隔離：已隔離資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="6cfd5-299">移除：已刪除資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="6cfd5-300">允許：允許執行/存在資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="6cfd5-301">使用者定義：使用者定義的動作，通常是從使用者已指定之動作清單中的一個專案。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="6cfd5-302">無動作：無動作</span><span class="sxs-lookup"><span data-stu-id="6cfd5-302">No action: No action</span></span></li>
<li><span data-ttu-id="6cfd5-303">封鎖：資源遭到封鎖，無法執行</span><span class="sxs-lookup"><span data-stu-id="6cfd5-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="6cfd5-304">
</dt>
<dt>錯誤碼： &lt;&gt;與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述：錯誤 &lt; 描述 &gt; 錯誤的描述。</dt>
<dt>狀態： &lt;狀態 &gt; </dt>
<dt>簽名版本： &lt; 定義版本 &gt; </dt>
<dt>引擎版本： &lt; Antimalware Engine 版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-304">
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
<th colspan="2"><span data-ttu-id="6cfd5-305">事件 ID: 1009</span><span class="sxs-lookup"><span data-stu-id="6cfd5-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-306">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-308">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-308">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-309">
<b>反惡意軟體平臺已從隔離區還原專案。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-310">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-311">Microsoft Defender 防毒軟體已從隔離區還原專案。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="6cfd5-312">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="6cfd5-313">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-314">低</span><span class="sxs-lookup"><span data-stu-id="6cfd5-314">Low</span></span></li>
<li><span data-ttu-id="6cfd5-315">中等</span><span class="sxs-lookup"><span data-stu-id="6cfd5-315">Moderate</span></span></li>
<li><span data-ttu-id="6cfd5-316">高</span><span class="sxs-lookup"><span data-stu-id="6cfd5-316">High</span></span></li>
<li><span data-ttu-id="6cfd5-317">嚴重</span><span class="sxs-lookup"><span data-stu-id="6cfd5-317">Severe</span></span></li>
</ul><span data-ttu-id="6cfd5-318">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt>
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>簽名版本： &lt; 定義版本 &gt; </dt>
<dt>引擎版本： &lt; Antimalware Engine 版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-318">
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
<th colspan="2"><span data-ttu-id="6cfd5-319">事件 ID: 1010</span><span class="sxs-lookup"><span data-stu-id="6cfd5-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-320">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-322">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-322">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-323">
<b>反惡意軟體平臺無法從隔離區還原專案。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-324">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-325">Microsoft Defender 防毒軟體嘗試從隔離區還原專案時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="6cfd5-326">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="6cfd5-327">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-328">低</span><span class="sxs-lookup"><span data-stu-id="6cfd5-328">Low</span></span></li>
<li><span data-ttu-id="6cfd5-329">中等</span><span class="sxs-lookup"><span data-stu-id="6cfd5-329">Moderate</span></span></li>
<li><span data-ttu-id="6cfd5-330">高</span><span class="sxs-lookup"><span data-stu-id="6cfd5-330">High</span></span></li>
<li><span data-ttu-id="6cfd5-331">嚴重</span><span class="sxs-lookup"><span data-stu-id="6cfd5-331">Severe</span></span></li>
</ul><span data-ttu-id="6cfd5-332">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt>
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述：錯誤 &lt; 描述 &gt; 錯誤的描述。</dt>簽章
<dt>版本： &lt;定義版本 &gt; </dt>
<dt>引擎版本： &lt; Antimalware Engine 版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-332">
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
<th colspan="2"><span data-ttu-id="6cfd5-333">事件 ID: 1011</span><span class="sxs-lookup"><span data-stu-id="6cfd5-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-334">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-336">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-336">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-337">
<b>反惡意軟體平臺已從隔離區中刪除專案。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-338">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-339">Microsoft Defender 防毒軟體已從隔離區中刪除專案。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="6cfd5-340">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="6cfd5-341">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-342">低</span><span class="sxs-lookup"><span data-stu-id="6cfd5-342">Low</span></span></li>
<li><span data-ttu-id="6cfd5-343">中等</span><span class="sxs-lookup"><span data-stu-id="6cfd5-343">Moderate</span></span></li>
<li><span data-ttu-id="6cfd5-344">高</span><span class="sxs-lookup"><span data-stu-id="6cfd5-344">High</span></span></li>
<li><span data-ttu-id="6cfd5-345">嚴重</span><span class="sxs-lookup"><span data-stu-id="6cfd5-345">Severe</span></span></li>
</ul><span data-ttu-id="6cfd5-346">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt>
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>簽名版本： &lt; 定義版本 &gt; </dt>
<dt>引擎版本： &lt; Antimalware Engine 版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-346">
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
<th colspan="2"><span data-ttu-id="6cfd5-347">事件 ID: 1012</span><span class="sxs-lookup"><span data-stu-id="6cfd5-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-348">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-350">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-350">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-351">
<b>反惡意軟體平臺無法從隔離區刪除專案。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-352">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-353">Microsoft Defender 防毒軟體嘗試從隔離區中刪除專案時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="6cfd5-354">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="6cfd5-355">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-356">低</span><span class="sxs-lookup"><span data-stu-id="6cfd5-356">Low</span></span></li>
<li><span data-ttu-id="6cfd5-357">中等</span><span class="sxs-lookup"><span data-stu-id="6cfd5-357">Moderate</span></span></li>
<li><span data-ttu-id="6cfd5-358">高</span><span class="sxs-lookup"><span data-stu-id="6cfd5-358">High</span></span></li>
<li><span data-ttu-id="6cfd5-359">嚴重</span><span class="sxs-lookup"><span data-stu-id="6cfd5-359">Severe</span></span></li>
</ul><span data-ttu-id="6cfd5-360">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt>
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述：錯誤 &lt; 描述 &gt; 錯誤的描述。</dt>簽章
<dt>版本： &lt;定義版本 &gt; </dt>
<dt>引擎版本： &lt; Antimalware Engine 版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-360">
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
<th colspan="2"><span data-ttu-id="6cfd5-361">事件 ID: 1013</span><span class="sxs-lookup"><span data-stu-id="6cfd5-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-362">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-364">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-364">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-365">
<b>惡意程式碼平臺已刪除惡意程式碼和其他可能不需要的軟體的歷程記錄。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-366">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-367">Microsoft Defender 防毒軟體已移除惡意程式碼和其他可能不需要的軟體的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="6cfd5-368">
<dt>時間：事件發生的時間，例如清除的史。此參數不會用於威脅事件，所以不會混淆是否為修正時間或感染時間。在這些情況下，我們特別是以動作時間或偵測時間的方式呼叫它們。</dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-369">事件 ID: 1014</span><span class="sxs-lookup"><span data-stu-id="6cfd5-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-370">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-372">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-373">反惡意軟體平臺無法刪除惡意程式碼和其他可能不需要的軟體的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-374">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-375">Microsoft Defender 防毒軟體嘗試移除惡意程式碼與其他可能不需要的軟體的記錄時會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="6cfd5-376">
<dt>時間：事件發生的時間，例如清除的史。此參數不會用於威脅事件，所以不會混淆是否為修正時間或感染時間。在這些情況下，我們特別是以動作時間或偵測時間的方式呼叫它們。</dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述：錯誤 &lt; 描述 &gt; 錯誤的描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-377">事件 ID: 1015</span><span class="sxs-lookup"><span data-stu-id="6cfd5-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-378">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-380">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-380">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-381">
<b>反惡意軟體平臺偵測到可疑行為。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-382">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-383">Microsoft Defender 防毒軟體偵測到可疑行為。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="6cfd5-384">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="6cfd5-385">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-386">低</span><span class="sxs-lookup"><span data-stu-id="6cfd5-386">Low</span></span></li>
<li><span data-ttu-id="6cfd5-387">中等</span><span class="sxs-lookup"><span data-stu-id="6cfd5-387">Moderate</span></span></li>
<li><span data-ttu-id="6cfd5-388">高</span><span class="sxs-lookup"><span data-stu-id="6cfd5-388">High</span></span></li>
<li><span data-ttu-id="6cfd5-389">嚴重</span><span class="sxs-lookup"><span data-stu-id="6cfd5-389">Severe</span></span></li>
</ul><span data-ttu-id="6cfd5-390">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt> 
<dt> 偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6cfd5-391">Unknown</span><span class="sxs-lookup"><span data-stu-id="6cfd5-391">Unknown</span></span></li>
<li><span data-ttu-id="6cfd5-392">本機電腦</span><span class="sxs-lookup"><span data-stu-id="6cfd5-392">Local computer</span></span></li>
<li><span data-ttu-id="6cfd5-393">網路共用</span><span class="sxs-lookup"><span data-stu-id="6cfd5-393">Network share</span></span></li>
<li><span data-ttu-id="6cfd5-394">網際網路</span><span class="sxs-lookup"><span data-stu-id="6cfd5-394">Internet</span></span></li>
<li><span data-ttu-id="6cfd5-395">傳入流量</span><span class="sxs-lookup"><span data-stu-id="6cfd5-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="6cfd5-396">外寄流量</span><span class="sxs-lookup"><span data-stu-id="6cfd5-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="6cfd5-397">
</dt>
<dt>偵測類型： &lt; 偵測類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-398">啟發式</span><span class="sxs-lookup"><span data-stu-id="6cfd5-398">Heuristics</span></span></li>
<li><span data-ttu-id="6cfd5-399">Generic</span><span class="sxs-lookup"><span data-stu-id="6cfd5-399">Generic</span></span></li>
<li><span data-ttu-id="6cfd5-400">混凝土</span><span class="sxs-lookup"><span data-stu-id="6cfd5-400">Concrete</span></span></li>
<li><span data-ttu-id="6cfd5-401">動態簽名</span><span class="sxs-lookup"><span data-stu-id="6cfd5-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="6cfd5-402">
</dt>
<dt>偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-403">使用者：使用者已啟動</span><span class="sxs-lookup"><span data-stu-id="6cfd5-403">User: user initiated</span></span></li>
<li><span data-ttu-id="6cfd5-404">系統：系統啟動</span><span class="sxs-lookup"><span data-stu-id="6cfd5-404">System: system initiated</span></span></li>
<li><span data-ttu-id="6cfd5-405">即時：啟動即時元件</span><span class="sxs-lookup"><span data-stu-id="6cfd5-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="6cfd5-406">IOAV： IE 下載和 Outlook Express 附件已初始化</span><span class="sxs-lookup"><span data-stu-id="6cfd5-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="6cfd5-407">NIS：網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="6cfd5-408">IEPROTECT： IE-IExtensionValidation;這可防止惡意的網頁控制項</span><span class="sxs-lookup"><span data-stu-id="6cfd5-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="6cfd5-409">ELAM) 上的初期啟動反惡意軟體 (。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="6cfd5-410">這包括由啟動順序偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="6cfd5-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="6cfd5-411">遠端證明</span><span class="sxs-lookup"><span data-stu-id="6cfd5-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="6cfd5-412">反惡意軟體掃描介面 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="6cfd5-413">主要是用來保護 (PS、VBS) 的腳本，不過也可由協力廠商呼叫。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="6cfd5-414">UAC </dt> 
<dt>狀態： &lt; 狀態 &gt; </dt>
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>進程名稱： &lt; PID &gt; 簽章中的處理</dt>程式
<dt>ID: 列舉比對嚴重性。</dt>簽章
<dt>版本： &lt;定義版本 &gt; </dt>
<dt>引擎版本： &lt; Antimalware Engine 版本 &gt; </dt>
<dt>保真標籤：</dt>
<dt>目的檔案名：檔案名 &lt; 的檔案名 &gt; 。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-414">UAC</dt>
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
<th colspan="2"><span data-ttu-id="6cfd5-415">事件 ID: 1116</span><span class="sxs-lookup"><span data-stu-id="6cfd5-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-416">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-418">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-418">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-419">
<b>反惡意軟體平臺偵測到惡意程式碼或其他可能不需要的軟體。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-420">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-421">Microsoft Defender 防毒軟體偵測到惡意程式碼或其他可能不需要的軟體。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="6cfd5-422">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="6cfd5-423">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-424">低</span><span class="sxs-lookup"><span data-stu-id="6cfd5-424">Low</span></span></li>
<li><span data-ttu-id="6cfd5-425">中等</span><span class="sxs-lookup"><span data-stu-id="6cfd5-425">Moderate</span></span></li>
<li><span data-ttu-id="6cfd5-426">高</span><span class="sxs-lookup"><span data-stu-id="6cfd5-426">High</span></span></li>
<li><span data-ttu-id="6cfd5-427">嚴重</span><span class="sxs-lookup"><span data-stu-id="6cfd5-427">Severe</span></span></li>
</ul><span data-ttu-id="6cfd5-428">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt> 
<dt> 偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6cfd5-429">Unknown</span><span class="sxs-lookup"><span data-stu-id="6cfd5-429">Unknown</span></span></li>
<li><span data-ttu-id="6cfd5-430">本機電腦</span><span class="sxs-lookup"><span data-stu-id="6cfd5-430">Local computer</span></span></li>
<li><span data-ttu-id="6cfd5-431">網路共用</span><span class="sxs-lookup"><span data-stu-id="6cfd5-431">Network share</span></span></li>
<li><span data-ttu-id="6cfd5-432">網際網路</span><span class="sxs-lookup"><span data-stu-id="6cfd5-432">Internet</span></span></li>
<li><span data-ttu-id="6cfd5-433">傳入流量</span><span class="sxs-lookup"><span data-stu-id="6cfd5-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="6cfd5-434">外寄流量</span><span class="sxs-lookup"><span data-stu-id="6cfd5-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="6cfd5-435">
</dt>
<dt>偵測類型： &lt; 偵測類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-436">啟發式</span><span class="sxs-lookup"><span data-stu-id="6cfd5-436">Heuristics</span></span></li>
<li><span data-ttu-id="6cfd5-437">Generic</span><span class="sxs-lookup"><span data-stu-id="6cfd5-437">Generic</span></span></li>
<li><span data-ttu-id="6cfd5-438">混凝土</span><span class="sxs-lookup"><span data-stu-id="6cfd5-438">Concrete</span></span></li>
<li><span data-ttu-id="6cfd5-439">動態簽名</span><span class="sxs-lookup"><span data-stu-id="6cfd5-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="6cfd5-440">
</dt>
<dt>偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-441">使用者：使用者已啟動</span><span class="sxs-lookup"><span data-stu-id="6cfd5-441">User: user initiated</span></span></li>
<li><span data-ttu-id="6cfd5-442">系統：系統啟動</span><span class="sxs-lookup"><span data-stu-id="6cfd5-442">System: system initiated</span></span></li>
<li><span data-ttu-id="6cfd5-443">即時：啟動即時元件</span><span class="sxs-lookup"><span data-stu-id="6cfd5-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="6cfd5-444">IOAV： IE 下載和 Outlook Express 附件已初始化</span><span class="sxs-lookup"><span data-stu-id="6cfd5-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="6cfd5-445">NIS：網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="6cfd5-446">IEPROTECT： IE-IExtensionValidation;這可防止惡意的網頁控制項</span><span class="sxs-lookup"><span data-stu-id="6cfd5-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="6cfd5-447">ELAM) 上的初期啟動反惡意軟體 (。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="6cfd5-448">這包括由啟動順序偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="6cfd5-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="6cfd5-449">遠端證明</span><span class="sxs-lookup"><span data-stu-id="6cfd5-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="6cfd5-450">反惡意軟體掃描介面 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="6cfd5-451">主要是用來保護 (PS、VBS) 的腳本，不過也可由協力廠商呼叫。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="6cfd5-452">UAC </dt> 
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>進程名稱： &lt; PID &gt; 簽章版本中的處理</dt>程式版本
<dt>： &lt; 定義版本 &gt; </dt>
<dt>引擎版本： &lt; Antimalware Engine 版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-453">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-454">不用執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-454">No action is required.</span></span> <span data-ttu-id="6cfd5-455">Microsoft Defender 防毒軟體可以暫掛並對此威脅採取例行動作。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="6cfd5-456">如果您想要手動移除威脅，請在 Microsoft Defender 防毒軟體介面中，按一下 [<b>清理電腦</b>]。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-457">事件 ID: 1117</span><span class="sxs-lookup"><span data-stu-id="6cfd5-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-458">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-460">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-460">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-461">
<b>反惡意軟體平臺會執行動作，以保護您的系統免受惡意軟體或其他可能不需要的軟體的攻擊。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-462">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-463">Microsoft Defender 防毒軟體已採取動作來保護此機器免受惡意程式碼或其他可能不需要的軟體的攻擊。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="6cfd5-464">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="6cfd5-465">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-466">低</span><span class="sxs-lookup"><span data-stu-id="6cfd5-466">Low</span></span></li>
<li><span data-ttu-id="6cfd5-467">中等</span><span class="sxs-lookup"><span data-stu-id="6cfd5-467">Moderate</span></span></li>
<li><span data-ttu-id="6cfd5-468">高</span><span class="sxs-lookup"><span data-stu-id="6cfd5-468">High</span></span></li>
<li><span data-ttu-id="6cfd5-469">嚴重</span><span class="sxs-lookup"><span data-stu-id="6cfd5-469">Severe</span></span></li>
</ul><span data-ttu-id="6cfd5-470">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt> 
<dt> 偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6cfd5-471">Unknown</span><span class="sxs-lookup"><span data-stu-id="6cfd5-471">Unknown</span></span></li>
<li><span data-ttu-id="6cfd5-472">本機電腦</span><span class="sxs-lookup"><span data-stu-id="6cfd5-472">Local computer</span></span></li>
<li><span data-ttu-id="6cfd5-473">網路共用</span><span class="sxs-lookup"><span data-stu-id="6cfd5-473">Network share</span></span></li>
<li><span data-ttu-id="6cfd5-474">網際網路</span><span class="sxs-lookup"><span data-stu-id="6cfd5-474">Internet</span></span></li>
<li><span data-ttu-id="6cfd5-475">傳入流量</span><span class="sxs-lookup"><span data-stu-id="6cfd5-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="6cfd5-476">外寄流量</span><span class="sxs-lookup"><span data-stu-id="6cfd5-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="6cfd5-477">
</dt>
<dt>偵測類型： &lt; 偵測類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-478">啟發式</span><span class="sxs-lookup"><span data-stu-id="6cfd5-478">Heuristics</span></span></li>
<li><span data-ttu-id="6cfd5-479">Generic</span><span class="sxs-lookup"><span data-stu-id="6cfd5-479">Generic</span></span></li>
<li><span data-ttu-id="6cfd5-480">混凝土</span><span class="sxs-lookup"><span data-stu-id="6cfd5-480">Concrete</span></span></li>
<li><span data-ttu-id="6cfd5-481">動態簽名</span><span class="sxs-lookup"><span data-stu-id="6cfd5-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="6cfd5-482">
</dt>
<dt>偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-483">使用者：使用者已啟動</span><span class="sxs-lookup"><span data-stu-id="6cfd5-483">User: user initiated</span></span></li>
<li><span data-ttu-id="6cfd5-484">系統：系統啟動</span><span class="sxs-lookup"><span data-stu-id="6cfd5-484">System: system initiated</span></span></li>
<li><span data-ttu-id="6cfd5-485">即時：啟動即時元件</span><span class="sxs-lookup"><span data-stu-id="6cfd5-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="6cfd5-486">IOAV： IE 下載和 Outlook Express 附件已初始化</span><span class="sxs-lookup"><span data-stu-id="6cfd5-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="6cfd5-487">NIS：網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="6cfd5-488">IEPROTECT： IE-IExtensionValidation;這可防止惡意的網頁控制項</span><span class="sxs-lookup"><span data-stu-id="6cfd5-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="6cfd5-489">ELAM) 上的初期啟動反惡意軟體 (。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="6cfd5-490">這包括由啟動順序偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="6cfd5-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="6cfd5-491">遠端證明</span><span class="sxs-lookup"><span data-stu-id="6cfd5-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="6cfd5-492">反惡意軟體掃描介面 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="6cfd5-493">主要是用來保護 (PS、VBS) 的腳本，不過也可由協力廠商呼叫。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="6cfd5-494">UAC </dt> 
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>進程名稱： &lt; PID &gt; 動作中的處理</dt> 
<dt> &lt; 程式：動作 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-495">清理：已清除資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="6cfd5-496">隔離：已隔離資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="6cfd5-497">移除：已刪除資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="6cfd5-498">允許：允許執行/存在資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="6cfd5-499">使用者定義：使用者定義的動作，通常是從使用者已指定之動作清單中的一個專案。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="6cfd5-500">無動作：無動作</span><span class="sxs-lookup"><span data-stu-id="6cfd5-500">No action: No action</span></span></li>
<li><span data-ttu-id="6cfd5-501">封鎖：資源遭到封鎖，無法執行</span><span class="sxs-lookup"><span data-stu-id="6cfd5-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="6cfd5-502">
</dt>
<dt>動作狀態： &lt;其他動作 &gt; 的描述</dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤碼的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>簽章
<dt>版本： &lt;定義版本 &gt; </dt>
<dt>引擎版本： &lt; 反惡意引擎 &gt; 版本</dt>請注意：每當 microsoft Defender 防毒程式、microsoft Security Essentials、惡意軟體移除工具或 System Center Endpoint Protection 偵測到惡意程式碼時，會還原下列系統設定和服務，惡意程式碼可能已變更：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="6cfd5-503">預設 Internet Explorer 或 Microsoft Edge 設定</span><span class="sxs-lookup"><span data-stu-id="6cfd5-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="6cfd5-504">使用者存取控制設定</span><span class="sxs-lookup"><span data-stu-id="6cfd5-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="6cfd5-505">Chrome 設定</span><span class="sxs-lookup"><span data-stu-id="6cfd5-505">Chrome settings</span></span></li>
<li><span data-ttu-id="6cfd5-506">引導控制資料</span><span class="sxs-lookup"><span data-stu-id="6cfd5-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="6cfd5-507">Regedit 和工作管理員登錄設定</span><span class="sxs-lookup"><span data-stu-id="6cfd5-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="6cfd5-508">Windows 更新、背景智慧傳送服務和遠端過程呼叫服務</span><span class="sxs-lookup"><span data-stu-id="6cfd5-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="6cfd5-509">Windows 作業系統檔</span><span class="sxs-lookup"><span data-stu-id="6cfd5-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="6cfd5-510">上述內容適用于下列用戶端和伺服器版本：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="6cfd5-511">作業系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-511">Operating system</span></span></th>
<th><span data-ttu-id="6cfd5-512">作業系統版本</span><span class="sxs-lookup"><span data-stu-id="6cfd5-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-513">用戶端作業系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="6cfd5-514">Windows Vista (Service Pack 1 或 Service Pack 2) ，Windows 7 和更新版本</span><span class="sxs-lookup"><span data-stu-id="6cfd5-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-515">伺服器作業系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="6cfd5-516">Windows Server 2008、Windows Server 2008 R2、Windows Server 2012 及 Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="6cfd5-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-517">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-518">不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-518">No action is necessary.</span></span> <span data-ttu-id="6cfd5-519">Microsoft Defender 防病毒已移除或隔離威脅。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-520">事件 ID: 1118</span><span class="sxs-lookup"><span data-stu-id="6cfd5-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-521">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-523">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-523">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-524">
<b>反惡意程式碼平臺嘗試執行動作，以保護您的系統免受惡意軟體或其他可能不需要的軟體的攻擊，但動作失敗。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-525">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-526">當對惡意程式碼或其他可能不需要的軟體採取動作時，Microsoft Defender 防毒軟體會遇到非嚴重的錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="6cfd5-527">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="6cfd5-528">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-529">低</span><span class="sxs-lookup"><span data-stu-id="6cfd5-529">Low</span></span></li>
<li><span data-ttu-id="6cfd5-530">中等</span><span class="sxs-lookup"><span data-stu-id="6cfd5-530">Moderate</span></span></li>
<li><span data-ttu-id="6cfd5-531">高</span><span class="sxs-lookup"><span data-stu-id="6cfd5-531">High</span></span></li>
<li><span data-ttu-id="6cfd5-532">嚴重</span><span class="sxs-lookup"><span data-stu-id="6cfd5-532">Severe</span></span></li>
</ul><span data-ttu-id="6cfd5-533">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt> 
<dt> 偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6cfd5-534">Unknown</span><span class="sxs-lookup"><span data-stu-id="6cfd5-534">Unknown</span></span></li>
<li><span data-ttu-id="6cfd5-535">本機電腦</span><span class="sxs-lookup"><span data-stu-id="6cfd5-535">Local computer</span></span></li>
<li><span data-ttu-id="6cfd5-536">網路共用</span><span class="sxs-lookup"><span data-stu-id="6cfd5-536">Network share</span></span></li>
<li><span data-ttu-id="6cfd5-537">網際網路</span><span class="sxs-lookup"><span data-stu-id="6cfd5-537">Internet</span></span></li>
<li><span data-ttu-id="6cfd5-538">傳入流量</span><span class="sxs-lookup"><span data-stu-id="6cfd5-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="6cfd5-539">外寄流量</span><span class="sxs-lookup"><span data-stu-id="6cfd5-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="6cfd5-540">
</dt>
<dt>偵測類型： &lt; 偵測類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-541">啟發式</span><span class="sxs-lookup"><span data-stu-id="6cfd5-541">Heuristics</span></span></li>
<li><span data-ttu-id="6cfd5-542">Generic</span><span class="sxs-lookup"><span data-stu-id="6cfd5-542">Generic</span></span></li>
<li><span data-ttu-id="6cfd5-543">混凝土</span><span class="sxs-lookup"><span data-stu-id="6cfd5-543">Concrete</span></span></li>
<li><span data-ttu-id="6cfd5-544">動態簽名</span><span class="sxs-lookup"><span data-stu-id="6cfd5-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="6cfd5-545">
</dt>
<dt>偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-546">使用者：使用者已啟動</span><span class="sxs-lookup"><span data-stu-id="6cfd5-546">User: user initiated</span></span></li>
<li><span data-ttu-id="6cfd5-547">系統：系統啟動</span><span class="sxs-lookup"><span data-stu-id="6cfd5-547">System: system initiated</span></span></li>
<li><span data-ttu-id="6cfd5-548">即時：啟動即時元件</span><span class="sxs-lookup"><span data-stu-id="6cfd5-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="6cfd5-549">IOAV：已啟動 IE 下載和 Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="6cfd5-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="6cfd5-550">NIS：網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="6cfd5-551">IEPROTECT： IE-IExtensionValidation;這可防止惡意的網頁控制項</span><span class="sxs-lookup"><span data-stu-id="6cfd5-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="6cfd5-552">ELAM) 上的初期啟動反惡意軟體 (。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="6cfd5-553">這包括由啟動順序偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="6cfd5-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="6cfd5-554">遠端證明</span><span class="sxs-lookup"><span data-stu-id="6cfd5-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="6cfd5-555">反惡意軟體掃描介面 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="6cfd5-556">主要是用來保護 (PS、VBS) 的腳本，不過也可由協力廠商呼叫。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="6cfd5-557">UAC </dt> 
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>進程名稱： &lt; PID &gt; 動作中的處理</dt> 
<dt> &lt; 程式：動作 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-558">清理：已清除資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="6cfd5-559">隔離：已隔離資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="6cfd5-560">移除：已刪除資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="6cfd5-561">允許：允許執行/存在資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="6cfd5-562">使用者定義：使用者定義的動作，通常是從使用者已指定之動作清單中的一個專案。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="6cfd5-563">無動作：無動作</span><span class="sxs-lookup"><span data-stu-id="6cfd5-563">No action: No action</span></span></li>
<li><span data-ttu-id="6cfd5-564">封鎖：資源遭到封鎖，無法執行</span><span class="sxs-lookup"><span data-stu-id="6cfd5-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="6cfd5-565">
</dt>
<dt>動作狀態： &lt;其他動作 &gt; 的描述</dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤碼的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>簽章
<dt>版本： &lt;定義版本 &gt; </dt>
<dt>引擎版本： &lt; 反惡意引擎 &gt; 版本</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-565">
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
<span data-ttu-id="6cfd5-566">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-567">不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-567">No action is necessary.</span></span> <span data-ttu-id="6cfd5-568">Microsoft Defender 防毒程式無法完成與惡意程式碼修復相關的工作。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="6cfd5-569">這不是嚴重失敗。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-570">事件 ID: 1119</span><span class="sxs-lookup"><span data-stu-id="6cfd5-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-571">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-573">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-573">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-574">
<b>反惡意程式碼平臺嘗試對惡意程式碼或其他可能不需要的軟體採取動作時，發生嚴重錯誤。事件訊息中有更多的詳細資料。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-575">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-576">Microsoft Defender 防毒程式在對惡意程式碼或其他可能不需要的軟體採取動作時，發生嚴重錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="6cfd5-577">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="6cfd5-578">
<dt>名稱： &lt;威脅名稱 &gt; </dt> 
<dt>ID: &lt; 威脅識別碼 &gt; </dt> 
<dt> 嚴重性： &lt; 嚴重性 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-579">低</span><span class="sxs-lookup"><span data-stu-id="6cfd5-579">Low</span></span></li>
<li><span data-ttu-id="6cfd5-580">中等</span><span class="sxs-lookup"><span data-stu-id="6cfd5-580">Moderate</span></span></li>
<li><span data-ttu-id="6cfd5-581">高</span><span class="sxs-lookup"><span data-stu-id="6cfd5-581">High</span></span></li>
<li><span data-ttu-id="6cfd5-582">嚴重</span><span class="sxs-lookup"><span data-stu-id="6cfd5-582">Severe</span></span></li>
</ul><span data-ttu-id="6cfd5-583">
</dt>
<dt>類別： &lt;類別描述 &gt; ，例如任何威脅或惡意程式碼類型。</dt>
<dt>路徑： &lt;檔路徑 &gt; </dt> 
<dt> 偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6cfd5-584">Unknown</span><span class="sxs-lookup"><span data-stu-id="6cfd5-584">Unknown</span></span></li>
<li><span data-ttu-id="6cfd5-585">本機電腦</span><span class="sxs-lookup"><span data-stu-id="6cfd5-585">Local computer</span></span></li>
<li><span data-ttu-id="6cfd5-586">網路共用</span><span class="sxs-lookup"><span data-stu-id="6cfd5-586">Network share</span></span></li>
<li><span data-ttu-id="6cfd5-587">網際網路</span><span class="sxs-lookup"><span data-stu-id="6cfd5-587">Internet</span></span></li>
<li><span data-ttu-id="6cfd5-588">傳入流量</span><span class="sxs-lookup"><span data-stu-id="6cfd5-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="6cfd5-589">外寄流量</span><span class="sxs-lookup"><span data-stu-id="6cfd5-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="6cfd5-590">
</dt>
<dt>偵測類型： &lt; 偵測類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-591">啟發式</span><span class="sxs-lookup"><span data-stu-id="6cfd5-591">Heuristics</span></span></li>
<li><span data-ttu-id="6cfd5-592">Generic</span><span class="sxs-lookup"><span data-stu-id="6cfd5-592">Generic</span></span></li>
<li><span data-ttu-id="6cfd5-593">混凝土</span><span class="sxs-lookup"><span data-stu-id="6cfd5-593">Concrete</span></span></li>
<li><span data-ttu-id="6cfd5-594">動態簽名</span><span class="sxs-lookup"><span data-stu-id="6cfd5-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="6cfd5-595">
</dt>
<dt>偵測來源： &lt; 偵測來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-596">使用者：使用者已啟動</span><span class="sxs-lookup"><span data-stu-id="6cfd5-596">User: user initiated</span></span></li>
<li><span data-ttu-id="6cfd5-597">系統：系統啟動</span><span class="sxs-lookup"><span data-stu-id="6cfd5-597">System: system initiated</span></span></li>
<li><span data-ttu-id="6cfd5-598">即時：啟動即時元件</span><span class="sxs-lookup"><span data-stu-id="6cfd5-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="6cfd5-599">IOAV：已啟動 IE 下載和 Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="6cfd5-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="6cfd5-600">NIS：網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="6cfd5-601">IEPROTECT： IE-IExtensionValidation;這可防止惡意的網頁控制項</span><span class="sxs-lookup"><span data-stu-id="6cfd5-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="6cfd5-602">ELAM) 上的初期啟動反惡意軟體 (。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="6cfd5-603">這包括由啟動順序偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="6cfd5-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="6cfd5-604">遠端證明</span><span class="sxs-lookup"><span data-stu-id="6cfd5-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="6cfd5-605">反惡意軟體掃描介面 (AMSI) 。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="6cfd5-606">主要是用來保護 (PS、VBS) 的腳本，不過也可由協力廠商呼叫。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="6cfd5-607">UAC </dt> 
<dt>使用者： &lt; 網域 &gt; \& lt;使用者 &gt; </dt>
<dt>進程名稱： &lt; PID &gt; 動作中的處理</dt> 
<dt> &lt; 程式：動作 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6cfd5-608">清理：已清除資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="6cfd5-609">隔離：已隔離資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="6cfd5-610">移除：已刪除資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="6cfd5-611">允許：允許執行/存在資源</span><span class="sxs-lookup"><span data-stu-id="6cfd5-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="6cfd5-612">使用者定義：使用者定義的動作，通常是從使用者已指定之動作清單中的一個專案。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="6cfd5-613">無動作：無動作</span><span class="sxs-lookup"><span data-stu-id="6cfd5-613">No action: No action</span></span></li>
<li><span data-ttu-id="6cfd5-614">封鎖：資源遭到封鎖，無法執行</span><span class="sxs-lookup"><span data-stu-id="6cfd5-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="6cfd5-615">
</dt>
<dt>動作狀態： &lt;其他動作 &gt; 的描述</dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤碼的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>簽章
<dt>版本： &lt;定義版本 &gt; </dt>
<dt>引擎版本： &lt; Antimalware Engine 版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-615">
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
<span data-ttu-id="6cfd5-616">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-617">Microsoft Defender 防毒軟體用戶端因嚴重問題而遇到此錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="6cfd5-618">端點可能不受保護。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-618">The endpoint might not be protected.</span></span> <span data-ttu-id="6cfd5-619">請複查錯誤描述，然後依照下列相關的 <b>使用者動作</b> 步驟進行。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="6cfd5-620">動作</span><span class="sxs-lookup"><span data-stu-id="6cfd5-620">Action</span></span></th>
<th><span data-ttu-id="6cfd5-621">使用者動作</span><span class="sxs-lookup"><span data-stu-id="6cfd5-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="6cfd5-622">
<b>刪除</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="6cfd5-623">更新定義，然後驗證是否已成功移除。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="6cfd5-624">
<b>清潔</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="6cfd5-625">更新定義，然後確認修復成功。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="6cfd5-626">
<b>檢疫</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="6cfd5-627">更新定義，並確認使用者具有存取必要資源的許可權。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="6cfd5-628">
<b>允許</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="6cfd5-629">確認使用者具有存取必要資源的許可權。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="6cfd5-630">如果此事件仍然存在：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="6cfd5-631">再次執行掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="6cfd5-632">若失敗，請移至 [ <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支援網站</a>]，然後在 <b>搜尋</b> 方塊中輸入錯誤號碼，以尋找錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="6cfd5-633">連絡 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技術支援</a>。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-634">事件 ID: 1120</span><span class="sxs-lookup"><span data-stu-id="6cfd5-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-635">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-637">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-637">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-638">
<b>Microsoft Defender 防毒軟體已推匯出威脅資源的雜湊。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-639">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-640">Microsoft Defender 防毒軟體用戶端已啟動並以健全的狀態運作。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="6cfd5-641">
<dt>目前平臺版本： &lt;目前平臺版本 &gt; </dt>
<dt>威脅資源路徑： &lt; 路徑 &gt; </dt>
<dt>雜湊 &lt; ： &gt; 雜湊</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="6cfd5-642"><b>注意：只有在設定下列原則時，才會記錄此事件： <b>ThreatFileHashLogging 未簽署</b>。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-643">事件 ID: 1150</span><span class="sxs-lookup"><span data-stu-id="6cfd5-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-644">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-646">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-646">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-647">
<b>如果您的反惡意程式碼平臺報告狀態為監控平臺，此事件表示反惡意軟體平臺正在執行中且狀態良好。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-648">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-649">Microsoft Defender 防毒軟體用戶端已啟動並以健全的狀態運作。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="6cfd5-650">
<dt>平臺版本： &lt;目前平臺版本 &gt; </dt>
<dt>簽名版本： &lt; 定義版本 &gt; </dt>
<dt>引擎版本： &lt; Antimalware Engine 版本 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-651">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-652">不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-652">No action is necessary.</span></span> <span data-ttu-id="6cfd5-653">Microsoft Defender 防毒軟體用戶端的狀態良好。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="6cfd5-654">此事件每小時報告一次。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="6cfd5-655">事件 ID: 1151</span><span class="sxs-lookup"><span data-stu-id="6cfd5-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-656">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-658">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-658">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-659">
<b>Endpoint Protection 用戶端狀況報告 (以 UTC 為單位的時間) </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-660">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-661">防病毒用戶端狀況報告。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="6cfd5-662">
<dt>平臺版本： &lt;目前的平臺 &gt; 版本</dt>
<dt>引擎版本： &lt; Antimalware Engine &gt; 版本</dt>
<dt>網路即時檢查引擎版本 &lt; &gt; ：「網路即時檢查引擎</dt>」版本：
<dt> &lt; 防毒軟體 &gt; </dt>簽章版本反間諜軟體簽章版本：
<dt> &lt; 反 &gt; 間諜</dt>軟體簽章版本
<dt>網路即時檢查簽章版本： &lt; 網路即時檢查 &gt; </dt>簽章版本 RTP 狀態： 
<dt> &lt; 在 Access (狀態上 &gt; 啟用或停用的</dt>[
<dt> &lt; 即時保護 &gt;)  (狀態</dt>]) 
<dt>IOAV 狀態： &lt; IE 下載和 Outlook Express 附件狀態 &gt; (啟用或停用) </dt> 
<dt>BM 狀態： &lt; 行為監視狀態 &gt; (啟用或停用) </dt>防毒軟體簽章： 
<dt> &lt; 防病毒 &gt; </dt> 
<dt> &lt; 軟體 &gt; </dt>簽章期限 (于
<dt>最近一次的快速掃描保留天數：上次的 &lt; 快速掃描 &gt; </dt>保留天數) 
<dt>上次完整掃描保留時間：上次完整掃描保留 &lt; &gt; 天數</dt> (
<dt>: ?&lt;防病毒簽名建立 &gt; 時間</dt>
<dt>反間諜軟體簽名建立時間：？ &lt;反間諜軟體簽名 &gt; 建立時間</dt>
<dt>上次快速掃描開始時間：？ &lt;上次快速掃描開始時間 &gt; </dt>
<dt>上次快速掃描結束時間：？ &lt;上次快速掃描結束時間 &gt; </dt>
<dt>上次快速掃描來源： &lt; 上次快速掃描來源 &gt; (0&#39;= 未執行、1 = 使用者啟動、2 = 系統起始) </dt>
<dt>上次完整掃描開始時間：？ &lt;上次完整掃描的開始 &gt; 時間</dt>
<dt>上次完整掃描結束時間：？ &lt;上次完整掃描結束時間 &gt; </dt>
<dt>上次完整掃描來源： &lt; 上次完整掃描來源 &gt; (0&#39;= 未執行、1 = 使用者啟動、2 = 系統起始) </dt> 
<dt> 產品狀態：用於內部疑難排解</span><span class="sxs-lookup"><span data-stu-id="6cfd5-662">
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

<tr><span data-ttu-id="6cfd5-663">
<th colspan="2">事件 ID: 2000</span><span class="sxs-lookup"><span data-stu-id="6cfd5-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-664">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-666">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-666">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-667">
<b>已成功更新反惡意程式碼定義。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-668">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-669">防病毒碼碼版本已更新。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="6cfd5-670">
<dt>目前的特徵碼版本： &lt;&gt;目前</dt>的簽章版本先前的簽章
<dt>版本： &lt; 上一個 &gt; </dt>簽章版本簽章 
<dt> 類型： &lt; 簽名類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="6cfd5-671">防毒</span><span class="sxs-lookup"><span data-stu-id="6cfd5-671">Antivirus</span></span></li>
<li><span data-ttu-id="6cfd5-672">間諜</span><span class="sxs-lookup"><span data-stu-id="6cfd5-672">Antispyware</span></span></li>
<li><span data-ttu-id="6cfd5-673">軟體</span><span class="sxs-lookup"><span data-stu-id="6cfd5-673">Antimalware</span></span></li>
<li><span data-ttu-id="6cfd5-674">網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="6cfd5-675">
</dt>
<dt>更新類型： &lt;更新類型 &gt; （完整或 Delta）。</dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
<dt>目前引擎版本： &lt; &gt; 目前引擎</dt>版本
<dt>先前 &lt; &gt; 引擎版本：舊</dt>引擎版本
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-675">
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
<span data-ttu-id="6cfd5-676">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-677">不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-677">No action is necessary.</span></span> <span data-ttu-id="6cfd5-678">Microsoft Defender 防毒軟體用戶端的狀態良好。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="6cfd5-679">成功更新特徵碼時會報告此事件。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-680">事件 ID: 2001</span><span class="sxs-lookup"><span data-stu-id="6cfd5-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-681">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-683">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-683">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-684">
<b>安全性智慧更新失敗。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-685">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-686">Microsoft Defender 防毒軟體嘗試更新簽名時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="6cfd5-687">
<dt>新的安全性情報版本： &lt;新的版本 &gt; 號碼</dt>
<dt>先前的安全性情報版本： &lt; 舊版本 &gt; </dt> 
<dt> 更新來源： &lt; 更新來源 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6cfd5-688">安全性智慧更新資料夾</span><span class="sxs-lookup"><span data-stu-id="6cfd5-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="6cfd5-689">內部安全性智慧補救伺服器</span><span class="sxs-lookup"><span data-stu-id="6cfd5-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="6cfd5-690">Microsoft 補救伺服器</span><span class="sxs-lookup"><span data-stu-id="6cfd5-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="6cfd5-691">檔案共用</span><span class="sxs-lookup"><span data-stu-id="6cfd5-691">File share</span></span></li>
<li><span data-ttu-id="6cfd5-692">Microsoft 惡意程式碼防護中心 (MMPC) </span><span class="sxs-lookup"><span data-stu-id="6cfd5-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="6cfd5-693">
</dt>
<dt>更新階段： &lt; 更新階段 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6cfd5-694">搜尋</span><span class="sxs-lookup"><span data-stu-id="6cfd5-694">Search</span></span></li>
<li><span data-ttu-id="6cfd5-695">下載</span><span class="sxs-lookup"><span data-stu-id="6cfd5-695">Download</span></span></li>
<li><span data-ttu-id="6cfd5-696">安裝</span><span class="sxs-lookup"><span data-stu-id="6cfd5-696">Install</span></span></li>
</ul><span data-ttu-id="6cfd5-697">
</dt>
<dt>來源路徑：通用命名慣例的檔案共用名稱稱 (UNC) ，Windows Server Update Services (WSUS 的伺服器名稱) /Microsoft Update/ADL。</dt> 
<dt>簽章類型： &lt; 簽名類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="6cfd5-698">防毒</span><span class="sxs-lookup"><span data-stu-id="6cfd5-698">Antivirus</span></span></li>
<li><span data-ttu-id="6cfd5-699">間諜</span><span class="sxs-lookup"><span data-stu-id="6cfd5-699">Antispyware</span></span></li>
<li><span data-ttu-id="6cfd5-700">軟體</span><span class="sxs-lookup"><span data-stu-id="6cfd5-700">Antimalware</span></span></li>
<li><span data-ttu-id="6cfd5-701">網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="6cfd5-702">
</dt>
<dt>更新類型： &lt;更新類型 &gt; （完整或 Delta）。</dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
<dt>目前引擎版本： &lt; &gt; 目前引擎</dt>版本
<dt>先前 &lt; &gt; 引擎版本：舊</dt>引擎版本
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤碼錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-702">
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
<span data-ttu-id="6cfd5-703">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-704">當更新定義時發生問題，便會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="6cfd5-705">若要疑難排解此事件：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="6cfd5-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">更新定義</a> ，並直接在端點上強制重新掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="6cfd5-707">如需此錯誤的詳細資訊，請參閱%Windir%\WindowsUpdate.log 檔案中的專案。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="6cfd5-708">連絡 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技術支援</a>。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-709">事件 ID: 2002</span><span class="sxs-lookup"><span data-stu-id="6cfd5-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-710">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-712">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-712">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-713">
<b>已成功更新反惡意程式碼引擎。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-714">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-715">Microsoft Defender 防毒軟體引擎版本已更新。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="6cfd5-716">
<dt>目前引擎版本： &lt;目前引擎版本 &gt; </dt>舊版引擎版本
<dt>： &lt; 舊引擎版本 &gt; </dt>
<dt>引擎類型： &lt; 引擎類型 &gt; ，反惡意程式碼引擎或網路檢查系統引擎。</dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-717">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-718">不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-718">No action is necessary.</span></span> <span data-ttu-id="6cfd5-719">Microsoft Defender 防毒軟體用戶端的狀態良好。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="6cfd5-720">當反惡意程式碼引擎成功更新時會報告此事件。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-721">事件 ID: 2003</span><span class="sxs-lookup"><span data-stu-id="6cfd5-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-722">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-724">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-724">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-725">
<b>反惡意程式碼引擎更新失敗。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-726">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-727">Microsoft Defender 防毒軟體嘗試更新引擎時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="6cfd5-728">
<dt>新引擎版本：</dt>
<dt>舊引擎版本： &lt; &gt; 舊</dt>引擎版本
<dt>引擎類型： &lt; 引擎類型 &gt; ，反惡意軟體引擎或網路檢查系統引擎。</dt>
<dt>使用者： &lt;網域 &gt; \& lt;使用者 &gt; </dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-728">
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
<span data-ttu-id="6cfd5-729">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-730">Microsoft Defender 防毒軟體用戶端更新失敗。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="6cfd5-731">當用戶端無法自行更新時，就會發生此事件。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="6cfd5-732">此事件通常是因為更新期間網路連線中斷所造成。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="6cfd5-733">若要疑難排解此事件：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="6cfd5-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">更新定義</a> ，並直接在端點上強制重新掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="6cfd5-735">連絡 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技術支援</a>。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-736">事件 ID: 2004</span><span class="sxs-lookup"><span data-stu-id="6cfd5-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-737">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-739">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-739">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-740">
<b>載入反惡意程式碼定義時發生問題。反惡意程式碼引擎會嘗試載入最後一組已知良好的定義。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-741">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-742">Microsoft Defender 防毒軟體嘗試載入簽章時發生錯誤，並會嘗試回復回已知良好的簽名集。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="6cfd5-743">
<dt>嘗試的簽名：</dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>簽章
<dt>版本： &lt;定義版本 &gt; </dt>
<dt>引擎版本： &lt; 反惡意引擎 &gt; 版本</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-743">
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
<span data-ttu-id="6cfd5-744">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-745">Microsoft Defender 防毒軟體用戶端嘗試下載並安裝最新的定義檔，但失敗。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="6cfd5-746">當用戶端嘗試載入定義時遇到錯誤，或檔案損毀時，可能會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="6cfd5-747">Microsoft Defender 防毒軟體會嘗試回復回一組已知良好的定義。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="6cfd5-748">若要疑難排解此事件：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="6cfd5-749">重新開機電腦，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="6cfd5-750">從<a href="https://aka.ms/wdsi">Microsoft 安全情報網站</a>下載最新的定義。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="6cfd5-751">附注：從網站下載的定義檔案大小可超過 60 MB，不應做為更新定義的長期方案。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="6cfd5-752">連絡 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技術支援</a>。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-753">事件 ID: 2005</span><span class="sxs-lookup"><span data-stu-id="6cfd5-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-754">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-756">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-756">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-757">
<b>由於反惡意軟體平臺已過時，反惡意程式碼引擎載入失敗。反惡意軟體平臺會載入最後一個已知良好的反惡意程式碼引擎，並嘗試更新。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-758">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-759">由於不支援目前平臺版本，因此 Microsoft Defender 防毒軟體無法載入反惡意程式碼引擎。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="6cfd5-760">Microsoft Defender 防毒軟體會回復至最後一個已知良好的引擎，並且會嘗試進行平臺更新。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="6cfd5-761">
<dt>目前平臺版本： &lt; 目前平臺版本&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-762">事件 ID: 2006</span><span class="sxs-lookup"><span data-stu-id="6cfd5-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-763">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-765">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-765">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-766">
<b>平臺更新失敗。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-767">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-768">Microsoft Defender 防毒軟體嘗試更新平臺時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="6cfd5-769">
<dt>目前平臺版本： &lt;目前的平臺 &gt; 版本</dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤碼錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-770">事件 ID: 2007</span><span class="sxs-lookup"><span data-stu-id="6cfd5-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-771">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-773">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-773">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-774">
<b>此平臺很快就會過期。下載最新的平臺，以維護最新的保護。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-775">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-776">Microsoft Defender 防毒軟體即將需要更新平臺版本，以支援未來版本的反惡意程式碼引擎。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="6cfd5-777">下載最新的 Microsoft Defender 防毒軟體平臺，以維持最佳的保護層級。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="6cfd5-778">
<dt>目前平臺版本： &lt; 目前平臺版本&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-779">事件 ID: 2010</span><span class="sxs-lookup"><span data-stu-id="6cfd5-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-780">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-782">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-782">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-783">
<b>反惡意程式碼引擎使用動態特徵碼服務來取得其他定義。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-784">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-785">Microsoft Defender 防毒軟體使用的<i>動態特徵碼服務</i>，以取得其他簽章，以協助保護您的電腦。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="6cfd5-786">
<dt>目前的特徵碼版本： &lt;目前 &gt; </dt>的簽章版本 
<dt> 簽名類型： &lt; 簽名類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="6cfd5-787">防毒</span><span class="sxs-lookup"><span data-stu-id="6cfd5-787">Antivirus</span></span></li>
<li><span data-ttu-id="6cfd5-788">間諜</span><span class="sxs-lookup"><span data-stu-id="6cfd5-788">Antispyware</span></span></li>
<li><span data-ttu-id="6cfd5-789">軟體</span><span class="sxs-lookup"><span data-stu-id="6cfd5-789">Antimalware</span></span></li>
<li><span data-ttu-id="6cfd5-790">網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="6cfd5-791">
</dt>
<dt>目前引擎版本： &lt;目前引擎版本 &gt; </dt>動態簽章 
<dt> 類型： &lt; 動態簽名類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6cfd5-792">版本</span><span class="sxs-lookup"><span data-stu-id="6cfd5-792">Version</span></span></li>
<li><span data-ttu-id="6cfd5-793">時間 戳</span><span class="sxs-lookup"><span data-stu-id="6cfd5-793">Timestamp</span></span></li>
<li><span data-ttu-id="6cfd5-794">無限制</span><span class="sxs-lookup"><span data-stu-id="6cfd5-794">No limit</span></span></li>
<li><span data-ttu-id="6cfd5-795">持續時間</span><span class="sxs-lookup"><span data-stu-id="6cfd5-795">Duration</span></span></li>
</ul><span data-ttu-id="6cfd5-796">
</dt>
<dt>持久性路徑： &lt;路徑 &gt; </dt>動態簽章
<dt>版本： &lt; 版本 &gt; 號碼</dt>動態簽章
<dt>編譯時間戳： &lt; timestamp &gt; </dt> 
<dt> 持續性限制類型：持續性 &lt; 限制類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6cfd5-797">VDM 版本</span><span class="sxs-lookup"><span data-stu-id="6cfd5-797">VDM version</span></span></li>
<li><span data-ttu-id="6cfd5-798">時間 戳</span><span class="sxs-lookup"><span data-stu-id="6cfd5-798">Timestamp</span></span></li>
<li><span data-ttu-id="6cfd5-799">無限制</span><span class="sxs-lookup"><span data-stu-id="6cfd5-799">No limit</span></span></li>
</ul><span data-ttu-id="6cfd5-800">
</dt>
<dt>持續性限制： fastpath 簽章的持續限制。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-801">事件 ID: 2011</span><span class="sxs-lookup"><span data-stu-id="6cfd5-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-802">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-804">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-804">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-805">
<b>動態簽章服務刪除了到期動態定義。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-806">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-807">Microsoft Defender 防毒軟體使用的<i>動態特徵碼服務</i>捨棄過時的簽名。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="6cfd5-808">
<dt>目前的特徵碼版本： &lt;目前 &gt; </dt>的簽章版本 
<dt> 簽名類型： &lt; 簽名類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="6cfd5-809">防毒</span><span class="sxs-lookup"><span data-stu-id="6cfd5-809">Antivirus</span></span></li>
<li><span data-ttu-id="6cfd5-810">間諜</span><span class="sxs-lookup"><span data-stu-id="6cfd5-810">Antispyware</span></span></li>
<li><span data-ttu-id="6cfd5-811">軟體</span><span class="sxs-lookup"><span data-stu-id="6cfd5-811">Antimalware</span></span></li>
<li><span data-ttu-id="6cfd5-812">網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="6cfd5-813">
</dt>
<dt>目前引擎版本： &lt;目前引擎版本 &gt; </dt>動態簽章 
<dt> 類型： &lt; 動態簽名類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6cfd5-814">版本</span><span class="sxs-lookup"><span data-stu-id="6cfd5-814">Version</span></span></li>
<li><span data-ttu-id="6cfd5-815">時間 戳</span><span class="sxs-lookup"><span data-stu-id="6cfd5-815">Timestamp</span></span></li>
<li><span data-ttu-id="6cfd5-816">無限制</span><span class="sxs-lookup"><span data-stu-id="6cfd5-816">No limit</span></span></li>
<li><span data-ttu-id="6cfd5-817">持續時間</span><span class="sxs-lookup"><span data-stu-id="6cfd5-817">Duration</span></span></li>
</ul><span data-ttu-id="6cfd5-818">
</dt>
<dt>持久性路徑： &lt;路徑 &gt; </dt>動態簽章
<dt>版本： &lt; 版本 &gt; 號碼</dt>動態簽章
<dt>編譯時間戳： &lt; 時間戳記 &gt; </dt>
<dt>移除原因：</dt> 
<dt> 持續性限制類型：持續性 &lt; 限制類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6cfd5-819">VDM 版本</span><span class="sxs-lookup"><span data-stu-id="6cfd5-819">VDM version</span></span></li>
<li><span data-ttu-id="6cfd5-820">時間 戳</span><span class="sxs-lookup"><span data-stu-id="6cfd5-820">Timestamp</span></span></li>
<li><span data-ttu-id="6cfd5-821">無限制</span><span class="sxs-lookup"><span data-stu-id="6cfd5-821">No limit</span></span></li>
</ul><span data-ttu-id="6cfd5-822">
</dt>
<dt>持續性限制： fastpath 簽章的持續限制。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-823">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-824">不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-824">No action is necessary.</span></span> <span data-ttu-id="6cfd5-825">Microsoft Defender 防毒軟體用戶端的狀態良好。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="6cfd5-826">當動態簽章服務成功刪除過期動態定義時，便會報告此事件。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-827">事件 ID: 2012</span><span class="sxs-lookup"><span data-stu-id="6cfd5-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-828">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-830">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-830">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-831">
<b>反惡意程式碼引擎在嘗試使用動態簽章服務時發生錯誤。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-832">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-833">Microsoft Defender 防毒軟體嘗試使用動態簽章<i>服務</i>時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="6cfd5-834">
<dt>目前的特徵碼版本： &lt;目前 &gt; </dt>的簽章版本 
<dt> 簽名類型： &lt; 簽名類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="6cfd5-835">防毒</span><span class="sxs-lookup"><span data-stu-id="6cfd5-835">Antivirus</span></span></li>
<li><span data-ttu-id="6cfd5-836">間諜</span><span class="sxs-lookup"><span data-stu-id="6cfd5-836">Antispyware</span></span></li>
<li><span data-ttu-id="6cfd5-837">軟體</span><span class="sxs-lookup"><span data-stu-id="6cfd5-837">Antimalware</span></span></li>
<li><span data-ttu-id="6cfd5-838">網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="6cfd5-839">
</dt>
<dt>目前引擎版本： &lt;目前引擎版本 &gt; </dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤碼錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt> 
<dt>動態特徵碼類型：動態簽章 &lt; 類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6cfd5-840">版本</span><span class="sxs-lookup"><span data-stu-id="6cfd5-840">Version</span></span></li>
<li><span data-ttu-id="6cfd5-841">時間 戳</span><span class="sxs-lookup"><span data-stu-id="6cfd5-841">Timestamp</span></span></li>
<li><span data-ttu-id="6cfd5-842">無限制</span><span class="sxs-lookup"><span data-stu-id="6cfd5-842">No limit</span></span></li>
<li><span data-ttu-id="6cfd5-843">持續時間</span><span class="sxs-lookup"><span data-stu-id="6cfd5-843">Duration</span></span></li>
</ul><span data-ttu-id="6cfd5-844">
</dt>
<dt>持久性路徑： &lt;路徑 &gt; </dt>動態簽章
<dt>版本： &lt; 版本 &gt; 號碼</dt>動態簽章
<dt>編譯時間戳： &lt; timestamp &gt; </dt> 
<dt> 持續性限制類型：持續性 &lt; 限制類型 &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6cfd5-845">VDM 版本</span><span class="sxs-lookup"><span data-stu-id="6cfd5-845">VDM version</span></span></li>
<li><span data-ttu-id="6cfd5-846">時間 戳</span><span class="sxs-lookup"><span data-stu-id="6cfd5-846">Timestamp</span></span></li>
<li><span data-ttu-id="6cfd5-847">無限制</span><span class="sxs-lookup"><span data-stu-id="6cfd5-847">No limit</span></span></li>
</ul><span data-ttu-id="6cfd5-848">
</dt>
<dt>持續性限制： fastpath 簽章的持續限制。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-849">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-850">檢查您的網際網路連線設定。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-851">事件 ID: 2013</span><span class="sxs-lookup"><span data-stu-id="6cfd5-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-852">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-854">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-854">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-855">
<b>動態特徵碼服務刪除所有動態定義。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-856">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-857">Microsoft Defender 防毒軟體捨棄所有的動態簽章<i>服務</i>簽名。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="6cfd5-858">
<dt>目前的特徵碼版本： &lt; 目前的特徵碼版本&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-859">事件 ID: 2020</span><span class="sxs-lookup"><span data-stu-id="6cfd5-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-860">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-862">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-862">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-863">
<b>反惡意程式碼引擎下載乾淨的檔案。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-864">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-865">Microsoft Defender 防毒軟體下載乾淨的檔案。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="6cfd5-866">
<dt>檔案名： &lt;檔案名 &gt; 的檔案名。</dt>
<dt>目前的特徵碼版本： &lt;目前的特徵 &gt; 碼版本</dt>
<dt>目前引擎版本： &lt; 目前 &gt; 引擎版本</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-867">事件 ID: 2021</span><span class="sxs-lookup"><span data-stu-id="6cfd5-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-868">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-870">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-870">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-871">
<b>反惡意程式碼引擎無法下載乾淨的檔案。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-872">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-873">Microsoft Defender 防毒軟體嘗試下載乾淨檔時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="6cfd5-874">
<dt>檔案名： &lt;檔案名 &gt; 的檔案名。</dt>
<dt>目前的特徵碼版本： &lt;&gt;目前</dt>的簽章版本
<dt>目前引擎版本： &lt; 目前 &gt; 引擎版本</dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤碼錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-874">
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
<span data-ttu-id="6cfd5-875">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-876">檢查您的網際網路連線設定。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="6cfd5-877">Microsoft Defender 防毒軟體用戶端使用動態簽章服務，將最新的定義下載至特定威脅時，發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="6cfd5-878">這種錯誤可能是網路連線問題所造成。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-879">事件 ID: 2030</span><span class="sxs-lookup"><span data-stu-id="6cfd5-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-880">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-882">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-882">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-883">
<b>反惡意程式碼引擎已下載，並設定為在下一個系統重新開機時離線執行。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-884">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-885">在下一次重新開機時，Microsoft Defender 防毒軟體下載和設定離線防病毒以執行。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-886">事件 ID: 2031</span><span class="sxs-lookup"><span data-stu-id="6cfd5-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-887">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-889">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-889">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-890">
<b>反惡意程式碼引擎無法下載和設定離線掃描。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-891">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-892">Microsoft Defender 防毒軟體嘗試下載和設定離線防毒程式時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="6cfd5-893">
<dt>錯誤碼： &lt;&gt;與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-894">事件 ID: 2040</span><span class="sxs-lookup"><span data-stu-id="6cfd5-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-895">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-897">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-897">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-898">
<b>此作業系統版本的反惡意軟體支援很快就會結束。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-899">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-900">您的作業系統支援即將到期。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="6cfd5-901">在不支援的作業系統上執行 Microsoft Defender 防毒程式，不是適當的解決方案來防禦威脅。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-902">事件 ID: 2041</span><span class="sxs-lookup"><span data-stu-id="6cfd5-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-903">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-905">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-905">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-906">
<b>此作業系統的反惡意軟體支援已結束。您必須升級作業系統以繼續支援。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-907">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-908">您的作業系統支援已過期。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-908">The support for your operating system has expired.</span></span> <span data-ttu-id="6cfd5-909">在不支援的作業系統上執行 Microsoft Defender 防毒程式，不是適當的解決方案來防禦威脅。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-910">事件 ID: 2042</span><span class="sxs-lookup"><span data-stu-id="6cfd5-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-911">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-913">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-913">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-914">
<b>反惡意軟體引擎不再支援此作業系統，而且不再從惡意程式碼保護您的系統。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-915">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-916">您的作業系統支援已過期。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-916">The support for your operating system has expired.</span></span> <span data-ttu-id="6cfd5-917">您的作業系統不再支援 Microsoft Defender 防病毒，已停止運作，而且無法防範惡意程式碼威脅。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-918">事件 ID: 3002</span><span class="sxs-lookup"><span data-stu-id="6cfd5-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-919">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-921">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-921">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-922">
<b>即時保護發生錯誤，失敗。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-923">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-924">Microsoft Defender 防病毒 Real-Time 保護功能發生錯誤，失敗。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="6cfd5-925">
<dt>Feature： &lt; feature &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6cfd5-926">存取</span><span class="sxs-lookup"><span data-stu-id="6cfd5-926">On Access</span></span></li>
<li><span data-ttu-id="6cfd5-927">Internet Explorer 下載和 Microsoft Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="6cfd5-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="6cfd5-928">行為監控</span><span class="sxs-lookup"><span data-stu-id="6cfd5-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="6cfd5-929">網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="6cfd5-930">
</dt>
<dt>錯誤碼： &lt;&gt;與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。</dt>
<dt>原因： Microsoft Defender 防病毒即時防護已重新開機某項功能的原因。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-931">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-932">您應該重新開機系統，然後執行完整掃描，因為它&#39;可能一段時間沒有保護系統。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="6cfd5-933">Microsoft Defender 防病毒用戶端&#39;即時保護功能發生錯誤，因為其中一個服務無法啟動。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="6cfd5-934">如果後面接著是3007事件識別碼，表示失敗為暫時的，反惡意軟體用戶端已從失敗中復原。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-935">事件 ID: 3007</span><span class="sxs-lookup"><span data-stu-id="6cfd5-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-936">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-938">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-938">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-939">
<b>即時保護已從失敗中復原。當您看到此錯誤時，建議執行完整系統掃描。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-940">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-941">Microsoft Defender 防病毒即時保護已重新開機功能。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="6cfd5-942">建議您執行完整系統掃描，以偵測此代理程式中斷時可能錯過的任何專案。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="6cfd5-943">
<dt>Feature： &lt; feature &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6cfd5-944">存取</span><span class="sxs-lookup"><span data-stu-id="6cfd5-944">On Access</span></span></li>
<li><span data-ttu-id="6cfd5-945">IE 下載和 Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="6cfd5-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="6cfd5-946">行為監控</span><span class="sxs-lookup"><span data-stu-id="6cfd5-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="6cfd5-947">網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="6cfd5-948">
</dt>
<dt>原因： Microsoft Defender 防病毒即時防護已重新開機某項功能的原因。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-949">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-950">已重新開機即時保護功能。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="6cfd5-951">如果發生此事件，請與 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技術支援</a>人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-952">事件 ID: 5000</span><span class="sxs-lookup"><span data-stu-id="6cfd5-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-953">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-955">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-955">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-956">
<b>已啟用即時保護。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-957">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-958">已啟用針對惡意程式碼和其他可能有害軟體的 Microsoft Defender 防病毒即時防護掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-959">事件 ID: 5001</span><span class="sxs-lookup"><span data-stu-id="6cfd5-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-960">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-962">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-962">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-963">
<b>已停用即時保護。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-964">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-965">已停用 Microsoft Defender 防毒軟體和其他可能有害軟體的即時防護掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-966">事件 ID: 5004</span><span class="sxs-lookup"><span data-stu-id="6cfd5-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-967">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-969">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-969">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-970">
<b>已變更即時保護設定。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-971">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-972">Microsoft Defender 防病毒即時保護功能設定已經變更。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="6cfd5-973">
<dt>Feature： &lt; feature &gt; ，例如：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6cfd5-974">存取</span><span class="sxs-lookup"><span data-stu-id="6cfd5-974">On Access</span></span></li>
<li><span data-ttu-id="6cfd5-975">IE 下載和 Outlook Express 附件</span><span class="sxs-lookup"><span data-stu-id="6cfd5-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="6cfd5-976">行為監控</span><span class="sxs-lookup"><span data-stu-id="6cfd5-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="6cfd5-977">網路檢查系統</span><span class="sxs-lookup"><span data-stu-id="6cfd5-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="6cfd5-978">
</dt>
<dt>配置： </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-979">事件 ID: 5007</span><span class="sxs-lookup"><span data-stu-id="6cfd5-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-980">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-982">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-982">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-983">
<b>已變更反惡意軟體平臺設定。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-984">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-985">Microsoft Defender 防病毒設定已經變更。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="6cfd5-986">如果這是未預期的事件，您應該檢查設定，因為這可能是惡意程式碼的結果。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="6cfd5-987">
<dt>舊值： &lt;舊值號碼 &gt; 舊的防病毒設定值。</dt>
<dt>新值： &lt;新值號碼 &gt; 新的防病毒設定值。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-988">事件 ID: 5008</span><span class="sxs-lookup"><span data-stu-id="6cfd5-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-989">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-991">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-991">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-992">
<b>反惡意軟體引擎發生錯誤，失敗。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-993">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-994">Microsoft Defender 防病毒引擎因未預期的錯誤而終止。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="6cfd5-995">
<dt>失敗類型： &lt;失敗類型 &gt; ，例如：損毀或懸掛</dt>
<dt>例外狀況碼： &lt; 錯誤碼 &gt; </dt> 
<dt>resource： &lt; resource &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-996">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-997">若要疑難排解此事件：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="6cfd5-998">嘗試重新開機服務。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="6cfd5-999">若為反惡意軟體、防病毒和間諜軟體，請在提升許可權的命令提示字元處，輸入 <b>net stop msmpsvc</b>，然後輸入 <b>net start msmpsvc</b> 以重新開機反惡意程式碼引擎。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="6cfd5-1000">針對 <i>網路檢查系統</i>，在提升許可權的命令提示字元處，輸入 <b>net start nissrv</b>，然後輸入 <b>net start nissrv</b> ，以使用 NiSSRV.exe 檔案重新開機 <i>網路檢查系統</i> 引擎。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="6cfd5-1001">若失敗，請存取 <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支援網站</a>  ，並在 <b>搜尋</b> 方塊中輸入錯誤號碼，以查詢錯誤碼，並與 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技術支援</a>人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1002">使用者動作：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-1003">Microsoft Defender 防毒軟體用戶端引擎因未預期的錯誤而停止。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="6cfd5-1004">若要疑難排解此事件：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="6cfd5-1005">再次執行掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="6cfd5-1006">若失敗，請移至 [ <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支援網站</a>]，然後在 <b>搜尋</b> 方塊中輸入錯誤號碼，以尋找錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="6cfd5-1007">連絡 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技術支援</a>。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1008">事件 ID: 5009</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-1009">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1011">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-1012">
<b>已啟用對惡意程式碼和其他可能有害軟體的掃描。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1013">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-1014">已啟用對惡意軟體和其他可能有害軟體的 Microsoft Defender 防毒軟體掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1015">事件 ID: 5010</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-1016">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1018">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-1019">
<b>已停用針對惡意程式碼和其他可能有害軟體的掃描。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1020">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-1021">已停用針對惡意程式碼和其他可能有害軟體的 Microsoft Defender 防毒軟體掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1022">事件 ID: 5011</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-1023">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1025">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-1026">
<b>已啟用病毒掃描。</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1027">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-1028">已啟用 Microsoft Defender 防毒軟體掃描病毒。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1029">事件 ID: 5012</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-1030">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1032">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-1033">
<b>已停用掃描病毒。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1034">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-1035">已停用 Microsoft Defender 防毒軟體掃描病毒。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1036">事件 ID: 5100</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-1037">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1039">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-1040">
<b>反惡意程式碼平臺即將到期。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1041">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-1042">Microsoft Defender 防毒軟體已輸入寬限期，很快就會到期。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="6cfd5-1043">到期後，此程式會停用防護病毒、間諜軟體和其他可能不需要的軟體。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="6cfd5-1044">
<dt>到期原因： Microsoft Defender 防毒軟體會到期的原因。</dt>
<dt>到期日：日期 Microsoft Defender 防毒軟體會到期。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1045">事件 ID: 5101</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6cfd5-1046">符號名稱：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1048">消息：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="6cfd5-1049">
<b>反惡意程式碼平臺已過期。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1050">描述：</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="6cfd5-1051">Microsoft Defender 防毒軟體寬限時間已過期。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="6cfd5-1052">停用防護病毒、間諜軟體和其他可能不需要的軟體。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="6cfd5-1053">
<dt>到期原因：</dt>
<dt>終止日期： </dt>
<dt>錯誤碼： &lt; &gt; 與威脅狀態相關聯的錯誤代碼結果代碼。標準 HRESULT 值。</dt>
<dt>錯誤描述： &lt;錯誤描述 &gt; 錯誤的描述。 </dt>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="6cfd5-1054">
</table>

<a id="error-codes"></a>
##Microsoft Defender 防毒軟體用戶端錯誤碼如果 Microsoft Defender 防毒軟體遇到任何問題，它通常會提供錯誤代碼來協助您進行問題的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="6cfd5-1055">最常見的錯誤是表示安裝更新時發生問題。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="6cfd5-1056">本節提供下列關於 Microsoft Defender 防毒軟體用戶端錯誤的資訊。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="6cfd5-1057">-   錯誤碼的 -   可能原因為錯誤 -   通知的現在原因</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="6cfd5-1058">使用這些表格中的資訊可協助疑難排解 Microsoft Defender 防毒軟體錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1059">錯誤碼：0x80508007</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="6cfd5-1060">訊息</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1060">Message</span></span></td>
<td><span data-ttu-id="6cfd5-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1062">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="6cfd5-1063">此錯誤表示您的記憶體可能不足。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="6cfd5-1064">解決方案</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="6cfd5-1065">檢查裝置上可用的記憶體。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="6cfd5-1066">關閉任何未使用的應用程式，以釋放裝置上的記憶體。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="6cfd5-1067">重新開機裝置，然後再次執行掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1068">錯誤碼：0x8050800C</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="6cfd5-1069">訊息</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1069">Message</span></span></td>
<td><span data-ttu-id="6cfd5-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="6cfd5-1071">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="6cfd5-1072">此錯誤表示您的安全性產品可能有問題。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="6cfd5-1073">解決方案</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="6cfd5-1074">更新定義。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1074">Update the definitions.</span></span> <span data-ttu-id="6cfd5-1075">可</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1075">Either:</span></span><ol>
<li><span data-ttu-id="6cfd5-1076">在 Microsoft Defender 防毒軟體的 [<b>更新</b>] 索引標籤上，按一下 [<b>更新定義</b>] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="6cfd5-1077">或是，</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1077">Or,</span></span>
</li>
<li><span data-ttu-id="6cfd5-1078">從<a href="https://aka.ms/wdsi">Microsoft 安全情報網站</a>下載最新的定義。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="6cfd5-1079">附注：從網站下載的定義檔案大小可超過 60 MB，不應做為更新定義的長期方案。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="6cfd5-1080">執行完整掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="6cfd5-1081">重新開機裝置，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1082">錯誤碼：0x80508020</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="6cfd5-1083">訊息</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1083">Message</span></span></td>
<td><span data-ttu-id="6cfd5-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="6cfd5-1085">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="6cfd5-1086">此錯誤表示可能存在引擎設定錯誤;這通常與不允許引擎正確運作的輸入資料相關。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1087">錯誤碼：0x805080211</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="6cfd5-1088">訊息</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1088">Message</span></span></td>
<td><span data-ttu-id="6cfd5-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="6cfd5-1090">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="6cfd5-1091">此錯誤表示 Microsoft Defender 防毒軟體無法隔離威脅。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1092">錯誤碼：0x80508022</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="6cfd5-1093">訊息</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1093">Message</span></span></td>
<td><span data-ttu-id="6cfd5-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="6cfd5-1095">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="6cfd5-1096">此錯誤指出需要重新開機以完成威脅移除。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="6cfd5-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="6cfd5-1098">訊息</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1098">Message</span></span></td>
<td><span data-ttu-id="6cfd5-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="6cfd5-1100">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="6cfd5-1101">此錯誤表示此威脅可能不再出現在媒體上，或惡意程式碼可能會停止您掃描裝置。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="6cfd5-1102">解決方案</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="6cfd5-1103">請執行<a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft 安全掃描工具</a>，更新您的安全性軟體，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1104">錯誤碼：0x80508024</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="6cfd5-1105">訊息</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1105">Message</span></span></td>
<td><span data-ttu-id="6cfd5-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="6cfd5-1107">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="6cfd5-1108">此錯誤表示可能需要進行完整系統掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="6cfd5-1109">解決方案</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1109">Resolution</span></span></td><td>
<span data-ttu-id="6cfd5-1110">執行完整系統掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1111">錯誤碼：0x80508025</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="6cfd5-1112">訊息</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1112">Message</span></span></td>
<td><span data-ttu-id="6cfd5-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="6cfd5-1114">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="6cfd5-1115">此錯誤指出需要手動步驟以完成威脅移除。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="6cfd5-1116">解決方案</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1116">Resolution</span></span></td><td>
<span data-ttu-id="6cfd5-1117">遵循 <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft 惡意程式碼保護百科全書</a>中所述的手動修正步驟。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="6cfd5-1118">您可以在事件歷程記錄中尋找威脅特有的連結。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1119">錯誤碼：0x80508026</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="6cfd5-1120">訊息</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1120">Message</span></span></td>
<td><span data-ttu-id="6cfd5-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="6cfd5-1122">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="6cfd5-1123">此錯誤表示可能不支援在容器類型中移除。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="6cfd5-1124">解決方案</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1124">Resolution</span></span></td><td>
<span data-ttu-id="6cfd5-1125">Microsoft Defender 防毒軟體無法修正在封存中偵測到的威脅。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="6cfd5-1126">請考慮手動移除偵測到的資源。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1127">錯誤碼：0x80508027</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="6cfd5-1128">訊息</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1128">Message</span></span></td>
<td><span data-ttu-id="6cfd5-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="6cfd5-1130">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="6cfd5-1131">此錯誤表示可能停用刪除低和中威脅的移除。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="6cfd5-1132">解決方案</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1132">Resolution</span></span></td><td>
<span data-ttu-id="6cfd5-1133">檢查偵測到的威脅，並視需要加以解決。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1134">錯誤碼：0x80508029</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="6cfd5-1135">訊息</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1135">Message</span></span></td>
<td><span data-ttu-id="6cfd5-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="6cfd5-1137">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="6cfd5-1138">此錯誤表示需要重新掃描威脅。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="6cfd5-1139">解決方案</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1139">Resolution</span></span></td><td>
<span data-ttu-id="6cfd5-1140">執行完整系統掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1141">錯誤碼：0x80508030</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="6cfd5-1142">訊息</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1142">Message</span></span></td>
<td><span data-ttu-id="6cfd5-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="6cfd5-1144">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="6cfd5-1145">此錯誤表示需要離線掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="6cfd5-1146">解決方案</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1146">Resolution</span></span></td><td>
<span data-ttu-id="6cfd5-1147">執行離線 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="6cfd5-1148">您可以在<a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">離線 Microsoft Defender 防毒軟體文章</a>中閱讀如何執行此動作。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6cfd5-1149">錯誤碼：0x80508031</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="6cfd5-1150">訊息</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1150">Message</span></span></td>
<td><span data-ttu-id="6cfd5-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="6cfd5-1152">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="6cfd5-1153">此錯誤指出 Microsoft Defender 防毒軟體不支援目前平臺版本，且需要新版本的平臺。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="6cfd5-1154">解決方案</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1154">Resolution</span></span></td><td>
<span data-ttu-id="6cfd5-1155">Windows 10 中只能使用 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="6cfd5-1156">針對 Windows 8，Windows 7 和 Windows 的 Vista，您可以使用<a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="6cfd5-1157">

<a id="internal-error-codes"></a>在 Microsoft Defender 防毒軟體內部測試期間會使用下列錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="6cfd5-1158">如果您看到這些錯誤，您可以嘗試 [更新定義](manage-updates-baselines-microsoft-defender-antivirus.md) ，並直接在端點上強制重新掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="6cfd5-1159">內部錯誤碼</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="6cfd5-1160"><b>錯誤碼</b></span><span class="sxs-lookup"><span data-stu-id="6cfd5-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="6cfd5-1161">顯示的訊息</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1161">Message displayed</span></span></th>
<th><span data-ttu-id="6cfd5-1162">錯誤和解決的可能原因</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="6cfd5-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="6cfd5-1165">請檢查您的網際網路連線，然後再次執行掃描。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="6cfd5-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>發送</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="6cfd5-1168">這是內部錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1168">This is an internal error.</span></span> <span data-ttu-id="6cfd5-1169">原因並未明確定義。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="6cfd5-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="6cfd5-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="6cfd5-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="6cfd5-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="6cfd5-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="6cfd5-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="6cfd5-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="6cfd5-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="6cfd5-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="6cfd5-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="6cfd5-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="6cfd5-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="6cfd5-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="6cfd5-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="6cfd5-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="6cfd5-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="6cfd5-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="6cfd5-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="6cfd5-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="6cfd5-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="6cfd5-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="6cfd5-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="6cfd5-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="6cfd5-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="6cfd5-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="6cfd5-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="6cfd5-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="6cfd5-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="6cfd5-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="6cfd5-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="6cfd5-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="6cfd5-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="6cfd5-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="6cfd5-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="6cfd5-1238">這是內部錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1238">This is an internal error.</span></span> <span data-ttu-id="6cfd5-1239">當惡意程式碼移除失敗時，可能會觸發此情況。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6cfd5-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="6cfd5-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="6cfd5-1242">這是內部錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1242">This is an internal error.</span></span> <span data-ttu-id="6cfd5-1243">它可能會在掃描無法完成時觸發。</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="6cfd5-1244">相關主題</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1244">Related topics</span></span>

- [<span data-ttu-id="6cfd5-1245">報告 Microsoft Defender 防毒軟體保護</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6cfd5-1246">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="6cfd5-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)