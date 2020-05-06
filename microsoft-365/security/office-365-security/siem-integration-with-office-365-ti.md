---
title: SIEM 與高級威脅防護的整合
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 11/22/2019
ms.collection:
- M365-security-compliance
description: 將組織的 SIEM 伺服器與 office 365 的高級威脅防護和相關威脅事件，與 Office 365 活動管理 API 整合。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0527a998e7049960df840c7756ef5deaafaf5ade
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035269"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="ee9c7-103">SIEM 與高級威脅防護的整合</span><span class="sxs-lookup"><span data-stu-id="ee9c7-103">SIEM integration with Advanced Threat Protection</span></span>

<span data-ttu-id="ee9c7-104">如果您的組織使用安全性事件和事件管理（SIEM）伺服器，您可以將 Office 365 的高級威脅防護與您的 SIEM 伺服器整合。</span><span class="sxs-lookup"><span data-stu-id="ee9c7-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="ee9c7-105">SIEM 整合可讓您在 SIEM 伺服器報告中查看 Office 365 Advanced Protection 偵測到的惡意程式碼或網路釣魚資訊（例如惡意程式碼或網路釣魚）。</span><span class="sxs-lookup"><span data-stu-id="ee9c7-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="ee9c7-106">若要設定 SIEM 整合，您可以使用[Office 365 活動管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="ee9c7-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="ee9c7-107">Office 365 活動管理 API 會從您組織的 Microsoft 365 for business 和 Azure Active Directory 活動記錄檔中，檢索使用者、系統管理、系統及原則動作和事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ee9c7-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 for business and Azure Active Directory activity logs.</span></span> <span data-ttu-id="ee9c7-108">[Office 365 Advanced 威脅防護架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)使用高級威脅防護功能，因此如果您的組織有 Office 365 高級威脅防護方案1或 Plan 2 或 Office 365 E5，您仍然可以使用該相同 API 進行 SIEM server 整合。</span><span class="sxs-lookup"><span data-stu-id="ee9c7-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="ee9c7-109">做為我們最近的更新的一部分，我們也新增了一些事件，來自于 office 365 管理活動 API 內，Office 365 ATP 方案2中自動調查和回應功能的事件。</span><span class="sxs-lookup"><span data-stu-id="ee9c7-109">As part of our recent updates, we have also added events from automated investigation and response capabilities in Office 365 ATP Plan 2 within the Office 365 Management Activity API.</span></span> <span data-ttu-id="ee9c7-110">除了包含有關核心調查詳細資料（例如識別碼、名稱及狀態）的資料之外，它還包含有關調查動作和實體的高層級資訊。</span><span class="sxs-lookup"><span data-stu-id="ee9c7-110">In addition to including data about core investigation details such as ID, name and status, it also contains high-level information about investigation actions and entities.</span></span>   

<span data-ttu-id="ee9c7-111">SIEM server 或其他類似系統應輪詢此**審核。一般**工作負載來存取偵測事件。</span><span class="sxs-lookup"><span data-stu-id="ee9c7-111">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="ee9c7-112">若要深入瞭解，請參閱[開始使用 Office 365 管理 APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="ee9c7-112">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="ee9c7-113">此外，下列**AuditLogRecordType**值是與 OFFICE 365 ATP 事件相關的：</span><span class="sxs-lookup"><span data-stu-id="ee9c7-113">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="ee9c7-114">列舉： AuditLogRecordType-類型： Edm</span><span class="sxs-lookup"><span data-stu-id="ee9c7-114">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="ee9c7-115">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="ee9c7-115">AuditLogRecordType</span></span>

|<span data-ttu-id="ee9c7-116">值</span><span class="sxs-lookup"><span data-stu-id="ee9c7-116">Value</span></span>|<span data-ttu-id="ee9c7-117">成員名稱</span><span class="sxs-lookup"><span data-stu-id="ee9c7-117">Member name</span></span>|<span data-ttu-id="ee9c7-118">描述</span><span class="sxs-lookup"><span data-stu-id="ee9c7-118">Description</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ee9c7-119">日</span><span class="sxs-lookup"><span data-stu-id="ee9c7-119">28</span></span>|<span data-ttu-id="ee9c7-120">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="ee9c7-120">ThreatIntelligence</span></span>|<span data-ttu-id="ee9c7-121">來自 Exchange Online Protection 和 Office 365 高級威脅防護的網路釣魚和惡意程式碼事件。</span><span class="sxs-lookup"><span data-stu-id="ee9c7-121">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="ee9c7-122">41</span><span class="sxs-lookup"><span data-stu-id="ee9c7-122">41</span></span>|<span data-ttu-id="ee9c7-123">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="ee9c7-123">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="ee9c7-124">ATP 安全連結從 Office 365 高級威脅防護的封鎖時間和封鎖覆寫事件。</span><span class="sxs-lookup"><span data-stu-id="ee9c7-124">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="ee9c7-125">47</span><span class="sxs-lookup"><span data-stu-id="ee9c7-125">47</span></span>|<span data-ttu-id="ee9c7-126">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="ee9c7-126">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="ee9c7-127">SharePoint Online 中檔案的網路釣魚和惡意程式碼事件、商務 OneDrive，以及 Office 365 高級威脅防護中的 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="ee9c7-127">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="ee9c7-128">64</span><span class="sxs-lookup"><span data-stu-id="ee9c7-128">64</span></span>|<span data-ttu-id="ee9c7-129">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="ee9c7-129">AirInvestigation</span></span>|<span data-ttu-id="ee9c7-130">自動調查和回應事件，例如調查詳細資料和 Office 365 的相關專案。高級威脅防護方案2。</span><span class="sxs-lookup"><span data-stu-id="ee9c7-130">Automated investigation and response events, such as investigation details and relevant artifacts from Office 365 Advanced Threat Protection Plan 2.</span></span>|


> [!IMPORTANT]
> <span data-ttu-id="ee9c7-131">您必須是全域系統管理員或已指派安全性 & 規範中心的安全性系統管理員角色，才能設定與 Office 365 高級威脅防護的 SIEM 整合。</span><span class="sxs-lookup"><span data-stu-id="ee9c7-131">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="ee9c7-132">您的 Microsoft 365 環境必須開啟審核記錄。</span><span class="sxs-lookup"><span data-stu-id="ee9c7-132">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="ee9c7-133">若要取得此相關協助，請參閱[開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="ee9c7-133">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ee9c7-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="ee9c7-134">Related topics</span></span>

[<span data-ttu-id="ee9c7-135">Office 365 威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="ee9c7-135">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="ee9c7-136">Office 365 中的自動化調查和回應（AIR）</span><span class="sxs-lookup"><span data-stu-id="ee9c7-136">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

[<span data-ttu-id="ee9c7-137">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="ee9c7-137">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="ee9c7-138">安全性&amp;與合規性中心的智慧報告和洞察力</span><span class="sxs-lookup"><span data-stu-id="ee9c7-138">Smart reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="ee9c7-139">安全性&amp;與合規性中心的許可權</span><span class="sxs-lookup"><span data-stu-id="ee9c7-139">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  
