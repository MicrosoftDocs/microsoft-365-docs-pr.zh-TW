---
title: Microsoft Defender for Office 365 的新功能
description: 深入瞭解 Microsoft Defender for Office 365 的最新版本中可用的新功能。
keywords: Office 365 atp 的新功能，ga，正式發行，可用，新功能
search.appverid: met150
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.date: 01/12/2021
ms.custom: seo-marvel-apr2020
ms.reviewer: vippand
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7dd691b0d018db2b7afb3b88a2c1f9f7f8a39a33
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51569776"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8d703-104">Microsoft Defender for Office 365 的新功能</span><span class="sxs-lookup"><span data-stu-id="8d703-104">What's new in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8d703-105">**適用於**</span><span class="sxs-lookup"><span data-stu-id="8d703-105">**Applies to**</span></span>
- [<span data-ttu-id="8d703-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="8d703-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8d703-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d703-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8d703-108">本文列出最新版本 Microsoft Defender for Office 365 的新功能。</span><span class="sxs-lookup"><span data-stu-id="8d703-108">This article lists new features in the latest release of Microsoft Defender for Office 365.</span></span> <span data-ttu-id="8d703-109">目前在預覽中的功能會以 **(預覽)** 表示。</span><span class="sxs-lookup"><span data-stu-id="8d703-109">Features that are currently in preview are denoted with **(preview)**.</span></span>

<span data-ttu-id="8d703-110">若要深入瞭解，請觀看 [這段影片](https://www.youtube.com/watch?v=Tdz6KfruDGo&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=3)。</span><span class="sxs-lookup"><span data-stu-id="8d703-110">Learn more by watching [this video](https://www.youtube.com/watch?v=Tdz6KfruDGo&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=3).</span></span>
> [!TIP]
> <span data-ttu-id="8d703-111">還沒有 Microsoft Defender for Office 365 嗎？</span><span class="sxs-lookup"><span data-stu-id="8d703-111">Don't have Microsoft Defender for Office 365 yet?</span></span> <span data-ttu-id="8d703-112">[連絡人銷售人員開始試用](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)。</span><span class="sxs-lookup"><span data-stu-id="8d703-112">[Contact sales to start a trial](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html).</span></span>

## <a name="februarymarch-2021"></a><span data-ttu-id="8d703-113">二月份/2021 年</span><span class="sxs-lookup"><span data-stu-id="8d703-113">February/March 2021</span></span> 

- <span data-ttu-id="8d703-114">在[搜尋體驗](threat-explorer.md)中使用警示識別碼及 Alert-Explorer 導覽) 進行搜尋的警示識別碼整合 (</span><span class="sxs-lookup"><span data-stu-id="8d703-114">Alert ID integration (search using Alert ID and Alert-Explorer navigation) in [hunting experiences](threat-explorer.md)</span></span>
- <span data-ttu-id="8d703-115">將[搜尋體驗](threat-explorer.md)中從9990到200000匯出記錄的限制提高</span><span class="sxs-lookup"><span data-stu-id="8d703-115">Increasing the limits for Export of records from 9990 to 200,000 in [hunting experiences](threat-explorer.md)</span></span>
- <span data-ttu-id="8d703-116">從 7 (先前的限制到[搜尋體驗](threat-explorer.md)中的30天內，擴充 Explorer (和即時的偵測) 資料保留和搜尋限制) </span><span class="sxs-lookup"><span data-stu-id="8d703-116">Extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 (previous limit) to 30 days in [hunting experiences](threat-explorer.md)</span></span>
- <span data-ttu-id="8d703-117">瀏覽器中新的搜尋功能稱為模擬的 **網域** 和模擬 **使用者** (和即時偵測) 搜尋受保護的使用者或網域的類比攻擊。</span><span class="sxs-lookup"><span data-stu-id="8d703-117">New hunting pivots called **Impersonated domain** and **Impersonated user** within the Explorer (and Real-time detections) to search for impersonation attacks against protected users or domains.</span></span> <span data-ttu-id="8d703-118">如需詳細資訊，請參閱 [詳細資料](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains)。</span><span class="sxs-lookup"><span data-stu-id="8d703-118">For more information, see [details](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains).</span></span> <span data-ttu-id="8d703-119"> (Office 365 的 Microsoft Defender 方案1或 Plan 2) </span><span class="sxs-lookup"><span data-stu-id="8d703-119">(Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>

## <a name="december-2020"></a><span data-ttu-id="8d703-120">2020 年 12 月</span><span class="sxs-lookup"><span data-stu-id="8d703-120">December 2020</span></span>

- [<span data-ttu-id="8d703-121">Office 365 中預設的安全性</span><span class="sxs-lookup"><span data-stu-id="8d703-121">Secure by default in Office 365</span></span>](secure-by-default.md)
- <span data-ttu-id="8d703-122">自動化調查改進功能：手動觸發電子郵件調查的一般提醒、將信箱變更視為個別實體類別、移除重複的 URL 封鎖動作，以及建立使用者已遭破壞調查的輸出電子郵件群集。</span><span class="sxs-lookup"><span data-stu-id="8d703-122">Automated investigation improvements to: general alerts for manually triggered email investigations, treat mailbox changes as a separate entity category, remove redundant URL block actions, and create outbound email clusters for user compromised investigations.</span></span>

## <a name="november-2020"></a><span data-ttu-id="8d703-123">2020 年 11 月</span><span class="sxs-lookup"><span data-stu-id="8d703-123">November 2020</span></span>

- <span data-ttu-id="8d703-124">更新的匯出限制 > 重要訊息中心 > 修正從郵件提交和動作記錄檔 (Defender for Office 365 方案 2) </span><span class="sxs-lookup"><span data-stu-id="8d703-124">Updated export limits in Review > Action Center > Remediation from Mail Submission and Action Log (Defender for Office 365 Plan 2)</span></span>

## <a name="septemberoctober-2020"></a><span data-ttu-id="8d703-125">2020年9月/10 月</span><span class="sxs-lookup"><span data-stu-id="8d703-125">September/October 2020</span></span>

- [<span data-ttu-id="8d703-126">使用 Configuration Analyzer 檢查您的原則</span><span class="sxs-lookup"><span data-stu-id="8d703-126">Check your policies using Configuration Analyzer</span></span>](configuration-analyzer-for-security-policies.md)
- <span data-ttu-id="8d703-127">[威脅瀏覽器中的延伸功能（包括主要目標使用者、傳輸規則，以及](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) 在 [威脅瀏覽器](threat-explorer.md) 中 (Defender for office 365 資訊） (電子郵件是由承租人/User policy)  (Defender for office 365 方案2所允許/封鎖) </span><span class="sxs-lookup"><span data-stu-id="8d703-127">[Extended capabilities in Threat Explorer including top targeted users, transport rules, and connectors](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) (Defender for Office 365 information in [Threat Explorer](threat-explorer.md) (email was allowed/blocked by tenant/user policy) (Defender for Office 365 Plan 2)</span></span>
- <span data-ttu-id="8d703-128">在 [威脅 Explorer](threat-explorer.md#threats-in-urls) 中呈現 URL 威脅 (惡意程式碼、網路釣魚、垃圾郵件或無)  (Office 365 方案2的 Defender) </span><span class="sxs-lookup"><span data-stu-id="8d703-128">Surfacing URL threats in [Threat Explorer](threat-explorer.md#threats-in-urls) (malware, phish, spam, or none) (Defender for Office 365 Plan 2)</span></span>
- <span data-ttu-id="8d703-129">[改進搜尋體驗威脅 Explorer](threat-explorer.md#improvements-to-the-threat-hunting-experience-upcoming) ，包含威脅的更新、其他動作、傳遞位置和更新的時程表視圖 (Defender for Office 365 方案 2) </span><span class="sxs-lookup"><span data-stu-id="8d703-129">[Improvements to Hunting Experience Threat Explorer](threat-explorer.md#improvements-to-the-threat-hunting-experience-upcoming) with updates around Threats, Additional Actions, Delivery locations and Updated timeline view (Defender for Office 365 Plan 2)</span></span>

## <a name="julyaugust-2020"></a><span data-ttu-id="8d703-130">2020年7月/8 月</span><span class="sxs-lookup"><span data-stu-id="8d703-130">July/August 2020</span></span>

- <span data-ttu-id="8d703-131">體驗 Microsoft Defender for Office 365 Plan 1 或 Plan 2) [的搜尋體驗改進功能的增強功能](threat-explorer.md#improvements-to-threat-hunting-experience) (</span><span class="sxs-lookup"><span data-stu-id="8d703-131">[Experience improvements to the hunting experience](threat-explorer.md#improvements-to-threat-hunting-experience) (Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>
- [<span data-ttu-id="8d703-132">使用預先設定的安全性原則輕鬆套用建議設定</span><span class="sxs-lookup"><span data-stu-id="8d703-132">Easily apply recommended settings using preset security policies</span></span>](preset-security-policies.md)

## <a name="marchapril-2020"></a><span data-ttu-id="8d703-133">2020年3月/4 月</span><span class="sxs-lookup"><span data-stu-id="8d703-133">March/April 2020</span></span>

- <span data-ttu-id="8d703-134">[使用自動調查和回應來處理已遭破壞之使用者帳戶](address-compromised-users-quickly.md)的功能現在現已提供。</span><span class="sxs-lookup"><span data-stu-id="8d703-134">The ability to [address compromised user accounts with automated investigation and response](address-compromised-users-quickly.md) is now generally available.</span></span> <span data-ttu-id="8d703-135"> (Microsoft Defender for Office 365 方案 2) </span><span class="sxs-lookup"><span data-stu-id="8d703-135">(Microsoft Defender for Office 365 Plan 2)</span></span>

## <a name="januaryfebruary-2020"></a><span data-ttu-id="8d703-136">2020年1月/2 月</span><span class="sxs-lookup"><span data-stu-id="8d703-136">January/February 2020</span></span>

- <span data-ttu-id="8d703-137">[Microsoft defender For office 365 中的即時檢視的公開可用性](campaigns.md) (microsoft Defender for Office 365 方案 2) </span><span class="sxs-lookup"><span data-stu-id="8d703-137">[General availability of Campaign Views in Microsoft Defender for Office 365](campaigns.md) (Microsoft Defender for Office 365 Plan 2)</span></span>
- <span data-ttu-id="8d703-138">[威脅瀏覽器](threat-explorer.md)的增強功能，讓安全性作業小組能夠在[調查電子郵件](investigate-malicious-email-that-was-delivered.md)時，在多個欄位上搜尋及篩選： (Microsoft Defender for Office 365 Plan 2) </span><span class="sxs-lookup"><span data-stu-id="8d703-138">Enhancements to [Threat Explorer](threat-explorer.md) to enable security operations teams to search and filter on multiple fields while [investigating email](investigate-malicious-email-that-was-delivered.md): (Microsoft Defender for Office 365 Plan 2)</span></span>
  - <span data-ttu-id="8d703-139">傳遞位置和特殊動作</span><span class="sxs-lookup"><span data-stu-id="8d703-139">Delivery location and special actions</span></span>
  - <span data-ttu-id="8d703-140">方向 (輸入、輸出或組織內) </span><span class="sxs-lookup"><span data-stu-id="8d703-140">Directionality (inbound, outbound, or intra-org)</span></span>
  - <span data-ttu-id="8d703-141">Advanced NOT 篩選 (這些是包含不包含、不包含等的高級篩選選項 ) </span><span class="sxs-lookup"><span data-stu-id="8d703-141">Advanced NOT filters (these are advanced filtering options that include does not contain, does not include, etc.)</span></span>
  - <span data-ttu-id="8d703-142">精確的時間篩選 (日、小時、半小時) </span><span class="sxs-lookup"><span data-stu-id="8d703-142">Granular time filters (day, hour, half-hour)</span></span>

- <span data-ttu-id="8d703-143">[ **事件** ] 小工具現在是「 **動作中心** 」小工具。</span><span class="sxs-lookup"><span data-stu-id="8d703-143">The **Incidents** widget is now the **Action Center** widget.</span></span> <span data-ttu-id="8d703-144"> (若要查看您的安全性小元件，請在安全性 & 規範中心中，移至「 **威脅管理**」 \>\ \*\*\**。 )  (Microsoft Defender for Office 365 方案 2) </span><span class="sxs-lookup"><span data-stu-id="8d703-144">(To view your security widgets, in the Security & Compliance Center, go to **Threat management** \> **Review**.) (Microsoft Defender for Office 365 Plan 2)</span></span>

- <span data-ttu-id="8d703-145">[Microsoft 365 中的安全檔](safe-docs.md) **(預覽)**</span><span class="sxs-lookup"><span data-stu-id="8d703-145">[Safe Documents in Microsoft 365](safe-docs.md) **(preview)**</span></span>

## <a name="december-2019"></a><span data-ttu-id="8d703-146">2019 年 12 月</span><span class="sxs-lookup"><span data-stu-id="8d703-146">December 2019</span></span>

- <span data-ttu-id="8d703-147">[匯出 URL 按一下 [資料] 以供離線分析](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) (Microsoft Defender for Office 365 Plan 1 or Plan 2) </span><span class="sxs-lookup"><span data-stu-id="8d703-147">[Export URL click data for offline analysis](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) (Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>

- <span data-ttu-id="8d703-148">[使用 Microsoft defender For office 365 中的 [市場即時檢視] (**預覽**)](campaigns.md) (Microsoft Defender for office 365 Plan 2) </span><span class="sxs-lookup"><span data-stu-id="8d703-148">[Use Campaign Views in Microsoft Defender for Office 365 (**preview**)](campaigns.md) (Microsoft Defender for Office 365 Plan 2)</span></span>

## <a name="november-2019"></a><span data-ttu-id="8d703-149">2019 年 11 月</span><span class="sxs-lookup"><span data-stu-id="8d703-149">November 2019</span></span>

- <span data-ttu-id="8d703-150">[查看新的已遭破壞的使用者偵測和回應功能](address-compromised-users-quickly.md) (**預覽**)  (Microsoft Defender for Office 365 Plan 2) </span><span class="sxs-lookup"><span data-stu-id="8d703-150">[Check out new compromised user detection and response capabilities](address-compromised-users-quickly.md) (**preview**) (Microsoft Defender for Office 365 Plan 2)</span></span>

## <a name="september-2019"></a><span data-ttu-id="8d703-151">2019 年 9 月</span><span class="sxs-lookup"><span data-stu-id="8d703-151">September 2019</span></span>

- <span data-ttu-id="8d703-152">使用 Microsoft Defender for Office 365 Plan 2 (的[自動化調查和回應功能](automated-investigation-response-office.md)) </span><span class="sxs-lookup"><span data-stu-id="8d703-152">[Employ automated investigation and response capabilities](automated-investigation-response-office.md) (Microsoft Defender for Office 365 Plan 2)</span></span>

- <span data-ttu-id="8d703-153">使用 office 365 管理活動 API （ (Defender for Office 365 Plan 2）[整合 Microsoft defender For office 365 自動化調查和回應事件](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)) </span><span class="sxs-lookup"><span data-stu-id="8d703-153">[Integrate with Microsoft Defender for Office 365 automated investigation and response events using the Office 365 Management Activity API](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) (Defender for Office 365 Plan 2)</span></span>

- <span data-ttu-id="8d703-154">[查看電子郵件頭，並下載](investigate-malicious-email-that-was-delivered.md) Microsoft Defender for Office 365 Plan 1 或 Plan 2 (的電子郵件內文) </span><span class="sxs-lookup"><span data-stu-id="8d703-154">[View the email headers and download the email body](investigate-malicious-email-that-was-delivered.md) (Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>

## <a name="august-2019"></a><span data-ttu-id="8d703-155">2019 年 8 月</span><span class="sxs-lookup"><span data-stu-id="8d703-155">August 2019</span></span>

- <span data-ttu-id="8d703-156">[查看電子郵件的時程表](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email) (Microsoft Defender for Office 365 Plan 1 or plan 2) </span><span class="sxs-lookup"><span data-stu-id="8d703-156">[View the timeline of email](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email) (Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>

## <a name="july-2019"></a><span data-ttu-id="8d703-157">2019 年 7 月</span><span class="sxs-lookup"><span data-stu-id="8d703-157">July 2019</span></span>

- <span data-ttu-id="8d703-158">[檢查電子郵件的傳遞動作和位置](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location) (Microsoft Defender for Office 365 Plan 1 or 2) </span><span class="sxs-lookup"><span data-stu-id="8d703-158">[Check the delivery action and location of email messages](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location) (Microsoft Defender for Office 365 Plan 1 or 2)</span></span>

## <a name="june-2019"></a><span data-ttu-id="8d703-159">2019 年 6 月</span><span class="sxs-lookup"><span data-stu-id="8d703-159">June 2019</span></span>

- <span data-ttu-id="8d703-160">[View 仿冒 URLs，然後按一下](threat-explorer.md#view-phishing-url-and-click-verdict-data) [ (Microsoft Defender for Office 365 方案 1] 或 [計畫 2) 的 [已判定資料]。</span><span class="sxs-lookup"><span data-stu-id="8d703-160">[View phishing URLs and click verdict data](threat-explorer.md#view-phishing-url-and-click-verdict-data) (Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a><span data-ttu-id="8d703-161">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="8d703-161">Microsoft Defender for Office 365 Plan 1 and Plan 2</span></span>

<span data-ttu-id="8d703-162">您知道 Microsoft Defender for Office 365 可提供兩種方案嗎？</span><span class="sxs-lookup"><span data-stu-id="8d703-162">Did you know that Microsoft Defender for Office 365 is available in two plans?</span></span> <span data-ttu-id="8d703-163">[深入瞭解每個方案包含的內容](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)。</span><span class="sxs-lookup"><span data-stu-id="8d703-163">[Learn more about what each plan includes](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2).</span></span>

## <a name="see-also"></a><span data-ttu-id="8d703-164">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8d703-164">See also</span></span>

[<span data-ttu-id="8d703-165">Microsoft 365 藍圖</span><span class="sxs-lookup"><span data-stu-id="8d703-165">Microsoft 365 roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap)

[<span data-ttu-id="8d703-166">Microsoft Defender for Office 365 服務說明</span><span class="sxs-lookup"><span data-stu-id="8d703-166">Microsoft Defender for Office 365 Service Description</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
