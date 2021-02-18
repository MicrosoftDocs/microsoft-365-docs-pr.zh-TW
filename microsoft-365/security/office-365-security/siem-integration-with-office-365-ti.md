---
title: SIEM 與 Microsoft Defender for Office 365 的整合
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 在 Office 365 活動管理 API 中，將組織的 SIEM 伺服器與 Microsoft Defender for Office 365 和相關威脅事件整合在一起。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f637750a31b5034d2ee1110ab0070fa6abcda49b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290390"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="6198f-103">SIEM 與 Microsoft Defender for Office 365 的整合</span><span class="sxs-lookup"><span data-stu-id="6198f-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="6198f-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="6198f-104">**Applies to**</span></span>
- [<span data-ttu-id="6198f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6198f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6198f-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="6198f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="6198f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6198f-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6198f-108">如果您的組織使用安全性資訊和事件管理 (SIEM) server，您可以將 Microsoft Defender for Office 365 與您的 SIEM 伺服器整合。</span><span class="sxs-lookup"><span data-stu-id="6198f-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="6198f-109">您可以使用 [Office 365 活動管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)設定這種整合方式。</span><span class="sxs-lookup"><span data-stu-id="6198f-109">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="6198f-110">SIEM 整合可讓您查看 SIEM 伺服器報告中的資訊，例如 Microsoft Defender for Office 365 偵測到的惡意程式碼或網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="6198f-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="6198f-111">若要查看 SIEM 與 Microsoft Defender for Office 365 整合的範例，請參閱 [技術社區博客：使用 office 365 的 defender 和 O365 管理 API，改善 SOC 的效能](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。</span><span class="sxs-lookup"><span data-stu-id="6198f-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="6198f-112">若要深入瞭解 Office 365 管理 APIs，請參閱 [office 365 管理 APIs 簡介](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)。</span><span class="sxs-lookup"><span data-stu-id="6198f-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="6198f-113">SIEM 整合的運作方式</span><span class="sxs-lookup"><span data-stu-id="6198f-113">How SIEM integration works</span></span>

<span data-ttu-id="6198f-114">Office 365 活動管理 API 會從您組織的 Microsoft 365 和 Azure Active Directory 活動記錄檔中，檢索使用者、系統管理員、系統及原則動作和事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6198f-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="6198f-115">如果您的組織有 Microsoft Defender for Office 365 方案1或2，或 Office 365 E5，您可以使用 [Microsoft defender For office 365 架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)。</span><span class="sxs-lookup"><span data-stu-id="6198f-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="6198f-116">最近， [Microsoft Defender For office 365 方案 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 中的自動調查和回應功能的事件已新增至 Office 365 管理活動 API。</span><span class="sxs-lookup"><span data-stu-id="6198f-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="6198f-117">除了包含有關核心調查詳細資料的資料（例如識別碼、名稱和狀態）之外，該 API 也包含有關調查動作和實體的高層級資訊。</span><span class="sxs-lookup"><span data-stu-id="6198f-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="6198f-118">SIEM server 或其他類似系統會輪詢此 **審核。一般** 工作負載來存取偵測事件。</span><span class="sxs-lookup"><span data-stu-id="6198f-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="6198f-119">若要深入瞭解，請參閱 [Office 365 管理 APIs 快速入門](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="6198f-119">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="6198f-120">列舉： AuditLogRecordType-類型： Edm</span><span class="sxs-lookup"><span data-stu-id="6198f-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="6198f-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="6198f-121">AuditLogRecordType</span></span>

<span data-ttu-id="6198f-122">下表摘要說明 Microsoft Defender for Office 365 事件相關的 **AuditLogRecordType** 值：</span><span class="sxs-lookup"><span data-stu-id="6198f-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="6198f-123">值</span><span class="sxs-lookup"><span data-stu-id="6198f-123">Value</span></span>|<span data-ttu-id="6198f-124">成員名稱</span><span class="sxs-lookup"><span data-stu-id="6198f-124">Member name</span></span>|<span data-ttu-id="6198f-125">描述</span><span class="sxs-lookup"><span data-stu-id="6198f-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="6198f-126">日</span><span class="sxs-lookup"><span data-stu-id="6198f-126">28</span></span>|<span data-ttu-id="6198f-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="6198f-127">ThreatIntelligence</span></span>|<span data-ttu-id="6198f-128">Exchange Online Protection 和 Microsoft Defender for Office 365 的網路釣魚和惡意程式碼事件。</span><span class="sxs-lookup"><span data-stu-id="6198f-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="6198f-129">41</span><span class="sxs-lookup"><span data-stu-id="6198f-129">41</span></span>|<span data-ttu-id="6198f-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="6198f-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="6198f-131">安全連結來自 Microsoft Defender for Office 365 的封鎖時間和封鎖覆寫事件。</span><span class="sxs-lookup"><span data-stu-id="6198f-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="6198f-132">47</span><span class="sxs-lookup"><span data-stu-id="6198f-132">47</span></span>|<span data-ttu-id="6198f-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="6198f-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="6198f-134">Microsoft Defender for Office 365 中 SharePoint Online、商務小組 OneDrive 的檔案的網路釣魚和惡意程式碼事件。</span><span class="sxs-lookup"><span data-stu-id="6198f-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="6198f-135">64</span><span class="sxs-lookup"><span data-stu-id="6198f-135">64</span></span>|<span data-ttu-id="6198f-136">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="6198f-136">AirInvestigation</span></span>|<span data-ttu-id="6198f-137">來自 Microsoft Defender for Office 365 方案2的自動化調查和回應事件，例如調查詳細資料和相關的專案。</span><span class="sxs-lookup"><span data-stu-id="6198f-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="6198f-138">您必須是全域系統管理員，或已指派安全性 & 規範中心的安全性系統管理員角色，才能設定與 Microsoft Defender for Office 365 的 SIEM 整合。</span><span class="sxs-lookup"><span data-stu-id="6198f-138">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="6198f-139">您的 Microsoft 365 環境必須開啟審核記錄。</span><span class="sxs-lookup"><span data-stu-id="6198f-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="6198f-140">若要取得此相關協助，請參閱 [開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="6198f-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6198f-141">請參閱</span><span class="sxs-lookup"><span data-stu-id="6198f-141">See also</span></span>

[<span data-ttu-id="6198f-142">Office 365 威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="6198f-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="6198f-143">Office 365 中的自動調查和回應 (AIR) </span><span class="sxs-lookup"><span data-stu-id="6198f-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

