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
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 將組織的 SIEM 伺服器與 office 365 的高級威脅防護和相關威脅事件，與 Office 365 活動管理 API 整合。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c4c92fc45546d3d8022a3925baa9c10f9bd0090b
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600550"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="85814-103">SIEM 與高級威脅防護的整合</span><span class="sxs-lookup"><span data-stu-id="85814-103">SIEM integration with Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="85814-104">如果您的組織使用安全性資訊和事件管理 (SIEM) server，您可以將 365 Office 365 的「高級威脅防護」與 SIEM server 整合 (Office ATP) 。</span><span class="sxs-lookup"><span data-stu-id="85814-104">If your organization is using a security information and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection (Office 365 ATP) with your SIEM server.</span></span> <span data-ttu-id="85814-105">您可以使用 [Office 365 活動管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)設定這種整合方式。</span><span class="sxs-lookup"><span data-stu-id="85814-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="85814-106">SIEM 整合可讓您在 SIEM 伺服器報告中查看 Office 365 ATP 所偵測到的惡意程式碼或網路釣魚資訊，例如惡意程式碼或網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="85814-106">SIEM integration enables you to view information, such as malware or phish detected by Office 365 ATP, in your SIEM server reports.</span></span> 

- <span data-ttu-id="85814-107">若要查看與 Office 365 ATP SIEM 整合的範例，請參閱 [技術社區博客：使用 Office 365 ATP 和 O365 管理 API，提高 SOC 的效能](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。</span><span class="sxs-lookup"><span data-stu-id="85814-107">To see an example of SIEM integration with Office 365 ATP, see [Tech Community blog: Improve the Effectiveness of your SOC with Office 365 ATP and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="85814-108">若要深入瞭解 Office 365 管理 APIs，請參閱 [office 365 管理 APIs 簡介](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)。</span><span class="sxs-lookup"><span data-stu-id="85814-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="85814-109">SIEM 整合的運作方式</span><span class="sxs-lookup"><span data-stu-id="85814-109">How SIEM integration works</span></span>

<span data-ttu-id="85814-110">Office 365 活動管理 API 會從您組織的 Microsoft 365 和 Azure Active Directory 活動記錄檔中，檢索使用者、系統管理員、系統及原則動作和事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="85814-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="85814-111">如果您的組織有 Office 365 ATP Plan 1 或2或 Office 365 E5，您可以使用 [office 365 atp 架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)。</span><span class="sxs-lookup"><span data-stu-id="85814-111">If your organization has Office 365 ATP Plan 1 or 2, or Office 365 E5, you can use the [Office 365 ATP schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>  

<span data-ttu-id="85814-112">最近， [office 365 ATP 方案 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) 中的自動調查和回應功能的事件已新增至 Office 365 管理活動 API。</span><span class="sxs-lookup"><span data-stu-id="85814-112">Recently, events from automated investigation and response capabilities in [Office 365 ATP Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="85814-113">除了包含有關核心調查詳細資料的資料（例如識別碼、名稱和狀態）之外，該 API 也包含有關調查動作和實體的高層級資訊。</span><span class="sxs-lookup"><span data-stu-id="85814-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="85814-114">SIEM server 或其他類似系統會輪詢此 **審核。一般** 工作負載來存取偵測事件。</span><span class="sxs-lookup"><span data-stu-id="85814-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="85814-115">若要深入瞭解，請參閱 [Office 365 管理 APIs 快速入門](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="85814-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="85814-116">列舉： AuditLogRecordType-類型： Edm</span><span class="sxs-lookup"><span data-stu-id="85814-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="85814-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="85814-117">AuditLogRecordType</span></span>

<span data-ttu-id="85814-118">下表摘要說明適用于 Office 365 ATP 事件的 **AuditLogRecordType** 值：</span><span class="sxs-lookup"><span data-stu-id="85814-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Office 365 ATP events:</span></span>

|<span data-ttu-id="85814-119">值</span><span class="sxs-lookup"><span data-stu-id="85814-119">Value</span></span>|<span data-ttu-id="85814-120">成員名稱</span><span class="sxs-lookup"><span data-stu-id="85814-120">Member name</span></span>|<span data-ttu-id="85814-121">描述</span><span class="sxs-lookup"><span data-stu-id="85814-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="85814-122">日</span><span class="sxs-lookup"><span data-stu-id="85814-122">28</span></span>|<span data-ttu-id="85814-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="85814-123">ThreatIntelligence</span></span>|<span data-ttu-id="85814-124">Exchange Online Protection 和 Office 365 ATP 中的網路釣魚和惡意程式碼事件。</span><span class="sxs-lookup"><span data-stu-id="85814-124">Phishing and malware events from Exchange Online Protection and Office 365 ATP.</span></span>|
|<span data-ttu-id="85814-125">41</span><span class="sxs-lookup"><span data-stu-id="85814-125">41</span></span>|<span data-ttu-id="85814-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="85814-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="85814-127">安全連結來自 Office 365 ATP 的封鎖時間與封鎖覆寫事件。</span><span class="sxs-lookup"><span data-stu-id="85814-127">Safe Links time-of-block and block override events from Office 365 ATP.</span></span>|
|<span data-ttu-id="85814-128">47</span><span class="sxs-lookup"><span data-stu-id="85814-128">47</span></span>|<span data-ttu-id="85814-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="85814-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="85814-130">來自 Office 365 ATP 的 SharePoint Online 中的檔案、商務 OneDrive 商務和 Microsoft 小組檔案的網路釣魚和惡意程式碼事件。</span><span class="sxs-lookup"><span data-stu-id="85814-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Office 365 ATP.</span></span>|
|<span data-ttu-id="85814-131">64</span><span class="sxs-lookup"><span data-stu-id="85814-131">64</span></span>|<span data-ttu-id="85814-132">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="85814-132">AirInvestigation</span></span>|<span data-ttu-id="85814-133">自動調查和回應事件，例如從 Office 365 ATP 方案2調查詳細資料和相關的偽像。</span><span class="sxs-lookup"><span data-stu-id="85814-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Office 365 ATP Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="85814-134">您必須是全域系統管理員或已指派安全性 & 規範中心的安全性系統管理員角色，才能設定與 Office 365 高級威脅防護的 SIEM 整合。</span><span class="sxs-lookup"><span data-stu-id="85814-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="85814-135">您的 Microsoft 365 環境必須開啟審核記錄。</span><span class="sxs-lookup"><span data-stu-id="85814-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="85814-136">若要取得此相關協助，請參閱 [開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="85814-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="85814-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="85814-137">See also</span></span>

[<span data-ttu-id="85814-138">Office 365 威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="85814-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="85814-139">Office 365 中的自動調查和回應 (AIR) </span><span class="sxs-lookup"><span data-stu-id="85814-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

