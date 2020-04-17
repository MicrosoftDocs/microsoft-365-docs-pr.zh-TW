---
title: 查看 Office 365 的報告高級威脅防護、惡意程式碼報告、網路釣魚報告、受損帳戶、URL 保護狀態、威脅報告、報告威脅
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: 在安全性&amp;與合規性中心尋找及使用 Office 365 的「高級威脅防護」報告。
ms.openlocfilehash: b91fb8d000b610439618be687e36dabc787ebb58
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528974"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="1e791-103">檢視 Office 365 進階威脅防護的報告</span><span class="sxs-lookup"><span data-stu-id="1e791-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="1e791-104">如果您的組織有[Office 365 高級威脅防護](office-365-atp.md)（ATP），而且您有[必要的許可權](#what-permissions-are-needed-to-view-the-atp-reports)，您可以在安全性&amp;與合規性中心使用數個 ATP 報告。</span><span class="sxs-lookup"><span data-stu-id="1e791-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="1e791-105">（移至 [**報表** \> ]**儀表板**）。</span><span class="sxs-lookup"><span data-stu-id="1e791-105">(Go to **Reports** \> **Dashboard**.)</span></span>

![安全性&amp;與合規性中心儀表板可協助您查看高級威脅防護的運作情形](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

<span data-ttu-id="1e791-107">ATP 報告包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="1e791-107">ATP reports include the following:</span></span>

- [<span data-ttu-id="1e791-108">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="1e791-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="1e791-109">ATP 檔案類型報告</span><span class="sxs-lookup"><span data-stu-id="1e791-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="1e791-110">ATP 郵件處置報告</span><span class="sxs-lookup"><span data-stu-id="1e791-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="1e791-111">[即時偵測或 Explorer](threat-explorer.md) （取決於您是否有 OFFICE 365 ATP 方案1或2）</span><span class="sxs-lookup"><span data-stu-id="1e791-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="1e791-112">...[等等](#additional-reports-to-view)。</span><span class="sxs-lookup"><span data-stu-id="1e791-112">... [and more](#additional-reports-to-view).</span></span>

<span data-ttu-id="1e791-113">請閱讀本文，以取得 ATP 報表及其用法的概覽。</span><span class="sxs-lookup"><span data-stu-id="1e791-113">Read this article to get an overview of ATP reports and how to use them.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="1e791-114">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="1e791-114">Threat Protection Status report</span></span>

<span data-ttu-id="1e791-115">「**威脅防護狀態**報告」是單一的視圖，可彙集[Exchange Online Protection](exchange-online-protection-overview.md) （EOP）和[Office 365 ATP](office-365-atp.md)所偵測到和封鎖的惡意內容和惡意電子郵件資訊。</span><span class="sxs-lookup"><span data-stu-id="1e791-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="1e791-116">此報告可用於查看一段時間內的偵測（最多90天），並可讓安全性管理員識別趨勢或判斷是否需要調整原則。</span><span class="sxs-lookup"><span data-stu-id="1e791-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

<span data-ttu-id="1e791-117">該報告提供包含惡意內容的獨特電子郵件的匯總計數，例如檔案或網站位址（URLs），該惡意內容已封鎖反惡意程式碼引擎、[零小時的自動清除（ZAP）](zero-hour-auto-purge.md)和 atp 功能（如[atp 安全連結](atp-safe-links.md)、 [atp 安全附件](atp-safe-attachments.md)及[atp 反網路釣魚](set-up-anti-phishing-policies.md)）。</span><span class="sxs-lookup"><span data-stu-id="1e791-117">The report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="1e791-118">資訊的篩選和細分可讓您在此報告中進一步細化資訊的類別。</span><span class="sxs-lookup"><span data-stu-id="1e791-118">Filters and breakdowns of the information allow for more granular categorizations of the information in this report.</span></span> <span data-ttu-id="1e791-119">具體而言，**電子郵件** \> **網路釣魚**和**電子郵件** \> **惡意程式碼視圖**中也會包含「細分者」功能表。</span><span class="sxs-lookup"><span data-stu-id="1e791-119">Specifically, there is a 'break down by' menu included for **Email** \> **Phish** and **Email** \> **Malware views**.</span></span> <span data-ttu-id="1e791-120">它會將資料分解成：</span><span class="sxs-lookup"><span data-stu-id="1e791-120">It will break down the data into:</span></span>

|||
|---|---|
|<span data-ttu-id="1e791-121">依偵測類型</span><span class="sxs-lookup"><span data-stu-id="1e791-121">By detection type</span></span>|<span data-ttu-id="1e791-122">哪些原則會協助捕捉這些威脅？</span><span class="sxs-lookup"><span data-stu-id="1e791-122">What policy helped catch these threats?</span></span>|
|<span data-ttu-id="1e791-123">依偵測技術</span><span class="sxs-lookup"><span data-stu-id="1e791-123">By detection technology</span></span>|<span data-ttu-id="1e791-124">哪些基本的 Microsoft 技術會陷入威脅？</span><span class="sxs-lookup"><span data-stu-id="1e791-124">What underlying Microsoft technology caught the threat?</span></span>|
|<span data-ttu-id="1e791-125">依傳遞狀態</span><span class="sxs-lookup"><span data-stu-id="1e791-125">By delivery status</span></span>|<span data-ttu-id="1e791-126">電子郵件被偵測為威脅時會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="1e791-126">What happened to the email messages detected as threats?</span></span>|
|

> [!TIP]
> <span data-ttu-id="1e791-127">電子郵件 > 網路釣魚 |惡意程式碼視圖對顯示的偵測技術有細微的損害，其類別如*ATP 產生的檔案信譽*、檔案*引爆*、 *URL 引爆*、*反欺騙性： DMARC 失敗*，例如，明確確切指出您的組織攔截威脅的確切功能 led。</span><span class="sxs-lookup"><span data-stu-id="1e791-127">Both the Email > Phish | Malware views have granular breakdowns for the detection technologies shown, with categories like *ATP-generated file reputation*, *File detonation*, *URL detonation*, *Anti-spoof: DMARC failure*, for example, helpful in pinpointing exactly which feature led your organization to catch threats.</span></span>

![[威脅防護狀態報表] 下拉式清單顯示「中斷者」。](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

<span data-ttu-id="1e791-129">這些視圖可讓您透過按鈕按一下（在電子郵件 > 網路釣魚詐騙、電子郵件 > 惡意程式碼和內容 > 惡意程式碼視圖）中匯出選項。</span><span class="sxs-lookup"><span data-stu-id="1e791-129">These views give you the option to export, via a button click (in Email > Phish, Email > Malware, and Content > Malware views).</span></span> <span data-ttu-id="1e791-130">匯出至電腦的匯總資料可以在 Excel 中開啟。</span><span class="sxs-lookup"><span data-stu-id="1e791-130">The aggregated data exported to your computer can be opened in Excel.</span></span>

![此圖形顯示匯出為惡意程式碼視圖功能表中的選項、建立排程和要求報告之間的選項。](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

<span data-ttu-id="1e791-132">「一覽」和「電子郵件」視圖會在處理時間內（而不是24小時）顯示資訊（要求重新）。</span><span class="sxs-lookup"><span data-stu-id="1e791-132">The Overview and Emails views will display information within hours of processing rather than in 24 hours (demand re.</span></span> <span data-ttu-id="1e791-133">增加的速度是清晰的信號）！</span><span class="sxs-lookup"><span data-stu-id="1e791-133">increased speeds here has been a clear signal)!</span></span>

> [!NOTE]
> <span data-ttu-id="1e791-134">具有[Office 365 ATP](office-365-atp.md)或[Exchange Online Protection](exchange-online-protection-eop.md) （EOP）的客戶可以使用威脅防護狀態報表;不過，針對 ATP 客戶顯示在威脅防護狀態報表中的資訊，其可能會包含與客戶可能看到的 EOP 不同的資料。</span><span class="sxs-lookup"><span data-stu-id="1e791-134">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="1e791-135">例如，ATP 客戶的「威脅防護狀態報表」會包含[SharePoint 線上、OneDrive 或 Microsoft 小組中偵測到之惡意](atp-for-spo-odb-and-teams.md)檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1e791-135">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="1e791-136">這類資訊專用於 ATP，所以具有 EOP 但不是 ATP 的客戶將無法在威脅防護狀態報表中看到這些詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1e791-136">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>

<span data-ttu-id="1e791-137">若要查看「威脅防護狀態」報告，請在[安全性&amp;與合規性中心](https://protection.office.com)，移至 [**報告** \> ]**儀表板** \> **威脅防護狀態**。</span><span class="sxs-lookup"><span data-stu-id="1e791-137">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>

![ATP 威脅防護狀態報表](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)

<span data-ttu-id="1e791-139">若要取得一天的詳細狀態，請將游標懸停在圖形上方。</span><span class="sxs-lookup"><span data-stu-id="1e791-139">To get detailed status for a day, hover over the graph.</span></span>

![一天的 ATP 威脅防護狀態資料](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)

<span data-ttu-id="1e791-141">「威脅防護狀態」報告預設會顯示過去7天的資料。</span><span class="sxs-lookup"><span data-stu-id="1e791-141">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="1e791-142">不過，您可以選擇 [**篩選**] 並變更日期範圍，以查看最多90天的資料。</span><span class="sxs-lookup"><span data-stu-id="1e791-142">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="1e791-143">（如果您是使用試用訂閱，則可能會限制為30天的資料。）</span><span class="sxs-lookup"><span data-stu-id="1e791-143">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

![ATP 威脅防護狀態篩選](../../media/4f703369-642b-402b-9758-b9c828283410.png)

<span data-ttu-id="1e791-145">您也可以使用 [ **View data by** ] 功能表來變更報表中所顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="1e791-145">You can also use the **View data by** menu to change what information is displayed in the report.</span></span>

![查看 ATP 威脅防護狀態報表的選項](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a><span data-ttu-id="1e791-147">URL 保護狀態報表</span><span class="sxs-lookup"><span data-stu-id="1e791-147">URL Protection Status report</span></span>

<span data-ttu-id="1e791-148">這份報告是以每次按一下來收集的資料，以及偵測到的威脅（而大多數其他電子郵件威脅相關的報告為每一封郵件資料）。</span><span class="sxs-lookup"><span data-stu-id="1e791-148">This report is based data collected, and threats detected, per click (whereas most other email threat related reports are per message data).</span></span> <span data-ttu-id="1e791-149">此報告的設計目的是顯示來自電子郵件和檔中每次按一下的超連結的威脅。</span><span class="sxs-lookup"><span data-stu-id="1e791-149">This report is designed to show threats that come from hyperlinks in email messages and documents, per click.</span></span> <span data-ttu-id="1e791-150">有兩種觀點：</span><span class="sxs-lookup"><span data-stu-id="1e791-150">There are two views:</span></span>

|||
|---|---|
|<span data-ttu-id="1e791-151">URL 按一下保護動作</span><span class="sxs-lookup"><span data-stu-id="1e791-151">URL click protection action</span></span>|<span data-ttu-id="1e791-152">查看封鎖的 URLs 數目、封鎖但以使用者的按一下權覆寫，使用者會以點擊和允許的方式覆寫。</span><span class="sxs-lookup"><span data-stu-id="1e791-152">See the number of URLs blocked, blocked but overridden with a click-through by a user, overridden with a click-through by a user, and allowed.</span></span>|
|<span data-ttu-id="1e791-153">依應用程式按一下 URL</span><span class="sxs-lookup"><span data-stu-id="1e791-153">URL click by application</span></span>|<span data-ttu-id="1e791-154">請參閱已按一下 URL 的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1e791-154">See the application from which the URL was clicked.</span></span>|
|

<span data-ttu-id="1e791-155">在 [詳細資料] 表格中，您將可以看到有關按一下時間和使用者資訊的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1e791-155">In the details table, you'll be able to see more information regarding click time and user information.</span></span> <span data-ttu-id="1e791-156">最後，請記住 URL 保護狀態報表顯示來自 ATP 安全連結功能的保護，所以只有已啟用 ATP 安全連結的客戶才能看到此報告上會反映的資料。</span><span class="sxs-lookup"><span data-stu-id="1e791-156">Finally, keep in mind the URL Protection Status report shows the protection from ATP Safe Links feature, so only customers who have enabled ATP Safe Links will see data reflected on this report.</span></span>

> [!NOTE]
> <span data-ttu-id="1e791-157">這是一項*保護趨勢報告*，表示資料代表較大資料集的趨勢。</span><span class="sxs-lookup"><span data-stu-id="1e791-157">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="1e791-158">報告無法在這裡即時提供。</span><span class="sxs-lookup"><span data-stu-id="1e791-158">Reporting isn't available in real time here.</span></span> <span data-ttu-id="1e791-159">若為即時 URL，請按一下 [資料]，然後繼續使用 URL 追蹤。</span><span class="sxs-lookup"><span data-stu-id="1e791-159">For real time URL click data, please continue to use URL Trace.</span></span>

## <a name="atp-file-types-report"></a><span data-ttu-id="1e791-160">ATP 檔案類型報告</span><span class="sxs-lookup"><span data-stu-id="1e791-160">ATP File Types report</span></span>

<span data-ttu-id="1e791-161">**Atp 檔案類型**報告會顯示由[ATP 安全附件](atp-safe-attachments.md)偵測為惡意的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="1e791-161">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

<span data-ttu-id="1e791-162">若要查看此報告，請[在&amp;安全性與合規性中心](https://protection.office.com)，移至 [**報告** \> ]**儀表板** \> **ATP 檔案類型**。</span><span class="sxs-lookup"><span data-stu-id="1e791-162">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>

![ATP 檔案類型報告](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)

<span data-ttu-id="1e791-164">當您將游標移到某一天時，您可以在 Office 365 中看到由[ATP 安全附件](atp-safe-attachments.md)和[ &amp;反垃圾郵件反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)所偵測到之惡意檔案類型的細目。</span><span class="sxs-lookup"><span data-stu-id="1e791-164">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>

![ATP 檔案類型一天的報告資料](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)

## <a name="atp-message-disposition-report"></a><span data-ttu-id="1e791-166">ATP 郵件處置報告</span><span class="sxs-lookup"><span data-stu-id="1e791-166">ATP Message Disposition report</span></span>

<span data-ttu-id="1e791-167">**ATP 郵件**處理報告會顯示偵測到有惡意內容的電子郵件所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="1e791-167">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="1e791-168">若要查看此報告，請[在&amp;安全性與合規性中心](https://protection.office.com)，移至 [**報告** \> ]**儀表板** \> **ATP 郵件部署**。</span><span class="sxs-lookup"><span data-stu-id="1e791-168">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>

![ATP 郵件處置報告](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)

<span data-ttu-id="1e791-170">當您將游標移到圖表中的某個列上方時，您就會看到針對該天所偵測到的電子郵件所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="1e791-170">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>

![一天的 ATP 郵件處置報告資料](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)

## <a name="additional-reports-to-view"></a><span data-ttu-id="1e791-172">要查看的其他報告</span><span class="sxs-lookup"><span data-stu-id="1e791-172">Additional reports to view</span></span>

<span data-ttu-id="1e791-173">除了本文所述的 ATP 報告之外，還有其他幾個報告可供使用，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="1e791-173">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|||
|---|---|
|<span data-ttu-id="1e791-174">**報告**</span><span class="sxs-lookup"><span data-stu-id="1e791-174">**Report(s)**</span></span>|<span data-ttu-id="1e791-175">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="1e791-175">**Details**</span></span>|
|<span data-ttu-id="1e791-176">**瀏覽器**或**即時**偵測：（Office 365 ATP Plan 2 客戶具有 Explorer;Office 365 ATP Plan 1 客戶具備即時偵測。</span><span class="sxs-lookup"><span data-stu-id="1e791-176">**Explorer** or **real-time detections**: (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>|[<span data-ttu-id="1e791-177">威脅總管 (及即時偵測)</span><span class="sxs-lookup"><span data-stu-id="1e791-177">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="1e791-178">**電子郵件安全性報告**，例如主要寄件者和收件者報告、冒名郵件報告和垃圾郵件偵測報告。</span><span class="sxs-lookup"><span data-stu-id="1e791-178">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span>|[<span data-ttu-id="1e791-179">檢視安全性與合規性中心內的電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="1e791-179">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="1e791-180">**ATP 安全連結 URL 追蹤**：（這是您使用 PowerShell 所產生的報表）。此報告顯示在過去七（7）天內 ATP 安全連結動作的結果。</span><span class="sxs-lookup"><span data-stu-id="1e791-180">**ATP Safe Links URL trace**: (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span>|[<span data-ttu-id="1e791-181">Get-UrlTrace Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="1e791-181">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace)|
|<span data-ttu-id="1e791-182">**EOP 和 ATP 結果**：（這是您使用 PowerShell 所產生的自訂報告）。</span><span class="sxs-lookup"><span data-stu-id="1e791-182">**EOP and ATP results**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="1e791-183">此報告包含資訊，例如網域、日期、事件種類、方向、動作和郵件數目。</span><span class="sxs-lookup"><span data-stu-id="1e791-183">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="1e791-184">MailTrafficATPReport Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="1e791-184">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport)|
|<span data-ttu-id="1e791-185">**EOP 和 ATP**偵測：（這是您使用 PowerShell 所產生的自訂報告）。</span><span class="sxs-lookup"><span data-stu-id="1e791-185">**EOP and ATP detections**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="1e791-186">此報告包含有關電子郵件或檔案中惡意檔案或 URLs、網路釣魚企圖、模仿及其他潛在威脅的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1e791-186">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="1e791-187">MailDetailATPReport Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="1e791-187">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="1e791-188">查看 ATP 報表所需的許可權為何？</span><span class="sxs-lookup"><span data-stu-id="1e791-188">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="1e791-189">為了查看和使用本文所述的報告，**您必須為安全性&amp;與合規性中心和 Exchange 系統管理中心指派適當的角色**。</span><span class="sxs-lookup"><span data-stu-id="1e791-189">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="1e791-190">針對「安全性與合規性中心」，您必須受指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="1e791-190">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="1e791-191">組織管理</span><span class="sxs-lookup"><span data-stu-id="1e791-191">Organization Management</span></span>
  - <span data-ttu-id="1e791-192">安全性系統管理員 (這可以在 Azure Active Directory 系統管理中心指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="1e791-192">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="1e791-193">安全操作員（可以在 Azure Active Directory 系統管理中心[https://aad.portal.azure.com](https://aad.portal.azure.com)內指派）</span><span class="sxs-lookup"><span data-stu-id="1e791-193">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="1e791-194">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="1e791-194">Security Reader</span></span>

- <span data-ttu-id="1e791-195">針對 Exchange Online，您必須在 Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) 受指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="1e791-195">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="1e791-196">組織管理</span><span class="sxs-lookup"><span data-stu-id="1e791-196">Organization Management</span></span>
  - <span data-ttu-id="1e791-197">僅檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="1e791-197">View-only Organization Management</span></span>
  - <span data-ttu-id="1e791-198">僅檢視收件者角色</span><span class="sxs-lookup"><span data-stu-id="1e791-198">View-Only Recipients role</span></span>
  - <span data-ttu-id="1e791-199">合規性管理</span><span class="sxs-lookup"><span data-stu-id="1e791-199">Compliance Management</span></span>

<span data-ttu-id="1e791-200">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="1e791-200">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="1e791-201">Office 365 安全性與合規性中心權限</span><span class="sxs-lookup"><span data-stu-id="1e791-201">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="1e791-202">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="1e791-202">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="1e791-203">如果報告未顯示資料，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="1e791-203">What if the reports aren't showing data?</span></span>

<span data-ttu-id="1e791-204">如果您未看到 ATP 報告中的資料，請仔細檢查您的原則設定是否正確。</span><span class="sxs-lookup"><span data-stu-id="1e791-204">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="1e791-205">您的組織必須已定義[Atp 安全連結原則](set-up-atp-safe-links-policies.md)和[atp 安全附件原則](set-up-atp-safe-attachments-policies.md)，才能進行 atp 保護。</span><span class="sxs-lookup"><span data-stu-id="1e791-205">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="1e791-206">另請參閱[Office 365 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="1e791-206">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1e791-207">相關主題</span><span class="sxs-lookup"><span data-stu-id="1e791-207">Related topics</span></span>

[<span data-ttu-id="1e791-208">Office 365 安全性&amp;與合規性中心內的報告與深入瞭解</span><span class="sxs-lookup"><span data-stu-id="1e791-208">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="1e791-209">在安全性&amp;與合規性中心建立報表的排程</span><span class="sxs-lookup"><span data-stu-id="1e791-209">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)

[<span data-ttu-id="1e791-210">在安全性&amp;與合規性中心內設定及下載自訂報告</span><span class="sxs-lookup"><span data-stu-id="1e791-210">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)

[<span data-ttu-id="1e791-211">角色許可權（Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1e791-211">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
