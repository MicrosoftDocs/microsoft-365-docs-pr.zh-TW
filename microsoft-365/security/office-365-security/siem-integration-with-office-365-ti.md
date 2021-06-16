---
title: SIEM 與適用于 Microsoft Defender 的 Office 365 整合
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 針對 Office 365 活動管理 API 中的 Office 365 和相關威脅事件，將組織的 SIEM 伺服器與 Microsoft Defender 整合。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f3d6bbacb4a64060ecd03cbb28eee3256f41827e
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929776"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>SIEM 與適用于 Microsoft Defender 的 Office 365 整合

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


如果您的組織使用安全性資訊和事件管理 (SIEM) server，您可以整合 Microsoft Defender 以 Office 365 與 SIEM server。 您可以使用[Office 365 活動管理 API](/office/office-365-management-api/office-365-management-activity-api-reference)設定這種整合方式。

SIEM 整合可讓您在 SIEM 伺服器報告中查看 Microsoft Defender Office 365 所偵測到的資訊，例如惡意程式碼或網路釣魚。

- 若要查看與 Office 365 的 Microsoft Defender 整合 SIEM 整合的範例，請參閱[技術 Community 博客：使用使用 Defender for Office 365 和 O365 管理 API，提高 SOC 的效能](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。

- 若要深入瞭解 Office 365 管理 APIs，請參閱[Office 365 管理 APIs 概述](/office/office-365-management-api/office-365-management-apis-overview)。

## <a name="how-siem-integration-works"></a>SIEM 整合的運作方式

Office 365 活動管理 API 會從您組織的 Microsoft 365 和 Azure Active Directory 活動記錄檔中，檢索使用者、系統管理員、系統及原則動作和事件的相關資訊。 如果貴組織的 microsoft defender Office 365 方案1或2，或是 Office 365 E5，您可以使用[microsoft defender for Office 365 schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)。

最近，已將[Microsoft Defender 中 Office 365 方案 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)之自動調查和回應功能的事件新增至 Office 365 管理活動 API。 除了包含有關核心調查詳細資料的資料（例如識別碼、名稱和狀態）之外，該 API 也包含有關調查動作和實體的高層級資訊。

SIEM server 或其他類似系統會輪詢此 **審核。一般** 工作負載來存取偵測事件。 若要深入瞭解，請參閱[Office 365 管理 APIs 快速入門](/office/office-365-management-api/get-started-with-office-365-management-apis)。

## <a name="enum-auditlogrecordtype---type-edmint32"></a>列舉： AuditLogRecordType-類型： Edm

### <a name="auditlogrecordtype"></a>AuditLogRecordType

下表摘要說明 Office 365 事件的 Microsoft Defender 相關的 **AuditLogRecordType** 值：

|值|成員名稱|描述|
|---|---|---|
|日|ThreatIntelligence|來自 Exchange Online Protection 和 Microsoft Defender for Office 365 的網路釣魚和惡意程式碼事件。|
|41|ThreatIntelligenceUrl|安全連結從 Microsoft Defender 取得 Office 365 的封鎖時間及封鎖覆寫事件。|
|47|ThreatIntelligenceAtpContent|Microsoft Defender for Office 365 中 SharePoint 線上、商務用 OneDrive 及 Microsoft Teams 中檔案的網路釣魚和惡意程式碼事件。|
|64|AirInvestigation|自動調查和回應事件，例如調查詳細資料和相關的專案，來自 Microsoft Defender for Office 365 Plan 2。|
|

> [!IMPORTANT]
> 您必須是全域系統管理員，或擁有為 Microsoft 365 defender 入口網站指派的安全性系統管理員角色，才能為 Office 365 設定與 Microsoft defender 的 SIEM 整合。
>
> 您的 Microsoft 365 環境必須開啟審核記錄。 若要取得此相關協助，請參閱 [開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="see-also"></a>另請參閱

[Office 365 威脅調查及回應](office-365-ti.md)

[ (空中) Office 365 中的自動化調查和回應](automated-investigation-response-office.md)