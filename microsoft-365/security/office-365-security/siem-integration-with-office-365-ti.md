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
# <a name="siem-integration-with-advanced-threat-protection"></a>SIEM 與高級威脅防護的整合

如果您的組織使用安全性事件和事件管理（SIEM）伺服器，您可以將 Office 365 的高級威脅防護與您的 SIEM 伺服器整合。 SIEM 整合可讓您在 SIEM 伺服器報告中查看 Office 365 Advanced Protection 偵測到的惡意程式碼或網路釣魚資訊（例如惡意程式碼或網路釣魚）。 若要設定 SIEM 整合，您可以使用[Office 365 活動管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。 

Office 365 活動管理 API 會從您組織的 Microsoft 365 for business 和 Azure Active Directory 活動記錄檔中，檢索使用者、系統管理、系統及原則動作和事件的相關資訊。 [Office 365 Advanced 威脅防護架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)使用高級威脅防護功能，因此如果您的組織有 Office 365 高級威脅防護方案1或 Plan 2 或 Office 365 E5，您仍然可以使用該相同 API 進行 SIEM server 整合。 

做為我們最近的更新的一部分，我們也新增了一些事件，來自于 office 365 管理活動 API 內，Office 365 ATP 方案2中自動調查和回應功能的事件。 除了包含有關核心調查詳細資料（例如識別碼、名稱及狀態）的資料之外，它還包含有關調查動作和實體的高層級資訊。   

SIEM server 或其他類似系統應輪詢此**審核。一般**工作負載來存取偵測事件。 若要深入瞭解，請參閱[開始使用 Office 365 管理 APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。 此外，下列**AuditLogRecordType**值是與 OFFICE 365 ATP 事件相關的：

### <a name="enum-auditlogrecordtype---type-edmint32"></a>列舉： AuditLogRecordType-類型： Edm

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

|值|成員名稱|描述|
|:-----|:-----|:-----|
|日|ThreatIntelligence|來自 Exchange Online Protection 和 Office 365 高級威脅防護的網路釣魚和惡意程式碼事件。|
|41|ThreatIntelligenceUrl|ATP 安全連結從 Office 365 高級威脅防護的封鎖時間和封鎖覆寫事件。|
|47|ThreatIntelligenceAtpContent|SharePoint Online 中檔案的網路釣魚和惡意程式碼事件、商務 OneDrive，以及 Office 365 高級威脅防護中的 Microsoft 團隊。|
|64|AirInvestigation|自動調查和回應事件，例如調查詳細資料和 Office 365 的相關專案。高級威脅防護方案2。|


> [!IMPORTANT]
> 您必須是全域系統管理員或已指派安全性 & 規範中心的安全性系統管理員角色，才能設定與 Office 365 高級威脅防護的 SIEM 整合。<br/>您的 Microsoft 365 環境必須開啟審核記錄。 若要取得此相關協助，請參閱[開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="related-topics"></a>相關主題

[Office 365 威脅調查及回應](office-365-ti.md)

[Office 365 中的自動化調查和回應（AIR）](automated-investigation-response-office.md)

[Office 365 進階威脅防護](office-365-atp.md)

[安全性&amp;與合規性中心的智慧報告和洞察力](reports-and-insights-in-security-and-compliance.md)
  
[安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)
  
