---
title: 檢視 Office 365 進階威脅防護報告
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 05/21/2019
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
description: 了解如何尋找並使用 Office 365 進階威脅防護中的安全性報告&amp;合規性中心。
ms.openlocfilehash: d5f0958d199684a9d6ca6bfe4ed01c0ab9102a2a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078313"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="4d8c0-103">檢視 Office 365 進階威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="4d8c0-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="4d8c0-104">如果您的組織有[Office 365 進階威脅防護](office-365-atp.md)(ATP)，而且您具有[必要權限](#what-permissions-are-needed-to-view-the-atp-reports)，您可以使用數個 ATP 報告中的安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="4d8c0-105">(前往**報告** \> **儀表板**。)</span><span class="sxs-lookup"><span data-stu-id="4d8c0-105">(Go to **Reports** \> **Dashboard**.)</span></span>
  
![安全性&amp;合規性中心的儀表板可協助您查看正常進階威脅防護](../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="4d8c0-107">ATP 報告包含下列：</span><span class="sxs-lookup"><span data-stu-id="4d8c0-107">ATP reports include the following:</span></span>
- [<span data-ttu-id="4d8c0-108">威脅保護狀態報表</span><span class="sxs-lookup"><span data-stu-id="4d8c0-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="4d8c0-109">ATP 檔案類型的報告</span><span class="sxs-lookup"><span data-stu-id="4d8c0-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="4d8c0-110">ATP 郵件處理報表</span><span class="sxs-lookup"><span data-stu-id="4d8c0-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="4d8c0-111">[即時偵測或檔案總管]](threat-explorer.md) （視您是否具有 Office 365 ATP 方案 1 或 2）</span><span class="sxs-lookup"><span data-stu-id="4d8c0-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="4d8c0-112">...[以及更多](#additional-reports-to-view)。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-112">... [and more](#additional-reports-to-view).</span></span> 

<span data-ttu-id="4d8c0-113">閱讀本篇文章以取得 ATP 報告概觀，以及如何使用它們。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-113">Read this article to get an overview of ATP reports and how to use them.</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="4d8c0-114">威脅保護狀態報表</span><span class="sxs-lookup"><span data-stu-id="4d8c0-114">Threat Protection Status report</span></span>

<span data-ttu-id="4d8c0-115">**威脅保護狀態**報表是整合在一起惡意內容和惡意電子郵件偵測並封鎖由[Exchange Online Protection](exchange-online-protection-overview.md) (EOP) 和[Office 365 ATP](office-365-atp.md)的相關資訊的單一檢視。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="4d8c0-116">這份報告可以用來檢視偵測一段時間 （最多為 90 天），並可讓安全性系統管理員識別趨勢或判斷原則是否需要調整。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span> 

<span data-ttu-id="4d8c0-117">威脅保護狀態報告提供的唯一的電子郵件與惡意內容，例如檔案或網站位址 (Url) 已封鎖的反惡意程式碼引擎，[零時差自動清除 (ZAP)](zero-hour-auto-purge.md)，彙總的計數，以及 like ATP 功能[ATP 安全連結](atp-safe-links.md)、 [ATP 安全附件](atp-safe-attachments.md)及[ATP 防網路釣魚功能](atp-anti-phishing.md)。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-117">The Threat Protection Status report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="4d8c0-118">威脅保護狀態報表是適用於擁有[Office 365 ATP](office-365-atp.md)或[Exchange Online Protection](exchange-online-protection-eop.md) (EOP); 客戶然而，ATP 客戶威脅保護狀態報表中顯示的資訊可能會包含不同資料比 EOP 客戶可能會看到的內容。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-118">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="4d8c0-119">例如，ATP 客戶威脅保護狀態報表將包含[SharePoint Online、 OneDrive 或 Microsoft Teams 中偵測到惡意檔案](atp-for-spo-odb-and-teams.md)的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-119">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="4d8c0-120">這類資訊是專屬於 ATP，，因此 EOP，但不是 ATP 的客戶將不會看到其威脅保護狀態報表中的這些詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-120">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="4d8c0-121">若要檢視中的威脅保護狀態報表，[安全性&amp;合規性中心](https://protection.office.com)，請移至**報表** \> **儀表板** \> **威脅保護狀態**。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-121">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![ATP 威脅保護狀態報表](../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="4d8c0-123">若要取得一天的詳細的狀態，將游標置於上方圖形。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-123">To get detailed status for a day, hover over the graph.</span></span>
  
![一天的 ATP 威脅保護狀態資料](../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="4d8c0-125">根據預設，威脅保護狀態報告顯示過去 7 天的資料。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-125">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="4d8c0-126">不過，您可以選擇 [**篩選器**，並變更日期範圍，以檢視最多為 90 天的資料。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-126">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="4d8c0-127">（如果您使用試用訂閱，您可能會受限於的 30 天的資料。）</span><span class="sxs-lookup"><span data-stu-id="4d8c0-127">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>
  
![ATP 威脅保護狀態篩選](../media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="4d8c0-129">您也可以使用 [**檢視資料**] 功能表來變更報表中顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-129">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![檢視 ATP 威脅保護狀態報表的選項](../media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="4d8c0-131">ATP 檔案類型的報告</span><span class="sxs-lookup"><span data-stu-id="4d8c0-131">ATP File Types report</span></span>

<span data-ttu-id="4d8c0-132">**ATP 檔案類型**的報告顯示[ATP 安全附件](atp-safe-attachments.md)所偵測到視為惡意的檔案的類型。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-132">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="4d8c0-133">若要檢視此報告中，在[安全性&amp;合規性中心](https://protection.office.com)，請移至**報表** \> **儀表板** \> **ATP 檔案類型**。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-133">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![ATP 檔案類型的報告](../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="4d8c0-135">當您將游標的特定一天時，您可以看到分解為由[ATP 安全附件](atp-safe-attachments.md)所偵測到的惡意檔案的類型和[反垃圾郵件&amp;Office 365 中的反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-135">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![一天的 ATP 檔案類型報告資料](../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="4d8c0-137">ATP 郵件處理報表</span><span class="sxs-lookup"><span data-stu-id="4d8c0-137">ATP Message Disposition report</span></span>

<span data-ttu-id="4d8c0-138">**ATP 郵件處理**報告會顯示您針對已偵測到具有惡意內容的電子郵件所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-138">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="4d8c0-139">若要檢視此報告中，在[安全性&amp;合規性中心](https://protection.office.com)，請移至**報表** \> **儀表板** \> **ATP 郵件處理**。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-139">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![ATP 郵件處理報告](../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="4d8c0-141">當您將滑鼠停留在圖表中的列時，您可以看到哪些動作是偵測到的電子郵件的那一天。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-141">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![一天的 ATP 郵件處理報告資料](../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="4d8c0-143">若要檢視其他報告</span><span class="sxs-lookup"><span data-stu-id="4d8c0-143">Additional reports to view</span></span>

<span data-ttu-id="4d8c0-144">除了本文所述的 ATP 報告下, 表所述，都可以使用、 數個其他報告：</span><span class="sxs-lookup"><span data-stu-id="4d8c0-144">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="4d8c0-145">報告</span><span class="sxs-lookup"><span data-stu-id="4d8c0-145">Report(s)</span></span>  |<span data-ttu-id="4d8c0-146">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4d8c0-146">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="4d8c0-147">**檔案總管**] 或 [**即時偵測**（Office 365 ATP 計劃 2 的客戶會有瀏覽器;Office 365 ATP 計劃 1 客戶擁有即時偵測的資訊）。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-147">**Explorer** or **real-time detections** (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>| [<span data-ttu-id="4d8c0-148">威脅總管 （和即時偵測的資訊）</span><span class="sxs-lookup"><span data-stu-id="4d8c0-148">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)       |
|<span data-ttu-id="4d8c0-149">**電子郵件安全性報告**，例如頂端寄件者和收件者報告、 詐騙郵件] 報告和垃圾郵件偵測] 報告。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-149">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="4d8c0-150">檢視安全性中的電子郵件安全性報告&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="4d8c0-150">View email security reports in the Security &amp; Compliance Center</span></span>](../../compliance/view-email-security-reports.md)        |
|<span data-ttu-id="4d8c0-151">**ATP 安全連結 URL 追蹤**（這是您藉由使用 PowerShell 產生報表）。這份報告顯示過去七 （7） 天 ATP 安全連結動作的結果。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-151">**ATP Safe Links URL trace** (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span> |[<span data-ttu-id="4d8c0-152">Get-urltrace cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="4d8c0-152">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace?view=exchange-ps) |
|<span data-ttu-id="4d8c0-153">**透過 EOP 和 ATP 的結果**（這是您藉由使用 PowerShell 產生自訂報告）。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-153">**EOP and ATP results** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="4d8c0-154">此報告中包含的資訊，例如網域、 日期、 事件類型、 方向、 巨集指令，以及訊息計數。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-154">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="4d8c0-155">取得 MailTrafficATPReport cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="4d8c0-155">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|<span data-ttu-id="4d8c0-156">**EOP 和 ATP 偵測**（這是您藉由使用 PowerShell 產生自訂報告）。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-156">**EOP and ATP detections** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="4d8c0-157">這份報告包含詳細惡意檔案或 Url、 網路釣魚嘗試、 模擬，以及其他電子郵件或檔案中的潛在威脅。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-157">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="4d8c0-158">取得 MailDetailATPReport cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="4d8c0-158">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="4d8c0-159">若要檢視 ATP 報告需要哪些權限？</span><span class="sxs-lookup"><span data-stu-id="4d8c0-159">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="4d8c0-160">若要檢視及使用本文中所述的報告**您必須具有適當的角色指派給這兩種安全性&amp;規範中心和 Exchange 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-160">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="4d8c0-161">Security&amp;合規性中心，您必須有一個指派的下列角色：</span><span class="sxs-lookup"><span data-stu-id="4d8c0-161">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="4d8c0-162">組織管理</span><span class="sxs-lookup"><span data-stu-id="4d8c0-162">Organization Management</span></span>
    - <span data-ttu-id="4d8c0-163">安全性系統管理員 (這可以在 Azure Active Directory 系統管理中心中指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="4d8c0-163">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="4d8c0-164">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="4d8c0-164">Security Reader</span></span>

- <span data-ttu-id="4d8c0-165">若是 Exchange Online 中，您必須安裝下列其中一個在 Exchange 系統管理中心中指派下列角色 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或使用 PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="4d8c0-165">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="4d8c0-166">組織管理</span><span class="sxs-lookup"><span data-stu-id="4d8c0-166">Organization Management</span></span>
    - <span data-ttu-id="4d8c0-167">僅檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="4d8c0-167">View-only Organization Management</span></span>
    - <span data-ttu-id="4d8c0-168">僅檢視收件者角色</span><span class="sxs-lookup"><span data-stu-id="4d8c0-168">View-Only Recipients role</span></span>
    - <span data-ttu-id="4d8c0-169">合規性管理</span><span class="sxs-lookup"><span data-stu-id="4d8c0-169">Compliance Management</span></span>

<span data-ttu-id="4d8c0-170">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="4d8c0-170">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="4d8c0-171">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="4d8c0-171">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="4d8c0-172">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="4d8c0-172">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="4d8c0-173">如果報表不顯示資料？</span><span class="sxs-lookup"><span data-stu-id="4d8c0-173">What if the reports aren't showing data?</span></span>

<span data-ttu-id="4d8c0-174">如果您不 ATP 報告中看到的資料，請仔細檢查您的原則已正確設定。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-174">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="4d8c0-175">您的組織必須有[ATP 安全連結原則](set-up-atp-safe-links-policies.md)，並定義 ATP 保護的順序中的[ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)就地。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-175">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="4d8c0-176">請參閱[在 Office 365 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="4d8c0-176">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4d8c0-177">相關主題</span><span class="sxs-lookup"><span data-stu-id="4d8c0-177">Related topics</span></span>

[<span data-ttu-id="4d8c0-178">報告和 Office 365 安全性的深入解析&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="4d8c0-178">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="4d8c0-179">建立報表排程安全性&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="4d8c0-179">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="4d8c0-180">設定及下載自訂報告中的安全性&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="4d8c0-180">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

