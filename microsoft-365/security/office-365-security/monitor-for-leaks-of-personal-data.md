---
title: 監視個人資料的外洩
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 了解三種您可以用來監視個人資料外洩的工具。
ms.openlocfilehash: 43133ed638f91957307b832826c21ae81aa269b0
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/28/2020
ms.locfileid: "41572970"
---
# <a name="monitor-for-leaks-of-personal-data"></a><span data-ttu-id="487b9-103">監視個人資料的外洩</span><span class="sxs-lookup"><span data-stu-id="487b9-103">Monitor for leaks of personal data</span></span>

<span data-ttu-id="487b9-p101">有許多工具，可用來監視個人資料的使用和傳輸。本主題描述三種效果不錯的工具。</span><span class="sxs-lookup"><span data-stu-id="487b9-p101">There are many tools that can be used to monitor the use and transport of personal data. This topic describes three tools that work well.</span></span>

![監視個人資料之使用及傳輸的工具](../media/Monitor-for-leaks-of-personal-data-image1.png)

<span data-ttu-id="487b9-107">在此圖例中：</span><span class="sxs-lookup"><span data-stu-id="487b9-107">In the illustration:</span></span>

- <span data-ttu-id="487b9-p102">從 Office 365 資料外洩防護報告開始，這些報告用於監視 SharePoint Online、商務用 OneDrive 和傳輸中電子郵件中的個人資料。這些提供監視個人資料時的最大詳細資料層級。不過，這類報告不包含 Office 365 中的所有服務。</span><span class="sxs-lookup"><span data-stu-id="487b9-p102">Start with Office 365 data loss prevention reports for monitoring personal data in SharePoint Online, OneDrive for Business, and email in transit. These provide the greatest level of detail for monitoring personal data. However, these reports don’t include all services in Office 365.</span></span>

- <span data-ttu-id="487b9-p103">接下來，使用警示和 Office 365 稽核記錄，以監視整個 Office 365 服務的活動。設定持續監視，或搜尋稽核記錄以調查事件。Office 365 稽核記錄適用於整個 Office 365 服務 — Sway、PowerBI、eDiscovery、Dynamics 365、Microsoft Flow’Microsoft Teams、Admin activity、OneDrive for Business、SharePoint Online、傳輸中郵件，以及靜態信箱。靜態信箱包括 Skype 交談。</span><span class="sxs-lookup"><span data-stu-id="487b9-p103">Next, use alert policies and the Office 365 audit log to monitor activity across Office 365 services. Setup ongoing monitoring or search the audit log to investigate an incident. The Office 365 audit log works across Office 365 services — Sway, PowerBI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, Admin activity, OneDrive for Business, SharePoint Online, mail in transit, and mailboxes at rest. Skype conversations are included in mailboxes at rest.</span></span>

- <span data-ttu-id="487b9-p104">最後，使用 Microsoft Cloud App Security 監視其他 SaaS 提供者中具有敏感資料的檔案。即將能夠在 Azure 資訊保護和具有 Cloud App Security 的 Office 之間使用 Office 365 敏感資訊類型和統一標籤。您可以設定適用於所有 SaaS 應用程式或特定應用程式 (例如 Box) 的原則。Cloud App Security 不會探索 Exchange 中的檔案，包括電子郵件的附加檔案。</span><span class="sxs-lookup"><span data-stu-id="487b9-p104">Finally, Use Microsoft Cloud App Security to monitor files with sensitive data in other SaaS providers. Coming soon is the ability to use Office 365 sensitive information types and unified labels across Azure Information Protection and Office with Cloud App Security. You can setup policies that apply to all of your SaaS apps or specific apps (like Box). Cloud App Security doesn’t discover files in Exchange Online, including files attached to email.</span></span>

## <a name="office-365-data-loss-prevention-reports"></a><span data-ttu-id="487b9-119">Office 365 資料外洩防護報告</span><span class="sxs-lookup"><span data-stu-id="487b9-119">Office 365 data loss prevention reports</span></span>

<span data-ttu-id="487b9-p105">建立資料外洩防護 (DLP) 原則之後，您會想要確認原則是否達到您想要的效果並協助您符合規範。使用 Office 365 中的 DLP 報告，您可以快速檢視 DLP 原則及規則相符、覆寫及誤判的數量、查看它們是否會隨時間而有趨勢上揚或下降的變化、以不同方式篩選報告，以及選取圖形上線條的點來檢視其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="487b9-p105">After you create your data loss prevention (DLP) policies, you’ll want to verify that they’re working as you intended and helping you to stay compliant. With the DLP reports in Office 365, you can quickly view the number of DLP policy matches, overrides, or false positives; see whether they’re trending up or down over time; filter the report in different ways; and view additional details by selecting a point on a line on the graph.</span></span>

<span data-ttu-id="487b9-122">您可以將 DLP 用於：</span><span class="sxs-lookup"><span data-stu-id="487b9-122">You can use the DLP reports to:</span></span>

- <span data-ttu-id="487b9-123">將重點放在特定時段，以了解尖峰和趨勢的原因。</span><span class="sxs-lookup"><span data-stu-id="487b9-123">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>

- <span data-ttu-id="487b9-124">探索違反貴組織 DLP 原則的商務程序。</span><span class="sxs-lookup"><span data-stu-id="487b9-124">Discover business processes that violate your organization’s DLP policies.</span></span>

- <span data-ttu-id="487b9-125">了解 DLP 原則帶來的任何業務影響。</span><span class="sxs-lookup"><span data-stu-id="487b9-125">Understand any business impact of the DLP policies.</span></span>

- <span data-ttu-id="487b9-126">檢視當使用者藉由覆寫原則，或報告誤判以解析原則秘訣時，他們所提交的理由。</span><span class="sxs-lookup"><span data-stu-id="487b9-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy or reporting a false positive.</span></span>

- <span data-ttu-id="487b9-127">顯示該原則的任何符合項目來驗證是否符合特定 DLP 原則的規範。</span><span class="sxs-lookup"><span data-stu-id="487b9-127">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>

- <span data-ttu-id="487b9-128">檢視檔案清單，其中的敏感性資料符合詳細資料窗格中的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="487b9-128">View a list of files with sensitive data that matches your DLP policies in the details pane.</span></span>

<span data-ttu-id="487b9-129">此外，在測試模式下執行 DLP 原則時，您可以使用 DLP 報告來微調這些原則。</span><span class="sxs-lookup"><span data-stu-id="487b9-129">In addition, you can use the DLP reports to fine tune your DLP policies as you run them in test mode.</span></span>

<span data-ttu-id="487b9-130">DLP 報告位於安全性中心和合規性中心。</span><span class="sxs-lookup"><span data-stu-id="487b9-130">DLP reports are in the security center and the compliance center.</span></span> <span data-ttu-id="487b9-131">瀏覽至 [報告] \> [檢視報告]。</span><span class="sxs-lookup"><span data-stu-id="487b9-131">Navigate to Reports \> View reports.</span></span> <span data-ttu-id="487b9-132">在 [資料外洩防護 (DLP)] 下，移至 [DLP 原則和規則相符項目] 或 [DLP 誤判和覆寫]。</span><span class="sxs-lookup"><span data-stu-id="487b9-132">Under Data loss prevention (DLP), go to either DLP policy and rule matches or DLP false positives and overrides.</span></span>

<span data-ttu-id="487b9-133">如需詳細資訊，請參閱[檢視資料外洩防護的報告](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)。</span><span class="sxs-lookup"><span data-stu-id="487b9-133">For more information, see [View the reports for data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).</span></span>

![顯示 DLP 原則比對的報告](../media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="office-365-audit-log-and-alert-policies"></a><span data-ttu-id="487b9-135">Office 365 稽核記錄和警示原則</span><span class="sxs-lookup"><span data-stu-id="487b9-135">Office 365 audit log and alert policies</span></span>

<span data-ttu-id="487b9-136">Office 365 稽核記錄包含的事件來自 Exchange Online、SharePoint Online、商務用 OneDrive、Azure Active Directory、Microsoft Teams’Power BI、Sway，以及其他 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="487b9-136">The Office 365 audit log contains events from Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway, and other Office 365 services.</span></span>

<span data-ttu-id="487b9-137">安全性中心和合規性中心提供兩種方法來監視及報告 Office 365 稽核記錄：</span><span class="sxs-lookup"><span data-stu-id="487b9-137">The security center and compliance center provide two ways to monitor and report against the Office 365 audit log:</span></span>

- <span data-ttu-id="487b9-138">設定警示原則、檢視警示和監視趨勢 — 使用安全性中心或合規性中心中的警示原則和警示儀表板工具。</span><span class="sxs-lookup"><span data-stu-id="487b9-138">Setup alert policies, view alerts, and monitor trends — Use the alert policy and alert dashboard tools in either the security center or compliance center.</span></span>

- <span data-ttu-id="487b9-p107">直接搜尋稽核記錄 — 搜尋指定日期範圍的所有事件。或者，根據特定準則 (例如執行動作的使用者、動作或目標物件) 篩選結果。</span><span class="sxs-lookup"><span data-stu-id="487b9-p107">Search the audit log directly — Search for all events in a specified date rage. Or you can filter the results based on specific criteria, such as the user who performed the action, the action, or the target object.</span></span>

<span data-ttu-id="487b9-p108">資訊安全與規範小組可以使用這些工具，主動檢閱使用者和系統管理員在 Office 365 服務之間執行的活動。您可以設定自動警示，在特定網站集合上發生特定活動時傳送電子郵件通知 - 例如，從已知包含 GDPR 相關資訊的網站共用內容時。這可讓那些小組追蹤使用者，以確保他們遵循公司安全性原則，或是提供其他訓練。</span><span class="sxs-lookup"><span data-stu-id="487b9-p108">Information security and compliance teams can use these tools to proactively review activities performed by both end users and administrators across Office 365 services. Automatic alerts can be configured to send email notifications when certain activities occur on specific site collections - for example when content is shared from sites known to contain GDPR related information. This allows those teams to follow up with users to ensure that corporate security policies are followed, or to provide additional training.</span></span>

<span data-ttu-id="487b9-p109">資訊安全小組也可以搜尋稽核記錄，以調查可疑的資料外洩，並判斷根本原因，以及外洩範圍。此內建功能有助於遵循 GDPR 的第 33 條和第 34 條，這需要在特定時段內將資料外洩通知 GDPR 監理局和資料主體本身。稽核記錄項目只會在服務內保留 90 天 - 通常這是建議的天數，但許多組織需要這些記錄保留更長的一段時間。</span><span class="sxs-lookup"><span data-stu-id="487b9-p109">Information security teams can also search the audit log to investigate suspected data breaches and determine both root cause and the extent of the breach. This built in capability facilitates compliance with article 33 and 34 of the GDPR, which require notifications be provided to the GDPR supervisory authority and to the data subjects themselves of a data breach within a specific time period. Audit log entries are only retained for 90 days within the service - it is often recommended and many organizations required that these logs be retained for longer periods of time.</span></span>

<span data-ttu-id="487b9-p110">可用的解決方案透過 Microsoft Management Activity API 訂閱統一的稽核記錄，同時可以視需要儲存記錄項目，並提供進階儀表板和警示。範例有 [Microsoft Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-office-365)。</span><span class="sxs-lookup"><span data-stu-id="487b9-p110">Solutions are available which subscribe to the Unified Audit Logs through the Microsoft Management Activity API and can both store log entries as needed, and provide advanced dashboards and alerts. One example is [Microsoft Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-office-365).</span></span>

<span data-ttu-id="487b9-149">警示原則和搜尋稽核記錄的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="487b9-149">More information about alert policies and searching the audit log:</span></span>

- [<span data-ttu-id="487b9-150">Microsoft 365 安全性與合規性中心的警示原則</span><span class="sxs-lookup"><span data-stu-id="487b9-150">Alert policies in the Microsoft 365 security and compliance centers</span></span>](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)

- <span data-ttu-id="487b9-151">[搜尋稽核記錄以取得 Office 365 中的使用者和系統管理員活動](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log) (簡介)</span><span class="sxs-lookup"><span data-stu-id="487b9-151">[Search the audit log for user and admin activity in Office 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log) (introduction)</span></span>

- [<span data-ttu-id="487b9-152">開啟或關閉 Office 365 稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="487b9-152">Turn Office 365 audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

- [<span data-ttu-id="487b9-153">搜尋稽核記錄</span><span class="sxs-lookup"><span data-stu-id="487b9-153">Search the audit log</span></span>](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

- <span data-ttu-id="487b9-154">[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) (Cmdlet)</span><span class="sxs-lookup"><span data-stu-id="487b9-154">[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) (cmdlet)</span></span>

- [<span data-ttu-id="487b9-155">Office 365 稽核記錄中的詳細內容</span><span class="sxs-lookup"><span data-stu-id="487b9-155">Detailed properties in the Office 365 audit log</span></span>](https://docs.microsoft.com/microsoft-365/compliance/detailed-properties-in-the-office-365-audit-log)

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="487b9-156">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="487b9-156">Microsoft Cloud App Security</span></span>

<span data-ttu-id="487b9-157">Microsoft Cloud App Security 可協助您探索在您的網路中使用的其他 SaaS 應用程式，以及在這些應用程式之間來回傳送的敏感資料。</span><span class="sxs-lookup"><span data-stu-id="487b9-157">Microsoft Cloud App Security helps you discover other SaaS apps in use across your networks and sensitive data that is sent to and from these apps.</span></span>

<span data-ttu-id="487b9-p111">Microsoft Cloud App Security 是一種全方位服務，可為您的雲端應用程式提供深入的可見性、細微控制和增強的威脅防護。它可從您網絡中的所有裝置識別出超過 15,000 個雲端應用程式，並提供風險評分和持續風險評估與分析。無需代理程式：從防火牆和 Proxy 收集資訊，為您提供雲端使用和影子 IT 的完整可見性和內容。</span><span class="sxs-lookup"><span data-stu-id="487b9-p111">Microsoft Cloud App Security is a comprehensive service providing deep visibility, granular controls and enhanced threat protection for your cloud apps. It identifies more than 15,000 cloud applications in your network-from all devices-and provides risk scoring and ongoing risk assessment and analytics. No agents required: information is collected from your firewalls and proxies to give you complete visibility and context for cloud usage and shadow IT.</span></span>

<span data-ttu-id="487b9-p112">為了更好地了解您的雲端環境，Cloud App Security 的調查功能可讓您深入了解所有獲批准和受管理應用程式的活動、文件和帳戶。您可以獲取檔案層級的詳細資訊，並探索資料在雲端應用程式中的傳輸位置。</span><span class="sxs-lookup"><span data-stu-id="487b9-p112">To better understand your cloud environment, Cloud App Security investigate feature provides deep visibility into all activities, files and accounts for sanctioned and managed apps. You can gain detailed information on a file level and discover where data travels in the cloud apps.</span></span>

<span data-ttu-id="487b9-163">例如，下圖示範兩個可協助 GDPR 的 Cloud App Security 原則。</span><span class="sxs-lookup"><span data-stu-id="487b9-163">For examples, the following illustration demonstrates two Cloud App Security policies that can help with GDPR.</span></span>

![Cloud App Security 原則範例](../media/Monitor-for-leaks-of-personal-data-image3.png)

<span data-ttu-id="487b9-165">當具有預先定義的 PII 屬性或您選擇的自訂運算式的檔案，在組織外從您選擇的 SaaS 應用程式共用時，第一個原則會發出警示。</span><span class="sxs-lookup"><span data-stu-id="487b9-165">The first policy alerts when files with a predefined PII attribute or custom expression that you choose is shared outside the organization from the SaaS apps that you choose.</span></span>

<span data-ttu-id="487b9-p113">第二個原則會禁止將檔案至任何未受管理的裝置。您可以選擇檔案內要尋找的屬性，以及要套用原則的 SaaS 應用程式。</span><span class="sxs-lookup"><span data-stu-id="487b9-p113">The second policy blocks downloads of files to any unmanaged device. You choose the attributes within the files to look for and the SaaS apps you want the policy to apply to.</span></span>

<span data-ttu-id="487b9-168">這些屬性類型即將在 Cloud App Security 推出：</span><span class="sxs-lookup"><span data-stu-id="487b9-168">These attribute types are coming soon to Cloud App Security:</span></span>

- <span data-ttu-id="487b9-169">Office 365 敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="487b9-169">Office 365 sensitive information types</span></span>

- <span data-ttu-id="487b9-170">Office 365 與 Azure 資訊保護之間的統一標籤</span><span class="sxs-lookup"><span data-stu-id="487b9-170">Unified labels across Office 365 and Azure Information Protection</span></span>

### <a name="cloud-app-security-dashboard"></a><span data-ttu-id="487b9-171">Cloud App Security 儀表板</span><span class="sxs-lookup"><span data-stu-id="487b9-171">Cloud App Security dashboard</span></span>

<span data-ttu-id="487b9-p114">如果您還沒開始使用 Cloud App Security，請先將其啟動。若要存取 Cloud App Security：<https://portal.cloudappsecurity.com>。</span><span class="sxs-lookup"><span data-stu-id="487b9-p114">If you haven’t yet started to use Cloud App Security, begin by starting it up. To access Cloud App Security: <https://portal.cloudappsecurity.com>.</span></span>

<span data-ttu-id="487b9-p115">附註：當開始使用 Cloud App Security 時，或在您指派標籤之前，請務必啟用 [自動掃描 Azure 資訊保護分類標籤的檔案] (在 [一般] 設定中)。設定後，Cloud App Security 不會重新掃描現有檔案，直到修改了它們。</span><span class="sxs-lookup"><span data-stu-id="487b9-p115">Note: Be sure to enable ‘Automatically scan files for Azure Information Protection classification labels’ (in General settings) when getting started with Cloud App Security or before you assign labels. After setup, Cloud App Security does not scan existing files again until they are modified.</span></span>

![顯示警示相關資訊的儀表板](../media/Monitor-for-leaks-of-personal-data-image4.png)

<span data-ttu-id="487b9-177">詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="487b9-177">More information:</span></span>

- [<span data-ttu-id="487b9-178">部署 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="487b9-178">Deploy Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [<span data-ttu-id="487b9-179">Microsoft Cloud App Security 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="487b9-179">More information about Microsoft Cloud App Security</span></span>](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [<span data-ttu-id="487b9-180">禁止使用 Microsoft Cloud App Security Proxy 下載敏感資訊</span><span class="sxs-lookup"><span data-stu-id="487b9-180">Block downloads of sensitive information using the Microsoft Cloud App Security proxy</span></span>](https://docs.microsoft.com/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a><span data-ttu-id="487b9-181">範例檔案以及偵測個人資料共用的活動原則</span><span class="sxs-lookup"><span data-stu-id="487b9-181">Example file and activity policies to detect sharing of personal data</span></span>

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a><span data-ttu-id="487b9-182">偵測包含 PII 之檔案的共用 — 信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="487b9-182">Detect sharing of files containing PII — Credit card number</span></span>

<span data-ttu-id="487b9-183">從核准的雲端應用程式共用包含信用卡號碼的檔案時發出警示。</span><span class="sxs-lookup"><span data-stu-id="487b9-183">Alert when a file containing a credit card number is shared from an approved cloud app.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="487b9-184"><strong>控制</strong></span><span class="sxs-lookup"><span data-stu-id="487b9-184"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="487b9-185"><strong>設定</strong></span><span class="sxs-lookup"><span data-stu-id="487b9-185"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="487b9-186">原則類型</span><span class="sxs-lookup"><span data-stu-id="487b9-186">Policy type</span></span></td>
<td align="left"><span data-ttu-id="487b9-187">檔案原則</span><span class="sxs-lookup"><span data-stu-id="487b9-187">File policy</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="487b9-188">原則範本</span><span class="sxs-lookup"><span data-stu-id="487b9-188">Policy template</span></span></td>
<td align="left"><span data-ttu-id="487b9-189">無範本</span><span class="sxs-lookup"><span data-stu-id="487b9-189">No template</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="487b9-190">原則重要性</span><span class="sxs-lookup"><span data-stu-id="487b9-190">Policy severity</span></span></td>
<td align="left"><span data-ttu-id="487b9-191">高</span><span class="sxs-lookup"><span data-stu-id="487b9-191">High</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="487b9-192">類別</span><span class="sxs-lookup"><span data-stu-id="487b9-192">Category</span></span></td>
<td align="left"><span data-ttu-id="487b9-193">DLP</span><span class="sxs-lookup"><span data-stu-id="487b9-193">DLP</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="487b9-194">篩選器設定</span><span class="sxs-lookup"><span data-stu-id="487b9-194">Filter settings</span></span></td>
<td align="left"><p><span data-ttu-id="487b9-195">存取層級 = 公用 (網際網路)、公用、外部</span><span class="sxs-lookup"><span data-stu-id="487b9-195">Access level = Public (Internet), Public, External</span></span></p>
<p><span data-ttu-id="487b9-196">App = &lt;select apps&gt; (如果想要限制對特定 SaaS 應用程式的監視，請使用此設定)</span><span class="sxs-lookup"><span data-stu-id="487b9-196">App = &lt;select apps&gt; (use this setting if you want to limit monitoring to specific SaaS apps)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="487b9-197">套用到</span><span class="sxs-lookup"><span data-stu-id="487b9-197">Apply to</span></span></td>
<td align="left"><span data-ttu-id="487b9-198">所有檔案，所有擁有者</span><span class="sxs-lookup"><span data-stu-id="487b9-198">All files, all owners</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="487b9-199">內容檢查</span><span class="sxs-lookup"><span data-stu-id="487b9-199">Content inspection</span></span></td>
<td align="left"><p><span data-ttu-id="487b9-200">包含符合當前運算式的檔案：所有國家/地區、金融、信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="487b9-200">Includes files that match a present expression: All countries: Finance: Credit card number</span></span></p>
<p><span data-ttu-id="487b9-201">不需要相關內容：已取消核取 (這會比對關鍵字，以及 regex)</span><span class="sxs-lookup"><span data-stu-id="487b9-201">Don’t require relevant context: unchecked (this will match keywords as well as regex)</span></span></p>
<p><span data-ttu-id="487b9-202">包含至少有 1 個相符項目的檔案</span><span class="sxs-lookup"><span data-stu-id="487b9-202">Includes files with at least 1 match</span></span></p>
<p><span data-ttu-id="487b9-203">取消遮罩違規的最後 4 個字元：已核取</span><span class="sxs-lookup"><span data-stu-id="487b9-203">Unmask the last 4 characters of the violation: checked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="487b9-204">警示</span><span class="sxs-lookup"><span data-stu-id="487b9-204">Alerts</span></span></td>
<td align="left"><p><span data-ttu-id="487b9-205">建立每個相符檔案的警示：已核取</span><span class="sxs-lookup"><span data-stu-id="487b9-205">Create an alert for each matching file: checked</span></span></p>
<p><span data-ttu-id="487b9-206">每日警示限制：1000</span><span class="sxs-lookup"><span data-stu-id="487b9-206">Daily alert limit: 1000</span></span></p>
<p><span data-ttu-id="487b9-207">選取警示做為電子郵件：已核取</span><span class="sxs-lookup"><span data-stu-id="487b9-207">Select an alert as email: checked</span></span></p>
<p><span data-ttu-id="487b9-208">收件人：infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="487b9-208">To: infosec@contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="487b9-209">治理</span><span class="sxs-lookup"><span data-stu-id="487b9-209">Governance</span></span></td>
<td align="left"><p><span data-ttu-id="487b9-210">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="487b9-210">Microsoft OneDrive for Business</span></span></p>
<p><span data-ttu-id="487b9-211">專用： 核取 [移除外部使用者]</span><span class="sxs-lookup"><span data-stu-id="487b9-211">Make private: check Remove External Users</span></span></p>
<p><span data-ttu-id="487b9-212">所有其他設定：已取消核取</span><span class="sxs-lookup"><span data-stu-id="487b9-212">All other settings: unchecked</span></span></p>
<p><span data-ttu-id="487b9-213">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="487b9-213">Microsoft SharePoint Online</span></span></p>
<p><span data-ttu-id="487b9-214">專用： 核取 [移除外部使用者]</span><span class="sxs-lookup"><span data-stu-id="487b9-214">Make private: check Remove External Users</span></span></p>
<p><span data-ttu-id="487b9-215">所有其他設定：已取消核取</span><span class="sxs-lookup"><span data-stu-id="487b9-215">All other settings: unchecked</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="487b9-216">類似原則：</span><span class="sxs-lookup"><span data-stu-id="487b9-216">Similar policies:</span></span>

- <span data-ttu-id="487b9-217">偵測包含 PII 之檔案的共用 — 電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="487b9-217">Detect sharing of Files containing PII - Email Address</span></span>

- <span data-ttu-id="487b9-218">偵測包含 PII 之檔案的共用 — 護照號碼</span><span class="sxs-lookup"><span data-stu-id="487b9-218">Detect sharing of Files containing PII - Passport Number</span></span>

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a><span data-ttu-id="487b9-219">偵測 Box 或商務用 OneDrive 中的客戶或 HR 資料</span><span class="sxs-lookup"><span data-stu-id="487b9-219">Detect Customer or HR Data in Box or OneDrive for Business</span></span>

<span data-ttu-id="487b9-220">當標示為「客戶資料或 HR 資料」的檔案上傳至商務用 OneDrive 或 Box 時發出警示。</span><span class="sxs-lookup"><span data-stu-id="487b9-220">Alert when a file labeled as Customer Data or HR Data is uploaded to OneDrive for Business or Box.</span></span>

<span data-ttu-id="487b9-221">附註：</span><span class="sxs-lookup"><span data-stu-id="487b9-221">Notes:</span></span>

- <span data-ttu-id="487b9-222">Box 監視需要您使用 API 連接器 SDK 設定連接器。</span><span class="sxs-lookup"><span data-stu-id="487b9-222">Box monitoring requires a connector be configured using the API Connector SDK.</span></span>

- <span data-ttu-id="487b9-223">此原則需要目前處於私人預覽的功能。</span><span class="sxs-lookup"><span data-stu-id="487b9-223">This policy requires capabilities that are currently in private preview.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="487b9-224"><strong>控制</strong></span><span class="sxs-lookup"><span data-stu-id="487b9-224"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="487b9-225"><strong>設定</strong></span><span class="sxs-lookup"><span data-stu-id="487b9-225"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="487b9-226">原則類型</span><span class="sxs-lookup"><span data-stu-id="487b9-226">Policy type</span></span></td>
<td align="left"><span data-ttu-id="487b9-227">活動原則</span><span class="sxs-lookup"><span data-stu-id="487b9-227">Activity policy</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="487b9-228">原則範本</span><span class="sxs-lookup"><span data-stu-id="487b9-228">Policy template</span></span></td>
<td align="left"><span data-ttu-id="487b9-229">無範本</span><span class="sxs-lookup"><span data-stu-id="487b9-229">No template</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="487b9-230">原則重要性</span><span class="sxs-lookup"><span data-stu-id="487b9-230">Policy severity</span></span></td>
<td align="left"><span data-ttu-id="487b9-231">高</span><span class="sxs-lookup"><span data-stu-id="487b9-231">High</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="487b9-232">類別</span><span class="sxs-lookup"><span data-stu-id="487b9-232">Category</span></span></td>
<td align="left"><span data-ttu-id="487b9-233">共用控制項</span><span class="sxs-lookup"><span data-stu-id="487b9-233">Sharing Control</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="487b9-234">採取行動</span><span class="sxs-lookup"><span data-stu-id="487b9-234">Act on</span></span></td>
<td align="left"><span data-ttu-id="487b9-235">單一活動</span><span class="sxs-lookup"><span data-stu-id="487b9-235">Single activity</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="487b9-236">篩選器設定</span><span class="sxs-lookup"><span data-stu-id="487b9-236">Filter settings</span></span></td>
<td align="left"><p><span data-ttu-id="487b9-237">活動類型 = 上傳檔案</span><span class="sxs-lookup"><span data-stu-id="487b9-237">Activity type = Upload File</span></span></p>
<p><span data-ttu-id="487b9-238">應用程式 = Microsoft OneDrive for Business 和 Box</span><span class="sxs-lookup"><span data-stu-id="487b9-238">App = Microsoft OneDrive for Business and Box</span></span></p>
<p><span data-ttu-id="487b9-239">分類標籤 (目前處於私人預覽)：Azure 資訊保護 = 客戶資料、人力資源—薪資資料、人力資源—員工資料</span><span class="sxs-lookup"><span data-stu-id="487b9-239">Classification Label (currently in private preview): Azure Information Protection = Customer Data, Human Resources—Salary Data, Human Resources—Employee Data</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="487b9-240">警示</span><span class="sxs-lookup"><span data-stu-id="487b9-240">Alerts</span></span></td>
<td align="left"><p><span data-ttu-id="487b9-241">建立警示：已核取</span><span class="sxs-lookup"><span data-stu-id="487b9-241">Create an alert: checked</span></span></p>
<p><span data-ttu-id="487b9-242">每日警示限制：1000</span><span class="sxs-lookup"><span data-stu-id="487b9-242">Daily alert limit: 1000</span></span></p>
<p><span data-ttu-id="487b9-243">選取警示做為電子郵件：已核取</span><span class="sxs-lookup"><span data-stu-id="487b9-243">Select an alert as email: checked</span></span></p>
<p><span data-ttu-id="487b9-244">收件人：infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="487b9-244">To: infosec@contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="487b9-245">治理</span><span class="sxs-lookup"><span data-stu-id="487b9-245">Governance</span></span></td>
<td align="left"><p><span data-ttu-id="487b9-246">所有應用程式</span><span class="sxs-lookup"><span data-stu-id="487b9-246">All apps</span></span></p>
<p><span data-ttu-id="487b9-247">將使用者隔離：已核取</span><span class="sxs-lookup"><span data-stu-id="487b9-247">Put user in quarantine: check</span></span></p>
<p><span data-ttu-id="487b9-248">所有其他設定：已取消核取</span><span class="sxs-lookup"><span data-stu-id="487b9-248">All other settings: unchecked</span></span></p>
<p><span data-ttu-id="487b9-249">Office 365</span><span class="sxs-lookup"><span data-stu-id="487b9-249">Office 365</span></span></p>
<p><span data-ttu-id="487b9-250">將使用者隔離：已核取</span><span class="sxs-lookup"><span data-stu-id="487b9-250">Put user in quarantine: check</span></span></p>
<p><span data-ttu-id="487b9-251">所有其他設定：已取消核取</span><span class="sxs-lookup"><span data-stu-id="487b9-251">All other settings: unchecked</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="487b9-252">類似原則：</span><span class="sxs-lookup"><span data-stu-id="487b9-252">Similar policies:</span></span>

- <span data-ttu-id="487b9-253">偵測客戶資料或 HR 資料的大量下載 — 當偵測到單一使用者在短時間內下載大量包含客戶資料或 HR 資料的檔案時發出警示。</span><span class="sxs-lookup"><span data-stu-id="487b9-253">Detect large downloads of Customer data or HR Data — Alert when a large number of files containing customer data or HR data have been detected being downloaded by a single user within a short period of time.</span></span>

- <span data-ttu-id="487b9-254">偵測客戶和 HR 資料的共用 — 當包含客戶或 HR 資料的檔案共用時發出警示。</span><span class="sxs-lookup"><span data-stu-id="487b9-254">Detect Sharing of Customer and HR Data — Alert when files containing Customer or HR Data are shared.</span></span>
