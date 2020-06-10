---
title: 安全性儀表板概述
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
description: 使用新的安全性儀表板來查看 Office 365 威脅防護狀態，並查看並處理安全性警示。
ms.openlocfilehash: 6aedc0e499a489d7526737700ecc76deab9e6e32
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679129"
---
# <a name="security-dashboard"></a><span data-ttu-id="b4e55-103">安全性儀表板</span><span class="sxs-lookup"><span data-stu-id="b4e55-103">Security Dashboard</span></span>

## <a name="overview"></a><span data-ttu-id="b4e55-104">概觀</span><span class="sxs-lookup"><span data-stu-id="b4e55-104">Overview</span></span>

<span data-ttu-id="b4e55-105">[安全性 & 合規性中心](../../compliance/go-to-the-securitycompliance-center.md)可讓您的組織管理資料保護和符合性。</span><span class="sxs-lookup"><span data-stu-id="b4e55-105">The [Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md) enables your organization to manage data protection and compliance.</span></span> <span data-ttu-id="b4e55-106">假設您有必要的許可權，安全性儀表板可讓您檢查威脅防護狀態，以及查看和處理安全性警示。</span><span class="sxs-lookup"><span data-stu-id="b4e55-106">Assuming you have the necessary permissions, the Security Dashboard enables you to review your Threat Protection Status, as well as view and act on security alerts.</span></span>

<span data-ttu-id="b4e55-107">觀賞影片以取得概要，然後閱讀本文以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="b4e55-107">Watch the video to get an overview, and then read this article to learn more.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

<span data-ttu-id="b4e55-108">根據您組織的訂閱內容，安全性儀表板包含數個小元件，例如威脅管理摘要、威脅防護狀態、全球每週威脅偵測、惡意程式碼等，如下列各節所述。</span><span class="sxs-lookup"><span data-stu-id="b4e55-108">Depending on what your organization's subscription includes, the Security Dashboard includes several widgets, such as Threat Management Summary, Threat Protection Status, Global Weekly Threat Detections, Malware, and more, as described in the following sections.</span></span>

<span data-ttu-id="b4e55-109">若要查看安全性儀表板，請在[安全性 & 合規性中心](../../compliance/go-to-the-securitycompliance-center.md)，移至 [**威脅管理**] \> **儀表板**。</span><span class="sxs-lookup"><span data-stu-id="b4e55-109">To view the Security Dashboard, in the [Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md), go to **Threat management** \> **Dashboard**.</span></span>

> [!NOTE]
> <span data-ttu-id="b4e55-110">您必須是全域系統管理員、安全性管理員或安全性讀者，才可查看安全性儀表板。</span><span class="sxs-lookup"><span data-stu-id="b4e55-110">You must be a global administrator, a security administrator, or a security reader to view the Security Dashboard.</span></span> <span data-ttu-id="b4e55-111">有些小元件需要其他許可權才能進行查看。</span><span class="sxs-lookup"><span data-stu-id="b4e55-111">Some widgets require additional permissions to view.</span></span> <span data-ttu-id="b4e55-112">若要深入瞭解，請參閱[安全性 & 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e55-112">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="threat-management-summary"></a><span data-ttu-id="b4e55-113">威脅管理摘要</span><span class="sxs-lookup"><span data-stu-id="b4e55-113">Threat Management Summary</span></span>

<span data-ttu-id="b4e55-114">「威脅管理」摘要構件會告訴您組織如何抵禦過去七天（7）天的威脅。</span><span class="sxs-lookup"><span data-stu-id="b4e55-114">The Threat Management Summary widget tells you at a glance how your organization was protected from threats over the past seven (7) days.</span></span>

![安全性儀表板-威脅管理摘要構件](../../media/SecDash-ThreatMgmtSummary.png)

<span data-ttu-id="b4e55-116">威脅管理摘要中所看到的資訊取決於您訂閱所包含的內容。</span><span class="sxs-lookup"><span data-stu-id="b4e55-116">The information you'll see in the Threat Management Summary depends on what you subscription includes.</span></span> <span data-ttu-id="b4e55-117">下表說明 Office 365 E3 和 Office 365 E5 所包含的資訊。</span><span class="sxs-lookup"><span data-stu-id="b4e55-117">The following table describes what information is included for Office 365 E3 and Office 365 E5.</span></span>

|<span data-ttu-id="b4e55-118">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="b4e55-118">Office 365 E3</span></span>|<span data-ttu-id="b4e55-119">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="b4e55-119">Office 365 E5</span></span>|
|---|---|
|<span data-ttu-id="b4e55-120">封鎖惡意程式碼郵件</span><span class="sxs-lookup"><span data-stu-id="b4e55-120">Malware messages blocked</span></span><br/><span data-ttu-id="b4e55-121">封鎖網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="b4e55-121">Phishing messages blocked</span></span><br><span data-ttu-id="b4e55-122">使用者所報告的郵件</span><span class="sxs-lookup"><span data-stu-id="b4e55-122">Messages reported by users</span></span><br><br><br><br>|<span data-ttu-id="b4e55-123">封鎖惡意程式碼郵件</span><span class="sxs-lookup"><span data-stu-id="b4e55-123">Malware messages blocked</span></span><br><span data-ttu-id="b4e55-124">封鎖網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="b4e55-124">Phishing messages blocked</span></span><br><span data-ttu-id="b4e55-125">使用者所報告的郵件</span><span class="sxs-lookup"><span data-stu-id="b4e55-125">Messages reported by users</span></span><br><span data-ttu-id="b4e55-126">已封鎖零天惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="b4e55-126">Zero-day malware blocked</span></span><br><span data-ttu-id="b4e55-127">偵測到的高級網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="b4e55-127">Advanced phishing messages detected</span></span><br><span data-ttu-id="b4e55-128">封鎖惡意 URLs</span><span class="sxs-lookup"><span data-stu-id="b4e55-128">Malicious URLs blocked</span></span>|

<span data-ttu-id="b4e55-129">若要查看或存取威脅管理摘要小工具，您必須具有查看高級威脅防護報告的許可權。</span><span class="sxs-lookup"><span data-stu-id="b4e55-129">To view or access the Threat Management Summary widget, you must have permissions to view Advanced Threat Protection reports.</span></span> <span data-ttu-id="b4e55-130">若要深入瞭解，請參閱[查看 ATP 報表所需的許可權為何？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)</span><span class="sxs-lookup"><span data-stu-id="b4e55-130">To learn more, see [What permissions are needed to view the ATP reports?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)</span></span>

## <a name="threat-protection-status"></a><span data-ttu-id="b4e55-131">威脅防護狀態</span><span class="sxs-lookup"><span data-stu-id="b4e55-131">Threat Protection Status</span></span>

<span data-ttu-id="b4e55-132">「威脅防護狀態」構件會透過網路釣魚和惡意程式碼的趨勢和詳細觀點，顯示威脅防護的有效性。</span><span class="sxs-lookup"><span data-stu-id="b4e55-132">The Threat Protection Status widget shows threat protection effectiveness with a trending and detailed view of phish and malware.</span></span>

![威脅防護狀態構件](../../media/tpswidget.png)

<span data-ttu-id="b4e55-134">詳細資料取決於您的 Microsoft 365 訂閱是否包含[Exchange Online Protection](exchange-online-protection-overview.md) （EOP），具有或沒有[Office 365 的高級威脅防護](office-365-atp.md)（ATP）。</span><span class="sxs-lookup"><span data-stu-id="b4e55-134">The details depend on whether your Microsoft 365 subscription includes [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) with or without [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP).</span></span>

|<span data-ttu-id="b4e55-135">如果您的訂閱包括 .。。</span><span class="sxs-lookup"><span data-stu-id="b4e55-135">If your subscription includes...</span></span>|<span data-ttu-id="b4e55-136">您將會看到這些詳細資料</span><span class="sxs-lookup"><span data-stu-id="b4e55-136">You'll see these details</span></span>|
|---|---|
|<span data-ttu-id="b4e55-137">EOP，但不是 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="b4e55-137">EOP but not Office 365 ATP</span></span>|<span data-ttu-id="b4e55-138">EOP 所偵測到並封鎖的惡意電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b4e55-138">Malicious email that was detected and blocked by EOP.</span></span><br><br> <span data-ttu-id="b4e55-139">請參閱[威脅防護狀態報表（EOP）](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="b4e55-139">See [Threat Protection Status report (EOP)](view-email-security-reports.md#threat-protection-status-report).</span></span>|
|<span data-ttu-id="b4e55-140">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="b4e55-140">Office 365 ATP</span></span>|<span data-ttu-id="b4e55-141">EOP 和 Office 365 ATP 偵測到並封鎖的惡意內容和惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="b4e55-141">Malicious content and malicious email detected and blocked by EOP and Office 365 ATP</span></span><br><br><span data-ttu-id="b4e55-142">反惡意程式碼引擎、[零小時自動清除](zero-hour-auto-purge.md)和 atp 功能（包括[安全連結](atp-safe-links.md)、[安全附件](atp-safe-attachments.md)及[atp 反網路釣魚](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)）封鎖的獨特電子郵件的匯總計數。</span><span class="sxs-lookup"><span data-stu-id="b4e55-142">Aggregated count of unique email messages with malicious content blocked by the anti-malware engine, [zero-hour auto purge](zero-hour-auto-purge.md), and ATP features (including [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)).</span></span><br><br><span data-ttu-id="b4e55-143">請參閱[威脅防護狀態報表（ATP）](view-reports-for-atp.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="b4e55-143">See [Threat Protection Status report (ATP)](view-reports-for-atp.md#threat-protection-status-report).</span></span>|

<span data-ttu-id="b4e55-144">若要查看或存取威脅防護狀態構件，您必須具有查看「高級威脅防護」報告的許可權。</span><span class="sxs-lookup"><span data-stu-id="b4e55-144">To view or access the Threat Protection Status widget, you must have permissions to view Advanced Threat Protection reports.</span></span> <span data-ttu-id="b4e55-145">若要深入瞭解，請參閱[查看 ATP 報表所需的許可權為何？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)</span><span class="sxs-lookup"><span data-stu-id="b4e55-145">To learn more, see [What permissions are needed to view the ATP reports?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)</span></span>

## <a name="global-weekly-threat-detections"></a><span data-ttu-id="b4e55-146">全球每週威脅偵測</span><span class="sxs-lookup"><span data-stu-id="b4e55-146">Global Weekly Threat Detections</span></span>

<span data-ttu-id="b4e55-147">「全球每週威脅偵測」構件會顯示電子郵件中偵測到超過7天的威脅數目。</span><span class="sxs-lookup"><span data-stu-id="b4e55-147">The Global Weekly Threat Detections widget shows how many threats were detected in email messages over the past seven (7) days.</span></span>

![全球每週威脅偵測小工具](../../media/globalweeklythreatdetections.png)

<span data-ttu-id="b4e55-149">度量單位如下表所述進行計算：</span><span class="sxs-lookup"><span data-stu-id="b4e55-149">The metrics are calculated as described in the following table:</span></span>

|<span data-ttu-id="b4e55-150">計量</span><span class="sxs-lookup"><span data-stu-id="b4e55-150">Metric</span></span>|<span data-ttu-id="b4e55-151">計算方式</span><span class="sxs-lookup"><span data-stu-id="b4e55-151">How it's calculated</span></span>|
|---|---|
|<span data-ttu-id="b4e55-152">掃描的郵件</span><span class="sxs-lookup"><span data-stu-id="b4e55-152">Messages scanned</span></span>|<span data-ttu-id="b4e55-153">已掃描的電子郵件數目乘以收件者數目</span><span class="sxs-lookup"><span data-stu-id="b4e55-153">Number of email messages scanned multiplied by the number of recipients</span></span>|
|<span data-ttu-id="b4e55-154">威脅已停止</span><span class="sxs-lookup"><span data-stu-id="b4e55-154">Threats stopped</span></span>|<span data-ttu-id="b4e55-155">識別為包含惡意軟體的電子郵件數目乘以收件者數目</span><span class="sxs-lookup"><span data-stu-id="b4e55-155">Number of email messages identified as containing malware multiplied by the number of recipients</span></span>|
|<span data-ttu-id="b4e55-156">由[ATP](office-365-atp.md)封鎖</span><span class="sxs-lookup"><span data-stu-id="b4e55-156">Blocked by [ATP](office-365-atp.md)</span></span>|<span data-ttu-id="b4e55-157">ATP 所封鎖的電子郵件數目乘以收件者數目</span><span class="sxs-lookup"><span data-stu-id="b4e55-157">Number of email messages blocked by ATP multiplied by the number of recipients</span></span>|
|<span data-ttu-id="b4e55-158">傳遞後移除</span><span class="sxs-lookup"><span data-stu-id="b4e55-158">Removed after delivery</span></span>|<span data-ttu-id="b4e55-159">以[零小時自動清除](zero-hour-auto-purge.md)乘以的收件者人數所移除的郵件數目</span><span class="sxs-lookup"><span data-stu-id="b4e55-159">Number of messages removed by [zero-hour auto purge](zero-hour-auto-purge.md) multiplied by the number of recipients</span></span>|

## <a name="malware"></a><span data-ttu-id="b4e55-160">惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="b4e55-160">Malware</span></span>

<span data-ttu-id="b4e55-161">惡意程式碼小元件會顯示過去七（7）天內惡意程式碼趨勢和惡意程式碼系列類型的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b4e55-161">Malware widgets show details about malware trends and malware family types over the past seven (7) days.</span></span>

![惡意程式碼趨勢及系列類型](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a><span data-ttu-id="b4e55-163">深入資訊</span><span class="sxs-lookup"><span data-stu-id="b4e55-163">Insights</span></span>

<span data-ttu-id="b4e55-164">不只是深入瞭解應該檢查的 surface key 問題，也包括要考慮的建議和動作。</span><span class="sxs-lookup"><span data-stu-id="b4e55-164">Insights not only surface key issues you should review, they also include recommendations and actions to consider.</span></span>

![Smart insights](../../media/smartinsights.png)

<span data-ttu-id="b4e55-166">例如，您可能會發現網路釣魚電子郵件已傳遞，因為某些使用者已停用其垃圾郵件選項。</span><span class="sxs-lookup"><span data-stu-id="b4e55-166">For example, you might see that phishing email messages are being delivered because some users have disabled their junk mail options.</span></span> <span data-ttu-id="b4e55-167">若要深入瞭解真知灼見的運作方式，請參閱[安全性 & 規範中心中的報告與深入](reports-and-insights-in-security-and-compliance.md)瞭解。</span><span class="sxs-lookup"><span data-stu-id="b4e55-167">To learn more about how insights work, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

## <a name="threat-investigation-and-response"></a><span data-ttu-id="b4e55-168">威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="b4e55-168">Threat investigation and response</span></span>

<span data-ttu-id="b4e55-169">如果貴組織的訂閱包含[Office 365 Advanced 威脅防護方案 2](office-365-ti.md)，則您的安全性儀表板中有一個區段，其中包含高級威脅調查和回應工具。</span><span class="sxs-lookup"><span data-stu-id="b4e55-169">If your organization's subscription includes  [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md), your Security Dashboard has a section that includes advanced threat investigation and response tools.</span></span> <span data-ttu-id="b4e55-170">這些工具組括[自動調查和回應功能](automated-investigation-response-office.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e55-170">These tools include [automated investigation and response capabilities](automated-investigation-response-office.md).</span></span> <span data-ttu-id="b4e55-171">自動調查和回應可能會非常有用，例如，[快速定址已遭破壞的使用者帳戶](address-compromised-users-quickly.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e55-171">Automated investigation and response can be helpful in scenarios such as [addressing compromised user accounts quickly](address-compromised-users-quickly.md).</span></span>

<span data-ttu-id="b4e55-172">若要深入瞭解，請參閱[開始使用 Office 365 中的自動調查和回應（AIR）](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e55-172">To learn more, see [Get started using Automated investigation and response (AIR) in Office 365](office-365-air.md).</span></span>

## <a name="trends"></a><span data-ttu-id="b4e55-173">趨勢</span><span class="sxs-lookup"><span data-stu-id="b4e55-173">Trends</span></span>

<span data-ttu-id="b4e55-174">靠近安全性儀表板底部的趨勢區段是一個**趨勢**區段，它會摘要組織的電子郵件流程趨勢。</span><span class="sxs-lookup"><span data-stu-id="b4e55-174">Near the bottom of the Security Dashboard is a **Trends** section, which summarizes email flow trends for your organization.</span></span> <span data-ttu-id="b4e55-175">報告提供有關歸類為垃圾郵件、惡意程式碼、網路釣魚企圖及良好電子郵件的電子郵件資訊。</span><span class="sxs-lookup"><span data-stu-id="b4e55-175">Reports provide information about email categorized as spam, malware, phishing attempts, and good email.</span></span> <span data-ttu-id="b4e55-176">按一下拼貼，以查看報告中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b4e55-176">Click a tile to view more detailed information in the report.</span></span>

![趨勢區段會摘要組織的電子郵件流程趨勢](../../media/trends.png)

<span data-ttu-id="b4e55-178">此外，如果貴組織的訂閱包含[Office 365 Advanced 威脅防護方案 2](office-365-ti.md)，您也會在此區段中有一個**最近的威脅管理警示**報告，讓您的安全性小組能夠查看並對高優先順序的安全性警示採取行動。</span><span class="sxs-lookup"><span data-stu-id="b4e55-178">And, if your organization's subscription includes [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md), you will also have a **Recent threat management alerts** report in this section that enables your security team to view and take action on high-priority security alerts.</span></span>

<span data-ttu-id="b4e55-179">若要查看或存取已傳送及已接收的電子郵件小工具，您必須具有查看高級威脅防護報告的許可權。</span><span class="sxs-lookup"><span data-stu-id="b4e55-179">To view or access the Sent and Received Email widget, you must have permissions to view Advanced Threat Protection reports.</span></span> <span data-ttu-id="b4e55-180">若要深入瞭解，請參閱[查看 ATP 報表所需的許可權為何？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)。</span><span class="sxs-lookup"><span data-stu-id="b4e55-180">To learn more, see [What permissions are needed to view the ATP reports?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports).</span></span>

<span data-ttu-id="b4e55-181">若要查看或存取最近的威脅管理提醒小工具，您必須具有查看提醒的許可權。</span><span class="sxs-lookup"><span data-stu-id="b4e55-181">To view or access the Recent Threat Management Alerts widget, you must have permissions to view alerts.</span></span> <span data-ttu-id="b4e55-182">若要深入瞭解，請參閱[查看提醒所需的 RBAC 許可權](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)。</span><span class="sxs-lookup"><span data-stu-id="b4e55-182">To learn more, see [RBAC permissions required to view alerts](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b4e55-183">相關主題</span><span class="sxs-lookup"><span data-stu-id="b4e55-183">Related topics</span></span>

[<span data-ttu-id="b4e55-184">檢視安全性與合規性中心內的電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="b4e55-184">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="b4e55-185">檢視 Office 365 進階威脅防護的報告</span><span class="sxs-lookup"><span data-stu-id="b4e55-185">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="b4e55-186">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="b4e55-186">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="b4e55-187">Office 365 威脅調查和回應</span><span class="sxs-lookup"><span data-stu-id="b4e55-187">Office 365 Threat investigation and response</span></span>](office-365-ti.md)
