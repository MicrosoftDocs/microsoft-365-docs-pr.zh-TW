---
title: Office 365 進階威脅防護的 SIEM 整合
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
description: 將貴組織的 SIEM 伺服器整合與 Office 365 進階威脅防護和 Office 365 活動管理 API 中的相關的威脅事件。
ms.openlocfilehash: 8a870e02a37ea7f4961d0b8dc42a49cb59d2bace
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598280"
---
# <a name="siem-integration-with-office-365-advanced-threat-protection"></a><span data-ttu-id="0d342-103">Office 365 進階威脅防護的 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="0d342-103">SIEM integration with Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="0d342-104">如果您的組織使用的安全性事件和事件管理 (SIEM) 伺服器，您可以使用 SIEM 伺服器整合 Office 365 進階威脅防護。</span><span class="sxs-lookup"><span data-stu-id="0d342-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="0d342-105">SIEM 整合可讓您檢視資訊，例如惡意程式碼或在 SIEM 伺服器報表中 Office 365 進階防護，所偵測到的釣魚程式。</span><span class="sxs-lookup"><span data-stu-id="0d342-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="0d342-106">若要設定 SIEM 整合，您可以使用[Office 365 活動管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="0d342-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="0d342-107">Office 365 活動管理 API 從貴組織的 Office 365 和 Azure Active Directory 活動記錄檔擷取使用者、 系統、 系統及原則動作和事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0d342-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="0d342-108">[Office 365 進階威脅防護結構描述](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)搭配進階威脅防護，因此如果您的組織有 Office 365 進階威脅防護方案 1 或方案 2 或 Office 365 E5，您仍然可以使用該相同的 API 您 SIEM 伺服器整合。</span><span class="sxs-lookup"><span data-stu-id="0d342-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="0d342-109">我們新版更新的一部分，我們也新增了事件自動化的調查及回應功能，在 Office 365 ATP 計劃 2 中 Office 365 管理活動 API。</span><span class="sxs-lookup"><span data-stu-id="0d342-109">As part of our recent updates, we have also added events from automated investigation and response capabilities in Office 365 ATP Plan 2 within the Office 365 Management Activity API.</span></span> <span data-ttu-id="0d342-110">除了包括核心調查詳細資料，例如 ID、 名稱和狀態的相關資料，它也會包含調查動作和實體的高階資訊。</span><span class="sxs-lookup"><span data-stu-id="0d342-110">In addition to including data about core investigation details such as ID, name and status, it also contains high-level information about investigation actions and entities.</span></span>   

<span data-ttu-id="0d342-111">SIEM 伺服器或其他相似 system 應輪詢 access 偵測事件**audit.general**工作負載。</span><span class="sxs-lookup"><span data-stu-id="0d342-111">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="0d342-112">若要深入了解，請參閱[開始使用 Office 365 管理 Api](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="0d342-112">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="0d342-113">此外，下列值的**AuditLogRecordType**是相關的 Office 365 ATP 事件：</span><span class="sxs-lookup"><span data-stu-id="0d342-113">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="0d342-114">列舉： AuditLogRecordType-類型： Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="0d342-114">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="0d342-115">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="0d342-115">AuditLogRecordType</span></span>

|<span data-ttu-id="0d342-116">值</span><span class="sxs-lookup"><span data-stu-id="0d342-116">Value</span></span>|<span data-ttu-id="0d342-117">成員名稱</span><span class="sxs-lookup"><span data-stu-id="0d342-117">Member name</span></span>|<span data-ttu-id="0d342-118">描述</span><span class="sxs-lookup"><span data-stu-id="0d342-118">Description</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0d342-119">28</span><span class="sxs-lookup"><span data-stu-id="0d342-119">28</span></span>|<span data-ttu-id="0d342-120">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="0d342-120">ThreatIntelligence</span></span>|<span data-ttu-id="0d342-121">從 Exchange Online Protection 和 Office 365 進階威脅防護的網路釣魚和惡意程式碼事件。</span><span class="sxs-lookup"><span data-stu-id="0d342-121">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="0d342-122">41</span><span class="sxs-lookup"><span data-stu-id="0d342-122">41</span></span>|<span data-ttu-id="0d342-123">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="0d342-123">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="0d342-124">ATP 安全連結區塊時間] 與 [封鎖覆寫來自 Office 365 進階威脅防護的事件。</span><span class="sxs-lookup"><span data-stu-id="0d342-124">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="0d342-125">47</span><span class="sxs-lookup"><span data-stu-id="0d342-125">47</span></span>|<span data-ttu-id="0d342-126">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="0d342-126">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="0d342-127">在 SharePoint Online、 OneDrive for Business 和 Microsoft Teams 從 Office 365 進階威脅防護的檔案的網路釣魚和惡意程式碼事件。</span><span class="sxs-lookup"><span data-stu-id="0d342-127">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="0d342-128">64</span><span class="sxs-lookup"><span data-stu-id="0d342-128">64</span></span>|<span data-ttu-id="0d342-129">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="0d342-129">AirInvestigation</span></span>|<span data-ttu-id="0d342-130">自動化調查及回應事件，例如調查的詳細資訊及相關成品從 Office 365 進階威脅防護計劃 2。</span><span class="sxs-lookup"><span data-stu-id="0d342-130">Automated investigation and response events, such as investigation details and relevant artifacts from Office 365 Advanced Threat Protection Plan 2.</span></span>|


> [!IMPORTANT]
> <span data-ttu-id="0d342-131">您必須是 Office 365 全域管理員或具有安全性系統管理員 」 角色指派的安全性 & 合規性中心，以設定 Office 365 進階威脅防護的 SIEM 整合。</span><span class="sxs-lookup"><span data-stu-id="0d342-131">You must be an Office 365 global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="0d342-132">稽核記錄必須開啟適用於 Office 365 環境。</span><span class="sxs-lookup"><span data-stu-id="0d342-132">Audit logging must be turned on for your Office 365 environment.</span></span> <span data-ttu-id="0d342-133">若要取得此問題的協助，請參閱[開啟 Office 365 稽核記錄搜尋的開啟或關閉](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="0d342-133">To get help with this, see [Turn Office 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0d342-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="0d342-134">Related topics</span></span>

[<span data-ttu-id="0d342-135">Office 365 威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="0d342-135">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="0d342-136">自動化的調查和 Office 365 中的回應 （空調）</span><span class="sxs-lookup"><span data-stu-id="0d342-136">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

[<span data-ttu-id="0d342-137">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="0d342-137">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="0d342-138">智慧型報表和深入了解 Office 365 安全性&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="0d342-138">Smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="0d342-139">Office 365 安全性與合規性中心權限</span><span class="sxs-lookup"><span data-stu-id="0d342-139">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  
