---
title: 檢視適用於 Office 365 的 Microsoft Defender 報告
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
description: 系統管理員可以瞭解如何針對 Microsoft 365 Defender 入口網站中提供的 Office 365 報告尋找和使用 Defender。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7eab856f22ac1c2282e83897db6e3f93d4d97e6
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083509"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="dcf8f-103">在 Microsoft 365 Defender 入口網站中查看 Office 365 報表的 Defender</span><span class="sxs-lookup"><span data-stu-id="dcf8f-103">View Defender for Office 365 reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="dcf8f-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-104">**Applies to**</span></span>
- [<span data-ttu-id="dcf8f-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="dcf8f-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="dcf8f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dcf8f-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="dcf8f-107">適用于 Office 365 組織的 Microsoft Defender (例如，Microsoft 365 E5 訂閱或 microsoft defender for Office 365 plan 1 或 microsoft defender for Office 365 plan 2 附加元件) 包含各種安全性相關的報表。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="dcf8f-108">如果您有 [必要的許可權](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)，您可以在 Microsoft 365 Defender 入口網站中透過 **報告** \> **&** 共同作業 \> **電子郵件 &** 共同作業報告來查看這些報告。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="dcf8f-109">若要直接移至 [ **電子郵件 &** 共同作業報告] 頁面上，開啟 <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-109">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Microsoft 365 Defender 入口網站中的電子郵件 & 共同作業報告] 頁面](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="dcf8f-111">不需要 Office 365 Defender 的電子郵件安全性報告會在[Microsoft 365 Defender 入口網站中的「查看電子郵件安全性報告](view-email-security-reports.md)」中說明加以說明。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-111">Email security reports that don't require Defender for Office 365 are described in [View email security reports in the Microsoft 365 Defender portal](view-email-security-reports.md).</span></span>
>
> <span data-ttu-id="dcf8f-112">與郵件流程相關的報告現在位於 Exchange 系統管理中心 (EAC) 。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-112">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="dcf8f-113">如需這些報告的詳細資訊，請參閱[新 Exchange 系統管理中心的郵件流程報告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-113">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="safe-attachments-file-types-report"></a><span data-ttu-id="dcf8f-114">保管庫附件檔案類型報告</span><span class="sxs-lookup"><span data-stu-id="dcf8f-114">Safe Attachments file types report</span></span>

> [!NOTE]
> <span data-ttu-id="dcf8f-115">**保管庫附件檔案類型報告** 會最終消失。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-115">The **Safe Attachments file types report** will eventually go away.</span></span> <span data-ttu-id="dcf8f-116">「 [威脅防護狀態」報告](#threat-protection-status-report)中提供相同的資訊。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-116">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="safe-attachments-message-disposition-report"></a><span data-ttu-id="dcf8f-117">保管庫附件郵件處理報告</span><span class="sxs-lookup"><span data-stu-id="dcf8f-117">Safe Attachments message disposition report</span></span>

> [!NOTE]
> <span data-ttu-id="dcf8f-118">**保管庫附件郵件處理報告** 會最後消失。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-118">The **Safe Attachments message disposition report** will eventually go away.</span></span> <span data-ttu-id="dcf8f-119">「 [威脅防護狀態」報告](#threat-protection-status-report)中提供相同的資訊。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-119">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="dcf8f-120">郵件延遲報告</span><span class="sxs-lookup"><span data-stu-id="dcf8f-120">Mail latency report</span></span>

<span data-ttu-id="dcf8f-121">**郵件延遲報告** 會向您顯示組織內的郵件傳遞和引爆延遲的匯總視圖。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-121">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="dcf8f-122">服務中的郵件傳遞時間受到多種因素的影響，而且絕對傳遞時間（秒）通常不是成功或問題的明確指示。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-122">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="dcf8f-123">在一天內的傳遞時間可能會被視為另一天的平均傳遞時間，或反過來。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-123">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="dcf8f-124">這會嘗試根據對其他郵件的觀察傳遞時間的統計資料來傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-124">This tries to qualify message delivery based on statistical data about the observed delivery times of other messages.</span></span>

<span data-ttu-id="dcf8f-125">不包括用戶端和網路延遲。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-125">Client side and network latency are not included.</span></span>

<span data-ttu-id="dcf8f-126">若要查看報告，請開啟 [Microsoft 365 Defender 入口網站](https://security.microsoft.com)，然後移至 [**報告** \> **電子郵件 &** 共同作業 \> **電子郵件 &** 共同作業報告]。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-126">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="dcf8f-127">在 [ **電子郵件 &** 共同作業報告] 頁面上，尋找 [ **郵件延遲報告** ]，然後按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-127">On the **Email & collaboration reports** page, find **Mail latency report** and then click **View details**.</span></span> <span data-ttu-id="dcf8f-128">若要直接前往報表，請開啟 <https://security.microsoft.com/mailLatencyReport> 。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-128">To go directly to the report, open <https://security.microsoft.com/mailLatencyReport>.</span></span>

![「電子郵件 & 協同報告」頁面上的郵件延遲報告構件](../../media/mail-latency-report-widget.png)

<span data-ttu-id="dcf8f-130">在 [ **郵件延遲報告** ] 頁面上，[ **郵件延遲報告** ] 頁面上提供下列索引標籤：</span><span class="sxs-lookup"><span data-stu-id="dcf8f-130">On the **Mail latency report** page, the following tabs are available on the **Mail latency report** page:</span></span>

- <span data-ttu-id="dcf8f-131">第 **50 個百分點**：這是郵件傳遞時間的中間部分。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-131">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="dcf8f-132">您可以將此值視為平均傳遞時間。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-132">You can consider this value as an average delivery time.</span></span> <span data-ttu-id="dcf8f-133">預設會選取此索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-133">This tab is selected by default.</span></span>
- <span data-ttu-id="dcf8f-134">**90%**：這表示郵件傳遞的高延遲。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-134">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="dcf8f-135">只有10% 的郵件花費的時間超過此值才能傳遞。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-135">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="dcf8f-136">**99th 百分點**：這表示郵件傳遞的最高延遲。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-136">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="dcf8f-137">不論選取的索引標籤為何，圖表都會顯示組織成下列類別的郵件：</span><span class="sxs-lookup"><span data-stu-id="dcf8f-137">Regardless of the tab you select, the chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="dcf8f-138">**郵件傳遞延遲**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-138">**Mail delivery latency**</span></span>
- <span data-ttu-id="dcf8f-139">**Detonations**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-139">**Detonations**</span></span>

<span data-ttu-id="dcf8f-140">當您將游標移到圖表中的某個類別時，您可以查看每個類別中的延遲明細。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-140">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![第50百分位數郵件延遲報告的視圖](../../media/mail-latency-report-50th-percentile-view.png)

<span data-ttu-id="dcf8f-142">如果您按一下 [ **篩選**]，您可以透過下列值來篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="dcf8f-142">If you click **Filter**, you can filter both the chart and the details table by the following values:</span></span>

- <span data-ttu-id="dcf8f-143">**日期 (UTC)**： **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-143">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="dcf8f-144">**郵件視圖**：下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="dcf8f-144">**Message view**: One of the following values:</span></span>
  - <span data-ttu-id="dcf8f-145">**所有郵件**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-145">**All messages**</span></span>
  - <span data-ttu-id="dcf8f-146">**包含附件或 URLs 的郵件**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-146">**Messages that contain attachments or URLs**</span></span>
  - <span data-ttu-id="dcf8f-147">**引爆郵件**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-147">**Detonated messages**</span></span>

<span data-ttu-id="dcf8f-148">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-148">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="dcf8f-149">在圖表下方的 [詳細資料] 表格中，可使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="dcf8f-149">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="dcf8f-150">**日期 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-150">**Date (UTC)**</span></span>
- <span data-ttu-id="dcf8f-151">**百分位數**： **50**、 **90** 或 **99**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-151">**Percentiles**: **50**, **90**, or **99**</span></span>
- <span data-ttu-id="dcf8f-152">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-152">**Message count**</span></span>
- <span data-ttu-id="dcf8f-153">**整體延遲**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-153">**Overall latency**</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="dcf8f-154">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="dcf8f-154">Threat protection status report</span></span>

<span data-ttu-id="dcf8f-155">「**威脅防護狀態** 報告」是單一的視圖，可透過 [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) 和 Microsoft Defender for Office 365，彙集惡意內容和惡意電子郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-155">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="dcf8f-156">如需詳細資訊，請參閱 [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-156">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="dcf8f-157">URL 威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="dcf8f-157">URL threat protection report</span></span>

<span data-ttu-id="dcf8f-158">**url 威脅防護報告** 可提供偵測到之威脅的摘要和趨勢視圖，以及在 URL 按一下上做為 [保管庫連結](safe-links.md)的一部分所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-158">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](safe-links.md).</span></span> <span data-ttu-id="dcf8f-159">在套用保管庫連結原則的使用者上，按一下 [不 **追蹤使用者點擊**] 選項時，此報告不會有按一下資料。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-159">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="dcf8f-160">若要查看報告，請開啟 [Microsoft 365 Defender 入口網站](https://security.microsoft.com)，然後移至 [**報告** \> **電子郵件 &** 共同作業 \> **電子郵件 &** 共同作業報告]。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-160">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="dcf8f-161">在 [ **電子郵件 &** 共同作業報告] 頁面上，找到 [ **URL 保護] 頁面** ，然後按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-161">On the **Email & collaboration reports** page, find **URL protection page** and then click **View details**.</span></span> <span data-ttu-id="dcf8f-162">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/URLProtectionActionReport> 。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-162">To go directly to the report, open <https://security.microsoft.com/reports/URLProtectionActionReport>.</span></span>

![電子郵件 & 協同報告] 頁面上的 URL 保護報告構件](../../media/url-protection-report-widget.png)

<span data-ttu-id="dcf8f-164">下列各節將說明 [ **URL 威脅防護** 報告] 頁面上可用的視圖。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-164">The available views on the **URL threat protection** report page are described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="dcf8f-165">這是一項 *保護趨勢報告*，表示資料代表較大資料集的趨勢。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-165">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="dcf8f-166">因此，在這種情況下，圖表中的資料並不是即時的，但是 [詳細資料] 表格中的資料是，因此您可能會看到兩者之間的差異稍有不同。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-166">As a result, the data in the charts is not available in real time here, but the data in the details table is, so you may see a slight discrepancy between the two.</span></span> <span data-ttu-id="dcf8f-167">圖表每四小時重新整理一次，並包含過去90天的資料。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-167">The charts are refreshed once every four hours and contain data for the last 90 days.</span></span>

### <a name="view-data-by-url-click-protection-action"></a><span data-ttu-id="dcf8f-168">依 URL 查看資料按一下 [保護動作]</span><span class="sxs-lookup"><span data-stu-id="dcf8f-168">View data by URL click protection action</span></span>

![Url 威脅防護報告中的 URL 按一下保護動作視圖](../../media/url-threat-protection-report-url-click-protection-action-view.png)

<span data-ttu-id="dcf8f-170">**依 URL 的查看資料按一下 [保護動作**] 視圖，會顯示組織中使用者的 URL 按一下數目，以及按一下的結果。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-170">The **View data by URL click protection action** view shows the number of URL clicks by users in the organization and the results of the click:</span></span>

- <span data-ttu-id="dcf8f-171">**允許**：允許使用者流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-171">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="dcf8f-172">已 **封鎖**：已封鎖使用者流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-172">**Blocked**: The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="dcf8f-173">**封鎖並按一下透過**：使用者已選擇繼續導覽 URL。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-173">**Blocked and clicked through**: The user has chosen to continue navigating to the URL.</span></span>
- <span data-ttu-id="dcf8f-174">在 **掃描期間按一下流覽**：使用者已在掃描完成之前按一下連結。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-174">**Clicked through during scan**: The user has clicked on the link before the scan was complete.</span></span>

<span data-ttu-id="dcf8f-175">按一下表示使用者已透過封鎖頁面按一下至惡意網站 (系統管理員可以停用保管庫連結原則) 中的按一下。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-175">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

<span data-ttu-id="dcf8f-176">如果您按一下 [ **篩選**]，您可以在出現的浮出控制項中選取下列一或多個值，以修改報告和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="dcf8f-176">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="dcf8f-177">**日期 (UTC)**： **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-177">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="dcf8f-178">**偵測**：</span><span class="sxs-lookup"><span data-stu-id="dcf8f-178">**Detection**:</span></span>
  - <span data-ttu-id="dcf8f-179">**允許**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-179">**Allowed**</span></span>
  - <span data-ttu-id="dcf8f-180">**封鎖**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-180">**Blocked**</span></span>
  - <span data-ttu-id="dcf8f-181">**封鎖並按一下**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-181">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="dcf8f-182">**在掃描期間按一下**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-182">**Clicked through during scan**</span></span>
- <span data-ttu-id="dcf8f-183">**網域**：報告結果中列出的 URL 網域。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-183">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="dcf8f-184">**收件者**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-184">**Recipients**</span></span>

<span data-ttu-id="dcf8f-185">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="dcf8f-186">圖表下方的 [詳細資料] 表格提供下列最近7天內所有按一下動作的近乎即時視圖：</span><span class="sxs-lookup"><span data-stu-id="dcf8f-186">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="dcf8f-187">**按一下 [時間]**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-187">**Click time**</span></span>
- <span data-ttu-id="dcf8f-188">**使用者**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-188">**User**</span></span>
- <span data-ttu-id="dcf8f-189">**URL**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-189">**URL**</span></span>
- <span data-ttu-id="dcf8f-190">**Action**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-190">**Action**</span></span>
- <span data-ttu-id="dcf8f-191">**應用程式**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-191">**App**</span></span>

### <a name="view-data-by-url-click-by-application"></a><span data-ttu-id="dcf8f-192">依 URL 查看資料依應用程式按一下</span><span class="sxs-lookup"><span data-stu-id="dcf8f-192">View data by URL click by application</span></span>

![URL 威脅防護報告中的 [依應用程式視圖按一下 URL]](../../media/url-threat-protection-report-url-click-by-application-view.png)

<span data-ttu-id="dcf8f-194">**依 URL 的 View data 依序按一下 [應用程式** 視圖]，會顯示支援保管庫連結的應用程式的 URL 按一下數目：</span><span class="sxs-lookup"><span data-stu-id="dcf8f-194">The **View data by URL click by application** view shows the number of URL clicks by apps that support Safe Links:</span></span>

- <span data-ttu-id="dcf8f-195">**電子郵件用戶端**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-195">**Email client**</span></span>
- <span data-ttu-id="dcf8f-196">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-196">**PowerPoint**</span></span>
- <span data-ttu-id="dcf8f-197">**Word**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-197">**Word**</span></span>
- <span data-ttu-id="dcf8f-198">**Excel**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-198">**Excel**</span></span>
- <span data-ttu-id="dcf8f-199">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-199">**OneNote**</span></span>
- <span data-ttu-id="dcf8f-200">**Visio**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-200">**Visio**</span></span>
- <span data-ttu-id="dcf8f-201">**Teams**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-201">**Teams**</span></span>
- <span data-ttu-id="dcf8f-202">**別人**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-202">**Others**</span></span>

<span data-ttu-id="dcf8f-203">如果您按一下 [ **篩選**]，您可以在出現的浮出控制項中選取下列一或多個值，以修改報告和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="dcf8f-203">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="dcf8f-204">**日期 (UTC)**： **開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-204">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="dcf8f-205">**偵測**：圖表中可用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-205">**Detection**: Available apps from the chart.</span></span>
- <span data-ttu-id="dcf8f-206">**網域**：報告結果中列出的 URL 網域。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-206">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="dcf8f-207">**收件者**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-207">**Recipients**</span></span>

<span data-ttu-id="dcf8f-208">當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-208">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="dcf8f-209">圖表下方的 [詳細資料] 表格提供下列最近7天內所有按一下動作的近乎即時視圖：</span><span class="sxs-lookup"><span data-stu-id="dcf8f-209">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="dcf8f-210">**按一下 [時間]**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-210">**Click time**</span></span>
- <span data-ttu-id="dcf8f-211">**使用者**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-211">**User**</span></span>
- <span data-ttu-id="dcf8f-212">**URL**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-212">**URL**</span></span>
- <span data-ttu-id="dcf8f-213">**Action**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-213">**Action**</span></span>
- <span data-ttu-id="dcf8f-214">**應用程式**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-214">**App**</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="dcf8f-215">要查看的其他報告</span><span class="sxs-lookup"><span data-stu-id="dcf8f-215">Additional reports to view</span></span>

<span data-ttu-id="dcf8f-216">除了本文所述的報告之外，還有其他幾個報告可供使用，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="dcf8f-216">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

<br>

****

|<span data-ttu-id="dcf8f-217">報告</span><span class="sxs-lookup"><span data-stu-id="dcf8f-217">Report</span></span>|<span data-ttu-id="dcf8f-218">主題</span><span class="sxs-lookup"><span data-stu-id="dcf8f-218">Topic</span></span>|
|---|---|
|<span data-ttu-id="dcf8f-219">**Explorer** (microsoft defender for Office 365 plan 2) 或 **即時** 偵測 (Microsoft defender for Office 365 Plan 1) </span><span class="sxs-lookup"><span data-stu-id="dcf8f-219">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="dcf8f-220">威脅總管 (及即時偵測)</span><span class="sxs-lookup"><span data-stu-id="dcf8f-220">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="dcf8f-221">**電子郵件安全性報告**，例如主要寄件者和收件者報告、冒名郵件報告和垃圾郵件偵測報告。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-221">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="dcf8f-222">在 Microsoft 365 Defender 入口網站中查看電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="dcf8f-222">View email security reports in the Microsoft 365 Defender portal</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="dcf8f-223">**郵件流程報告**，例如轉寄報告、郵件流程狀態報表，以及主要寄件者和收件者報告。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-223">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="dcf8f-224">新 Exchange 系統管理中心的郵件流程報告</span><span class="sxs-lookup"><span data-stu-id="dcf8f-224">Mail flow reports in the new Exchange admin center</span></span>](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|<span data-ttu-id="dcf8f-225">**保管庫連結的 URL 追蹤** (僅 PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-225">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="dcf8f-226">此 Cmdlet 的輸出會顯示在過去7天中保管庫連結動作的結果。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-226">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="dcf8f-227">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="dcf8f-227">Get-UrlTrace</span></span>](/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="dcf8f-228">僅 PowerShell) ， **EOP 和 Microsoft Defender for Office 365 (的郵件流量結果**。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-228">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="dcf8f-229">此 Cmdlet 的輸出包含網域、日期、事件種類、方向、動作和郵件數目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-229">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="dcf8f-230">MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="dcf8f-230">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="dcf8f-231">**EOP 和 Defender Office 365 偵測的郵件詳細資料包告** (僅 PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-231">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="dcf8f-232">此 Cmdlet 的輸出包含有關電子郵件或檔案中惡意檔案或 URLs、網路釣魚企圖、模仿及其他潛在威脅的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-232">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="dcf8f-233">MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="dcf8f-233">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="dcf8f-234">流覽 Office 365 報表的 Defender 時，需要哪些許可權？</span><span class="sxs-lookup"><span data-stu-id="dcf8f-234">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="dcf8f-235">為了查看和使用本文所述的報表，您必須是 Microsoft 365 Defender 入口網站中下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="dcf8f-235">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="dcf8f-236">**組織管理**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-236">**Organization Management**</span></span>
- <span data-ttu-id="dcf8f-237">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-237">**Security Administrator**</span></span>
- <span data-ttu-id="dcf8f-238">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-238">**Security Reader**</span></span>
- <span data-ttu-id="dcf8f-239">**全域讀取器**</span><span class="sxs-lookup"><span data-stu-id="dcf8f-239">**Global Reader**</span></span>

<span data-ttu-id="dcf8f-240">如需詳細資訊，請參閱 [Microsoft 365 Defender 入口網站中的權限](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-240">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

<span data-ttu-id="dcf8f-241">**附注**：將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 Defender 入口網站中的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-241">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="dcf8f-242">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-242">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="dcf8f-243">如果報告未顯示資料，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="dcf8f-243">What if the reports aren't showing data?</span></span>

<span data-ttu-id="dcf8f-244">如果您未在 Office 365 報告中看到您的 Defender 資料，請仔細檢查您的原則設定是否正確。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-244">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="dcf8f-245">您的組織必須已定義[保管庫連結原則](set-up-safe-links-policies.md)及[保管庫附件原則](set-up-safe-attachments-policies.md)，才能使用 Defender，Office 365 保護功能即就地。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-245">Your organization must have [Safe Links policies](set-up-safe-links-policies.md) and [Safe Attachments policies](set-up-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="dcf8f-246">另請參閱 [反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="dcf8f-246">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dcf8f-247">相關主題</span><span class="sxs-lookup"><span data-stu-id="dcf8f-247">Related topics</span></span>

[<span data-ttu-id="dcf8f-248">Microsoft 365 Defender 入口網站中的智慧報告和洞察力</span><span class="sxs-lookup"><span data-stu-id="dcf8f-248">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="dcf8f-249">角色許可權 (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="dcf8f-249">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
